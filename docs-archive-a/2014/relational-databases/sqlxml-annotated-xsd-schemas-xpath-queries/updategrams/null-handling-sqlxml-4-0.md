---
title: Gestione dei valori NULL (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- updg:nullvalue attribute
- updategrams [SQLXML], null values
- nullvalue attribute
- null values [SQLXML]
ms.assetid: 5e11eebb-d94e-4ce6-a6d0-870225706bc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 430643e8a6c9bd3dd00b2763990645c6a162ee40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87634956"
---
# <a name="null-handling-sqlxml-40"></a><span data-ttu-id="ff093-102">Gestione dei valori Null (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ff093-102">NULL Handling (SQLXML 4.0)</span></span>
  <span data-ttu-id="ff093-103">Nella sintassi XML il valore Null indica un'assenza.</span><span class="sxs-lookup"><span data-stu-id="ff093-103">XML syntax denotes NULL as an absence.</span></span> <span data-ttu-id="ff093-104">Se, ad esempio, il valore di un attributo o di un elemento è NULL, l'attributo o l'elemento è assente dal documento XML. In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML l' `updg:nullvalue` attributo consente di specificare null per un valore di elemento o attributo.</span><span class="sxs-lookup"><span data-stu-id="ff093-104">(For example, if an attribute or element value is NULL, that attribute or element is absent from the XML document.) In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML, the `updg:nullvalue` attribute enables specifying NULL for an element or attribute value.</span></span>  
  
 <span data-ttu-id="ff093-105">L'updategram seguente, ad esempio, assicura che il valore del **titolo** per un contatto con **ContactID** di 64 sia null e quindi aggiorni il valore del **titolo** a "Mr."</span><span class="sxs-lookup"><span data-stu-id="ff093-105">For example, the following updategram ensures that the **Title** value for a contact with **ContactID** of 64 is NULL, and then updates the **Title** value to "Mr."</span></span> <span data-ttu-id="ff093-106">per questo contatto.</span><span class="sxs-lookup"><span data-stu-id="ff093-106">for this contact.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync updg:nullvalue="IsNULL"  >  
    <updg:before>  
       <Person.Contact ContactID="64" Title="IsNULL" />  
    </updg:before>  
    <updg:after>  
       <Person.Contact ContactID="64" Title="Mr." />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="ff093-107">Quando i parametri vengono passati a un updategram, è possibile passare Null come valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="ff093-107">When parameters are passed to an updategram, NULL can be passed as the parameter value.</span></span> <span data-ttu-id="ff093-108">A tale scopo è necessario specificare l'attributo `nullvalue` nel blocco `<updg:header>`.</span><span class="sxs-lookup"><span data-stu-id="ff093-108">This is done by specifying the `nullvalue` attribute in the `<updg:header>` block.</span></span> <span data-ttu-id="ff093-109">Per un esempio, vedere [passaggio di parametri agli updategram &#40;SQLXML 4,0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ff093-109">For an example, see [Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;](passing-parameters-to-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff093-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff093-110">See Also</span></span>  
 [<span data-ttu-id="ff093-111">Considerazioni sulla sicurezza degli updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ff093-111">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
