---
title: Finestra di dialogo Filtra membri (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensiondesigner.filtermembers.f1
helpviewer_keywords:
- Filter Members dialog box
ms.assetid: 52c6da1d-9fb5-4dbc-bffa-248d11cd337c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 66980b1afe9d4eed353ae18c37ed1fdd052e62b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623563"
---
# <a name="filter-members-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="b45d5-102">Finestra di dialogo Filtra membri (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="b45d5-102">Filter Members Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="b45d5-103">Usare la finestra di dialogo **Filtra membri** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] per filtrare i membri della dimensione in base alla didascalia dei membri, al nome dei membri, al nome univoco dei membri, al valore di colonna chiave o al valore di colonna valore per il livello corrente quando si visualizza una dimensione nella scheda **Esplorazione** di **Progettazione dimensioni**.</span><span class="sxs-lookup"><span data-stu-id="b45d5-103">Use the **Filter Members** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to filter dimension members by member caption, member name, member unique name, key column value, or value column value for the current level while browsing a dimension in the **Browser** tab of **Dimension Designer**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b45d5-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b45d5-104">Options</span></span>  
  
|<span data-ttu-id="b45d5-105">Termine</span><span class="sxs-lookup"><span data-stu-id="b45d5-105">Term</span></span>|<span data-ttu-id="b45d5-106">Definizione</span><span class="sxs-lookup"><span data-stu-id="b45d5-106">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="b45d5-107">**Espressione filtro**</span><span class="sxs-lookup"><span data-stu-id="b45d5-107">**Filter expression**</span></span>|<span data-ttu-id="b45d5-108">Consente di visualizzare una griglia di proprietà, operatori e valori utilizzati per creare un'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="b45d5-108">Displays a grid of properties, operators, and values used to construct a filter expression.</span></span> <span data-ttu-id="b45d5-109">Si noti che non è possibile rimuovere una riga dopo averla aggiunta.</span><span class="sxs-lookup"><span data-stu-id="b45d5-109">Note that after a row is added, it cannot be removed.</span></span> <span data-ttu-id="b45d5-110">Per specificare una nuova espressione di filtro è necessario chiudere e riaprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b45d5-110">You must close and reopen the dialog box to specify a new filter expression.</span></span> <span data-ttu-id="b45d5-111">La griglia include le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="b45d5-111">The grid contains the following columns:</span></span><br /><br /> <span data-ttu-id="b45d5-112">**Proprietà**: selezionare la proprietà del membro da utilizzare per l'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="b45d5-112">**Property**: Select the property of the member to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="b45d5-113">**Operatore**: selezionare l'operatore da utilizzare per l'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="b45d5-113">**Operator**: Select the operator to use for the filter expression.</span></span><br /><br /> <span data-ttu-id="b45d5-114">**Valore**: digitare il valore della proprietà selezionata in **Proprietà** da valutare utilizzando l'operatore specificato in **operatore**.</span><span class="sxs-lookup"><span data-stu-id="b45d5-114">**Value**: Type the value of the property selected in **Property** to evaluate using the operator specified in **Operator**.</span></span>|  
|<span data-ttu-id="b45d5-115">**Riquadro Test**</span><span class="sxs-lookup"><span data-stu-id="b45d5-115">**Test pane**</span></span>|<span data-ttu-id="b45d5-116">Quando si fa clic sul pulsante **Test** questo riquadro visualizza i membri restituiti dall'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="b45d5-116">When **Test** is clicked, this pane displays the members returned by the filter expression.</span></span> <span data-ttu-id="b45d5-117">Se non viene restituito alcun membro usando i criteri specificati in **Espressione filtro**verrà visualizzato un avviso.</span><span class="sxs-lookup"><span data-stu-id="b45d5-117">If no members are returned using the criteria specified in **Filter expression**, a warning is displayed.</span></span>|  
|<span data-ttu-id="b45d5-118">**Test**</span><span class="sxs-lookup"><span data-stu-id="b45d5-118">**Test**</span></span>|<span data-ttu-id="b45d5-119">Fare clic su questo pulsante per eseguire un test dei criteri specificati in **Espressione filtro**.</span><span class="sxs-lookup"><span data-stu-id="b45d5-119">Click to test the criteria specified in **Filter expression**.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b45d5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b45d5-120">See Also</span></span>  
 <span data-ttu-id="b45d5-121">[Finestre di progettazione e finestre di dialogo Analysis Services &#40;dati multidimensionali&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b45d5-121">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b45d5-122">Browser &#40;Progettazione dimensioni&#41; &#40;Analysis Services Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="b45d5-122">Browser &#40;Dimension Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;</span></span>](browser-dimension-designer-analysis-services-multidimensional-data.md)  
  
  
