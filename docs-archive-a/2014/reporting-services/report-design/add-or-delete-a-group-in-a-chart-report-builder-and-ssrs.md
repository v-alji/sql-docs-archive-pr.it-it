---
title: Aggiungere o eliminare un gruppo in un grafico (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0445b0ac-acae-4462-80fb-fe9735ac66db
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2ac558ccbd8855018877228b2b38debf769f1573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723459"
---
# <a name="add-or-delete-a-group-in-a-chart-report-builder-and-ssrs"></a><span data-ttu-id="42256-102">Aggiungere o eliminare un gruppo in un grafico (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="42256-102">Add or Delete a Group in a Chart (Report Builder and SSRS)</span></span>
  <span data-ttu-id="42256-103">Fare clic nell'area dati del grafico per visualizzare il riquadro **dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="42256-103">Click in the chart data region to display the **Chart Data** pane.</span></span> <span data-ttu-id="42256-104">Creare gruppi trascinando i campi del set di dati nelle aree **Gruppi di categorie** e **Gruppi di serie** .</span><span class="sxs-lookup"><span data-stu-id="42256-104">Create groups by dragging dataset fields to the **Category Groups** and **Series Groups** areas.</span></span> <span data-ttu-id="42256-105">Per aggiungere gruppi nidificati, aggiungere più campi all'area.</span><span class="sxs-lookup"><span data-stu-id="42256-105">To add nested groups, add multiple fields to the area.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-parent-or-child-group-to-a-chart"></a><span data-ttu-id="42256-106">Per aggiungere un gruppo padre o figlio a un grafico</span><span class="sxs-lookup"><span data-stu-id="42256-106">To add a parent or child group to a chart</span></span>  
  
1.  <span data-ttu-id="42256-107">Nell'area di progettazione del report fare clic in un punto qualsiasi del grafico per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="42256-107">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="42256-108">Viene visualizzato il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="42256-108">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="42256-109">Trascinare un campo dalla finestra di dialogo **Dati report** nell'area **Gruppi di categorie** o **Gruppi di serie** .</span><span class="sxs-lookup"><span data-stu-id="42256-109">Drag a field from the **Report Data** window to the **Category Groups** or **Series Groups** area.</span></span> <span data-ttu-id="42256-110">Per aggiungere un gruppo padre, posizionare il cursore prima di un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="42256-110">To add a parent group, position the cursor in front of an existing group.</span></span> <span data-ttu-id="42256-111">Per aggiungere un gruppo figlio, posizionare il cursore dopo un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="42256-111">To add a child group, position the cursor after an existing group.</span></span>  
  
### <a name="to-edit-a-category-group-on-a-chart"></a><span data-ttu-id="42256-112">Per modificare un gruppo di categorie su un grafico</span><span class="sxs-lookup"><span data-stu-id="42256-112">To edit a category group on a chart</span></span>  
  
1.  <span data-ttu-id="42256-113">Nell'area di progettazione del report fare clic in un punto qualsiasi del grafico per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="42256-113">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="42256-114">Viene visualizzato il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="42256-114">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="42256-115">Fare clic con il pulsante destro del mouse sul gruppo nell'area **Gruppi di categorie** e quindi fare clic su **Proprietà gruppo categorie**.</span><span class="sxs-lookup"><span data-stu-id="42256-115">Right-click the group in the **Category Groups** area, and then click **Category Group Properties**.</span></span>  
  
3.  <span data-ttu-id="42256-116">Aggiungere o rimuovere espressioni di raggruppamento, filtri, espressioni di ordinamento e variabili di gruppo.</span><span class="sxs-lookup"><span data-stu-id="42256-116">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-series-group-on-a-chart"></a><span data-ttu-id="42256-117">Per modificare un gruppo di serie su un grafico</span><span class="sxs-lookup"><span data-stu-id="42256-117">To edit a series group on a chart</span></span>  
  
1.  <span data-ttu-id="42256-118">Nell'area di progettazione del report fare clic in un punto qualsiasi del grafico per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="42256-118">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="42256-119">Viene visualizzato il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="42256-119">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="42256-120">Fare clic con il pulsante destro del mouse sul gruppo nell'area **Gruppi di serie** e quindi scegliere **Proprietà gruppo serie**.</span><span class="sxs-lookup"><span data-stu-id="42256-120">Right-click the group in the **Series Groups** area, and then click **Series Group Properties**.</span></span>  
  
3.  <span data-ttu-id="42256-121">Aggiungere o rimuovere espressioni di raggruppamento, filtri, espressioni di ordinamento e variabili di gruppo.</span><span class="sxs-lookup"><span data-stu-id="42256-121">Add or remove group expressions, filters, sort expressions, and group variables.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-group-from-a-chart"></a><span data-ttu-id="42256-122">Per eliminare un gruppo da un grafico</span><span class="sxs-lookup"><span data-stu-id="42256-122">To delete a group from a chart</span></span>  
  
1.  <span data-ttu-id="42256-123">Nell'area di progettazione del report fare clic in un punto qualsiasi del grafico per selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="42256-123">On the report design surface, click anywhere in the chart to select it.</span></span> <span data-ttu-id="42256-124">Viene visualizzato il riquadro **Dati grafico** .</span><span class="sxs-lookup"><span data-stu-id="42256-124">The **Chart Data** pane appears.</span></span>  
  
2.  <span data-ttu-id="42256-125">Fare clic con il pulsante destro del mouse sul gruppo nell'area **Gruppi di categorie** o **Gruppi di serie** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="42256-125">Right-click the group in the **Category Groups** or **Series Groups** area, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42256-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42256-126">See Also</span></span>  
 [<span data-ttu-id="42256-127">Grafici &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="42256-127">Charts &#40;Report Builder and SSRS&#41;</span></span>](charts-report-builder-and-ssrs.md)  
  
  
