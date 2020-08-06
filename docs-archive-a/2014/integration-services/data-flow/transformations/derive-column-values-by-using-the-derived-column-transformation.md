---
title: Derivare i valori di colonna tramite la trasformazione Colonna derivata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- columns [Integration Services]
- derived columns
- columns [Integration Services], values
- Derived Column transformation
ms.assetid: 28b07746-fc6f-42b2-b741-9de6fac3f29c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 837ec552144697b40cf649bc0403edfe4dc57a57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624273"
---
# <a name="derive-column-values-by-using-the-derived-column-transformation"></a><span data-ttu-id="f27ff-102">Derivazione di valori di colonna tramite la trasformazione Colonna derivata</span><span class="sxs-lookup"><span data-stu-id="f27ff-102">Derive Column Values by Using the Derived Column Transformation</span></span>
  <span data-ttu-id="f27ff-103">È possibile aggiungere e configurare una trasformazione Colonna derivata solo se il pacchetto include già almeno un'attività Flusso di dati e un'origine.</span><span class="sxs-lookup"><span data-stu-id="f27ff-103">To add and configure a Derived Column transformation, the package must already include at least one Data Flow task and one source.</span></span>  
  
 <span data-ttu-id="f27ff-104">Nella trasformazione Colonna derivata vengono utilizzate espressioni per aggiornare i valori di colonne esistenti o aggiungere valori a nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="f27ff-104">The Derived Column transformation uses expressions to update the values of existing or to add values to new columns.</span></span> <span data-ttu-id="f27ff-105">Quando si sceglie di aggiungere valori a nuove colonne, nella finestra di dialogo **Editor trasformazione Colonna derivata** viene valutata l'espressione e vengono definiti di conseguenza i metadati delle colonne.</span><span class="sxs-lookup"><span data-stu-id="f27ff-105">When you choose to add values to new columns, the **Derived Column Transformation Editor** dialog box evaluates the expression and defines the metadata of the columns accordingly.</span></span> <span data-ttu-id="f27ff-106">Se ad esempio un'espressione determina la concatenazione di due colonne, ognuna con tipo di dati DT_WSTR e lunghezza di 50, con uno spazio tra i valori delle due colonne, la nuova colonna dispone del tipo di dati DT_WSTR e di una lunghezza di 101.</span><span class="sxs-lookup"><span data-stu-id="f27ff-106">For example, if an expression concatenates two columns-each with the DT_WSTR data type and a length of 50-with a space between the two column values, the new column has the DT_WSTR data type and a length of 101.</span></span> <span data-ttu-id="f27ff-107">È possibile aggiornare il tipo di dati di nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="f27ff-107">You can update the data type of new columns.</span></span> <span data-ttu-id="f27ff-108">L'unico requisito è rappresentato dal fatto che il tipo di dati deve essere compatibile con i dati inseriti.</span><span class="sxs-lookup"><span data-stu-id="f27ff-108">The only requirement is that data type be compatible with the inserted data.</span></span> <span data-ttu-id="f27ff-109">Nella finestra di dialogo **Editor trasformazione Colonna derivata** viene ad esempio generato un errore di convalida quando si assegna un valore di data a una colonna con tipo di dati integer.</span><span class="sxs-lookup"><span data-stu-id="f27ff-109">For example, the **Derived Column Transformation Editor** dialog box generates a validation error when you assign a date value to a column with an integer data type.</span></span> <span data-ttu-id="f27ff-110">A seconda del tipo di dati selezionato, è possibile specificare la lunghezza, la precisione, la scala e la tabella codici della colonna.</span><span class="sxs-lookup"><span data-stu-id="f27ff-110">Depending on the data type that you selected, you can specify the length, precision, scale, and code page of the column.</span></span>  
  
### <a name="to-derive-column-values"></a><span data-ttu-id="f27ff-111">Per derivare valori di colonna</span><span class="sxs-lookup"><span data-stu-id="f27ff-111">To derive column values</span></span>  
  
