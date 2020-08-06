---
title: Filtrare il cubo di origine per una struttura di data mining | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- slice cubes [Analysis Services]
- mining structures [Analysis Services], filtering source cube
- cubes [Analysis Services], slicing
- filtering data [Analysis Services]
ms.assetid: 05dce7e1-2fe5-4500-bacf-c1a8a76e1424
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61409b4803f43d3ff2634daaba65a92bc343db36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625692"
---
# <a name="filter-the-source-cube-for-a-mining-structure"></a><span data-ttu-id="ef427-102">Filtrare il cubo di origine per una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="ef427-102">Filter the Source Cube for a Mining Structure</span></span>
  <span data-ttu-id="ef427-103">Quando si crea una struttura di data mining basata sui dati in un modello multidimensionale (un cubo OLAP), è possibile *sezionare* il cubo su cui è basata la struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="ef427-103">When you create a mining structure that is based on data in a multidimensional model (an OLAP cube), you can *slice* the cube that the mining structure is based on.</span></span> <span data-ttu-id="ef427-104">Il sezionamento consente di creare subset di dati, come un filtro da applicare ai dati utilizzati per il training del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="ef427-104">Slicing lets you create subsets of data, as a kind of filter on the data that is used to train the mining model.</span></span>  
  
### <a name="to-slice-a-cube"></a><span data-ttu-id="ef427-105">Per sezionare un cubo</span><span class="sxs-lookup"><span data-stu-id="ef427-105">To slice a cube</span></span>  
  
1.  <span data-ttu-id="ef427-106">In Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] selezionare la scheda **struttura** di data mining o modelli di **data mining** .</span><span class="sxs-lookup"><span data-stu-id="ef427-106">In Data Mining Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], select the **Mining Structure** tab or the **Mining Models** tab.</span></span>  
  
2.  <span data-ttu-id="ef427-107">Scegliere **Definisci sezione del cubo della struttura di data**mining dal menu **modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="ef427-107">On the **Mining Model** menu, select **Define Mining Structure Cube Slice**.</span></span>  
  
     <span data-ttu-id="ef427-108">Verrà visualizzata la finestra di dialogo **Seziona cubo** .</span><span class="sxs-lookup"><span data-stu-id="ef427-108">The **Slice Cube** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="ef427-109">Nella colonna **dimensione** della finestra di dialogo **sezionamento cubo** Selezionare la dimensione che si desidera filtrare.</span><span class="sxs-lookup"><span data-stu-id="ef427-109">In the **Dimension** column of the **Slice Cube** dialog box, select the dimension that you want to filter.</span></span>  
  
4.  <span data-ttu-id="ef427-110">Consente di selezionare un livello di una gerarchia, utilizzando l'elenco nella colonna **gerarchia** .</span><span class="sxs-lookup"><span data-stu-id="ef427-110">Select a level of a hierarchy, using the list in the **Hierarchy** column.</span></span>  
  
5.  <span data-ttu-id="ef427-111">Consente di selezionare un operatore nell'elenco della colonna **operatore** da utilizzare per la compilazione della condizione di filtro.</span><span class="sxs-lookup"><span data-stu-id="ef427-111">Select an operator from the list in the **Operator** column, to use in building the filter condition.</span></span>  
  
6.  <span data-ttu-id="ef427-112">Fare clic sulla casella nella colonna **filtro** .</span><span class="sxs-lookup"><span data-stu-id="ef427-112">Click the box in the **Filter** column.</span></span>  
  
     <span data-ttu-id="ef427-113">Verrà visualizzata una finestra di dialogo contenente tutti i membri al livello specificato della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="ef427-113">A dialog box opens that contains all the members at the specified level of the hierarchy.</span></span>  
  
7.  <span data-ttu-id="ef427-114">Selezionare uno o più membri a cui si desidera applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="ef427-114">Select the member or members on which you want to filter.</span></span>  
  
8.  <span data-ttu-id="ef427-115">Fare clic su **OK** nella finestra di dialogo membro.</span><span class="sxs-lookup"><span data-stu-id="ef427-115">Click **OK** in the member dialog box.</span></span>  
  
9. <span data-ttu-id="ef427-116">Fare clic su **OK** nella finestra di dialogo **Seziona cubo** .</span><span class="sxs-lookup"><span data-stu-id="ef427-116">Click **OK** in the **Slice Cube** dialog box.</span></span>  
  
     <span data-ttu-id="ef427-117">A questo punto, il cubo di origine è filtrato come definito dalla sezione del cubo.</span><span class="sxs-lookup"><span data-stu-id="ef427-117">The source cube is now filtered as defined by the cube slice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef427-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef427-118">See Also</span></span>  
 <span data-ttu-id="ef427-119">[Attività e procedure relative alla struttura di data mining](data-mining/mining-structure-tasks-and-how-tos.md) </span><span class="sxs-lookup"><span data-stu-id="ef427-119">[Mining Structure Tasks and How-tos](data-mining/mining-structure-tasks-and-how-tos.md) </span></span>  
 [<span data-ttu-id="ef427-120">Creare una nuova struttura di data mining OLAP</span><span class="sxs-lookup"><span data-stu-id="ef427-120">Create a New OLAP Mining Structure</span></span>](data-mining/create-a-new-olap-mining-structure.md)  
  
  
