---
title: Mantenere i valori Null o usare i valori predefiniti durante un'importazione bulk (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], null values
- bulk importing [SQL Server], default values
- data formats [SQL Server], null values
- bulk rowset providers [SQL Server]
- bcp utility [SQL Server], null values
- BULK INSERT statement
- default values
- OPENROWSET function, bulk importing
- data formats [SQL Server], default values
ms.assetid: 6b91d762-337b-4345-a159-88abb3e64a81
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 856aa12f6ad5e5094324e0df65941bc63d611451
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724732"
---
# <a name="keep-nulls-or-use-default-values-during-bulk-import-sql-server"></a><span data-ttu-id="64530-102">Mantenimento dei valori Null o utilizzo dei valori predefiniti durante un'importazione bulk (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="64530-102">Keep Nulls or Use Default Values During Bulk Import (SQL Server)</span></span>
  <span data-ttu-id="64530-103">Per impostazione predefinita, durante l'importazione di dati in una tabella il comando **bcp** e l'istruzione BULK INSERT osservano gli eventuali valori predefiniti che sono stati specificati per le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="64530-103">By default, when data is imported into a table, the **bcp** command and BULK INSERT statement observe any defaults that are defined for the columns in the table.</span></span> <span data-ttu-id="64530-104">Ad esempio, se un file di dati contiene un campo Null, verrà caricato nel campo il valore predefinito della colonna.</span><span class="sxs-lookup"><span data-stu-id="64530-104">For example, if there is a null field in a data file, the default value for the column is loaded instead.</span></span> <span data-ttu-id="64530-105">Il comando **bcp** e l'istruzione BULK INSERT consentono entrambi di specificare che dovranno essere mantenuti i valori Null.</span><span class="sxs-lookup"><span data-stu-id="64530-105">The **bcp** command and BULK INSERT statement both allow you to specify that nulls values be retained.</span></span>  
  
 <span data-ttu-id="64530-106">Un'istruzione INSERT regolare mantiene invece il valore Null anziché inserire un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="64530-106">In contrast, a regular INSERT statement retains the null value instead of inserting a default value.</span></span> <span data-ttu-id="64530-107">L'istruzione INSERT ... SELECT \* FROM OPENROWSET(BULK...) funziona in modo analogo a un'istruzione INSERT regolare, ma supporta inoltre un hint di tabella per l'inserimento di valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="64530-107">The INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement provides the same basic behavior as regular INSERT but additionally supports a table hint for inserting the default values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64530-108">Per i file di formato di esempio che ignorano una colonna di tabella, vedere [Usare un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="64530-108">For sample format files that skip a table column, see [Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="64530-109">Tabella e file di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="64530-109">Sample Table and Data File</span></span>  
 <span data-ttu-id="64530-110">Per eseguire gli esempi riportati in questo argomento, è necessario creare una tabella e un file di dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="64530-110">To run the examples in this topic, you need to create a sample table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="64530-111">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="64530-111">Sample Table</span></span>  
 <span data-ttu-id="64530-112">Gli esempi richiedono la creazione di una tabella denominata **MyTestDefaultCol2** nel database di esempio **AdventureWorks** nello schema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="64530-112">The examples require that a table named **MyTestDefaultCol2** be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="64530-113">Per creare questa tabella, nell' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] editor di query di eseguire:</span><span class="sxs-lookup"><span data-stu-id="64530-113">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE MyTestDefaultCol2   
(Col1 smallint,  
Col2 nvarchar(50) DEFAULT 'Default value of Col2',  
Col3 nvarchar(50)   
);  
GO  
  
