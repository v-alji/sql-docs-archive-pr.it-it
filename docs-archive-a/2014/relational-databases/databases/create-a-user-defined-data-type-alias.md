---
title: Creare un alias del tipo di dati definito dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.userdefineddatatype.general.f1
- sql12.swb.new.datatype.properties.general.f1
helpviewer_keywords:
- alias data types [SQL Server], creating
ms.assetid: b1dd8413-0cd0-411b-a79b-1bb043ccc62d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35db332c23e2df5a8e67c3677cd2411768816765
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623328"
---
# <a name="create-a-user-defined-data-type-alias"></a><span data-ttu-id="397d1-102">Creare un alias del tipo di dati definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="397d1-102">Create a User-Defined Data Type Alias</span></span>
  <span data-ttu-id="397d1-103">In questo argomento si illustra come creare un nuovo alias del tipo di dati definito dall'utente in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="397d1-103">This topic describes how to create a new user-defined data type alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="397d1-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="397d1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="397d1-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="397d1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="397d1-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="397d1-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="397d1-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="397d1-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="397d1-108">**Per creare un alias del tipo di dati definito dall'utente utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="397d1-108">**To create a user-defined data type alias, using:**</span></span>  
  
     [<span data-ttu-id="397d1-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="397d1-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="397d1-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="397d1-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="397d1-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="397d1-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="397d1-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="397d1-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="397d1-113">Il nome di un alias del tipo di dati definito dall'utente deve essere conforme alle regole per gli identificatori.</span><span class="sxs-lookup"><span data-stu-id="397d1-113">The name of a user-defined data type alias must comply with the rules for identifiers.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="397d1-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="397d1-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="397d1-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="397d1-115">Permissions</span></span>  
 <span data-ttu-id="397d1-116">È richiesta l'autorizzazione CREATE TYPE nel database corrente e l'autorizzazione ALTER per *schema_name*.</span><span class="sxs-lookup"><span data-stu-id="397d1-116">Requires CREATE TYPE permission in the current database and ALTER permission on *schema_name*.</span></span> <span data-ttu-id="397d1-117">Se *schema_name* viene omesso, vengono applicate le regole predefinite per la risoluzione dei nomi per determinare lo schema dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="397d1-117">If *schema_name* is not specified, the default name resolution rules for determining the schema for the current user apply.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="397d1-118">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="397d1-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-user-defined-data-type"></a><span data-ttu-id="397d1-119">Per creare un tipo di dati definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="397d1-119">To create a user-defined data type</span></span>  
  
1.  <span data-ttu-id="397d1-120">In Esplora oggetti espandere **Database**, espandere un database, **Programmabilità**e **Tipi**, fare clic con il pulsante destro del mouse su **Tipi di dati definiti dall'utente**, quindi scegliere **Nuovo tipo di dati definito dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="397d1-120">In Object Explorer, expand **Databases**, expand a database, expand **Programmability**, expand **Types**, right-click **User-Defined Data Types**, and then click **New User-Defined Data Type**.</span></span>  
  
     <span data-ttu-id="397d1-121">**Consenti valori Null**</span><span class="sxs-lookup"><span data-stu-id="397d1-121">**Allow NULLs**</span></span>  
     <span data-ttu-id="397d1-122">Specificare se dal tipo di dati definito dall'utente possono essere accettati valori Null.</span><span class="sxs-lookup"><span data-stu-id="397d1-122">Specify whether the user-defined data type can accept NULL values.</span></span> <span data-ttu-id="397d1-123">Il supporto di valori Null di un tipo di dati definito dall'utente esistente non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="397d1-123">The nullability of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="397d1-124">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="397d1-124">**Data type**</span></span>  
     <span data-ttu-id="397d1-125">Selezionare il tipo di dati di base dalla casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="397d1-125">Select the base data type from the list box.</span></span> <span data-ttu-id="397d1-126">In questa casella vengono visualizzati tutti i tipi di dati, ad eccezione di `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` e `xml`.</span><span class="sxs-lookup"><span data-stu-id="397d1-126">The list box displays all data types except for the `geography`, `geometry`, `hierarchyid`, `sysname`, `timestamp` , and `xml` data types.</span></span> <span data-ttu-id="397d1-127">Il tipo di dati di un tipo di dati definito dall'utente esistente non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="397d1-127">The data type of an existing user-defined data type is not editable.</span></span>  
  
     <span data-ttu-id="397d1-128">**Default**</span><span class="sxs-lookup"><span data-stu-id="397d1-128">**Default**</span></span>  
     <span data-ttu-id="397d1-129">Facoltativamente, selezionare una regola o un valore predefinito da associare all'alias del tipo di dati definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="397d1-129">Optionally select a rule or a default to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="397d1-130">**Lunghezza/Precisione**</span><span class="sxs-lookup"><span data-stu-id="397d1-130">**Length/Precision**</span></span>  
     <span data-ttu-id="397d1-131">Consente di visualizzare la lunghezza o la precisione del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="397d1-131">Displays the length or precision of the data type as applicable.</span></span> <span data-ttu-id="397d1-132">L'opzione**Lunghezza** viene applicata ai tipi di dati carattere definiti dall'utente mentre **Precisione** solo ai tipi di dati numerici definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="397d1-132">**Length** applies to character-based user-defined data types; **Precision** applies only to numeric-based user-defined data types.</span></span> <span data-ttu-id="397d1-133">L'etichetta varia a seconda del tipo di dati selezionato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="397d1-133">The label changes depending on the data type selected earlier.</span></span> <span data-ttu-id="397d1-134">Se la lunghezza o la precisione del tipo di dati selezionato è fissa, la casella non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="397d1-134">This box is not editable if the length or precision of the selected data type is fixed.</span></span>  
  
     <span data-ttu-id="397d1-135">La lunghezza non viene visualizzata per tipi di dati `nvarchar(max)`, `varchar(max)` o `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="397d1-135">Length is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
     <span data-ttu-id="397d1-136">**Nome**</span><span class="sxs-lookup"><span data-stu-id="397d1-136">**Name**</span></span>  
     <span data-ttu-id="397d1-137">Se si crea un nuovo alias del tipo di dati definito dall'utente, digitare un nome univoco da utilizzare nel database per rappresentare il tipo di dati definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="397d1-137">If you are creating a new user-defined data type alias, type a unique name to be used across the database to represent the user-defined data type.</span></span> <span data-ttu-id="397d1-138">Il numero massimo di caratteri deve corrispondere al tipo di dati di sistema `sysname` .</span><span class="sxs-lookup"><span data-stu-id="397d1-138">The maximum number of characters must match the system `sysname` data type.</span></span> <span data-ttu-id="397d1-139">Il nome di un alias del tipo di dati definito dall'utente esistente non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="397d1-139">The name of an existing user-defined data type alias is not editable.</span></span>  
  
     <span data-ttu-id="397d1-140">**Regola**</span><span class="sxs-lookup"><span data-stu-id="397d1-140">**Rule**</span></span>  
     <span data-ttu-id="397d1-141">Facoltativamente, selezionare una regola da associare all'alias del tipo di dati definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="397d1-141">Optionally select a rule to bind to the user-defined data type alias.</span></span>  
  
     <span data-ttu-id="397d1-142">**Ridimensionare**</span><span class="sxs-lookup"><span data-stu-id="397d1-142">**Scale**</span></span>  
     <span data-ttu-id="397d1-143">Specificare il numero massimo di cifre decimali che è possibile archiviare a destra del separatore decimale.</span><span class="sxs-lookup"><span data-stu-id="397d1-143">Specify the maximum number of decimal digits that can be stored to the right of the decimal point.</span></span>  
  
     <span data-ttu-id="397d1-144">**Schema**</span><span class="sxs-lookup"><span data-stu-id="397d1-144">**Schema**</span></span>  
     <span data-ttu-id="397d1-145">Consente di selezionare uno schema dall'elenco di tutti gli schemi disponibili per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="397d1-145">Select a schema from a list of all schemas available to the current user.</span></span> <span data-ttu-id="397d1-146">La selezione predefinita corrisponde allo schema predefinito per l'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="397d1-146">The default selection is the default schema for the current user.</span></span>  
  
     <span data-ttu-id="397d1-147">**Storage**</span><span class="sxs-lookup"><span data-stu-id="397d1-147">**Storage**</span></span>  
     <span data-ttu-id="397d1-148">Consente di visualizzare la capacità di memorizzazione massima per l'alias del tipo di dati definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="397d1-148">Displays the maximum storage size for the user-defined data type alias.</span></span> <span data-ttu-id="397d1-149">Le dimensioni di archiviazione massime variano in base alla precisione.</span><span class="sxs-lookup"><span data-stu-id="397d1-149">Maximum storage sizes vary, based on precision.</span></span>  
  
    |||  
    |-|-|  
    |<span data-ttu-id="397d1-150">1 - 9</span><span class="sxs-lookup"><span data-stu-id="397d1-150">1 - 9</span></span>|<span data-ttu-id="397d1-151">5</span><span class="sxs-lookup"><span data-stu-id="397d1-151">5</span></span>|  
    |<span data-ttu-id="397d1-152">10 - 19</span><span class="sxs-lookup"><span data-stu-id="397d1-152">10 - 19</span></span>|<span data-ttu-id="397d1-153">9</span><span class="sxs-lookup"><span data-stu-id="397d1-153">9</span></span>|  
    |<span data-ttu-id="397d1-154">20 - 28</span><span class="sxs-lookup"><span data-stu-id="397d1-154">20 - 28</span></span>|<span data-ttu-id="397d1-155">13</span><span class="sxs-lookup"><span data-stu-id="397d1-155">13</span></span>|  
    |<span data-ttu-id="397d1-156">29 - 38</span><span class="sxs-lookup"><span data-stu-id="397d1-156">29 - 38</span></span>|<span data-ttu-id="397d1-157">17</span><span class="sxs-lookup"><span data-stu-id="397d1-157">17</span></span>|  
  
     <span data-ttu-id="397d1-158">Per `nchar` i `nvarchar` tipi di dati e, il valore di archiviazione è sempre il doppio del valore di **lunghezza**.</span><span class="sxs-lookup"><span data-stu-id="397d1-158">For `nchar` and `nvarchar` data types, the storage value is always two times the value in **Length**.</span></span>  
  
     <span data-ttu-id="397d1-159">L'archiviazione non viene visualizzata per tipi di dati `nvarchar(max)`, `varchar(max)` o `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="397d1-159">Storage is not displayed for `nvarchar(max)`, `varchar(max)`, or `varbinary(max)` data types.</span></span>  
  
2.  <span data-ttu-id="397d1-160">Nella casella **Schema** della finestra di dialogo **Nuovo tipo di dati definito dall'utente** digitare lo schema proprietario per questo alias del tipo di dati oppure usare il pulsante sfoglia per selezionare lo schema.</span><span class="sxs-lookup"><span data-stu-id="397d1-160">In the **New User-defined Data Type** dialog box, in the **Schema** box, type the schema to own this data type alias, or use the browse button to select the schema.</span></span>  
  
3.  <span data-ttu-id="397d1-161">Nella casella **Nome** digitare un nome per il nuovo alias del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="397d1-161">In the **Name** box, type a name for the new data type alias.</span></span>  
  
4.  <span data-ttu-id="397d1-162">Nella casella **Tipo di dati** selezionare il tipo di dati sul quale sarà basato il nuovo alias del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="397d1-162">In the **Data type** box, select the data type that the new data type alias will be based on.</span></span>  
  
5.  <span data-ttu-id="397d1-163">Compilare le caselle **Lunghezza**, **Precisione**e **Scala** se necessarie per il tipo di dati selezionato.</span><span class="sxs-lookup"><span data-stu-id="397d1-163">Complete the **Length**, **Precision**, and **Scale** boxes if appropriate for that data type.</span></span>  
  
6.  <span data-ttu-id="397d1-164">Selezionare **Consenti valori NULL** se il nuovo alias del tipo di dati può consentire valori NULL.</span><span class="sxs-lookup"><span data-stu-id="397d1-164">Check **Allow NULLs** if the new data type alias can permit NULL values.</span></span>  
  
7.  <span data-ttu-id="397d1-165">Nell'area **Associazione** compilare le caselle **Valore predefinito** o **Regola** per associare un valore predefinito o una regola al nuovo alias del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="397d1-165">In the **Binding** area, complete the **Default** or **Rule** boxes if you want to bind a default or rule to the new data type alias.</span></span> <span data-ttu-id="397d1-166">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]non è possibile creare valori predefiniti e regole.</span><span class="sxs-lookup"><span data-stu-id="397d1-166">Defaults and rules cannot be created in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="397d1-167">Usare [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="397d1-167">Use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="397d1-168">Esempi di codice per la creazione di valori predefiniti e di regole sono disponibili in Esplora modelli.</span><span class="sxs-lookup"><span data-stu-id="397d1-168">Example code for creating defaults and rules are available in Template Explorer.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="397d1-169">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="397d1-169">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-user-defined-data-type-alias"></a><span data-ttu-id="397d1-170">Per creare un alias del tipo di dati definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="397d1-170">To create a user-defined data type alias</span></span>  
  
1.  <span data-ttu-id="397d1-171">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="397d1-171">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="397d1-172">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="397d1-172">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="397d1-173">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="397d1-173">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="397d1-174">In questo esempio si crea un alias del tipo di dati basato sul tipo di dati di sistema `varchar` .</span><span class="sxs-lookup"><span data-stu-id="397d1-174">This example creates a data type alias based on the system-supplied `varchar` data type.</span></span> <span data-ttu-id="397d1-175">L'alias del tipo di dati `ssn` viene utilizzato per colonne contenenti numeri di previdenza sociale a 11 cifre (999-99-9999).</span><span class="sxs-lookup"><span data-stu-id="397d1-175">The `ssn` data type alias is used for columns holding 11-digit social security numbers (999-99-9999).</span></span> <span data-ttu-id="397d1-176">Questa colonna non può contenere valori NULL.</span><span class="sxs-lookup"><span data-stu-id="397d1-176">The column cannot be NULL.</span></span>  
  
```sql  
CREATE TYPE ssn  
FROM varchar(11) NOT NULL ;  
```  
  
## <a name="see-also"></a><span data-ttu-id="397d1-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="397d1-177">See Also</span></span>  
 <span data-ttu-id="397d1-178">[Identificatori del database](database-identifiers.md) </span><span class="sxs-lookup"><span data-stu-id="397d1-178">[Database Identifiers](database-identifiers.md) </span></span>  
 [<span data-ttu-id="397d1-179">CREATE TYPE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="397d1-179">CREATE TYPE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-type-transact-sql)  
  
  
