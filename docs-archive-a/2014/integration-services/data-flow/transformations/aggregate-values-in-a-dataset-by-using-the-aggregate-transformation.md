---
title: Aggregare valori in un set di dati tramite la trasformazione Aggregazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Aggregate transformation [Integration Services]
- aggregate values [Integration Services]
- datasets [Integration Services], aggregate values
ms.assetid: 01b81c0f-d5e0-483b-81b2-73800a6945ac
author: chugugrace
ms.author: chugu
ms.openlocfilehash: de918c6c2adf194d5808ccd1b64c77a94a52e357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712204"
---
# <a name="aggregate-values-in-a-dataset-by-using-the-aggregate-transformation"></a><span data-ttu-id="a7335-102">Aggregazione di valori in un set di dati utilizzando la trasformazione Aggregazione</span><span class="sxs-lookup"><span data-stu-id="a7335-102">Aggregate Values in a Dataset by Using the Aggregate Transformation</span></span>
  <span data-ttu-id="a7335-103">È possibile aggiungere e configurare una trasformazione Aggregazione solo se il pacchetto include almeno un'attività Flusso di dati e un'origine.</span><span class="sxs-lookup"><span data-stu-id="a7335-103">To add and configure an Aggregate transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
### <a name="to-aggregate-values-in-a-dataset"></a><span data-ttu-id="a7335-104">Per aggregare valori in un set di dati</span><span class="sxs-lookup"><span data-stu-id="a7335-104">To aggregate values in a dataset</span></span>  
  
1.  <span data-ttu-id="a7335-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="a7335-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="a7335-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="a7335-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="a7335-107">Fare clic sulla scheda **Flusso di dati** e quindi, dalla **casella degli strumenti**, trascinare la trasformazione Aggregazione sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a7335-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Aggregate transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="a7335-108">Connettere la trasformazione Aggregazione al flusso di dati trascinando un connettore dall'origine o da una trasformazione precedente alla trasformazione Aggregazione.</span><span class="sxs-lookup"><span data-stu-id="a7335-108">Connect the Aggregate transformation to the data flow by dragging a connector from the source or the previous transformation to the Aggregate transformation.</span></span>  
  
5.  <span data-ttu-id="a7335-109">Fare doppio clic sulla trasformazione.</span><span class="sxs-lookup"><span data-stu-id="a7335-109">Double-click the transformation.</span></span>  
  
6.  <span data-ttu-id="a7335-110">Nella finestra di dialogo **Editor trasformazione Aggregazione** fare clic sulla scheda **Aggregazioni** .</span><span class="sxs-lookup"><span data-stu-id="a7335-110">In the **Aggregate Transformation Editor** dialog box, click the **Aggregations** tab.</span></span>  
  
7.  <span data-ttu-id="a7335-111">Nell'elenco **Colonne di input disponibili** selezionare le caselle di controllo corrispondenti alle colonne in cui si vogliono aggregare i valori.</span><span class="sxs-lookup"><span data-stu-id="a7335-111">In the **Available Input Columns** list, select the check box by the columns on which you want to aggregate values.</span></span> <span data-ttu-id="a7335-112">Le colonne selezionate verranno visualizzate nella tabella.</span><span class="sxs-lookup"><span data-stu-id="a7335-112">The selected columns appear in the table.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7335-113">È possibile selezionare una stessa colonna più volte e applicarvi più trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="a7335-113">You can select a column multiple times, applying multiple transformations to the column.</span></span> <span data-ttu-id="a7335-114">Per identificare univocamente le aggregazioni, viene aggiunto un numero al nome predefinito dell'alias di output della colonna.</span><span class="sxs-lookup"><span data-stu-id="a7335-114">To uniquely identify aggregations, a number is appended to the default name of the output alias of the column.</span></span>  
  
8.  <span data-ttu-id="a7335-115">Facoltativamente, modificare il valore nelle colonne **Alias di output** .</span><span class="sxs-lookup"><span data-stu-id="a7335-115">Optionally, modify the value in the **Output Alias** columns.</span></span>  
  
9. <span data-ttu-id="a7335-116">Per modificare l'operazione di aggregazione predefinita, **Group by**, selezionare un'operazione diversa nell'elenco **Operazione** .</span><span class="sxs-lookup"><span data-stu-id="a7335-116">To change the default aggregation operation, **Group by**, select a different operation in the **Operation** list.</span></span>  
  
