---
title: Eliminare relazioni (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d40e3f05-54e8-4c4b-807a-0b06f446079b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3c63324918eb6919ce0abd65b5ee0765f9d7243b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712524"
---
# <a name="delete-relationships-ssas-tabular"></a><span data-ttu-id="c5f40-102">Eliminare relazioni (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="c5f40-102">Delete Relationships (SSAS Tabular)</span></span>
  <span data-ttu-id="c5f40-103">È possibile eliminare relazioni esistenti utilizzando Progettazione modelli nella Vista diagramma o la finestra di dialogo Gestisci relazioni.</span><span class="sxs-lookup"><span data-stu-id="c5f40-103">You can delete existing relationships by using the model designer in Diagram View or by using the Manage Relationships dialog box.</span></span> <span data-ttu-id="c5f40-104">Per informazioni sulla modalità d'uso delle relazioni nei modelli tabulari, vedere [Relazioni &#40;SSAS tabulare&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c5f40-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="considerations-for-deleting-relationships"></a><span data-ttu-id="c5f40-105">Considerazioni sull'eliminazione di relazioni</span><span class="sxs-lookup"><span data-stu-id="c5f40-105">Considerations for Deleting Relationships</span></span>  
 <span data-ttu-id="c5f40-106">Quando si decide se eliminare una relazione, tenere presente i fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c5f40-106">Keep the following issues in mind when deciding whether to delete a relationship:</span></span>  
  
-   <span data-ttu-id="c5f40-107">L'eliminazione di una relazione non può essere annullata in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="c5f40-107">There is no way to undo the deletion of a relationship.</span></span> <span data-ttu-id="c5f40-108">È possibile creare nuovamente la relazione, tuttavia questa azione richiede un ricalcolo completo delle formule nel modello.</span><span class="sxs-lookup"><span data-stu-id="c5f40-108">You can re-create the relationship, but this action requires a complete recalculation of formulas in the model.</span></span> <span data-ttu-id="c5f40-109">Eseguire pertanto sempre un controllo prima di eliminare una relazione utilizzata nelle formule.</span><span class="sxs-lookup"><span data-stu-id="c5f40-109">Therefore, always check first before deleting a relationship that is used in formulas.</span></span>  
  
-   <span data-ttu-id="c5f40-110">L'eliminazione di una relazione tra due tabelle può provocare errori nelle formule che fanno riferimento a queste tabelle.</span><span class="sxs-lookup"><span data-stu-id="c5f40-110">Deleting a relationship between two tables can cause errors in formulas that reference these tables.</span></span>  
  
-   <span data-ttu-id="c5f40-111">La funzione Data Analysis Expression (DAX) RELATED consente di utilizzare le relazioni tra tabelle per cercare valori correlati in un'altra tabella</span><span class="sxs-lookup"><span data-stu-id="c5f40-111">The Data Analysis Expression (DAX) RELATED function uses the relationships between tables to look up related values in another table.</span></span> <span data-ttu-id="c5f40-112">e, dopo l'eliminazione della relazione, verranno restituiti valori diversi.</span><span class="sxs-lookup"><span data-stu-id="c5f40-112">It will return different results after the relationship is deleted.</span></span> <span data-ttu-id="c5f40-113">Per ulteriori informazioni, vedere la funzione RELATED (DAX).</span><span class="sxs-lookup"><span data-stu-id="c5f40-113">For more information, see the RELATED Function (DAX).</span></span>  
  
-   <span data-ttu-id="c5f40-114">Oltre a cambiare i risultati delle formule e delle tabelle pivot, sia la creazione sia l'eliminazione delle relazioni determinano il ricalcolo della cartella di lavoro, operazione che può richiedere tempo.</span><span class="sxs-lookup"><span data-stu-id="c5f40-114">In addition to changing PivotTable and formula results, both the creation and deletion of relationships will cause the workbook to be recalculated, which can take some time.</span></span>  
  
## <a name="delete-relationships"></a><span data-ttu-id="c5f40-115">Eliminare relazioni</span><span class="sxs-lookup"><span data-stu-id="c5f40-115">Delete Relationships</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-diagram-view"></a><span data-ttu-id="c5f40-116">Per eliminare una relazione tramite Vista diagramma</span><span class="sxs-lookup"><span data-stu-id="c5f40-116">To delete a relationship by using Diagram View</span></span>  
  
1.  <span data-ttu-id="c5f40-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]scegliere **Vista modelli** dal menu **Modello**, quindi fare clic su **Vista diagramma**.</span><span class="sxs-lookup"><span data-stu-id="c5f40-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, then point to **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="c5f40-118">Fare clic con il pulsante destro del mouse su una linea della relazione tra le due tabelle, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="c5f40-118">Right-click a relationship line between two tables, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-relationship-by-using-the-manage-relationships-dialog-box"></a><span data-ttu-id="c5f40-119">Per eliminare una relazione utilizzando la finestra di dialogo Gestisci relazioni</span><span class="sxs-lookup"><span data-stu-id="c5f40-119">To delete a relationship by using the Manage Relationships dialog box</span></span>  
  
1.  <span data-ttu-id="c5f40-120">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]scegliere **Gestisci relazioni** dal menu **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="c5f40-120">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Manage Relationships**.</span></span>  
  
2.  <span data-ttu-id="c5f40-121">Nella finestra di dialogo **Gestisci relazioni** selezionare una o più relazioni dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="c5f40-121">In the **Manage Relationships** dialog box, select one or more relationships from the list.</span></span>  
  
     <span data-ttu-id="c5f40-122">Per selezionare più relazioni, tenere premuto CTRL mentre si fa clic su ciascuna relazione.</span><span class="sxs-lookup"><span data-stu-id="c5f40-122">To select multiple relationships, hold down CTRL while you click each relationship.</span></span>  
  
3.  <span data-ttu-id="c5f40-123">Fare clic su **Elimina relazione**.</span><span class="sxs-lookup"><span data-stu-id="c5f40-123">Click **Delete Relationship**.</span></span>  
  
4.  <span data-ttu-id="c5f40-124">Fare clic su **Chiudi** nella finestra di dialogo **Gestisci relazioni**.</span><span class="sxs-lookup"><span data-stu-id="c5f40-124">In the **Manage Relationships** dialog box, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f40-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5f40-125">See Also</span></span>  
 <span data-ttu-id="c5f40-126">[Relazioni &#40;SSAS tabulare&#41;](relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="c5f40-126">[Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="c5f40-127">Creare una relazione tra due tabelle &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="c5f40-127">Create a Relationship Between Two Tables &#40;SSAS Tabular&#41;</span></span>](create-a-relationship-between-two-tables-ssas-tabular.md)  
  
  
