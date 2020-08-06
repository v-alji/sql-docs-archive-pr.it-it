---
title: Eseguire la convalida XML con Attività XML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- XML validation
- XML, validating
ms.assetid: 224fc025-c21f-4d43-aa9d-5ffac337f9b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 633a269f53c85353c956b33bff8fd3af518dad56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623410"
---
# <a name="validate-xml-with-the-xml-task"></a><span data-ttu-id="e6fa8-102">Validate XML with the XML Task</span><span class="sxs-lookup"><span data-stu-id="e6fa8-102">Validate XML with the XML Task</span></span>
  <span data-ttu-id="e6fa8-103">È possibile convalidare documenti XML e ottenere output avanzato degli errori abilitando la proprietà `ValidationDetails` dell'Attività XML.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-103">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span>

 <span data-ttu-id="e6fa8-104">L'immagine seguente mostra l' **Editor attività XML** con le impostazioni necessarie per la convalida di XML con l'output di errore completo.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-104">The following screen shot shows the **XML Task Editor** with the settings required for XML validation with rich error output.</span></span>

 <span data-ttu-id="e6fa8-105">![Proprietà delle attività XML nell'Editor attività XML](../media/xmltaskproperties.jpg "Proprietà delle attività XML nell'Editor attività XML")</span><span class="sxs-lookup"><span data-stu-id="e6fa8-105">![XML task properties in the XML Task Editor](../media/xmltaskproperties.jpg "XML task properties in the XML Task Editor")</span></span>

 <span data-ttu-id="e6fa8-106">Prima che fosse disponibile la proprietà `ValidationDetails`, la convalida XML da parte dell'Attività XML restituiva solo un risultato di tipo True o False, senza informazioni sugli errori o sulle rispettive posizioni.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-106">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="e6fa8-107">Attualmente, quando si imposta `ValidationDetails` su True, il file di output contiene informazioni dettagliate su ogni errore, inclusi il numero di riga e la posizione.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-107">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="e6fa8-108">È possibile usare questa informazione per comprendere, individuare e risolvere gli errori nei documenti XML.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-108">You can use this information to understand, locate, and fix errors in XML documents.</span></span>

 <span data-ttu-id="e6fa8-109">La funzionalità di convalida XML è facilmente scalabile per documenti XML di grandi dimensioni e un numero elevato di errori.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-109">The XML validation functionality scales easily for large XML documents and large numbers of errors.</span></span> <span data-ttu-id="e6fa8-110">Dato che il file di output è in formato XML, è possibile eseguire una query e analizzare l'output.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-110">Since the output file itself is in XML format, you can query and analyze the output.</span></span> <span data-ttu-id="e6fa8-111">Ad esempio, se l'output contiene un numero elevato di errori, è possibile raggrupparli usando un [!INCLUDE[tsql](../../../includes/tsql-md.md)] , come descritto in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-111">For example, if the output contains a large number of errors, you can group the errors by using a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query, as described in this topic.</span></span>

> [!NOTE]
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="e6fa8-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]( [!INCLUDE[ssIS](../../includes/ssis-md.md)] ) ha introdotto la `ValidationDetails` Proprietà in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-112">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="e6fa8-113">La proprietà è disponibile anche in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] e in SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-113">The property is also available in [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>

## <a name="sample-output-for-xml-thats-valid"></a><span data-ttu-id="e6fa8-114">Esempio di output per un file XML valido</span><span class="sxs-lookup"><span data-stu-id="e6fa8-114">Sample output for XML that's valid</span></span>
 <span data-ttu-id="e6fa8-115">Ecco un file di output di esempio con i risultati della convalida per un file XML valido.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-115">Here is a sample output file with validation results for a valid XML file.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>true</result>
        <errors>0</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:27:22.087</startTime>
        <endTime>2015-05-28T10:29:07.007</endTime>
        <xmlFile>d:\Temp\TestData.xml</xmlFile>
        <xsdFile>d:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages />
</root>
```

## <a name="sample-output-for-xml-thats-not-valid"></a><span data-ttu-id="e6fa8-116">Esempio di output per un file XML non valido</span><span class="sxs-lookup"><span data-stu-id="e6fa8-116">Sample output for XML that's not valid</span></span>
 <span data-ttu-id="e6fa8-117">Ecco un file di output di esempio con i risultati della convalida per un file XML che contiene un numero ridotto di errori.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-117">Here is a sample output file with validation results for an XML file that contains a small number of errors.</span></span> <span data-ttu-id="e6fa8-118">Il testo degli elementi \<error> è stato mandato a capo per migliorare la leggibilità.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-118">The text of the \<error> elements has been wrapped for readability.</span></span>

```xml

