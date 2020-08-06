---
title: Inserire o eliminare una riga (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: b9642af3-b3ae-4f78-b0be-8f96b79fc313
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fdec24801d1fae3b95c7d75acb5a3add650d523b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723424"
---
# <a name="insert-or-delete-a-row-report-builder-and-ssrs"></a><span data-ttu-id="fd0b8-102">Inserire o eliminare una riga (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="fd0b8-102">Insert or Delete a Row (Report Builder and SSRS)</span></span>
  <span data-ttu-id="fd0b8-103">È possibile aggiungere o eliminare righe in un'area dati Tablix.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-103">You can add or delete rows in a tablix data region.</span></span> <span data-ttu-id="fd0b8-104">L'area dati Tablix può essere una tabella, una matrice o un elenco.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-104">The tablix data region can be a table, a matrix, or a list.</span></span> <span data-ttu-id="fd0b8-105">Le procedure riportate di seguito non sono applicabili alle aree dati del grafico e del misuratore.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-105">The following procedures do not apply to the chart and gauge data regions.</span></span>  
  
 <span data-ttu-id="fd0b8-106">In un'area dati Tablix è possibile aggiungere righe associate a un gruppo (interne a un gruppo) o non associate a un gruppo (esterne a un gruppo).</span><span class="sxs-lookup"><span data-stu-id="fd0b8-106">In a tablix data region, you can add rows that are associated with a group (inside a group) or that are not associated with a group (outside a group).</span></span> <span data-ttu-id="fd0b8-107">Una riga interna a un gruppo viene ripetuta una volta per ogni valore di gruppo univoco.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-107">A row that is inside a group repeats once per unique group value.</span></span> <span data-ttu-id="fd0b8-108">Ad esempio, una riga all'interno di un gruppo che si basa sul valore di una colonna di dati contenente nomi di colori, viene ripetuta una volta per ogni nome di colore distinto.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-108">For example, a row inside a group based on the value in a data column that contains color names, repeats once per distinct color name.</span></span> <span data-ttu-id="fd0b8-109">Per i gruppi nidificati, una riga può essere esterna al gruppo figlio ma interna al gruppo padre.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-109">For nested groups, a row can be outside the child group but inside the parent group.</span></span> <span data-ttu-id="fd0b8-110">In questo caso, la riga viene ripetuta una volta per ogni valore univoco nel gruppo padre.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-110">In this case, the row repeats once for each unique value in the parent group.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-select-a-data-region-so-the-row-and-column-handles-appear"></a><span data-ttu-id="fd0b8-111">Per selezionare un'area dati in modo da visualizzare gli handle di riga e di colonna</span><span class="sxs-lookup"><span data-stu-id="fd0b8-111">To select a data region so the row and column handles appear</span></span>  
  
-   <span data-ttu-id="fd0b8-112">In visualizzazione Progettazione fare clic sull'angolo superiore sinistro dell'area dati Tablix in modo da visualizzare gli handle di colonna e di riga sopra e accanto all'area.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-112">In Design view, click the upper left corner of the tablix data region so that column and row handles appear above and next to it.</span></span>  
  
     <span data-ttu-id="fd0b8-113">Per ulteriori informazioni sulle aree dell'area dati, vedere la pagina relativa agli [elenchi &#40;Generatore report e SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fd0b8-113">For more information about data region areas, see [Lists &#40;Report Builder and SSRS&#41;](tables-matrices-and-lists-report-builder-and-ssrs.md).</span></span>  
  
### <a name="to-insert-a-row-in-a-selected-data-region"></a><span data-ttu-id="fd0b8-114">Per inserire una riga in un'area dati selezionata</span><span class="sxs-lookup"><span data-stu-id="fd0b8-114">To insert a row in a selected data region</span></span>  
  
-   <span data-ttu-id="fd0b8-115">Fare clic con il pulsante destro del mouse su un handle di riga in corrispondenza del quale si desidera inserire una riga, scegliere **Inserisci riga**, quindi fare clic su **Sopra** o **Sotto**.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-115">Right-click a row handle where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
     <span data-ttu-id="fd0b8-116">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="fd0b8-116">\- or -</span></span>  
  
-   <span data-ttu-id="fd0b8-117">Fare clic con il pulsante destro del mouse su una cella nell'area dati in corrispondenza della quale si desidera inserire una riga, scegliere **Inserisci riga**, quindi fare clic su **Sopra** o **Sotto**.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-117">Right-click a cell in the data region where you want to insert a row, click **Insert Row**, and then click **Above** or **Below**.</span></span>  
  
### <a name="to-delete-a-row-from-a-selected-data-region"></a><span data-ttu-id="fd0b8-118">Per eliminare una riga da un'area dati selezionata</span><span class="sxs-lookup"><span data-stu-id="fd0b8-118">To delete a row from a selected data region</span></span>  
  
-   <span data-ttu-id="fd0b8-119">Selezionare la riga o le righe che si desidera eliminare, fare clic con il pulsante destro del mouse sull'handle di una delle righe selezionate, quindi scegliere **Elimina righe**.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-119">Select the row or rows that you want to delete, right-click the handle for one of the rows you selected, and then click **Delete Rows**.</span></span>  
  
     <span data-ttu-id="fd0b8-120">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="fd0b8-120">\- or -</span></span>  
  
-   <span data-ttu-id="fd0b8-121">Fare clic con il pulsante destro del mouse su una cella nell'area dati in corrispondenza della quale si desidera eliminare una riga, quindi scegliere **Elimina righe**.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-121">Right-click a cell in the data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
### <a name="to-insert-a-row-in-a-group-in-a-selected-data-region"></a><span data-ttu-id="fd0b8-122">Per inserire una riga in un gruppo di un'area dati selezionata</span><span class="sxs-lookup"><span data-stu-id="fd0b8-122">To insert a row in a group in a selected data region</span></span>  
  
-   <span data-ttu-id="fd0b8-123">Fare clic con il pulsante destro del mouse su una cella di un gruppo di righe nell'area dei gruppi di righe di un'area dati Tablix in corrispondenza della quale si desidera inserire una riga, scegliere **Inserisci riga**, quindi fare clic su **Sopra - Gruppo esterno**, **Sopra - Gruppo interno**, **Sotto - Gruppo interno**o **Sotto - Gruppo esterno**.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-123">Right-click a row group cell in the row group area of a tablix data region where you want to insert a row, click **Insert Row**, and then click **Above - Outside Group**, **Above - Inside Group**, **Below - Inside Group**, or **Below - Outside Group**.</span></span>  
  
     <span data-ttu-id="fd0b8-124">Verrà aggiunta una riga all'interno o all'esterno del gruppo rappresentato dalla cella del gruppo di righe selezionata mediante clic.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-124">A row is added either inside or outside the group represented by the row group cell you clicked on.</span></span>  
  
### <a name="to-delete-a-row-from-a-group-in-a-selected-data-region"></a><span data-ttu-id="fd0b8-125">Per eliminare una riga da un gruppo di un'area dati selezionata</span><span class="sxs-lookup"><span data-stu-id="fd0b8-125">To delete a row from a group in a selected data region</span></span>  
  
-   <span data-ttu-id="fd0b8-126">Fare clic con il pulsante destro del mouse su una cella di un gruppo di righe nell'area dei gruppi di righe di un'area dati Tablix in corrispondenza della quale si desidera eliminare una riga, quindi scegliere **Elimina righe**.</span><span class="sxs-lookup"><span data-stu-id="fd0b8-126">Right-click a row group cell in the row group area of a tablix data region where you want to delete a row, and then click **Delete Rows**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd0b8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd0b8-127">See Also</span></span>  
 <span data-ttu-id="fd0b8-128">[Area dati Tablix &#40;Generatore report e SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fd0b8-128">[Tablix Data Region &#40;Report Builder and SSRS&#41;](../tablix-data-region-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fd0b8-129">[Informazioni sui gruppi &#40;Generatore report e SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fd0b8-129">[Understanding Groups &#40;Report Builder and SSRS&#41;](understanding-groups-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fd0b8-130">[Tabelle &#40;Generatore report e SSRS&#41;](tables-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fd0b8-130">[Tables &#40;Report Builder  and SSRS&#41;](tables-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fd0b8-131">[Matrici &#40;Generatore report e SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fd0b8-131">[Matrices &#40;Report Builder and SSRS&#41;](create-a-matrix-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="fd0b8-132">[Elenchi &#40;Generatore report e SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="fd0b8-132">[Lists &#40;Report Builder and SSRS&#41;](create-invoices-and-forms-with-lists-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="fd0b8-133">Elenchi &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fd0b8-133">Lists &#40;Report Builder and SSRS&#41;</span></span>](tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  
