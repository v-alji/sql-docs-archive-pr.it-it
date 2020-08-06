---
title: Specifica di variabili XPath in query XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], XPath variables
- XPath variables [SQLXML]
ms.assetid: c11ab816-11b8-4131-8b77-c03fe500fa10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5045831f627722f7dbb9a9189be5c48d830f2add
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623981"
---
# <a name="specifying-xpath-variables-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="e326a-102">Definizione di variabili XPath in query XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e326a-102">Specifying XPath Variables in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="e326a-103">Negli esempi seguenti viene illustrato il modo in cui passare variabili XPath in query XPath.</span><span class="sxs-lookup"><span data-stu-id="e326a-103">The following examples show how XPath variables are passed in XPath queries.</span></span> <span data-ttu-id="e326a-104">Le query XPath di questi esempi vengono specificate sullo schema di mapping contenuto in SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e326a-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="e326a-105">Per informazioni su questo schema di esempio, vedere [schema XSD con annotazioni di esempio per gli esempi XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e326a-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e326a-106">Esempi</span><span class="sxs-lookup"><span data-stu-id="e326a-106">Examples</span></span>  
  
### <a name="a-use-the-xpath-variables"></a><span data-ttu-id="e326a-107">R.</span><span class="sxs-lookup"><span data-stu-id="e326a-107">A.</span></span> <span data-ttu-id="e326a-108">Utilizzare le variabili XPath</span><span class="sxs-lookup"><span data-stu-id="e326a-108">Use the XPath variables</span></span>  
 <span data-ttu-id="e326a-109">Un modello di esempio è costituito da due query XPath.</span><span class="sxs-lookup"><span data-stu-id="e326a-109">A sample template consists of two XPath queries.</span></span> <span data-ttu-id="e326a-110">Ognuna delle query XPath accetta un parametro.</span><span class="sxs-lookup"><span data-stu-id="e326a-110">Each of the XPath queries takes one parameter.</span></span> <span data-ttu-id="e326a-111">Il modello specifica inoltre valori predefiniti per tali parametri.</span><span class="sxs-lookup"><span data-stu-id="e326a-111">The template also specifies default values for these parameters.</span></span> <span data-ttu-id="e326a-112">Se i valori dei parametri non sono specificati, vengono utilizzati i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e326a-112">The default values are used if parameter values are not specified.</span></span> <span data-ttu-id="e326a-113">In sono specificati due parametri con valori predefiniti **\<sql:header>** .</span><span class="sxs-lookup"><span data-stu-id="e326a-113">Two parameters with default values are specified in **\<sql:header>**.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='CustomerID'>1</sql:param>  
     <sql:param name='ContactID'>1</sql:param>   
  </sql:header>  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
    Customer[@CustomerID=$CustomerID]   
  </sql:xpath-query >  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
   Contact[@ContactID=$ContactID]   
  </sql:xpath-query>  
</ROOT>  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="e326a-114">Per testare la query Xpath sullo schema di mapping</span><span class="sxs-lookup"><span data-stu-id="e326a-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="e326a-115">Copiare il [codice dello schema di esempio](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e incollarlo in un file di testo.</span><span class="sxs-lookup"><span data-stu-id="e326a-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="e326a-116">Salvare il file con il nome SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e326a-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="e326a-117">Creare il modello seguente (XPathVariables.xml) e salvarlo nella directory in cui:</span><span class="sxs-lookup"><span data-stu-id="e326a-117">Create the following template (XPathVariables.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:header>  
         <sql:param name='CustomerID'>1</sql:param>  
         <sql:param name='ContactID'>1</sql:param>   
      </sql:header>  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[@CustomerID=$CustomerID]   
      </sql:xpath-query >  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
       Contact[@ContactID=$ContactID]   
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e326a-118">Il percorso di directory specificato per lo schema di mapping SampleSchema1.xml è relativo alla directory in cui è salvato il modello.</span><span class="sxs-lookup"><span data-stu-id="e326a-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e326a-119">È possibile specificare anche un percorso assoluto, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e326a-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="e326a-120">Creare e utilizzare lo script di test SQLXML 4.0 (Sqlxml4test.vbs) per eseguire il modello.</span><span class="sxs-lookup"><span data-stu-id="e326a-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="e326a-121">Per ulteriori informazioni, vedere [utilizzo di ADO per eseguire query SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e326a-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e326a-122">In questo esempio non viene passato alcun parametro.</span><span class="sxs-lookup"><span data-stu-id="e326a-122">In this example, no parameters are passed.</span></span> <span data-ttu-id="e326a-123">Vengono pertanto utilizzati i valori di parametro predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e326a-123">Therefore, the default parameter values are used.</span></span>  
  
  
