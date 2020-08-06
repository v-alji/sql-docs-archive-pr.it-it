---
title: Usare il formato nativo per importare o esportare dati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- data formats [SQL Server], native
ms.assetid: eb279b2f-0f1f-428f-9b8f-2a7fc495b79f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab42ba3eb6468aac3da2fa780d371818c8776690
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724716"
---
# <a name="use-native-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="b3d3e-102">Utilizzo del formato nativo per importare o esportare dati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b3d3e-102">Use Native Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="b3d3e-103">L'utilizzo del formato nativo è consigliabile per il trasferimento bulk dei dati tra più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante un file di dati in cui non sono inclusi caratteri estesi o DBCS (Double Byte Character Set).</span><span class="sxs-lookup"><span data-stu-id="b3d3e-103">Native format is recommended when you bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using a data file that does not contain any extended/double-byte character set (DBCS) characters.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3d3e-104">Per il trasferimento bulk di dati tra più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante un file di dati contenente caratteri estesi o DBCS, è consigliabile utilizzare il formato nativo Unicode.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-104">To bulk transfer data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters, you should use the Unicode native format.</span></span> <span data-ttu-id="b3d3e-105">Per altre informazioni, vedere [Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3d3e-105">For more information, see [Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;](use-unicode-native-format-to-import-or-export-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="b3d3e-106">Il formato nativo mantiene i tipi di dati nativi di un database</span><span class="sxs-lookup"><span data-stu-id="b3d3e-106">Native format maintains the native data types of a database.</span></span> <span data-ttu-id="b3d3e-107">e viene utilizzato per il trasferimento dei dati ad alta velocità tra le tabelle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b3d3e-107">Native format is intended for high-speed data transfer of data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span> <span data-ttu-id="b3d3e-108">Se si utilizza un file di formato, non è necessario che le tabelle di origine e di destinazione siano identiche.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-108">If you use a format file, the source and target tables do not need to be identical.</span></span> <span data-ttu-id="b3d3e-109">Il trasferimento dei dati è costituito da due passaggi:</span><span class="sxs-lookup"><span data-stu-id="b3d3e-109">The data transfer involves two steps:</span></span>  
  
1.  <span data-ttu-id="b3d3e-110">Esportazione bulk dei dati da una tabella di origine in un file di dati</span><span class="sxs-lookup"><span data-stu-id="b3d3e-110">Bulk exporting the data from a source table into a data file</span></span>  
  
2.  <span data-ttu-id="b3d3e-111">Importazione bulk dei dati dal file di dati nella tabella di destinazione</span><span class="sxs-lookup"><span data-stu-id="b3d3e-111">Bulk importing the data from the data file into the target table</span></span>  
  
 <span data-ttu-id="b3d3e-112">L'utilizzo del formato nativo tra tabelle identiche consente di evitare la conversione di tipi di dati nel/dal formato carattere, risparmiando tempo e spazio.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-112">The use of native format between identical tables avoids unnecessary conversion of data types to and from character format, saving time and space.</span></span> <span data-ttu-id="b3d3e-113">Per raggiungere la velocità di trasferimento ottimale, tuttavia, vengono eseguiti solo alcuni controlli relativi alla formattazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-113">To achieve the optimum transfer rate, however, few checks are performed regarding data formatting.</span></span> <span data-ttu-id="b3d3e-114">Per evitare problemi relativi ai dati caricati, vedere l'elenco di restrizioni seguente.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-114">To prevent problems with the loaded data, see the following restrictions list.</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="b3d3e-115">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="b3d3e-115">Restrictions</span></span>  
 <span data-ttu-id="b3d3e-116">Per importare correttamente i dati in formato nativo, verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b3d3e-116">To import data in native format successfully, ensure that:</span></span>  
  
-   <span data-ttu-id="b3d3e-117">Il file di dati deve essere in formato nativo.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-117">The data file is in native format.</span></span>  
  
