---
title: Proprietà livello | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- user hierarchies [Analysis Services]
- hierarchies [Analysis Services], user
ms.assetid: dabb7335-887b-442a-b67c-4901ba1242b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 553503b9d35142bcc998b4ec12ad2e29d4c66318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625011"
---
# <a name="level-properties"></a><span data-ttu-id="7c8ca-102">Proprietà di livello</span><span class="sxs-lookup"><span data-stu-id="7c8ca-102">Level Properties</span></span> 
  <span data-ttu-id="7c8ca-103">Nella tabella seguente vengono elencate e descritte le proprietà di un livello in una gerarchia definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-103">The following table lists and describes the properties of a level in a user-defined hierarchy.</span></span>  
  
|<span data-ttu-id="7c8ca-104">Proprietà</span><span class="sxs-lookup"><span data-stu-id="7c8ca-104">Property</span></span>|<span data-ttu-id="7c8ca-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c8ca-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7c8ca-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c8ca-106">Description</span></span>|<span data-ttu-id="7c8ca-107">Contiene la descrizione del livello.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-107">Contains the description of the level.</span></span>|  
|<span data-ttu-id="7c8ca-108">HideMemberIf</span><span class="sxs-lookup"><span data-stu-id="7c8ca-108">HideMemberIf</span></span>|<span data-ttu-id="7c8ca-109">Indica se e quando un membro di un livello deve essere nascosto per le applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-109">Indicates whether and when a member in a level should be hidden from client applications.</span></span> <span data-ttu-id="7c8ca-110">I possibili valori della proprietà sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c8ca-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="7c8ca-111">Mai</span><span class="sxs-lookup"><span data-stu-id="7c8ca-111">Never</span></span><br /> <span data-ttu-id="7c8ca-112">I membri non vengono mai nascosti.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-112">Members are never hidden.</span></span> <span data-ttu-id="7c8ca-113">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-113">This is the default value.</span></span><br /><br /> <span data-ttu-id="7c8ca-114">OnlyChildWithNoName</span><span class="sxs-lookup"><span data-stu-id="7c8ca-114">OnlyChildWithNoName</span></span><br /> <span data-ttu-id="7c8ca-115">Un membro viene nascosto quando il membro è l'unico figlio del relativo padre e il nome del membro è vuoto.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-115">A member is hidden when the member is the only child of its parent and the member's name is empty.</span></span><br /><br /> <span data-ttu-id="7c8ca-116">OnlyChildWithParentName</span><span class="sxs-lookup"><span data-stu-id="7c8ca-116">OnlyChildWithParentName</span></span><br /> <span data-ttu-id="7c8ca-117">Un membro viene nascosto quando il membro è l'unico figlio del relativo padre e il nome del membro è uguale a quello del relativo padre.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-117">A member is hidden when the member is the only child of its parent and the member's name is identical to that of its parent.</span></span><br /><br /> <span data-ttu-id="7c8ca-118">NoName</span><span class="sxs-lookup"><span data-stu-id="7c8ca-118">NoName</span></span><br /> <span data-ttu-id="7c8ca-119">Un membro viene nascosto quando il nome del membro è vuoto.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-119">A member is hidden when the member's name is empty.</span></span><br /><br /> <span data-ttu-id="7c8ca-120">ParentName</span><span class="sxs-lookup"><span data-stu-id="7c8ca-120">ParentName</span></span><br /> <span data-ttu-id="7c8ca-121">Un membro viene nascosto quando il nome del membro è uguale a quello del relativo padre.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-121">A member is hidden when the member's name is identical to that of its parent.</span></span>|  
|<span data-ttu-id="7c8ca-122">ID</span><span class="sxs-lookup"><span data-stu-id="7c8ca-122">ID</span></span>|<span data-ttu-id="7c8ca-123">Contiene l'identificatore univoco (ID) del livello.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-123">Contains the unique identifier (ID) of the level.</span></span>|  
|<span data-ttu-id="7c8ca-124">Nome</span><span class="sxs-lookup"><span data-stu-id="7c8ca-124">Name</span></span>|<span data-ttu-id="7c8ca-125">Contiene il nome descrittivo del livello.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-125">Contains the friendly name of the level.</span></span> <span data-ttu-id="7c8ca-126">Per impostazione predefinita, il nome di un livello è uguale al nome dell'attributo di origine.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-126">By default, the name of a level is the same as the name of the source attribute.</span></span>|  
|<span data-ttu-id="7c8ca-127">SourceAttribute</span><span class="sxs-lookup"><span data-stu-id="7c8ca-127">SourceAttribute</span></span>|<span data-ttu-id="7c8ca-128">Contiene il nome dell'attributo di origine sul quale si basa il livello.</span><span class="sxs-lookup"><span data-stu-id="7c8ca-128">Contains the name of the source attribute on which the level is based.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c8ca-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c8ca-129">See Also</span></span>  
 [<span data-ttu-id="7c8ca-130">Proprietà delle gerarchie definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="7c8ca-130">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