<root xmlns:ns="https://schemas.microsoft.com/xmltools/2002/xmlvalidation">
    <metadata>
        <result>false</result>
        <errors>2</errors>
        <warnings>0</warnings>
        <startTime>2015-05-28T10:45:09.538</startTime>
        <endTime>2015-05-28T10:45:09.558</endTime>
        <xmlFile>C:\Temp\TestData.xml</xmlFile>
        <xsdFile>C:\Temp\TestSchema.xsd</xsdFile>
    </metadata>
    <messages>
        <error line="5" position="26">The 'ApplicantRole' element is invalid - The value 'wer3' is invalid
    according to its datatype 'ApplicantRoleType' - The Enumeration constraint failed.</error>
        <error line="16" position="28">The 'Phone' element is invalid - The value 'we3056666666' is invalid
     according to its datatype 'phone' - The Pattern constraint failed.</error>
    </messages>
</root>
```

## <a name="analyze-xml-validation-output-with-a-transact-sql-query"></a><span data-ttu-id="e6fa8-119">Analizzare l'output della convalida XML con una query Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="e6fa8-119">Analyze XML validation output with a Transact-SQL query</span></span>
 <span data-ttu-id="e6fa8-120">Se l'output della convalida XML contiene un numero elevato di errori, è possibile usare una query di [!INCLUDE[tsql](../../../includes/tsql-md.md)] per caricare l'output in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6fa8-120">If the output of XML validation contains a large number of errors, you can use a [!INCLUDE[tsql](../../../includes/tsql-md.md)] query to load the output in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="e6fa8-121">È quindi possibile analizzare l'elenco di errori con tutte le funzionalità del linguaggio T-SQL, inclusi WHERE, GROUP BY, ORDER BY, JOIN e così via.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-121">Then you can analyze the error list with all the capabilities of the T-SQL language including WHERE, GROUP BY, ORDER BY, JOIN, and so forth.</span></span>

```sql
DECLARE @xml XML;

SELECT @xml = XmlDoc   
FROM OPENROWSET (BULK N'C:\Temp\XMLValidation_2016-02-212T10-41-00.xml', SINGLE_BLOB) AS Tab(XmlDoc);

-- Query # 1, flat list of errors
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT * FROM rs;
-- WHERE error LIKE '%whatever_string%'

-- Query # 2, count of errors grouped by the error message
-- convert to relational/rectangular
;WITH XMLNAMESPACES ('https://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS
(
SELECT col.value('@line','INT') AS line
     , col.value('@position','INT') AS position
     , col.value('.','VARCHAR(1024)') AS error
FROM @XML.nodes('/root/messages/error') AS tab(col)
)
SELECT COALESCE(error,'Total # of errors:') AS [error], COUNT(*) AS [counter]
FROM rs
GROUP BY GROUPING SETS ((error), ())
ORDER BY 2 DESC, COALESCE(error, 'Z');

```

 <span data-ttu-id="e6fa8-122">Ecco il risultato in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] della seconda query di esempio illustrata nel testo precedente.</span><span class="sxs-lookup"><span data-stu-id="e6fa8-122">Here is the result in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] of the second sample query shown in the preceding text.</span></span>

 <span data-ttu-id="e6fa8-123">![Errori XML di query su gruppo in Management Studio](../media/queryforxmlerrors.jpg "Errori XML di query su gruppo in Management Studio")</span><span class="sxs-lookup"><span data-stu-id="e6fa8-123">![Query to group XML errors in Management Studio](../media/queryforxmlerrors.jpg "Query to group XML errors in Management Studio")</span></span>

## <a name="see-also"></a><span data-ttu-id="e6fa8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6fa8-124">See Also</span></span>
 <span data-ttu-id="e6fa8-125">[XML Task](xml-task.md) [Editor attività xml attività XML &#40;pagina generale&#41;](../xml-task-editor-general-page.md)</span><span class="sxs-lookup"><span data-stu-id="e6fa8-125">[XML Task](xml-task.md) [XML Task Editor &#40;General Page&#41;](../xml-task-editor-general-page.md)</span></span>


