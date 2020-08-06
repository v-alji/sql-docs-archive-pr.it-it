---
title: Esempi di importazione ed esportazione bulk di documenti XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- field terminators [SQL Server]
- bulk importing [SQL Server], data formats
- row terminators [SQL Server]
- OPENROWSET function, XML bulk load
- terminators [SQL Server]
- bulk exporting [SQL Server], data formats
- XML bulk load [SQL Server]
ms.assetid: dff99404-a002-48ee-910e-f37f013d946d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d72c84a7ed84503e0c88d2a46c808196903900b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635601"
---
# <a name="examples-of-bulk-import-and-export-of-xml-documents-sql-server"></a><span data-ttu-id="953fb-102">Esempi di importazione ed esportazione bulk di documenti XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="953fb-102">Examples of Bulk Import and Export of XML Documents (SQL Server)</span></span>
    
##  <a name="you-can-bulk-import-xml-documents-into-a-ssnoversion-database-or-bulk-export-them-from-a-ssnoversion-database-this-topic-provides-examples-of-both"></a><a name="top"></a><span data-ttu-id="953fb-103">È possibile eseguire l'importazione bulk di documenti XML in un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database di o esportarli in blocco da un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database di.</span><span class="sxs-lookup"><span data-stu-id="953fb-103">You can bulk import XML documents into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database or bulk export them from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="953fb-104">In questo argomento vengono forniti esempi di entrambe le situazioni.</span><span class="sxs-lookup"><span data-stu-id="953fb-104">This topic provides examples of both.</span></span>  
  
 <span data-ttu-id="953fb-105">Per l'importazione bulk di dati da un file di dati a una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o a una vista non partizionata, è possibile utilizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="953fb-105">To bulk import data from a data file into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or non-partitioned view, you can use the following:</span></span>  
  
-   <span data-ttu-id="953fb-106">utilità**bcp**</span><span class="sxs-lookup"><span data-stu-id="953fb-106">**bcp** utility</span></span>  
  
     <span data-ttu-id="953fb-107">È possibile usare l'utilità **bcp** anche per esportare dati da qualunque posizione in un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] su cui sia possibile usare l'istruzione SELECT, incluse le viste partizionate.</span><span class="sxs-lookup"><span data-stu-id="953fb-107">You can also use the **bcp** utility to export data from anywhere in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database that a SELECT statement works, including partitioned views.</span></span>  
  
-   <span data-ttu-id="953fb-108">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="953fb-108">BULK INSERT</span></span>  
  
