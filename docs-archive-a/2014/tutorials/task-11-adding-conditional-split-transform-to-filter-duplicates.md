---
title: 'Attività 11: aggiunta della trasformazione Suddivisione condizionale per filtrare i duplicati | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 3094bd57-5cf4-4860-bf51-fadd1b309f94
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e8370563c4275df0d0513d5434a8b16efba728d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726367"
---
# <a name="task-11-adding-conditional-split-transform-to-filter-duplicates"></a><span data-ttu-id="6fe9a-102">Attività 11: Aggiunta della trasformazione Suddivisione condizionale a Filtra duplicati</span><span class="sxs-lookup"><span data-stu-id="6fe9a-102">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>
  <span data-ttu-id="6fe9a-103">In questa attività viene aggiunta la trasformazione Suddivisione condizionale al flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-103">In this task, you add the Conditional Split Transform to the data flow.</span></span> <span data-ttu-id="6fe9a-104">Tramite questa trasformazione è possibile filtrare i duplicati del set di record in ingresso.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-104">This transform helps you filter duplicates from the incoming record set.</span></span> <span data-ttu-id="6fe9a-105">Tramite la trasformazione Raggruppamento fuzzy vengono raggruppati i record corrispondenti e uno dei record viene selezionato come record pivot.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-105">The Fuzzy Group transform groups the records that it finds to be matches and picks one of the records as a pivot record.</span></span> <span data-ttu-id="6fe9a-106">A tutti i record di un gruppo è assegnato lo stesso valore _key_out.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-106">All the records in a group have the same _key_out value.</span></span> <span data-ttu-id="6fe9a-107">I valori _key_in e _key_out del record pivot nel gruppo sono uguali.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-107">The pivot record in the group has _key_in same as the _key_out value.</span></span> <span data-ttu-id="6fe9a-108">Agli altri record del gruppo sono associati valori diversi per _key_in e _key_out.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-108">The other records in the group have different values for _key_in and _key_out.</span></span> <span data-ttu-id="6fe9a-109">Pertanto, quando si applicano filtri utilizzando la condizione _key_in==_key_out, viene visualizzata solo la riga pivot nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-109">Therefore, when you filter using the condition _key_in==_key_out, you only get the pivot row in the group.</span></span>  
  
1.  <span data-ttu-id="6fe9a-110">Trascinare la trasformazione **Suddivisione condizionale** dalla sezione **comune** nella **casella degli strumenti SSIS** alla scheda flusso di **dati** .</span><span class="sxs-lookup"><span data-stu-id="6fe9a-110">Drag-drop **Conditional Split** Transform from **Common** section in the **SSIS Toolbox** to the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="6fe9a-111">Fare clic con il pulsante destro del mouse su **trasformazione Suddivisione condizionale** nella scheda **flusso di dati** e quindi scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-111">Right-click **Conditional Split Transform** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="6fe9a-112">Digitare **filtro duplicati** e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-112">Type **Filter Duplicates** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="6fe9a-113">Connettere i **fornitori del gruppo con ID corrispondenti** per **filtrare i duplicati**.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-113">Connect **Group Suppliers with Matching IDs** to **Filter Duplicates**.</span></span>  
  
4.  <span data-ttu-id="6fe9a-114">Fare doppio clic su **Filtra duplicati** per avviare la finestra di dialogo **Editor trasformazione Suddivisione condizionale** .</span><span class="sxs-lookup"><span data-stu-id="6fe9a-114">Double-click **Filter Duplicates** to launch the **Conditional Split Transform Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="6fe9a-115">Espandere **colonne** nel riquadro superiore sinistro.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-115">Expand **Columns** in the top-left pane.</span></span>  
  
6.  <span data-ttu-id="6fe9a-116">Trascinare **_key_in** nella colonna **condizione** .</span><span class="sxs-lookup"><span data-stu-id="6fe9a-116">Drag-drop **_key_in** to the **Condition** column.</span></span>  
  
7.  <span data-ttu-id="6fe9a-117">Digitare = = (uguale a) accanto a **_key_in** e trascinamento della selezione **_key_out**.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-117">Type == (equals to) next to **_key_in** and drag-drop **_key_out**.</span></span>  
  
8.  <span data-ttu-id="6fe9a-118">Fare clic su **case 1** nella colonna **Nome output** , digitare **record univoci**e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="6fe9a-118">Click **Case 1** in the **Output Name** column, type **Unique Records**, and press **ENTER**.</span></span>  
  
     <span data-ttu-id="6fe9a-119">![Editor trasformazione Suddivisione condizionale](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Editor trasformazione Suddivisione condizionale")</span><span class="sxs-lookup"><span data-stu-id="6fe9a-119">![Conditional Split Transformation Editor](../../2014/tutorials/media/et-addingconditionalsplittransformtofilterduplicates.jpg "Conditional Split Transformation Editor")</span></span>  
  
9. <span data-ttu-id="6fe9a-120">Fare clic su **OK** per chiudere la finestra di dialogo **Editor trasformazione Suddivisione condizionale** .</span><span class="sxs-lookup"><span data-stu-id="6fe9a-120">Click **OK** to close the **Conditional Split Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="6fe9a-121">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6fe9a-121">Next Step</span></span>  
 [<span data-ttu-id="6fe9a-122">Attività 12: Aggiunta della trasformazione Colonna derivata ad Aggiungi colonne richieste da MDS</span><span class="sxs-lookup"><span data-stu-id="6fe9a-122">Task 12: Adding Derived Column Transform to Add Columns Required by MDS</span></span>](../../2014/tutorials/task-12-adding-derived-column-transform-to-add-columns-required-by-mds.md)  
  
  
