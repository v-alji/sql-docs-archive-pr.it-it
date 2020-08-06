---
title: Suddivisione condizionale - trasformazione | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.conditionalsplittrans.f1
helpviewer_keywords:
- Conditional Split transformation
- route rows to different outputs [Integration Services]
ms.assetid: 3f8b5825-226f-413c-ba8f-0bb931ca3770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 96ff4b177992c329908ebc93df8f6220168e634d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629948"
---
# <a name="conditional-split-transformation"></a><span data-ttu-id="cc156-102">Suddivisione condizionale - trasformazione</span><span class="sxs-lookup"><span data-stu-id="cc156-102">Conditional Split Transformation</span></span>
  <span data-ttu-id="cc156-103">La trasformazione Suddivisione condizionale consente di indirizzare righe di dati verso output diversi a seconda del contenuto dei dati.</span><span class="sxs-lookup"><span data-stu-id="cc156-103">The Conditional Split transformation can route data rows to different outputs depending on the content of the data.</span></span> <span data-ttu-id="cc156-104">L'implementazione della trasformazione Suddivisione condizionale è simile a una struttura decisionale CASE in un linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="cc156-104">The implementation of the Conditional Split transformation is similar to a CASE decision structure in a programming language.</span></span> <span data-ttu-id="cc156-105">La trasformazione valuta una o più espressioni e, in base ai risultati, dirige la riga di dati verso l'output specificato.</span><span class="sxs-lookup"><span data-stu-id="cc156-105">The transformation evaluates expressions, and based on the results, directs the data row to the specified output.</span></span> <span data-ttu-id="cc156-106">Questa trasformazione prevede inoltre un output predefinito, in modo che se una riga non corrisponde ad alcuna espressione venga indirizzata all'output predefinito.</span><span class="sxs-lookup"><span data-stu-id="cc156-106">This transformation also provides a default output, so that if a row matches no expression it is directed to the default output.</span></span>  
  
## <a name="configuration-of-the-conditional-split-transformation"></a><span data-ttu-id="cc156-107">Configurazione della trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="cc156-107">Configuration of the Conditional Split Transformation</span></span>  
 <span data-ttu-id="cc156-108">Per configurare la trasformazione Suddivisione condizionale, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="cc156-108">You can configure the Conditional Split transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="cc156-109">Specificare un'espressione che restituisce un valore booleano per ogni condizione che dovrà essere verificata dalla trasformazione.</span><span class="sxs-lookup"><span data-stu-id="cc156-109">Provide an expression that evaluates to a Boolean for each condition you want the transformation to test.</span></span>  
  
-   <span data-ttu-id="cc156-110">Specificare l'ordine in cui devono essere valutate le condizioni.</span><span class="sxs-lookup"><span data-stu-id="cc156-110">Specify the order in which the conditions are evaluated.</span></span> <span data-ttu-id="cc156-111">L'ordine è estremamente importante, perché ogni riga viene inviata all'output corrispondente alla prima condizione che restituisce True.</span><span class="sxs-lookup"><span data-stu-id="cc156-111">Order is significant, because a row is sent to the output corresponding to the first condition that evaluates to true.</span></span>  
  
