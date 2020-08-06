---
title: Trasformazione Unione input multipli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.unionalltrans.f1
helpviewer_keywords:
- merging datasets [Integration Services]
- combining datasets
- Union All transformation
- datasets [Integration Services], merging
ms.assetid: 942e4b90-9c41-4e9c-a6f3-80b3afe57f2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: eaaab1abf2587979e947cc1be24cbedf8f61b6e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636296"
---
# <a name="union-all-transformation"></a><span data-ttu-id="4ed07-102">Unione input multipli - trasformazione</span><span class="sxs-lookup"><span data-stu-id="4ed07-102">Union All Transformation</span></span>
  <span data-ttu-id="4ed07-103">La trasformazione Unione input multipli consente di combinare più input in un unico output.</span><span class="sxs-lookup"><span data-stu-id="4ed07-103">The Union All transformation combines multiple inputs into one output.</span></span> <span data-ttu-id="4ed07-104">È ad esempio possibile utilizzare gli output di cinque diverse origini file flat come input per la trasformazione Unione input multipli e combinarli in un singolo output.</span><span class="sxs-lookup"><span data-stu-id="4ed07-104">For example, the outputs from five different Flat File sources can be inputs to the Union All transformation and combined into one output.</span></span>  
  
## <a name="inputs-and-outputs"></a><span data-ttu-id="4ed07-105">Input e output</span><span class="sxs-lookup"><span data-stu-id="4ed07-105">Inputs and Outputs</span></span>  
 <span data-ttu-id="4ed07-106">Gli input della trasformazione vengono aggiunti all'output della trasformazione uno dopo l'altro, senza riordinare le righe.</span><span class="sxs-lookup"><span data-stu-id="4ed07-106">The transformation inputs are added to the transformation output one after the other; no reordering of rows occurs.</span></span> <span data-ttu-id="4ed07-107">Se il pacchetto richiede un output ordinato, sarà necessario utilizzare la trasformazione Unione anziché la trasformazione Unione input multipli.</span><span class="sxs-lookup"><span data-stu-id="4ed07-107">If the package requires a sorted output, you should use the Merge transformation instead of the Union All transformation.</span></span>  
  
 <span data-ttu-id="4ed07-108">L'output della trasformazione Unione input multipli viene creato a partire dal primo input connesso alla trasformazione.</span><span class="sxs-lookup"><span data-stu-id="4ed07-108">The first input that you connect to the Union All transformation is the input from which the transformation creates the transformation output.</span></span> <span data-ttu-id="4ed07-109">Sulle colonne negli input connessi successivamente alla trasformazione viene eseguito il mapping a quelle dell'output della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="4ed07-109">The columns in the inputs you subsequently connect to the transformation are mapped to the columns in the transformation output.</span></span>  
  
 <span data-ttu-id="4ed07-110">Per unire gli input è necessario eseguire il mapping delle relative colonne alle colonne nell'output.</span><span class="sxs-lookup"><span data-stu-id="4ed07-110">To merge inputs, you map columns in the inputs to columns in the output.</span></span> <span data-ttu-id="4ed07-111">È necessario eseguire il mapping di almeno una colonna di input a ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="4ed07-111">A column from at least one input must be mapped to each output column.</span></span> <span data-ttu-id="4ed07-112">Il mapping tra due colonne può essere eseguito solo se i relativi metadati corrispondono.</span><span class="sxs-lookup"><span data-stu-id="4ed07-112">The mapping between two columns requires that the metadata of the columns match.</span></span> <span data-ttu-id="4ed07-113">Le colonne sulle quali viene eseguito il mapping devono ad esempio avere lo stesso tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="4ed07-113">For example, the mapped columns must have the same data type.</span></span>  
  
 <span data-ttu-id="4ed07-114">Se le colonne sulle quali viene eseguito il mapping contengono dati stringa e la lunghezza della colonna di output è inferiore a quella della colonna di input, la lunghezza della colonna di output verrà aumentata automaticamente in modo che possa contenere la colonna di input.</span><span class="sxs-lookup"><span data-stu-id="4ed07-114">If the mapped columns contain string data and the output column is shorter in length than the input column, the output column is automatically increased in length to contain the input column.</span></span> <span data-ttu-id="4ed07-115">Le colonne di input sulle quali non viene eseguito il mapping a colonne di output vengono impostate su valori Null nelle colonne di output.</span><span class="sxs-lookup"><span data-stu-id="4ed07-115">Input columns that are not mapped to output columns are set to null values in the output columns.</span></span>  
  
 <span data-ttu-id="4ed07-116">Questa trasformazione include più input e un output.</span><span class="sxs-lookup"><span data-stu-id="4ed07-116">This transformation has multiple inputs and one output.</span></span> <span data-ttu-id="4ed07-117">Non supporta un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="4ed07-117">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-union-all-transformation"></a><span data-ttu-id="4ed07-118">Configurazione della trasformazione Unione input multipli</span><span class="sxs-lookup"><span data-stu-id="4ed07-118">Configuration of the Union All Transformation</span></span>  
 <span data-ttu-id="4ed07-119">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="4ed07-119">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="4ed07-120">Per altre informazioni sulle proprietà che è possibile impostare nella finestra di dialogo **Editor trasformazione Unione** , vedere [Editor trasformazione Unione input multipli](../../union-all-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="4ed07-120">For more information about the properties that you can set in the **Union All Transformation Editor** dialog box, see [Union All Transformation Editor](../../union-all-transformation-editor.md).</span></span>  
  
 <span data-ttu-id="4ed07-121">Per altre informazioni sulle proprietà che è possibile impostare a livello di codice, vedere [Proprietà comuni](../../common-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4ed07-121">For more information about the properties that you can set programmatically, see [Common Properties](../../common-properties.md).</span></span>  
  
 <span data-ttu-id="4ed07-122">Per ulteriori informazioni sulle procedure per l'impostazione delle proprietà, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ed07-122">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="4ed07-123">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="4ed07-123">Set the Properties of a Data Flow Component</span></span>](../set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="4ed07-124">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="4ed07-124">Related Tasks</span></span>  
 [<span data-ttu-id="4ed07-125">Unione di dati tramite la trasformazione Unione input multipli</span><span class="sxs-lookup"><span data-stu-id="4ed07-125">Merge Data by Using the Union All Transformation</span></span>](union-all-transformation.md)  
  
  
