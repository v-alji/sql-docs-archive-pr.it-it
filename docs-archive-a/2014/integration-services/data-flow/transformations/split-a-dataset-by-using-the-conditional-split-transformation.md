---
title: Dividere un set di dati tramite la trasformazione Suddivisione condizionale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Conditional Split transformation
- splitting dataset
- datasets [Integration Services], splitting
ms.assetid: 23b3e84f-9296-4dc9-81c0-c7f06ae3f1ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2efbc3973db1ab1b6b61f6de879e451319b50e49
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636300"
---
# <a name="split-a-dataset-by-using-the-conditional-split-transformation"></a><span data-ttu-id="7145e-102">Divisione di un set di dati tramite la trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="7145e-102">Split a Dataset by Using the Conditional Split Transformation</span></span>
  <span data-ttu-id="7145e-103">È possibile aggiungere e configurare una trasformazione Suddivisione condizionale solo se il pacchetto include già almeno un'attività Flusso di dati e un'origine.</span><span class="sxs-lookup"><span data-stu-id="7145e-103">To add and configure a Conditional Split transformation, the package must already include at least one Data Flow task and a source.</span></span>  
  
### <a name="to-conditionally-split-a-dataset"></a><span data-ttu-id="7145e-104">Per eseguire la suddivisione condizionale di un set di dati</span><span class="sxs-lookup"><span data-stu-id="7145e-104">To conditionally split a dataset</span></span>  
  
1.  <span data-ttu-id="7145e-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="7145e-105">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="7145e-106">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="7145e-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="7145e-107">Fare clic sulla scheda **Flusso di dati** e quindi, dalla **casella degli strumenti**, trascinare la trasformazione Suddivisione condizionale sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="7145e-107">Click the **Data Flow** tab, and, from the **Toolbox**, drag the Conditional Split transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="7145e-108">Connettere la trasformazione Suddivisione condizionale al flusso di dati trascinando il connettore dall'origine dati o dalla trasformazione precedente alla trasformazione Suddivisione condizionale.</span><span class="sxs-lookup"><span data-stu-id="7145e-108">Connect the Conditional Split transformation to the data flow by dragging the connector from the data source or the previous transformation to the Conditional Split transformation.</span></span>  
  
5.  <span data-ttu-id="7145e-109">Fare doppio clic sulla trasformazione Suddivisione condizionale.</span><span class="sxs-lookup"><span data-stu-id="7145e-109">Double-click the Conditional Split transformation.</span></span>  
  
6.  <span data-ttu-id="7145e-110">Nella finestra di dialogo **Editor trasformazione Suddivisione condizionale**compilare le espressioni da usare come condizioni trascinando variabili, colonne, funzioni e operatori nella colonna **Condizione** della griglia.</span><span class="sxs-lookup"><span data-stu-id="7145e-110">In the **Conditional Split Transformation Editor**, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Condition** column in the grid.</span></span> <span data-ttu-id="7145e-111">In alternativa, digitare l'espressione nella colonna **Condizione** .</span><span class="sxs-lookup"><span data-stu-id="7145e-111">Or, you can type the expression in the **Condition** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7145e-112">È possibile utilizzare una stessa variabile o colonna in più espressioni.</span><span class="sxs-lookup"><span data-stu-id="7145e-112">A variable or column can be used in multiple expressions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7145e-113">Se l'espressione non è valida, il testo dell'espressione viene evidenziato e tramite una descrizione comando nella colonna vengono descritti gli errori.</span><span class="sxs-lookup"><span data-stu-id="7145e-113">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="7145e-114">Facoltativamente, modificare i valori nella colonna **Nome output** .</span><span class="sxs-lookup"><span data-stu-id="7145e-114">Optionally, modify the values in the **Output Name** column.</span></span> <span data-ttu-id="7145e-115">I nomi predefiniti sono Case 1, Case 2 e così via.</span><span class="sxs-lookup"><span data-stu-id="7145e-115">The default names are Case 1, Case 2, and so forth.</span></span>  
  
8.  <span data-ttu-id="7145e-116">Per modificare la sequenza in cui vengono valutate le condizioni, fare clic sulla freccia in su o sulla freccia in giù.</span><span class="sxs-lookup"><span data-stu-id="7145e-116">To modify the sequence in which the conditions are evaluated, click the up arrow or down arrow.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7145e-117">Collocare le condizioni più probabili all'inizio dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7145e-117">Place the conditions that are most likely to be encountered at the top of the list.</span></span>  
  
9. <span data-ttu-id="7145e-118">Facoltativamente, modificare il nome dell'output predefinito per le righe di dati che non soddisfano alcuna condizione.</span><span class="sxs-lookup"><span data-stu-id="7145e-118">Optionally, modify the name of the default output for data rows that do not match any condition.</span></span>  
  
10. <span data-ttu-id="7145e-119">Per configurare un output degli errori, fare clic su **Configura output errori**.</span><span class="sxs-lookup"><span data-stu-id="7145e-119">To configure an error output, click **Configure Error Output**.</span></span> <span data-ttu-id="7145e-120">Per altre informazioni, vedere [Configurazione di un output degli errori in un componente del flusso di dati](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="7145e-120">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="7145e-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7145e-121">Click **OK**.</span></span>  
  
12. <span data-ttu-id="7145e-122">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="7145e-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7145e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7145e-123">See Also</span></span>  
 <span data-ttu-id="7145e-124">[Conditional Split Transformation](conditional-split-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="7145e-124">[Conditional Split Transformation](conditional-split-transformation.md) </span></span>  
 <span data-ttu-id="7145e-125">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="7145e-125">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="7145e-126">[Percorsi in Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="7145e-126">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="7145e-127">[Tipi di dati di Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="7145e-127">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="7145e-128">[Attività Flusso di dati](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="7145e-128">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="7145e-129">Espressioni di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="7145e-129">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