-   <span data-ttu-id="b3d3e-118">È necessario che la tabella di destinazione sia compatibile con il file di dati (deve includere il numero di colonne, il tipo di dati e la lunghezza corretti, lo stato NULL e così via). In alternativa, è necessario utilizzare un file di formato per eseguire il mapping tra ogni campo e le colonne corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-118">Either the target table must be compatible with the data file (having the correct number of columns, data type, length, NULL status, and so forth), or you must use a format file to map each field to its corresponding columns.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b3d3e-119">Se si importano i dati da un file non corrispondente alla tabella di destinazione, è possibile che l'operazione di importazione riesca ma i dati della tabella di destinazione potrebbero non essere corretti.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-119">If you import data from a file that is mismatched with the target table, the import operation might succeed but the data values inserted into the target table are likely to be incorrect.</span></span> <span data-ttu-id="b3d3e-120">Ciò è dovuto al fatto che i dati del file vengono interpretati utilizzando il formato della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-120">This is because the data from the file is interpreted by using the format of the target table.</span></span> <span data-ttu-id="b3d3e-121">Pertanto, la mancata corrispondenza causa l'inserimento di valori non corretti</span><span class="sxs-lookup"><span data-stu-id="b3d3e-121">Therefore, any mismatch results in the insertion of incorrect values.</span></span> <span data-ttu-id="b3d3e-122">ma in nessun caso può determinare inconsistenze di tipo logico o fisico nel database.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-122">However, under no circumstances can such a mismatch cause logical or physical inconsistencies in the database.</span></span>  
  
     <span data-ttu-id="b3d3e-123">Per altre informazioni sull'uso dei file di formato, vedere [File di formato per l'importazione o l'esportazione di dati &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3d3e-123">For information on using format files, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="b3d3e-124">Un'importazione corretta non danneggerà la tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-124">A successful import will not corrupt the target table.</span></span>  
  
## <a name="how-bcp-handles-data-in-native-format"></a><span data-ttu-id="b3d3e-125">Gestione dei dati in formato nativo mediante l'utilità bcp</span><span class="sxs-lookup"><span data-stu-id="b3d3e-125">How bcp Handles Data in Native Format</span></span>  
 <span data-ttu-id="b3d3e-126">In questa sezione sono contenute considerazioni particolari sull'importazione e sull'esportazione dei dati in formato nativo mediante l'utilità **bcp** .</span><span class="sxs-lookup"><span data-stu-id="b3d3e-126">This section discusses special considerations for how the **bcp** utility exports and imports data in native format.</span></span>  
  
-   <span data-ttu-id="b3d3e-127">Dati non di tipo carattere</span><span class="sxs-lookup"><span data-stu-id="b3d3e-127">Noncharacter data</span></span>  
  
     <span data-ttu-id="b3d3e-128">L'utilità bcp utilizza il formato di dati binario interno di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per trasferire dati non di tipo carattere da una tabella in un file di dati.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-128">The bcp utility uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] internal binary data format to write noncharacter data from a table to a data file.</span></span>  
  
-   <span data-ttu-id="b3d3e-129">Dati `char` o `varchar`</span><span class="sxs-lookup"><span data-stu-id="b3d3e-129">`char` or `varchar` data</span></span>  
  
     <span data-ttu-id="b3d3e-130">All'inizio di ogni `char` campo o `varchar` , **bcp** aggiunge la lunghezza del prefisso.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-130">At the beginning of each `char` or `varchar` field, **bcp** adds the prefix length.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b3d3e-131">Quando viene utilizzata la modalità nativa, per impostazione predefinita l'utilità **bcp** converte i caratteri da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a caratteri OEM prima di copiarli in un file di dati.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-131">When native mode is used, by default, the **bcp** utility converts characters from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to OEM characters before it copies them to a data file.</span></span> <span data-ttu-id="b3d3e-132">L'utilità **bcp** converte i caratteri di un file di dati in caratteri ANSI prima di eseguirne l'importazione bulk in una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabella.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-132">The **bcp** utility converts characters from a data file to ANSI characters before it bulk imports them into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="b3d3e-133">Durante queste conversioni può verificarsi la perdita dei dati con caratteri estesi.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-133">During these conversions, extended character data can be lost.</span></span> <span data-ttu-id="b3d3e-134">Per i caratteri estesi, è necessario utilizzare il formato nativo Unicode o specificare una tabella codici.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-134">For extended characters, either use Unicode native format or specify a code page.</span></span>  
  
