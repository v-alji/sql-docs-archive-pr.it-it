---
title: Regole di confronto dei database indipendenti | Microsoft Docs
ms.custom: ''
ms.date: 07/17/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- contained database, collations
ms.assetid: 4b44f6b9-2359-452f-8bb1-5520f2528483
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2648dbedea7708c4f39c922c56bba96cf38b0c0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718245"
---
# <a name="contained-database-collations"></a><span data-ttu-id="ffe08-102">Regole di confronto dei database indipendenti</span><span class="sxs-lookup"><span data-stu-id="ffe08-102">Contained Database Collations</span></span>
  <span data-ttu-id="ffe08-103">Varie proprietà incidono sull'ordinamento e sulla semantica di uguaglianza dei dati testuali, ad esempio distinzione maiuscole/minuscole, distinzione caratteri accentati/non accentati e linguaggio di base utilizzato.</span><span class="sxs-lookup"><span data-stu-id="ffe08-103">Various properties affect the sort order and equality semantics of textual data, including case sensitivity, accent sensitivity, and the base language being used.</span></span> <span data-ttu-id="ffe08-104">Queste qualità vengono espresse in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite la scelta di regole di confronto per i dati.</span><span class="sxs-lookup"><span data-stu-id="ffe08-104">These qualities are expressed to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the choice of collation for the data.</span></span> <span data-ttu-id="ffe08-105">Per informazioni dettagliate sulle regole di confronto, vedere [Regole di confronto e supporto Unicode](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="ffe08-105">For a more in-depth discussion of collations themselves, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="ffe08-106">Le regole di confronto si applicano non solo ai dati archiviati nelle tabelle utente, ma a tutto il testo gestito da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], inclusi metadati, oggetti temporanei, nomi di variabili e così via. La gestione di tali elementi risulta diversa nei database indipendenti rispetto a quelli non indipendenti.</span><span class="sxs-lookup"><span data-stu-id="ffe08-106">Collations apply not only to data stored in user tables, but to all text handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], including metadata, temporary objects, variable names, etc. The handling of these differs in contained and non-contained databases.</span></span> <span data-ttu-id="ffe08-107">Questa modifica non interesserà molti utenti, ma contribuirà ad assicurare uniformità e indipendenza dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="ffe08-107">This change will not affect many users, but helps provide instance independence and uniformity.</span></span> <span data-ttu-id="ffe08-108">È tuttavia possibile che sia anche causa di qualche confusione, nonché di problemi per le sessioni che accedono sia a database indipendenti che non indipendenti.</span><span class="sxs-lookup"><span data-stu-id="ffe08-108">But this may also cause some confusion, as well as problems for sessions that access both contained and non-contained databases.</span></span>  
  
 <span data-ttu-id="ffe08-109">In questo argomento si illustra il contenuto della modifica e si esaminano alcune aree in cui tale modifica potrebbe causare problemi.</span><span class="sxs-lookup"><span data-stu-id="ffe08-109">This topic clarifies the content of the change, and examines areas where the change may cause problems.</span></span>  
  
