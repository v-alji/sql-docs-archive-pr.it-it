---
title: Estendere un set di dati tramite la trasformazione Merge join | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Merge Join transformation
- datasets [Integration Services], joining
- datasets [Integration Services], extending
- joining datasets [Integration Services]
ms.assetid: 9e512c3c-f89b-45f3-8281-cdb8f35a2b1f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a387c4ad840eb739d36023be9323c063dcb9a68e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625485"
---
# <a name="extend-a-dataset-by-using-the-merge-join-transformation"></a><span data-ttu-id="796e1-102">Estensione di un set di dati tramite la trasformazione Merge join</span><span class="sxs-lookup"><span data-stu-id="796e1-102">Extend a Dataset by Using the Merge Join Transformation</span></span>
  <span data-ttu-id="796e1-103">È possibile aggiungere e configurare una trasformazione Merge join solo se il pacchetto include già almeno un'attività Flusso di dati e due componenti flusso di dati che forniscono input alla trasformazione Merge join.</span><span class="sxs-lookup"><span data-stu-id="796e1-103">To add and configure a Merge Join transformation, the package must already include at least one Data Flow task and two data flow components that provide inputs to the Merge Join transformation.</span></span>  
  
 <span data-ttu-id="796e1-104">La trasformazione Merge join richiede due input ordinati.</span><span class="sxs-lookup"><span data-stu-id="796e1-104">The Merge Join transformation requires two sorted inputs.</span></span> <span data-ttu-id="796e1-105">Per altre informazioni, vedere [Ordinamento dei dati per le trasformazioni Unione e Merge Join](sort-data-for-the-merge-and-merge-join-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="796e1-105">For more information, see [Sort Data for the Merge and Merge Join Transformations](sort-data-for-the-merge-and-merge-join-transformations.md).</span></span>  
  
### <a name="to-extend-a-dataset"></a><span data-ttu-id="796e1-106">Per estendere un set di dati</span><span class="sxs-lookup"><span data-stu-id="796e1-106">To extend a dataset</span></span>  
  
1.  <span data-ttu-id="796e1-107">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="796e1-107">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="796e1-108">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="796e1-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="796e1-109">Fare clic sulla scheda **Flusso di dati** e quindi, dalla **casella degli strumenti**trascinare la trasformazione Merge join sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="796e1-109">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Merge Join transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="796e1-110">Connettere la trasformazione Merge join al flusso di dati trascinando il connettore da un'origine dati o una trasformazione precedente alla trasformazione Merge join.</span><span class="sxs-lookup"><span data-stu-id="796e1-110">Connect the Merge Join transformation to the data flow by dragging the connector from a data source or a previous transformation to the Merge Join transformation.</span></span>  
  
5.  <span data-ttu-id="796e1-111">Fare doppio clic sulla trasformazione Merge join.</span><span class="sxs-lookup"><span data-stu-id="796e1-111">Double-click the Merge Join transformation.</span></span>  
  
6.  <span data-ttu-id="796e1-112">Nella finestra di dialogo **Editor trasformazione Merge join** selezionare il tipo di join da usare nell'elenco **Tipo di join** .</span><span class="sxs-lookup"><span data-stu-id="796e1-112">In the **Merge Join Transformation Editor** dialog box, select the type of join to use in the **Join type** list.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="796e1-113">Se si seleziona il tipo **Left outer join** è possibile fare clic su **Inverti ordine input** per invertire gli input e convertire il left outer join in un right outer join.</span><span class="sxs-lookup"><span data-stu-id="796e1-113">If you select the **Left outer join** type, you can click **Swap Inputs** to switch the inputs and convert the left outer join to a right outer join.</span></span>  
  
7.  <span data-ttu-id="796e1-114">Trascinare le colonne nell'input di sinistra verso quelle dell'input di destra per specificare le colonne di join.</span><span class="sxs-lookup"><span data-stu-id="796e1-114">Drag columns in the left input to columns in the right input to specify the join columns.</span></span> <span data-ttu-id="796e1-115">Se le colonne hanno lo stesso nome, sarà possibile selezionare la casella di controllo **Chiave di join** per creare il join automaticamente.</span><span class="sxs-lookup"><span data-stu-id="796e1-115">If the columns have the same name, you can select the **Join Key** check box and the Merge Join transformation automatically creates the join.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="796e1-116">È possibile creare join solo tra colonne con la stessa posizione di ordinamento e nell'ordine specificato dalla posizione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="796e1-116">You can create joins only between columns that have the same sort position, and the joins must be created in the order specified by the sort position.</span></span> <span data-ttu-id="796e1-117">Se si tenta di creare i join senza rispettare l'ordine, **Editor trasformazione Merge join** richiederà di creare join aggiuntivi per le posizioni di ordinamento ignorate.</span><span class="sxs-lookup"><span data-stu-id="796e1-117">If you attempt to create the joins out of order, the **Merge Join Transformation Editor** prompts you to create additional joins for the skipped sort order positions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="796e1-118">Per impostazione predefinita, l'output viene ordinato in base alle colonne di join.</span><span class="sxs-lookup"><span data-stu-id="796e1-118">By default, the output is sorted on the join columns.</span></span>  
  
8.  <span data-ttu-id="796e1-119">Negli input sinistro e destro selezionare le caselle di controllo corrispondenti alle colonne aggiuntive da includere nell'output.</span><span class="sxs-lookup"><span data-stu-id="796e1-119">In the left and right inputs, select the check boxes of additional columns to include in the output.</span></span> <span data-ttu-id="796e1-120">Le colonne di join vengono incluse per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="796e1-120">Join columns are included by default.</span></span>  
  
9. <span data-ttu-id="796e1-121">Facoltativamente, aggiornare i nomi delle colonne di output nella colonna **Alias di output** .</span><span class="sxs-lookup"><span data-stu-id="796e1-121">Optionally, update the names of output columns in the **Output Alias** column.</span></span>  
  
10. <span data-ttu-id="796e1-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="796e1-122">Click **OK**.</span></span>  
  
11. <span data-ttu-id="796e1-123">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="796e1-123">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="796e1-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="796e1-124">See Also</span></span>  
 <span data-ttu-id="796e1-125">[Trasformazione Merge join](merge-join-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="796e1-125">[Merge Join Transformation](merge-join-transformation.md) </span></span>  
 <span data-ttu-id="796e1-126">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="796e1-126">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="796e1-127">[Percorsi in Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="796e1-127">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="796e1-128">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="796e1-128">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
