---
title: File di formato per l'importazione o l'esportazione di dati (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], format files
- bulk importing [SQL Server], format files
- format files [SQL Server]
ms.assetid: b7b97d68-4336-4091-aee4-1941fab568e3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1143690f0322fef2612fde51eebcb7427ee237ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635595"
---
# <a name="format-files-for-importing-or-exporting-data-sql-server"></a><span data-ttu-id="7bbd1-102">File di formato per l'importazione o l'esportazione di dati (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7bbd1-102">Format Files for Importing or Exporting Data (SQL Server)</span></span>
  <span data-ttu-id="7bbd1-103">Quando si importando dati in blocco in una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o si esportano dati in blocco da una tabella, è possibile usare un *file di formato* per archiviare le informazioni sul formato necessarie all'esportazione o all'importazione in blocco dei dati.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-103">When you bulk import data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table or bulk export data from a table, you can use a *format file* to store all the format information that is required to bulk export or bulk import data.</span></span> <span data-ttu-id="7bbd1-104">Sono incluse informazioni sul formato per ogni campo in un file di dati relativo a quella tabella.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-104">This includes format information for each field in a data file relative to that table.</span></span>  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="7bbd1-105">supporta due tipi di file di formato: file di formato XML e file di formato non XML.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-105">supports two types of format files: XML formats and non-XML format files.</span></span> <span data-ttu-id="7bbd1-106">In entrambi i tipi di file di formato XML e non XML sono contenute descrizioni di ogni campo in un file di dati; nei file di formato XML sono inoltre presenti descrizioni delle colonne della tabella corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-106">Both non-XML format files and XML format files contain descriptions of every field in a data file, and XML format files also contain descriptions of the corresponding table columns.</span></span> <span data-ttu-id="7bbd1-107">In generale, i file di formato XML e non XML sono intercambiabili.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-107">Generally, XML and non-XML format files are interchangeable.</span></span> <span data-ttu-id="7bbd1-108">È tuttavia consigliabile utilizzare la sintassi XML per i nuovi file di formato, in quanto questo tipo di file offre numerosi vantaggi rispetto ai file di formato non XML.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-108">However, we recommend that you use the XML syntax for new format files because they provide several advantages over non-XML format files.</span></span> <span data-ttu-id="7bbd1-109">Per altre informazioni, vedere [File in formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd1-109">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 
  
##  <a name="benefits-of-format-files"></a><a name="Benefits"></a> <span data-ttu-id="7bbd1-110">Vantaggi dei file di formato</span><span class="sxs-lookup"><span data-stu-id="7bbd1-110">Benefits of Format Files</span></span>  
  
-   <span data-ttu-id="7bbd1-111">Fornisce un sistema flessibile per la scrittura di file di dati che non richiede alcuna modifica o richiede modifiche minime per la conformità con altri formati di dati o la lettura di file di dati da un altro prodotto software.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-111">Provides a flexible system for writing data files that requires little or no editing to comply with other data formats or to read data files from other software.</span></span>  
  
-   <span data-ttu-id="7bbd1-112">Consente di eseguire l'importazione bulk dei dati senza necessità di aggiungere o eliminare dati superflui o di ripetere l'ordinamento dei dati esistenti nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-112">Enables you to bulk import data without having to add or delete unnecessary data or to reorder existing data in the data file.</span></span> <span data-ttu-id="7bbd1-113">I file di formato sono particolarmente utili quando è presente una mancata corrispondenza tra i campi nel file di dati e le colonne nella tabella.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-113">Format files are particularly useful when a mismatch exists between fields in the data file and columns in the table.</span></span>  
  
##  <a name="examples-of-format-files"></a><a name="ExamplesOfFFs"></a> <span data-ttu-id="7bbd1-114">Esempi di file di formato</span><span class="sxs-lookup"><span data-stu-id="7bbd1-114">Examples of Format Files</span></span>  
 <span data-ttu-id="7bbd1-115">Negli esempi seguenti viene illustrato il layout di un file di formato non XML e di un file di formato XML.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-115">The following examples show the layout of a non-XML format file and of an XML format file.</span></span> <span data-ttu-id="7bbd1-116">Questi file di formato corrispondono alla tabella `HumanResources.myTeam` nel database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7bbd1-116">These format files correspond to the `HumanResources.myTeam` table in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="7bbd1-117">Questa tabella contiene quattro colonne: `EmployeeID`, `Name`, `Title`e `ModifiedDate`.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-117">This table contains four columns: `EmployeeID`, `Name`, `Title`, and `ModifiedDate`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bbd1-118">Per informazioni su questa tabella e su come crearla, vedere [Tabella di esempio HumanResources.myTeam &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd1-118">For information about this table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
### <a name="a-using-a-non-xml-format-file"></a><span data-ttu-id="7bbd1-119">R.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-119">A.</span></span> <span data-ttu-id="7bbd1-120">Utilizzo di un file di formato non XML</span><span class="sxs-lookup"><span data-stu-id="7bbd1-120">Using a non-XML format file</span></span>  
 <span data-ttu-id="7bbd1-121">Il file di formato non XML seguente utilizza il formato di dati nativo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la tabella `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="7bbd1-121">The following non-XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="7bbd1-122">Questo file di formato è stato creato utilizzando il comando `bcp` seguente.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-122">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Fmt -n -T   
The contents of this format file are as follows: 9.0  
4  
1       SQLSMALLINT   0       2       ""   1     EmployeeID               ""  
2       SQLNCHAR      2       100     ""   2     Name                     SQL_Latin1_General_CP1_CI_AS  
3       SQLNCHAR      2       100     ""   3     Title                    SQL_Latin1_General_CP1_CI_AS  
4       SQLNCHAR      2       100     ""   4     Background               SQL_Latin1_General_CP1_CI_AS  
```  
  
 <span data-ttu-id="7bbd1-123">Per altre informazioni, vedere [File in formato non XML &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd1-123">For more information, see [Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md).</span></span>  
  
 
  
### <a name="b-using-an-xml-format-file"></a><span data-ttu-id="7bbd1-124">B.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-124">B.</span></span> <span data-ttu-id="7bbd1-125">Utilizzo di un file di formato XML</span><span class="sxs-lookup"><span data-stu-id="7bbd1-125">Using an XML format file</span></span>  
 <span data-ttu-id="7bbd1-126">Il seguente file di formato XML utilizza il formato nativo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la tabella `HumanResources.myTeam` .</span><span class="sxs-lookup"><span data-stu-id="7bbd1-126">The following XML format file uses the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data format for the `HumanResources.myTeam` table.</span></span> <span data-ttu-id="7bbd1-127">Questo file di formato è stato creato utilizzando il comando `bcp` seguente.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-127">This format file was created by using the following `bcp` command.</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam format nul -f myTeam.Xml -x -n -T   
```  
  
 <span data-ttu-id="7bbd1-128">Il file di formato contiene:</span><span class="sxs-lookup"><span data-stu-id="7bbd1-128">The format file contains:</span></span>  
  
```  
 <?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="3" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  <FIELD ID="4" xsi:type="NCharPrefix" PREFIX_LENGTH="2" MAX_LENGTH="100" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="EmployeeID" xsi:type="SQLSMALLINT"/>  
  <COLUMN SOURCE="2" NAME="Name" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="3" NAME="Title" xsi:type="SQLNVARCHAR"/>  
  <COLUMN SOURCE="4" NAME="Background" xsi:type="SQLNVARCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
 <span data-ttu-id="7bbd1-129">Per altre informazioni, vedere [File in formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7bbd1-129">For more information, see [XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="when-is-a-format-file-required"></a><a name="WhenFFrequired"></a> <span data-ttu-id="7bbd1-130">Quando è necessario un file di formato?</span><span class="sxs-lookup"><span data-stu-id="7bbd1-130">When Is a Format File Required?</span></span>  
 <span data-ttu-id="7bbd1-131">Un'istruzione INSERT ... SELECT \* FROM OPENROWSET(BULK...) richiede sempre un file di formato.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-131">An INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement always requires a format file.</span></span>  
  
-   <span data-ttu-id="7bbd1-132">Per **bcp** o BULK INSERT, in situazioni non complesse, l'uso di un file di formato è facoltativo e solo raramente necessario.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-132">For **bcp** or BULK INSERT, in simple situations, using a format file is optional and rarely necessary.</span></span> <span data-ttu-id="7bbd1-133">In situazioni di importazione bulk complesse, tuttavia, un file di formato è spesso necessario.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-133">However, for complex bulk-import situations, a format file is frequently required.</span></span>  
  
 <span data-ttu-id="7bbd1-134">I file di formato sono necessari nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bbd1-134">Format files are required if:</span></span>  
  
-   <span data-ttu-id="7bbd1-135">Viene utilizzato lo stesso file di dati come origine per più tabelle con schemi diversi.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-135">The same data file is used as a source for multiple tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="7bbd1-136">I campi nel file di dati sono in numero diverso rispetto alle colonne della tabella di destinazione, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="7bbd1-136">The data file has a different number of fields that the target table has columns; for example:</span></span>  
  
    -   <span data-ttu-id="7bbd1-137">La tabella di destinazione include almeno una colonna per la quale un valore predefinito è definito o è consentito un valore NULL.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-137">The target table contains at least one column for which either a default value is defined or NULL is allowed.</span></span>  
  
    -   <span data-ttu-id="7bbd1-138">L'utente non dispone di autorizzazioni SELECT/INSERT su una o più colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-138">The users do not have SELECT/INSERT permissions on one or more columns in the table.</span></span>  
  
    -   <span data-ttu-id="7bbd1-139">Un singolo file di dati è utilizzato con due o più tabelle con schemi diversi.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-139">A single data file is used with two or more tables that have different schemas.</span></span>  
  
-   <span data-ttu-id="7bbd1-140">L'ordine delle colonne è diverso nel file di dati rispetto alla tabella.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-140">The column order is different for the data file and table.</span></span>  
  
-   <span data-ttu-id="7bbd1-141">I caratteri di terminazione o le lunghezze di prefisso sono diverse all'interno delle colonne del file di dati.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-141">The terminating characters or prefix lengths differ among the columns of the data file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7bbd1-142">In assenza di un file di formato, se in un comando **bcp** viene specificata un'opzione di formato di dati ( **-n**, **-c**, **-w**o **-N**) o se in un'operazione BULK INSERT viene specificata l'opzione DATAFILETYPE, il formato di dati specificato viene usato come metodo predefinito per l'interpretazione dei campi del file di dati.</span><span class="sxs-lookup"><span data-stu-id="7bbd1-142">In the absence of a format file, if a **bcp** command specifies a data-format switch (**-n**, **-c**, **-w**, or **-N**) or a BULK INSERT operation specifies the DATAFILETYPE option, the specified data format is used as the default method of interpreting the fields of the data file.</span></span>  
  
 
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7bbd1-143">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="7bbd1-143">Related Tasks</span></span>  
  
-   [<span data-ttu-id="7bbd1-144">Creazione di un file di formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7bbd1-144">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="7bbd1-145">Usare un file di formato per l'importazione in blocco dei dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7bbd1-145">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="7bbd1-146">Utilizzo di un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7bbd1-146">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="7bbd1-147">Utilizzo di un file di formato per escludere un campo di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7bbd1-147">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="7bbd1-148">Utilizzo di un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7bbd1-148">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="7bbd1-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bbd1-149">See Also</span></span>  
 <span data-ttu-id="7bbd1-150">[File in formato non XML &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7bbd1-150">[Non-XML Format Files &#40;SQL Server&#41;](non-xml-format-files-sql-server.md) </span></span>  
 <span data-ttu-id="7bbd1-151">[File in formato XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7bbd1-151">[XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="7bbd1-152">Formati di dati per l'importazione o l'esportazione in blocco &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7bbd1-152">Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;</span></span>](data-formats-for-bulk-import-or-bulk-export-sql-server.md)  
  
  
