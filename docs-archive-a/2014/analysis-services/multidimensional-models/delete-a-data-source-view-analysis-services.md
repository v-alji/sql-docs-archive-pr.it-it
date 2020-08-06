---
title: Eliminazione di una vista origine dati (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- deleting data source views
- data source views [Analysis Services], deleting
- removing data source views
ms.assetid: ae3f5ca0-ecbf-4b52-8386-eb457719d854
author: minewiskan
ms.author: owend
ms.openlocfilehash: 24b587e8d8961161ea803915c31d117c11f7cf2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637461"
---
# <a name="delete-a-data-source-view-analysis-services"></a><span data-ttu-id="bf336-102">Eliminare una vista origine dati (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="bf336-102">Delete a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="bf336-103">Se non si usa più una vista origine dati in un progetto OLAP, è possibile eliminarla dal progetto in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf336-103">If you are no longer using a data source view (DSV) in an OLAP project, you can delete it from the project in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="bf336-104">L'eliminazione di una vista origine dati è permanente.</span><span class="sxs-lookup"><span data-stu-id="bf336-104">Deleting a DSV is permanent.</span></span> <span data-ttu-id="bf336-105">Non è possibile ripristinare una vista origine dati eliminata in un progetto o database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf336-105">You cannot restore a deleted DSV to a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span>  
  
 <span data-ttu-id="bf336-106">Non è possibile eliminare viste origine dati da cui dipendono altri oggetti da un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] aperto da [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] in modalità online.</span><span class="sxs-lookup"><span data-stu-id="bf336-106">DSVs that other objects depend on cannot be deleted from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database opened by [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span> <span data-ttu-id="bf336-107">Per eliminare una vista origine dati da un progetto connesso o da un database in esecuzione in un server, è necessario eliminare innanzitutto tutti gli oggetti nel database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] che dipendono da tale vista prima di eliminare la vista origine dati stessa.</span><span class="sxs-lookup"><span data-stu-id="bf336-107">To delete a DSV from a project that is connected o a database running on a server, you must first delete all objects in the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database that depend on that DSV before deleting the DSV itself.</span></span>  
  
 <span data-ttu-id="bf336-108">Se si elimina una vista origina dati, gli altri oggetti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] da cui dipendono non saranno validi pertanto, prima di eliminare la vista origine dati, si esaminerà l'elenco di oggetti che diventeranno non validi una volta rimossa tale vista.</span><span class="sxs-lookup"><span data-stu-id="bf336-108">Deleting a DSV will invalidate other [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects that depend on it, so before you delete the DSV, you will see the list of objects that will become invalid once the DSV is removed.</span></span> <span data-ttu-id="bf336-109">Esaminare con attenzione l'elenco per assicurarsi che non siano inclusi oggetti che si prevede di utilizzare ancora.</span><span class="sxs-lookup"><span data-stu-id="bf336-109">Review this list carefully to be sure that it does not include objects you still expect to use.</span></span>  
  
 <span data-ttu-id="bf336-110">![Finestra di dialogo Elimina oggetti](../media/ssas-olapdsv-deleteobjects.gif "Finestra di dialogo Elimina oggetti")</span><span class="sxs-lookup"><span data-stu-id="bf336-110">![Delete Objects dialog box](../media/ssas-olapdsv-deleteobjects.gif "Delete Objects dialog box")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf336-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf336-111">See Also</span></span>  
 <span data-ttu-id="bf336-112">[Viste origine dati in modelli multidimensionali](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="bf336-112">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="bf336-113">Modificare le proprietà in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bf336-113">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](change-properties-in-a-data-source-view-analysis-services.md)  
  
  
