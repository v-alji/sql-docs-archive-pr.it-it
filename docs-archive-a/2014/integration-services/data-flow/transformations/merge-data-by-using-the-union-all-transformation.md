---
title: Unire dati tramite la trasformazione Unione input multipli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- merging datasets [Integration Services]
- merging inputs [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 78304403-a81c-4101-b87e-ec80ddfdac98
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e782a5770ab9936e4c5cc84da706a5472ecd4d36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636303"
---
# <a name="merge-data-by-using-the-union-all-transformation"></a><span data-ttu-id="2a96d-102">Unione di dati tramite la trasformazione Unione input multipli</span><span class="sxs-lookup"><span data-stu-id="2a96d-102">Merge Data by Using the Union All Transformation</span></span>
  <span data-ttu-id="2a96d-103">È possibile aggiungere e configurare una trasformazione Unione input multipli solo se il pacchetto include già almeno un'attività Flusso di dati e due origini dati.</span><span class="sxs-lookup"><span data-stu-id="2a96d-103">To add and configure a Union All transformation, the package must already include at least one Data Flow task and two data sources.</span></span>  
  
 <span data-ttu-id="2a96d-104">La trasformazione Unione input multipli consente di combinare più input.</span><span class="sxs-lookup"><span data-stu-id="2a96d-104">The Union All transformation combines multiple inputs.</span></span> <span data-ttu-id="2a96d-105">Il primo input connesso alla trasformazione è l'input di riferimento, mentre gli input connessi successivamente sono gli input secondari.</span><span class="sxs-lookup"><span data-stu-id="2a96d-105">The first input that is connected to the transformation is the reference input, and the inputs connected subsequently are the secondary inputs.</span></span> <span data-ttu-id="2a96d-106">L'output include le colonne dell'input di riferimento.</span><span class="sxs-lookup"><span data-stu-id="2a96d-106">The output includes the columns in the reference input.</span></span>  
  
### <a name="to-combine-inputs-in-a-data-flow"></a><span data-ttu-id="2a96d-107">Per combinare più input in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="2a96d-107">To combine inputs in a data flow</span></span>  
  
1.  <span data-ttu-id="2a96d-108">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]fare doppio clic sul pacchetto in Esplora soluzioni per aprire il pacchetto in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] e quindi fare clic sulla scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="2a96d-108">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], double-click the package in Solution Explorer to open the package in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer, and then click the **Data Flow** tab.</span></span>  
  
2.  <span data-ttu-id="2a96d-109">Dalla **casella degli strumenti**trascinare la trasformazione Unione input multipli all'area di progettazione della scheda **Flusso di dati** .</span><span class="sxs-lookup"><span data-stu-id="2a96d-109">From the **Toolbox**, drag the Union All transformation to the design surface of the **Data Flow** tab.</span></span>  
  
3.  <span data-ttu-id="2a96d-110">Connettere la trasformazione Unione input multipli al flusso di dati trascinando un connettore dall'origine dati o da una trasformazione precedente alla trasformazione Unione input multipli.</span><span class="sxs-lookup"><span data-stu-id="2a96d-110">Connect the Union All transformation to the data flow by dragging a connector from the data source or a previous transformation to the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="2a96d-111">Fare doppio clic sulla trasformazione Unione input multipli.</span><span class="sxs-lookup"><span data-stu-id="2a96d-111">Double-click the Union All transformation.</span></span>  
  
5.  <span data-ttu-id="2a96d-112">In **Editor trasformazione Unione input multipli**eseguire il mapping di una colonna dell'input a una colonna nell'elenco **Nome colonna di output** , facendo clic su una riga e quindi selezionando una colonna nell'elenco degli input.</span><span class="sxs-lookup"><span data-stu-id="2a96d-112">In the **Union All Transformation Editor**, map a column from an input to a column in the **Output Column Name** list by clicking a row and then selecting a column in the input list.</span></span> <span data-ttu-id="2a96d-113">Per evitare di eseguire il mapping della colonna, selezionare **\<ignore>** nell'elenco degli input.</span><span class="sxs-lookup"><span data-stu-id="2a96d-113">Select **\<ignore>** in the input list to skip mapping the column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a96d-114">Il mapping tra due colonne può essere eseguito solo se i relativi metadati corrispondono.</span><span class="sxs-lookup"><span data-stu-id="2a96d-114">The mapping between two columns requires that the metadata of the columns match.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2a96d-115">Le colonne degli input secondari di cui non è stato eseguito il mapping alle colonne di riferimento, nell'output vengono impostate su valori Null.</span><span class="sxs-lookup"><span data-stu-id="2a96d-115">Columns in a secondary input that are not mapped to reference columns are set to null values in the output.</span></span>  
  
6.  <span data-ttu-id="2a96d-116">Facoltativamente, modificare i nomi delle colonne nell'elenco **Nome colonna di output** .</span><span class="sxs-lookup"><span data-stu-id="2a96d-116">Optionally, modify the names of columns in the **Output Column Name** column.</span></span>  
  
7.  <span data-ttu-id="2a96d-117">Ripetere i passaggi 5 e 6 per ogni colonna di ogni input.</span><span class="sxs-lookup"><span data-stu-id="2a96d-117">Repeat steps 5 and 6 for each column in each input.</span></span>  
  
8.  <span data-ttu-id="2a96d-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a96d-118">Click **OK**.</span></span>  
  
9. <span data-ttu-id="2a96d-119">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="2a96d-119">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a96d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a96d-120">See Also</span></span>  
 <span data-ttu-id="2a96d-121">[Trasformazione Unione input multipli](union-all-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="2a96d-121">[Union All Transformation](union-all-transformation.md) </span></span>  
 <span data-ttu-id="2a96d-122">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="2a96d-122">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="2a96d-123">[Percorsi in Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="2a96d-123">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="2a96d-124">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="2a96d-124">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
