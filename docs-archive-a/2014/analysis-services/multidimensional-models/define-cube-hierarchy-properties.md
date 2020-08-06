---
title: Definire le proprietà della gerarchia del cubo | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- hierarchies [Analysis Services], multilevel
- hierarchies [Analysis Services], cubes
ms.assetid: 819d0a4e-7815-4332-a605-b07ca2ade6ac
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8903a49754357aad9cf24ee63fffa45fbf120e4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712568"
---
# <a name="define-cube-hierarchy-properties"></a><span data-ttu-id="3c33a-102">Definire le proprietà della gerarchia del cubo</span><span class="sxs-lookup"><span data-stu-id="3c33a-102">Define Cube Hierarchy Properties</span></span>
  <span data-ttu-id="3c33a-103">Le proprietà delle gerarchie dei cubi consentono di specificare impostazioni univoche per gerarchie definite dall'utente in dimensioni del cubo basate sulla stessa dimensione del database.</span><span class="sxs-lookup"><span data-stu-id="3c33a-103">Cube hierarchy properties enable you to specify unique settings for user-defined hierarchies in cube dimensions based on the same database dimension.</span></span> <span data-ttu-id="3c33a-104">Nella tabella seguente vengono descritte le proprietà della gerarchia di un cubo.</span><span class="sxs-lookup"><span data-stu-id="3c33a-104">The following table describes the properties of a cube hierarchy.</span></span>  
  
|<span data-ttu-id="3c33a-105">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3c33a-105">Property</span></span>|<span data-ttu-id="3c33a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c33a-106">Description</span></span>|  
|--------------|-----------------|  
|`Enabled`|<span data-ttu-id="3c33a-107">Determina l'eventuale abilitazione della gerarchia per la dimensione del cubo.</span><span class="sxs-lookup"><span data-stu-id="3c33a-107">Determines whether the hierarchy is enabled for the cube dimension.</span></span>|  
|`HierarchyID`|<span data-ttu-id="3c33a-108">Contiene l'identificatore univoco (ID) della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="3c33a-108">Contains the unique identifier (ID) of the hierarchy.</span></span>|  
|`OptimizedState`|<span data-ttu-id="3c33a-109">Determina il livello di ottimizzazione applicato alla gerarchia.</span><span class="sxs-lookup"><span data-stu-id="3c33a-109">Determines the level of optimization that is applied to the hierarchy.</span></span> <span data-ttu-id="3c33a-110">I possibili valori della proprietà sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c33a-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="3c33a-111">`FullyOptimized`: l'istanza compila indici per la gerarchia allo scopo di migliorare le prestazioni delle query.</span><span class="sxs-lookup"><span data-stu-id="3c33a-111">`FullyOptimized`: The instance builds indexes for the hierarchy to improve query performance.</span></span> <span data-ttu-id="3c33a-112">Rappresenta il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="3c33a-112">This is the default value.</span></span><br /><br /> <span data-ttu-id="3c33a-113">`NotOptimized`: l'istanza non compila indici aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="3c33a-113">`NotOptimized`: The instance does not build additional indexes.</span></span>|  
|`Visible`|<span data-ttu-id="3c33a-114">Determina la visibilità della gerarchia del cubo.</span><span class="sxs-lookup"><span data-stu-id="3c33a-114">Determines the visibility of the cube hierarchy.</span></span> <span data-ttu-id="3c33a-115">Il valore predefinito è `True`.</span><span class="sxs-lookup"><span data-stu-id="3c33a-115">The default value is `True`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c33a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c33a-116">See Also</span></span>  
 [<span data-ttu-id="3c33a-117">Gerarchie definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="3c33a-117">User Hierarchies</span></span>](../multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md)  
  
  