-   <span data-ttu-id="cc156-112">Specificare l'output predefinito per la trasformazione.</span><span class="sxs-lookup"><span data-stu-id="cc156-112">Specify the default output for the transformation.</span></span> <span data-ttu-id="cc156-113">La trasformazione richiede che venga specificato un output predefinito.</span><span class="sxs-lookup"><span data-stu-id="cc156-113">The transformation requires that a default output be specified.</span></span>  
  
 <span data-ttu-id="cc156-114">Ogni riga di input può essere inviata a un solo output, ovvero quello corrispondente alla prima condizione che restituisce True.</span><span class="sxs-lookup"><span data-stu-id="cc156-114">Each input row can be sent to only one output, that being the output for the first condition that evaluates to true.</span></span> <span data-ttu-id="cc156-115">Le condizioni seguenti, ad esempio, dirigono tutte le righe della colonna **FirstName** che iniziano con la lettera *A* a un determinato output, a un altro output le righe che iniziano con la lettera *B* e tutte le altre righe all'output predefinito.</span><span class="sxs-lookup"><span data-stu-id="cc156-115">For example, the following conditions direct any rows in the **FirstName** column that begin with the letter *A* to one output, rows that begin with the letter *B* to a different output, and all other rows to the default output.</span></span>  
  
 <span data-ttu-id="cc156-116">Output 1</span><span class="sxs-lookup"><span data-stu-id="cc156-116">Output 1</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "A"`  
  
 <span data-ttu-id="cc156-117">Output 2</span><span class="sxs-lookup"><span data-stu-id="cc156-117">Output 2</span></span>  
  
 `SUBSTRING(FirstName,1,1) == "B"`  
  
 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] <span data-ttu-id="cc156-118">include funzioni e operatori che è possibile usare per creare le espressioni che valutano i dati di input e dirigono i dati di output.</span><span class="sxs-lookup"><span data-stu-id="cc156-118">includes functions and operators that you can use to create the expressions that evaluate input data and direct output data.</span></span> <span data-ttu-id="cc156-119">Per altre informazioni, vedere [Espressioni di Integration Services &#40;SSIS&#41;](../../expressions/integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="cc156-119">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../../expressions/integration-services-ssis-expressions.md).</span></span>  
  
 <span data-ttu-id="cc156-120">La trasformazione Suddivisione condizionale include la proprietà personalizzata `FriendlyExpression`,</span><span class="sxs-lookup"><span data-stu-id="cc156-120">The Conditional Split transformation includes the `FriendlyExpression` custom property.</span></span> <span data-ttu-id="cc156-121">che può essere aggiornata da un'espressione di proprietà al caricamento del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cc156-121">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="cc156-122">Per altre informazioni, vedere [Utilizzo delle espressioni di proprietà nei pacchetti](../../expressions/use-property-expressions-in-packages.md) e [Proprietà personalizzate delle trasformazioni](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="cc156-122">For more information, see [Use Property Expressions in Packages](../../expressions/use-property-expressions-in-packages.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
 <span data-ttu-id="cc156-123">Questa trasformazione include un input, uno o più output e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="cc156-123">This transformation has one input, one or more outputs, and one error output.</span></span>  
  
 <span data-ttu-id="cc156-124">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="cc156-124">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="cc156-125">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Suddivisione condizionale** , vedere [Editor trasformazione Suddivisione condizionale](../../conditional-split-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="cc156-125">For more information about the properties that you can set in the **Conditional Split Transformation Editor** dialog box, see [Conditional Split Transformation Editor](../../conditional-split-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="cc156-126">Nella finestra di dialogo **Editor avanzato** sono disponibili le proprietà che è possibile impostare a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="cc156-126">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="cc156-127">Per ulteriori informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor avanzato** o a livello di codice, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc156-127">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cc156-128">Proprietà comuni</span><span class="sxs-lookup"><span data-stu-id="cc156-128">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="cc156-129">Proprietà personalizzate delle trasformazioni</span><span class="sxs-lookup"><span data-stu-id="cc156-129">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
 <span data-ttu-id="cc156-130">Per ulteriori informazioni sulle procedure per l'impostazione delle proprietà, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cc156-130">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="cc156-131">Divisione di un set di dati tramite la trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="cc156-131">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
-   [<span data-ttu-id="cc156-132">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="cc156-132">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="cc156-133">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="cc156-133">Related Tasks</span></span>  
 [<span data-ttu-id="cc156-134">Divisione di un set di dati tramite la trasformazione Suddivisione condizionale</span><span class="sxs-lookup"><span data-stu-id="cc156-134">Split a Dataset by Using the Conditional Split Transformation</span></span>](conditional-split-transformation.md)  
  
## <a name="see-also"></a><span data-ttu-id="cc156-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc156-135">See Also</span></span>  
 <span data-ttu-id="cc156-136">[Flusso di dati](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="cc156-136">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="cc156-137">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="cc156-137">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
