---
title: Usare il formato carattere Unicode per importare o esportare dati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], Unicode character
- Unicode [SQL Server], bulk importing and exporting
ms.assetid: 74342a11-c1c0-4746-b482-7f3537744a70
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 520ce1b4eed8dc11d6d3fe038969257aea1e90fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724712"
---
# <a name="use-unicode-character-format-to-import-or-export-data-sql-server"></a><span data-ttu-id="e7544-102">Utilizzo del formato carattere Unicode per l'importazione o l'esportazione di dati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="e7544-102">Use Unicode Character Format to Import or Export Data (SQL Server)</span></span>
  <span data-ttu-id="e7544-103">È consigliabile utilizzare il formato carattere Unicode per il trasferimento bulk di dati tra più istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tramite un file di dati contenente caratteri estesi o DBCS.</span><span class="sxs-lookup"><span data-stu-id="e7544-103">Unicode character format is recommended for bulk transfer of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended/DBCS characters.</span></span> <span data-ttu-id="e7544-104">Questo formato di dati consente di trasferire i dati da un server utilizzando una tabella codici diversa da quella del client che esegue l'operazione.</span><span class="sxs-lookup"><span data-stu-id="e7544-104">The Unicode character data format allows data to be exported from a server by using a code page that differs from the code page used by the client that is performing the operation.</span></span> <span data-ttu-id="e7544-105">In questi casi, l'utilizzo del formato di dati carattere Unicode offre i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7544-105">In such cases, use of Unicode character format has the following advantages:</span></span>  
  
-   <span data-ttu-id="e7544-106">Se i dati di origine e di destinazione sono di tipo Unicode, il formato carattere Unicode consente di mantenere tutti i dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="e7544-106">If the source and destination data are Unicode data types, use of Unicode character format preserves all of the character data.</span></span>  
  
