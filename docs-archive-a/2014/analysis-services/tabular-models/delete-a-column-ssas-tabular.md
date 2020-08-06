---
title: Eliminare una colonna (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 703db83b-e554-450e-813e-23ad08c1cdad
author: minewiskan
ms.author: owend
ms.openlocfilehash: 06af0b7fd9879661db95bb2073cced545bb4eef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629626"
---
# <a name="delete-a-column-ssas-tabular"></a><span data-ttu-id="93a59-102">Eliminare una colonna (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="93a59-102">Delete a Column (SSAS Tabular)</span></span>
  <span data-ttu-id="93a59-103">In questo argomento viene descritto come eliminare una colonna da una tabella di modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="93a59-103">This topic describes how to delete a column from a tabular model table.</span></span>  
  
## <a name="delete-a-model-table-column"></a><span data-ttu-id="93a59-104">Eliminare una colonna dalla tabella del modello</span><span class="sxs-lookup"><span data-stu-id="93a59-104">Delete a Model Table Column</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="93a59-105">L'eliminazione di una colonna da una tabella del modello non elimina la colonna da una definizione della query della partizione.</span><span class="sxs-lookup"><span data-stu-id="93a59-105">Deleting a column from a model table does not delete the column from a partition query definition.</span></span> <span data-ttu-id="93a59-106">Se la colonna che si desidera eliminare fa parte di una partizione, è necessario eliminare manualmente la colonna dalla definizione della query della partizione.</span><span class="sxs-lookup"><span data-stu-id="93a59-106">If the column you are deleting is part of a partition, you must manually delete the column from the partition query definition.</span></span> <span data-ttu-id="93a59-107">Se non si elimina la colonna dalla definizione della query della partizione, durante le operazioni di elaborazione verranno eseguite query sulla colonna e restituiti dati che tuttavia non saranno popolati nella tabella del modello.</span><span class="sxs-lookup"><span data-stu-id="93a59-107">Failure to delete the column from the partition query definition will cause the column to be queried and data returned, but not populated to the model table, during processing operations.</span></span> <span data-ttu-id="93a59-108">Per altre informazioni, vedere [Partizioni &#40;SSAS tabulare&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="93a59-108">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-delete-a-model-table-column"></a><span data-ttu-id="93a59-109">Per eliminare una colonna dalla tabella del modello</span><span class="sxs-lookup"><span data-stu-id="93a59-109">To delete a model table column</span></span>  
  
-   <span data-ttu-id="93a59-110">In Progettazione modelli, nella tabella contenente la colonna che si desidera eliminare, fare clic con il pulsante destro del mouse su tale colonna, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="93a59-110">In the model designer, in the table that contains the column you want to delete, right-click on the column, and then click **Delete**.</span></span>  
  
#### <a name="to-delete-a-model-table-column-by-using-the-table-properties-dialog-box"></a><span data-ttu-id="93a59-111">Per eliminare una colonna dalla tabella del modello tramite la finestra di dialogo Proprietà tabella</span><span class="sxs-lookup"><span data-stu-id="93a59-111">To delete a model table column by using the Table Properties dialog box</span></span>  
  
1.  <span data-ttu-id="93a59-112">In Progettazione modelli fare clic sulla tabella contenente la colonna che si desidera eliminare, quindi scegliere **Proprietà tabella** dal menu  **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="93a59-112">In the model designer, click on the table which contains the column you want to delete, then click the **Table** menu, and then click  **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="93a59-113">In **Nomi colonne da**selezionare **Modello** (*per usare nomi delle colonna della tabella del modello, se diversi dall'origine*).</span><span class="sxs-lookup"><span data-stu-id="93a59-113">In **Column names from**, select **Model** (*to use model table column names, if different from source*).</span></span>  
  
3.  <span data-ttu-id="93a59-114">Nella finestra di anteprima della tabella nella finestra di dialogo **Modifica proprietà tabella** deselezionare la colonna che si desidera eliminare, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="93a59-114">In the **Edit Table Properties** dialog box, in the table preview window, uncheck the column you want to delete, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93a59-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93a59-115">See Also</span></span>  
 <span data-ttu-id="93a59-116">[Aggiungere colonne a una tabella &#40;SSAS tabulare&#41;](add-columns-to-a-table-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="93a59-116">[Add Columns to a Table &#40;SSAS Tabular&#41;](add-columns-to-a-table-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="93a59-117">Partizioni &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="93a59-117">Partitions &#40;SSAS Tabular&#41;</span></span>](partitions-ssas-tabular.md)  
  
  