-   <span data-ttu-id="b3d3e-135">Dati `sql_variant`</span><span class="sxs-lookup"><span data-stu-id="b3d3e-135">`sql_variant` data</span></span>  
  
     <span data-ttu-id="b3d3e-136">Se i dati `sql_variant` vengono archiviati come SQLVARIANT in un file di dati in formato nativo, verranno mantenute tutte le relative caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-136">If `sql_variant` data is stored as a SQLVARIANT in a native-format data file, the data maintains all of its characteristics.</span></span> <span data-ttu-id="b3d3e-137">I metadati che registrano il tipo di dati di ogni valore vengono archiviati insieme al valore stesso.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-137">The metadata that records the data type of each data value is stored along with the data value.</span></span> <span data-ttu-id="b3d3e-138">Questi metadati vengono utilizzati per creare di nuovo il valore con lo stesso tipo di dati in una colonna di destinazione `sql_variant`.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-138">This metadata is used to re-create the data value with the same data type in a destination `sql_variant` column.</span></span>  
  
     <span data-ttu-id="b3d3e-139">Se il tipo di dati della colonna di destinazione è diverso da `sql_variant`, ogni valore viene convertito nel tipo di dati della colonna di destinazione, in base alle regole standard di conversione implicita dei dati.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-139">If the data type of the destination column is not `sql_variant`, each data value is converted to the data type of the destination column, following the normal rules of implicit data conversion.</span></span> <span data-ttu-id="b3d3e-140">Se si verifica un errore durante la conversione dei dati, viene eseguito il rollback del batch corrente.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-140">If an error occurs during data conversion, the current batch is rolled back.</span></span> <span data-ttu-id="b3d3e-141">Per i valori `char` e `varchar` trasferiti tra colonne `sql_variant` possono verificarsi problemi relativi alla conversione di tabelle codici.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-141">Any `char` and `varchar` values that are transferred between `sql_variant` columns may have code page conversion issues.</span></span>  
  
     <span data-ttu-id="b3d3e-142">Per altre informazioni sulla conversione dei dati, vedere [Conversione del tipo di dati &#40;Motore di database&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span><span class="sxs-lookup"><span data-stu-id="b3d3e-142">For more information about data conversion, see [Data Type Conversion &#40;Database Engine&#41;](/sql/t-sql/data-types/data-type-conversion-database-engine).</span></span>  
  
## <a name="command-options-for-native-format"></a><span data-ttu-id="b3d3e-143">Opzioni di comando per il formato nativo</span><span class="sxs-lookup"><span data-stu-id="b3d3e-143">Command Options for Native Format</span></span>  
 <span data-ttu-id="b3d3e-144">È possibile importare dati in formato nativo in una tabella utilizzando **bcp**, BULK INSERT o INSERT... SELECT \* FROM OPENROWSET (bulk...). Per un comando **bcp** o un'istruzione BULK INSERT, è possibile specificare il formato dati nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-144">You can import native format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="b3d3e-145">Per un'istruzione INSERT ... SELECT \* FROM OPENROWSET(BULK...) è necessario specificare il formato dati in un file di formato.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-145">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="b3d3e-146">Il formato nativo viene supportato dalle opzioni della riga di comando seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3d3e-146">Native format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="b3d3e-147">Comando</span><span class="sxs-lookup"><span data-stu-id="b3d3e-147">Command</span></span>|<span data-ttu-id="b3d3e-148">Opzione</span><span class="sxs-lookup"><span data-stu-id="b3d3e-148">Option</span></span>|<span data-ttu-id="b3d3e-149">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3d3e-149">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="b3d3e-150">**bcp**</span><span class="sxs-lookup"><span data-stu-id="b3d3e-150">**bcp**</span></span>|<span data-ttu-id="b3d3e-151">**-n**</span><span class="sxs-lookup"><span data-stu-id="b3d3e-151">**-n**</span></span>|<span data-ttu-id="b3d3e-152">Consente all'utilità **bcp** di utilizzare i tipi di dati nativi dei dati. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b3d3e-152">Causes the **bcp** utility to use the native data types of the data.<sup>1</sup></span></span>|  
|<span data-ttu-id="b3d3e-153">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="b3d3e-153">BULK INSERT</span></span>|<span data-ttu-id="b3d3e-154">FileType **='** Native **'**</span><span class="sxs-lookup"><span data-stu-id="b3d3e-154">DATAFILETYPE **='** native **'**</span></span>|<span data-ttu-id="b3d3e-155">Utilizza i tipi di dati nativi o nativi estesi.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-155">Uses the native or wide native data types of the data.</span></span> <span data-ttu-id="b3d3e-156">Si noti che DATAFILETYPE non è necessario se i tipi di dati vengono specificati in un file di formato.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-156">Note that DATAFILETYPE is not needed if a format file specifies the data types.</span></span>|  
  
 <span data-ttu-id="b3d3e-157"><sup>1</sup> per caricare i dati nativi (**-n**) in un formato compatibile con le versioni precedenti dei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client, usare l'opzione **-V** .</span><span class="sxs-lookup"><span data-stu-id="b3d3e-157"><sup>1</sup> To load native (**-n**) data to a format compatible with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients, use the **-V** switch.</span></span> <span data-ttu-id="b3d3e-158">Per altre informazioni, vedere [Importare dati in formato nativo e carattere da versioni precedenti di SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3d3e-158">For more information, see [Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md).</span></span>  
  
 <span data-ttu-id="b3d3e-159">Per altre informazioni, vedere [Utilità bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) o [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b3d3e-159">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b3d3e-160">In alternativa, è possibile definire la formattazione di ogni singolo campo in un file di formato.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-160">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="b3d3e-161">Per altre informazioni, vedere [File di formato per l'importazione o l'esportazione di dati &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3d3e-161">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b3d3e-162">Esempi</span><span class="sxs-lookup"><span data-stu-id="b3d3e-162">Examples</span></span>  
 <span data-ttu-id="b3d3e-163">Gli esempi seguenti mostrano come eseguire l'esportazione in blocco di dati nativi usando **bcp** e l'importazione in blocco degli stessi dati usando BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-163">The following examples demonstrate how to bulk export native data using **bcp** and bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="b3d3e-164">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="b3d3e-164">Sample Table</span></span>  
 <span data-ttu-id="b3d3e-165">È necessario creare innanzitutto una tabella denominata **myTestNativeData** nel database di esempio **AdventureWorks** all'interno dello schema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-165">The examples require that a table named **myTestNativeData** table be created in the **AdventureWorks** sample database under the **dbo** schema.</span></span> <span data-ttu-id="b3d3e-166">Prima di eseguire le procedure illustrate negli esempi, è necessario creare la tabella.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-166">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="b3d3e-167">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="b3d3e-167">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
CREATE TABLE myTestNativeData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="b3d3e-168">Per popolare la tabella e visualizzare il contenuto risultante, eseguire le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3d3e-168">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3');  
INSERT INTO myTestNativeData(Col1,Col2,Col3)  
   VALUES(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
  
```  
  
### <a name="using-bcp-to-bulk-export-native-data"></a><span data-ttu-id="b3d3e-169">Utilizzo del comando bcp per l'esportazione bulk di dati nativi</span><span class="sxs-lookup"><span data-stu-id="b3d3e-169">Using bcp to Bulk Export Native Data</span></span>  
 <span data-ttu-id="b3d3e-170">Per esportare i dati dalla tabella al file di dati, usare **bcp** con l'opzione **out** e i qualificatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3d3e-170">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="b3d3e-171">Qualificatori</span><span class="sxs-lookup"><span data-stu-id="b3d3e-171">Qualifiers</span></span>|<span data-ttu-id="b3d3e-172">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3d3e-172">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="b3d3e-173">**-n**</span><span class="sxs-lookup"><span data-stu-id="b3d3e-173">**-n**</span></span>|<span data-ttu-id="b3d3e-174">Specifica i tipi di dati nativi.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-174">Specifies native data types.</span></span>|  
|<span data-ttu-id="b3d3e-175">**-T**</span><span class="sxs-lookup"><span data-stu-id="b3d3e-175">**-T**</span></span>|<span data-ttu-id="b3d3e-176">Specifica che l'utilità **bcp** si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una connessione trusted che usa la sicurezza integrata.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-176">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="b3d3e-177">Se non si specifica **-T** , è necessario specificare **-U** e **-P** per eseguire correttamente l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-177">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="b3d3e-178">Nel seguente esempio viene eseguita l'esportazione bulk dei dati in formato nativo dalla tabella `myTestNativeData` in un nuovo file di dati denominato `myTestNativeData-n.Dat`.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-178">The following example bulk exports data in native format from the `myTestNativeData` table into a new data file named `myTestNativeData-n.Dat` data file.</span></span> <span data-ttu-id="b3d3e-179">Al prompt dei comandi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="b3d3e-179">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks..myTestNativeData out C:\myTestNativeData-n.Dat -n -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-native-data"></a><span data-ttu-id="b3d3e-180">Utilizzo dell'istruzione BULK INSERT per l'importazione bulk di dati nativi</span><span class="sxs-lookup"><span data-stu-id="b3d3e-180">Using BULK INSERT to Bulk Import Native Data</span></span>  
 <span data-ttu-id="b3d3e-181">Nell'esempio seguente si utilizza BULK INSERT per importare i dati dal file di dati `myTestNativeData-n.Dat` nella tabella `myTestNativeData`.</span><span class="sxs-lookup"><span data-stu-id="b3d3e-181">The following example uses BULK INSERT to import the data in the `myTestNativeData-n.Dat` data file into the `myTestNativeData` table.</span></span> <span data-ttu-id="b3d3e-182">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="b3d3e-182">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks;  
GO  
BULK INSERT myTestNativeData   
    FROM 'C:\myTestNativeData-n.Dat'   
   WITH (DATAFILETYPE='native');   
GO  
SELECT Col1,Col2,Col3 FROM myTestNativeData  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b3d3e-183">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="b3d3e-183">Related Tasks</span></span>  
 <span data-ttu-id="b3d3e-184">**Per utilizzare formati di dati per l'importazione o l'esportazione bulk**</span><span class="sxs-lookup"><span data-stu-id="b3d3e-184">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="b3d3e-185">Importare dati in formato nativo e carattere da versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b3d3e-185">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="b3d3e-186">Utilizzo del formato carattere per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b3d3e-186">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="b3d3e-187">Utilizzo del formato carattere Unicode per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b3d3e-187">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="b3d3e-188">Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b3d3e-188">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b3d3e-189">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3d3e-189">See Also</span></span>  
 <span data-ttu-id="b3d3e-190">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b3d3e-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="b3d3e-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b3d3e-191">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="b3d3e-192">[Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b3d3e-192">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="b3d3e-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b3d3e-193">[sql_variant &#40;Transact-SQL&#41;](/sql/t-sql/data-types/sql-variant-transact-sql) </span></span>  
 <span data-ttu-id="b3d3e-194">[Importare dati in formato nativo e carattere da versioni precedenti di SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b3d3e-194">[Import Native and Character Format Data from Earlier Versions of SQL Server](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md) </span></span>  
 <span data-ttu-id="b3d3e-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b3d3e-195">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 [<span data-ttu-id="b3d3e-196">Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b3d3e-196">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
  