## <a name="non-contained-databases"></a><span data-ttu-id="ffe08-110">Database non indipendenti</span><span class="sxs-lookup"><span data-stu-id="ffe08-110">Non-Contained Databases</span></span>  
 <span data-ttu-id="ffe08-111">A tutti i database sono associate regole di confronto predefinite, che possono essere impostate quando si crea o si modifica un database.</span><span class="sxs-lookup"><span data-stu-id="ffe08-111">All databases have a default collation (which can be set when creating or altering a database.</span></span> <span data-ttu-id="ffe08-112">Queste regole di confronto vengono utilizzate per tutti i metadati presenti nel database e come impostazione predefinita per tutte le colonne stringa all'interno del database.</span><span class="sxs-lookup"><span data-stu-id="ffe08-112">This collation is used for all metadata in the database, as well as the default for all string columns within the database.</span></span> <span data-ttu-id="ffe08-113">Gli utenti possono scegliere regole di confronto diverse per qualsiasi colonna specifica tramite la clausola `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="ffe08-113">Users can choose a different collation for any particular column by using the `COLLATE` clause.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="ffe08-114">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="ffe08-114">Example 1</span></span>  
 <span data-ttu-id="ffe08-115">Se si lavora ad esempio a Pechino, è possibile che venga utilizzata una regola di confronto cinese:</span><span class="sxs-lookup"><span data-stu-id="ffe08-115">For example, if we were working in Beijing, we might use a Chinese collation:</span></span>  
  
```sql  
ALTER DATABASE MyDB COLLATE Chinese_Simplified_Pinyin_100_CI_AS;  
```  
  
 <span data-ttu-id="ffe08-116">Se ora si crea una colonna, le relative regole di confronto predefinite saranno quelle cinesi, ma è possibile sceglierne altre, se lo si desidera:</span><span class="sxs-lookup"><span data-stu-id="ffe08-116">Now if we create a column, its default collation will be this Chinese collation, but we can choose another one if we want:</span></span>  
  
```sql  
CREATE TABLE MyTable  
      (mycolumn1 nvarchar,  
      mycolumn2 nvarchar COLLATE Frisian_100_CS_AS);  
GO  
SELECT name, collation_name  
FROM sys.columns  
WHERE name LIKE 'mycolumn%' ;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```sql  
name            collation_name  
--------------- ----------------------------------  
mycolumn1       Chinese_Simplified_Pinyin_100_CI_AS  
mycolumn2       Frisian_100_CS_AS  
```  
  
 <span data-ttu-id="ffe08-117">Questo approccio sembra relativamente semplice, ma insorgono vari problemi.</span><span class="sxs-lookup"><span data-stu-id="ffe08-117">This appears relatively simple, but several problems arise.</span></span> <span data-ttu-id="ffe08-118">Poiché le regole di confronto per una colonna dipendono dal database in cui viene creata la tabella, si verificano problemi con l'utilizzo di tabelle temporanee archiviate in `tempdb` .</span><span class="sxs-lookup"><span data-stu-id="ffe08-118">Because the collation for a column is dependent on the database in which the table is created, problems arise with the use of temporary tables which are stored in `tempdb`.</span></span> <span data-ttu-id="ffe08-119">Le regole di confronto di `tempdb` in genere corrispondono alle regole di confronto per l'istanza di, che non devono corrispondere alle regole di confronto del database.</span><span class="sxs-lookup"><span data-stu-id="ffe08-119">The collation of `tempdb` usually matches the collation for the instance, which does not have to match the database collation.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="ffe08-120">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="ffe08-120">Example 2</span></span>  
 <span data-ttu-id="ffe08-121">Si consideri, ad esempio, il database precedente (cinese) usato in un'istanza con regole di confronto **Latin1_General** :</span><span class="sxs-lookup"><span data-stu-id="ffe08-121">For example, consider the (Chinese) database above when used on an instance with a **Latin1_General** collation:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max)) ;  
GO  
```  
  
 <span data-ttu-id="ffe08-122">A prima vista queste due tabelle hanno apparentemente lo stesso schema, ma poiché le regole di confronto dei database sono diverse, i valori sono in effetti incompatibili:</span><span class="sxs-lookup"><span data-stu-id="ffe08-122">At first glance, these two tables look like they have the same schema, but since the collations of the databases differ, the values are actually incompatible:</span></span>  
  
```  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="ffe08-123">Messaggio 468, livello 16, stato 9, riga 2</span><span class="sxs-lookup"><span data-stu-id="ffe08-123">Msg 468, Level 16, State 9, Line 2</span></span>  
  
 <span data-ttu-id="ffe08-124">Impossibile risolvere il conflitto tra le regole di confronto "Latin1_General_100_CI_AS_KS_WS_SC" e "Chinese_Simplified_Pinyin_100_CI_AS" nell'operazione uguale a.</span><span class="sxs-lookup"><span data-stu-id="ffe08-124">Cannot resolve the collation conflict between "Latin1_General_100_CI_AS_KS_WS_SC" and Chinese_Simplified_Pinyin_100_CI_AS" in the equal to operation.</span></span>  
  
 <span data-ttu-id="ffe08-125">Per correggere questo problema è necessario confrontare esplicitamente la tabella temporanea.</span><span class="sxs-lookup"><span data-stu-id="ffe08-125">We can fix this by explicitly collating the temporary table.</span></span> <span data-ttu-id="ffe08-126">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] questa operazione è resa più semplice perché viene fornita la parola chiave `DATABASE_DEFAULT` per la clausola `COLLATE`.</span><span class="sxs-lookup"><span data-stu-id="ffe08-126">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] makes this somewhat easier by providing the `DATABASE_DEFAULT` keyword for the `COLLATE` clause.</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max) COLLATE DATABASE_DEFAULT);  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="ffe08-127">A questo punto l'esecuzione avviene senza errori.</span><span class="sxs-lookup"><span data-stu-id="ffe08-127">This now runs without error.</span></span>  
  
 <span data-ttu-id="ffe08-128">Il comportamento dipendente dalle regole di confronto è rilevabile anche con le variabili.</span><span class="sxs-lookup"><span data-stu-id="ffe08-128">We can also see collation-dependent behavior with variables.</span></span> <span data-ttu-id="ffe08-129">Si consideri la funzione seguente:</span><span class="sxs-lookup"><span data-stu-id="ffe08-129">Consider the following function:</span></span>  
  
```  
CREATE FUNCTION f(@x INT) RETURNS INT  
AS BEGIN   
      DECLARE @I INT = 1  
      DECLARE @?? INT = 2  
      RETURN @x * @i  
END;  
```  
  
 <span data-ttu-id="ffe08-130">Si tratta di una funzione piuttosto particolare.</span><span class="sxs-lookup"><span data-stu-id="ffe08-130">This is a rather peculiar function.</span></span> <span data-ttu-id="ffe08-131">Nelle regole di confronto con distinzione tra maiuscole e minuscole, nella @i clausola return non è possibile eseguire l'associazione a @I o @??.</span><span class="sxs-lookup"><span data-stu-id="ffe08-131">In a case-sensitive collation, the @i in the return clause cannot bind to either @I or @??.</span></span> <span data-ttu-id="ffe08-132">Nelle regole di confronto Latin1_General senza distinzione tra maiuscole e minuscole, @i viene associato a @I e la funzione restituisce 1.</span><span class="sxs-lookup"><span data-stu-id="ffe08-132">In a case-insensitive Latin1_General collation, @i binds to @I, and the function returns 1.</span></span> <span data-ttu-id="ffe08-133">Tuttavia, nelle regole di confronto turche senza distinzione tra maiuscole e minuscole, viene @i associato a @??, e la funzione restituisce 2.</span><span class="sxs-lookup"><span data-stu-id="ffe08-133">But in a case-insensitive Turkish collation, @i binds to @??, and the function returns 2.</span></span> <span data-ttu-id="ffe08-134">Questa funzione può causare seri problemi in un database che passa da un'istanza all'altra con regole di confronto diverse.</span><span class="sxs-lookup"><span data-stu-id="ffe08-134">This can wreak havoc on a database that moves between instances with different collations.</span></span>  
  
## <a name="contained-databases"></a><span data-ttu-id="ffe08-135">Database indipendenti</span><span class="sxs-lookup"><span data-stu-id="ffe08-135">Contained Databases</span></span>  
 <span data-ttu-id="ffe08-136">Poiché uno degli obiettivi di progettazione dei database indipendenti è di renderli autosufficienti, è necessario eliminare la dipendenza dalle regole di confronto di istanza e `tempdb`.</span><span class="sxs-lookup"><span data-stu-id="ffe08-136">Since a design objective of contained databases is to make them self-contained, the dependence on the instance and `tempdb` collations must be severed.</span></span> <span data-ttu-id="ffe08-137">A questo scopo, nei database indipendenti viene introdotto il concetto di regole di confronto del catalogo.</span><span class="sxs-lookup"><span data-stu-id="ffe08-137">To do this, contained databases introduce the concept of the catalog collation.</span></span> <span data-ttu-id="ffe08-138">Tali regole vengono utilizzate per metadati di sistema e oggetti temporanei.</span><span class="sxs-lookup"><span data-stu-id="ffe08-138">The catalog collation is used for system metadata and transient objects.</span></span> <span data-ttu-id="ffe08-139">Di seguito vengono illustrati i dettagli.</span><span class="sxs-lookup"><span data-stu-id="ffe08-139">Details are provided below.</span></span>  
  
 <span data-ttu-id="ffe08-140">In un database indipendente vengono usate le regole di confronto del catalogo **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="ffe08-140">In a contained database, the catalog collation **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="ffe08-141">Si tratta delle stesse regole di confronto per tutti i database indipendenti in tutte le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e non è possibile modificarle.</span><span class="sxs-lookup"><span data-stu-id="ffe08-141">This collation is the same for all contained databases on all instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and cannot be changed.</span></span>  
  
 <span data-ttu-id="ffe08-142">Le regole di confronto del database vengono mantenute, ma utilizzate solo come regole di confronto predefinite per i dati utente.</span><span class="sxs-lookup"><span data-stu-id="ffe08-142">The database collation is retained, but is only used as the default collation for user data.</span></span> <span data-ttu-id="ffe08-143">Per impostazione predefinita, le regole di confronto del database sono uguali a quelle del database modello, ma possono essere modificate dall'utente tramite `CREATE` un `ALTER DATABASE` comando o come con i database non indipendenti.</span><span class="sxs-lookup"><span data-stu-id="ffe08-143">By default, the database collation is equal to the model database collation, but can be changed by the user through a `CREATE` or `ALTER DATABASE` command as with non-contained databases.</span></span>  
  
 <span data-ttu-id="ffe08-144">Nella clausola `CATALOG_DEFAULT` è disponibile la nuova parola chiave `COLLATE`,</span><span class="sxs-lookup"><span data-stu-id="ffe08-144">A new keyword, `CATALOG_DEFAULT`, is available in the `COLLATE` clause.</span></span> <span data-ttu-id="ffe08-145">che viene utilizzata come collegamento alle regole di confronto correnti per i metadati nei database indipendenti e non indipendenti.</span><span class="sxs-lookup"><span data-stu-id="ffe08-145">This is used as a shortcut to the current collation of metadata in both contained and non-contained databases.</span></span> <span data-ttu-id="ffe08-146">Vale a dire che, in un database non indipendente, la parola chiave `CATALOG_DEFAULT` restituirà le regole di confronto del database correnti, poiché i metadati vengono confrontati nelle regole di confronto del database.</span><span class="sxs-lookup"><span data-stu-id="ffe08-146">That is, in a non-contained database, `CATALOG_DEFAULT` will return the current database collation, since metadata is collated in the database collation.</span></span> <span data-ttu-id="ffe08-147">In un database indipendente questi due valori potrebbero essere diversi, in quanto l'utente può modificare le regole di confronto del database in modo che non corrispondano alle regole di confronto del catalogo.</span><span class="sxs-lookup"><span data-stu-id="ffe08-147">In a contained database, these two values may be different, since the user can change the database collation so that it does not match the catalog collation.</span></span>  
  
 <span data-ttu-id="ffe08-148">Nella tabella seguente viene riepilogato il comportamento di vari oggetti sia nei database non indipendenti che in quelli indipendenti:</span><span class="sxs-lookup"><span data-stu-id="ffe08-148">The behavior of various objects in both non-contained and contained databases is summarized in this table:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="ffe08-149">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="ffe08-149">**Item**</span></span>|<span data-ttu-id="ffe08-150">**Database non indipendente**</span><span class="sxs-lookup"><span data-stu-id="ffe08-150">**Non-Contained Database**</span></span>|<span data-ttu-id="ffe08-151">**Database indipendente**</span><span class="sxs-lookup"><span data-stu-id="ffe08-151">**Contained Database**</span></span>|  
|<span data-ttu-id="ffe08-152">Dati utente (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="ffe08-152">User Data (default)</span></span>|<span data-ttu-id="ffe08-153">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ffe08-153">DATABASE_DEFAULT</span></span>|<span data-ttu-id="ffe08-154">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ffe08-154">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="ffe08-155">Dati temporanei (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="ffe08-155">Temp Data (default)</span></span>|<span data-ttu-id="ffe08-156">Regole di confronto TempDB</span><span class="sxs-lookup"><span data-stu-id="ffe08-156">TempDB Collation</span></span>|<span data-ttu-id="ffe08-157">DATABASE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ffe08-157">DATABASE_DEFAULT</span></span>|  
|<span data-ttu-id="ffe08-158">Metadati</span><span class="sxs-lookup"><span data-stu-id="ffe08-158">Metadata</span></span>|<span data-ttu-id="ffe08-159">DATABASE_DEFAULT/CATALOG_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="ffe08-159">DATABASE_DEFAULT / CATALOG_DEFAULT</span></span>|<span data-ttu-id="ffe08-160">COLLATE</span><span class="sxs-lookup"><span data-stu-id="ffe08-160">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="ffe08-161">Metadati temporanei</span><span class="sxs-lookup"><span data-stu-id="ffe08-161">Temporary Metadata</span></span>|<span data-ttu-id="ffe08-162">Regole di confronto TempDB</span><span class="sxs-lookup"><span data-stu-id="ffe08-162">tempdb Collation</span></span>|<span data-ttu-id="ffe08-163">COLLATE</span><span class="sxs-lookup"><span data-stu-id="ffe08-163">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="ffe08-164">variables</span><span class="sxs-lookup"><span data-stu-id="ffe08-164">Variables</span></span>|<span data-ttu-id="ffe08-165">Regole di confronto di istanza</span><span class="sxs-lookup"><span data-stu-id="ffe08-165">Instance Collation</span></span>|<span data-ttu-id="ffe08-166">COLLATE</span><span class="sxs-lookup"><span data-stu-id="ffe08-166">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="ffe08-167">Etichette Goto</span><span class="sxs-lookup"><span data-stu-id="ffe08-167">Goto Labels</span></span>|<span data-ttu-id="ffe08-168">Regole di confronto di istanza</span><span class="sxs-lookup"><span data-stu-id="ffe08-168">Instance Collation</span></span>|<span data-ttu-id="ffe08-169">COLLATE</span><span class="sxs-lookup"><span data-stu-id="ffe08-169">CATALOG_DEFAULT</span></span>|  
|<span data-ttu-id="ffe08-170">Nomi di cursori</span><span class="sxs-lookup"><span data-stu-id="ffe08-170">Cursor Names</span></span>|<span data-ttu-id="ffe08-171">Regole di confronto di istanza</span><span class="sxs-lookup"><span data-stu-id="ffe08-171">Instance Collation</span></span>|<span data-ttu-id="ffe08-172">COLLATE</span><span class="sxs-lookup"><span data-stu-id="ffe08-172">CATALOG_DEFAULT</span></span>|  
  
 <span data-ttu-id="ffe08-173">Se si utilizza una tabella temporanea nell'esempio precedentemente descritto, è possibile osservare che questo comportamento delle regole di confronto elimina l'esigenza di una clausola `COLLATE` esplicita nella maggior parte degli usi della tabelle temporanee.</span><span class="sxs-lookup"><span data-stu-id="ffe08-173">If we temp table example previously described, we can see that this collation behavior eliminates the need for an explicit `COLLATE` clause in most temp table uses.</span></span> <span data-ttu-id="ffe08-174">In un database indipendente questo codice ora viene eseguito senza errori, anche se le regole di confronto di database e istanza sono diverse:</span><span class="sxs-lookup"><span data-stu-id="ffe08-174">In a contained database, this code now runs without error, even if the database and instance collations differ:</span></span>  
  
```sql  
CREATE TABLE T1 (T1_txt nvarchar(max)) ;  
GO  
CREATE TABLE #T2 (T2_txt nvarchar(max));  
GO  
SELECT T1_txt, T2_txt  
FROM T1   
JOIN #T2   
    ON T1.T1_txt = #T2.T2_txt ;  
```  
  
 <span data-ttu-id="ffe08-175">Il codice funziona perché il confronto di `T1_txt` e di `T2_txt` viene effettuato nelle regole di confronto del database relative al database indipendente.</span><span class="sxs-lookup"><span data-stu-id="ffe08-175">This works because both `T1_txt` and `T2_txt` are collated in the database collation of the contained database.</span></span>  
  
## <a name="crossing-between-contained-and-uncontained-contexts"></a><span data-ttu-id="ffe08-176">Passaggio tra contesti indipendenti e non indipendenti</span><span class="sxs-lookup"><span data-stu-id="ffe08-176">Crossing Between Contained and Uncontained Contexts</span></span>  
 <span data-ttu-id="ffe08-177">Finché una sessione in un database indipendente rimane indipendente, dovrà rimanere all'interno del database al quale è connessa.</span><span class="sxs-lookup"><span data-stu-id="ffe08-177">As long as a session in a contained database remains contained, it must remain within the database to which it connected.</span></span> <span data-ttu-id="ffe08-178">In questo caso il comportamento è molto chiaro.</span><span class="sxs-lookup"><span data-stu-id="ffe08-178">In this case the behavior is very straightforward.</span></span> <span data-ttu-id="ffe08-179">Se, tuttavia, avviene il passaggio di una sessione tra contesti indipendenti e non indipendenti, il comportamento diventa più complesso, poiché è necessario creare un collegamento tra i due set di regole.</span><span class="sxs-lookup"><span data-stu-id="ffe08-179">But if a session crosses between contained and non-contained contexts, the behavior becomes more complex, since the two sets of rules must be bridged.</span></span> <span data-ttu-id="ffe08-180">Questa condizione può verificarsi in un database parzialmente indipendente, poiché un utente può utilizzare `USE` su un altro database.</span><span class="sxs-lookup"><span data-stu-id="ffe08-180">This can happen in a partially-contained database, since a user may `USE` to another database.</span></span> <span data-ttu-id="ffe08-181">In questo caso, la differenza nelle regole di confronto viene gestita in base al principio seguente.</span><span class="sxs-lookup"><span data-stu-id="ffe08-181">In this case, the difference in collation rules is handled by the following principle.</span></span>  
  
-   <span data-ttu-id="ffe08-182">Il comportamento delle regole di confronto per un batch viene determinato dal database in cui inizia il batch.</span><span class="sxs-lookup"><span data-stu-id="ffe08-182">The collation behavior for a batch is determined by the database in which the batch begins.</span></span>  
  
 <span data-ttu-id="ffe08-183">Questa decisione avviene prima dell'esecuzione di qualsiasi comando, incluso un comando `USE` iniziale.</span><span class="sxs-lookup"><span data-stu-id="ffe08-183">Note that this decision is made before any commands are issued, including an initial `USE`.</span></span> <span data-ttu-id="ffe08-184">Ciò significa che se un batch inizia in un database indipendente, ma il primo comando è `USE` su un database non indipendente, per il batch verrà comunque utilizzato il comportamento delle regole di confronto indipendenti.</span><span class="sxs-lookup"><span data-stu-id="ffe08-184">That is, if a batch begins in a contained database, but the first command is a `USE` to a non-contained database, the contained collation behavior will still be used for the batch.</span></span> <span data-ttu-id="ffe08-185">In questo caso, un riferimento a una variabile, ad esempio, può avere più risultati possibili:</span><span class="sxs-lookup"><span data-stu-id="ffe08-185">Given this, a reference to a variable, for example, may have multiple possible outcomes:</span></span>  
  
-   <span data-ttu-id="ffe08-186">Il riferimento può trovare esattamente una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ffe08-186">The reference may find exactly one match.</span></span> <span data-ttu-id="ffe08-187">In questo caso il riferimento funzionerà senza errori.</span><span class="sxs-lookup"><span data-stu-id="ffe08-187">In this case, the reference will work without error.</span></span>  
  
-   <span data-ttu-id="ffe08-188">Il riferimento può non trovare una corrispondenza nelle regole di confronto correnti dove in precedenza ne era presente una.</span><span class="sxs-lookup"><span data-stu-id="ffe08-188">The reference may not find a match in the current collation where there was one before.</span></span> <span data-ttu-id="ffe08-189">In questo caso verrà generato un errore nel quale è indicato che la variabile non esiste, anche se apparentemente è stata creata.</span><span class="sxs-lookup"><span data-stu-id="ffe08-189">This will raise an error indicating that the variable does not exist, even though it was apparently created.</span></span>  
  
-   <span data-ttu-id="ffe08-190">Il riferimento più trovare più corrispondenze originariamente distinte.</span><span class="sxs-lookup"><span data-stu-id="ffe08-190">The reference may find multiple matches that were originally distinct.</span></span> <span data-ttu-id="ffe08-191">Anche in questo caso verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="ffe08-191">This will also raise an error.</span></span>  
  
 <span data-ttu-id="ffe08-192">Di seguito vengono usati alcuni esempi per illustrare questo comportamento,</span><span class="sxs-lookup"><span data-stu-id="ffe08-192">We'll illustrate this with a few examples.</span></span> <span data-ttu-id="ffe08-193">presupponendo l'uso di un database parzialmente indipendente, denominato `MyCDB` , con regole di confronto del database impostate sulle regole di confronto predefinite **Latin1_General_100_CI_AS_WS_KS_SC**.</span><span class="sxs-lookup"><span data-stu-id="ffe08-193">For these we assume there is a partially-contained database named `MyCDB` with its database collation set to the default collation, **Latin1_General_100_CI_AS_WS_KS_SC**.</span></span> <span data-ttu-id="ffe08-194">Si supponga che le regole di confronto di istanza siano `Latin1_General_100_CS_AS_WS_KS_SC`,</span><span class="sxs-lookup"><span data-stu-id="ffe08-194">We assume that the instance collation is `Latin1_General_100_CS_AS_WS_KS_SC`.</span></span> <span data-ttu-id="ffe08-195">la sola differenza tra le due regole di confronto riguarda la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="ffe08-195">The two collations differ only in case sensitivity.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="ffe08-196">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="ffe08-196">Example 1</span></span>  
 <span data-ttu-id="ffe08-197">Nell'esempio seguente viene illustrato il caso in cui il riferimento trova esattamente una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="ffe08-197">The following example illustrates the case where the reference finds exactly one match.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #a VALUES(1);  
GO  
  
USE master;  
GO  
  
SELECT * FROM #a;  
GO  
  
Results:  
  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
x  
-----------  
1  
```  
  
 <span data-ttu-id="ffe08-198">In questo caso, il risultato #a identificato viene associato sia nelle regole di confronto del catalogo senza distinzione tra maiuscole e minuscole che nelle regole di confronto di istanza con distinzione tra maiuscole e minuscole e il codice funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="ffe08-198">In this case, the identified #a binds in both the case-insensitive catalog collation and the case-sensitive instance collation, and the code works.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="ffe08-199">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="ffe08-199">Example 2</span></span>  
 <span data-ttu-id="ffe08-200">Nell'esempio seguente viene illustrato il caso in cui il riferimento non trova una corrispondenza nelle regole di confronto correnti dove in precedenza ne era presente una.</span><span class="sxs-lookup"><span data-stu-id="ffe08-200">The following example illustrates the case where the reference does not find a match in the current collation where there was one before.</span></span>  
  
```  
USE MyCDB;  
GO  
  
CREATE TABLE #a(x int);  
INSERT INTO #A VALUES(1);  
GO  
```  
  
 <span data-ttu-id="ffe08-201">In questo caso #A viene associato ad #a nelle regole di confronto predefinite senza distinzione tra maiuscole e minuscole e l'inserimento funziona:</span><span class="sxs-lookup"><span data-stu-id="ffe08-201">Here, the #A binds to #a in the case-insensitive default collation, and the insert works,</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="ffe08-202">Se tuttavia si continua lo script...</span><span class="sxs-lookup"><span data-stu-id="ffe08-202">But if we continue the script...</span></span>  
  
```  
USE master;  
GO  
  
SELECT * FROM #A;  
GO  
```  
  
 <span data-ttu-id="ffe08-203">il tentativo di associazione ad #A nelle regole di confronto di istanza con distinzione tra maiuscole e minuscole restituisce un errore:</span><span class="sxs-lookup"><span data-stu-id="ffe08-203">We get an error trying to bind to #A in the case-sensitive instance collation;</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="ffe08-204">Messaggio 208, livello 16, stato 0, riga 2</span><span class="sxs-lookup"><span data-stu-id="ffe08-204">Msg 208, Level 16, State 0, Line 2</span></span>  
  
 <span data-ttu-id="ffe08-205">Il nome di oggetto '#A' non è valido.</span><span class="sxs-lookup"><span data-stu-id="ffe08-205">Invalid object name '#A'.</span></span>  
  
### <a name="example-3"></a><span data-ttu-id="ffe08-206">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="ffe08-206">Example 3</span></span>  
 <span data-ttu-id="ffe08-207">Nell'esempio seguente viene illustrato il caso in cui il riferimento trova più corrispondenze originariamente distinte.</span><span class="sxs-lookup"><span data-stu-id="ffe08-207">The following example illustrates the case where the reference finds multiple matches that were originally distinct.</span></span> <span data-ttu-id="ffe08-208">Innanzitutto, si inizia in `tempdb` (che ha le stesse regole di confronto con distinzione tra maiuscole e minuscole dell'istanza) e si eseguono le istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="ffe08-208">First, we start in `tempdb` (which has the same case-sensitive collation as our instance) and execute the following statements.</span></span>  
  
