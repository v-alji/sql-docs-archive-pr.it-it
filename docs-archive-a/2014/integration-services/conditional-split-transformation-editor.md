---
title: Editor trasformazione Suddivisione condizionale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittransformation.f1
helpviewer_keywords:
- Conditional Split Transformation Editor
ms.assetid: c30e1633-537a-4837-9991-6203c6f2a21e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 386a93eb7c3058c7c3e98f2b652199d115d841f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624877"
---
# <a name="conditional-split-transformation-editor"></a><span data-ttu-id="f3639-102">Editor trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="f3639-102">Conditional Split Transformation Editor</span></span>
  <span data-ttu-id="f3639-103">Utilizzare la finestra di dialogo **Editor trasformazione Suddivisione condizionale** per creare espressioni e impostare l'ordine in cui vengono valutate, nonché per assegnare un nome agli output di una suddivisione condizionale.</span><span class="sxs-lookup"><span data-stu-id="f3639-103">Use the **Conditional Split Transformation Editor** dialog box to create expressions, set the order in which expressions are evaluated, and name the outputs of a conditional split.</span></span> <span data-ttu-id="f3639-104">In questa finestra di dialogo sono inclusi funzioni e operatori matematici, di data/ora e per i valori stringa che possono essere utilizzati per la compilazione di espressioni.</span><span class="sxs-lookup"><span data-stu-id="f3639-104">This dialog box includes mathematical, string, and date/time functions and operators that you can use to build expressions.</span></span> <span data-ttu-id="f3639-105">La prima condizione che restituisce true determina l'output a cui è indirizzata una riga.</span><span class="sxs-lookup"><span data-stu-id="f3639-105">The first condition that evaluates as true determines the output to which a row is directed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f3639-106">La trasformazione Suddivisione condizionale indirizza ogni riga di input a un unico output.</span><span class="sxs-lookup"><span data-stu-id="f3639-106">The Conditional Split transformation directs each input row to one output only.</span></span> <span data-ttu-id="f3639-107">Se si immettono più condizioni, la trasformazione invierà ogni riga al primo output per cui la condizione è verificata e ignorerà le successive condizioni per tale riga.</span><span class="sxs-lookup"><span data-stu-id="f3639-107">If you enter multiple conditions, the transformation sends each row to the first output for which the condition is true and disregards subsequent conditions for that row.</span></span> <span data-ttu-id="f3639-108">Per valutare più condizioni consecutivamente, potrebbe essere necessario concatenare più trasformazioni Suddivisione condizionale nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="f3639-108">If you need to evaluate several conditions successively, you may need to concatenate multiple Conditional Split transformations in the data flow.</span></span>  
  
 <span data-ttu-id="f3639-109">Per altre informazioni sulla trasformazione Suddivisione condizionale, vedere [Trasformazione Suddivisione condizionale](data-flow/transformations/conditional-split-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="f3639-109">To learn more about the Conditional Split transformation, see [Conditional Split Transformation](data-flow/transformations/conditional-split-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f3639-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f3639-110">Options</span></span>  
 <span data-ttu-id="f3639-111">**Ordine**</span><span class="sxs-lookup"><span data-stu-id="f3639-111">**Order**</span></span>  
 <span data-ttu-id="f3639-112">Selezionare una riga e utilizzare i tasti di direzione a destra per modificare l'ordine in base a cui valutare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="f3639-112">Select a row and use the arrow keys at right to change the order in which to evaluate expressions.</span></span>  
  
 <span data-ttu-id="f3639-113">**Nome output**</span><span class="sxs-lookup"><span data-stu-id="f3639-113">**Output Name**</span></span>  
 <span data-ttu-id="f3639-114">Consente di specificare un nome per l'output.</span><span class="sxs-lookup"><span data-stu-id="f3639-114">Provide an output name.</span></span> <span data-ttu-id="f3639-115">Per impostazione predefinita viene suggerito un elenco numerato di casi. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="f3639-115">The default is a numbered list of cases; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="f3639-116">**Condition**.</span><span class="sxs-lookup"><span data-stu-id="f3639-116">**Condition**</span></span>  
 <span data-ttu-id="f3639-117">Consente di digitare un'espressione o di compilarne una eseguendo un'operazione di trascinamento dall'elenco di operatori, funzioni, variabili e colonne disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3639-117">Type an expression or build one by dragging from the list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="f3639-118">È possibile specificare il valore di questa proprietà tramite un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="f3639-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="f3639-119">**Argomenti correlati:**  [Espressioni di Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Operatori &#40;espressione SSIS&#41;](expressions/operators-ssis-expression.md) e [Funzioni &#40;espressione SSIS&#41;](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="f3639-119">**Related topics:**  [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="f3639-120">**Nome output predefinito**</span><span class="sxs-lookup"><span data-stu-id="f3639-120">**Default output name**</span></span>  
 <span data-ttu-id="f3639-121">Consente di immettere un nome per la trasformazione. In alternativa, utilizzare quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="f3639-121">Type a name for the default output, or use the default.</span></span>  
  
 <span data-ttu-id="f3639-122">**Configurare l'output degli errori**</span><span class="sxs-lookup"><span data-stu-id="f3639-122">**Configure error output**</span></span>  
 <span data-ttu-id="f3639-123">Consente di indicare come gestire gli errori tramite la finestra di dialogo [Configura output errori](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="f3639-123">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3639-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3639-124">See Also</span></span>  
 <span data-ttu-id="f3639-125">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f3639-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="f3639-126">Divisione di un set di dati tramite la trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="f3639-126">Split a Dataset by Using the Conditional Split Transformation</span></span>](data-flow/transformations/split-a-dataset-by-using-the-conditional-split-transformation.md)  
  
  
