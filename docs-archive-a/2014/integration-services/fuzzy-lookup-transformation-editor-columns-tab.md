---
title: Editor trasformazione Ricerca fuzzy (scheda colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.columns.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: aaf45327-79e9-4760-9b4d-546ace91b5b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f9294022b52536940916a381d7b811437eaa5814
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713307"
---
# <a name="fuzzy-lookup-transformation-editor-columns-tab"></a><span data-ttu-id="8d915-102">Editor trasformazione Ricerca fuzzy (scheda Colonne)</span><span class="sxs-lookup"><span data-stu-id="8d915-102">Fuzzy Lookup Transformation Editor (Columns Tab)</span></span>
  <span data-ttu-id="8d915-103">Utilizzare la scheda **Colonne** della finestra di dialogo **Editor trasformazione Ricerca fuzzy** per impostare le proprietà delle colonne di input e output.</span><span class="sxs-lookup"><span data-stu-id="8d915-103">Use the **Columns** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set properties for input and output columns.</span></span>  
  
 <span data-ttu-id="8d915-104">Per ulteriori informazioni sulla trasformazione Ricerca fuzzy, vedere [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="8d915-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="8d915-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8d915-105">Options</span></span>  
 <span data-ttu-id="8d915-106">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="8d915-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="8d915-107">Trascinare le colonne di input per collegarle alle colonne di ricerca disponibili.</span><span class="sxs-lookup"><span data-stu-id="8d915-107">Drag input columns to connect them to available lookup columns.</span></span> <span data-ttu-id="8d915-108">Queste colonne devono disporre di tipi di dati supportati e corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="8d915-108">These columns must have matching, supported data types.</span></span> <span data-ttu-id="8d915-109">Selezionare una riga di mapping e fare clic con il pulsante destro del mouse per modificare i mapping nella finestra di dialogo [Crea relazioni](data-flow/transformations/create-relationships.md) .</span><span class="sxs-lookup"><span data-stu-id="8d915-109">Select a mapping line and right-click to edit the mappings in the [Create Relationships](data-flow/transformations/create-relationships.md) dialog box.</span></span>  
  
 <span data-ttu-id="8d915-110">**Nome**</span><span class="sxs-lookup"><span data-stu-id="8d915-110">**Name**</span></span>  
 <span data-ttu-id="8d915-111">Consente di visualizzare i nomi delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="8d915-111">View the names of the available input columns.</span></span>  
  
 <span data-ttu-id="8d915-112">**Pass-through**</span><span class="sxs-lookup"><span data-stu-id="8d915-112">**Pass Through**</span></span>  
 <span data-ttu-id="8d915-113">Consente di indicare l'inclusione delle colonne di input nell'output della trasformazione.</span><span class="sxs-lookup"><span data-stu-id="8d915-113">Specify whether to include the input columns in the output of the transformation.</span></span>  
  
 <span data-ttu-id="8d915-114">**Colonne di ricerca disponibili**</span><span class="sxs-lookup"><span data-stu-id="8d915-114">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="8d915-115">Utilizzare le caselle di controllo per selezionare le colonne su cui eseguire operazioni di ricerca fuzzy.</span><span class="sxs-lookup"><span data-stu-id="8d915-115">Use the check boxes to select columns on which to perform fuzzy lookup operations.</span></span>  
  
 <span data-ttu-id="8d915-116">**Colonna di ricerca**</span><span class="sxs-lookup"><span data-stu-id="8d915-116">**Lookup Column**</span></span>  
 <span data-ttu-id="8d915-117">Selezionare le colonne di ricerca dall'elenco delle colonne della tabella di riferimento disponibili.</span><span class="sxs-lookup"><span data-stu-id="8d915-117">Select lookup columns from the list of available reference table columns.</span></span> <span data-ttu-id="8d915-118">Queste selezioni si rifletteranno nelle selezioni delle caselle di controllo nella tabella **Colonne di ricerca disponibili** .</span><span class="sxs-lookup"><span data-stu-id="8d915-118">Your selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span> <span data-ttu-id="8d915-119">La selezione di una colonna nella tabella **Colonne di ricerca disponibili** comporta la creazione di una colonna di output contenente il valore della colonna della tabella di riferimento per ogni riga corrispondente restituita.</span><span class="sxs-lookup"><span data-stu-id="8d915-119">Selecting a column in the **Available Lookup Columns** table creates an output column that contains the reference table column value for each matching row returned.</span></span>  
  
 <span data-ttu-id="8d915-120">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="8d915-120">**Output Alias**</span></span>  
 <span data-ttu-id="8d915-121">Consente di digitare un alias per l'output relativo a ogni colonna di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8d915-121">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="8d915-122">Per impostazione predefinita viene suggerito il nome della colonna di ricerca a cui è accodato un valore di indice numerico. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="8d915-122">The default is the name of the lookup column with a numeric index value appended; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d915-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d915-123">See Also</span></span>  
 <span data-ttu-id="8d915-124">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8d915-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="8d915-125">[Editor trasformazione Ricerca fuzzy &#40;scheda tabella di riferimento&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="8d915-125">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="8d915-126">Editor trasformazione Ricerca fuzzy &#40;scheda Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="8d915-126">Fuzzy Lookup Transformation Editor &#40;Advanced Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-advanced-tab.md)  
  
  
