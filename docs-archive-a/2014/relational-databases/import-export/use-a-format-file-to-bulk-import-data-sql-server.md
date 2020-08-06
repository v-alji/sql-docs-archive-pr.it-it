---
title: Usare un file di formato per l'importazione in blocco dei dati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk importing [SQL Server], format files
- format files [SQL Server], importing data using
ms.assetid: 2956df78-833f-45fa-8a10-41d6522562b9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c6d9779209b3ffb317658243c168d74740f6731b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638408"
---
# <a name="use-a-format-file-to-bulk-import-data-sql-server"></a><span data-ttu-id="40a0d-102">Utilizzo di un file di formato per l'importazione bulk dei dati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="40a0d-102">Use a Format File to Bulk Import Data (SQL Server)</span></span>
  <span data-ttu-id="40a0d-103">In questo argomento viene illustrato l'utilizzo di un file di formato per operazioni di importazione bulk.</span><span class="sxs-lookup"><span data-stu-id="40a0d-103">This topic illustrates the use of a format file in bulk-import operations.</span></span> <span data-ttu-id="40a0d-104">Il file di formato esegue il mapping dei campi del file di dati alle colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="40a0d-104">The format file maps the fields of the data file to the columns of the table.</span></span>  <span data-ttu-id="40a0d-105">È possibile utilizzare un file di formato XML o non XML per eseguire un'importazione bulk dei dati quando si utilizza un comando **bcp** o un BULK INSERT o un'istruzione INSERT... SELECT \* FROM OPENROWSET (BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] comando.</span><span class="sxs-lookup"><span data-stu-id="40a0d-105">You can use a non-XML or XML format file to bulk import data when using a **bcp** command or a BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...) [!INCLUDE[tsql](../../includes/tsql-md.md)] command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="40a0d-106">Affinché un file di formato sia funzionante con un file di dati di formato carattere Unicode, è necessario che tutti i campi di input siano stringhe di testo Unicode, ovvero stringhe Unicode di dimensioni fisse o che terminano con un carattere.</span><span class="sxs-lookup"><span data-stu-id="40a0d-106">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40a0d-107">Se non si ha familiarità con i file di formato, vedere [file di formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) e [file di formato xml &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="40a0d-107">If you are unfamiliar with format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) and [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="format-file-options-for-bulk-import-commands"></a><span data-ttu-id="40a0d-108">Opzioni del file di formato per comandi di importazione bulk</span><span class="sxs-lookup"><span data-stu-id="40a0d-108">Format File Options for Bulk-Import Commands</span></span>  
 <span data-ttu-id="40a0d-109">Nella tabella seguente vengono riepilogate le opzioni del file di formato per ogni comando di importazione bulk.</span><span class="sxs-lookup"><span data-stu-id="40a0d-109">The following table summarizes the format-file option of for each of the bulk-import commands.</span></span>  
  
