---
title: Vincolo di attribuzione di particelle univoche | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
f1_keywords:
- unique particle attribution
helpviewer_keywords:
- schema collections [SQL Server], unique particle attribution
- XML schema collections [SQL Server], unique particle attribution
- UPA constraint rule
- unique particle attribution constraint rule
ms.assetid: 6bb879e9-a5ee-402e-94e4-fe8cec5966b0
author: rothja
ms.author: jroth
ms.openlocfilehash: 7416aa4ea14539f3bf633207768783aa439ec818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711779"
---
# <a name="unique-particle-attribution-constraint"></a><span data-ttu-id="870af-102">Vincolo di attribuzione di particelle univoche</span><span class="sxs-lookup"><span data-stu-id="870af-102">Unique Particle Attribution Constraint</span></span>
  <span data-ttu-id="870af-103">In XSD i modelli di contenuto complessi sono soggetti alla regola del vincolo di attribuzione di particelle univoche (UPA, Unique Particle Attribution).</span><span class="sxs-lookup"><span data-stu-id="870af-103">In XSD, complex content models are constrained by the unique particle attribution (UPA) constraint rule.</span></span> <span data-ttu-id="870af-104">Tale regola prevede che ogni elemento in un documento dell'istanza corrisponda in modo non ambiguo a una particella `<xsd:element>` o `<xsd:any>` nel relativo modello di contenuto padre.</span><span class="sxs-lookup"><span data-stu-id="870af-104">This rule requires that each element in an instance document correspond unambiguously to exactly one `<xsd:element>` or `<xsd:any>` particle in its parent's content model.</span></span> <span data-ttu-id="870af-105">Ogni schema che contiene un tipo con un modello di contenuto potenzialmente ambiguo viene rifiutato.</span><span class="sxs-lookup"><span data-stu-id="870af-105">Any schema that contains a type with a potentially ambiguous content model is rejected.</span></span>  
  
 <span data-ttu-id="870af-106">Le cause di ambiguità più comuni sono la presenza di caratteri jolly `<xsd:any>` e le particelle con intervalli di occorrenze variabili, ad esempio minOccurs < maxOccurs.</span><span class="sxs-lookup"><span data-stu-id="870af-106">The most common causes of ambiguity are `<xsd:any>` wildcard characters and particles that have variable occurrence ranges, such as minOccurs < maxOccurs.</span></span> <span data-ttu-id="870af-107">Il modello di contenuto seguente, ad esempio, è ambiguo perché un elemento <`e1`> può corrispondere sia all'elemento `<xsd:element>` che all'elemento `<xsd:any>`.</span><span class="sxs-lookup"><span data-stu-id="870af-107">For example, the following content model is ambiguous, because an <`e1`> element could match either the `<xsd:element>` or the `<xsd:any>` element.</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
            <xsd:element name="e1"/>  
            <xsd:any namespace="##any"/>  
        </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="870af-108">Anche il modello di contenuto seguente è ambiguo:</span><span class="sxs-lookup"><span data-stu-id="870af-108">The following content model is also ambiguous:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:sequence>  
            <xsd:element name="e1" maxOccurs="2"/>  
            <xsd:element name="e2" minOccurs="0"/>  
            <xsd:element name="e1"/>  
        </xsd:sequence>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="870af-109">Mentre un documento come `<root><e1/><e2/><e1/></root>` può essere convalidato senza ambiguità, questo non è possibile per un documento quale `<root><e1/><e1/></root>` , perché non è chiaro a quale `<xsd:element>` corrisponda il secondo `<e1/>` .</span><span class="sxs-lookup"><span data-stu-id="870af-109">Although a document such as `<root><e1/><e2/><e1/></root>` can be validated unambiguously, a document such as `<root><e1/><e1/></root>` cannot, because it is not clear to which `<xsd:element>` the second `<e1/>` corresponds.</span></span> <span data-ttu-id="870af-110">Anche se alcuni documenti possono essere convalidati senza ambiguità, lo schema verrà rifiutato a causa delle ambiguità potenziali.</span><span class="sxs-lookup"><span data-stu-id="870af-110">Even though some documents can be validated unambiguously, the schema will be rejected, because of the potential for ambiguity.</span></span>  
  
 <span data-ttu-id="870af-111">Si noti che, affinché un modello di contenuto sia valido, deve essere possibile convalidare in modo non ambiguo tutte le istanze, senza eseguire ricerche look-ahead.</span><span class="sxs-lookup"><span data-stu-id="870af-111">Note that for a content model to be valid, it must be possible to validate any instance unambiguously without looking ahead.</span></span> <span data-ttu-id="870af-112">Si consideri, ad esempio, il modello di contenuto seguente.</span><span class="sxs-lookup"><span data-stu-id="870af-112">For example, consider the following content model:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e2"/>  
           </xsd:sequence>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e3"/>  
           </xsd:sequence>  
       </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="870af-113">Per un documento quale `<root><e1/><e3/></root>`, la sequenza `<e1/><e3/>` corrisponde esattamente al secondo elemento `<xsd:sequence>`.</span><span class="sxs-lookup"><span data-stu-id="870af-113">For a document such as `<root><e1/><e3/></root>`, the sequence `<e1/><e3/>` unambiguously matches the second `<xsd:sequence>`.</span></span> <span data-ttu-id="870af-114">Poiché tuttavia l'elemento `<xsd:element>` a cui corrisponde `<e1/>` non può essere determinato senza eseguire ricerche look-ahead a `<e3/>`, il modello di contenuto viola la regola del vincolo UPA.</span><span class="sxs-lookup"><span data-stu-id="870af-114">However, because the `<xsd:element>` to which `<e1/>` corresponds cannot be determined without looking ahead to `<e3/>`, the content model violates the UPA constraint rule.</span></span>  
  
## <a name="finding-more-information"></a><span data-ttu-id="870af-115">Per ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="870af-115">Finding More Information</span></span>  
 <span data-ttu-id="870af-116">Il documento seguente è pubblicato dal World Wide Web Consortium (W3C) e contiene la descrizione tecnica del vincolo di attribuzione di particelle univoche (informazioni in lingua inglese):</span><span class="sxs-lookup"><span data-stu-id="870af-116">The following document is published by the World Wide Web Consortium (W3C) and contains the technical description of the unique particle attribution constraint:</span></span>  
  
 <span data-ttu-id="870af-117">"XML Schema Part 1: Structures Second Edition, W3C Proposed Edited Recommendation":</span><span class="sxs-lookup"><span data-stu-id="870af-117">"XML Schema Part 1: Structures Second Edition, W3C Proposed Edited Recommendation":</span></span>  
  
-   <span data-ttu-id="870af-118">Section 3.8.6: Constraints on Model Group Schema Components</span><span class="sxs-lookup"><span data-stu-id="870af-118">Section 3.8.6: Constraints on Model Group Schema Components</span></span>  
  
-   <span data-ttu-id="870af-119">Appendix H: Analysis of the Unique Particle Attribution Constraint (non-normative)</span><span class="sxs-lookup"><span data-stu-id="870af-119">Appendix H: Analysis of the Unique Particle Attribution Constraint (non-normative)</span></span>  
  
 <span data-ttu-id="870af-120">Per vedere il documento, visitare [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span><span class="sxs-lookup"><span data-stu-id="870af-120">To see the document, visit [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870af-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="870af-121">See Also</span></span>  
 [<span data-ttu-id="870af-122">Raccolte di XML Schema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="870af-122">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
