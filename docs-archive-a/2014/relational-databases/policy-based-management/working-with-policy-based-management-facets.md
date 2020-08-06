---
title: Usare la copia di facet della gestione basata su criteri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- viewing Policy-Based Management facets
- facets [Policy-Based Management], copying
- facets [Policy-Based Management], viewing
- copying Policy-Based Management facets
ms.assetid: 88d025c4-07c2-4e4d-8634-204249a8c82c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5a356550796cc682b2292defffd6565b7fea0783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626680"
---
# <a name="working-with-policy-based-management-facets"></a><span data-ttu-id="088e6-102">Utilizzo della copia di facet della gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="088e6-102">Working with Policy-Based Management Facets</span></span>
  <span data-ttu-id="088e6-103">Un facet di gestione basata su criteri è un set di proprietà logiche correlate a un'area di interesse di gestione.</span><span class="sxs-lookup"><span data-stu-id="088e6-103">A Policy-Based Management facet is a set of logical properties that are related to an area of management interest.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="088e6-104">ha diversi facet predefiniti.</span><span class="sxs-lookup"><span data-stu-id="088e6-104">includes several predefined facets.</span></span> <span data-ttu-id="088e6-105">Il facet di gestione della superficie di attacco, ad esempio, definisce come proprietà le funzionalità disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="088e6-105">For example, the Surface Area Configuration facet defines, as properties, the features that are off by default.</span></span>  
  
 <span data-ttu-id="088e6-106">Quando si gestiscono molti ambienti [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] simili, è possibile configurare un facet in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copiare lo stato del facet in un file, quindi importare il file come criteri in un'altra istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="088e6-106">When you manage many similar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environments, you can configure a facet in one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copy the state of the facet to a file, and then import that file into another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a policy.</span></span> <span data-ttu-id="088e6-107">Una volta convertito lo stato in criteri, è possibile applicare i criteri ad altre istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], nonché ad altri oggetti delle istanze, database o oggetti di database.</span><span class="sxs-lookup"><span data-stu-id="088e6-107">When the state has been converted to a policy, the policy can be applied to other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance objects, databases, or database objects.</span></span>  
  
 <span data-ttu-id="088e6-108">In questo argomento viene descritto come copiare lo stato di un facet in un file XML.</span><span class="sxs-lookup"><span data-stu-id="088e6-108">This topic describes how to copy the state of a facet to an XML file.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="088e6-109">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="088e6-109">Permissions</span></span>  
 <span data-ttu-id="088e6-110">Le procedure descritte in questo argomento richiedono l'appartenenza al ruolo PolicyAdministratorRole nel database msdb.</span><span class="sxs-lookup"><span data-stu-id="088e6-110">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
## <a name="viewing-and-copying-facet-states"></a><span data-ttu-id="088e6-111">Visualizzazione e copia di stati di un facet</span><span class="sxs-lookup"><span data-stu-id="088e6-111">Viewing and Copying Facet States</span></span>  
 [<span data-ttu-id="088e6-112">Visualizzare i facet della gestione basata su criteri in un oggetto di SQL Server</span><span class="sxs-lookup"><span data-stu-id="088e6-112">View the Policy-Based Management Facets on a SQL Server Object</span></span>](view-the-policy-based-management-facets-on-a-sql-server-object.md)  
  
 [<span data-ttu-id="088e6-113">Copiare lo stato di un facet della gestione basata su criteri in un file XML</span><span class="sxs-lookup"><span data-stu-id="088e6-113">Copy a Policy-Based Management Facet State to an XML File</span></span>](copy-a-policy-based-management-facet-state-to-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="088e6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="088e6-114">See Also</span></span>  
 [<span data-ttu-id="088e6-115">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="088e6-115">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