1.  <span data-ttu-id="f27ff-112">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="f27ff-112">In [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f27ff-113">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="f27ff-113">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="f27ff-114">Fare clic sulla scheda **Flusso di dati** e quindi, dalla **casella degli strumenti**, trascinare la trasformazione Colonna derivata sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="f27ff-114">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the Derived Column transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="f27ff-115">Connettere la trasformazione Colonna derivata al flusso di dati trascinando il connettore dall'origine o dalla trasformazione precedente alla trasformazione Colonna derivata.</span><span class="sxs-lookup"><span data-stu-id="f27ff-115">Connect the Derived Column transformation to the data flow by dragging the connector from the source or the previous transformation to the Derived Column transformation.</span></span>  
  
5.  <span data-ttu-id="f27ff-116">Fare doppio clic sulla trasformazione Colonna derivata.</span><span class="sxs-lookup"><span data-stu-id="f27ff-116">Double-click the Derived Column transformation.</span></span>  
  
6.  <span data-ttu-id="f27ff-117">Nella finestra di dialogo **Editor trasformazione Colonna derivata** compilare le espressioni da usare come condizioni trascinando variabili, colonne, funzioni e operatori nella colonna **Espressione** della griglia.</span><span class="sxs-lookup"><span data-stu-id="f27ff-117">In the **Derived Column Transformation Editor** dialog box, build the expressions to use as conditions by dragging variables, columns, functions, and operators to the **Expression** column in the grid.</span></span> <span data-ttu-id="f27ff-118">In alternativa, digitare l'espressione nella colonna **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="f27ff-118">Alternatively, you can type the expression in the **Expression** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="f27ff-119">Se l'espressione non è valida, il testo dell'espressione viene evidenziato e tramite una descrizione comando nella colonna vengono descritti gli errori.</span><span class="sxs-lookup"><span data-stu-id="f27ff-119">If the expression is not valid, the expression text is highlighted and a ToolTip on the column describes the errors.</span></span>  
  
7.  <span data-ttu-id="f27ff-120">Nell'elenco **Colonna derivata** selezionare **\<add as new column>** per scrivere il risultato della valutazione dell'espressione in una nuova colonna oppure selezionare una colonna esistente per aggiornarla con il risultato della valutazione.</span><span class="sxs-lookup"><span data-stu-id="f27ff-120">In the **Derived Column** list, select **\<add as new column>** to write the evaluation result of the expression to a new column, or select an existing column to update with the evaluation result.</span></span>  
  
     <span data-ttu-id="f27ff-121">Se si è scelto di usare una nuova colonna, nella finestra di dialogo **Editor trasformazione Colonna derivata** viene valutata l'espressione e viene assegnato un tipo di dati alla colonna, a seconda del tipo di dati, della lunghezza, della precisione, della scala e della tabella codici.</span><span class="sxs-lookup"><span data-stu-id="f27ff-121">If you chose to use a new column, the **Derived Column Transformation Editor** dialog box evaluates the expression and assigns a data type to the column, depending on the data type, length, precisions, scale, and code page.</span></span>  
  
8.  <span data-ttu-id="f27ff-122">Se si usa una nuova colonna, selezionare un tipo di dati nell'elenco **Tipo di dati** .</span><span class="sxs-lookup"><span data-stu-id="f27ff-122">If using a new column, select a data type in the **Data Type** list.</span></span> <span data-ttu-id="f27ff-123">A seconda del tipo di dati selezionato, aggiornare facoltativamente i valori nelle colonne **Lunghezza**, **Precisione**, **Scala**e **Tabella codici** .</span><span class="sxs-lookup"><span data-stu-id="f27ff-123">Depending on the selected data type, optionally update the values in the **Length**, **Precision**, **Scale**, and **Code Page** columns.</span></span> <span data-ttu-id="f27ff-124">I metadati delle colonne esistenti non possono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="f27ff-124">Metadata of existing columns cannot be changed.</span></span>  
  
9. <span data-ttu-id="f27ff-125">Facoltativamente, modificare i valori nella colonna **Nome colonna derivata** .</span><span class="sxs-lookup"><span data-stu-id="f27ff-125">Optionally, modify the values in the **Derived Column Name** column.</span></span>  
  
10. <span data-ttu-id="f27ff-126">Per configurare l'output degli errori, fare clic su **Configura output errori**.</span><span class="sxs-lookup"><span data-stu-id="f27ff-126">To configure the error output, click **Configure Error Output**.</span></span> <span data-ttu-id="f27ff-127">Per altre informazioni, vedere [Configurazione di un output degli errori in un componente del flusso di dati](../../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="f27ff-127">For more information, see [Configure an Error Output in a Data Flow Component](../../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
11. <span data-ttu-id="f27ff-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f27ff-128">Click **OK**.</span></span>  
  
12. <span data-ttu-id="f27ff-129">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="f27ff-129">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f27ff-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f27ff-130">See Also</span></span>  
 <span data-ttu-id="f27ff-131">[Derived Column Transformation](derived-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="f27ff-131">[Derived Column Transformation](derived-column-transformation.md) </span></span>  
 <span data-ttu-id="f27ff-132">[Tipi di dati di Integration Services](../integration-services-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="f27ff-132">[Integration Services Data Types](../integration-services-data-types.md) </span></span>  
 <span data-ttu-id="f27ff-133">[Trasformazioni di Integration Services](integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="f27ff-133">[Integration Services Transformations](integration-services-transformations.md) </span></span>  
 <span data-ttu-id="f27ff-134">[Percorsi in Integration Services](../integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="f27ff-134">[Integration Services Paths](../integration-services-paths.md) </span></span>  
 <span data-ttu-id="f27ff-135">[Attività Flusso di dati](../../control-flow/data-flow-task.md) </span><span class="sxs-lookup"><span data-stu-id="f27ff-135">[Data Flow Task](../../control-flow/data-flow-task.md) </span></span>  
 [<span data-ttu-id="f27ff-136">Espressioni di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="f27ff-136">Integration Services &#40;SSIS&#41; Expressions</span></span>](../../expressions/integration-services-ssis-expressions.md)  
  
  
