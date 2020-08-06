---
title: Selezione metodo di creazione (creazione guidata cubo) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubewizard.cubedefinition.f1
ms.assetid: 985d3b5b-7891-465b-862d-f7e75431b342
author: minewiskan
ms.author: owend
ms.openlocfilehash: c8c4d611e00a2b3f5d115ea5749b1e494a44bf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636403"
---
# <a name="select-creation-method-cube-wizard"></a><span data-ttu-id="fbcae-102">Seleziona metodo di creazione (Creazione guidata cubo)</span><span class="sxs-lookup"><span data-stu-id="fbcae-102">Select Creation Method (Cube Wizard)</span></span>
  <span data-ttu-id="fbcae-103">Utilizzare la pagina **Seleziona metodo di creazione** per specificare la modalità di creazione del cubo.</span><span class="sxs-lookup"><span data-stu-id="fbcae-103">Use the **Select Creation Method** page to specify how to create the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fbcae-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fbcae-104">Options</span></span>  
 <span data-ttu-id="fbcae-105">**Usa tabelle esistenti**</span><span class="sxs-lookup"><span data-stu-id="fbcae-105">**Use existing tables**</span></span>  
 <span data-ttu-id="fbcae-106">Selezionare per creare un cubo utilizzando le tabelle esistenti in un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="fbcae-106">Select to create a cube by using existing tables in a data source.</span></span> <span data-ttu-id="fbcae-107">La procedura guidata descriverà dettagliatamente il processo di selezione e definizione dei gruppi di misure e delle dimensioni in base alle tabelle esistenti per compilare il cubo nuovo.</span><span class="sxs-lookup"><span data-stu-id="fbcae-107">The wizard will guide you through the process of selecting and defining measure groups and dimensions based on existing tables to build your new cube.</span></span>  
  
 <span data-ttu-id="fbcae-108">**Crea un cubo vuoto**</span><span class="sxs-lookup"><span data-stu-id="fbcae-108">**Create an empty cube**</span></span>  
 <span data-ttu-id="fbcae-109">Selezionare per creare un cubo vuoto.</span><span class="sxs-lookup"><span data-stu-id="fbcae-109">Select to create an empty cube.</span></span> <span data-ttu-id="fbcae-110">Questa opzione è utile per creare tutto manualmente o quando tutti i gruppi di misure nel cubo sono gruppi di misure collegati.</span><span class="sxs-lookup"><span data-stu-id="fbcae-110">This option is useful when you want to create everything manually, or when all measure groups in the cube are linked measure groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbcae-111">Questa opzione è disponibile solo quando si lavora a un progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e non quando si è connessi direttamente a un database [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fbcae-111">This option is only available when you are working with an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and not when you are connected directly to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="fbcae-112">**Genera tabelle nell'origine dei dati**</span><span class="sxs-lookup"><span data-stu-id="fbcae-112">**Generate tables in the data source**</span></span>  
 <span data-ttu-id="fbcae-113">Selezionare per creare prima un cubo e quindi generare tabelle nuove nell'origine dati in base alla definizione del cubo.</span><span class="sxs-lookup"><span data-stu-id="fbcae-113">Select to create a cube first and then generate new tables in the data source based on the cube definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbcae-114">Per utilizzare questa opzione, si deve disporre delle autorizzazioni per creare gli oggetti nell'origine dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="fbcae-114">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="fbcae-115">La selezione di questa opzione renderà disponibile l'opzione **Modello** .</span><span class="sxs-lookup"><span data-stu-id="fbcae-115">Selecting this option will make the **Template** option available.</span></span>  
  
 <span data-ttu-id="fbcae-116">**Modello**</span><span class="sxs-lookup"><span data-stu-id="fbcae-116">**Template**</span></span>  
 <span data-ttu-id="fbcae-117">Selezionare il modello che si desidera utilizzare per creare il cubo.</span><span class="sxs-lookup"><span data-stu-id="fbcae-117">Select the template that you want to use to create the cube.</span></span> <span data-ttu-id="fbcae-118">I modelli offrono un set completo di definizioni orientate ad applicazioni aziendali specifiche.</span><span class="sxs-lookup"><span data-stu-id="fbcae-118">Templates provide a set of definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fbcae-119">Questa opzione è disponibile solo quando l'opzione viene selezionata l'opzione **Genera tabelle nell'origine dati** .</span><span class="sxs-lookup"><span data-stu-id="fbcae-119">This option is only available when the **Generate tables in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbcae-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbcae-120">See Also</span></span>  
 <span data-ttu-id="fbcae-121">[Oggetti Cube &#40;Analysis Services-Dati multidimensionali&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="fbcae-121">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="fbcae-122">[Cubi nei modelli multidimensionali](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="fbcae-122">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="fbcae-123">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="fbcae-123">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
