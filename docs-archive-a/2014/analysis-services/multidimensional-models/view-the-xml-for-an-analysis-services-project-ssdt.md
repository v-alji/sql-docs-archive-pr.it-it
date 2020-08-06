---
title: Visualizzare il codice XML per un progetto di Analysis Services (SSDT) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Analysis Services], viewing XML
ms.assetid: dd1a4bc6-57b5-47df-8619-09f921aa6351
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c320145be2073c741498bed0f10732ac8d528e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724236"
---
# <a name="view-the-xml-for-an-analysis-services-project-ssdt"></a><span data-ttu-id="dc421-102">Visualizzare il codice XML per un progetto di Analysis Services (SSDT)</span><span class="sxs-lookup"><span data-stu-id="dc421-102">View the XML for an Analysis Services Project (SSDT)</span></span>
  <span data-ttu-id="dc421-103">Quando si utilizza un database di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in modalità progetto, in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] viene creata una definizione XML per ogni oggetto all'interno della cartella di progetto.</span><span class="sxs-lookup"><span data-stu-id="dc421-103">When you are working with an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in project mode, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates an XML definition for each object within the project folder.</span></span> <span data-ttu-id="dc421-104">È possibile visualizzare il contenuto del file XML per ogni oggetto in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc421-104">You can view the contents of the XML file for each object within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="dc421-105">È inoltre possibile modificare direttamente il file XML. Nella maggior parte delle circostanze, tuttavia, ciò non è consigliabile poiché le modifiche apportate potrebbero rendere il codice XML illeggibile per [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc421-105">You can also edit the XML file directly; however, this is not recommended in most circumstances as you may make changes that make the XML unreadable by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dc421-106">Non è possibile visualizzare il codice XML per un intero progetto. Viene invece visualizzato il codice per ogni oggetto, per il quale esiste un file separato.</span><span class="sxs-lookup"><span data-stu-id="dc421-106">You cannot view the xml code for an entire project, but rather you view the code for each object because a separate file exists for each object.</span></span> <span data-ttu-id="dc421-107">L'unico modo per visualizzare il codice di un intero progetto consiste nel compilare il progetto e visualizzare il codice ASSL nel \<project name> file con estensione asdatabase.</span><span class="sxs-lookup"><span data-stu-id="dc421-107">The only way to view the code for an entire project is to build the project and view the ASSL code in the \<project name>.asdatabase file.</span></span>  
  
### <a name="to-view-the-xml-code-for-an-object"></a><span data-ttu-id="dc421-108">Per visualizzare il codice XML per un oggetto</span><span class="sxs-lookup"><span data-stu-id="dc421-108">To view the XML code for an object</span></span>  
  
1.  <span data-ttu-id="dc421-109">Aprire il progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc421-109">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="dc421-110">Fare clic con il pulsante destro del mouse sull'oggetto in Esplora soluzioni e quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="dc421-110">Right-click the object in Solution Explorer and then click **View Code**.</span></span>  
  
     <span data-ttu-id="dc421-111">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]verrà visualizzato il codice XML per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc421-111">The XML code for the object appears in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc421-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc421-112">See Also</span></span>  
 [<span data-ttu-id="dc421-113">Compilare progetti di Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="dc421-113">Build Analysis Services Projects &#40;SSDT&#41;</span></span>](build-analysis-services-projects-ssdt.md)  
  
  
