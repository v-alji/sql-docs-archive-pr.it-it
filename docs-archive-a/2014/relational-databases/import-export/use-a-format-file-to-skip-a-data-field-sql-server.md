---
title: Usare un file di formato per ignorare un campo dati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], skipping data fields
- skipping data fields when importing
ms.assetid: 6a76517e-983b-47a1-8f02-661b99859a8b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2d3f78c3c97c5bbe862867d5f51ff35f57d147df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638407"
---
# <a name="use-a-format-file-to-skip-a-data-field-sql-server"></a><span data-ttu-id="16cac-102">Utilizzo di un file di formato per escludere un campo di dati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="16cac-102">Use a Format File to Skip a Data Field (SQL Server)</span></span>
  <span data-ttu-id="16cac-103">È possibile che un file di dati contenga un numero di campi maggiore del numero di colonne presenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="16cac-103">A data file can contain more fields than the number of columns in the table.</span></span> <span data-ttu-id="16cac-104">In questo argomento viene descritta la modifica dei file di formato XML e non XML per consentire l'utilizzo di un file di dati con un numero maggiore di campi tramite il mapping delle colonne della tabella ai campi dati corrispondenti e l'esclusione dei campi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="16cac-104">This topic describes modifying both non-XML and XML format files to accommodate a data file with more fields by mapping the table columns to the corresponding data fields and ignoring the extra fields.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16cac-105">È possibile utilizzare un file di formato non XML o XML per importare in blocco un file di dati nella tabella utilizzando un comando **bcp** , un'istruzione BULK INSERT o un'istruzione INSERT... Istruzione SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="16cac-105">Either a non-XML or XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="16cac-106">Per altre informazioni, vedere [Usare un file di formato per l'importazione in blocco dei dati &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="16cac-106">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-data-file-and-table"></a><span data-ttu-id="16cac-107">File di dati e tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="16cac-107">Sample Data File and Table</span></span>  
 <span data-ttu-id="16cac-108">Gli esempi di file di formato modificati contenuti in questo argomento sono basati sulla tabella e sul file di dati seguenti.</span><span class="sxs-lookup"><span data-stu-id="16cac-108">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="16cac-109">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="16cac-109">Sample Table</span></span>  
 <span data-ttu-id="16cac-110">Per gli esempi, è necessario che nel database di esempio `myTestSkipField` venga creata una tabella [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] basata sullo schema `dbo` .</span><span class="sxs-lookup"><span data-stu-id="16cac-110">The examples require that a table named `myTestSkipField` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="16cac-111">Per creare questa tabella, nell' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] editor di query di eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="16cac-111">To create this table, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestSkipField   
   (  
   PersonID smallint,  
   FirstName nvarchar(50) ,  
   LastName nvarchar(50)   
   );  
GO  
```  
  
### <a name="sample-data-file"></a><span data-ttu-id="16cac-112">File di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="16cac-112">Sample Data File</span></span>  
 <span data-ttu-id="16cac-113">Il file di dati `myTestSkipField-c.dat` include i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="16cac-113">The data file, `myTestSkipField-c.dat`, contains the following records:</span></span>  
  
```  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
1,Skipme,DataField3,DataField4  
```  
  
 <span data-ttu-id="16cac-114">Per eseguire un'importazione bulk dei dati da `myTestSkipField-c.dat` nella tabella `myTestSkipField` , è necessario che il file di formato esegua le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16cac-114">To bulk import data from `myTestSkipField-c.dat` into the `myTestSkipField` table, the format file must do the following:</span></span>  
  
-   <span data-ttu-id="16cac-115">Mapping del primo campo dati alla prima colonna `PersonID`.</span><span class="sxs-lookup"><span data-stu-id="16cac-115">Map the first data field to the first column, `PersonID`.</span></span>  
  
-   <span data-ttu-id="16cac-116">Esclusione del secondo campo dati.</span><span class="sxs-lookup"><span data-stu-id="16cac-116">Skip the second data field.</span></span>  
  
-   <span data-ttu-id="16cac-117">Mapping del terzo campo dati alla seconda colonna `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="16cac-117">Map the third data field to the second column, `FirstName`.</span></span>  
  
-   <span data-ttu-id="16cac-118">Mapping del quarto campo dati alla terza colonna `LastName`.</span><span class="sxs-lookup"><span data-stu-id="16cac-118">Map the fourth data field to the third column, `LastName`.</span></span>  
  
## <a name="non-xml-format-file-for-more-data-fields"></a><span data-ttu-id="16cac-119">File di formato non XML per un maggior numero di campi dati</span><span class="sxs-lookup"><span data-stu-id="16cac-119">Non-XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="16cac-120">Il file di formato seguente, `myTestSkipField.fmt`, esegue il mapping dei campi di `myTestSkipField-c.dat` alle colonne della tabella `myTestSkipField`</span><span class="sxs-lookup"><span data-stu-id="16cac-120">The following format file, `myTestSkipField.fmt`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="16cac-121">Il file di formato utilizza dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="16cac-121">The format file uses character data format.</span></span> <span data-ttu-id="16cac-122">Per escludere il mapping di una colonna, è necessario modificare il valore relativo all'ordine della colonna impostandolo su 0, come illustrato per la colonna `ExtraField` nel file di formato.</span><span class="sxs-lookup"><span data-stu-id="16cac-122">Skipping a column mapping requires changing its column order value to 0, as shown for the `ExtraField` column in the format file.</span></span>  
  
 <span data-ttu-id="16cac-123">Il file di formato `myTestSkipField.fmt` contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16cac-123">The `myTestSkipField.fmt` format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       7       ","      1     PersonID               ""  