```  
USE tempdb;  
GO  
  
CREATE TABLE #a(x int);  
GO  
CREATE TABLE #A(x int);  
GO  
INSERT INTO #a VALUES(1);  
GO  
INSERT INTO #A VALUES(2);  
GO  
```  
  
 <span data-ttu-id="ffe08-209">L'esito è positivo poiché in queste regole di confronto le tabelle sono distinte:</span><span class="sxs-lookup"><span data-stu-id="ffe08-209">This succeeds, since the tables are distinct in this collation:</span></span>  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
```  
(1 row(s) affected)  
(1 row(s) affected)  
```  
  
 <span data-ttu-id="ffe08-210">Se si passa al database indipendente, si noterà tuttavia che l'associazione a queste tabelle non è più possibile.</span><span class="sxs-lookup"><span data-stu-id="ffe08-210">If we move into our contained database, however, we find that we can no longer bind to these tables.</span></span>  
  
```  
USE MyCDB;  
GO  
SELECT * FROM #a;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 <span data-ttu-id="ffe08-211">Messaggio 12800, livello 16, stato 1, riga 2</span><span class="sxs-lookup"><span data-stu-id="ffe08-211">Msg 12800, Level 16, State 1, Line 2</span></span>  
  
 <span data-ttu-id="ffe08-212">Il riferimento al nome della tabella temporanea '#a' è ambiguo e non può essere risolto.</span><span class="sxs-lookup"><span data-stu-id="ffe08-212">The reference to temp table name '#a' is ambiguous and cannot be resolved.</span></span> <span data-ttu-id="ffe08-213">I possibili candidati sono '#a' e '#A'.</span><span class="sxs-lookup"><span data-stu-id="ffe08-213">Possible candidates are '#a' and '#A'.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="ffe08-214">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="ffe08-214">Conclusion</span></span>  
 <span data-ttu-id="ffe08-215">Il comportamento delle regole di confronto dei database indipendenti è leggermente diverso da quello nei database non indipendenti.</span><span class="sxs-lookup"><span data-stu-id="ffe08-215">The collation behavior of contained databases differs subtly from that in non-contained databases.</span></span> <span data-ttu-id="ffe08-216">Questo comportamento è generalmente utile, in quanto consente l'indipendenza dell'istanza e favorisce la semplicità.</span><span class="sxs-lookup"><span data-stu-id="ffe08-216">This behavior is generally beneficial, providing instance-independence and simplicity.</span></span> <span data-ttu-id="ffe08-217">È possibile che alcuni utenti riscontrino problemi, specialmente quando una sessione accede a database indipendenti e non indipendenti.</span><span class="sxs-lookup"><span data-stu-id="ffe08-217">Some users may have issues, particularly when a session accesses both contained and non-contained databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffe08-218">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffe08-218">See Also</span></span>  
 [<span data-ttu-id="ffe08-219">Database indipendenti</span><span class="sxs-lookup"><span data-stu-id="ffe08-219">Contained Databases</span></span>](contained-databases.md)  
  
  
