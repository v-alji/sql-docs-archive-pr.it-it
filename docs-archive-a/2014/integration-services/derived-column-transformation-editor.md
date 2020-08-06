---
title: Editor trasformazione colonna derivata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.derivedcolumntransformation.f1
helpviewer_keywords:
- Derived Column Transformation Editor
ms.assetid: ff73923e-d245-43d8-bf24-af3bdc942e51
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41a0f0dcd253473f78f2f38426b5fbd3d2ac2812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636819"
---
# <a name="derived-column-transformation-editor"></a><span data-ttu-id="737bf-102">Editor trasformazione Colonna derivata</span><span class="sxs-lookup"><span data-stu-id="737bf-102">Derived Column Transformation Editor</span></span>
  <span data-ttu-id="737bf-103">Usare la finestra di dialogo **Editor trasformazione Colonna derivata** per creare espressioni che popolino le colonne nuove o di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="737bf-103">Use the **Derived Column Transformation Editor** dialog box to create expressions that populate new or replacement columns.</span></span>  
  
 <span data-ttu-id="737bf-104">Per altre informazioni sulla trasformazione Colonna derivata, vedere [Trasformazione Colonna derivata](data-flow/transformations/derived-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="737bf-104">To learn more about the Derived Column transformation, see [Derived Column Transformation](data-flow/transformations/derived-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="737bf-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="737bf-105">Options</span></span>  
 <span data-ttu-id="737bf-106">**Variabili e Colonne**</span><span class="sxs-lookup"><span data-stu-id="737bf-106">**Variables and Columns**</span></span>  
 <span data-ttu-id="737bf-107">Consente di compilare un'espressione che utilizza una variabile o una colonna di input tramite un'operazione di trascinamento della variabile o della colonna dall'elenco di variabili e colonne disponibili in una riga di tabella esistente nel riquadro sottostante o in una nuova riga alla fine dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="737bf-107">Build an expression that uses a variable or an input column by dragging the variable or column from the list of available variables and columns to an existing table row in the pane below, or to a new row at the bottom of the list.</span></span>  
  
 <span data-ttu-id="737bf-108">**Funzioni e Operatori**</span><span class="sxs-lookup"><span data-stu-id="737bf-108">**Functions and Operators**</span></span>  
 <span data-ttu-id="737bf-109">Compilare un'espressione che utilizza una funzione o un operatore per valutare i dati di input e indirizzare i dati di output trascinando le funzioni e gli operatori dall'elenco al riquadro sottostante.</span><span class="sxs-lookup"><span data-stu-id="737bf-109">Build an expression that uses a function or an operator to evaluate input data and direct output data by dragging functions and operators from the list to the pane below.</span></span>  
  
 <span data-ttu-id="737bf-110">**Nome colonna derivata**</span><span class="sxs-lookup"><span data-stu-id="737bf-110">**Derived Column Name**</span></span>  
 <span data-ttu-id="737bf-111">Consente di assegnare un nome alla colonna derivata.</span><span class="sxs-lookup"><span data-stu-id="737bf-111">Provide a derived column name.</span></span> <span data-ttu-id="737bf-112">L'impostazione predefinita è rappresentata da un elenco numerato di colonne derivate. È tuttavia possibile scegliere qualsiasi nome descrittivo e univoco.</span><span class="sxs-lookup"><span data-stu-id="737bf-112">The default is a numbered list of derived columns; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="737bf-113">**Colonna derivata**</span><span class="sxs-lookup"><span data-stu-id="737bf-113">**Derived Column**</span></span>  
 <span data-ttu-id="737bf-114">Consente di selezionare una colonna derivata dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="737bf-114">Select a derived column from the list.</span></span> <span data-ttu-id="737bf-115">Scegliere se aggiungere la colonna derivata come nuova colonna di output o sostituire i dati in una colonna esistente.</span><span class="sxs-lookup"><span data-stu-id="737bf-115">Choose whether to add the derived column as a new output column, or to replace the data in an existing column.</span></span>  
  
 <span data-ttu-id="737bf-116">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="737bf-116">**Expression**</span></span>  
 <span data-ttu-id="737bf-117">Consente di digitare un'espressione o compilarne una mediante il trascinamento dal precedente elenco di colonne, variabili, funzioni e operatori disponibili.</span><span class="sxs-lookup"><span data-stu-id="737bf-117">Type an expression or build one by dragging from the previous list of available columns, variables, functions, and operators.</span></span>  
  
 <span data-ttu-id="737bf-118">È possibile specificare il valore di questa proprietà tramite un'espressione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="737bf-118">The value of this property can be specified by using a property expression.</span></span>  
  
 <span data-ttu-id="737bf-119">**Argomenti correlati**: [Espressioni di Integration Services &#40;SSIS&#41;](expressions/integration-services-ssis-expressions.md), [Operatori &#40;espressione SSIS&#41;](expressions/operators-ssis-expression.md) e [Funzioni &#40;espressione SSIS&#41;](expressions/functions-ssis-expression.md)</span><span class="sxs-lookup"><span data-stu-id="737bf-119">**Related topics**: [Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md), [Operators &#40;SSIS Expression&#41;](expressions/operators-ssis-expression.md), and [Functions &#40;SSIS Expression&#41;](expressions/functions-ssis-expression.md)</span></span>  
  
 <span data-ttu-id="737bf-120">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="737bf-120">**Data Type**</span></span>  
 <span data-ttu-id="737bf-121">Se si aggiungono dati a una nuova colonna, nella finestra di dialogo **Editor trasformazione Colonna derivata** viene valutata automaticamente l'espressione e viene impostato automaticamente il tipo di dati appropriato.</span><span class="sxs-lookup"><span data-stu-id="737bf-121">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the data type appropriately.</span></span> <span data-ttu-id="737bf-122">Il valore di questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="737bf-122">The value of this column is read-only.</span></span> <span data-ttu-id="737bf-123">Per altre informazioni, vedere [Tipi di dati di Integration Services](data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="737bf-123">For more information, see [Integration Services Data Types](data-flow/integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="737bf-124">**Lunghezza**</span><span class="sxs-lookup"><span data-stu-id="737bf-124">**Length**</span></span>  
 <span data-ttu-id="737bf-125">Se si aggiungono dati a una nuova colonna, nella finestra di dialogo **Editor trasformazione colonna derivata** viene valutata automaticamente l'espressione e impostata la lunghezza della colonna per i dati stringa.</span><span class="sxs-lookup"><span data-stu-id="737bf-125">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically evaluates the expression and sets the column length for string data.</span></span> <span data-ttu-id="737bf-126">Il valore di questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="737bf-126">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="737bf-127">**Precisione**</span><span class="sxs-lookup"><span data-stu-id="737bf-127">**Precision**</span></span>  
 <span data-ttu-id="737bf-128">Se si aggiungono dati a una nuova colonna, nella finestra di dialogo **Editor trasformazione Colonna derivata** viene impostata automaticamente la precisione per i dati numerici in base al tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="737bf-128">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the precision for numeric data based on the data type.</span></span> <span data-ttu-id="737bf-129">Il valore di questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="737bf-129">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="737bf-130">**Ridimensionamento**</span><span class="sxs-lookup"><span data-stu-id="737bf-130">**Scale**</span></span>  
 <span data-ttu-id="737bf-131">Se si aggiungono dati a una nuova colonna, nella finestra di dialogo **Editor trasformazione Colonna derivata** viene impostata automaticamente la scala per i dati numerici in base al tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="737bf-131">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets the scale for numeric data based on the data type.</span></span> <span data-ttu-id="737bf-132">Il valore di questa colonna è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="737bf-132">The value of this column is read-only.</span></span>  
  
 <span data-ttu-id="737bf-133">**Tabella codici**</span><span class="sxs-lookup"><span data-stu-id="737bf-133">**Code Page**</span></span>  
 <span data-ttu-id="737bf-134">Se si aggiungono dati a una nuova colonna, nella finestra di dialogo **Editor trasformazione Colonna derivata** viene impostata automaticamente la tabella codici per il tipo di dati DT_STR.</span><span class="sxs-lookup"><span data-stu-id="737bf-134">If adding data to a new column, the **Derived Column TransformationEditor** dialog box automatically sets code page for the DT_STR data type.</span></span> <span data-ttu-id="737bf-135">È possibile aggiornare **Tabella codici**.</span><span class="sxs-lookup"><span data-stu-id="737bf-135">You can update **Code Page**.</span></span>  
  
 <span data-ttu-id="737bf-136">**Configurare l'output degli errori**</span><span class="sxs-lookup"><span data-stu-id="737bf-136">**Configure error output**</span></span>  
 <span data-ttu-id="737bf-137">Consente di indicare come gestire gli errori tramite la finestra di dialogo [Configura output errori](../../2014/integration-services/configure-error-output.md) .</span><span class="sxs-lookup"><span data-stu-id="737bf-137">Specify how to handle errors by using the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="737bf-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="737bf-138">See Also</span></span>  
 <span data-ttu-id="737bf-139">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="737bf-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="737bf-140">Derivazione di valori di colonna tramite la trasformazione Colonna derivata</span><span class="sxs-lookup"><span data-stu-id="737bf-140">Derive Column Values by Using the Derived Column Transformation</span></span>](data-flow/transformations/derive-column-values-by-using-the-derived-column-transformation.md)  
  
  
