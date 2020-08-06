---
title: Modifica dei nomi di tabella predefiniti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: ddd97483-a76d-43c1-8b40-fc7cc57fb0c2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 254f797be95f60211983400b019415431d4cf39c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623556"
---
# <a name="modifying-default-table-names"></a><span data-ttu-id="a36d4-102">Modifica dei nomi predefiniti delle tabelle</span><span class="sxs-lookup"><span data-stu-id="a36d4-102">Modifying Default Table Names</span></span>
  <span data-ttu-id="a36d4-103">È possibile modificare il valore della proprietà **FriendlyName** per gli oggetti nella vista origine dati per renderli più semplici da individuare e usare.</span><span class="sxs-lookup"><span data-stu-id="a36d4-103">You can change the value of the **FriendlyName** property for objects in the data source view to make them easier to notice and use.</span></span>  
  
 <span data-ttu-id="a36d4-104">Nell'attività seguente si modificherà il nome descrittivo di ogni tabella nella vista origine dati rimuovendo da tali tabelle i prefissi "**Dim**" e "**Fact**".</span><span class="sxs-lookup"><span data-stu-id="a36d4-104">In the following task, you will change the friendly name of each table in the data source view by removing the "**Dim**" and "**Fact**" prefixes from these tables.</span></span> <span data-ttu-id="a36d4-105">In questo modo, gli oggetti cubo e dimensione, che verranno definiti nella lezione successiva, risulteranno più semplici da individuare e utilizzare.</span><span class="sxs-lookup"><span data-stu-id="a36d4-105">This will make the cube and dimension objects (that you will define in the next lesson) easier to notice and use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a36d4-106">È inoltre possibile modificare i nomi descrittivi delle colonne, definire colonne calcolate e unire in join tabelle o viste della vista origine dati per semplificarne l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="a36d4-106">You can also change the friendly names of columns, define calculated columns, and join tables or views in the data source view to make them easier to use.</span></span>  
  
### <a name="to-modify-the-default-name-of-a-table"></a><span data-ttu-id="a36d4-107">Per modificare il nome predefinito di una tabella</span><span class="sxs-lookup"><span data-stu-id="a36d4-107">To modify the default name of a table</span></span>  
  
1.  <span data-ttu-id="a36d4-108">Nel riquadro **Tabelle** di **Progettazione vista origine dati**fare clic con il pulsante destro del mouse sulla tabella **FactInternetSales** e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a36d4-108">In the **Tables** pane of **Data Source View Designer**, right-click the **FactInternetSales** table, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a36d4-109">Se la finestra Proprietà non è visualizzata sul lato destro della finestra di Microsoft Visual Studio, fare clic sul pulsante **Nascondi automaticamente** sulla barra del titolo della finestra Proprietà in modo che la finestra rimanga visibile.</span><span class="sxs-lookup"><span data-stu-id="a36d4-109">If the Properties window on the right side of the Microsoft Visual Studio window is not displayed, click the **Auto Hide** button on the title bar of the Properties window so that this window remains visible.</span></span>  
  
     <span data-ttu-id="a36d4-110">Se la finestra Proprietà rimane aperta è più facile modificare le proprietà di ogni tabella della vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="a36d4-110">It is easier to change the properties for each table in the data source view when the Properties window remains open.</span></span> <span data-ttu-id="a36d4-111">Se la finestra non viene tenuta aperta usando il pulsante **Nascondi automaticamente** , si chiuderà quando si fa clic su un altro oggetto nel riquadro **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="a36d4-111">If you do not pin the window open by using the **Auto Hide** button, the window will close when you click a different object in the **Diagram** pane.</span></span>  
  
3.  <span data-ttu-id="a36d4-112">Modificare la proprietà **FriendlyName** dell'oggetto **FactInternetSales** in *`InternetSales`* .</span><span class="sxs-lookup"><span data-stu-id="a36d4-112">Change the **FriendlyName** property for the **FactInternetSales** object to *`InternetSales`*.</span></span>  
  
     <span data-ttu-id="a36d4-113">La modifica viene applicata quando si fa clic in un punto diverso dalla cella della proprietà **FriendlyName** .</span><span class="sxs-lookup"><span data-stu-id="a36d4-113">When you click away from the cell for the **FriendlyName** property, the change is applied.</span></span> <span data-ttu-id="a36d4-114">Nella lezione successiva si definirà un gruppo di misure basato su questa tabella dei fatti.</span><span class="sxs-lookup"><span data-stu-id="a36d4-114">In the next lesson, you will define a measure group that is based on this fact table.</span></span> <span data-ttu-id="a36d4-115">Il nome della tabella dei fatti sarà InternetSales anziché FactInternetSales a causa della modifica apportata in questa lezione.</span><span class="sxs-lookup"><span data-stu-id="a36d4-115">The name of the fact table will be InternetSales instead of FactInternetSales because of the change you made in this lesson.</span></span>  
  
4.  <span data-ttu-id="a36d4-116">Fare clic su **DimProduct** nel riquadro **Tabelle** .</span><span class="sxs-lookup"><span data-stu-id="a36d4-116">Click **DimProduct** in the **Tables** pane.</span></span> <span data-ttu-id="a36d4-117">Nella Finestra Proprietà modificare la proprietà **FriendlyName** in *`Product`* .</span><span class="sxs-lookup"><span data-stu-id="a36d4-117">In the Properties window, change the **FriendlyName** property to *`Product`*.</span></span>  
  
5.  <span data-ttu-id="a36d4-118">Modificare la proprietà **FriendlyName** delle tabelle rimanenti nella vista origine dati allo stesso modo per rimuovere il prefisso "**Dim**".</span><span class="sxs-lookup"><span data-stu-id="a36d4-118">Change the **FriendlyName** property of each remaining table in the data source view in the same way, to remove the "**Dim**" prefix.</span></span>  
  
6.  <span data-ttu-id="a36d4-119">Al termine fare di nuovo clic sul pulsante **Nascondi automaticamente** per nascondere la finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a36d4-119">When you have finished, click the **Auto Hide** button to hide the Properties window again.</span></span>  
  
7.  <span data-ttu-id="a36d4-120">Scegliere **Salva tutti** dal menu [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]File **o sulla barra degli strumenti di** per salvare le modifiche apportate fino a questo punto al progetto [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial.</span><span class="sxs-lookup"><span data-stu-id="a36d4-120">On the **File** menu, or on the toolbar of [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click **Save All** to save the changes you have made to this point in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial project.</span></span> <span data-ttu-id="a36d4-121">Se si desidera, è possibile arrestare l'esercitazione e riprenderla in seguito.</span><span class="sxs-lookup"><span data-stu-id="a36d4-121">You can stop the tutorial here if you want and resume it later.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="a36d4-122">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="a36d4-122">Next Lesson</span></span>  
 [<span data-ttu-id="a36d4-123">Lezione 2: Definizione e distribuzione di un cubo</span><span class="sxs-lookup"><span data-stu-id="a36d4-123">Lesson 2: Defining and Deploying a Cube</span></span>](lesson-2-defining-and-deploying-a-cube.md)  
  
## <a name="see-also"></a><span data-ttu-id="a36d4-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a36d4-124">See Also</span></span>  
 <span data-ttu-id="a36d4-125">[Viste origine dati in modelli multidimensionali](multidimensional-models/data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="a36d4-125">[Data Source Views in Multidimensional Models](multidimensional-models/data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="a36d4-126">Modificare le proprietà in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="a36d4-126">Change Properties in a Data Source View &#40;Analysis Services&#41;</span></span>](multidimensional-models/change-properties-in-a-data-source-view-analysis-services.md)  
  
  