-   <span data-ttu-id="e7544-107">Se i dati di origine e di destinazione non sono di tipo Unicode, il formato carattere Unicode consente di ridurre al minimo la perdita dei caratteri estesi nei dati di origine che non possono essere rappresentati nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="e7544-107">if the source and destination data are not Unicode data types, use of Unicode character format minimizes the loss of extended characters in the source data that cannot be represented at the destination.</span></span>  
  
 <span data-ttu-id="e7544-108">Per i file in formato carattere Unicode vengono rispettate le convenzioni dei file Unicode.</span><span class="sxs-lookup"><span data-stu-id="e7544-108">Unicode character format data files follow the conventions for Unicode files.</span></span> <span data-ttu-id="e7544-109">I primi due byte del file sono rappresentati da numeri esadecimali, 0xFFFE.</span><span class="sxs-lookup"><span data-stu-id="e7544-109">The first two bytes of the file are hexadecimal numbers, 0xFFFE.</span></span> <span data-ttu-id="e7544-110">Tali byte hanno la funzione di indicatori per l'ordine dei byte e specificano se archiviare il byte più significativo come primo o ultimo byte del file.</span><span class="sxs-lookup"><span data-stu-id="e7544-110">These bytes serve as byte-order marks, specifying whether the high-order byte is stored first or last in the file.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e7544-111">Affinché un file di formato sia funzionante con un file di dati di formato carattere Unicode, è necessario che tutti i campi di input siano stringhe di testo Unicode, ovvero stringhe Unicode di dimensioni fisse o che terminano con un carattere.</span><span class="sxs-lookup"><span data-stu-id="e7544-111">For a format file to work with a Unicode character data file, all the input fields must be Unicode text strings (that is, either fixed-size or character-terminated Unicode strings).</span></span>  
  
 <span data-ttu-id="e7544-112">I dati `sql_variant` archiviati in un file in formato carattere Unicode funzionano allo stesso modo di quelli archiviati in un file in formato carattere, con la differenza che vengono archiviati come dati `nchar` anziché `char`.</span><span class="sxs-lookup"><span data-stu-id="e7544-112">The `sql_variant` data that is stored in a Unicode character-format data file operates in the same way it operates in a character-format data file, except that the data is stored as `nchar` instead of `char` data.</span></span> <span data-ttu-id="e7544-113">Per altre informazioni sul formato carattere, vedere [Regole di confronto e supporto Unicode](../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="e7544-113">For more information about character format, see [Collation and Unicode Support](../collations/collation-and-unicode-support.md).</span></span>  
  
 <span data-ttu-id="e7544-114">Per usare un carattere di terminazione del campo o della riga diverso da quello predefinito del formato carattere Unicode, vedere [Specificare caratteri di terminazione del campo e della riga &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e7544-114">To use a field or row terminator other than the default that is provided with Unicode character format, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
## <a name="command-options-for-unicode-character-format"></a><span data-ttu-id="e7544-115">Opzioni di comando per il formato carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="e7544-115">Command Options for Unicode Character Format</span></span>  
 <span data-ttu-id="e7544-116">È possibile importare dati in formato carattere Unicode in una tabella usando **bcp**, BULK INSERT o INSERT... SELECT \* FROM OPENROWSET (bulk...). Per un comando **bcp** o un'istruzione BULK INSERT, è possibile specificare il formato dati nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e7544-116">You can import Unicode character format data into a table using **bcp**, BULK INSERT or INSERT ... SELECT \* FROM OPENROWSET(BULK...). For a **bcp** command or BULK INSERT statement, you can specify the data format on the command line.</span></span> <span data-ttu-id="e7544-117">Per un'istruzione INSERT ... SELECT \* FROM OPENROWSET(BULK...) è necessario specificare il formato dati in un file di formato.</span><span class="sxs-lookup"><span data-stu-id="e7544-117">For an INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement, you must specify the data format in a format file.</span></span>  
  
 <span data-ttu-id="e7544-118">Il formato carattere Unicode è supportato dalle opzioni della riga di comando riportate di seguito:</span><span class="sxs-lookup"><span data-stu-id="e7544-118">Unicode character format is supported by the following command line options:</span></span>  
  
|<span data-ttu-id="e7544-119">Comando</span><span class="sxs-lookup"><span data-stu-id="e7544-119">Command</span></span>|<span data-ttu-id="e7544-120">Opzione</span><span class="sxs-lookup"><span data-stu-id="e7544-120">Option</span></span>|<span data-ttu-id="e7544-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7544-121">Description</span></span>|  
|-------------|------------|-----------------|  
|<span data-ttu-id="e7544-122">**bcp**</span><span class="sxs-lookup"><span data-stu-id="e7544-122">**bcp**</span></span>|<span data-ttu-id="e7544-123">**-w**</span><span class="sxs-lookup"><span data-stu-id="e7544-123">**-w**</span></span>|<span data-ttu-id="e7544-124">Utilizza il formato carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="e7544-124">Uses the Unicode character format.</span></span>|  
|<span data-ttu-id="e7544-125">BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="e7544-125">BULK INSERT</span></span>|<span data-ttu-id="e7544-126">FileType **='** widechar **'**</span><span class="sxs-lookup"><span data-stu-id="e7544-126">DATAFILETYPE **='** widechar **'**</span></span>|<span data-ttu-id="e7544-127">Utilizza il formato carattere Unicode durante l'importazione bulk di dati.</span><span class="sxs-lookup"><span data-stu-id="e7544-127">Uses Unicode character format when bulk importing data.</span></span>|  
  
 <span data-ttu-id="e7544-128">Per altre informazioni, vedere [Utilità bcp](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) o [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e7544-128">For more information, see [bcp Utility](../../tools/bcp-utility.md), [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql), or [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7544-129">In alternativa, è possibile definire la formattazione di ogni singolo campo in un file di formato.</span><span class="sxs-lookup"><span data-stu-id="e7544-129">Alternatively, you can specify formatting on a per-field basis in a format file.</span></span> <span data-ttu-id="e7544-130">Per altre informazioni, vedere [File di formato per l'importazione o l'esportazione di dati &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e7544-130">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e7544-131">Esempi</span><span class="sxs-lookup"><span data-stu-id="e7544-131">Examples</span></span>  
 <span data-ttu-id="e7544-132">Gli esempi seguenti illustrano come eseguire l'esportazione in blocco di dati di tipo carattere Unicode con **bcp** e l'importazione in blocco degli stessi dati con BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="e7544-132">The following examples demonstrate how to bulk export Unicode character data using **bcp** and to bulk import the same data using BULK INSERT.</span></span>  
  
### <a name="sample-table"></a><span data-ttu-id="e7544-133">Tabella di esempio</span><span class="sxs-lookup"><span data-stu-id="e7544-133">Sample Table</span></span>  
 <span data-ttu-id="e7544-134">Gli esempi richiedono che nel database di esempio [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] venga creata una tabella denominata `myTestUniCharData` in base allo schema `dbo`.</span><span class="sxs-lookup"><span data-stu-id="e7544-134">The examples require that a table named `myTestUniCharData` table be created in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the `dbo` schema.</span></span> <span data-ttu-id="e7544-135">Prima di eseguire le procedure illustrate negli esempi, è necessario creare la tabella.</span><span class="sxs-lookup"><span data-stu-id="e7544-135">Before you can run the examples, you must create this table.</span></span> <span data-ttu-id="e7544-136">Per creare la tabella, nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="e7544-136">To create this table, in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE myTestUniCharData (  
   Col1 smallint,  
   Col2 nvarchar(50),  
   Col3 nvarchar(50)  
   );   
```  
  
 <span data-ttu-id="e7544-137">Per popolare la tabella e visualizzare il contenuto risultante, eseguire le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7544-137">To populate this table and view the resulting contents execute the following statements:</span></span>  
  
```  
INSERT INTO myTestUniCharData(Col1,Col2,Col3)  
   VALUES(1,'DataField2','DataField3')   
        ,(2,'DataField2','DataField3');  
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
  
```  
  
### <a name="using-bcp-to-bulk-export-unicode-character-data"></a><span data-ttu-id="e7544-138">Utilizzo di bcp per l'esportazione bulk di dati in formato carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="e7544-138">Using bcp to Bulk Export Unicode Character Data</span></span>  
 <span data-ttu-id="e7544-139">Per esportare i dati dalla tabella al file di dati, usare **bcp** con l'opzione **out** e i qualificatori seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7544-139">To export data from the table to the data file, use **bcp** with the **out** option and the following qualifiers:</span></span>  
  
|<span data-ttu-id="e7544-140">Qualificatori</span><span class="sxs-lookup"><span data-stu-id="e7544-140">Qualifiers</span></span>|<span data-ttu-id="e7544-141">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e7544-141">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="e7544-142">**-w**</span><span class="sxs-lookup"><span data-stu-id="e7544-142">**-w**</span></span>|<span data-ttu-id="e7544-143">Specifica il formato carattere Unicode.</span><span class="sxs-lookup"><span data-stu-id="e7544-143">Specifies Unicode character format.</span></span>|  
|<span data-ttu-id="e7544-144">**-t** `,`</span><span class="sxs-lookup"><span data-stu-id="e7544-144">**-t** `,`</span></span>|<span data-ttu-id="e7544-145">Specifica la virgola (`,`) come carattere di terminazione del campo.</span><span class="sxs-lookup"><span data-stu-id="e7544-145">Specifies a comma (`,`) as the field terminator.</span></span><br /><br /> <span data-ttu-id="e7544-146">Nota: il carattere di terminazione del campo predefinito è il carattere di tabulazione Unicode (\t).</span><span class="sxs-lookup"><span data-stu-id="e7544-146">Note: The default field terminator is the tab Unicode character (\t).</span></span> <span data-ttu-id="e7544-147">Per altre informazioni, vedere [Impostazione dei caratteri di terminazione del campo e della riga &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="e7544-147">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>|  
|<span data-ttu-id="e7544-148">**-T**</span><span class="sxs-lookup"><span data-stu-id="e7544-148">**-T**</span></span>|<span data-ttu-id="e7544-149">Specifica che l'utilità **bcp** si connette a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con una connessione trusted che usa la sicurezza integrata.</span><span class="sxs-lookup"><span data-stu-id="e7544-149">Specifies that the **bcp** utility connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with a trusted connection using integrated security.</span></span> <span data-ttu-id="e7544-150">Se non si specifica **-T** , è necessario specificare **-U** e **-P** per eseguire correttamente l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e7544-150">If **-T** is not specified, you need to specify **-U** and **-P** to successfully log in.</span></span>|  
  
 <span data-ttu-id="e7544-151">Nell'esempio seguente viene eseguita l'esportazione bulk di dati in formato carattere Unicode dalla tabella `myTestUniCharData` in un nuovo file di dati denominato `myTestUniCharData-w.Dat` che utilizza la virgola (`,`) come carattere di terminazione del campo.</span><span class="sxs-lookup"><span data-stu-id="e7544-151">The following example bulk exports data in Unicode character format from the `myTestUniCharData` table into a new data file named `myTestUniCharData-w.Dat` data file that uses the comma (`,`) as the field terminator.</span></span> <span data-ttu-id="e7544-152">Al prompt dei comandi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="e7544-152">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks2012..myTestUniCharData out C:\myTestUniCharData-w.Dat -w -t, -T  
  
```  
  
### <a name="using-bulk-insert-to-bulk-import-unicode-character-data"></a><span data-ttu-id="e7544-153">Utilizzo di BULK INSERT per l'importazione bulk di dati in formato carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="e7544-153">Using BULK INSERT to Bulk Import Unicode Character Data</span></span>  
 <span data-ttu-id="e7544-154">Nell'esempio seguente viene utilizzata l'istruzione `BULK INSERT` per importare i dati del file di dati `myTestUniCharData-w.Dat` nella tabella `myTestUniCharData`.</span><span class="sxs-lookup"><span data-stu-id="e7544-154">The following example uses `BULK INSERT` to import the data in the `myTestUniCharData-w.Dat` data file into the `myTestUniCharData` table.</span></span> <span data-ttu-id="e7544-155">Nell'istruzione è necessario dichiarare il carattere di terminazione del campo non predefinito (`,`).</span><span class="sxs-lookup"><span data-stu-id="e7544-155">The nondefault field terminator (`,`) must be declared in the statement.</span></span> <span data-ttu-id="e7544-156">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire:</span><span class="sxs-lookup"><span data-stu-id="e7544-156">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
BULK INSERT myTestUniCharData   
   FROM 'C:\myTestUniCharData-w.Dat'   
   WITH (  
      DATAFILETYPE='widechar',  
      FIELDTERMINATOR=','  
   );   
GO  
SELECT Col1,Col2,Col3 FROM myTestUniCharData;  
GO  
  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="e7544-157">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="e7544-157">Related Tasks</span></span>  
 <span data-ttu-id="e7544-158">**Per utilizzare formati di dati per l'importazione o l'esportazione bulk**</span><span class="sxs-lookup"><span data-stu-id="e7544-158">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="e7544-159">Importare dati in formato nativo e carattere da versioni precedenti di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7544-159">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
-   [<span data-ttu-id="e7544-160">Utilizzo del formato carattere per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e7544-160">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e7544-161">Usare il formato nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e7544-161">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="e7544-162">Usare il formato Unicode nativo per importare o esportare dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e7544-162">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7544-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7544-163">See Also</span></span>  
 <span data-ttu-id="e7544-164">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="e7544-164">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="e7544-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7544-165">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="e7544-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7544-166">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="e7544-167">[Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="e7544-167">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="e7544-168">Regole di confronto e supporto Unicode</span><span class="sxs-lookup"><span data-stu-id="e7544-168">Collation and Unicode Support</span></span>](../collations/collation-and-unicode-support.md)  
  
  