```  
  
 <span data-ttu-id="64530-114">Si noti che la seconda colonna della tabella, `Col2`, ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="64530-114">Notice that the second table column, `Col2`, has a default value.</span></span>  
  
### <a name="sample-format-file"></a><span data-ttu-id="64530-115">File di formato di esempio</span><span class="sxs-lookup"><span data-stu-id="64530-115">Sample Format File</span></span>  
 <span data-ttu-id="64530-116">In alcuni degli esempi di importazione bulk viene utilizzato un file di formato non XML, `MyTestDefaultCol2-f-c.Fmt` che corrisponde esattamente alla tabella `MyTestDefaultCol2`.</span><span class="sxs-lookup"><span data-stu-id="64530-116">Some of the bulk-import examples use a non-XML format file, `MyTestDefaultCol2-f-c.Fmt` that corresponds exactly to the `MyTestDefaultCol2` table.</span></span> <span data-ttu-id="64530-117">Per creare questo file di formato, al prompt dei comandi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="64530-117">To create this format file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 format nul -c -f C:\MyTestDefaultCol2-f-c.Fmt -t, -r\n -T  
  
```  
  
 <span data-ttu-id="64530-118">Per informazioni sulla creazione di file di formato, vedere [Creare un file di formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="64530-118">For more information about creating format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
### <a name="sample-data-file"></a><span data-ttu-id="64530-119">File di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="64530-119">Sample Data File</span></span>  
 <span data-ttu-id="64530-120">Nell'esempio viene utilizzato un file di dati di esempio, `MyTestEmptyField2-c.Dat`, che non contiene alcun valore nel secondo campo.</span><span class="sxs-lookup"><span data-stu-id="64530-120">The example uses a sample data file, `MyTestEmptyField2-c.Dat`, that contains no values in the second field.</span></span> <span data-ttu-id="64530-121">Il file di dati `MyTestEmptyField2-c.Dat` contiene i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="64530-121">The `MyTestEmptyField2-c.Dat` data file contains the following records.</span></span>  
  
```  
1,,DataField3  
2,,DataField3  
  
```  
  
## <a name="keeping-null-values-with-bcp-or-bulk-insert"></a><span data-ttu-id="64530-122">Mantenimento dei valori Null con bcp o BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="64530-122">Keeping Null Values with bcp or BULK INSERT</span></span>  
 <span data-ttu-id="64530-123">I qualificatori seguenti specificano che un campo vuoto del file di dati mantiene il relativo valore Null durante l'importazione bulk anziché ereditare un valore predefinito (se disponibile) per le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="64530-123">The following qualifiers specify that an empty field in the data file retains its null value during the bulk-import operation, rather than inheriting a default value (if any) for the table columns.</span></span>  
  
|<span data-ttu-id="64530-124">Comando</span><span class="sxs-lookup"><span data-stu-id="64530-124">Command</span></span>|<span data-ttu-id="64530-125">Qualifier</span><span class="sxs-lookup"><span data-stu-id="64530-125">Qualifier</span></span>|<span data-ttu-id="64530-126">Tipo di qualificatore</span><span class="sxs-lookup"><span data-stu-id="64530-126">Qualifier type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="64530-127">**bcp**</span><span class="sxs-lookup"><span data-stu-id="64530-127">**bcp**</span></span>|`-k`|<span data-ttu-id="64530-128">Opzione</span><span class="sxs-lookup"><span data-stu-id="64530-128">Switch</span></span>|  
|<span data-ttu-id="64530-129">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="64530-129">BULK INSERT</span></span>|<span data-ttu-id="64530-130">KEEPNULLS<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="64530-130">KEEPNULLS<sup>1</sup></span></span>|<span data-ttu-id="64530-131">Argomento</span><span class="sxs-lookup"><span data-stu-id="64530-131">Argument</span></span>|  
  
 <span data-ttu-id="64530-132"><sup>1</sup> per BULK INSERT, se i valori predefiniti non sono disponibili, è necessario definire la colonna della tabella in modo da consentire i valori null.</span><span class="sxs-lookup"><span data-stu-id="64530-132"><sup>1</sup> For BULK INSERT, if default values are not available, the table column must be defined to allow null values.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64530-133">Questi qualificatori disabilitano il controllo delle definizioni DEFAULT di una tabella mediante i comandi per l'importazione bulk.</span><span class="sxs-lookup"><span data-stu-id="64530-133">These qualifiers disable checking of DEFAULT definitions on a table by these bulk-import commands.</span></span> <span data-ttu-id="64530-134">Per le istruzioni INSERT simultanee, le definizioni DEFAULT sono tuttavia previste.</span><span class="sxs-lookup"><span data-stu-id="64530-134">However, for any concurrent INSERT statements, DEFAULT definitions are expected.</span></span>  
  
 <span data-ttu-id="64530-135">Per altre informazioni, vedere [Utilità bcp](../../tools/bcp-utility.md) e [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="64530-135">For more information, see [bcp Utility](../../tools/bcp-utility.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="64530-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="64530-136">Examples</span></span>  
 <span data-ttu-id="64530-137">Gli esempi in questa sezione eseguono l'importazione in blocco con **bcp** o BULK INSERT e mantengono i valori Null.</span><span class="sxs-lookup"><span data-stu-id="64530-137">The examples in this section bulk import using **bcp** or BULK INSERT and keep null values.</span></span>  
  
 <span data-ttu-id="64530-138">La seconda colonna della tabella, **Col2**, ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="64530-138">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="64530-139">Il campo corrispondente del file di dati contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="64530-139">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="64530-140">Per impostazione predefinita, se si usa **bcp** o BULK INSERT per importare i dati di questo file di dati nella tabella **MyTestDefaultCol2**, viene inserito il valore predefinito di **Col2** e viene generato il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="64530-140">By default, when **bcp** or BULK INSERT is used to import data from this data file into the **MyTestDefaultCol2** table, the default value of **Col2** is inserted, producing the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`Default value of Col2`|`DataField3`|  
|`2`|`Default value of Col2`|`DataField3`|  
  
 <span data-ttu-id="64530-141">Per inserire " `NULL` " anziché " `Default value of Col2` ", è necessario usare l' `-k` opzione switch o KEEPNULL, come illustrato negli esempi di **bcp** ed BULK INSERT seguenti.</span><span class="sxs-lookup"><span data-stu-id="64530-141">To insert "`NULL`" instead of "`Default value of Col2`", you need to use the `-k` switch or KEEPNULL option, as demonstrated in the following **bcp** and BULK INSERT examples.</span></span>  
  
#### <a name="using-bcp-and-keeping-null-values"></a><span data-ttu-id="64530-142">Utilizzo di bcp e mantenimento dei valori Null</span><span class="sxs-lookup"><span data-stu-id="64530-142">Using bcp and Keeping Null Values</span></span>  
 <span data-ttu-id="64530-143">L'esempio seguente mostra come mantenere i valori Null in un comando **bcp**.</span><span class="sxs-lookup"><span data-stu-id="64530-143">The following example demonstrates how to keep null values in a **bcp** command.</span></span> <span data-ttu-id="64530-144">Il comando **bcp** contiene le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64530-144">The **bcp** command contains the following switches:</span></span>  
  
|<span data-ttu-id="64530-145">Opzione</span><span class="sxs-lookup"><span data-stu-id="64530-145">Switch</span></span>|<span data-ttu-id="64530-146">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64530-146">Description</span></span>|  
|------------|-----------------|  
|`-f`|<span data-ttu-id="64530-147">Specifica che il comando utilizza un file di formato.</span><span class="sxs-lookup"><span data-stu-id="64530-147">Specifies that the command is using a format file..</span></span>|  
|`-k`|<span data-ttu-id="64530-148">Specifica che durante l'operazione il valore delle colonne vuote deve essere Null, ovvero che non verranno inseriti valori predefiniti in tali colonne.</span><span class="sxs-lookup"><span data-stu-id="64530-148">Specifies that empty columns should retain a null value during the operation, rather than have any default values for the columns inserted.</span></span>|  
|`-T`|<span data-ttu-id="64530-149">Specifica che l'utilità bcp si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite una connessione trusted.</span><span class="sxs-lookup"><span data-stu-id="64530-149">Specifies that the bcp utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection.</span></span>|  
  
 <span data-ttu-id="64530-150">Al prompt dei comandi di Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="64530-150">At the Windows command prompt, enter.</span></span>  
  
```  
bcp AdventureWorks..MyTestDefaultCol2 in C:\MyTestEmptyField2-c.Dat -f C:\MyTestDefaultCol2-f-c.Fmt -k -T  
  
```  
  
#### <a name="using-bulk-insert-and-keeping-null-values"></a><span data-ttu-id="64530-151">Utilizzo di BULK INSERT e mantenimento dei valori Null</span><span class="sxs-lookup"><span data-stu-id="64530-151">Using BULK INSERT and Keeping Null Values</span></span>  
 <span data-ttu-id="64530-152">Nell'esempio seguente viene illustrato come utilizzare l'opzione KEEPNULLS in un'istruzione BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="64530-152">The following example demonstrates how to use the KEEPNULLS option in a BULK INSERT statement.</span></span> <span data-ttu-id="64530-153">Da uno strumento per le query, come l'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], eseguire:</span><span class="sxs-lookup"><span data-stu-id="64530-153">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT MyTestDefaultCol2  
   FROM 'C:\MyTestEmptyField2-c.Dat'  
   WITH (  
      DATAFILETYPE = 'char',  
      FIELDTERMINATOR = ',',  
      KEEPNULLS  
   );  
GO  
  
```  
  
## <a name="keeping-default-values-with-insert--select--from-openrowsetbulk"></a><span data-ttu-id="64530-154">Mantenimento dei valori predefiniti con INSERT... SELECT \* FROM OPENROWSET (BULK...)</span><span class="sxs-lookup"><span data-stu-id="64530-154">Keeping Default Values with INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
 <span data-ttu-id="64530-155">Per impostazione predefinita, tutte le colonne non specificate nell'operazione di caricamento bulk vengono impostate su NULL da INSERT... SELECT \* FROM OPENROWSET (BULK...). Tuttavia, è possibile specificare che per un campo vuoto nel file di dati, nella colonna della tabella corrispondente viene utilizzato il valore predefinito, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="64530-155">By default, any columns that are not specified in the bulk-load operation are set to NULL by INSERT ... SELECT \* FROM OPENROWSET(BULK...). However, you can specify that for an empty field in the data file, the corresponding table column uses its default value (if any).</span></span> <span data-ttu-id="64530-156">Per utilizzare i valori predefiniti, specificare l'hint di tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="64530-156">To use default values, specify the following table hint:</span></span>  
  
|<span data-ttu-id="64530-157">Comando</span><span class="sxs-lookup"><span data-stu-id="64530-157">Command</span></span>|<span data-ttu-id="64530-158">Qualifier</span><span class="sxs-lookup"><span data-stu-id="64530-158">Qualifier</span></span>|<span data-ttu-id="64530-159">Tipo di qualificatore</span><span class="sxs-lookup"><span data-stu-id="64530-159">Qualifier Type</span></span>|  
|-------------|---------------|--------------------|  
|<span data-ttu-id="64530-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="64530-160">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="64530-161">WITH(KEEPDEFAULTS)</span><span class="sxs-lookup"><span data-stu-id="64530-161">WITH(KEEPDEFAULTS)</span></span>|<span data-ttu-id="64530-162">Hint di tabella</span><span class="sxs-lookup"><span data-stu-id="64530-162">Table hint</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="64530-163">Per ulteriori informazioni, vedere [INSERT &#40;Transact-sql&#41;](/sql/t-sql/statements/insert-transact-sql), [Select &#40;transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql)e [hint di tabella &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span><span class="sxs-lookup"><span data-stu-id="64530-163">for more information, see [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql), [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql), and [Table Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-table)</span></span>  
  
### <a name="examples"></a><span data-ttu-id="64530-164">Esempi</span><span class="sxs-lookup"><span data-stu-id="64530-164">Examples</span></span>  
 <span data-ttu-id="64530-165">L'istruzione INSERT seguente... SELECT \* FROM OPENROWSET (BULK...) esegue l'importazione bulk di dati e mantiene i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="64530-165">The following INSERT ... SELECT \* FROM OPENROWSET(BULK...) example bulk imports data and keeps the default values.</span></span>  
  
 <span data-ttu-id="64530-166">Per eseguire gli esempi, è necessario creare la tabella di esempio **MyTestDefaultCol2**, il file di dati `MyTestEmptyField2-c.Dat` e usare un file di formato, `MyTestDefaultCol2-f-c.Fmt`.</span><span class="sxs-lookup"><span data-stu-id="64530-166">To run the examples, you need to create the **MyTestDefaultCol2** sample table, the `MyTestEmptyField2-c.Dat` data file, and use a format file, `MyTestDefaultCol2-f-c.Fmt`.</span></span> <span data-ttu-id="64530-167">Per informazioni sulla creazione di questi esempi, vedere la sezione relativa alla tabella e file di dati di esempio più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="64530-167">For information on creating these samples, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="64530-168">La seconda colonna della tabella, **Col2**, ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="64530-168">The second table column, **Col2**, has a default value.</span></span> <span data-ttu-id="64530-169">Il campo corrispondente del file di dati contiene una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="64530-169">The corresponding field of the data file contains an empty string.</span></span> <span data-ttu-id="64530-170">Quando si inserisce... SELECT \* FROM OPENROWSET (bulk...) importa i campi del file di dati nella tabella **MyTestDefaultCol2** . per impostazione predefinita, il valore null viene inserito in **col2** anziché nel valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="64530-170">When INSERT ... SELECT \* FROM OPENROWSET(BULK...) import the fields of this data file into the **MyTestDefaultCol2** table, by default, NULL is inserted into **Col2** instead of the default value.</span></span> <span data-ttu-id="64530-171">Questo comportamento predefinito genera il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="64530-171">This default behavior produces the following result:</span></span>  
  
||||  
|-|-|-|  
|`1`|`NULL`|`DataField3`|  
|`2`|`NULL`|`DataField3`|  
  
 <span data-ttu-id="64530-172">Per inserire il valore predefinito "`Default value of Col2`" anziché "`NULL`", è necessario utilizzare l'hint di tabella KEEPDEFAULTS, come è illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="64530-172">To insert the default value, "`Default value of Col2`", instead of "`NULL`", you need to use KEEPDEFAULTS table hint, as demonstrated in the following example.</span></span> <span data-ttu-id="64530-173">Da uno strumento per le query, come l'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], eseguire:</span><span class="sxs-lookup"><span data-stu-id="64530-173">From a query tool, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
INSERT INTO MyTestDefaultCol2  
    WITH (KEEPDEFAULTS)  
    SELECT *  
      FROM OPENROWSET(BULK  'C:\MyTestEmptyField2-c.Dat',  
      FORMATFILE='C:\MyTestDefaultCol2-f-c.Fmt'       
      ) as t1 ;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="64530-174">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="64530-174">Related Tasks</span></span>  
  
-   [<span data-ttu-id="64530-175">Mantenere i valori Identity durante l'importazione in blocco dei dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-175">Keep Identity Values When Bulk Importing Data &#40;SQL Server&#41;</span></span>](keep-identity-values-when-bulk-importing-data-sql-server.md)  
  
-   [<span data-ttu-id="64530-176">Preparare i dati per l'importazione o l'esportazione in blocco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-176">Prepare Data for Bulk Export or Import &#40;SQL Server&#41;</span></span>](prepare-data-for-bulk-export-or-import-sql-server.md)  
  
 <span data-ttu-id="64530-177">**Per utilizzare un file di formato**</span><span class="sxs-lookup"><span data-stu-id="64530-177">**To use a format file**</span></span>  
  
-   [<span data-ttu-id="64530-178">Creazione di un file di formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-178">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="64530-179">Usare un file di formato per l'importazione in blocco dei dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-179">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="64530-180">Utilizzo di un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-180">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
-   [<span data-ttu-id="64530-181">Utilizzo di un file di formato per escludere un campo di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-181">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="64530-182">Utilizzo di un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-182">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 <span data-ttu-id="64530-183">**Per utilizzare formati di dati per l'importazione o l'esportazione bulk**</span><span class="sxs-lookup"><span data-stu-id="64530-183">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="64530-184">Importare dati in formato nativo e carattere da versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="64530-184">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="64530-185">Utilizzo del formato carattere per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-185">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="64530-186">Usare il formato nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-186">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="64530-187">Utilizzo del formato carattere Unicode per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="64530-188">Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 <span data-ttu-id="64530-189">**Per specificare i formati di dati per la compatibilità mediante bcp**</span><span class="sxs-lookup"><span data-stu-id="64530-189">**To specify data formats for compatibility when using bcp**</span></span>  
  
-   [<span data-ttu-id="64530-190">Impostazione dei caratteri di terminazione del campo e della riga &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-190">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
-   [<span data-ttu-id="64530-191">Specificare la lunghezza del prefisso nei file di dati con bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-191">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="64530-192">Specifica del tipo di archiviazione di file tramite bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-192">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="64530-193">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64530-193">See Also</span></span>  
 <span data-ttu-id="64530-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="64530-194">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="64530-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="64530-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="64530-196">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="64530-196">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="64530-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="64530-197">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="64530-198">Hint di tabella &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="64530-198">Table Hints &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/hints-transact-sql-table)  
  
  
