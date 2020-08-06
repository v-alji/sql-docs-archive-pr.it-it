---
title: File di formato XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- format files [SQL Server], XML format files
- bulk importing [SQL Server], format files
- XML format files [SQL Server]
ms.assetid: 69024aad-eeea-4187-8fea-b49bc2359849
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7cc1e8de30fa582898ef8516b9767dec14c4fa81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636087"
---
# <a name="xml-format-files-sql-server"></a><span data-ttu-id="2efce-102">File in formato XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2efce-102">XML Format Files (SQL Server)</span></span>
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="2efce-103">viene fornito un XML Schema che definisce la sintassi per la scrittura di *file di formato XML* da utilizzare per l'importazione bulk dei dati in una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2efce-103">provides an XML schema that defines syntax for writing *XML format files* to use for bulk importing data into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="2efce-104">I file di formato XML devono essere conformi a questo schema, definito in XML Schema Definition Language (XSDL).</span><span class="sxs-lookup"><span data-stu-id="2efce-104">XML format files must adhere to this schema, which is defined in the XML Schema Definition Language (XSDL).</span></span> <span data-ttu-id="2efce-105">I file di formato XML sono supportati solo quando gli strumenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono installati insieme a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="2efce-105">XML format files are only supported when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tools are installed together with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 <span data-ttu-id="2efce-106">È possibile usare un file di formato XML con un comando **bcp**, un'istruzione BULK INSERT o un'istruzione INSERT ... Istruzione SELECT \* FROM OPENROWSET(BULK...).</span><span class="sxs-lookup"><span data-stu-id="2efce-106">You can use an XML format file with a **bcp** command, BULK INSERT statement, or INSERT ... SELECT \* FROM OPENROWSET(BULK...) statement.</span></span> <span data-ttu-id="2efce-107">Il comando **bcp** consente di generare automaticamente un file di formato XML per una tabella. Per ulteriori informazioni, vedere [bcp Utility](../../tools/bcp-utility.md).</span><span class="sxs-lookup"><span data-stu-id="2efce-107">The **bcp** command allows you to automatically generate an XML format file for a table; for more information, see [bcp Utility](../../tools/bcp-utility.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2efce-108">Sono supportati due tipi di file di formato per l'esportazione e l'importazione in blocco: *file di formato non XML* e *file di formato XML*.</span><span class="sxs-lookup"><span data-stu-id="2efce-108">Two types of format files are supported for bulk exporting and importing: *non-XML format files* and *XML format files*.</span></span> <span data-ttu-id="2efce-109">I file di formato XML offrono un'alternativa flessibile ed efficiente rispetto ai file di formato non XML.</span><span class="sxs-lookup"><span data-stu-id="2efce-109">XML format files provide a flexible and powerful alternative to non-XML format files.</span></span> <span data-ttu-id="2efce-110">Per informazioni sui file di formato non XML, vedere [File in formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2efce-110">For information about non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  

  
##  <a name="benefits-of-xml-format-files"></a><a name="BenefitsOfXmlFFs"></a> <span data-ttu-id="2efce-111">Vantaggi dei file di formato XML</span><span class="sxs-lookup"><span data-stu-id="2efce-111">Benefits of XML Format Files</span></span>  
  
-   <span data-ttu-id="2efce-112">I file di formato XML sono autodescrittivi, semplificandone la lettura, la creazione e l'estensione.</span><span class="sxs-lookup"><span data-stu-id="2efce-112">XML format files are self-describing, making them easy to read, create, and extend.</span></span> <span data-ttu-id="2efce-113">Sono inoltre leggibili, semplificando la comprensione della modalità di interpretazione dei dati durante le operazioni bulk.</span><span class="sxs-lookup"><span data-stu-id="2efce-113">They are human readable, making it easy to understand how data is interpreted during bulk operations.</span></span>  
  
-   <span data-ttu-id="2efce-114">I file di formato XML contengono i tipi di dati delle colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2efce-114">XML format files contain the data types of target columns.</span></span>  <span data-ttu-id="2efce-115">La codifica XML descrive in modo semplice i tipi di dati e gli elementi dati del file di dati, nonché il mapping tra gli elementi dati e le colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="2efce-115">The XML encoding clearly describes the data types and data elements of the data file and also the mapping between data elements and table columns.</span></span>  
  
     <span data-ttu-id="2efce-116">Consente la separazione tra la modalità di rappresentazione dei dati nel file di dati e il tipo di dati associato a ogni campo nel file.</span><span class="sxs-lookup"><span data-stu-id="2efce-116">This enables separation between how data is represented in the data file and what data type is associated with each field in the file.</span></span> <span data-ttu-id="2efce-117">Ad esempio, se il file di dati include una rappresentazione dei caratteri dei dati, il tipo della colonna SQL corrispondente viene perduto.</span><span class="sxs-lookup"><span data-stu-id="2efce-117">For example, if a data file contains a character representation of the data, the corresponding SQL column type is lost.</span></span>  
  
-   <span data-ttu-id="2efce-118">Un file di formato XML consente il caricamento di un campo contenente un unico tipo di dati LOB (Large Object) da un file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-118">An XML format file allows for loading of a field that contains a single large object (LOB) data type from a data file.</span></span>  
  
-   <span data-ttu-id="2efce-119">È possibile apportare miglioramenti a un file di formato XML, mantenendolo tuttavia compatibile con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="2efce-119">An XML format file can be enhanced yet remain compatible with its earlier versions.</span></span> <span data-ttu-id="2efce-120">La semplicità della codifica XML facilita inoltre la creazione di più file di formato per un file di dati specifico,</span><span class="sxs-lookup"><span data-stu-id="2efce-120">Furthermore, the clarity of XML encoding facilitates the creation of multiple format files for a given data file.</span></span> <span data-ttu-id="2efce-121">il che risulta utile nel caso sia necessario eseguire il mapping di tutti i campi dati o parte di essi a colonne di tabelle o viste diverse.</span><span class="sxs-lookup"><span data-stu-id="2efce-121">This is useful if you have to map all or some of the data fields to columns in different tables or views.</span></span>  
  
-   <span data-ttu-id="2efce-122">La sintassi XML è indipendente dalla direzione dell'operazione, ovvero è identica sia per l'esportazione bulk che per l'importazione bulk.</span><span class="sxs-lookup"><span data-stu-id="2efce-122">The XML syntax is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span>  
  
-   <span data-ttu-id="2efce-123">È possibile utilizzare i file di formato XML per l'importazione bulk dei dati in tabelle o in viste non partizionate e per l'esportazione bulk dei dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-123">You can use XML format files to bulk import data into tables or non-partitioned views and to bulk export data.</span></span>  
  
-   <span data-ttu-id="2efce-124">È facoltativo specificare una tabella di destinazione per la funzione OPENROWSET(BULK...),</span><span class="sxs-lookup"><span data-stu-id="2efce-124">For the OPENROWSET(BULK...) function specifying a target table is optional.</span></span> <span data-ttu-id="2efce-125">poiché la funzione si basa su un file di formato XML per la lettura dei dati da un file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-125">This is because the function relies on the XML format file to read data from a data file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2efce-126">Una tabella di destinazione è necessaria con il comando **bcp** e l'istruzione BULK INSERT in cui le colonne della tabella di destinazione vengono usate per eseguire la conversione dei tipi.</span><span class="sxs-lookup"><span data-stu-id="2efce-126">A target table is necessary with the **bcp** command and the BULK INSERT statement, which uses the target table columns to do the type conversion.</span></span>  
  
##  <a name="structure-of-xml-format-files"></a><a name="StructureOfXmlFFs"></a> <span data-ttu-id="2efce-127">Struttura dei file di formato XML</span><span class="sxs-lookup"><span data-stu-id="2efce-127">Structure of XML Format Files</span></span>  
 <span data-ttu-id="2efce-128">Analogamente a un file di formato non XML, un file di formato XML definisce il formato e la struttura dei campi dati di un file di dati ed esegue il mapping di tali campi alle colonne di una singola tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2efce-128">Like a non-XML format file, an XML format file defines the format and structure of the data fields in a data file and maps those data fields to columns in a single target table.</span></span>  
  
 <span data-ttu-id="2efce-129">Un file di formato XML include due componenti principali, \<RECORD> e \<ROW>:</span><span class="sxs-lookup"><span data-stu-id="2efce-129">An XML format file possesses two main components, \<RECORD> and \<ROW>:</span></span>  
  
-   <span data-ttu-id="2efce-130">\<RECORD> descrive i dati archiviati nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-130">\<RECORD> describes the data as it is stored in the data file.</span></span>  
  
     <span data-ttu-id="2efce-131">Ogni elemento \<RECORD> include un set di uno o più elementi \<FIELD>.</span><span class="sxs-lookup"><span data-stu-id="2efce-131">Each \<RECORD> element contains a set of one or more \<FIELD> elements.</span></span> <span data-ttu-id="2efce-132">Questi elementi corrispondono ai campi del file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-132">These elements correspond to fields in the data file.</span></span> <span data-ttu-id="2efce-133">La sintassi di base è la seguente:</span><span class="sxs-lookup"><span data-stu-id="2efce-133">The basic syntax is as follows:</span></span>  
  
     \<RECORD>  
  
     <span data-ttu-id="2efce-134">\<FIELD .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="2efce-134">\<FIELD .../> [ ...*n* ]</span></span>  
  
     \</RECORD>  
  
     <span data-ttu-id="2efce-135">Ogni elemento \<FIELD> descrive il contenuto di un campo dati specifico.</span><span class="sxs-lookup"><span data-stu-id="2efce-135">Each \<FIELD> element describes the contents of a specific data field.</span></span> <span data-ttu-id="2efce-136">È possibile eseguire il mapping di un campo unicamente a una colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="2efce-136">A field can only be mapped to one column in the table.</span></span> <span data-ttu-id="2efce-137">Non è tuttavia necessario eseguire il mapping di tutti i campi a colonne.</span><span class="sxs-lookup"><span data-stu-id="2efce-137">Not all fields need to be mapped to columns.</span></span>  
  
     <span data-ttu-id="2efce-138">Un campo di un file di dati può essere a lunghezza fissa o variabile oppure può terminare con un carattere.</span><span class="sxs-lookup"><span data-stu-id="2efce-138">A field in a data file can be either of fixed/variable length or character terminated.</span></span> <span data-ttu-id="2efce-139">Un *valore del campo* può essere rappresentato da un carattere (rappresentazione a un byte), da un carattere wide (rappresentazione Unicode a due byte), da un formato nativo del database o da un nome file.</span><span class="sxs-lookup"><span data-stu-id="2efce-139">A *field value* can be represented as: a character (using single-byte representation), a wide character (using Unicode two-byte representation), native database format, or a file name.</span></span> <span data-ttu-id="2efce-140">Se un valore del campo è rappresentato da un nome di file, tale nome punta al file contenente il valore di una colonna BLOB della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2efce-140">If a field value is represented as a file name, the file name points to the file that contains the value of a BLOB column in the target table.</span></span>  
  
-   <span data-ttu-id="2efce-141">\<ROW> descrive come creare righe di dati da un file di dati quando i dati del file vengono importati in una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2efce-141">\<ROW> describes how to construct data rows from a data file when the data from the file is imported into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
     <span data-ttu-id="2efce-142">Un elemento \<ROW> include un set di elementi \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="2efce-142">A \<ROW> element contains a set of \<COLUMN> elements.</span></span> <span data-ttu-id="2efce-143">Questi elementi corrispondono alle colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="2efce-143">These elements correspond to table columns.</span></span> <span data-ttu-id="2efce-144">La sintassi di base è la seguente:</span><span class="sxs-lookup"><span data-stu-id="2efce-144">The basic syntax is as follows:</span></span>  
  
     \<ROW>  
  
     <span data-ttu-id="2efce-145">\<COLUMN .../> [ ...*n* ]</span><span class="sxs-lookup"><span data-stu-id="2efce-145">\<COLUMN .../> [ ...*n* ]</span></span>  
  
     \</ROW>  
  
     <span data-ttu-id="2efce-146">È possibile eseguire il mapping di ogni elemento \<COLUMN> a un solo campo nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-146">Each \<COLUMN> element can be mapped to only one field in the data file.</span></span> <span data-ttu-id="2efce-147">L'ordine degli elementi \<COLUMN> nell'elemento \<ROW> definisce l'ordine in cui gli elementi vengono restituiti dall'operazione in blocco.</span><span class="sxs-lookup"><span data-stu-id="2efce-147">The order of the \<COLUMN> elements in the \<ROW> element defines the order in which they are returned by the bulk operation.</span></span> <span data-ttu-id="2efce-148">Il file di formato XML assegna ogni elemento \<COLUMN> a un nome locale senza alcuna relazione con la colonna nella tabella di destinazione di un'operazione di importazione in blocco.</span><span class="sxs-lookup"><span data-stu-id="2efce-148">The XML format file assigns each \<COLUMN> element a local name that has no relationship to the column in the target table of a bulk import operation.</span></span>  
  
##  <a name="schema-syntax-for-xml-format-files"></a><a name="SchemaSyntax"></a> <span data-ttu-id="2efce-149">Sintassi dello schema per i file di formato XML</span><span class="sxs-lookup"><span data-stu-id="2efce-149">Schema Syntax for XML Format Files</span></span>  
 <span data-ttu-id="2efce-150">In questa sezione è incluso un riepilogo degli elementi e degli attributi di XML Schema per i file di formato XML.</span><span class="sxs-lookup"><span data-stu-id="2efce-150">This section contains a summary of the elements and attributes of the XML schema for XML format files.</span></span> <span data-ttu-id="2efce-151">La sintassi di un file di formato è indipendente dalla direzione dell'operazione, ovvero è identica sia per l'esportazione bulk che per l'importazione bulk.</span><span class="sxs-lookup"><span data-stu-id="2efce-151">The syntax of a format file is independent of the direction of the operation; that is, the syntax is the same for bulk export and bulk import.</span></span> <span data-ttu-id="2efce-152">Questa sezione descrive anche in che modo l'importazione in blocco usa gli elementi \<ROW> e \<COLUMN> e come inserire il valore xsi:type di un elemento in un set di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-152">This section also considers how bulk import uses the \<ROW> and \<COLUMN> elements and how to put the xsi:type value of an element into a data set.</span></span>  
  
 <span data-ttu-id="2efce-153">Per informazioni sulla corrispondenza tra la sintassi e i file di formato XML effettivi, vedere [File di formato XML di esempio](#SampleXmlFFs), più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2efce-153">To see how the syntax corresponds to actual XML format files, see [Sample XML Format Files](#SampleXmlFFs), later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2efce-154">È possibile modificare un file di formato per eseguire l'importazione bulk da un file di dati in cui il numero e/o l'ordine dei campi differisce dal numero e/o dall'ordine delle colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="2efce-154">You can modify a format file to let you bulk import from a data file in which the number and/or order of the fields differ from the number and/or order of table columns.</span></span> <span data-ttu-id="2efce-155">Per altre informazioni, vedere [File di formato per l'importazione o l'esportazione di dati &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2efce-155">For more information, see [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
  
  
###  <a name="basic-syntax-of-the-xml-schema"></a><a name="BasicSyntax"></a> <span data-ttu-id="2efce-156">Sintassi di base di XML Schema</span><span class="sxs-lookup"><span data-stu-id="2efce-156">Basic Syntax of the XML Schema</span></span>  
 <span data-ttu-id="2efce-157">Le istruzioni della sintassi seguenti mostrano solo gli elementi (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW> e \<COLUMN>) e i relativi attributi di base.</span><span class="sxs-lookup"><span data-stu-id="2efce-157">This syntax statements show only the elements (\<BCPFORMAT>, \<RECORD>, \<FIELD>, \<ROW>, and \<COLUMN>) and their basic attributes.</span></span>  
  
 \<BCPFORMAT ...>  
  
 \<RECORD>  
  
 <span data-ttu-id="2efce-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span><span class="sxs-lookup"><span data-stu-id="2efce-158">\<FIELD ID = "*fieldID*" xsi:type = "*fieldType*" [...]</span></span>  
  
 />  
  
 \</RECORD>  
  
 \<ROW>  
  
 <span data-ttu-id="2efce-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span><span class="sxs-lookup"><span data-stu-id="2efce-159">\<COLUMN SOURCE = "*fieldID*" NAME = "*columnName*" xsi:type = "*columnType*" [...]</span></span>  
  
 />  
  
 \</ROW>  
  
 \</BCPFORMAT>  
  
> [!NOTE]  
>  <span data-ttu-id="2efce-160">Gli altri attributi associati al valore di xsi:type in un elemento \<FIELD> o \<COLUMN> sono descritti più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2efce-160">Additional attributes that are associated with the value of the xsi:type in a \<FIELD> or \<COLUMN> element are described later in this topic.</span></span>  
  

  
####  <a name="schema-elements"></a><a name="SchemaElements"></a> <span data-ttu-id="2efce-161">Elementi dello schema</span><span class="sxs-lookup"><span data-stu-id="2efce-161">Schema Elements</span></span>  
 <span data-ttu-id="2efce-162">In questa sezione viene riepilogato lo scopo di ciascun elemento definito da XML Schema per i file di formato XML.</span><span class="sxs-lookup"><span data-stu-id="2efce-162">This section summarizes the purpose of each element that the XML schema defines for XML format files.</span></span> <span data-ttu-id="2efce-163">Gli attributi sono descritti in apposite sezioni più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2efce-163">The attributes are described in separate sections later in this topic.</span></span>  
  
 \<BCPFORMAT>  
 <span data-ttu-id="2efce-164">Corrisponde all'elemento del file di formato che definisce la struttura del record di un file di dati specifico e la relativa corrispondenza con le colonne di una riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="2efce-164">Is the format-file element that defines the record structure of a given data file and its correspondence to the columns of a table row in the table.</span></span>  
  
 \<RECORD .../>  
 <span data-ttu-id="2efce-165">Definisce un elemento complesso contenente uno o più elementi \<FIELD>.</span><span class="sxs-lookup"><span data-stu-id="2efce-165">Defines a complex element containing one or more \<FIELD> elements.</span></span> <span data-ttu-id="2efce-166">L'ordine con cui i campi vengono dichiarati nel file di formato corrisponde a quello con cui tali campi sono riportati nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-166">The order in which the fields are declared in the format file is the order in which those fields appear in the data file.</span></span>  
  
 \<FIELD .../>  
 <span data-ttu-id="2efce-167">Definisce un campo, contenente dati, nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-167">Defines a field in data file, which contains data.</span></span>  
  
 <span data-ttu-id="2efce-168">Gli attributi di questo elemento sono descritti in [Attributi dell'elemento \<FIELD>](#AttrOfFieldElement) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2efce-168">The attributes of this element are discussed in [Attributes of the \<FIELD> Element](#AttrOfFieldElement), later in this topic.</span></span>  
  
 \<ROW .../>  
 <span data-ttu-id="2efce-169">Definisce un elemento complesso contenente uno o più elementi \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="2efce-169">Defines a complex element containing one or more \<COLUMN> elements.</span></span> <span data-ttu-id="2efce-170">L'ordine degli elementi \<COLUMN> è indipendente da quello degli elementi \<FIELD> in una definizione RECORD.</span><span class="sxs-lookup"><span data-stu-id="2efce-170">The order of the \<COLUMN> elements is independent of the order of \<FIELD> elements in a RECORD definition.</span></span> <span data-ttu-id="2efce-171">L'ordine degli elementi \<COLUMN> in un file di formato determina invece l'ordine delle colonne del set di righe risultante.</span><span class="sxs-lookup"><span data-stu-id="2efce-171">Rather, the order of the \<COLUMN> elements in a format file determines the column order of the resultant rowset.</span></span> <span data-ttu-id="2efce-172">I campi di dati vengono caricati nell'ordine in cui vengono dichiarati gli elementi \<COLUMN> corrispondenti nell'elemento \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="2efce-172">Data fields are loaded in the order in which the corresponding \<COLUMN> elements are declared in the \<COLUMN> element.</span></span>  
  
 <span data-ttu-id="2efce-173">Per altre informazioni, vedere [Uso dell'elemento \<ROW> nell'importazione in blocco](#HowUsesROW) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2efce-173">For more information, see [How Bulk Import Uses the \<ROW> Element](#HowUsesROW), later in this topic.</span></span>  
  
 \<COLUMN>  
 <span data-ttu-id="2efce-174">Definisce una colonna come elemento (\<COLUMN>).</span><span class="sxs-lookup"><span data-stu-id="2efce-174">Defines a column as an element (\<COLUMN>).</span></span> <span data-ttu-id="2efce-175">Ogni elemento \<COLUMN> corrisponde a un elemento \<FIELD>, il cui ID viene specificato nell'attributo SOURCE dell'elemento \<COLUMN>.</span><span class="sxs-lookup"><span data-stu-id="2efce-175">Each \<COLUMN> element corresponds to a \<FIELD> element (whose ID is specified in the SOURCE attribute of the \<COLUMN> element).</span></span>  
  
 <span data-ttu-id="2efce-176">Gli attributi di questo elemento sono descritti in [Attributi dell'elemento \<COLUMN>](#AttrOfColumnElement) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2efce-176">The attributes of this element are discussed in [Attributes of the \<COLUMN> Element](#AttrOfColumnElement), later in this topic.</span></span> <span data-ttu-id="2efce-177">Vedere anche [Uso dell'elemento \<COLUMN> nell'importazione in blocco](#HowUsesColumn) più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="2efce-177">Also see, [How Bulk Import Uses the \<COLUMN> Element](#HowUsesColumn), later in this topic.</span></span>  
  
 \</BCPFORMAT>  
 <span data-ttu-id="2efce-178">Richiesto per terminare il file di formato.</span><span class="sxs-lookup"><span data-stu-id="2efce-178">Required to end the format file.</span></span>  
  
####  <a name="attributes-of-the-field-element"></a><a name="AttrOfFieldElement"></a> <span data-ttu-id="2efce-179">Attributi dell'elemento \<FIELD></span><span class="sxs-lookup"><span data-stu-id="2efce-179">Attributes of the \<FIELD> Element</span></span>  
 <span data-ttu-id="2efce-180">Questa sezione descrive gli attributi dell'elemento \<FIELD>, riepilogati nella sintassi dello schema seguente:</span><span class="sxs-lookup"><span data-stu-id="2efce-180">This section describes the attributes of the \<FIELD> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="2efce-181">Valori xsi:type di <FIELD</span><span class="sxs-lookup"><span data-stu-id="2efce-181"><FIELD</span></span>  
  
 <span data-ttu-id="2efce-182">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-182">ID **="*`fieldID`*"**</span></span>  
  
 <span data-ttu-id="2efce-183">xsi **:** Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-183">xsi **:** type **="*`fieldType`*"**</span></span>  
  
 <span data-ttu-id="2efce-184">[ LENGTH **="*`n`*"** ]</span><span class="sxs-lookup"><span data-stu-id="2efce-184">[ LENGTH **="*`n`*"** ]</span></span>  
  
 <span data-ttu-id="2efce-185">[PREFIX_LENGTH **= " *`p`* "** ]</span><span class="sxs-lookup"><span data-stu-id="2efce-185">[ PREFIX_LENGTH **="*`p`*"** ]</span></span>  
  
 <span data-ttu-id="2efce-186">[MAX_LENGTH **= " *`m`* "** ]</span><span class="sxs-lookup"><span data-stu-id="2efce-186">[ MAX_LENGTH **="*`m`*"** ]</span></span>  
  
 <span data-ttu-id="2efce-187">[COLLAtion **= " *`collationName`* "** ]</span><span class="sxs-lookup"><span data-stu-id="2efce-187">[ COLLATION **="*`collationName`*"** ]</span></span>  
  
 <span data-ttu-id="2efce-188">[TERMINAtore **= " *`terminator`* "** ]</span><span class="sxs-lookup"><span data-stu-id="2efce-188">[ TERMINATOR **="*`terminator`*"** ]</span></span>  
  
 />  
  
 <span data-ttu-id="2efce-189">Ogni elemento \<FIELD> è indipendente dagli altri.</span><span class="sxs-lookup"><span data-stu-id="2efce-189">Each \<FIELD> element is independent of the others.</span></span> <span data-ttu-id="2efce-190">Per la descrizione di un campo vengono utilizzati gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2efce-190">A field is described in terms of the following attributes:</span></span>  
  
|<span data-ttu-id="2efce-191">Attributo FIELD</span><span class="sxs-lookup"><span data-stu-id="2efce-191">FIELD Attribute</span></span>|<span data-ttu-id="2efce-192">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2efce-192">Description</span></span>|<span data-ttu-id="2efce-193">Facoltativo /</span><span class="sxs-lookup"><span data-stu-id="2efce-193">Optional /</span></span><br /><br /> <span data-ttu-id="2efce-194">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="2efce-194">Required</span></span>|  
|---------------------|-----------------|------------------------------|  
|<span data-ttu-id="2efce-195">ID **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-195">ID **="*`fieldID`*"**</span></span>|<span data-ttu-id="2efce-196">Specifica il nome logico del campo nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-196">Specifies the logical name of the field in the data file.</span></span> <span data-ttu-id="2efce-197">L'ID di un campo rappresenta la chiave utilizzata per fare riferimento al campo.</span><span class="sxs-lookup"><span data-stu-id="2efce-197">The ID of a field is the key used to refer to the field.</span></span><br /><br /> <span data-ttu-id="2efce-198"><Field ID **= " *`fieldID`* "**/> esegue il mapping a <Column Source **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="2efce-198"><FIELD ID **="*`fieldID`*"**/> maps to <COLUMN SOURCE **="*`fieldID`*"**/></span></span>|<span data-ttu-id="2efce-199">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="2efce-199">Required</span></span>|  
|<span data-ttu-id="2efce-200">xsi: Type **= " *`fieldType`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-200">xsi:type **="*`fieldType`*"**</span></span>|<span data-ttu-id="2efce-201">Costrutto XML, utilizzato in modo simile a un attributo, che identifica il tipo dell'istanza dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2efce-201">This is an XML construct (used like an attribute) that identifies the type of the instance of the element.</span></span> <span data-ttu-id="2efce-202">Il valore di *fieldType* determina gli attributi opzionali, riportati di seguito, necessari in un'istanza specifica.</span><span class="sxs-lookup"><span data-stu-id="2efce-202">The value of *fieldType* determines which of the optional attributes (below) you need in a given instance.</span></span>|<span data-ttu-id="2efce-203">Obbligatorio, a seconda del tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2efce-203">Required (depending on the data type)</span></span>|  
|<span data-ttu-id="2efce-204">LUNGHEZZA **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-204">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="2efce-205">Definisce la lunghezza per un'istanza di un tipo di dati a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="2efce-205">This attribute defines the length for an instance of a fixed-length data type.</span></span><br /><br /> <span data-ttu-id="2efce-206">Il valore di *n* deve essere un numero intero positivo.</span><span class="sxs-lookup"><span data-stu-id="2efce-206">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="2efce-207">Facoltativo, a meno che non richiesto dal valore xsi:type</span><span class="sxs-lookup"><span data-stu-id="2efce-207">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="2efce-208">PREFIX_LENGTH **= " *`p`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-208">PREFIX_LENGTH **="*`p`*"**</span></span>|<span data-ttu-id="2efce-209">Definisce la lunghezza del prefisso per una rappresentazione di dati binary.</span><span class="sxs-lookup"><span data-stu-id="2efce-209">This attribute defines the prefix length for a binary data representation.</span></span> <span data-ttu-id="2efce-210">Il valore PREFIX_LENGTH *p*deve essere uno dei seguenti: 1, 2, 4 o 8.</span><span class="sxs-lookup"><span data-stu-id="2efce-210">The PREFIX_LENGTH value, *p*, must be one of the following: 1, 2, 4, or 8.</span></span>|<span data-ttu-id="2efce-211">Facoltativo, a meno che non richiesto dal valore xsi:type</span><span class="sxs-lookup"><span data-stu-id="2efce-211">Optional unless required by the xsi:type value</span></span>|  
|<span data-ttu-id="2efce-212">MAX_LENGTH **= " *`m`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-212">MAX_LENGTH **="*`m`*"**</span></span>|<span data-ttu-id="2efce-213">Corrisponde al numero massimo di byte archiviabile in un campo specifico.</span><span class="sxs-lookup"><span data-stu-id="2efce-213">This attribute is the maximum number of bytes that can be stored in a given field.</span></span> <span data-ttu-id="2efce-214">In assenza di una tabella di destinazione, la lunghezza massima della colonna non è nota.</span><span class="sxs-lookup"><span data-stu-id="2efce-214">Without a target table, the column max-length is not known.</span></span> <span data-ttu-id="2efce-215">L'attributo MAX_LENGTH limita la lunghezza massima di una colonna di testo di output e di conseguenza anche lo spazio di archiviazione allocato al valore della colonna.</span><span class="sxs-lookup"><span data-stu-id="2efce-215">The MAX_LENGTH attribute restricts the maximum length of an output character column, limiting the storage allocated for the column value.</span></span> <span data-ttu-id="2efce-216">Tale limitazione risulta particolarmente comoda quando si utilizza l'opzione BULK della funzione OPENROWSET in una clausola SELECT FROM.</span><span class="sxs-lookup"><span data-stu-id="2efce-216">This is especially convenient when using the OPENROWSET function's BULK option in a SELECT FROM clause.</span></span><br /><br /> <span data-ttu-id="2efce-217">Il valore di *m* deve essere un numero intero positivo.</span><span class="sxs-lookup"><span data-stu-id="2efce-217">The value of *m* must be a positive integer.</span></span> <span data-ttu-id="2efce-218">Per impostazione predefinita, la lunghezza massima è pari a 8000 caratteri per una colonna **char** e a 4000 caratteri per una colonna **nchar** .</span><span class="sxs-lookup"><span data-stu-id="2efce-218">By default, the maximum length is 8000 characters for a **char** column and 4000 characters for an **nchar** column.</span></span>|<span data-ttu-id="2efce-219">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2efce-219">Optional</span></span>|  
|<span data-ttu-id="2efce-220">COLLAtion **= " *`collationName`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-220">COLLATION **="*`collationName`*"**</span></span>|<span data-ttu-id="2efce-221">Questo attributo è consentito solo per i campi di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="2efce-221">COLLATION is only allowed for character fields.</span></span> <span data-ttu-id="2efce-222">Per un elenco dei nomi delle regole di confronto SQL, vedere [Nome delle regole di confronto di SQL Server &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2efce-222">For a list of the SQL collation names, see [SQL Server Collation Name &#40;Transact-SQL&#41;](/sql/t-sql/statements/sql-server-collation-name-transact-sql).</span></span>|<span data-ttu-id="2efce-223">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2efce-223">Optional</span></span>|  
|<span data-ttu-id="2efce-224">TERMINAtore **= " *`terminator`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-224">TERMINATOR **= "*`terminator`*"**</span></span>|<span data-ttu-id="2efce-225">Specifica il carattere di terminazione di un campo di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-225">This attribute specifies the terminator of a data field.</span></span> <span data-ttu-id="2efce-226">Il carattere di terminazione può essere costituito da un carattere qualsiasi,</span><span class="sxs-lookup"><span data-stu-id="2efce-226">The terminator can be any character.</span></span> <span data-ttu-id="2efce-227">univoco e non facente parte dei dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-227">The terminator must be a unique character that is not part of the data.</span></span><br /><br /> <span data-ttu-id="2efce-228">Per impostazione predefinita, il carattere di terminazione corrisponde al carattere di tabulazione, rappresentato come \t.</span><span class="sxs-lookup"><span data-stu-id="2efce-228">By default, the field terminator is the tab character (represented as \t).</span></span> <span data-ttu-id="2efce-229">Per rappresentare un segno di paragrafo, utilizzare \r\n.</span><span class="sxs-lookup"><span data-stu-id="2efce-229">To represent a paragraph mark, use \r\n.</span></span>|<span data-ttu-id="2efce-230">Viene utilizzato solo con un valore xsi:type di dati di tipo carattere, per il quale è necessario specificare questo attributo.</span><span class="sxs-lookup"><span data-stu-id="2efce-230">Used only with an xsi:type of character data, which requires this attribute</span></span>|  
  
#####  <a name="xsitype-values-of-the-field-element"></a><a name="XsiTypeValuesOfFIELD"></a> <span data-ttu-id="2efce-231">Valori xsi:type dell'elemento \<FIELD></span><span class="sxs-lookup"><span data-stu-id="2efce-231">Xsi:type values of the \<FIELD> Element</span></span>  
 <span data-ttu-id="2efce-232">Il valore xsi:type è un costrutto XML, utilizzato in modo simile a un attributo, che identifica il tipo di dati di un'istanza di un elemento.</span><span class="sxs-lookup"><span data-stu-id="2efce-232">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="2efce-233">Per informazioni sull'utilizzo di questo valore, vedere "Inserimento del valore xsi:type in un set di dati", più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="2efce-233">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="2efce-234">Il valore xsi:type dell'elemento \<FIELD> supporta i tipi di dati seguenti.</span><span class="sxs-lookup"><span data-stu-id="2efce-234">The xsi:type value of the \<FIELD> element supports the following data types.</span></span>  
  
|<span data-ttu-id="2efce-235">Valori xsi:type di \<FIELD></span><span class="sxs-lookup"><span data-stu-id="2efce-235">\<FIELD> xsi:type values</span></span>|<span data-ttu-id="2efce-236">Attributi XML obbligatori</span><span class="sxs-lookup"><span data-stu-id="2efce-236">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="2efce-237">per il tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2efce-237">for Data Type</span></span>|<span data-ttu-id="2efce-238">Attributi XML facoltativi</span><span class="sxs-lookup"><span data-stu-id="2efce-238">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="2efce-239">per il tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2efce-239">for Data Type</span></span>|  
|-------------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="2efce-240">**NativeFixed**</span><span class="sxs-lookup"><span data-stu-id="2efce-240">**NativeFixed**</span></span>|`LENGTH`|<span data-ttu-id="2efce-241">No.</span><span class="sxs-lookup"><span data-stu-id="2efce-241">None.</span></span>|  
|<span data-ttu-id="2efce-242">**NativePrefix**</span><span class="sxs-lookup"><span data-stu-id="2efce-242">**NativePrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="2efce-243">MAX_LENGTH</span><span class="sxs-lookup"><span data-stu-id="2efce-243">MAX_LENGTH</span></span>|  
|<span data-ttu-id="2efce-244">**CharFixed**</span><span class="sxs-lookup"><span data-stu-id="2efce-244">**CharFixed**</span></span>|`LENGTH`|<span data-ttu-id="2efce-245">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2efce-245">COLLATION</span></span>|  
|<span data-ttu-id="2efce-246">**NCharFixed**</span><span class="sxs-lookup"><span data-stu-id="2efce-246">**NCharFixed**</span></span>|`LENGTH`|<span data-ttu-id="2efce-247">COLLATION</span><span class="sxs-lookup"><span data-stu-id="2efce-247">COLLATION</span></span>|  
|<span data-ttu-id="2efce-248">**CharPrefix**</span><span class="sxs-lookup"><span data-stu-id="2efce-248">**CharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="2efce-249">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="2efce-249">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="2efce-250">**NCharPrefix**</span><span class="sxs-lookup"><span data-stu-id="2efce-250">**NCharPrefix**</span></span>|`PREFIX_LENGTH`|<span data-ttu-id="2efce-251">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="2efce-251">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="2efce-252">**CharTerm**</span><span class="sxs-lookup"><span data-stu-id="2efce-252">**CharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="2efce-253">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="2efce-253">MAX_LENGTH, COLLATION</span></span>|  
|<span data-ttu-id="2efce-254">**NCharTerm**</span><span class="sxs-lookup"><span data-stu-id="2efce-254">**NCharTerm**</span></span>|`TERMINATOR`|<span data-ttu-id="2efce-255">MAX_LENGTH, COLLATION</span><span class="sxs-lookup"><span data-stu-id="2efce-255">MAX_LENGTH, COLLATION</span></span>|  
  
 <span data-ttu-id="2efce-256">Per altre informazioni sui tipi di dati di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2efce-256">For more information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
####  <a name="attributes-of-the-column-element"></a><a name="AttrOfColumnElement"></a> <span data-ttu-id="2efce-257">Attributi dell'elemento \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="2efce-257">Attributes of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="2efce-258">Questa sezione descrive gli attributi dell'elemento \<COLUMN>, riepilogati nella sintassi dello schema seguente:</span><span class="sxs-lookup"><span data-stu-id="2efce-258">This section describes the attributes of the \<COLUMN> element, which are summarized in the following schema syntax:</span></span>  
  
 <span data-ttu-id="2efce-259">\<COLUMN</span><span class="sxs-lookup"><span data-stu-id="2efce-259">\<COLUMN</span></span>  
  
 <span data-ttu-id="2efce-260">SOURCE = "*fieldID*"</span><span class="sxs-lookup"><span data-stu-id="2efce-260">SOURCE = "*fieldID*"</span></span>  
  
 <span data-ttu-id="2efce-261">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="2efce-261">NAME = "*columnName*"</span></span>  
  
 <span data-ttu-id="2efce-262">xsi:type = "*columnType*"</span><span class="sxs-lookup"><span data-stu-id="2efce-262">xsi:type = "*columnType*"</span></span>  
  
 <span data-ttu-id="2efce-263">[ LENGTH = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="2efce-263">[ LENGTH = "*n*" ]</span></span>  
  
 <span data-ttu-id="2efce-264">[ PRECISION = "*n*" ]</span><span class="sxs-lookup"><span data-stu-id="2efce-264">[ PRECISION = "*n*" ]</span></span>  
  
 <span data-ttu-id="2efce-265">[ SCALE = "*value*" ]</span><span class="sxs-lookup"><span data-stu-id="2efce-265">[ SCALE = "*value*" ]</span></span>  
  
 <span data-ttu-id="2efce-266">[ NULLABLE = { "YES"</span><span class="sxs-lookup"><span data-stu-id="2efce-266">[ NULLABLE = { "YES"</span></span>  
  
 <span data-ttu-id="2efce-267">"NO" } ]</span><span class="sxs-lookup"><span data-stu-id="2efce-267">"NO" } ]</span></span>  
  
 />  
  
 <span data-ttu-id="2efce-268">Per eseguire il mapping di un campo a una colonna nella tabella di destinazione vengono utilizzati gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2efce-268">A field is mapped to a column in the target table using the following attributes:</span></span>  
  
|<span data-ttu-id="2efce-269">Attributo COLUMN</span><span class="sxs-lookup"><span data-stu-id="2efce-269">COLUMN Attribute</span></span>|<span data-ttu-id="2efce-270">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2efce-270">Description</span></span>|<span data-ttu-id="2efce-271">Facoltativo /</span><span class="sxs-lookup"><span data-stu-id="2efce-271">Optional /</span></span><br /><br /> <span data-ttu-id="2efce-272">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="2efce-272">Required</span></span>|  
|----------------------|-----------------|------------------------------|  
|<span data-ttu-id="2efce-273">SOURCE **= " *`fieldID`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-273">SOURCE **="*`fieldID`*"**</span></span>|<span data-ttu-id="2efce-274">Specifica l'ID del campo di cui eseguire il mapping alla colonna.</span><span class="sxs-lookup"><span data-stu-id="2efce-274">Specifies the ID of the field being mapped to the column.</span></span><br /><br /> <span data-ttu-id="2efce-275"><colonna Source **= " *`fieldID`* "**/> esegue il mapping a <Field ID **= " *`fieldID`* "**/></span><span class="sxs-lookup"><span data-stu-id="2efce-275"><COLUMN SOURCE **="*`fieldID`*"**/> maps to <FIELD ID **="*`fieldID`*"**/></span></span>|<span data-ttu-id="2efce-276">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="2efce-276">Required</span></span>|  
|<span data-ttu-id="2efce-277">NAME = "*columnName*"</span><span class="sxs-lookup"><span data-stu-id="2efce-277">NAME = "*columnName*"</span></span>|<span data-ttu-id="2efce-278">Specifica il nome della colonna del set di righe rappresentato dal file di formato.</span><span class="sxs-lookup"><span data-stu-id="2efce-278">Specifies the name of the column in the row set represented by the format file.</span></span> <span data-ttu-id="2efce-279">Viene utilizzato per identificare la colonna nel set dei risultati e non corrisponde necessariamente al nome di colonna utilizzato nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2efce-279">This column name is used to identify the column in the result set, and it need not correspond to the column name used in the target table.</span></span>|<span data-ttu-id="2efce-280">Obbligatoria</span><span class="sxs-lookup"><span data-stu-id="2efce-280">Required</span></span>|  
|<span data-ttu-id="2efce-281">xsi **:** Type **= " *`ColumnType`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-281">xsi **:** type **="*`ColumnType`*"**</span></span>|<span data-ttu-id="2efce-282">Costrutto XML, utilizzato in modo simile a un attributo, che identifica il tipo di dati dell'istanza dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2efce-282">This is an XML construct (used like an attribute) that identifies the data type of the instance of the element.</span></span> <span data-ttu-id="2efce-283">Il valore di *ColumnType* determina gli attributi opzionali, riportati di seguito, necessari in un'istanza specifica.</span><span class="sxs-lookup"><span data-stu-id="2efce-283">The value of *ColumnType* determines which of the optional attributes (below) you need in a given instance.</span></span><br /><br /> <span data-ttu-id="2efce-284">Nota: i valori possibili di *ColumnType* e i relativi attributi associati sono elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2efce-284">Note: The possible values of *ColumnType* and their associated attributes are listed in the next table.</span></span>|<span data-ttu-id="2efce-285">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="2efce-285">Optional</span></span>|  
|<span data-ttu-id="2efce-286">LUNGHEZZA **= " *`n`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-286">LENGTH **="*`n`*"**</span></span>|<span data-ttu-id="2efce-287">Definisce la lunghezza per un'istanza di un tipo di dati a lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="2efce-287">Defines the length for an instance of a fixed-length data type.</span></span> <span data-ttu-id="2efce-288">Viene utilizzato solo quanto il valore xsi:type corrisponde a un tipo di dati string.</span><span class="sxs-lookup"><span data-stu-id="2efce-288">LENGTH is used only when the xsi:type is a string data type.</span></span><br /><br /> <span data-ttu-id="2efce-289">Il valore di *n* deve essere un numero intero positivo.</span><span class="sxs-lookup"><span data-stu-id="2efce-289">The value of *n* must be a positive integer.</span></span>|<span data-ttu-id="2efce-290">Facoltativo (disponibile solo se il valore xsi:type corrisponde a un tipo di dati string)</span><span class="sxs-lookup"><span data-stu-id="2efce-290">Optional (available only if the xsi:type is a string data type)</span></span>|  
|<span data-ttu-id="2efce-291">PRECISION **="*`n`*"**</span><span class="sxs-lookup"><span data-stu-id="2efce-291">PRECISION **="*`n`*"**</span></span>|<span data-ttu-id="2efce-292">Indica il numero di cifre in un numero.</span><span class="sxs-lookup"><span data-stu-id="2efce-292">Indicates the number of digits in a number.</span></span> <span data-ttu-id="2efce-293">Il numero 123,45, ad esempio, ha una precisione di 5.</span><span class="sxs-lookup"><span data-stu-id="2efce-293">For example, the number 123.45 has a precision of 5.</span></span><br /><br /> <span data-ttu-id="2efce-294">Il valore deve essere un numero intero positivo.</span><span class="sxs-lookup"><span data-stu-id="2efce-294">The value must be a positive integer.</span></span>|<span data-ttu-id="2efce-295">Facoltativo (disponibile solo se il valore xsi:type corrisponde a un tipo di dati numerico variabile)</span><span class="sxs-lookup"><span data-stu-id="2efce-295">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="2efce-296">SCALE **= " *`int`* "**</span><span class="sxs-lookup"><span data-stu-id="2efce-296">SCALE **="*`int`*"**</span></span>|<span data-ttu-id="2efce-297">Indica il numero di cifre a destra della virgola decimale in un numero.</span><span class="sxs-lookup"><span data-stu-id="2efce-297">Indicates the number of digits to the right of the decimal point in a number.</span></span> <span data-ttu-id="2efce-298">Il numero 123,45, ad esempio, ha una scala di 2.</span><span class="sxs-lookup"><span data-stu-id="2efce-298">For example, the number 123.45 has a scale of 2.</span></span><br /><br /> <span data-ttu-id="2efce-299">Il valore deve essere un numero intero.</span><span class="sxs-lookup"><span data-stu-id="2efce-299">The value must be an integer.</span></span>|<span data-ttu-id="2efce-300">Facoltativo (disponibile solo se il valore xsi:type corrisponde a un tipo di dati numerico variabile)</span><span class="sxs-lookup"><span data-stu-id="2efce-300">Optional (available only if the xsi:type is a variable-number data type)</span></span>|  
|<span data-ttu-id="2efce-301">NULLABLE **=** { **"** YES **"**</span><span class="sxs-lookup"><span data-stu-id="2efce-301">NULLABLE **=** { **"** YES **"**</span></span><br /><br /> <span data-ttu-id="2efce-302">**"** NO **"** }</span><span class="sxs-lookup"><span data-stu-id="2efce-302">**"** NO **"** }</span></span>|<span data-ttu-id="2efce-303">Indica se una colonna supporta o meno valori NULL.</span><span class="sxs-lookup"><span data-stu-id="2efce-303">Indicates whether a column can assume NULL values.</span></span> <span data-ttu-id="2efce-304">Questo attributo è completamente indipendente da FIELDS.</span><span class="sxs-lookup"><span data-stu-id="2efce-304">This attribute is completely independent of FIELDS.</span></span> <span data-ttu-id="2efce-305">Se, tuttavia, una colonna non ammette valori Null e il valore del campo è NULL, ovvero non è stato specificato alcun valore, verrà restituito un errore di run-time.</span><span class="sxs-lookup"><span data-stu-id="2efce-305">However, if a column is not NULLABLE and field specifies NULL (by not specifying any value), a run-time error results.</span></span><br /><br /> <span data-ttu-id="2efce-306">L'attributo NULLABLE viene utilizzato solo per un'istruzione SELECT FROM OPENROWSET(BULK...) semplice.</span><span class="sxs-lookup"><span data-stu-id="2efce-306">The NULLABLE attribute is used only if you do a plain SELECT FROM OPENROWSET(BULK...) statement.</span></span>|<span data-ttu-id="2efce-307">Facoltativo (disponibile per qualsiasi tipo di dati)</span><span class="sxs-lookup"><span data-stu-id="2efce-307">Optional (available for any data type)</span></span>|  
  
#####  <a name="xsitype-values-of-the-column-element"></a><a name="XsiTypeValuesOfCOLUMN"></a> <span data-ttu-id="2efce-308">Valori xsi:type dell'elemento \<COLUMN></span><span class="sxs-lookup"><span data-stu-id="2efce-308">Xsi:type values of the \<COLUMN> Element</span></span>  
 <span data-ttu-id="2efce-309">Il valore xsi:type è un costrutto XML, utilizzato in modo simile a un attributo, che identifica il tipo di dati di un'istanza di un elemento.</span><span class="sxs-lookup"><span data-stu-id="2efce-309">The xsi:type value is an XML construct (used like an attribute) that identifies the data type of an instance of an element.</span></span> <span data-ttu-id="2efce-310">Per informazioni sull'utilizzo di questo valore, vedere "Inserimento del valore xsi:type in un set di dati", più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="2efce-310">For information on using the "Putting the xsi:type Value into a Data Set," later in this section.</span></span>  
  
 <span data-ttu-id="2efce-311">L'elemento \<COLUMN> supporta i tipi di dati SQL nativi, come descritto di seguito:</span><span class="sxs-lookup"><span data-stu-id="2efce-311">The \<COLUMN> element supports native SQL data types, as follows:</span></span>  
  
|<span data-ttu-id="2efce-312">Categoria del tipo</span><span class="sxs-lookup"><span data-stu-id="2efce-312">Type Category</span></span>|<span data-ttu-id="2efce-313">\<COLUMN> Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="2efce-313">\<COLUMN> Data Types</span></span>|<span data-ttu-id="2efce-314">Attributi XML obbligatori</span><span class="sxs-lookup"><span data-stu-id="2efce-314">Required XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="2efce-315">per il tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2efce-315">for Data Type</span></span>|<span data-ttu-id="2efce-316">Attributi XML facoltativi</span><span class="sxs-lookup"><span data-stu-id="2efce-316">Optional XML Attribute(s)</span></span><br /><br /> <span data-ttu-id="2efce-317">per il tipo di dati</span><span class="sxs-lookup"><span data-stu-id="2efce-317">for Data Type</span></span>|  
|-------------------|---------------------------|---------------------------------------------------|---------------------------------------------------|  
|<span data-ttu-id="2efce-318">Correzione</span><span class="sxs-lookup"><span data-stu-id="2efce-318">Fixed</span></span>|<span data-ttu-id="2efce-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT` e `SQLUNIQUEID`</span><span class="sxs-lookup"><span data-stu-id="2efce-319">`SQLBIT`, `SQLTINYINT`, `SQLSMALLINT`, `SQLINT`, `SQLBIGINT`, `SQLFLT4`, `SQLFLT8`, `SQLDATETIME`, `SQLDATETIM4`, `SQLDATETIM8`, `SQLMONEY`, `SQLMONEY4`, `SQLVARIANT`, and `SQLUNIQUEID`</span></span>|<span data-ttu-id="2efce-320">No.</span><span class="sxs-lookup"><span data-stu-id="2efce-320">None.</span></span>|<span data-ttu-id="2efce-321">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2efce-321">NULLABLE</span></span>|  
|<span data-ttu-id="2efce-322">Numero variabile</span><span class="sxs-lookup"><span data-stu-id="2efce-322">Variable Number</span></span>|<span data-ttu-id="2efce-323">`SQLDECIMAL` e `SQLNUMERIC`</span><span class="sxs-lookup"><span data-stu-id="2efce-323">`SQLDECIMAL` and `SQLNUMERIC`</span></span>|<span data-ttu-id="2efce-324">No.</span><span class="sxs-lookup"><span data-stu-id="2efce-324">None.</span></span>|<span data-ttu-id="2efce-325">NULLABLE, PRECISION, SCALE</span><span class="sxs-lookup"><span data-stu-id="2efce-325">NULLABLE, PRECISION, SCALE</span></span>|  
|<span data-ttu-id="2efce-326">LOB</span><span class="sxs-lookup"><span data-stu-id="2efce-326">LOB</span></span>|<span data-ttu-id="2efce-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT` e `SQLUDT`</span><span class="sxs-lookup"><span data-stu-id="2efce-327">`SQLIMAGE`, `CharLOB`, `SQLTEXT`, and `SQLUDT`</span></span>|<span data-ttu-id="2efce-328">No.</span><span class="sxs-lookup"><span data-stu-id="2efce-328">None.</span></span>|<span data-ttu-id="2efce-329">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2efce-329">NULLABLE</span></span>|  
|<span data-ttu-id="2efce-330">Character LOB</span><span class="sxs-lookup"><span data-stu-id="2efce-330">Character LOB</span></span>|`SQLNTEXT`|<span data-ttu-id="2efce-331">No.</span><span class="sxs-lookup"><span data-stu-id="2efce-331">None.</span></span>|<span data-ttu-id="2efce-332">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="2efce-332">NULLABLE</span></span>|  
|<span data-ttu-id="2efce-333">Stringa binaria</span><span class="sxs-lookup"><span data-stu-id="2efce-333">Binary string</span></span>|<span data-ttu-id="2efce-334">`SQLBINARY` e `SQLVARYBIN`</span><span class="sxs-lookup"><span data-stu-id="2efce-334">`SQLBINARY` and `SQLVARYBIN`</span></span>|<span data-ttu-id="2efce-335">No.</span><span class="sxs-lookup"><span data-stu-id="2efce-335">None.</span></span>|<span data-ttu-id="2efce-336">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="2efce-336">NULLABLE, LENGTH</span></span>|  
|<span data-ttu-id="2efce-337">Stringa di caratteri</span><span class="sxs-lookup"><span data-stu-id="2efce-337">Character string</span></span>|<span data-ttu-id="2efce-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR` e `SQLNVARCHAR`</span><span class="sxs-lookup"><span data-stu-id="2efce-338">`SQLCHAR`, `SQLVARYCHAR`, `SQLNCHAR`, and `SQLNVARCHAR`</span></span>|<span data-ttu-id="2efce-339">No.</span><span class="sxs-lookup"><span data-stu-id="2efce-339">None.</span></span>|<span data-ttu-id="2efce-340">NULLABLE, LENGTH</span><span class="sxs-lookup"><span data-stu-id="2efce-340">NULLABLE, LENGTH</span></span>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2efce-341">Per eseguire l'esportazione o l'importazione bulk di dati SQLXML, utilizzare uno dei tipi di dati seguenti nel file di formato: SQLCHAR o SQLVARYCHAR (i dati vengono inviati nella tabella codici del client o nella tabella codici implicita nelle regole di confronto), SQLNCHAR o SQLNVARCHAR (i dati vengono inviati come Unicode) oppure SQLBINARY o SQLVARYBIN (i dati vengono inviati senza conversione).</span><span class="sxs-lookup"><span data-stu-id="2efce-341">To bulk export or import SQLXML data, use one of the following data types in your format file: SQLCHAR or SQLVARYCHAR (the data is sent in the client code page or in the code page implied by the collation), SQLNCHAR or SQLNVARCHAR (the data is sent as Unicode), or SQLBINARY or SQLVARYBIN (the data is sent without any conversion).</span></span>  
  
 <span data-ttu-id="2efce-342">Per altre informazioni sui tipi di dati di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vedere [Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2efce-342">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
###  <a name="how-bulk-import-uses-the-row-element"></a><a name="HowUsesROW"></a> <span data-ttu-id="2efce-343">Uso dell'elemento \<ROW> nell'importazione in blocco</span><span class="sxs-lookup"><span data-stu-id="2efce-343">How Bulk Import Uses the \<ROW> Element</span></span>  
 <span data-ttu-id="2efce-344">L'elemento \<ROW> viene ignorato in alcuni contesti.</span><span class="sxs-lookup"><span data-stu-id="2efce-344">The \<ROW> element is ignored in some contexts.</span></span> <span data-ttu-id="2efce-345">L'elemento \<ROW> può influire su un'operazione di importazione in blocco a seconda della modalità con cui viene eseguita l'operazione:</span><span class="sxs-lookup"><span data-stu-id="2efce-345">Whether the \<ROW> element affects a bulk-import operation depends on how the operation is performed:</span></span>  
  
-   <span data-ttu-id="2efce-346">Comando **bcp**</span><span class="sxs-lookup"><span data-stu-id="2efce-346">the **bcp** command</span></span>  
  
     <span data-ttu-id="2efce-347">Quando i dati vengono caricati in una tabella di destinazione, **bcp** ignora il componente \<ROW>.</span><span class="sxs-lookup"><span data-stu-id="2efce-347">When data is loaded into a target table, **bcp** ignores the \<ROW> component.</span></span> <span data-ttu-id="2efce-348">e **bcp** carica i dati in base ai tipi di colonna della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2efce-348">Instead, **bcp** loads the data based on the column types of the target table.</span></span>  
  
-   [!INCLUDE[tsql](../../../includes/tsql-md.md)] <span data-ttu-id="2efce-349">Istruzioni (provider bulk per set di righe di BULK INSERT e OPENROWSET)</span><span class="sxs-lookup"><span data-stu-id="2efce-349">statements (BULK INSERT and OPENROWSET's Bulk rowset provider)</span></span>  
  
     <span data-ttu-id="2efce-350">Durante l'importazione in blocco dei dati in una tabella, le istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] usano il componente \<ROW> per generare il set di righe di input.</span><span class="sxs-lookup"><span data-stu-id="2efce-350">When bulk importing data into a table, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements use the \<ROW> component to generate the input rowset.</span></span> <span data-ttu-id="2efce-351">Le istruzioni [!INCLUDE[tsql](../../../includes/tsql-md.md)] eseguono anche le conversioni appropriate dei tipi sulla base dei tipi di colonna specificati in \<ROW> e della colonna corrispondente nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2efce-351">Also, [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements perform appropriate type conversions based on the column types specified under \<ROW> and the corresponding column in the target table.</span></span> <span data-ttu-id="2efce-352">Se i tipi di colonna specificati nel file di formato e quelli della tabella di destinazione non corrispondono, verrà eseguita un'ulteriore conversione dei tipi.</span><span class="sxs-lookup"><span data-stu-id="2efce-352">If a mismatch exists between column types as specified in the format file and in the target table, an extra type conversion occurs.</span></span> <span data-ttu-id="2efce-353">Questa conversione supplementare può comportare alcune discrepanze, ovvero mancanza di precisione, nel comportamento del provider bulk per set di righe di BULK INSERT o OPENROWSET rispetto a **bcp**.</span><span class="sxs-lookup"><span data-stu-id="2efce-353">This extra type conversion may lead to some discrepancy (that is, a loss of precision) in behavior in BULK INSERT or OPENROWSET's Bulk rowset provider as compared to **bcp**.</span></span>  
  
     <span data-ttu-id="2efce-354">Le informazioni presenti nell'elemento \<ROW> consentono di costruire una riga senza richiedere altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="2efce-354">The information in the \<ROW> element allows a row to be constructed without requiring any additional information.</span></span> <span data-ttu-id="2efce-355">È quindi possibile generare un set di righe usando un'istruzione SELECT (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span><span class="sxs-lookup"><span data-stu-id="2efce-355">For this reason, you can generate a rowset using a SELECT statement (SELECT \* FROM OPENROWSET(BULK *datafile* FORMATFILE=*xmlformatfile*).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2efce-356">La clausola OPENROWSET BULK richiede un file di formato. Si noti che la conversione da un tipo di dati del campo al tipo di dati di una colonna è disponibile solo con un file di formato XML.</span><span class="sxs-lookup"><span data-stu-id="2efce-356">The OPENROWSET BULK clause requires a format file (note that converting from the data type of the field to the data type of a column is available only with an XML format file).</span></span>  
  
###  <a name="how-bulk-import-uses-the-column-element"></a><a name="HowUsesColumn"></a> <span data-ttu-id="2efce-357">Uso dell'elemento \<COLUMN> nell'importazione in blocco</span><span class="sxs-lookup"><span data-stu-id="2efce-357">How Bulk Import Uses the \<COLUMN> Element</span></span>  
 <span data-ttu-id="2efce-358">Per consentire l'importazione in blocco dei dati in una tabella, gli elementi \<COLUMN> di un file di formato eseguono il mapping di un campo del file di dati alle colonne della tabella specificando:</span><span class="sxs-lookup"><span data-stu-id="2efce-358">For bulk importing data into a table, the \<COLUMN> elements in a format file map a data-file field to table columns by specifying:</span></span>  
  
-   <span data-ttu-id="2efce-359">La posizione di ogni campo all'interno di una riga del file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-359">The position of each field within a row in the data file.</span></span>  
  
-   <span data-ttu-id="2efce-360">Il tipo di colonna utilizzata per la conversione del tipo di dati del campo nel tipo di dati della colonna desiderato.</span><span class="sxs-lookup"><span data-stu-id="2efce-360">The column type, which is used to convert the field data type to the desired column data type.</span></span>  
  
 <span data-ttu-id="2efce-361">In caso di assenza di mapping delle colonne a un campo, quest'ultimo non verrà copiato nella riga o nelle righe generate.</span><span class="sxs-lookup"><span data-stu-id="2efce-361">If no column is mapped to a field, the field is not copied into the generated row(s).</span></span> <span data-ttu-id="2efce-362">Questo comportamento consente a un file di dati di generare righe con diverse colonne e in diverse tabelle.</span><span class="sxs-lookup"><span data-stu-id="2efce-362">This behavior allows a data file to generate rows with different columns (in different tables).</span></span>  
  
 <span data-ttu-id="2efce-363">Analogamente, per consentire l'esportazione in blocco dei dati di una tabella, ogni \<COLUMN> del file di formato esegue il mapping della colonna dalla riga della tabella di input al campo corrispondente del file di dati di output.</span><span class="sxs-lookup"><span data-stu-id="2efce-363">Similarly, for bulk exporting data from a table, each \<COLUMN> in the format file maps the column from the input table row to its corresponding field in the output data file.</span></span>  
  
###  <a name="putting-the-xsitype-value-into-a-data-set"></a><a name="PutXsiTypeValueIntoDataSet"></a> <span data-ttu-id="2efce-364">Inserimento del valore xsi:type in un set di dati</span><span class="sxs-lookup"><span data-stu-id="2efce-364">Putting the xsi:type Value into a Data Set</span></span>  
 <span data-ttu-id="2efce-365">Quando per la convalida di un documento XML si utilizza il linguaggio XML Schema Definition (XSD), il valore xsi:type non viene inserito nel set di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-365">When an XML document is validated through the XML Schema Definition (XSD) language, the xsi:type value is not put into the data set.</span></span> <span data-ttu-id="2efce-366">Per inserire le informazioni relative al valore xsi:type nel set di dati, è tuttavia possibile caricare il file di formato XML in un documento XML, ad esempio `myDoc`, come illustrato nel frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2efce-366">However, you can put the xsi:type information into the data set by loading the XML format file into an XML document (for example, `myDoc`), as illustrated in the following code snippet:</span></span>  
  
```  
...;  
myDoc.LoadXml(xmlFormat);  
XmlNodeList ColumnList = myDoc.GetElementsByTagName("COLUMN");  
for(int i=0;i<ColumnList.Count;i++)  
{  
   Console.Write("COLUMN: xsi:type=" +ColumnList[i].Attributes["type",  
      "http://www.w3.org/2001/XMLSchema-instance"].Value+"\n");  
}  
```  
  
##  <a name="sample-xml-format-files"></a><a name="SampleXmlFFs"></a> <span data-ttu-id="2efce-367">File di formato XML di esempio</span><span class="sxs-lookup"><span data-stu-id="2efce-367">Sample XML Format Files</span></span>  
 <span data-ttu-id="2efce-368">In questa sezione sono vengono fornite informazioni sull'utilizzo dei file di formato XML in una vasta gamma di situazioni, incluso un esempio relativo a [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2efce-368">This section contains information on using XML format files in a variety of cases, including an [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2efce-369">Nei file di dati degli esempi seguenti `<tab>` indica un carattere di tabulazione e `<return>` indica un ritorno a capo.</span><span class="sxs-lookup"><span data-stu-id="2efce-369">In the data files shown in the following examples, `<tab>` indicates a tab character in a data file, and `<return>` indicates a carriage return.</span></span>  
  

  
> [!NOTE]  
>  <span data-ttu-id="2efce-370">Per informazioni su come creare file di formato, vedere [Creare un file di formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2efce-370">For information about how to create format files, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="a-ordering-character-data-fields-the-same-as-table-columns"></a><a name="OrderCharFieldsSameAsCols"></a> <span data-ttu-id="2efce-371">A.</span><span class="sxs-lookup"><span data-stu-id="2efce-371">A.</span></span> <span data-ttu-id="2efce-372">Ordinamento dei campi dati di tipo carattere identico a quello delle colonne della tabella</span><span class="sxs-lookup"><span data-stu-id="2efce-372">Ordering character-data fields the same as table columns</span></span>  
 <span data-ttu-id="2efce-373">Nell'esempio seguente viene illustrato un file di formato XML che descrive un file di dati contenente tre campi dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="2efce-373">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="2efce-374">Il file di formato esegue il mapping tra il file di dati e una tabella che contiene tre colonne.</span><span class="sxs-lookup"><span data-stu-id="2efce-374">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="2efce-375">Tra i campi dati e le colonne della tabella esiste una corrispondenza di tipo uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="2efce-375">The data fields correspond one-to-one with the columns of the table.</span></span>  
  
 <span data-ttu-id="2efce-376">**Tabella (riga):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="2efce-376">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="2efce-377">**File di dati (record):** Age\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="2efce-377">**Data file (record):** Age\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="2efce-378">Il file di formato XML seguente legge il file di dati e quindi la tabella.</span><span class="sxs-lookup"><span data-stu-id="2efce-378">The following XML format file reads from the data file to the table.</span></span>  
  
 <span data-ttu-id="2efce-379">Nell'elemento `<RECORD>` il file di formato rappresenta i valori dei dati di tutti e tre i campi come dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="2efce-379">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span> <span data-ttu-id="2efce-380">Per ogni campo, l'attributo `TERMINATOR` indica il carattere di terminazione che segue il valore dei dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-380">For each field, the `TERMINATOR` attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="2efce-381">Tra i campi dati e le colonne della tabella esiste una corrispondenza di tipo uno-a-uno.</span><span class="sxs-lookup"><span data-stu-id="2efce-381">The data fields correspond one-to-one with the columns of the table.</span></span> <span data-ttu-id="2efce-382">Nell'elemento `<ROW>` il file di formato esegue il mapping tra la colonna `Age` e il primo campo, la colonna `FirstName` e il secondo campo e la colonna `LastName` e il terzo campo.</span><span class="sxs-lookup"><span data-stu-id="2efce-382">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the second field, and the column `LastName` to the third field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>   
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="2" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="3" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2efce-383">Per un esempio equivalente di [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , vedere [Creare un file di formato &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2efce-383">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Create a Format File &#40;SQL Server&#41;](create-a-format-file-sql-server.md).</span></span>  
  
###  <a name="b-ordering-data-fields-and-table-columns-differently"></a><a name="OrderFieldsAndColsDifferently"></a> <span data-ttu-id="2efce-384">B.</span><span class="sxs-lookup"><span data-stu-id="2efce-384">B.</span></span> <span data-ttu-id="2efce-385">Ordinamento dei campi dati diverso da quello delle colonne della tabella</span><span class="sxs-lookup"><span data-stu-id="2efce-385">Ordering data fields and table columns differently</span></span>  
 <span data-ttu-id="2efce-386">Nell'esempio seguente viene illustrato un file di formato XML che descrive un file di dati contenente tre campi dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="2efce-386">The following example shows an XML format file that describes a data file containing three fields of character data.</span></span> <span data-ttu-id="2efce-387">Il file di formato esegue il mapping tra il file di dati e una tabella che contiene tre colonne ordinate in modo diverso rispetto ai campi del file di dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-387">The format file maps the data file to a table that contains three columns that are ordered differently from the fields of the data file.</span></span>  
  
 <span data-ttu-id="2efce-388">**Tabella (riga):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span><span class="sxs-lookup"><span data-stu-id="2efce-388">**Table (row):** Person (Age int, FirstName varchar(20), LastName varchar(30))</span></span>  
  
 <span data-ttu-id="2efce-389">**File di dati** (record): Age\<tab>Lastname\<tab>Firstname\<return></span><span class="sxs-lookup"><span data-stu-id="2efce-389">**Data file** (record): Age\<tab>Lastname\<tab>Firstname\<return></span></span>  
  
 <span data-ttu-id="2efce-390">Nell'elemento `<RECORD>` il file di formato rappresenta i valori dei dati di tutti e tre i campi come dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="2efce-390">In the `<RECORD>` element, the format file represents the data values in all three fields as character data.</span></span>  
  
 <span data-ttu-id="2efce-391">Nell'elemento `<ROW>` il file di formato esegue il mapping tra la colonna `Age` e il primo campo, la colonna `FirstName` e il terzo campo e la colonna `LastName` e il secondo campo.</span><span class="sxs-lookup"><span data-stu-id="2efce-391">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the second field.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t" MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30" COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="2" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2efce-392">Per un esempio equivalente di [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , vedere [Usare un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2efce-392">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md).</span></span>  
  
### <a name="c-omitting-a-data-field"></a><span data-ttu-id="2efce-393">C.</span><span class="sxs-lookup"><span data-stu-id="2efce-393">C.</span></span> <span data-ttu-id="2efce-394">Omissione di un campo dati</span><span class="sxs-lookup"><span data-stu-id="2efce-394">Omitting a data field</span></span>  
 <span data-ttu-id="2efce-395">Nell'esempio seguente viene illustrato un file di formato XML che descrive un file di dati contenente quattro campi dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="2efce-395">The following example shows an XML format file that describes a data file containing four fields of character data.</span></span> <span data-ttu-id="2efce-396">Il file di formato esegue il mapping tra il file di dati e una tabella che contiene tre colonne.</span><span class="sxs-lookup"><span data-stu-id="2efce-396">The format file maps the data file to a table that contains three columns.</span></span> <span data-ttu-id="2efce-397">Il secondo campo dati non corrisponde a nessuna colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="2efce-397">The second data field does not correspond to any table column.</span></span>  
  
 <span data-ttu-id="2efce-398">**Tabella (riga):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span><span class="sxs-lookup"><span data-stu-id="2efce-398">**Table (row):** Person (Age int, FirstName Varchar(20), LastName Varchar(30))</span></span>  
  
 <span data-ttu-id="2efce-399">**File di dati (record):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span><span class="sxs-lookup"><span data-stu-id="2efce-399">**Data file (record):** Age\<tab>employeeID\<tab>Firstname\<tab>Lastname\<return></span></span>  
  
 <span data-ttu-id="2efce-400">Nell'elemento `<RECORD>` il file di formato rappresenta i valori dei dati di tutti e quattro i campi come dati di tipo carattere.</span><span class="sxs-lookup"><span data-stu-id="2efce-400">In the `<RECORD>` element, the format file represents the data values in all four fields as character data.</span></span> <span data-ttu-id="2efce-401">Per ogni campo, l'attributo TERMINATOR indica il carattere di terminazione che segue il valore dei dati.</span><span class="sxs-lookup"><span data-stu-id="2efce-401">For each field, the TERMINATOR attribute indicates the terminator that follows the data value.</span></span>  
  
 <span data-ttu-id="2efce-402">Nell'elemento `<ROW>` il file di formato esegue il mapping tra la colonna `Age` e il primo campo, la colonna `FirstName` e il terzo campo e la colonna `LastName` e il quarto campo.</span><span class="sxs-lookup"><span data-stu-id="2efce-402">In the `<ROW>` element, the format file maps the column `Age` to the first field, the column `FirstName` to the third field, and the column `LastName` to the fourth field.</span></span>  
  
```  
<BCPFORMAT   
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="12"/>  
    <FIELD ID="2" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="10"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\t"   
      MAX_LENGTH="20"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
    <FIELD ID="4" xsi:type="CharTerm" TERMINATOR="\r\n"   
      MAX_LENGTH="30"   
      COLLATION="SQL_Latin1_General_CP1_CI_AS"/>  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="age" xsi:type="SQLINT"/>  
    <COLUMN SOURCE="3" NAME="firstname" xsi:type="SQLVARYCHAR"/>  
    <COLUMN SOURCE="4" NAME="lastname" xsi:type="SQLVARYCHAR"/>  
  </ROW>  
</BCPFORMAT>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="2efce-403">Per un esempio equivalente di [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] , vedere [Usare un file di formato per escludere un campo di dati &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2efce-403">For an equivalent [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] example, see [Use a Format File to Skip a Data Field &#40;SQL Server&#41;](use-a-format-file-to-skip-a-data-field-sql-server.md).</span></span>  
  
###  <a name="d-mapping-field-xsitype-to-column-xsitype"></a><a name="MapXSItype"></a> <span data-ttu-id="2efce-404">D.</span><span class="sxs-lookup"><span data-stu-id="2efce-404">D.</span></span> <span data-ttu-id="2efce-405">Mapping di \<FIELD> xsi:type a \<COLUMN> xsi:type</span><span class="sxs-lookup"><span data-stu-id="2efce-405">Mapping \<FIELD> xsi:type to \<COLUMN> xsi:type</span></span>  
 <span data-ttu-id="2efce-406">Nell'esempio seguente vengono illustrati tipi diversi di campi e i relativi mapping alle colonne.</span><span class="sxs-lookup"><span data-stu-id="2efce-406">The following example shows different types of fields and their mappings to columns.</span></span>  
  
```  
<?xml version = "1.0"?>  
<BCPFORMAT  
xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
   <RECORD>  
      <FIELD xsi:type="CharTerm" ID="C1" TERMINATOR="\t"   
            MAX_LENGTH="4"/>  
      <FIELD xsi:type="CharFixed" ID="C2" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="CharPrefix" ID="C3" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharTerm" ID="C4" TERMINATOR="\t"   
         MAX_LENGTH="4"/>  
      <FIELD xsi:type="NCharFixed" ID="C5" LENGTH="10"   
         COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NCharPrefix" ID="C6" PREFIX_LENGTH="2"   
         MAX_LENGTH="32" COLLATION="SQL_LATIN1_GENERAL_CP1_CI_AS"/>  
      <FIELD xsi:type="NativeFixed" ID="C7" LENGTH="4"/>  
   </RECORD>  
   <ROW>  
      <COLUMN SOURCE="C1" NAME="Age" xsi:type="SQLTINYINT"/>  
      <COLUMN SOURCE="C2" NAME="FirstName" xsi:type="SQLVARYCHAR"   
      LENGTH="16" NULLABLE="NO"/>  
      <COLUMN SOURCE="C3" NAME="LastName" />  
      <COLUMN SOURCE="C4" NAME="Salary" xsi:type="SQLMONEY"/>  
      <COLUMN SOURCE="C5" NAME="Picture" xsi:type="SQLIMAGE"/>  
      <COLUMN SOURCE="C6" NAME="Bio" xsi:type="SQLTEXT"/>  
      <COLUMN SOURCE="C7" NAME="Interest"xsi:type="SQLDECIMAL"   
      PRECISION="5" SCALE="3"/>  
   </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="e-mapping-xml-data-to-a-table"></a><a name="MapXMLDataToTbl"></a> <span data-ttu-id="2efce-407">E.</span><span class="sxs-lookup"><span data-stu-id="2efce-407">E.</span></span> <span data-ttu-id="2efce-408">Mapping tra i dati XML e una tabella</span><span class="sxs-lookup"><span data-stu-id="2efce-408">Mapping XML data to a table</span></span>  
 <span data-ttu-id="2efce-409">Nell'esempio seguente viene creata una tabella vuota a due colonne denominata`t_xml`in cui viene eseguito il mapping tra la prima colonna e il tipo di dati `int` e tra la seconda colonna e il tipo di dati `xml` .</span><span class="sxs-lookup"><span data-stu-id="2efce-409">The following example creates an empty two-column table (`t_xml`), in which the first column maps to the `int` data type and the second column maps to the `xml` data type.</span></span>  
  
```  
CREATE TABLE t_xml (c1 int, c2 xml)  
```  
  
 <span data-ttu-id="2efce-410">Il file di formato XML seguente carica un file di dati nella tabella `t_xml`.</span><span class="sxs-lookup"><span data-stu-id="2efce-410">The following XML format file would load a data file into table `t_xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"   
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
 <RECORD>  
  <FIELD ID="1" xsi:type="NativePrefix" PREFIX_LENGTH="1"/>  
  <FIELD ID="2" xsi:type="NCharPrefix" PREFIX_LENGTH="8"/>  
 </RECORD>  
 <ROW>  
  <COLUMN SOURCE="1" NAME="c1" xsi:type="SQLINT"/>  
  <COLUMN SOURCE="2" NAME="c2" xsi:type="SQLNCHAR"/>  
 </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="f-importing-fixed-length-or-fixed-width-fields"></a><a name="ImportFixedFields"></a> <span data-ttu-id="2efce-411">F.</span><span class="sxs-lookup"><span data-stu-id="2efce-411">F.</span></span> <span data-ttu-id="2efce-412">Importazione di campi a lunghezza fissa o a larghezza fissa</span><span class="sxs-lookup"><span data-stu-id="2efce-412">Importing fixed-length or fixed-width fields</span></span>  
 <span data-ttu-id="2efce-413">Nell'esempio seguente vengono descritti campi fissi di `10` o `6` caratteri ognuno.</span><span class="sxs-lookup"><span data-stu-id="2efce-413">The following example describes fixed fields of `10` or `6` characters each.</span></span> <span data-ttu-id="2efce-414">Il file di formato rappresenta queste lunghezze o larghezze dei campi rispettivamente come `LENGTH="10"` e `LENGTH="6"`.</span><span class="sxs-lookup"><span data-stu-id="2efce-414">The format file represents these field lengths/widths as `LENGTH="10"` and `LENGTH="6"`, respectively.</span></span> <span data-ttu-id="2efce-415">Ogni riga dei file di dati termina con una combinazione di ritorno a capo e avanzamento riga, {CR}{LF}, rappresentata nel file di formato come `TERMINATOR="\r\n"`.</span><span class="sxs-lookup"><span data-stu-id="2efce-415">Every row of the data files ends with a carriage return-line feed combination, {CR}{LF}, which the format file represents as `TERMINATOR="\r\n"`.</span></span>  
  
```  
<?xml version="1.0"?>  
<BCPFORMAT  
       xmlns="https://schemas.microsoft.com/sqlserver/2004/bulkload/format"  
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <RECORD>  
    <FIELD ID="1" xsi:type="CharFixed" LENGTH="10"/>  
    <FIELD ID="2" xsi:type="CharFixed" LENGTH="6"/>  
    <FIELD ID="3" xsi:type="CharTerm" TERMINATOR="\r\n"  
  </RECORD>  
  <ROW>  
    <COLUMN SOURCE="1" NAME="C1" xsi:type="SQLINT" />  
    <COLUMN SOURCE="2" NAME="C2" xsi:type="SQLINT" />  
  </ROW>  
</BCPFORMAT>  
```  
  
###  <a name="additional-examples"></a><a name="AdditionalExamples"></a> <span data-ttu-id="2efce-416">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="2efce-416">Additional Examples</span></span>  
 <span data-ttu-id="2efce-417">Per ulteriori esempi di file di formato XML e non XML, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2efce-417">For additional examples of both non-XML format files and XML format files, see the following topics:</span></span>  
  
-   [<span data-ttu-id="2efce-418">Utilizzo di un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-418">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="2efce-419">Utilizzo di un file di formato per escludere un campo di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-419">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="2efce-420">Utilizzo di un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-420">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="2efce-421">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="2efce-421">Related Tasks</span></span>  
  
-   [<span data-ttu-id="2efce-422">Creazione di un file di formato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-422">Create a Format File &#40;SQL Server&#41;</span></span>](create-a-format-file-sql-server.md)  
  
-   [<span data-ttu-id="2efce-423">Usare un file di formato per l'importazione in blocco dei dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-423">Use a Format File to Bulk Import Data &#40;SQL Server&#41;</span></span>](use-a-format-file-to-bulk-import-data-sql-server.md)  
  
-   [<span data-ttu-id="2efce-424">Utilizzo di un file di formato per ignorare una colonna di una tabella &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-424">Use a Format File to Skip a Table Column &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-table-column-sql-server.md)  
  
-   [<span data-ttu-id="2efce-425">Utilizzo di un file di formato per escludere un campo di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-425">Use a Format File to Skip a Data Field &#40;SQL Server&#41;</span></span>](use-a-format-file-to-skip-a-data-field-sql-server.md)  
  
-   [<span data-ttu-id="2efce-426">Utilizzo di un file di formato per eseguire il mapping tra le colonne della tabella e i campi del file di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-426">Use a Format File to Map Table Columns to Data-File Fields &#40;SQL Server&#41;</span></span>](use-a-format-file-to-map-table-columns-to-data-file-fields-sql-server.md)  
  
##  <a name="related-content"></a><a name="RelatedContent"></a> <span data-ttu-id="2efce-427">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="2efce-427">Related Content</span></span>  
 <span data-ttu-id="2efce-428">No.</span><span class="sxs-lookup"><span data-stu-id="2efce-428">None.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2efce-429">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2efce-429">See Also</span></span>  
 <span data-ttu-id="2efce-430">[Informazioni sull'importazione ed esportazione bulk di dati &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2efce-430">[Bulk Import and Export of Data &#40;SQL Server&#41;](bulk-import-and-export-of-data-sql-server.md) </span></span>  
 <span data-ttu-id="2efce-431">[Tipi di dati &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2efce-431">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="2efce-432">[File in formato non XML &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="2efce-432">[Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md) </span></span>  
 [<span data-ttu-id="2efce-433">File di formato per l'importazione o l'esportazione di dati &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2efce-433">Format Files for Importing or Exporting Data &#40;SQL Server&#41;</span></span>](format-files-for-importing-or-exporting-data-sql-server.md)  
  
  