|<span data-ttu-id="40a0d-110">Comando di caricamento bulk</span><span class="sxs-lookup"><span data-stu-id="40a0d-110">Bulk-load Command</span></span>|<span data-ttu-id="40a0d-111">Utilizzo dell'opzione del file di formato</span><span class="sxs-lookup"><span data-stu-id="40a0d-111">Using the Format-File Option</span></span>|  
|------------------------|-----------------------------------|  
|<span data-ttu-id="40a0d-112">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="40a0d-112">BULK INSERT</span></span>|<span data-ttu-id="40a0d-113">FORMATFILE = '*format_file_path*'</span><span class="sxs-lookup"><span data-stu-id="40a0d-113">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="40a0d-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="40a0d-114">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>|<span data-ttu-id="40a0d-115">FORMATFILE = '*format_file_path*'</span><span class="sxs-lookup"><span data-stu-id="40a0d-115">FORMATFILE = '*format_file_path*'</span></span>|  
|<span data-ttu-id="40a0d-116">**bcp** ... **in**</span><span class="sxs-lookup"><span data-stu-id="40a0d-116">**bcp** ... **in**</span></span>|<span data-ttu-id="40a0d-117">**-f** *format_file*</span><span class="sxs-lookup"><span data-stu-id="40a0d-117">**-f** *format_file*</span></span>|  
  
 <span data-ttu-id="40a0d-118">Per altre informazioni, vedere [Utilità bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) o [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40a0d-118">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="40a0d-119">Per eseguire l'esportazione o l'importazione bulk di dati SQLXML, utilizzare uno dei tipi di dati seguenti nel file di formato: SQLCHAR o SQLVARYCHAR (i dati vengono inviati nella tabella codici del client o nella tabella codici implicita nelle regole di confronto), SQLNCHAR o SQLNVARCHAR (i dati vengono inviati come Unicode) oppure SQLBINARY o SQLVARYBIN (i dati vengono inviati senza conversione).</span><span class="sxs-lookup"><span data-stu-id="40a0d-119">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="40a0d-120">Esempi</span><span class="sxs-lookup"><span data-stu-id="40a0d-120">Examples</span></span>  
 <span data-ttu-id="40a0d-121">Negli esempi di questa sezione viene illustrato come utilizzare i file di formato per eseguire l'importazione bulk dei dati utilizzando il comando **bcp** e il BULK INSERT e INSERT... SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="40a0d-121">The examples in this section illustrate how to use format files to bulk-import data by using the **bcp** command and the BULK INSERT, and INSERT ... SELECT \* FROM OPENROWSET(BULK...) statements.</span></span> <span data-ttu-id="40a0d-122">Prima di eseguire uno degli esempi di importazione bulk, è necessario creare una tabella, un file di dati e un file di formato di esempio.</span><span class="sxs-lookup"><span data-stu-id="40a0d-122">Before you can run one of the bulk-import examples, you need to create a sample table, data file, and a format file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="40a0d-123">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="40a0d-123">Sample Table</span></span>  
 <span data-ttu-id="40a0d-124">Gli esempi richiedono la creazione di una tabella denominata **myTestFormatFiles** nel database di esempio [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] in base allo schema **dbo**.</span><span class="sxs-lookup"><span data-stu-id="40a0d-124">The examples require that a table named **myTestFormatFiles** table be created in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="40a0d-125">Per creare la tabella, nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="40a0d-125">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestFormatFiles (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50),  
   Col4 nvarchar(50)  
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="40a0d-126">File di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="40a0d-126">Sample Data File</span></span>  
 <span data-ttu-id="40a0d-127">Nell'esempio viene utilizzato un file di dati di esempio, `myTestFormatFiles-c.Dat`, che include i record riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="40a0d-127">The examples use a sample data file, `myTestFormatFiles-c.Dat`, which contains the following records.</span></span> <span data-ttu-id="40a0d-128">Per creare il file di dati, al prompt dei comandi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="40a0d-128">To create the data file, at the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
10,Field2,Field3,Field4  
15,Field2,Field3,Field4  
46,Field2,Field3,Field4  
58,Field2,Field3,Field4  
```  
  
### <a name="sample-format-files"></a><span data-ttu-id="40a0d-129">File di formato di esempio</span><span class="sxs-lookup"><span data-stu-id="40a0d-129">Sample Format Files</span></span>  
 <span data-ttu-id="40a0d-130">In alcuni esempi di questa sezione viene utilizzato un file di formato XML, `myTestFormatFiles-f-x-c.Xml`, mentre in altri esempi viene utilizzato un file di formato non XML.</span><span class="sxs-lookup"><span data-stu-id="40a0d-130">Some of the examples in this section use an XML format file, `myTestFormatFiles-f-x-c.Xml`, and other examples use a non-XML format file.</span></span> <span data-ttu-id="40a0d-131">In entrambi i file di formato viene utilizzato il formato carattere e un carattere di terminazione del campo non predefinito (,).</span><span class="sxs-lookup"><span data-stu-id="40a0d-131">Both format files use character data formats and a non-default field terminator (,).</span></span>  
  
#### <a name="the-sample-non-xml-format-file"></a><span data-ttu-id="40a0d-132">File di formato non XML di esempio</span><span class="sxs-lookup"><span data-stu-id="40a0d-132">The Sample Non-XML Format File</span></span>  
 <span data-ttu-id="40a0d-133">L'esempio seguente usa **bcp** per generare un file di formato XML dalla tabella `myTestFormatFiles`.</span><span class="sxs-lookup"><span data-stu-id="40a0d-133">The following example uses **bcp** to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="40a0d-134">Il file `myTestFormatFiles.Fmt` contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a0d-134">The `myTestFormatFiles.Fmt` file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     Col1         ""  
2       SQLCHAR       0       100     ","      2     Col2         SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      3     Col3         SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   4     Col4         SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="40a0d-135">Per usare **bcp** con l'opzione **format** per creare questo file di formato, al prompt dei comandi di Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="40a0d-135">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -f myTestFormatFiles.Fmt -T  
  
```  
  
 <span data-ttu-id="40a0d-136">Per altre informazioni sulla creazione di un file di formato, vedere [Creazione di un file di formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="40a0d-136">For more information about creating a format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
#### <a name="the-sample-xml-format-file"></a><span data-ttu-id="40a0d-137">File di formato XML di esempio</span><span class="sxs-lookup"><span data-stu-id="40a0d-137">The Sample XML Format File</span></span>  
 <span data-ttu-id="40a0d-138">L'esempio seguente viene usa **bcp** per creare un file di formato XML dalla tabella `myTestFormatFiles`.</span><span class="sxs-lookup"><span data-stu-id="40a0d-138">The following example uses **bcp** to create to generate an XML format file from the `myTestFormatFiles` table.</span></span> <span data-ttu-id="40a0d-139">Il file `myTestFormatFiles.Xml` contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="40a0d-139">The `myTestFormatFiles.Xml` file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="40a0d-140">Per usare **bcp** con l'opzione **format** per creare questo file di formato, al prompt dei comandi di Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="40a0d-140">To use **bcp** with the **format** option to create this format file, at the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..MyTestFormatFiles format nul -c -t, -x -f myTestFormatFiles.Xml -T  
```  
  
### <a name="using-bcp"></a><span data-ttu-id="40a0d-141">Utilizzo di bcp</span><span class="sxs-lookup"><span data-stu-id="40a0d-141">Using bcp</span></span>  
 <span data-ttu-id="40a0d-142">L'esempio seguente usa **bcp** per l'importazione in blocco dei dati dal file di dati `myTestFormatFiles-c.Dat` nella tabella `HumanResources.myTestFormatFiles` del database di esempio.</span><span class="sxs-lookup"><span data-stu-id="40a0d-142">The following example uses **bcp** to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the  sample database.</span></span> <span data-ttu-id="40a0d-143">In questo esempio viene utilizzato un file di formato XML, `MyTestFormatFiles.Xml`,</span><span class="sxs-lookup"><span data-stu-id="40a0d-143">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="40a0d-144">ed eventuali righe di tabella esistenti vengono eliminate prima dell'importazione del file di dati.</span><span class="sxs-lookup"><span data-stu-id="40a0d-144">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="40a0d-145">Al prompt dei comandi di Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="40a0d-145">At the Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestFormatFiles in C:\myTestFormatFiles-c.Dat -f C:\myTestFormatFiles.Xml -T  
```  
  
> [!NOTE]  
>  <span data-ttu-id="40a0d-146">Per altre informazioni su questo comando, vedere [Utilità bcp](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="40a0d-146">For more information about this command, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
### <a name="using-bulk-insert"></a><span data-ttu-id="40a0d-147">Utilizzo di BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="40a0d-147">Using BULK INSERT</span></span>  
 <span data-ttu-id="40a0d-148">Nell'esempio seguente viene utilizzato BULK INSERT per l'importazione bulk dei dati dal file di dati `myTestFormatFiles-c.Dat` nella tabella `HumanResources.myTestFormatFiles` del database di esempio [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="40a0d-148">The following example uses BULK INSERT to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="40a0d-149">In questo esempio viene utilizzato un file di formato non XML, `MyTestFormatFiles.Fmt`,</span><span class="sxs-lookup"><span data-stu-id="40a0d-149">This example uses a non-XML format file, `MyTestFormatFiles.Fmt`.</span></span> <span data-ttu-id="40a0d-150">ed eventuali righe di tabella esistenti vengono eliminate prima dell'importazione del file di dati.</span><span class="sxs-lookup"><span data-stu-id="40a0d-150">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="40a0d-151">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="40a0d-151">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DELETE myTestFormatFiles;  
GO  
BULK INSERT myTestFormatFiles   
   FROM 'C:\myTestFormatFiles-c.Dat'   
   WITH (FORMATFILE = 'C:\myTestFormatFiles.Fmt');  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
> [!NOTE]  
>  <span data-ttu-id="40a0d-152">Per altre informazioni su questa istruzione, vedere [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40a0d-152">For more information about this statement, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
### <a name="using-the-openrowset-bulk-rowset-provider"></a><span data-ttu-id="40a0d-153">Utilizzo del provider di set di righe con lettura bulk OPENROWSET</span><span class="sxs-lookup"><span data-stu-id="40a0d-153">Using the OPENROWSET Bulk Rowset Provider</span></span>  
 <span data-ttu-id="40a0d-154">Nell'esempio seguente viene utilizzato `INSERT ... SELECT * FROM OPENROWSET(BULK...)` per l'importazione bulk dei dati dal file di dati `myTestFormatFiles-c.Dat` nella tabella `HumanResources.myTestFormatFiles` del database di esempio `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="40a0d-154">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` to bulk import data from the `myTestFormatFiles-c.Dat` data file into `HumanResources.myTestFormatFiles` table in the `AdventureWorks` sample database.</span></span> <span data-ttu-id="40a0d-155">In questo esempio viene utilizzato un file di formato XML, `MyTestFormatFiles.Xml`,</span><span class="sxs-lookup"><span data-stu-id="40a0d-155">This example uses an XML format file, `MyTestFormatFiles.Xml`.</span></span> <span data-ttu-id="40a0d-156">ed eventuali righe di tabella esistenti vengono eliminate prima dell'importazione del file di dati.</span><span class="sxs-lookup"><span data-stu-id="40a0d-156">The example deletes any existing table rows before importing the data file.</span></span>  
  
 <span data-ttu-id="40a0d-157">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="40a0d-157">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
DELETE myTestFormatFiles;  
GO  
INSERT INTO myTestFormatFiles  
    SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestFormatFiles-c.Dat',  
      FORMATFILE='C:\myTestFormatFiles.Xml'       
      ) as t1 ;  
GO  
SELECT * FROM myTestFormatFiles;  
GO  
```  
  
 <span data-ttu-id="40a0d-158">Al termine dell'utilizzo della tabella di esempio, è possibile rimuoverla mediante l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="40a0d-158">When you finish using the sample table, you can drop it using the following statement:</span></span>  
  
```  
DROP TABLE myTestFormatFiles  
```  
  
> [!NOTE]  
>  <span data-ttu-id="40a0d-159">Per altre informazioni sulla clausola OPENROWSET BULK, vedere [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="40a0d-159">For more information about the OPENROWSET BULK clause, see [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="40a0d-160">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="40a0d-160">Additional Examples</span></span>  
 [<span data-ttu-id="40a0d-161">Creazione di un file di formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40a0d-161">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
 [<span data-ttu-id="40a0d-162">Utilizzo di un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40a0d-162">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
 [<span data-ttu-id="40a0d-163">Utilizzo di un file di formato per escludere un campo di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40a0d-163">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
 [<span data-ttu-id="40a0d-164">Utilizzo di un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40a0d-164">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="40a0d-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40a0d-165">See Also</span></span>  
 <span data-ttu-id="40a0d-166">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="40a0d-166">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="40a0d-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="40a0d-167">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="40a0d-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="40a0d-168">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="40a0d-169">[File in formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="40a0d-169">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="40a0d-170">File in formato XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="40a0d-170">XML Format Files &#40;SQL Server&#41;</span></span>](xml-format-files-sql-server.md)  
  
  
