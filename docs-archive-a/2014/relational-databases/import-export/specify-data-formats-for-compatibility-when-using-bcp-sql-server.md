---
title: Specificare i formati di dati per la compatibilità con bcp (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- bulk exporting [SQL Server], compatibility
- bulk importing [SQL Server], compatibility
- compatibility [SQL Server], data formats
- data formats [SQL Server], compatibility
- bcp utility [SQL Server], compatibility
ms.assetid: cd5fc8c8-eab1-4165-9468-384f31e53f0a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5d12456760f32ddbd8cc434d474aebb0e0ecf141
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722844"
---
# <a name="specify-data-formats-for-compatibility-when-using-bcp-sql-server"></a><span data-ttu-id="33744-102">Impostazione dei formati di dati per la compatibilità mediante bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="33744-102">Specify Data Formats for Compatibility when Using bcp (SQL Server)</span></span>
  <span data-ttu-id="33744-103">In questo argomento vengono descritti gli attributi di formato dati, i prompt specifici di campo e l'archiviazione dei dati campo per campo in un file di formato non XML del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `bcp` comando.</span><span class="sxs-lookup"><span data-stu-id="33744-103">This topic describes the data-format attributes, field-specific prompts, and storing field-by-field data in a non-xml format file of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]`bcp` command.</span></span> <span data-ttu-id="33744-104">La comprensione di questi concetti può risultare utile per l'esportazione bulk di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a fini di importazione in un altro programma, ad esempio un altra applicazione di database.</span><span class="sxs-lookup"><span data-stu-id="33744-104">Understanding these can be helpful when you bulk export [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data for bulk import into another program, such as another database program.</span></span> <span data-ttu-id="33744-105">I formati di dati predefiniti (native, character o Unicode) nella tabella di origine potrebbero non essere compatibili con il layout di dati previsto dall'altra applicazione. In questo caso, quando si esportano i dati è necessario descriverne il layout.</span><span class="sxs-lookup"><span data-stu-id="33744-105">The default data formats (native, character, or Unicode) in the source table might be incompatible with the data layout expected by the other program If an incompatibility exists, when you export the data, you must describe the data layout.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33744-106">Se non si ha familiarità con i formati di dati per l'importazione o esportazione di dati, vedere [Formati di dati per l'importazione o l'esportazione bulk &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33744-106">If you are unfamiliar with data formats for importing or exporting data, see [Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md).</span></span>  
  
 <span data-ttu-id="33744-107">**Contenuto dell'argomento:**</span><span class="sxs-lookup"><span data-stu-id="33744-107">**In This Topic:**</span></span>  
  
-   [<span data-ttu-id="33744-108">Attributi di formato dati bcp</span><span class="sxs-lookup"><span data-stu-id="33744-108">bcp Data-Format Attributes</span></span>](#bcpDataFormatAttr)  
  
-   [<span data-ttu-id="33744-109">Panoramica dei prompt specifici del campo</span><span class="sxs-lookup"><span data-stu-id="33744-109">Overview of the Field-Specific Prompts</span></span>](#FieldSpecificPrompts)  
  
-   [<span data-ttu-id="33744-110">Archiviazione di dati campo per campo in un file di formato non XML</span><span class="sxs-lookup"><span data-stu-id="33744-110">Storing Field-by-Field Data in a Non-XML Format File</span></span>](#FieldByFieldNonXmlFF)  
  
-   [<span data-ttu-id="33744-111">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="33744-111">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="bcp-data-format-attributes"></a><a name="bcpDataFormatAttr"></a> <span data-ttu-id="33744-112">Attributi di formato e dati di bcp</span><span class="sxs-lookup"><span data-stu-id="33744-112">bcp Data-Format Attributes</span></span>  
 <span data-ttu-id="33744-113">Il comando `bcp` consente di specificare la struttura di tutti i campi di un file di dati mediante i seguenti attributi di formato dati:</span><span class="sxs-lookup"><span data-stu-id="33744-113">The `bcp` command allows you to specify the structure of each field in a data file in terms of the following data-format attributes:</span></span>  
  
-   <span data-ttu-id="33744-114">tipo di archiviazione di file</span><span class="sxs-lookup"><span data-stu-id="33744-114">File storage type</span></span>  
  
     <span data-ttu-id="33744-115">Il *tipo di archiviazione di file* indica la modalità con la quale vengono archiviati i dati in un file.</span><span class="sxs-lookup"><span data-stu-id="33744-115">The *file storage type* describes how data is stored in the data file.</span></span> <span data-ttu-id="33744-116">I dati possono essere esportati in un file utilizzando il tipo di dati della tabella del database in cui si trovano (formato nativo), come caratteri (formato carattere) o utilizzando qualsiasi tipo di dati nel caso in cui sia supportata la conversione implicita. È possibile ad esempio copiare il tipo `smallint` come `int`.</span><span class="sxs-lookup"><span data-stu-id="33744-116">Data can be exported to a data file as its database table type (native format), in its character representation (character format), or as any data type where implicit conversion is supported; for example, copying a `smallint` as an `int`.</span></span> <span data-ttu-id="33744-117">I tipi di dati definiti dall'utente vengono esportati utilizzando il tipo di dati di base corrispondente.</span><span class="sxs-lookup"><span data-stu-id="33744-117">User-defined data types are exported as their base types.</span></span> <span data-ttu-id="33744-118">Per altre informazioni, vedere [Specifica del tipo di archiviazione di file tramite bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33744-118">For more information, see [Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="33744-119">Lunghezza del prefisso</span><span class="sxs-lookup"><span data-stu-id="33744-119">Prefix length</span></span>  
  
     <span data-ttu-id="33744-120">Per implementare il tipo di archiviazione più compatto durante l'esportazione bulk dei dati in formato nativo in un file di dati, il comando `bcp` inserisce davanti a ogni campo uno o più caratteri che ne indicano la lunghezza.</span><span class="sxs-lookup"><span data-stu-id="33744-120">To provide the most compact file storage for the bulk export of data in native format to a data file, the `bcp` command precedes each field with one or more characters that indicates the length of the field.</span></span> <span data-ttu-id="33744-121">Tali caratteri sono denominati *caratteri per il prefisso di lunghezza*.</span><span class="sxs-lookup"><span data-stu-id="33744-121">These characters are called *length prefix characters*.</span></span> <span data-ttu-id="33744-122">Per altre informazioni, vedere [Specificare la lunghezza del prefisso nei file di dati tramite bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33744-122">For more information, see [Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="33744-123">Lunghezza del campo</span><span class="sxs-lookup"><span data-stu-id="33744-123">Field length</span></span>  
  
     <span data-ttu-id="33744-124">La lunghezza del campo indica il numero massimo di caratteri necessari per rappresentare i dati in formato carattere.</span><span class="sxs-lookup"><span data-stu-id="33744-124">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="33744-125">Se i dati sono archiviati in formato nativo, la lunghezza del campo è già nota.</span><span class="sxs-lookup"><span data-stu-id="33744-125">The field length is already known if the data is stored in the native format.</span></span> <span data-ttu-id="33744-126">Per altre informazioni, vedere [Definizione della lunghezza di campo tramite bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33744-126">For more information, see [Specify Field Length by Using bcp &#40;SQL Server&#41;](specify-field-length-by-using-bcp-sql-server.md).</span></span>  
  
-   <span data-ttu-id="33744-127">Carattere di terminazione del campo</span><span class="sxs-lookup"><span data-stu-id="33744-127">Field terminator</span></span>  
  
     <span data-ttu-id="33744-128">Nei campi dati di tipo carattere, i caratteri di terminazione facoltativi consentono di indicare la fine di ogni campo nel file di dati (tramite un *carattere di terminazione del campo*) e di ogni riga (tramite un *carattere di terminazione della riga*).</span><span class="sxs-lookup"><span data-stu-id="33744-128">For character data fields, optional terminating characters allow you to mark the end of each field in a data file (using a *field terminator*) and the end of each row (using a *row terminator*).</span></span> <span data-ttu-id="33744-129">I caratteri di terminazione indicano ai programmi che leggono il file il punto in cui termina il campo o la riga e inizia il campo o la riga successiva.</span><span class="sxs-lookup"><span data-stu-id="33744-129">Terminating characters are one way to indicate to programs reading the data file where one field or row ends and another begins.</span></span> <span data-ttu-id="33744-130">Per altre informazioni, vedere [Impostazione dei caratteri di terminazione del campo e della riga &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33744-130">For more information, see [Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md).</span></span>  
  
##  <a name="overview-of-the-field-specific-prompts"></a><a name="FieldSpecificPrompts"></a> <span data-ttu-id="33744-131">Panoramica dei prompt specifici dei campi</span><span class="sxs-lookup"><span data-stu-id="33744-131">Overview of the Field-Specific Prompts</span></span>  
 <span data-ttu-id="33744-132">Se un `bcp` comando interattivo contiene l' **opzione in** o **out** , ma non contiene anche l'opzione del file di formato (**-f**) o un'opzione di formato dati (**-n**, **-c**, **-w**o **-n**), ogni colonna nella tabella di origine o di destinazione, il comando richiede ciascuno degli attributi precedenti, a sua volta.</span><span class="sxs-lookup"><span data-stu-id="33744-132">If an interactive `bcp` command contains the **in** or **out** option but does not also contain either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**),  each column in the source or target table, the command prompts for each of the preceding attributes, in turn.</span></span> <span data-ttu-id="33744-133">In ogni prompt, il comando `bcp` offre un valore predefinito in base al tipo di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] della colonna di tabella.</span><span class="sxs-lookup"><span data-stu-id="33744-133">In each prompt, the `bcp` command provides a default value based on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the table column.</span></span> <span data-ttu-id="33744-134">Accettare il valore predefinito per tutti i prompt equivale a specificare il formato nativo ( **-n**) nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="33744-134">Accepting the default value for all of the prompts produces the same result as specifying native format (**-n**) on the command line.</span></span> <span data-ttu-id="33744-135">Ogni prompt mostra un valore predefinito fra parentesi: [*predefinito*].</span><span class="sxs-lookup"><span data-stu-id="33744-135">Each prompt displays a default value in brackets: [*default*].</span></span> <span data-ttu-id="33744-136">Per accettare i valori predefiniti, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="33744-136">Pressing ENTER accepts the displayed default.</span></span> <span data-ttu-id="33744-137">Per specificare un valore diverso da quello predefinito, immettere il valore desiderato al prompt.</span><span class="sxs-lookup"><span data-stu-id="33744-137">To specify a value other than the default, enter the new value at the prompt.</span></span>  
  
### <a name="example"></a><span data-ttu-id="33744-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="33744-138">Example</span></span>  
 <span data-ttu-id="33744-139">Nell'esempio seguente il comando `bcp` viene utilizzato per l'esportazione bulk interattiva dei dati dalla tabella `HumanResources.myTeam` al file `myTeam.txt`.</span><span class="sxs-lookup"><span data-stu-id="33744-139">The following example uses the `bcp` command to bulk export data from the `HumanResources.myTeam` table interactively to the `myTeam.txt` file.</span></span> <span data-ttu-id="33744-140">Prima di eseguire l'esempio è necessario creare questa tabella.</span><span class="sxs-lookup"><span data-stu-id="33744-140">Before you can run the example, you must create this table.</span></span> <span data-ttu-id="33744-141">Per informazioni sulla modalità di creazione e sulla tabella, vedere [Tabella di esempio HumanResources.myTeam &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33744-141">For information about the table and how to create it, see [HumanResources.myTeam Sample Table &#40;SQL Server&#41;](humanresources-myteam-sample-table-sql-server.md).</span></span>  
  
 <span data-ttu-id="33744-142">Il comando non specifica un file di formato né un tipo di dati. Ciò provoca la richiesta di informazioni di formato dati da parte di `bcp`.</span><span class="sxs-lookup"><span data-stu-id="33744-142">The command specifies neither a format file nor a data type, causing `bcp` to prompt for data-format information.</span></span> <span data-ttu-id="33744-143">Al prompt dei comandi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows digitare:</span><span class="sxs-lookup"><span data-stu-id="33744-143">At the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows command prompt, enter:</span></span>  
  
```  
bcp AdventureWorks.HumanResources.myTeam out myTeam.txt -T  
```  
  
 <span data-ttu-id="33744-144">Per ogni colonna, bcp richiede valori specifici del campo.</span><span class="sxs-lookup"><span data-stu-id="33744-144">For each column, bcp prompts for field-specific values.</span></span> <span data-ttu-id="33744-145">Nell'esempio seguente vengono illustrati i prompt specifici di campo per le colonne `EmployeeID` e `Name` della tabella e viene suggerito il tipo di archiviazione file predefinito (il formato nativo) per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="33744-145">The following example shows the field-specific prompts for the `EmployeeID` and `Name` columns of the table, and suggests the default file storage type (the native format) for each column.</span></span> <span data-ttu-id="33744-146">Le lunghezze del prefisso delle colonne `EmployeeID` e `Name` sono rispettivamente 0 e 2.</span><span class="sxs-lookup"><span data-stu-id="33744-146">The prefix lengths of the `EmployeeID` and `Name` column are 0 and 2, respectively.</span></span> <span data-ttu-id="33744-147">L'utente specifica una virgola (`,`) come carattere di terminazione di ogni campo.</span><span class="sxs-lookup"><span data-stu-id="33744-147">The user specifies a comma (`,`) as the terminator of each field.</span></span>  
  
 `Enter the file storage type of field EmployeeID [smallint]:`  
  
 `Enter prefix-length of field EmployeeID [0]:`  
  
 `Enter field terminator [none]:,`  
  
 `Enter the file storage type of field Name [nvarchar]:`  
  
 `Enter prefix length of field Name [2]:`  
  
 `Enter field terminator [none]:,`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 <span data-ttu-id="33744-148">Per ogni colonna della tabella, in ordine e se necessario, vengono visualizzati prompt equivalenti.</span><span class="sxs-lookup"><span data-stu-id="33744-148">Equivalent prompts (as needed) are displayed for each of the table columns in order.</span></span>  
  
##  <a name="storing-field-by-field-data-in-a-non-xml-format-file"></a><a name="FieldByFieldNonXmlFF"></a> <span data-ttu-id="33744-149">Archiviazione di dati campo per campo in un file di formato non XML</span><span class="sxs-lookup"><span data-stu-id="33744-149">Storing Field-by-Field Data in a Non-XML Format File</span></span>  
 <span data-ttu-id="33744-150">Una volta specificate tutte le colonne della tabella, il comando `bcp` chiede se si desidera generare un file di formato non XML per l'archiviazione delle informazioni campo per campo appena inserite (vedere l'esempio precedente).</span><span class="sxs-lookup"><span data-stu-id="33744-150">After all of the table columns are specified, the `bcp` command prompts you to optionally generate a non-XML format file that stores the field-by-field information just supplied (see the preceding example).</span></span> <span data-ttu-id="33744-151">Se si sceglie di generare un file di formato, è possibile utilizzarlo ogni volta che si esportano dati da quella tabella o si importano dati di struttura simile in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33744-151">If you choose to generate a format file, you can whenever you export data out of that table or import like-structured data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33744-152">Il file di formato può essere utilizzato per eseguire l'importazione bulk dal file di dati a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o per eseguire l'esportazione bulk di dati dalla tabella senza dover nuovamente specificare il formato.</span><span class="sxs-lookup"><span data-stu-id="33744-152">You can use the format file to bulk import data from the data file into an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or to bulk export data from the table, without needing to respecify the format.</span></span> <span data-ttu-id="33744-153">Per altre informazioni, vedere [File di formato per l'importazione o l'esportazione di dati &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33744-153">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="33744-154">Nell'esempio seguente viene creato un file di formato non XML denominato `myFormatFile.fmt`:</span><span class="sxs-lookup"><span data-stu-id="33744-154">The following example creates a non-XML format file named `myFormatFile.fmt`:</span></span>  
  
 `Do you want to save this format information in a file? [Y/n] y`  
  
 `Host filename: [bcp.fmt]myFormatFile.fmt`  
  
 <span data-ttu-id="33744-155">Il nome predefinito per il file di formato è bcp.fmt, ma è possibile specificare un nome diverso.</span><span class="sxs-lookup"><span data-stu-id="33744-155">The default name for the format file is bcp.fmt, but you can specify a different file name if you choose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33744-156">Per un file di dati che usa un unico formato dati per il tipo di archiviazione, ad esempio il formato carattere o nativo, è possibile creare rapidamente un file di formato senza esportare o importare dati usando l'opzione **format** .</span><span class="sxs-lookup"><span data-stu-id="33744-156">For a data file that uses a single data format for its file-storage type, such as character or native format, you can quickly create a format file without exporting or importing data by using the **format** option.</span></span> <span data-ttu-id="33744-157">Questo approccio ha il vantaggio della semplicità e consente di creare un file di formato XML o non XML.</span><span class="sxs-lookup"><span data-stu-id="33744-157">This approach has the advantages of being easy and of allowing you to create either an XML format file or a non-XML format file.</span></span> <span data-ttu-id="33744-158">Per altre informazioni, vedere [Creazione di un file di formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="33744-158">For more information, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="33744-159">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="33744-159">Related Tasks</span></span>  
  
-   [<span data-ttu-id="33744-160">Specifica del tipo di archiviazione di file tramite bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="33744-160">Specify File Storage Type by Using bcp &#40;SQL Server&#41;</span></span>](specify-file-storage-type-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="33744-161">Specificare la lunghezza del prefisso nei file di dati con bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="33744-161">Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;</span></span>](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="33744-162">Definizione della lunghezza di campo tramite bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="33744-162">Specify Field Length by Using bcp &#40;SQL Server&#41;</span></span>](specify-field-length-by-using-bcp-sql-server.md)  
  
-   [<span data-ttu-id="33744-163">Impostazione dei caratteri di terminazione del campo e della riga &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="33744-163">Specify Field and Row Terminators &#40;SQL Server&#41;</span></span>](specify-field-and-row-terminators-sql-server.md)  
  
## <a name="related-content"></a><span data-ttu-id="33744-164">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="33744-164">Related Content</span></span>  
 <span data-ttu-id="33744-165">No.</span><span class="sxs-lookup"><span data-stu-id="33744-165">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33744-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33744-166">See Also</span></span>  
 <span data-ttu-id="33744-167">[Informazioni sull'importazione ed esportazione bulk di dati &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="33744-167">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="33744-168">[Formati di dati per l'importazione o l'esportazione bulk &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="33744-168">[Data Formats for Bulk Import or Bulk Export &#40;SQL Server&#41;](data-formats-for-bulk-import-or-bulk-export-sql-server.md) </span></span>  
 <span data-ttu-id="33744-169">[Utilità bcp](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="33744-169">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 [<span data-ttu-id="33744-170">Tipi di dati &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="33744-170">Data Types &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/data-types/data-types-transact-sql)  
  
  
