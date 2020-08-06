---
title: Creazione di set denominati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- calculations [Analysis Services], named sets
- named sets [Analysis Services]
- members [Analysis Services], named sets
ms.assetid: 03cf97a4-1a18-45f3-acb0-35123bd619be
author: minewiskan
ms.author: owend
ms.openlocfilehash: e92984102ceb8ad0ac049c15870e9f1efd6090fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712575"
---
# <a name="create-named-sets"></a><span data-ttu-id="bea05-102">Creare set denominati</span><span class="sxs-lookup"><span data-stu-id="bea05-102">Create Named Sets</span></span>
  <span data-ttu-id="bea05-103">Un set denominato è un set di membri delle dimensioni oppure un'espressione set creata per successivi utilizzi, ad esempio all'interno di query MDX (MultiDimensional Expressions).</span><span class="sxs-lookup"><span data-stu-id="bea05-103">A named set is a set of dimension members or a set expression that is created for reuse, for example in Multidimensional Expressions (MDX) queries.</span></span> <span data-ttu-id="bea05-104">Per creare set denominati è possibile combinare dati di cubi, operatori aritmetici, numeri e funzioni.</span><span class="sxs-lookup"><span data-stu-id="bea05-104">You can create named sets by combining cube data, arithmetic operators, numbers, and functions.</span></span> <span data-ttu-id="bea05-105">Ad esempio, è possibile creare un set denominato Top Ten Factories contenente i dieci membri della dimensione Factories con i valori più alti per la misura Production.</span><span class="sxs-lookup"><span data-stu-id="bea05-105">For example, you can create a named set called Top Ten Factories that contains the ten members of the Factories dimension that have the highest values for the Production measure.</span></span> <span data-ttu-id="bea05-106">Il set denominato Top Ten Factories può quindi essere utilizzato nelle query dagli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="bea05-106">Top Ten Factories can then be used in queries by end users.</span></span> <span data-ttu-id="bea05-107">Ad esempio, un utente finale può inserire Top Ten Factories su un asse e la dimensione Measures, che include la misura Production, su un altro asse.</span><span class="sxs-lookup"><span data-stu-id="bea05-107">For example, an end user can place Top Ten Factories on one axis and the Measures dimension, including Production, on another axis.</span></span> <span data-ttu-id="bea05-108">Per altre informazioni, vedere [Calcoli nei modelli multidimensionali](calculations-in-multidimensional-models.md) e [Compilazione di set denominati in MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span><span class="sxs-lookup"><span data-stu-id="bea05-108">For more information, see [Calculations in Multidimensional Models](calculations-in-multidimensional-models.md), and [Building Named Sets in MDX &#40;MDX&#41;](mdx/mdx-named-sets-building-named-sets.md).</span></span>  
  
 <span data-ttu-id="bea05-109">Per creare un set denominato usare il comando **Nuovo set denominato** nella scheda **Calcoli** di Progettazione cubi.</span><span class="sxs-lookup"><span data-stu-id="bea05-109">To create a named set, use the **New Named Set** command on the **Calculations** tab of Cube Designer.</span></span> <span data-ttu-id="bea05-110">Questo comando è accessibile dal menu **Cubo** sulla barra degli strumenti della scheda **Calcoli** .</span><span class="sxs-lookup"><span data-stu-id="bea05-110">This command can be invoked on the **Cube** menu on the **Calculations** tab toolbar.</span></span> <span data-ttu-id="bea05-111">e visualizza un form in cui è possibile specificare le opzioni seguenti per il set denominato:</span><span class="sxs-lookup"><span data-stu-id="bea05-111">This command displays a form to specify the following options for the named set:</span></span>  
  
 <span data-ttu-id="bea05-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="bea05-112">**Name**</span></span>  
 <span data-ttu-id="bea05-113">Selezionare il nome del set denominato.</span><span class="sxs-lookup"><span data-stu-id="bea05-113">Select the name of the named set.</span></span> <span data-ttu-id="bea05-114">Questo nome appare agli utenti finali quando visualizzano il cubo.</span><span class="sxs-lookup"><span data-stu-id="bea05-114">This name appears to end users when they browse the cube.</span></span>  
  
 <span data-ttu-id="bea05-115">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="bea05-115">**Expression**</span></span>  
 <span data-ttu-id="bea05-116">Specificare l'espressione che genera il set denominato.</span><span class="sxs-lookup"><span data-stu-id="bea05-116">Specify the expression that produces the named set.</span></span> <span data-ttu-id="bea05-117">Questa espressione può essere scritta in MDX</span><span class="sxs-lookup"><span data-stu-id="bea05-117">This expression can be written in MDX.</span></span> <span data-ttu-id="bea05-118">e può contenere gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bea05-118">The expression can contain any of the following:</span></span>  
  
-   <span data-ttu-id="bea05-119">Espressioni di dati che rappresentano i componenti del cubo, quali dimensioni, livelli, misure e così via.</span><span class="sxs-lookup"><span data-stu-id="bea05-119">Data expressions that represent cube components such as dimensions, levels, measures, and so on.</span></span>  
  
-   <span data-ttu-id="bea05-120">Operatori aritmetici.</span><span class="sxs-lookup"><span data-stu-id="bea05-120">Arithmetic operators.</span></span>  
  
-   <span data-ttu-id="bea05-121">Numeri.</span><span class="sxs-lookup"><span data-stu-id="bea05-121">Numbers.</span></span>  
  
-   <span data-ttu-id="bea05-122">Funzioni.</span><span class="sxs-lookup"><span data-stu-id="bea05-122">Functions.</span></span>  
  
 <span data-ttu-id="bea05-123">È possibile copiare o trascinare componenti del cubo dalla scheda **Metadati** del riquadro **Strumenti di calcolo** nella casella **Espressione** del riquadro **Editor Form set denominato** .</span><span class="sxs-lookup"><span data-stu-id="bea05-123">You can copy or drag cube components from the **Metadata** tab of the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span> <span data-ttu-id="bea05-124">È possibile copiare o trascinare funzioni dalla scheda **Funzioni** del riquadro **Strumenti di calcolo** nella casella **Espressione** del riquadro **Editor Form set denominato** .</span><span class="sxs-lookup"><span data-stu-id="bea05-124">You can copy or drag functions from the **Functions** tab in the **Calculation Tools** pane to the **Expression** box in the **Named Set Form Editor** pane.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bea05-125">Se si crea l'espressione set assegnando in modo esplicito un nome ai membri del set, racchiudere l'elenco dei membri in una coppia di parentesi graffe ( {} ).</span><span class="sxs-lookup"><span data-stu-id="bea05-125">If you create the set expression by explicitly naming the members in the set, enclose the list of members in a pair of braces ({}).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bea05-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bea05-126">See Also</span></span>  
 [<span data-ttu-id="bea05-127">Calcoli nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="bea05-127">Calculations in Multidimensional Models</span></span>](calculations-in-multidimensional-models.md)  
  
  
