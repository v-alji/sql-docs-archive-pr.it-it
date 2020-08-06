---
title: Componenti jolly e convalida del contenuto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- wildcard components [XML]
- content validation [XML]
ms.assetid: ffa7d974-3645-446c-8425-f0b22b6b060a
author: rothja
ms.author: jroth
ms.openlocfilehash: 76ff2b48efb8cff0b98827fe8522405682c294e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625257"
---
# <a name="wildcard-components-and-content-validation"></a><span data-ttu-id="a81d3-102">Componenti jolly e convalida del contenuto</span><span class="sxs-lookup"><span data-stu-id="a81d3-102">Wildcard Components and Content Validation</span></span>
  <span data-ttu-id="a81d3-103">I componenti jolly vengono utilizzati per consentire una maggiore flessibilità riguardo agli elementi che è possibile includere in un modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="a81d3-103">Wildcard components are used to increase flexibility in what is allowed to appear in a content model.</span></span> <span data-ttu-id="a81d3-104">Tali componenti vengono supportati nel linguaggio XSD nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a81d3-104">These components are supported in the XSD language in the following ways:</span></span>  
  
-   <span data-ttu-id="a81d3-105">Elemento componenti jolly.</span><span class="sxs-lookup"><span data-stu-id="a81d3-105">Element wildcard components.</span></span> <span data-ttu-id="a81d3-106">Sono rappresentati dall'elemento **\<xsd:any>** .</span><span class="sxs-lookup"><span data-stu-id="a81d3-106">These are represented by the **\<xsd:any>** element.</span></span>  
  
-   <span data-ttu-id="a81d3-107">Attributo componenti jolly.</span><span class="sxs-lookup"><span data-stu-id="a81d3-107">Attribute wildcard components.</span></span> <span data-ttu-id="a81d3-108">Sono rappresentati dall'elemento **\<xsd:anyAttribute>** .</span><span class="sxs-lookup"><span data-stu-id="a81d3-108">These are represented by the **\<xsd:anyAttribute>** element.</span></span>  
  
 <span data-ttu-id="a81d3-109">Entrambi gli elementi dei caratteri jolly, **\<xsd:any>** e **\<xsd:anyAttribute>** , supportano l'utilizzo di un attributo **processContents**.</span><span class="sxs-lookup"><span data-stu-id="a81d3-109">Both wildcard character elements, **\<xsd:any>** and **\<xsd:anyAttribute>**, support the use of a **processContents** attribute.</span></span> <span data-ttu-id="a81d3-110">Questo attributo consente di specificare un valore che indica il modo in cui le applicazioni XML gestiscono la convalida del contenuto di documenti associato a tali elementi dei caratteri jolly.</span><span class="sxs-lookup"><span data-stu-id="a81d3-110">This lets you specify a value that indicates how XML applications handle the validation of document content associated with these wildcard character elements.</span></span> <span data-ttu-id="a81d3-111">Valori diversi e relativo effetto:</span><span class="sxs-lookup"><span data-stu-id="a81d3-111">These are the different values and their effect:</span></span>  
  
-   <span data-ttu-id="a81d3-112">Il valore **strict** specifica che viene eseguita la convalida completa del contenuto.</span><span class="sxs-lookup"><span data-stu-id="a81d3-112">The **strict** value specifies that the contents are fully validated.</span></span>  
  
-   <span data-ttu-id="a81d3-113">Il valore **skip** specifica che non viene eseguita la convalida del contenuto.</span><span class="sxs-lookup"><span data-stu-id="a81d3-113">The **skip** value specifies that the contents are not validated.</span></span>  
  
-   <span data-ttu-id="a81d3-114">Il valore **lax** specifica che viene eseguita solo la convalida di elementi e attributi per i quali sono disponibili definizioni di schemi.</span><span class="sxs-lookup"><span data-stu-id="a81d3-114">The **lax** value specifies that only elements and attributes for which schema definitions are available are validated.</span></span>  
  
## <a name="lax-validation-and-xsanytype-elements"></a><span data-ttu-id="a81d3-115">Elementi della convalida lax e del tipo xs:anyType</span><span class="sxs-lookup"><span data-stu-id="a81d3-115">Lax Validation and xs:anyType Elements</span></span>  
 <span data-ttu-id="a81d3-116">La specifica di XML Schema utilizza la convalida **lax** per elementi del tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="a81d3-116">The XML Schema specification uses **lax** validation for elements of the **anyType** type.</span></span> <span data-ttu-id="a81d3-117">Poiché [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] non supportava la convalida di tipo lax, per gli elementi di tipo **anyType**veniva applicata la convalida di tipo strict.</span><span class="sxs-lookup"><span data-stu-id="a81d3-117">Because [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] did not support lax validation, strict validation was applied for elements of the **anyType**.</span></span> <span data-ttu-id="a81d3-118">A partire da [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], la convalida lax è supportata.</span><span class="sxs-lookup"><span data-stu-id="a81d3-118">Beginning with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], lax validation is supported.</span></span> <span data-ttu-id="a81d3-119">Il contenuto degli elementi del tipo **anyType** sarà convalidato utilizzando la convalida lax.</span><span class="sxs-lookup"><span data-stu-id="a81d3-119">Content of elements of type **anyType** will be validated using lax validation.</span></span>  
  
 <span data-ttu-id="a81d3-120">L'esempio seguente illustra la convalida lax.</span><span class="sxs-lookup"><span data-stu-id="a81d3-120">The following example illustrates the lax validation.</span></span> <span data-ttu-id="a81d3-121">L'elemento schema `e` è del tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="a81d3-121">The schema element `e` is of the **anyType** type.</span></span> <span data-ttu-id="a81d3-122">L'esempio crea variabili **xml** tipizzate e illustra la convalida lax dell'elemento di tipo **anyType** .</span><span class="sxs-lookup"><span data-stu-id="a81d3-122">The example creates typed **xml** variables and illustrates the lax validation of the element of the **anyType** type.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="http://ns">  
   <element name="e" type="anyType"/>  
   <element name="a" type="byte"/>  
   <element name="b" type="string"/>  
 </schema>'  
GO  
```  
  
 <span data-ttu-id="a81d3-123">L'esempio seguente è corretto in quanto la convalida di `<e>` ha esito positivo:</span><span class="sxs-lookup"><span data-stu-id="a81d3-123">The following example succeeds, because the validation of `<e>` is successful:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="a81d3-124">L'esempio seguente ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a81d3-124">The following example succeeds.</span></span> <span data-ttu-id="a81d3-125">L'istanza è accettata, anche se non è definito alcun elemento `<c>` nello schema:</span><span class="sxs-lookup"><span data-stu-id="a81d3-125">The instance is accepted, even though no element `<c>` is defined in the schema:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><c>Wrong</c><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="a81d3-126">L'istanza XML nell'esempio seguente è rifiutata, perché la definizione dell'elemento `<a>` non consente un valore della stringa.</span><span class="sxs-lookup"><span data-stu-id="a81d3-126">The XML instance in the following example is rejected, because the definition of the `<a>` element does not allow a string value.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>Wrong</a><b>data</b></e>'  
SELECT @var  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="a81d3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a81d3-127">See Also</span></span>  
 [<span data-ttu-id="a81d3-128">Requisiti e limitazioni per le raccolte di XML Schema nel server</span><span class="sxs-lookup"><span data-stu-id="a81d3-128">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
