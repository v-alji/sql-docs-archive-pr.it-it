---
title: Usare un file di formato per ignorare una colonna di una tabella (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- skipping columns when importing
- format files [SQL Server], skipping columns
ms.assetid: 30e0e7b9-d131-46c7-90a4-6ccf77e3d4f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 153ef21209ff4261020e26aca3bc52d28dc852a7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638399"
---
# <a name="use-a-format-file-to-skip-a-table-column-sql-server"></a><span data-ttu-id="ba9d0-102">Utilizzo di un file di formato per ignorare una colonna di una tabella (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="ba9d0-102">Use a Format File to Skip a Table Column (SQL Server)</span></span>
  <span data-ttu-id="ba9d0-103">In questo argomento vengono illustrati i file di formato.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-103">This topic describes format files.</span></span> <span data-ttu-id="ba9d0-104">È possibile utilizzare un file di formato per evitare di importare la colonna di una tabella quando il campo non esiste nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-104">You can use a format file to skip importing a table column when the field does not exist in the data file.</span></span> <span data-ttu-id="ba9d0-105">Un file di dati può contenere un numero di campi inferiore rispetto al numero di colonne della tabella solo se le colonne ignorate ammettono valori Null e/o hanno un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-105">A data file can contain fewer fields than the number of columns in the table only if the skipped columns are nullable and/or have default value.</span></span>

## <a name="sample-table-and-data-file"></a><span data-ttu-id="ba9d0-106">Tabella e file di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="ba9d0-106">Sample Table and Data File</span></span>
 <span data-ttu-id="ba9d0-107">Per gli esempi seguenti è necessaria una tabella denominata `myTestSkipCol` nel database di esempio [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] nello schema **dbo** .</span><span class="sxs-lookup"><span data-stu-id="ba9d0-107">The following examples require a table named `myTestSkipCol` in the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database under the **dbo** schema.</span></span> <span data-ttu-id="ba9d0-108">Per creare la tabella, utilizzare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-108">Create this table as follows:</span></span>

```
USE AdventureWorks2012;
GO
CREATE TABLE myTestSkipCol 
   (
   Col1 smallint,
   Col2 nvarchar(50) NULL,
   Col3 nvarchar(50) not NULL
   );
GO
```

 <span data-ttu-id="ba9d0-109">Negli esempi seguenti viene utilizzato un file di dati di esempio, `myTestSkipCol2.dat`, che contiene solo due campi, mentre la tabella corrispondente contiene tre colonne:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-109">The following examples use a sample data file, `myTestSkipCol2.dat`, which contains only two fields, although the corresponding table contains three columns:</span></span>

```
1,DataForColumn3
1,DataForColumn3
1,DataForColumn3

```

 <span data-ttu-id="ba9d0-110">Per eseguire l'importazione bulk dei dati da `myTestSkipCol2.dat` nella tabella `myTestSkipCol` , è necessario che il file di formato esegua il mapping tra il primo campo di dati e `Col1`e tra il secondo campo e `Col3`, ignorando `Col2`.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-110">To bulk import data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the format file must map the first data field to `Col1`, the second field to `Col3`, skipping `Col2`.</span></span>

## <a name="using-a-non-xml-format-file"></a><span data-ttu-id="ba9d0-111">Utilizzo di un file di formato non XML</span><span class="sxs-lookup"><span data-stu-id="ba9d0-111">Using a Non-XML Format File</span></span>
 <span data-ttu-id="ba9d0-112">È possibile modificare un file di formato non XML per ignorare una colonna di tabella.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-112">You can modify a non-XML format file to skip a table column.</span></span> <span data-ttu-id="ba9d0-113">In genere, questo richiede l'uso dell'utilità **bcp** per creare un file di formato non XML predefinito e per modificare il file predefinito in un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-113">Typically, this involves using the **bcp** utility to create a default non-XML format file and the modifying the default file in a text editor.</span></span> <span data-ttu-id="ba9d0-114">Il file di formato modificato deve eseguire il mapping tra ogni campo esistente e la colonna di tabella corrispondente e indicare quale colonna o quali colonne di tabella ignorare.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-114">The modified format file must map each existing fields to its corresponding table column and indicate which table column or columns to skip.</span></span> <span data-ttu-id="ba9d0-115">Esistono due alternative per la modifica di un file di dati non XML predefinito.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-115">Two alternatives exist for modifying a default non-XML data file.</span></span> <span data-ttu-id="ba9d0-116">Entrambi consentono di indicare che il campo dati non esiste nel file di dati e che nella colonna della tabella corrispondente non verrà inserito alcun dato.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-116">Either alternative indicates that the data field does not exist in the data file and that no data will be inserted into the corresponding table column.</span></span>

### <a name="creating-a-default-non-xml-format-file"></a><span data-ttu-id="ba9d0-117">Creazione di un file di formato non XML predefinito</span><span class="sxs-lookup"><span data-stu-id="ba9d0-117">Creating a Default Non-XML Format File</span></span>
 <span data-ttu-id="ba9d0-118">Questo argomento usa il file di formato non XML predefinito creato per la tabella di esempio `myTestSkipCol` usando il comando **bcp** seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-118">This topic uses the default non-XML format file that was created for the `myTestSkipCol` sample table by using the following **bcp** command:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.fmt -c -T
```

 <span data-ttu-id="ba9d0-119">Il comando precedente crea un file di formato non XML, `myTestSkipCol_Default.fmt`.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-119">The previous command creates a non-XML format file, `myTestSkipCol_Default.fmt`.</span></span> <span data-ttu-id="ba9d0-120">Questo file di formato è chiamato *file di formato predefinito* perché è generato da **bcp**.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-120">This format file is called a *default format file* because it is the form generated by **bcp**.</span></span> <span data-ttu-id="ba9d0-121">In genere, un file di formato predefinito descrive una corrispondenza uno-a-uno tra i campi del file di dati e le colonne di tabella.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-121">Typically, a default format file describes a one-to-one correspondence between data-file fields and table columns.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="ba9d0-122">Potrebbe essere necessario specificare il nome dell'istanza del server al quale ci si connette.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-122">You might have to specify the name of the server instance to which you are connecting.</span></span> <span data-ttu-id="ba9d0-123">Potrebbe inoltre essere necessario specificare il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-123">Also, you might have to specify the user name and password.</span></span> <span data-ttu-id="ba9d0-124">Per altre informazioni, vedere [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="ba9d0-124">For more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>

 <span data-ttu-id="ba9d0-125">Nella figura seguente vengono illustrati i valori nei file di formato predefinito di esempio.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-125">The following illustration shows the values in this sample default format files.</span></span> <span data-ttu-id="ba9d0-126">Nella figura viene inoltre indicato il nome di ogni campo del file di formato.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-126">The illustration also shows the name of each format-file field.</span></span>

 <span data-ttu-id="ba9d0-127">![file di formato non XML predefinito per myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "file di formato non XML predefinito per myTestSkipCol")</span><span class="sxs-lookup"><span data-stu-id="ba9d0-127">![default non-XML format file for myTestSkipCol](../../database-engine/media/mytestskipcol-f-c-default-fmt.gif "default non-XML format file for myTestSkipCol")</span></span>

> [!NOTE]
>  <span data-ttu-id="ba9d0-128">Per altre informazioni sui campi dei file di formato, vedere [File in formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba9d0-128">For more information about the format-file fields, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="methods-for-modifying-a-non-xml-format-file"></a><span data-ttu-id="ba9d0-129">Modalità di modifica di un file di formato non XML</span><span class="sxs-lookup"><span data-stu-id="ba9d0-129">Methods for Modifying a Non-XML Format File</span></span>
 <span data-ttu-id="ba9d0-130">Per ignorare una colonna di tabella, modificare il file di formato non XML predefinito, utilizzando una delle modalità alternative seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-130">To skip a table column, edit the default non-XML format file and modify the file by using one of the following alternative methods:</span></span>

-   <span data-ttu-id="ba9d0-131">La modalità preferita include tre passaggi principali.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-131">The preferred method involves three basic steps.</span></span> <span data-ttu-id="ba9d0-132">Eliminare innanzitutto eventuali righe del file di formato che specifichino un campo non presente nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-132">First, delete any format-file row that describes a field that is missing from the data file.</span></span> <span data-ttu-id="ba9d0-133">Ridurre quindi il valore "Ordine dei campi nel file host" di ogni riga del file di formato che segue una riga eliminata.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-133">Then, reduce the "Host file field order" value of each format-file row that follows a deleted row.</span></span> <span data-ttu-id="ba9d0-134">L'obiettivo sono i valori sequenziali "Ordine dei campi nel file host", da 1 a *n*, che riflettono l'effettiva posizione di ogni campo nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-134">The goal is sequential "Host file field order" values, 1 through *n*, that reflect the actual position of each data field in the data file.</span></span> <span data-ttu-id="ba9d0-135">Ridurre infine il valore nel campo "Numero di colonne" in modo da riflettere il numero effettivo di campi nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-135">Finally, reduce the value in the "Number of columns" field to reflect the actual number of fields in the data file.</span></span>

     <span data-ttu-id="ba9d0-136">L'esempio seguente si basa sul file di formato predefinito per la tabella `myTestSkipCol` , creato in "Creazione di un file di formato non XML predefinito", più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-136">The following example is based on the default format file for the `myTestSkipCol` table, which is created in "Creating a Default Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="ba9d0-137">Questo file di formato modificato esegue il mapping tra il primo campo dati e `Col1`, ignora `Col2`ed esegue il mapping tra il secondo campo dati e `Col3`.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-137">This modified format file maps the first data field to `Col1`, skips `Col2`, and maps the second data field to `Col3`.</span></span> <span data-ttu-id="ba9d0-138">La riga per `Col2` è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-138">The row for `Col2` has been deleted.</span></span> <span data-ttu-id="ba9d0-139">Le altre modifiche sono indicate in grassetto:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-139">Other modifications are indicated in bold:</span></span>

    ```
    9.0
    2
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

-   <span data-ttu-id="ba9d0-140">In alternativa, per ignorare una colonna di tabella, è possibile modificare la definizione della riga del file di formato che corrisponde alla colonna di tabella.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-140">Alternatively, to skip a table column, you can modify the definition of the format-file row that corresponds to the table column.</span></span> <span data-ttu-id="ba9d0-141">In questa riga del file di formato, i valori "lunghezza del prefisso," "lunghezza dei dati del file host" e "ordine delle colonne nel server" devono essere impostati su 0.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-141">In this format-file row, the "prefix length," "host file data length," and "server column order" values must be set to 0.</span></span> <span data-ttu-id="ba9d0-142">Inoltre, i campi "terminatore" e "regole di confronto a livello di colonna" devono essere impostati su "" (NULL).</span><span class="sxs-lookup"><span data-stu-id="ba9d0-142">Also, the "terminator" and "column collation" fields must be set to "" (NULL).</span></span>

     <span data-ttu-id="ba9d0-143">Il valore "nome della colonna del server" richiede una stringa non vuota, sebbene il nome di colonna effettivo non sia necessario.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-143">The "server column name" value requires a nonblank string, though the actual column name is not necessary.</span></span> <span data-ttu-id="ba9d0-144">Per i campi di formato restanti sono necessari i relativi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-144">The remaining format fields require their default values.</span></span>

     <span data-ttu-id="ba9d0-145">L'esempio seguente deriva inoltre dal file di formato predefinito per la tabella `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="ba9d0-145">The following example is also derived from the default format file for the `myTestSkipCol` table.</span></span> <span data-ttu-id="ba9d0-146">I valori che devono essere 0 o NULL sono indicati in grassetto.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-146">Values that must be 0 or NULL are indicated in bold.</span></span>

    ```
    9.0
    3
    1       SQLCHAR       0       7       "\t"     1     Col1         ""
    2       SQLCHAR       00""0     Col2         ""
    3       SQLCHAR       0       100     "\r\n"   3     Col3         SQL_Latin1_General_CP1_CI_AS
    ```

### <a name="examples"></a><span data-ttu-id="ba9d0-147">Esempi</span><span class="sxs-lookup"><span data-stu-id="ba9d0-147">Examples</span></span>
 <span data-ttu-id="ba9d0-148">Gli esempi seguenti sono inoltre basati sulla tabella di esempio `myTestSkipCol` e sul file di dati di esempio `myTestSkipCol2.dat` creati in "File di dati e tabella di esempio", più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-148">The following examples are also based on the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span>

#### <a name="using-bulk-insert"></a><span data-ttu-id="ba9d0-149">Utilizzo di BULK INSERT</span><span class="sxs-lookup"><span data-stu-id="ba9d0-149">Using BULK INSERT</span></span>
 <span data-ttu-id="ba9d0-150">Il funzionamento di questo esempio si basa sull'utilizzo dei file di formato non XML modificati creati in "Modalità di modifica di un file di formato non XML", più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-150">This example works by using either of the modified non-XML format files created in "Methods for Modifying a Non-XML Format File," earlier in this topic.</span></span> <span data-ttu-id="ba9d0-151">In questo esempio, il file di formato modificato è denominato `C:\myTestSkipCol2.fmt`.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-151">In this example, the modified format file is named `C:\myTestSkipCol2.fmt`.</span></span> <span data-ttu-id="ba9d0-152">Per utilizzare `BULK INSERT` per l'importazione bulk dei file di dati `myTestSkipCol2.dat` , nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-152">To use `BULK INSERT` to bulk import the `myTestSkipCol2.dat` data file, in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
BULK INSERT myTestSkipCol 
   FROM 'C:\myTestSkipCol2.dat' 
   WITH (FORMATFILE = 'C:\myTestSkipCol2.fmt');
GO
SELECT * FROM myTestSkipCol;
GO
```

## <a name="using-an-xml-format-file"></a><span data-ttu-id="ba9d0-153">Utilizzo di un file di formato XML</span><span class="sxs-lookup"><span data-stu-id="ba9d0-153">Using an XML Format File</span></span>
 <span data-ttu-id="ba9d0-154">Con un file di formato XML non è possibile ignorare una colonna quando si sta eseguendo l'importazione diretta in una tabella usando un comando **bcp** o un'istruzione BULK INSERT.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-154">With an XML format file, you cannot skip a column when you are importing directly into a table by using a **bcp** command or a BULK INSERT statement.</span></span> <span data-ttu-id="ba9d0-155">È tuttavia possibile importare un'intera tabella a eccezione dell'ultima colonna.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-155">However, you can import into all but the last column of a table.</span></span> <span data-ttu-id="ba9d0-156">Se si desidera ignorare una colonna diversa dall'ultima, è necessario creare una vista della tabella di destinazione che contiene solo le colonne contenute nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-156">If you have to skip any but the last column, you must create a view of the target table that contains only the columns contained in the data file.</span></span> <span data-ttu-id="ba9d0-157">In seguito sarà possibile eseguire un'importazione bulk dei dati da tale file nella vista.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-157">Then, you can bulk import data from that file into the view.</span></span>

 <span data-ttu-id="ba9d0-158">Per utilizzare un file di formato XML per ignorare una colonna di una tabella tramite OPENROWSET(BULK...), è necessario specificare un elenco esplicito di colonne nell'elenco selezionato e nella tabella di destinazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-158">To use an XML format file to skip a table column by using OPENROWSET(BULK...), you have to provide explicit list of columns in the select list and also in the target table, as follows:</span></span>

 <span data-ttu-id="ba9d0-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="ba9d0-159">INSERT ...<column_list> SELECT <column_list> FROM OPENROWSET(BULK...)</span></span>

### <a name="creating-a-default-xml-format-file"></a><span data-ttu-id="ba9d0-160">Creazione di un file di formato XML predefinito</span><span class="sxs-lookup"><span data-stu-id="ba9d0-160">Creating a Default XML Format File</span></span>
 <span data-ttu-id="ba9d0-161">Gli esempi dei file di formato modificati sono basati sulla tabella di esempio `myTestSkipCol` e sul file di dati di esempio creati in "File di dati e tabella di esempio", più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-161">The examples of modified format files are based on the `myTestSkipCol` sample table and data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="ba9d0-162">Il comando **bcp** seguente crea un file di formato XML predefinito per la tabella `myTestSkipCol` :</span><span class="sxs-lookup"><span data-stu-id="ba9d0-162">The following **bcp** command creates a default XML format file for the `myTestSkipCol` table:</span></span>

```
bcp AdventureWorks2012..myTestSkipCol format nul -f myTestSkipCol_Default.xml -c -x -T
```

 <span data-ttu-id="ba9d0-163">Il file di formato non XML predefinito risultante descrive una corrispondenza uno-a-uno tra i campi del file di dati e le colonne di tabella, come segue:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-163">The resulting default non-XML format file describes a one-to-one correspondence between data-file fields and table columns, as follows:</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
  <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col2" xsi:type="SQLNVARCHAR"/>
  <COLUMN SOURCE="3" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

> [!NOTE]
>  <span data-ttu-id="ba9d0-164">Per informazioni sulla struttura dei file di formato XML, vedere [File in formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="ba9d0-164">For information about the structure of XML format files, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>

### <a name="examples"></a><span data-ttu-id="ba9d0-165">Esempi</span><span class="sxs-lookup"><span data-stu-id="ba9d0-165">Examples</span></span>
 <span data-ttu-id="ba9d0-166">Gli esempi in questa sezione utilizzano la tabella di esempio `myTestSkipCol` e il file di dati di esempio `myTestSkipCol2.dat` creati in "File di dati e tabella di esempio", più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-166">The examples in this section use the `myTestSkipCol` sample table and the `myTestSkipCol2.dat` sample data file that are created in "Sample Table and Data File," earlier in this topic.</span></span> <span data-ttu-id="ba9d0-167">Per importare i dati da `myTestSkipCol2.dat` nella tabella `myTestSkipCol` , gli esempi utilizzano il file di formato XML modificato seguente, `myTestSkipCol2-x.xml`,</span><span class="sxs-lookup"><span data-stu-id="ba9d0-167">To import the data from `myTestSkipCol2.dat` into the `myTestSkipCol` table, the examples use the following modified XML format file, `myTestSkipCol2-x.xml`.</span></span> <span data-ttu-id="ba9d0-168">basato sul file di formato creato in "Creazione di un file di formato XML predefinito" più indietro in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-168">This is based on the format file that is created in "Creating a Default XML Format File," earlier in this topic.</span></span>

```
<?xml version="1.0"?>
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
 <RECORD>
  <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="," MAX_LENGTH="7"/>
  <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\r\n" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>
 </RECORD>
 <ROW>
  <COLUMN SOURCE="1" NAME="Col1" xsi:type="SQLSMALLINT"/>
  <COLUMN SOURCE="2" NAME="Col3" xsi:type="SQLNVARCHAR"/>
 </ROW>
</BCPFORMAT>
```

#### <a name="using-openrowsetbulk"></a><span data-ttu-id="ba9d0-169">Utilizzo di OPENROWSET(BULK...)</span><span class="sxs-lookup"><span data-stu-id="ba9d0-169">Using OPENROWSET(BULK...)</span></span>
 <span data-ttu-id="ba9d0-170">Nell'esempio seguente viene utilizzato il provider di set di righe con lettura bulk `OPENROWSET` e il file di formato `myTestSkipCol2.xml` .</span><span class="sxs-lookup"><span data-stu-id="ba9d0-170">The following example uses the `OPENROWSET` bulk rowset provider and the `myTestSkipCol2.xml` format file.</span></span> <span data-ttu-id="ba9d0-171">Nell'esempio viene eseguita l'importazione bulk del file di dati `myTestSkipCol2.dat` nella tabella `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="ba9d0-171">The example bulk imports the `myTestSkipCol2.dat` data file into the `myTestSkipCol` table.</span></span> <span data-ttu-id="ba9d0-172">L'istruzione contiene un elenco esplicito di colonne nell'elenco selezionato e nella tabella di destinazione, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-172">The statement contains an explicit list of columns in the select list and also in the target table, as required.</span></span>

 <span data-ttu-id="ba9d0-173">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-173">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
USE AdventureWorks2012;
GO
INSERT INTO myTestSkipCol
  (Col1,Col3)
    SELECT Col1,Col3
      FROM  OPENROWSET(BULK  'C:\myTestSkipCol2.Dat',
      FORMATFILE='C:\myTestSkipCol2.Xml'  
       ) as t1 ;
GO
```

#### <a name="using-bulk-import-on-a-view"></a><span data-ttu-id="ba9d0-174">Utilizzo di BULK IMPORT in una vista</span><span class="sxs-lookup"><span data-stu-id="ba9d0-174">Using BULK IMPORT on a View</span></span>
 <span data-ttu-id="ba9d0-175">Nell'esempio seguente viene creata la tabella `v_myTestSkipCol` nella tabella `myTestSkipCol` .</span><span class="sxs-lookup"><span data-stu-id="ba9d0-175">The following example creates the `v_myTestSkipCol` on the `myTestSkipCol` table.</span></span> <span data-ttu-id="ba9d0-176">Questa vista ignora la seconda colonna della tabella, `Col2`.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-176">This view skips the second table column, `Col2`.</span></span> <span data-ttu-id="ba9d0-177">Nell'esempio viene quindi utilizzato `BULK INSERT` per importare il file di dati `myTestSkipCol2.dat` in questa vista.</span><span class="sxs-lookup"><span data-stu-id="ba9d0-177">The example then uses `BULK INSERT` to import the `myTestSkipCol2.dat` data file into this view.</span></span>

 <span data-ttu-id="ba9d0-178">Nell'editor di query di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] eseguire il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ba9d0-178">In the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] Query Editor, execute the following code:</span></span>

```
CREATE VIEW v_myTestSkipCol AS
    SELECT Col1,Col3
    FROM myTestSkipCol;
GO

USE AdventureWorks2012;
GO
BULK INSERT v_myTestSkipCol
FROM 'C:\myTestSkipCol2.dat'
WITH (FORMATFILE='C:\myTestSkipCol2.xml');
GO
```

## <a name="see-also"></a><span data-ttu-id="ba9d0-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba9d0-179">See Also</span></span>
 <span data-ttu-id="ba9d0-180">[utilità bcp](../../tools/bcp-utility.md) [BULK INSERT &#40;transact-sql&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) utilizzare un file [di formato per ignorare un campo dati &#40;](use-a-format-file-to-skip-a-data-field-sql-server.md) SQL Server&#41;[utilizzare un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) SQL Server&#41;[utilizzare un file di formato per l'importazione bulk dei dati](use-a-format-file-to-bulk-import-data-sql-server.md) &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ba9d0-180">[bcp Utility](../../tools/bcp-utility.md) [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) [OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md) [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md) [Use a Format File to Bulk Import Data &#40;SQL Server&#41;](use-a-format-file-to-bulk-import-data-sql-server.md)</span></span>