2       SQLCHAR       0       100       ","    0     ExtraField             SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       100     ","      2     FirstName              SQL_Latin1_General_CP1_CI_AS  
4       SQLCHAR       0       100     "\r\n"   3     LastName               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="16cac-124">Per informazioni sulla sintassi dei file di formato non XML, vedere [File in formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="16cac-124">For information about the syntax of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="examples"></a><span data-ttu-id="16cac-125">Esempi</span><span class="sxs-lookup"><span data-stu-id="16cac-125">Examples</span></span>  
 <span data-ttu-id="16cac-126">Nell'esempio seguente viene utilizzata l'istruzione `INSERT ... SELECT * FROM OPENROWSET(BULK...)` con il file di formato `myTestSkipField.fmt` .</span><span class="sxs-lookup"><span data-stu-id="16cac-126">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.fmt` format file.</span></span> <span data-ttu-id="16cac-127">Nell'esempio viene eseguita l'importazione bulk del file di dati `myTestSkipField-c.dat` nella tabella `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="16cac-127">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="16cac-128">Per creare il file di dati e la tabella di esempio, vedere la sezione "File di dati e tabella di esempio" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="16cac-128">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="16cac-129">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="16cac-129">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
   SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.fmt'    
       ) AS t1;  
GO   
```  
  
## <a name="xml-format-file-for-more-data-fields"></a><span data-ttu-id="16cac-130">File di formato XML per un maggior numero di campi dati</span><span class="sxs-lookup"><span data-stu-id="16cac-130">XML Format File for More Data Fields</span></span>  
 <span data-ttu-id="16cac-131">Il file di formato utilizzato in questo esempio è basato su un altro file di formato, `myTestSkipField.xml`, che utilizza il formato di dati carattere e i cui campi corrispondono esattamente per numero e ordine alle colonne della tabella `myTestSkipField`.</span><span class="sxs-lookup"><span data-stu-id="16cac-131">The format file presented in this example is based on another format file, `myTestSkipField.xml`, which uses character data format throughout and whose fields correspond exactly in number and order to the columns in the `myTestSkipField` table.</span></span> <span data-ttu-id="16cac-132">Per visualizzare il contenuto del file di formato, vedere [Creare un file di formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="16cac-132">To view the contents of that format file, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
 <span data-ttu-id="16cac-133">Il file di formato seguente, `myTestSkipField.xml`, esegue il mapping dei campi di `myTestSkipField-c.dat` alle colonne della tabella `myTestSkipField`</span><span class="sxs-lookup"><span data-stu-id="16cac-133">The following format file, `myTestSkipField.xml`, maps the fields in `myTestSkipField-c.dat` to the columns of the `myTestSkipField` table.</span></span> <span data-ttu-id="16cac-134">Il file di formato utilizza dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="16cac-134">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="16cac-135">Il file di formato `myTestSkipField.xml` contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="16cac-135">The `myTestSkipField.xml` format file contains the following information:</span></span>  
  
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
  <COLUMN SOURCE="1" NAME="PersonID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="3" NAME="FirstName" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="LastName" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
### <a name="examples"></a><span data-ttu-id="16cac-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="16cac-136">Examples</span></span>  
 <span data-ttu-id="16cac-137">Nell'esempio seguente viene utilizzata l'istruzione `INSERT ... SELECT * FROM OPENROWSET(BULK...)` con il file di formato `myTestSkipField.Xml` .</span><span class="sxs-lookup"><span data-stu-id="16cac-137">The following example uses `INSERT ... SELECT * FROM OPENROWSET(BULK...)` using the `myTestSkipField.Xml` format file.</span></span> <span data-ttu-id="16cac-138">Nell'esempio viene eseguita l'importazione bulk del file di dati `myTestSkipField-c.dat` nella tabella `myTestSkipField` .</span><span class="sxs-lookup"><span data-stu-id="16cac-138">The example bulk imports the `myTestSkipField-c.dat` data file into the `myTestSkipField` table.</span></span> <span data-ttu-id="16cac-139">Per creare il file di dati e la tabella di esempio, vedere la sezione "File di dati e tabella di esempio" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="16cac-139">To create the sample table and data file, see "Sample Data File and Table," earlier in this topic.</span></span>  
  
 <span data-ttu-id="16cac-140">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="16cac-140">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, run the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestSkipField   
  SELECT *  
      FROM  OPENROWSET(BULK  'C:\myTestSkipField-c.dat',  
      FORMATFILE='C:\myTestSkipField.xml'    
       ) AS t1;  
GO  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="16cac-141">Per altre informazioni sulla sintassi dell'XML Schema e ulteriori esempi di file di formato XML, vedere [File in formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="16cac-141">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16cac-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16cac-142">See Also</span></span>  
 <span data-ttu-id="16cac-143">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="16cac-143">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="16cac-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="16cac-144">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="16cac-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="16cac-145">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="16cac-146">[Utilizzo di un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="16cac-146">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="16cac-147">Utilizzo di un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="16cac-147">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
  
