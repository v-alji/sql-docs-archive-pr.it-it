---
title: Rimuovere colonne da una struttura di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- removing columns
- deleting columns
- columns [data mining], mining structure columns
ms.assetid: 41073ffe-9351-416b-9f0c-62634bc213f9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 44ad1de08d57d00fd9798e1ceeddb85d146d7111
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623598"
---
# <a name="remove-columns-from-a-mining-structure"></a><span data-ttu-id="995a5-102">Rimuovere colonne da una struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="995a5-102">Remove Columns from a Mining Structure</span></span>
  <span data-ttu-id="995a5-103">È possibile utilizzare Progettazione modelli di data mining per rimuovere le colonne da una struttura di data mining dopo averla creata.</span><span class="sxs-lookup"><span data-stu-id="995a5-103">You can use Data Mining Designer to remove columns from a mining structure after the structure has already been created.</span></span> <span data-ttu-id="995a5-104">I motivi per cui rimuovere una colonna della struttura di data mining possono includere i seguenti:</span><span class="sxs-lookup"><span data-stu-id="995a5-104">Reasons to remove a mining structure column might include the following:</span></span>  
  
-   <span data-ttu-id="995a5-105">La struttura di data mining contiene più copie di una colonna e si desidera evitare l'utilizzo di dati duplicati in un modello.</span><span class="sxs-lookup"><span data-stu-id="995a5-105">The mining structure contains multiple copies of a column and you want to avoid the use of duplicate data in a model.</span></span>  
  
-   <span data-ttu-id="995a5-106">I dati devono essere protetti, ma il drill-through è abilitato.</span><span class="sxs-lookup"><span data-stu-id="995a5-106">The data should be protected, but drillthrough has been enabled.</span></span>  
  
-   <span data-ttu-id="995a5-107">I dati non vengono utilizzati nella modellazione e non devono essere elaborati.</span><span class="sxs-lookup"><span data-stu-id="995a5-107">The data is unused in modeling and should not be processed.</span></span>  
  
 <span data-ttu-id="995a5-108">L'eliminazione di una colonna dalla struttura di data mining non comporta la modifica della colonna nella vista origine dati o nei dati esterni. Solo i metadati vengono eliminati.</span><span class="sxs-lookup"><span data-stu-id="995a5-108">Deleting a column from the mining structure does not change the column in the data source view or in the external data; only metadata is deleted.</span></span> <span data-ttu-id="995a5-109">Tuttavia, quando si modificano le colonne utilizzate in una struttura di data mining, è necessario rielaborare la struttura e alcuni modelli basati su di essa.</span><span class="sxs-lookup"><span data-stu-id="995a5-109">However, when you change the columns used in a mining structure, you must reprocess the structure and any models based on it.</span></span>  
  
### <a name="to-remove-a-column-from-the-mining-structure"></a><span data-ttu-id="995a5-110">Per rimuovere una colonna dalla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="995a5-110">To remove a column from the mining structure</span></span>  
  
1.  <span data-ttu-id="995a5-111">Selezionare la scheda **Struttura di data mining** in Progettazione modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="995a5-111">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="995a5-112">Espandere l'albero per visualizzare tutte le colonne della struttura di data mining.</span><span class="sxs-lookup"><span data-stu-id="995a5-112">Expand the tree for the mining structure, to show all the columns.</span></span>  
  
3.  <span data-ttu-id="995a5-113">Fare clic con il pulsante destro del mouse sulla colonna che si desidera eliminare, quindi scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="995a5-113">Right-click the column that you want to delete, and then select **Delete**.</span></span>  
  
4.  <span data-ttu-id="995a5-114">Nella finestra di dialogo **Elimina oggetti** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="995a5-114">In the **Delete Objects** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="995a5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="995a5-115">See Also</span></span>  
 [<span data-ttu-id="995a5-116">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="995a5-116">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
