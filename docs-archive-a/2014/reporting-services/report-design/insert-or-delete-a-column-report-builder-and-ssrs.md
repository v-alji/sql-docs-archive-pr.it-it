---
title: Inserire o eliminare una colonna (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e9db79e2-7e7d-4359-a706-cb746c94182a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9a6f782dbb6cc1024583926aafe4bab1cfe2d042
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723431"
---
# <a name="insert-or-delete-a-column-report-builder-and-ssrs"></a><span data-ttu-id="64d06-102">Inserire o eliminare una colonna (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="64d06-102">Insert or Delete a Column (Report Builder and SSRS)</span></span>
  <span data-ttu-id="64d06-103">È possibile aggiungere o eliminare colonne in un'area dati Tablix.</span><span class="sxs-lookup"><span data-stu-id="64d06-103">You can add or delete columns in a tablix data region.</span></span> <span data-ttu-id="64d06-104">L'area dati Tablix può essere una tabella, una matrice o un elenco.</span><span class="sxs-lookup"><span data-stu-id="64d06-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="64d06-105">Le procedure riportate di seguito non sono applicabili alle aree dati del grafico e del misuratore.</span><span class="sxs-lookup"><span data-stu-id="64d06-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="64d06-106">In un'area dati Tablix è possibile aggiungere colonne associate a un gruppo (interne a un gruppo) o non associate a un gruppo (esterne a un gruppo).</span><span class="sxs-lookup"><span data-stu-id="64d06-106">In a tablix data region, you can add columns that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="64d06-107">Una colonna interna a un gruppo viene ripetuta una volta per ogni valore di gruppo univoco.</span><span class="sxs-lookup"><span data-stu-id="64d06-107">A column that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="64d06-108">Ad esempio, una colonna all'interno di un gruppo che si basa sul valore di una colonna di dati contenente nomi di colori, viene ripetuta una volta per ogni nome di colore distinto.</span><span class="sxs-lookup"><span data-stu-id="64d06-108">For example, a column inside a group based the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="64d06-109">Per i gruppi nidificati, una colonna può essere esterna al gruppo figlio ma interna al gruppo padre.</span><span class="sxs-lookup"><span data-stu-id="64d06-109">For nested groups, a column can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="64d06-110">In questo caso, la riga viene ripetuta una volta per ogni valore univoco nel gruppo padre.</span><span class="sxs-lookup"><span data-stu-id="64d06-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-that-the-row-and-column-handles-appear"></a><span data-ttu-id="64d06-111">Per selezionare un'area dati in modo da visualizzare gli handle di riga e di colonna</span><span class="sxs-lookup"><span data-stu-id="64d06-111">To select a data region so that the row and column handles appear</span></span>  
  
-   <span data-ttu-id="64d06-112">In visualizzazione della struttura fare clic sull'angolo superiore sinistro dell'area dati Tablix in modo da visualizzare gli handle di colonna e di riga sopra e accanto all'area.</span><span class="sxs-lookup"><span data-stu-id="64d06-112">In Design view, click the upper left corner of the tablix data region, so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="64d06-113">Per ulteriori informazioni sulle aree dell'area dati, vedere la pagina relativa agli [elenchi &#40;Generatore report e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="64d06-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-column-in-a-selected-data-region"></a><span data-ttu-id="64d06-114">Per inserire una colonna in un'area dati selezionata</span><span class="sxs-lookup"><span data-stu-id="64d06-114">To insert a column in a selected data region</span></span>  
  
-   <span data-ttu-id="64d06-115">Fare clic con il pulsante destro del mouse su un handle di colonna in corrispondenza del quale si vuole inserire una colonna, scegliere **Inserisci colonna**e quindi fare clic su **A sinistra** o **A destra**.</span><span class="sxs-lookup"><span data-stu-id="64d06-115">Right-click a column handle where you want to insert a column, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
     <span data-ttu-id="64d06-116">-- o --</span><span class="sxs-lookup"><span data-stu-id="64d06-116">-- or --</span></span>  
  
-   <span data-ttu-id="64d06-117">Fare clic con il pulsante destro del mouse su una cella nell'area dati in corrispondenza della quale si vuole inserire una colonna, scegliere **Inserisci colonna**e quindi fare clic su **A sinistra** o **A destra**.</span><span class="sxs-lookup"><span data-stu-id="64d06-117">Right-click a cell in the data region where you want to insert a row, click **Insert Column**, and then click **Left** or **Right**.</span></span>  
  
### <a name="to-delete-a-column-from-a-selected-data-region"></a><span data-ttu-id="64d06-118">Per eliminare una colonna da un'area dati selezionata</span><span class="sxs-lookup"><span data-stu-id="64d06-118">To delete a column from a selected data region</span></span>  
  
-   <span data-ttu-id="64d06-119">Selezionare la colonna o le colonne da eliminare, fare clic con il pulsante destro del mouse sull'handle di una delle colonne selezionate e quindi scegliere **Elimina colonne**.</span><span class="sxs-lookup"><span data-stu-id="64d06-119">Select the column or columns that you want to delete, right-click the handle for one of the columns you selected, and then click **Delete Columns**.</span></span>  
  
     <span data-ttu-id="64d06-120">-- o --</span><span class="sxs-lookup"><span data-stu-id="64d06-120">-- or --</span></span>  
  
-   <span data-ttu-id="64d06-121">Fare clic con il pulsante destro del mouse su una cella nell'area dati in corrispondenza della quale si vuole eliminare una colonna e quindi scegliere **Elimina colonne**.</span><span class="sxs-lookup"><span data-stu-id="64d06-121">Right-click a cell in the data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
### <a name="to-insert-a-column-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="64d06-122">Per inserire una colonna in un gruppo di un'area dati selezionata</span><span class="sxs-lookup"><span data-stu-id="64d06-122">To insert a column in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="64d06-123">Fare clic con il pulsante destro del mouse su una cella di un gruppo di colonne nell'area dei gruppi di colonne di un'area dati Tablix in corrispondenza della quale si vuole inserire una colonna, scegliere **Inserisci colonna**e quindi fare clic su **A sinistra - Gruppo esterno**, **A sinistra - Gruppo interno**, **A destra - Gruppo interno**o **A destra - Gruppo esterno**.</span><span class="sxs-lookup"><span data-stu-id="64d06-123">Right-click a column group cell in the column group area of a tablix data region where you want to insert a column, click **Insert Column**, and then click **Left - Outside Group**, **Left - Inside Group**, **Right - Inside Group**, or **Right - Outside Group**.</span></span>  
  
     <span data-ttu-id="64d06-124">Verrà aggiunta una colonna all'interno o all'esterno del gruppo rappresentato dalla cella del gruppo di colonne selezionata mediante clic.</span><span class="sxs-lookup"><span data-stu-id="64d06-124">A column is added either inside or outside the group represented by the column group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-column-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="64d06-125">Per eliminare una colonna da un gruppo di un'area dati selezionata</span><span class="sxs-lookup"><span data-stu-id="64d06-125">To delete a column from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="64d06-126">Fare clic con il pulsante destro del mouse su una cella di un gruppo di colonne nell'area dei gruppi di colonne di un'area dati Tablix in corrispondenza della quale si vuole eliminare una colonna e quindi scegliere **Elimina colonne**.</span><span class="sxs-lookup"><span data-stu-id="64d06-126">Right-click a column group cell in the column group area of a tablix data region where you want to delete a column, and then click **Delete Columns**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d06-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64d06-127">See Also</span></span>  
 <span data-ttu-id="64d06-128">[Informazioni sui gruppi &#40;Generatore report e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64d06-128">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="64d06-129">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64d06-129">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="64d06-130">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64d06-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="64d06-131">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64d06-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="64d06-132">[Elenchi &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="64d06-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="64d06-133">Elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="64d06-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
