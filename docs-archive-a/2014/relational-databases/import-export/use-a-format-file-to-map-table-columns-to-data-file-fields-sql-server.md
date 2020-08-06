---
title: Usare un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- mapping columns to fields during import [SQL Server]
- format files [SQL Server], mapping columns to fields
ms.assetid: e7ee4f7e-24c4-4eb7-84d2-41e57ccc1ef1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c7de0b5ce486f187a1bdd27197984aa3c411f4a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626095"
---
# <a name="use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server"></a><span data-ttu-id="568c2-102">Utilizzo di un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="568c2-102">Use a Format File to Map Table Columns to Data-File Fields (SQL Server)</span></span>
  <span data-ttu-id="568c2-103">Un file di dati può includere campi disposti in un ordine diverso da quello delle colonne corrispondenti presenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="568c2-103">A data file can contain fields arranged in a different order from the corresponding columns in the table.</span></span> <span data-ttu-id="568c2-104">In questo argomento vengono descritti file di formato sia non XML che XML, modificati per adattarli a un file di dati contenente campi disposti un ordine diverso da quello delle colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="568c2-104">This topic presents both non-XML and XML format files that have been modified to accommodate a data file whose fields are arranged in a different order from the table columns.</span></span> <span data-ttu-id="568c2-105">Il file di formato modificato esegue il mapping tra i campi dati e le colonne corrispondenti della tabella.</span><span class="sxs-lookup"><span data-stu-id="568c2-105">The modified format file maps the data fields to their corresponding table columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="568c2-106">È possibile utilizzare un file di formato non XML o un file di formato XML per l'importazione bulk di un file di dati nella tabella tramite un comando **bcp** , un'istruzione BULK INSERT o un'istruzione INSERT... Istruzione SELECT \* FROM OPENROWSET (BULK...).</span><span class="sxs-lookup"><span data-stu-id="568c2-106">Either a non-XML format file or an XML format file can be used to bulk import a data file into the table by using a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="568c2-107">Per altre informazioni, vedere [Usare un file di formato per l'importazione in blocco dei dati &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="568c2-107">For more information, see [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md).</span></span>  
  
## <a name="sample-table-and-data-file"></a><span data-ttu-id="568c2-108">Tabella e file di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="568c2-108">Sample Table and Data File</span></span>  
 <span data-ttu-id="568c2-109">Gli esempi di file di formato modificati contenuti in questo argomento sono basati sulla tabella e sul file di dati seguenti.</span><span class="sxs-lookup"><span data-stu-id="568c2-109">The examples of modified format files in this topic are based on the following table and data file.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="568c2-110">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="568c2-110">Sample Table</span></span>  
 <span data-ttu-id="568c2-111">Per gli esempi di questo argomento è necessario creare una tabella denominata `myTestOrder` nel database di esempio [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] nello schema `dbo`.</span><span class="sxs-lookup"><span data-stu-id="568c2-111">The examples in this topic require that a table named `myTestOrder` be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="568c2-112">A tale scopo, nell'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="568c2-112">To create this table, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestOrder   
   (  
   Col1 smallint,  
   Col2 nvarchar(50) ,  
   Col3 nvarchar(50) ,   
   Col4 nvarchar(50)   
   );  
GO  
  
```  
  
### <a name="data-file"></a><span data-ttu-id="568c2-113">File di dati</span><span class="sxs-lookup"><span data-stu-id="568c2-113">Data File</span></span>  
 <span data-ttu-id="568c2-114">Il file di dati `myTestOrder-c.txt` include i record seguenti:</span><span class="sxs-lookup"><span data-stu-id="568c2-114">The data file, `myTestOrder-c.txt`, contains the following records:</span></span>  
  
```  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
DataField3,DataField2,1,DataField4  
  
