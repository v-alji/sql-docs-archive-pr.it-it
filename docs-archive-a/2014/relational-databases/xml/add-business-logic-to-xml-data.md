---
title: Aggiungere una logica di business ai dati XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- business logic [XML]
ms.assetid: 0877fb38-f1a2-43d8-86cf-4754be224dc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 5bf8e9edc36e9c420faa92f2db1a92c311194e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626581"
---
# <a name="add-business-logic-to-xml-data"></a><span data-ttu-id="dd0a7-102">Aggiunta di una logica di business ai dati XML</span><span class="sxs-lookup"><span data-stu-id="dd0a7-102">Add Business Logic to XML Data</span></span>
  <span data-ttu-id="dd0a7-103">Per aggiungere una logica di business ai dati XML è possibile procedere in vari modi:</span><span class="sxs-lookup"><span data-stu-id="dd0a7-103">Your business logic can be added to XML data in several ways:</span></span>  
  
-   <span data-ttu-id="dd0a7-104">È possibile creare vincoli a livello di riga o colonna per applicare vincoli specifici del dominio durante la modifica e l'inserimento dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-104">You can write row or column constraints to enforce domain-specific constraints during insertion and modification of XML data.</span></span>  
  
-   <span data-ttu-id="dd0a7-105">È possibile creare sulla colonna XML un trigger che viene attivato all'inserimento o all'aggiornamento dei valori nella colonna.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-105">You can write a trigger on the XML column that fires when you insert or update values in the column.</span></span> <span data-ttu-id="dd0a7-106">Tale trigger può contenere regole di convalida specifiche del dominio o popolare tabelle di proprietà.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-106">The trigger can contain domain-specific validation rules or populate property tables.</span></span>  
  
-   <span data-ttu-id="dd0a7-107">Il motore di database include la possibilità di eseguire codice gestito.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-107">The Database Engine includes the ability execute managed code.</span></span> <span data-ttu-id="dd0a7-108">È possibile usare l'integrazione con CLR (Common Language Runtime) per creare funzioni in codice gestito a cui passare valori XML e usare le funzionalità di elaborazione XML offerte dallo spazio dei nomi System.Xml.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-108">You can use this common language runtime (CLR) integration to write functions in managed code to which you pass XML values, and use XML processing capabilities provided by the System.Xml namespace.</span></span> <span data-ttu-id="dd0a7-109">Ad esempio è possibile applicare la trasformazione XSL ai dati XML.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-109">An example is to apply XSL transformation to XML data.</span></span> <span data-ttu-id="dd0a7-110">In alternativa è possibile deserializzare il valore XML in una o più classi gestite ed utilizzare il codice gestito per agire su tali classi.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-110">Alternatively, you can deserialize the XML into one or more managed classes and operate on them by using managed code.</span></span>  
  
-   <span data-ttu-id="dd0a7-111">È possibile creare funzioni e stored procedure Transact-SQL che avviano l'elaborazione della colonna XML in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-111">You can write Transact-SQL stored procedures and functions that start the processing on the XML column for your business needs.</span></span>  
  
## <a name="example-applying-xsl-transformation"></a><span data-ttu-id="dd0a7-112">Esempio: Applicazione della trasformazione XSL</span><span class="sxs-lookup"><span data-stu-id="dd0a7-112">Example: Applying XSL Transformation</span></span>  
 <span data-ttu-id="dd0a7-113">Si consideri una funzione CLR **TransformXML ()** che accetta un' `xml` istanza del tipo di dati e una trasformazione XSL archiviata in un file, applica la trasformazione ai dati XML e quindi restituisce il codice XML trasformato nel risultato.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-113">Consider a CLR function **TransformXml()** that accepts an `xml` data type instance and an XSL transformation stored in a file, applies the transformation to the XML data, and then returns the transformed XML in the result.</span></span> <span data-ttu-id="dd0a7-114">Di seguito è riportato lo scheletro della funzione scritta in C#:</span><span class="sxs-lookup"><span data-stu-id="dd0a7-114">Following is a skeleton function that is written in C#:</span></span>  
  
```  
public static SqlXml TransformXml (SqlXml XmlData, string xslPath) {  
   // Load XSL transformation  
   XslCompiledTransform xform = new XslCompiledTransform();  
   XPathDocument xslDoc = new XPathDocument (xslPath);  
   xform.Load(xslDoc);  
  
   // Load XML data   
   XPathDocument xDoc = new XPathDocument (XmlData.CreateReader());  
  
   // Return the transformed value  
   MemoryStream xsltResult = new MemoryStream();  
   xform.Transform(xDoc, null, xsltResult);  
   SqlXml retSqlXml = new SqlXml(xsltResult);  
   return (retSqlXml);  
}   
```  
  
 <span data-ttu-id="dd0a7-115">Dopo aver registrato l'assembly e creato la funzione [!INCLUDE[tsql](../../includes/tsql-md.md)] definita dall'utente **SqlXslTransform()** corrispondente a **TransformXml()** è possibile chiamare la funzione da Transact-SQL come illustrato nella query seguente:</span><span class="sxs-lookup"><span data-stu-id="dd0a7-115">After the assembly is registered and a user-defined [!INCLUDE[tsql](../../includes/tsql-md.md)] function is created, **SqlXslTransform()** corresponding to **TransformXml()**, the function can be invoked from Transact-SQL as shown in the following query:</span></span>  
  
```  
SELECT SqlXslTransform (xCol, 'C:\MyFile\xsltransform.xsl')  
FROM    T  
WHERE  xCol.exist('/book/title/text()[contains(.,"custom")]') =1;  
```  
  
 <span data-ttu-id="dd0a7-116">Il risultato della query contiene un set di righe con il valore XML trasformato.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-116">The query result contains a rowset of the transformed XML.</span></span>  
  
 <span data-ttu-id="dd0a7-117">L'integrazione di CLR in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estende le possibilità di scomporre dati XML in tabelle o di promuovere le proprietà, nonché di eseguire query sui dati XML usando classi gestite nello spazio dei nomi System.Xml.</span><span class="sxs-lookup"><span data-stu-id="dd0a7-117">The CLR integration into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expands the possibilities for decomposing XML data into tables or property promotion, and querying XML data by using managed classes in the System.Xml namespace.</span></span> <span data-ttu-id="dd0a7-118">Per altre informazioni, vedere [Dati XML &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd0a7-118">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
  
