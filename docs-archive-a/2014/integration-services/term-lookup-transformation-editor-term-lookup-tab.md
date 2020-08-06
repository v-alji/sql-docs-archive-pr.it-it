---
title: Editor trasformazione Ricerca termini (scheda ricerca termini) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.termlookup.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 245d3466-d51f-4073-978a-694a8d9dfaec
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bb8c0bd0477d9883640cc3e4d3cb25c2a3a8b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637419"
---
# <a name="term-lookup-transformation-editor-term-lookup-tab"></a><span data-ttu-id="46d45-102">Editor trasformazione Ricerca termini (scheda Ricerca termini)</span><span class="sxs-lookup"><span data-stu-id="46d45-102">Term Lookup Transformation Editor (Term Lookup Tab)</span></span>
  <span data-ttu-id="46d45-103">Utilizzare la scheda **Ricerca termini** della finestra di dialogo **Editor trasformazione Ricerca termini** per eseguire il mapping tra una colonna di input e una colonna di ricerca in una tabella di riferimento e per specificare un alias per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="46d45-103">Use the **Term Lookup** tab of the **Term Lookup Transformation Editor** dialog box to map an input column to a lookup column in a reference table and to provide an alias for each output column.</span></span>  
  
 <span data-ttu-id="46d45-104">Per ulteriori informazioni sulla trasformazione Ricerca termini, vedere [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="46d45-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="46d45-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="46d45-105">Options</span></span>  
 <span data-ttu-id="46d45-106">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="46d45-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="46d45-107">Utilizzare le caselle di controllo per selezionare le colonne di input da passare all'output senza modifiche.</span><span class="sxs-lookup"><span data-stu-id="46d45-107">Using the check boxes, select input columns to pass through to the output unchanged.</span></span> <span data-ttu-id="46d45-108">Trascinare una colonna di input nell'elenco **Colonne di riferimento disponibili** per eseguirne il mapping a una colonna di ricerca nella tabella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="46d45-108">Drag an input column to the **Available Reference Columns** list to map it to a lookup column in the reference table.</span></span> <span data-ttu-id="46d45-109">Le colonne di input e di output devono avere tipi di dati corrispondenti e supportati, ovvero DT_NTEXT o DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="46d45-109">The input and lookup columns must have matching, supported data types, either DT_NTEXT or DT_WSTR.</span></span> <span data-ttu-id="46d45-110">Selezionare una riga di mapping e fare clic con il pulsante destro del mouse per modificare i mapping nella finestra di dialogo [Crea relazioni](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="46d45-110">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="46d45-111">**Colonne di riferimento disponibili**</span><span class="sxs-lookup"><span data-stu-id="46d45-111">**Available Reference Columns**</span></span>  
 <span data-ttu-id="46d45-112">Consente di visualizzare le colonne disponibili nella tabella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="46d45-112">View the available columns in the reference table.</span></span> <span data-ttu-id="46d45-113">Selezionare la colonna contenente l'elenco dei termini per i quali si desidera trovare una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="46d45-113">Choose the column that contains the list of terms to match.</span></span>  
  
 <span data-ttu-id="46d45-114">**Colonna pass-through**</span><span class="sxs-lookup"><span data-stu-id="46d45-114">**Pass-Through Column**</span></span>  
 <span data-ttu-id="46d45-115">Consente di selezionare una colonna di input nell'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="46d45-115">Select from the list of available input columns.</span></span> <span data-ttu-id="46d45-116">Le selezioni effettuate vengono riflesse nelle selezioni delle caselle di controllo nella tabella **Colonne di input disponibili** .</span><span class="sxs-lookup"><span data-stu-id="46d45-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="46d45-117">**Alias colonna di output**</span><span class="sxs-lookup"><span data-stu-id="46d45-117">**Output Column Alias**</span></span>  
 <span data-ttu-id="46d45-118">Consente di digitare un alias per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="46d45-118">Type an alias for each output column.</span></span> <span data-ttu-id="46d45-119">Per impostazione predefinita, viene suggerito il nome della colonna. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="46d45-119">The default is the name of the column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="46d45-120">**Configura output errori**</span><span class="sxs-lookup"><span data-stu-id="46d45-120">**Configure Error Output**</span></span>  
 <span data-ttu-id="46d45-121">Usare la finestra di dialogo [Configura output errori](../../2014/integration-services/configure-error-output.md) per specificare le opzioni di gestione degli errori per le righe che causano errori.</span><span class="sxs-lookup"><span data-stu-id="46d45-121">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d45-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46d45-122">See Also</span></span>  
 <span data-ttu-id="46d45-123">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="46d45-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="46d45-124">[Editor trasformazione Ricerca termini &#40;scheda tabella di riferimento&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="46d45-124">[Term Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 <span data-ttu-id="46d45-125">[Editor trasformazione Ricerca termini &#40;scheda Avanzate&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="46d45-125">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="46d45-126">Trasformazione Estrazione termini</span><span class="sxs-lookup"><span data-stu-id="46d45-126">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
