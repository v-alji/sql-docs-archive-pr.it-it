---
title: Gestione delle cache (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- XMLA, cache
- XML for Analysis, cache
- clearing cache
- cache [Analysis Services]
ms.assetid: afad5c39-d4c3-4307-b3b9-a06617da0028
author: minewiskan
ms.author: owend
ms.openlocfilehash: cdc5bcd2e0500749edfa298a871b6fec7243ddfb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627479"
---
# <a name="managing-caches-xmla"></a><span data-ttu-id="1ccbe-102">Gestione delle cache (XMLA)</span><span class="sxs-lookup"><span data-stu-id="1ccbe-102">Managing Caches (XMLA)</span></span>
  <span data-ttu-id="1ccbe-103">È possibile utilizzare il comando [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) in XML for Analysis (XMLA) per cancellare la cache di una dimensione o di una partizione specificata.</span><span class="sxs-lookup"><span data-stu-id="1ccbe-103">You can use the [ClearCache](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/clearcache-element-xmla) command in XML for Analysis (XMLA) to clear the cache of a specified dimension or partition.</span></span> <span data-ttu-id="1ccbe-104">Cancellare le forze della cache [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] per ricompilare la cache per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="1ccbe-104">Clearing the cache forces [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to rebuild the cache for that object.</span></span>  
  
## <a name="specifying-objects"></a><span data-ttu-id="1ccbe-105">Specifica di oggetti</span><span class="sxs-lookup"><span data-stu-id="1ccbe-105">Specifying Objects</span></span>  
 <span data-ttu-id="1ccbe-106">La proprietà [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `ClearCache` comando può contenere un riferimento a un oggetto solo per uno degli oggetti seguenti.</span><span class="sxs-lookup"><span data-stu-id="1ccbe-106">The [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `ClearCache` command can contain an object reference only for one of the following objects.</span></span> <span data-ttu-id="1ccbe-107">Se un riferimento è relativo a un oggetto diverso da uno di quelli seguenti, si verifica un errore:</span><span class="sxs-lookup"><span data-stu-id="1ccbe-107">An error occurs if an object reference is for an object other than one of following objects:</span></span>  
  
 <span data-ttu-id="1ccbe-108">Database</span><span class="sxs-lookup"><span data-stu-id="1ccbe-108">Database</span></span>  
 <span data-ttu-id="1ccbe-109">Cancella la cache per tutte le dimensioni e le partizioni contenute nel database.</span><span class="sxs-lookup"><span data-stu-id="1ccbe-109">Clears the cache for all dimensions and partitions contained in the database.</span></span>  
  
 <span data-ttu-id="1ccbe-110">Dimension</span><span class="sxs-lookup"><span data-stu-id="1ccbe-110">Dimension</span></span>  
 <span data-ttu-id="1ccbe-111">Cancella la cache per la dimensione specificata.</span><span class="sxs-lookup"><span data-stu-id="1ccbe-111">Clears the cache for the specified dimension.</span></span>  
  
 <span data-ttu-id="1ccbe-112">Cubo</span><span class="sxs-lookup"><span data-stu-id="1ccbe-112">Cube</span></span>  
 <span data-ttu-id="1ccbe-113">Cancella la cache per tutte le partizioni contenute nei gruppi di misure per il cubo.</span><span class="sxs-lookup"><span data-stu-id="1ccbe-113">Clears the cache for all partitions contained in the measure groups for the cube.</span></span>  
  
 <span data-ttu-id="1ccbe-114">Gruppo di misure</span><span class="sxs-lookup"><span data-stu-id="1ccbe-114">Measure group</span></span>  
 <span data-ttu-id="1ccbe-115">Cancella la cache per tutte le partizioni contenute nel gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="1ccbe-115">Clears the cache for all partitions contained in the measure group.</span></span>  
  
 <span data-ttu-id="1ccbe-116">Partition</span><span class="sxs-lookup"><span data-stu-id="1ccbe-116">Partition</span></span>  
 <span data-ttu-id="1ccbe-117">Cancella la cache per la partizione specificata.</span><span class="sxs-lookup"><span data-stu-id="1ccbe-117">Clears the cache for the specified partition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccbe-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ccbe-118">See Also</span></span>  
 [<span data-ttu-id="1ccbe-119">Sviluppo con XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="1ccbe-119">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
