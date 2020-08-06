---
title: Eliminare una tabella (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: be4ed45f-fde3-466c-9869-49bd3ddb505e
author: minewiskan
ms.author: owend
ms.openlocfilehash: c72fa90426440c1be84318a15cf0d761ef16aca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635727"
---
# <a name="delete-a-table-ssas-tabular"></a><span data-ttu-id="a9d8b-102">Eliminare una tabella (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="a9d8b-102">Delete a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="a9d8b-103">In Progettazione modelli è possibile eliminare le tabelle non più necessarie nel database dell'area di lavoro modello.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-103">In the model designer, you can delete tables in your model workspace database that you no longer need.</span></span> <span data-ttu-id="a9d8b-104">L'eliminazione di una tabella non influisce sui dati di origine, ma solo sui dati importati che si stavano utilizzando.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-104">Deleting a table does not affect the original source data, only the data that you imported and were working with.</span></span> <span data-ttu-id="a9d8b-105">Non è possibile annullare l'eliminazione di una tabella.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-105">You cannot undo the deletion of a table.</span></span>  
  
### <a name="to-delete-a-table"></a><span data-ttu-id="a9d8b-106">Per eliminare una tabella</span><span class="sxs-lookup"><span data-stu-id="a9d8b-106">To delete a table</span></span>  
  
-   <span data-ttu-id="a9d8b-107">Fare clic con il pulsante destro del mouse sulla scheda nella parte inferiore di Progettazione modelli per la tabella che si vuole eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-107">Right-click the tab at the bottom of the model designer for the table that you want to delete, and then click **Delete**.</span></span>  
  
## <a name="considerations-when-deleting-tables"></a><span data-ttu-id="a9d8b-108">Considerazioni in caso di eliminazione di tabelle</span><span class="sxs-lookup"><span data-stu-id="a9d8b-108">Considerations when Deleting Tables</span></span>  
  
-   <span data-ttu-id="a9d8b-109">Quando si elimina una tabella, viene eliminata la scheda intera nella quale si trova la tabella.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-109">When you delete a table, the entire tab that the table was on is deleted.</span></span>  
  
-   <span data-ttu-id="a9d8b-110">Se tutte le misura sono associate a tale tabella, anche la definizione della misura sarà eliminata.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-110">If any measures were associated with that table, the definition of the measure will also be deleted.</span></span>  
  
-   <span data-ttu-id="a9d8b-111">Se sono state create alcune colonne calcolate utilizzando quella tabella, anche le colonne in tale tabella vengono eliminate. Nelle colonne calcolate delle altre tabelle in cui vengono utilizzate colonne della tabella eliminata verrà visualizzato un errore.</span><span class="sxs-lookup"><span data-stu-id="a9d8b-111">If you created any calculated columns using that table, columns in that table are also deleted; any calculated columns in other tables that use columns from the deleted table will display an error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d8b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9d8b-112">See Also</span></span>  
 [<span data-ttu-id="a9d8b-113">Tabelle e colonne &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="a9d8b-113">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tables-and-columns-ssas-tabular.md)  
  
  