```  
  
 <span data-ttu-id="568c2-115">Per eseguire l'importazione bulk dei dati da `myTestSkipCol2-c.dat` alla tabella `myTestSkipCol`, il file di formato deve eseguire il mapping tra il primo campo dati e `Col3`, il secondo campo dati e `Col2`, il terzo campo dati e `Col1` e il quarto campo dati e `Col4`.</span><span class="sxs-lookup"><span data-stu-id="568c2-115">To bulk import data from `myTestSkipCol2-c.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col3`, the second data field to `Col2`, the third data field to `Col1`, and the fourth data field to `Col4`.</span></span>  
  
## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="568c2-116">Utilizzo di un file di formato non XML</span><span class="sxs-lookup"><span data-stu-id="568c2-116">Using a Non-XML Format File</span></span>  
 <span data-ttu-id="568c2-117">È possibile cambiare l'ordine del mapping di una colonna modificando il valore relativo all'ordine della colonna per indicare la posizione del campo dati corrispondente.</span><span class="sxs-lookup"><span data-stu-id="568c2-117">You can change the order of a column mapping by changing the order value for the column to indicate the position of the corresponding data field.</span></span>  
  
 <span data-ttu-id="568c2-118">Nel seguente file di formato non XML di esempio è illustrato un file di formato, `myTestOrder.fmt`, che esegue il mapping tra i campi in `myTestOrder-c.txt` e le colonne della tabella `myTestOrder`.</span><span class="sxs-lookup"><span data-stu-id="568c2-118">The following sample non-XML format file presents a format file, `myTestOrder.fmt`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table.</span></span> <span data-ttu-id="568c2-119">Per informazioni su come creare la tabella e il file di dati, vedere "Tabella e file di dati di esempio", più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="568c2-119">For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="568c2-120">Il file di formato utilizza dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="568c2-120">The format file uses character data format.</span></span>  
  
 <span data-ttu-id="568c2-121">Il file di formato contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="568c2-121">The format file contains the following information:</span></span>  
  
```  
9.0  
4  
1       SQLCHAR       0       100     ","     3     Col3               SQL_Latin1_General_CP1_CI_AS  
2       SQLCHAR       0       100     ","     2     Col2               SQL_Latin1_General_CP1_CI_AS  
3       SQLCHAR       0       7       ","     1     Col1               ""  
4       SQLCHAR       0       100     "\r\n"  4     Col4               SQL_Latin1_General_CP1_CI_AS  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="568c2-122">Per altre informazioni sul layout dei file di formato non XML, vedere [File in formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="568c2-122">For more information about the layout of non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="568c2-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="568c2-123">Example</span></span>  
 <span data-ttu-id="568c2-124">Nell'esempio seguente viene utilizzata un'istruzione `BULK INSERT` per l'importazione bulk dei dati dal file di dati `myTestOrder-c.txt` alla tabella di esempio `myTestOrder` tramite il file di formato non XML `myTestOrder.fmt`.</span><span class="sxs-lookup"><span data-stu-id="568c2-124">The following example uses a `BULK INSERT` statement to bulk import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.fmt` non-XML format file.</span></span>  
  
 <span data-ttu-id="568c2-125">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="568c2-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestOrder  
FROM 'C:\myTestOrder-c.txt'   
WITH (formatfile='C:\myTestOrder.fmt');  
GO  
  
```  
  
## <a name="using-an-xml-format-file"></a><span data-ttu-id="568c2-126">Utilizzo di un file di formato XML</span><span class="sxs-lookup"><span data-stu-id="568c2-126">Using an XML Format File</span></span>  
 <span data-ttu-id="568c2-127">Nel seguente file di formato non XML di esempio è illustrato un file di formato, `myTestOrder.xml`, che esegue il mapping tra i campi in `myTestOrder-c.txt` e le colonne della tabella `myTestOrder`. Per informazioni su come creare la tabella e il file di dati, vedere "Tabella e file di dati di esempio", più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="568c2-127">The following sample non-XML format file presents a format file, `myTestOrder.xml`, that maps the fields in `myTestOrder-c.txt` to the columns of the `myTestOrder` table For information about how to create the data file and table, see "Sample Table and Data File," earlier in this topic.</span></span>  
  
 <span data-ttu-id="568c2-128">Il file di formato `myTestOrder.xml` contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="568c2-128">The `myTestOrder.xml` format file contains the following information:</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>  
  <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="3" NAME="Col1" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="1" NAME="Col3" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Col4" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
  
```  
  
> [!NOTE]  
>  <span data-ttu-id="568c2-129">Per altre informazioni sulla sintassi dell'XML Schema e ulteriori esempi di file di formato XML, vedere [File in formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="568c2-129">For information about the syntax of the XML Schema and additional samples of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="568c2-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="568c2-130">Example</span></span>  
 <span data-ttu-id="568c2-131">Nell'esempio seguente viene utilizzato il provider di set di righe con lettura bulk `OPENROWSET` per l'importazione bulk dei dati dal file di dati `myTestOrder-c.txt` alla tabella di esempio `myTestOrder`  tramite il file di formato XML `myTestOrder.xml`.</span><span class="sxs-lookup"><span data-stu-id="568c2-131">The following example uses the `OPENROWSET` bulk rowset provider to import data from the `myTestOrder-c.txt` data file into the `myTestOrder` sample table by using the `myTestOrder.xml` XML format file.</span></span> <span data-ttu-id="568c2-132">L'istruzione `INSERT... SELECT` specifica l'elenco di colonne nell'elenco di selezione.</span><span class="sxs-lookup"><span data-stu-id="568c2-132">The `INSERT... SELECT` statement specifies the column list in the select list.</span></span>  
  
 <span data-ttu-id="568c2-133">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="568c2-133">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
INSERT INTO myTestOrder   
  SELECT Col1, Col2, Col3, Col4  
      FROM  OPENROWSET(BULK  'C:\myTestOrder-c.txt',  
      FORMATFILE='C:\myTestOrder.Xml'    
       ) AS t1;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="568c2-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="568c2-134">See Also</span></span>  
 <span data-ttu-id="568c2-135">[Utilizzo di un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="568c2-135">[Use a Format File to Skip a Table Column &#40;SQL Server&#41;](use-a-format-file-to-skip-a-table-column-sql-server.md) </span></span>  
 [<span data-ttu-id="568c2-136">Utilizzo di un file di formato per escludere un campo di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="568c2-136">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
  
