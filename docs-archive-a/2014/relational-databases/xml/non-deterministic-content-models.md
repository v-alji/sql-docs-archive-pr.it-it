---
title: Modelli di contenuto non deterministici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- non-deterministic content models
- content models [XML in SQL Server]
ms.assetid: 9d4513e7-dd19-4491-b7c7-28bc7c2f8589
author: rothja
ms.author: jroth
ms.openlocfilehash: 6182ff4a5ee0c9c109f6880c7d3337fb6dd20749
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712831"
---
# <a name="non-deterministic-content-models"></a><span data-ttu-id="1cd7a-102">modelli di contenuto non deterministici</span><span class="sxs-lookup"><span data-stu-id="1cd7a-102">Non-Deterministic Content Models</span></span>
  <span data-ttu-id="1cd7a-103">Prima di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), gli elementi XML Schema che contenevano modelli di contenuto non deterministici venivano rifiutati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1cd7a-103">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 1 (SP1), [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] rejected XML schemas that had non-deterministic content models.</span></span>  
  
 <span data-ttu-id="1cd7a-104">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, i modelli di contenuto non deterministici vengono accettati se i vincoli di occorrenza sono 0, 1 o senza vincoli.</span><span class="sxs-lookup"><span data-stu-id="1cd7a-104">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1, however, non-deterministic content models are accepted if the occurrence constraints are 0,1, or unbounded.</span></span>  
  
## <a name="example-non-deterministic-content-model-rejected"></a><span data-ttu-id="1cd7a-105">Esempio: modello di contenuto non deterministico rifiutato</span><span class="sxs-lookup"><span data-stu-id="1cd7a-105">Example: Non-deterministic content model rejected</span></span>  
 <span data-ttu-id="1cd7a-106">Nello schema dell'esempio viene illustrato il tentativo di creare un elemento XML Schema con un modello di contenuto non deterministico.</span><span class="sxs-lookup"><span data-stu-id="1cd7a-106">The following example attempts to create an XML schema with a non-deterministic content model.</span></span> <span data-ttu-id="1cd7a-107">Il codice ha esito negativo poiché non è possibile determinare se l'elemento `<root>` debba avere una sequenza di due elementi `<a>` oppure se l'elemento `<root>` debba averne due, ognuna con un elemento `<a>` .</span><span class="sxs-lookup"><span data-stu-id="1cd7a-107">The code fails because it is not clear whether the `<root>` element should have a sequence of two `<a>` elements or if the `<root>` element should have two sequences, each with an `<a>` element.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="1" maxOccurs="2">  
                <element name="a" type="string" minOccurs="1" maxOccurs="2"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
 <span data-ttu-id="1cd7a-108">È possibile correggere lo schema spostando il vincolo di occorrenza in una posizione univoca,</span><span class="sxs-lookup"><span data-stu-id="1cd7a-108">The schema can be fixed by moving the occurrence constraint to a unique location.</span></span> <span data-ttu-id="1cd7a-109">ad esempio, il vincolo può essere spostato nella particella contenente la sequenza:</span><span class="sxs-lookup"><span data-stu-id="1cd7a-109">For example, the constraint can be moved to the containing sequence particle:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="4">  
    <element name="a" type="string" minOccurs="1" maxOccurs="1"/>  
</sequence>  
```  
  
 <span data-ttu-id="1cd7a-110">In alternativa, il vincolo può essere spostato sull'elemento contenuto:</span><span class="sxs-lookup"><span data-stu-id="1cd7a-110">Or the constraint can be moved to the contained element:</span></span>  
  
```  
<sequence minOccurs="1" maxOccurs="1">  
     <element name="a" type="string" minOccurs="1" maxOccurs="4"/>  
</sequence>  
```  
  
## <a name="example-non-deterministic-content-model-accepted"></a><span data-ttu-id="1cd7a-111">Esempio: modello di contenuto non deterministico accettato</span><span class="sxs-lookup"><span data-stu-id="1cd7a-111">Example: Non-deterministic content model accepted</span></span>  
 <span data-ttu-id="1cd7a-112">Lo schema seguente verrebbe rifiutato nelle versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] precedenti a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="1cd7a-112">The following schema would be rejected in versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] SP1.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION MyCollection AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema">  
    <element name="root">  
        <complexType>  
            <sequence minOccurs="0" maxOccurs="unbounded">  
                <element name="a" type="string" minOccurs="0" maxOccurs="1"/>  
                <element name="b" type="string" minOccurs="1" maxOccurs="unbounded"/>  
            </sequence>  
        </complexType>  
    </element>  
</schema>  
'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1cd7a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cd7a-113">See Also</span></span>  
 [<span data-ttu-id="1cd7a-114">Requisiti e limitazioni per le raccolte di XML Schema nel server</span><span class="sxs-lookup"><span data-stu-id="1cd7a-114">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