-   <span data-ttu-id="953fb-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="953fb-109">INSERT ... SELECT \* FROM OPENROWSET(BULK...)</span></span>  
  
 <span data-ttu-id="953fb-110">Per ulteriori informazioni, vedere [importare ed esportare dati per operazioni bulk tramite l'utilità bcp &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) e [importare dati in blocco utilizzando BULK INSERT o OPENROWSET&#40;bulk... &#41; &#40;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md)SQL Server&#41;.</span><span class="sxs-lookup"><span data-stu-id="953fb-110">For more information, see [Import and Export Bulk Data by Using the bcp Utility &#40;SQL Server&#41;](import-and-export-bulk-data-by-using-the-bcp-utility-sql-server.md) and [Import Bulk Data by Using BULK INSERT or OPENROWSET&#40;BULK...&#41; &#40;SQL Server&#41;](import-bulk-data-by-using-bulk-insert-or-openrowset-bulk-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="953fb-111">Esempi</span><span class="sxs-lookup"><span data-stu-id="953fb-111">Examples</span></span>  
 <span data-ttu-id="953fb-112">Gli esempi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="953fb-112">The examples are the following:</span></span>  
  
-   <span data-ttu-id="953fb-113">R.</span><span class="sxs-lookup"><span data-stu-id="953fb-113">A.</span></span> [<span data-ttu-id="953fb-114">Importazione BULK di dati XML come flusso di byte binario</span><span class="sxs-lookup"><span data-stu-id="953fb-114">BULK importing XML data as a binary byte stream</span></span>](#binary_byte_stream)  
  
-   <span data-ttu-id="953fb-115">B.</span><span class="sxs-lookup"><span data-stu-id="953fb-115">B.</span></span> [<span data-ttu-id="953fb-116">Importazione bulk di dati XML in una riga esistente</span><span class="sxs-lookup"><span data-stu-id="953fb-116">Bulk importing XML data in an existing row</span></span>](#existing_row)  
  
-   <span data-ttu-id="953fb-117">C.</span><span class="sxs-lookup"><span data-stu-id="953fb-117">C.</span></span> [<span data-ttu-id="953fb-118">Importazione bulk di dati XML da un file che contiene una DTD</span><span class="sxs-lookup"><span data-stu-id="953fb-118">Bulk importing XML data from a file that contains a DTD</span></span>](#file_contains_dtd)  
  
-   <span data-ttu-id="953fb-119">D.</span><span class="sxs-lookup"><span data-stu-id="953fb-119">D.</span></span> [<span data-ttu-id="953fb-120">Impostazione esplicita del carattere di terminazione del campo tramite un file di formato</span><span class="sxs-lookup"><span data-stu-id="953fb-120">Specifying the field terminator explicitly using a format file</span></span>](#field_terminator_in_format_file)  
  
-   <span data-ttu-id="953fb-121">E.</span><span class="sxs-lookup"><span data-stu-id="953fb-121">E.</span></span> [<span data-ttu-id="953fb-122">Esportazione bulk di dati XML</span><span class="sxs-lookup"><span data-stu-id="953fb-122">Bulk exporting XML data</span></span>](#bulk_export_xml_data)  
  
###  <a name="a-bulk-importing-xml-data-as-a-binary-byte-stream"></a><a name="binary_byte_stream"></a> <span data-ttu-id="953fb-123">A.</span><span class="sxs-lookup"><span data-stu-id="953fb-123">A.</span></span> <span data-ttu-id="953fb-124">Importazione bulk di dati XML come flusso di byte binario</span><span class="sxs-lookup"><span data-stu-id="953fb-124">Bulk importing XML data as a binary byte stream</span></span>  
 <span data-ttu-id="953fb-125">Quando si esegue un'importazione bulk di dati XML da un file contenente una dichiarazione di codifica che si desidera applicare, specificare l'opzione SINGLE_BLOB nella clausola OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="953fb-125">When you bulk import XML data from a file that contains an encoding declaration that you want to apply, specify the SINGLE_BLOB option in the OPENROWSET(BULK...) clause.</span></span> <span data-ttu-id="953fb-126">L'opzione SINGLE_BLOB garantisce che il parser XML di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importi i dati in base allo schema di codifica specificato nella dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="953fb-126">The SINGLE_BLOB option makes sure that the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] imports the data according to the encoding scheme specified in the XML declaration.</span></span>  
  
#### <a name="sample-table"></a><span data-ttu-id="953fb-127">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="953fb-127">Sample Table</span></span>  
 <span data-ttu-id="953fb-128">Per testare l'esempio A, è necessario creare la tabella di esempio `T`.</span><span class="sxs-lookup"><span data-stu-id="953fb-128">To test example A, you must create sample table `T`.</span></span>  
  
```  
USE tempdb  
CREATE TABLE T (IntCol int, XmlCol xml);  
GO  
```  
  
#### <a name="sample-data-file"></a><span data-ttu-id="953fb-129">File di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="953fb-129">Sample Data File</span></span>  
 <span data-ttu-id="953fb-130">Prima di eseguire l'esempio A, è necessario creare un file con codifica UTF-8 (`C:\SampleFolder\SampleData3.txt`) contenente l'istanza di esempio seguente che specifica lo schema di codifica `UTF-8` .</span><span class="sxs-lookup"><span data-stu-id="953fb-130">Before you can run example A, you must create a UTF-8 encoded file (`C:\SampleFolder\SampleData3.txt`) that contains the following sample instance that specifies the `UTF-8` encoding scheme.</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
<Root>  
          <ProductDescription ProductModelID="5">  
             <Summary>Some Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-a"></a><span data-ttu-id="953fb-131">Esempio A</span><span class="sxs-lookup"><span data-stu-id="953fb-131">Example A</span></span>  
 <span data-ttu-id="953fb-132">In questo esempio viene utilizzata l'opzione `SINGLE_BLOB` in un'istruzione `INSERT ... SELECT * FROM OPENROWSET(BULK...)` per importare dati da un file denominato `SampleData3.txt` e inserire un'istanza XML in una tabella a colonna singola, ovvero la tabella di esempio `T`.</span><span class="sxs-lookup"><span data-stu-id="953fb-132">This example uses the `SINGLE_BLOB` option in an `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement to import data from a file named `SampleData3.txt` and insert an XML instance in the single-column table, sample table `T`.</span></span>  
  
```  
INSERT INTO T(XmlCol)  
SELECT * FROM OPENROWSET(  
   BULK 'c:\SampleFolder\SampleData3.txt',  
   SINGLE_BLOB) AS x;  
```  
  
#### <a name="remarks"></a><span data-ttu-id="953fb-133">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="953fb-133">Remarks</span></span>  
 <span data-ttu-id="953fb-134">L'utilizzo di SINGLE_BLOB in questo caso consente di evitare una mancata corrispondenza tra la codifica del documento XML (come specificata dalla dichiarazione di codifica XML) e la tabella codici della stringa implicita del server.</span><span class="sxs-lookup"><span data-stu-id="953fb-134">By using SINGLE_BLOB in this case, you can avoid a mismatch between the encoding of the XML document (as specified by the XML encoding declaration) and the string codepage implied by the server.</span></span>  
  
 <span data-ttu-id="953fb-135">Se si utilizzano tipi di dati NCLOB o CLOB e si verifica un conflitto di tabella codici o di codifica, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="953fb-135">If you use NCLOB or CLOB data types and run into a codepage or encoding conflict, you must do one of the following:</span></span>  
  
-   <span data-ttu-id="953fb-136">Rimuovere la dichiarazione XML per importare correttamente il contenuto del file di dati XML.</span><span class="sxs-lookup"><span data-stu-id="953fb-136">Remove the XML declaration to successfully import the contents of the XML data file.</span></span>  
  
-   <span data-ttu-id="953fb-137">Specificare una tabella codici nell'opzione CODEPAGE della query corrispondente allo schema di codifica utilizzato nella dichiarazione XML.</span><span class="sxs-lookup"><span data-stu-id="953fb-137">Specify a code page in the CODEPAGE option of the query that matches the encoding scheme that is used in the XML declaration.</span></span>  
  
-   <span data-ttu-id="953fb-138">Verificare la corrispondenza o risolvere le impostazioni delle regole di confronto del database con uno schema di codifica XML non Unicode.</span><span class="sxs-lookup"><span data-stu-id="953fb-138">Match, or resolve, the database collation settings with a non-Unicode XML encoding scheme.</span></span>  
  
 [<span data-ttu-id="953fb-139">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="953fb-139">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="b-bulk-importing-xml-data-in-an-existing-row"></a><a name="existing_row"></a> <span data-ttu-id="953fb-140">B.</span><span class="sxs-lookup"><span data-stu-id="953fb-140">B.</span></span> <span data-ttu-id="953fb-141">Importazione bulk di dati XML in una riga esistente</span><span class="sxs-lookup"><span data-stu-id="953fb-141">Bulk importing XML data in an existing row</span></span>  
 <span data-ttu-id="953fb-142">In questo esempio viene utilizzato il provider di set di righe con lettura bulk `OPENROWSET` per aggiungere un'istanza XML a una o più righe esistenti nella tabella di esempio `T`.</span><span class="sxs-lookup"><span data-stu-id="953fb-142">This example uses the `OPENROWSET` bulk rowset provider to add an XML instance to an existing row or rows in sample table `T`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="953fb-143">Per eseguire questo esempio è necessario innanzitutto completare lo script di prova fornito nell'esempio A, nel quale viene creata la tabella `tempdb.dbo.T` e viene eseguita l'importazione bulk di dati da `SampleData3.txt`.</span><span class="sxs-lookup"><span data-stu-id="953fb-143">To run this example, you must first complete the test script provided in example A. That example creates the `tempdb.dbo.T` table and bulk imports data from `SampleData3.txt`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="953fb-144">File di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="953fb-144">Sample Data File</span></span>  
 <span data-ttu-id="953fb-145">Nell'esempio B viene utilizzata una versione modificata del file di dati di esempio `SampleData3.txt` dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="953fb-145">Example B uses a modified version of the `SampleData3.txt` sample data file from the preceding example.</span></span> <span data-ttu-id="953fb-146">Per eseguire questo esempio, modificare il contenuto del file nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="953fb-146">To run this example, modify the content of this file as follows:</span></span>  
  
```  
<Root>  
          <ProductDescription ProductModelID="10">  
             <Summary>Some New Text</Summary>  
          </ProductDescription>  
</Root>  
```  
  
#### <a name="example-b"></a><span data-ttu-id="953fb-147">Esempio B</span><span class="sxs-lookup"><span data-stu-id="953fb-147">Example B</span></span>  
  
```  
-- Query before update shows initial state of XmlCol values.  
SELECT * FROM T  
UPDATE T  
SET XmlCol =(  
SELECT * FROM OPENROWSET(  
   BULK 'C:\SampleFolder\SampleData3.txt',  
           SINGLE_BLOB  
) AS x  
)  
WHERE IntCol = 1;  
GO  
```  
  
 [<span data-ttu-id="953fb-148">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="953fb-148">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="c-bulk-importing-xml-data-from-a-file-that-contains-a-dtd"></a><a name="file_contains_dtd"></a> <span data-ttu-id="953fb-149">C.</span><span class="sxs-lookup"><span data-stu-id="953fb-149">C.</span></span> <span data-ttu-id="953fb-150">Importazione bulk di dati XML da un file contenente una definizione DTD</span><span class="sxs-lookup"><span data-stu-id="953fb-150">Bulk importing XML data from a file that contains a DTD</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="953fb-151">È consigliabile non abilitare il supporto per le definizioni DTD (Document Type Definition) se non è necessario nell'ambiente XML utilizzato.</span><span class="sxs-lookup"><span data-stu-id="953fb-151">We recommended that you not enable support for Document Type Definitions (DTDs) if it is not required in your XML environment.</span></span> <span data-ttu-id="953fb-152">L'attivazione del supporto DTD aumenta la superficie di attacco del server esposta a rischi e può esporre quest'ultimo a un attacco Denial-of-Service.</span><span class="sxs-lookup"><span data-stu-id="953fb-152">Turning on DTD support increases the attackable surface area of your server, and may expose it to a denial-of-service attack.</span></span> <span data-ttu-id="953fb-153">Se è necessario abilitare il supporto DTD, è possibile ridurre questo rischio per la sicurezza limitando l'elaborazione a documenti XML attendibili.</span><span class="sxs-lookup"><span data-stu-id="953fb-153">If you must enable DTD support, you can reduce this security risk by processing only trusted XML documents.</span></span>  
  
 <span data-ttu-id="953fb-154">Quando si tenta di usare un comando [bcp](../../tools/bcp-utility.md) per importare dati XML da un file contenente una definizione DTD, è possibile che venga visualizzato un errore analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="953fb-154">During an attempt to use a [bcp](../../tools/bcp-utility.md) command to import XML data from a file that contains a DTD, an error similar to the following can occur:</span></span>  
  
 <span data-ttu-id="953fb-155">"SQLState = 42000, NativeError = 6359"</span><span class="sxs-lookup"><span data-stu-id="953fb-155">"SQLState = 42000, NativeError = 6359"</span></span>  
  
 <span data-ttu-id="953fb-156">"Error = [Microsoft][SQL Server Native Client][SQL Server]L'analisi di codice XML con DTD di subset interni non è consentita.</span><span class="sxs-lookup"><span data-stu-id="953fb-156">"Error = [Microsoft][SQL Server Native Client][ SQL Server]Parsing XML with internal subset DTDs not allowed.</span></span> <span data-ttu-id="953fb-157">Utilizzare l'istruzione CONVERT con l'opzione di stile 2 per abilitare il supporto limitato per i DTD di subset interni."</span><span class="sxs-lookup"><span data-stu-id="953fb-157">Use CONVERT with style option 2 to enable limited internal subset DTD support."</span></span>  
  
 <span data-ttu-id="953fb-158">"Copia BCP %s non riuscita"</span><span class="sxs-lookup"><span data-stu-id="953fb-158">"BCP copy %s failed"</span></span>  
  
 <span data-ttu-id="953fb-159">Per risolvere il problema, è possibile importare dati XML da un file di dati contenente una definizione DTD utilizzando la funzione `OPENROWSET(BULK...)` e specificando quindi l'opzione `CONVERT` nella clausola `SELECT` del comando.</span><span class="sxs-lookup"><span data-stu-id="953fb-159">To work around this problem, you can import XML data from a data file that contains a DTD by using the `OPENROWSET(BULK...)` function and then specifying the `CONVERT` option in the `SELECT` clause of the command.</span></span> <span data-ttu-id="953fb-160">La sintassi di base per il comando è la seguente:</span><span class="sxs-lookup"><span data-stu-id="953fb-160">The basic syntax for the command is:</span></span>  
  
 `INSERT ... SELECT CONVERT(...) FROM OPENROWSET(BULK...)`  
  
#### <a name="sample-data-file"></a><span data-ttu-id="953fb-161">File di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="953fb-161">Sample Data File</span></span>  
 <span data-ttu-id="953fb-162">Prima di testare questo esempio di importazione bulk, creare un file (`C:\temp\Dtdfile.xml`) contenente l'istanza di esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="953fb-162">Before you can test this bulk import example, create a file (`C:\temp\Dtdfile.xml`) that contains the following sample instance:</span></span>  
  
```  
<!DOCTYPE DOC [<!ATTLIST elem1 attr1 CDATA "defVal1">]><elem1>January</elem1>  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="953fb-163">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="953fb-163">Sample Table</span></span>  
 <span data-ttu-id="953fb-164">Nell'esempio C viene utilizzata la tabella di esempio `T1` creata mediante l'istruzione `CREATE TABLE` seguente:</span><span class="sxs-lookup"><span data-stu-id="953fb-164">Example C uses the `T1` sample table that is created by the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE T1(XmlCol xml);  
GO  
```  
  
#### <a name="example-c"></a><span data-ttu-id="953fb-165">Esempio C</span><span class="sxs-lookup"><span data-stu-id="953fb-165">Example C</span></span>  
 <span data-ttu-id="953fb-166">In questo esempio viene utilizzata la funzione `OPENROWSET(BULK...)` e viene specificata l'opzione `CONVERT` nella clausola `SELECT` per importare i dati XML da `Dtdfile.xml` nella tabella di esempio `T1`.</span><span class="sxs-lookup"><span data-stu-id="953fb-166">This example uses `OPENROWSET(BULK...)` and specifies the `CONVERT` option in the `SELECT` clause to import the XML data from `Dtdfile.xml` into sample table `T1`.</span></span>  
  
```  
INSERT T1  
  SELECT CONVERT(xml, BulkColumn, 2) FROM   
    OPENROWSET(Bulk 'c:\temp\Dtdfile.xml', SINGLE_BLOB) [rowsetresults];  
```  
  
 <span data-ttu-id="953fb-167">Dopo l'esecuzione dell'istruzione `INSERT` , la definizione DTD viene rimossa dai dati XML e archiviata nella tabella `T1` .</span><span class="sxs-lookup"><span data-stu-id="953fb-167">After the `INSERT` statement executes, the DTD is stripped from the XML and stored in the `T1` table.</span></span>  
  
 [<span data-ttu-id="953fb-168">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="953fb-168">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="d-specifying-the-field-terminator-explicitly-using-a-format-file"></a><a name="field_terminator_in_format_file"></a> <span data-ttu-id="953fb-169">D.</span><span class="sxs-lookup"><span data-stu-id="953fb-169">D.</span></span> <span data-ttu-id="953fb-170">Definizione esplicita del carattere di terminazione del campo tramite un file di formato</span><span class="sxs-lookup"><span data-stu-id="953fb-170">Specifying the field terminator explicitly using a format file</span></span>  
 <span data-ttu-id="953fb-171">Nell'esempio seguente viene descritta la procedura per l'importazione bulk del documento XML `Xmltable.dat`.</span><span class="sxs-lookup"><span data-stu-id="953fb-171">The following example shows how to bulk import the following XML document, `Xmltable.dat`.</span></span>  
  
#### <a name="sample-data-file"></a><span data-ttu-id="953fb-172">File di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="953fb-172">Sample Data File</span></span>  
 <span data-ttu-id="953fb-173">Il documento in `Xmltable.dat` contiene due valori XML, uno per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="953fb-173">The document in `Xmltable.dat` contains two XML values, one for each row.</span></span> <span data-ttu-id="953fb-174">Per il primo valore XML è stata utilizzata la codifica UTF-16, mentre per il secondo valore è stata utilizzata la codifica UTF-8.</span><span class="sxs-lookup"><span data-stu-id="953fb-174">The first XML value is encoded with UTF-16, and the second value is encoded with UTF-8.</span></span>  
  
 <span data-ttu-id="953fb-175">Il contenuto di questo file di dati è illustrato nel dump Hex seguente:</span><span class="sxs-lookup"><span data-stu-id="953fb-175">The contents of this data file are shown in the following Hex dump:</span></span>  
  
```  
FF FE 3C 00 3F 00 78 00-6D 00 6C 00 20 00 76 00  *..<.?.x.m.l. .v.*  
65 00 72 00 73 00 69 00-6F 00 6E 00 3D 00 22 00  *e.r.s.i.o.n.=.".*  
31 00 2E 00 30 00 22 00-20 00 65 00 6E 00 63 00  *1...0.". .e.n.c.*  
6F 00 64 00 69 00 6E 00-67 00 3D 00 22 00 75 00  *o.d.i.n.g.=.".u.*  
74 00 66 00 2D 00 31 00-36 00 22 00 3F 00 3E 00  *t.f.-.1.6.".?.>.*  
3C 00 72 00 6F 00 6F 00-74 00 3E 00 A2 4F 9C 76  *<.r.o.o.t.>..O.v*  
0C FA 77 E4 80 00 89 00-00 06 90 06 91 2E 9B 2E  *..w.............*  
99 34 A2 34 86 00 83 02-92 20 7F 02 4E C5 E4 A3  *.4.4..... ..N...*  
34 B2 B7 B3 B7 FE F8 FF-F8 00 3C 00 2F 00 72 00  *4.........<./.r.*  
6F 00 6F 00 74 00 3E 00-00 00 00 00 7A EF BB BF  *o.o.t.>.....z...*  
3C 3F 78 6D 6C 20 76 65-72 73 69 6F 6E 3D 22 31  *<?xml version="1*  
2E 30 22 20 65 6E 63 6F-64 69 6E 67 3D 22 75 74  *.0" encoding="ut*  
66 2D 38 22 3F 3E 3C 72-6F 6F 74 3E E4 BE A2 E7  *f-8"?><root>....*  
9A 9C EF A8 8C EE 91 B7-C2 80 C2 89 D8 80 DA 90  *................*  
E2 BA 91 E2 BA 9B E3 92-99 E3 92 A2 C2 86 CA 83  *................*  
E2 82 92 C9 BF EC 95 8E-EA 8F A4 EB 88 B4 EB 8E  *................*  
B7 EF BA B7 EF BF B8 C3-B8 3C 2F 72 6F 6F 74 3E  *.........</root>*  
00 00 00 00 7A                                   *....z*  
```  
  
#### <a name="sample-table"></a><span data-ttu-id="953fb-176">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="953fb-176">Sample Table</span></span>  
 <span data-ttu-id="953fb-177">Per l'importazione o l'esportazione bulk di un documento XML, è consigliabile usare un [carattere di terminazione del campo](specify-field-and-row-terminators-sql-server.md) che non sia contenuto in alcun documento, ad esempio una serie di quattro valori Null (`\0`) seguita dalla lettera `z`: `\0\0\0\0z`.</span><span class="sxs-lookup"><span data-stu-id="953fb-177">When you bulk import or export an XML document, you should use a [field terminator](specify-field-and-row-terminators-sql-server.md) that cannot possibly appear in any of the documents; for example, a series of four nulls (`\0`) followed by the letter `z`: `\0\0\0\0z`.</span></span>  
  
 <span data-ttu-id="953fb-178">In questo esempio viene illustrato come utilizzare questo carattere di terminazione del campo per la tabella di esempio `xTable` .</span><span class="sxs-lookup"><span data-stu-id="953fb-178">This example shows how to use this field terminator for the `xTable` sample table.</span></span> <span data-ttu-id="953fb-179">Per creare questa tabella di esempio, utilizzare l'istruzione `CREATE TABLE` seguente:</span><span class="sxs-lookup"><span data-stu-id="953fb-179">To create this sample table, use the following `CREATE TABLE` statement:</span></span>  
  
```  
USE tempdb;  
CREATE TABLE xTable (xCol xml);  
GO  
```  
  
#### <a name="sample-format-file"></a><span data-ttu-id="953fb-180">File di formato di esempio</span><span class="sxs-lookup"><span data-stu-id="953fb-180">Sample Format File</span></span>  
 <span data-ttu-id="953fb-181">È necessario specificare il carattere di terminazione del campo nel file di formato.</span><span class="sxs-lookup"><span data-stu-id="953fb-181">The field terminator must be specified in the format file.</span></span> <span data-ttu-id="953fb-182">Nell'esempio D viene utilizzato un file di formato non XML denominato `Xmltable.fmt` che contiene quanto segue:</span><span class="sxs-lookup"><span data-stu-id="953fb-182">Example D uses a non-XML format file named `Xmltable.fmt` that contains the following:</span></span>  
  
```  
9.0  
1  
1       SQLBINARY     0       0       "\0\0\0\0z"    1     xCol         ""  
```  
  
 <span data-ttu-id="953fb-183">È possibile utilizzare tale file di formato per l'importazione bulk di documenti XML nella tabella `xTable` tramite un comando `bcp` o un'istruzione `BULK INSERT` o `INSERT ... SELECT * FROM OPENROWSET(BULK...)` .</span><span class="sxs-lookup"><span data-stu-id="953fb-183">You can use this format file to bulk import XML documents into the `xTable` table by using a `bcp` command or a `BULK INSERT` or `INSERT ... SELECT * FROM OPENROWSET(BULK...)` statement.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="953fb-184">Esempio D</span><span class="sxs-lookup"><span data-stu-id="953fb-184">Example D</span></span>  
 <span data-ttu-id="953fb-185">In questo esempio viene utilizzato il file di formato `Xmltable.fmt` in un'istruzione `BULK INSERT` per importare il contenuto di un file di dati XML denominato `Xmltable.dat`.</span><span class="sxs-lookup"><span data-stu-id="953fb-185">This example uses the `Xmltable.fmt` format file in a `BULK INSERT` statement to import the contents of an XML data file named `Xmltable.dat`.</span></span>  
  
```  
BULK INSERT xTable   
FROM 'C:\Xmltable.dat'  
WITH (FORMATFILE = 'C:\Xmltable.fmt');  
GO  
```  
  
 [<span data-ttu-id="953fb-186">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="953fb-186">&#91;Top&#93;</span></span>](#top)  
  
###  <a name="e-bulk-exporting-xml-data"></a><a name="bulk_export_xml_data"></a> <span data-ttu-id="953fb-187">E.</span><span class="sxs-lookup"><span data-stu-id="953fb-187">E.</span></span> <span data-ttu-id="953fb-188">Esportazione bulk di dati XML</span><span class="sxs-lookup"><span data-stu-id="953fb-188">Bulk exporting XML data</span></span>  
 <span data-ttu-id="953fb-189">Nell'esempio seguente viene utilizzata l'utilità `bcp` per l'esportazione bulk di dati XML dalla tabella creata nell'esempio precedente tramite lo stesso file di formato XML.</span><span class="sxs-lookup"><span data-stu-id="953fb-189">The following example uses `bcp` to bulk export XML data from the table that is created in the preceding example by using the same XML format file.</span></span> <span data-ttu-id="953fb-190">Nel comando `bcp` seguente, `<server_name>` e `<instance_name>` rappresentano segnaposto da sostituire con valori appropriati:</span><span class="sxs-lookup"><span data-stu-id="953fb-190">In the following `bcp` command, `<server_name>` and `<instance_name>` represent placeholders that must be replaced with appropriate values:</span></span>  
  
```  
bcp bulktest..xTable out a-wn.out -N -T -S<server_name>\<instance_name>  
```  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="953fb-191">non salva la codifica XML in caso di persistenza di dati XML nel database.</span><span class="sxs-lookup"><span data-stu-id="953fb-191">does not save the XML encoding when XML data is persisted in the database.</span></span> <span data-ttu-id="953fb-192">La codifica originale dei campi XML, pertanto, non è disponibile quando vengono esportati i dati XML.</span><span class="sxs-lookup"><span data-stu-id="953fb-192">Therefore, the original encoding of XML fields is not available when XML data is exported.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="953fb-193">usa la codifica UTF-16 durante l'esportazione di dati XML.</span><span class="sxs-lookup"><span data-stu-id="953fb-193">uses UTF-16 encoding when exporting XML data.</span></span>  
  
 [<span data-ttu-id="953fb-194">&#91;Torna all'inizio&#93;</span><span class="sxs-lookup"><span data-stu-id="953fb-194">&#91;Top&#93;</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="953fb-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="953fb-195">See Also</span></span>  
 <span data-ttu-id="953fb-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="953fb-196">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="953fb-197">[Clausola SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="953fb-197">[SELECT Clause &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-clause-transact-sql) </span></span>  
 <span data-ttu-id="953fb-198">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="953fb-198">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="953fb-199">[Informazioni sull'importazione ed esportazione bulk di dati &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="953fb-199">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="953fb-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="953fb-200">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="953fb-201">OPENROWSET &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="953fb-201">OPENROWSET &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/openrowset-transact-sql)  
  
  