10. <span data-ttu-id="a7335-117">Per modificare il tipo di confronto predefinito, selezionare nella colonna **Flag di confronto** i singoli flag di confronto da usare.</span><span class="sxs-lookup"><span data-stu-id="a7335-117">To change the default comparison, select the individual comparison flags listed in the **Comparison Flags** column.</span></span> <span data-ttu-id="a7335-118">Per impostazione predefinita, nel confronto vengono ignorati i caratteri senza spaziatura, la distinzione tra maiuscole e minuscole, la distinzione tra Katakana e Hiragana e la larghezza dei caratteri.</span><span class="sxs-lookup"><span data-stu-id="a7335-118">By default, a comparison ignores case, kana type, non-spacing characters, and character width.</span></span>  
  
11. <span data-ttu-id="a7335-119">Facoltativamente, per l'aggregazione **Count distinct** specificare un numero esatto di valori distinct nella colonna **Chiavi conteggio valori distinct** oppure selezionare un numero approssimativo nella colonna **Scala conteggio valori distinct** .</span><span class="sxs-lookup"><span data-stu-id="a7335-119">Optionally, for the **Count distinct** aggregation, specify an exact number of distinct values in the **Count Distinct Keys** column, or select an approximate count in the **Count Distinct Scale** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7335-120">L'indicazione del numero dei valori distinct, esatto o approssimativo, consente di ottimizzare le prestazioni, perché la trasformazione può preallocare la quantità di memoria appropriata per l'esecuzione delle operazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="a7335-120">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
12. <span data-ttu-id="a7335-121">Facoltativamente, fare clic su **Avanzate** e aggiornare il nome dell'output della trasformazione Aggregazione.</span><span class="sxs-lookup"><span data-stu-id="a7335-121">Optionally, click **Advanced** and update the name of the Aggregate transformation output.</span></span> <span data-ttu-id="a7335-122">Se le aggregazioni includono un' `Group By` operazione, è possibile selezionare un numero approssimativo di valori di chiavi di raggruppamento nella colonna **Scala chiavi** oppure specificare un numero esatto di valori di chiave di raggruppamento nella colonna **chiavi** .</span><span class="sxs-lookup"><span data-stu-id="a7335-122">If the aggregations include a `Group By` operation, you can select an approximate count of grouping key values in the **Keys Scale** column or specify an exact number of grouping key values in the **Keys** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7335-123">L'indicazione del numero dei valori distinct, esatto o approssimativo, consente di ottimizzare le prestazioni, perché la trasformazione può preallocare la quantità di memoria appropriata per l'esecuzione delle operazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="a7335-123">Providing the number of distinct values, exact or approximate, optimizes performance, because the transformation can preallocate an appropriate amount of memory to do its work.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a7335-124">Le opzioni **Scala chiavi** e **Chiavi** si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="a7335-124">The **Keys Scale** and **Keys** options are mutually exclusive.</span></span> <span data-ttu-id="a7335-125">Se si immettono valori in entrambe le colonne, verrà usato il valore più elevato di **Scala chiavi** e **Chiavi** .</span><span class="sxs-lookup"><span data-stu-id="a7335-125">If you enter values in both columns, the larger value in either **Keys Scale** or **Keys** is used.</span></span>  
  
13. <span data-ttu-id="a7335-126">Facoltativamente, fare clic sulla scheda **Avanzate** e impostare gli attributi relativi all'ottimizzazione di tutte le operazioni eseguite dalla trasformazione Aggregazione.</span><span class="sxs-lookup"><span data-stu-id="a7335-126">Optionally, click the **Advanced** tab and set the attributes that apply to optimizing all the operations that the Aggregate transformation performs.</span></span>  
  
14. <span data-ttu-id="a7335-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7335-127">Click **OK**.</span></span>  
  
15. <span data-ttu-id="a7335-128">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="a7335-128">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7335-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7335-129">See Also</span></span>  
 <span data-ttu-id="a7335-130">[Trasformazione Aggregazione](aggregate-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="a7335-130">[Aggregate Transformation](aggregate-transformation.md) </span></span>  
 <span data-ttu-id="a7335-131">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="a7335-131">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="a7335-132">[Percorsi in Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="a7335-132">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 [<span data-ttu-id="a7335-133">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="a7335-133">Data Flow Task</span></span>](../../control-flow/data-flow-task.md)  
  
  
