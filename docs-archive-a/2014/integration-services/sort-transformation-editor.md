---
title: Editor trasformazione ordinamento | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sorttransformation.f1
helpviewer_keywords:
- Sort Transformation Editor
ms.assetid: 8ae23970-49a9-4d6d-9f15-c7074783347c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9f48c366f4337af29b03877f6bb20b804457a293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726031"
---
# <a name="sort-transformation-editor"></a><span data-ttu-id="870f8-102">Editor trasformazione Ordinamento</span><span class="sxs-lookup"><span data-stu-id="870f8-102">Sort Transformation Editor</span></span>
  <span data-ttu-id="870f8-103">Utilizzare la finestra di dialogo **Editor trasformazione Ordinamento** per selezionare le colonne da ordinare, impostare il tipo di ordinamento e specificare se rimuovere i duplicati.</span><span class="sxs-lookup"><span data-stu-id="870f8-103">Use the **Sort Transformation Editor** dialog box to select the columns to sort, set the sort order, and specify whether duplicates are removed.</span></span>  
  
 <span data-ttu-id="870f8-104">Per ulteriori informazioni sulla trasformazione Ordinamento, vedere [Sort Transformation](data-flow/transformations/sort-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="870f8-104">To learn more about the Sort transformation, see [Sort Transformation](data-flow/transformations/sort-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="870f8-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="870f8-105">Options</span></span>  
 <span data-ttu-id="870f8-106">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="870f8-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="870f8-107">Consente di specificare le colonne da ordinare utilizzando le caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="870f8-107">Using the check boxes, specify the columns to sort.</span></span>  
  
 <span data-ttu-id="870f8-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="870f8-108">**Name**</span></span>  
 <span data-ttu-id="870f8-109">Consente di visualizzare il nome di ogni colonna di input disponibile.</span><span class="sxs-lookup"><span data-stu-id="870f8-109">View the name of each available input column.</span></span>  
  
 <span data-ttu-id="870f8-110">**Pass-through**</span><span class="sxs-lookup"><span data-stu-id="870f8-110">**Passthrough**</span></span>  
 <span data-ttu-id="870f8-111">Indica se includere la colonna nell'output ordinato.</span><span class="sxs-lookup"><span data-stu-id="870f8-111">Indicate whether to include the column in the sorted output.</span></span>  
  
 <span data-ttu-id="870f8-112">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="870f8-112">**Input Column**</span></span>  
 <span data-ttu-id="870f8-113">Consente di selezionare una colonna di input nell'elenco delle colonne di input disponibili per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="870f8-113">Select from the list of available input columns for each row.</span></span> <span data-ttu-id="870f8-114">Le selezioni effettuate vengono riflesse nelle selezioni delle caselle di controllo nella tabella **Colonne di input disponibili** .</span><span class="sxs-lookup"><span data-stu-id="870f8-114">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="870f8-115">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="870f8-115">**Output Alias**</span></span>  
 <span data-ttu-id="870f8-116">Consente di digitare un alias per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="870f8-116">Type an alias for each output column.</span></span> <span data-ttu-id="870f8-117">Per impostazione predefinita viene suggerito il nome della colonna di input. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="870f8-117">The default is the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
 <span data-ttu-id="870f8-118">**Tipo di ordinamento**</span><span class="sxs-lookup"><span data-stu-id="870f8-118">**Sort Type**</span></span>  
 <span data-ttu-id="870f8-119">Indica se eseguire l'ordinamento in ordine crescente o decrescente.</span><span class="sxs-lookup"><span data-stu-id="870f8-119">Indicate whether to sort in ascending or descending order.</span></span>  
  
 <span data-ttu-id="870f8-120">**Ordinamento**</span><span class="sxs-lookup"><span data-stu-id="870f8-120">**Sort Order**</span></span>  
 <span data-ttu-id="870f8-121">Indica l'ordine da utilizzare per l'ordinamento delle colonne.</span><span class="sxs-lookup"><span data-stu-id="870f8-121">Indicate the order in which to sort columns.</span></span> <span data-ttu-id="870f8-122">È possibile impostare questa opzione in modo manuale per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="870f8-122">This must be set manually for each column.</span></span>  
  
 <span data-ttu-id="870f8-123">**Flag di confronto**</span><span class="sxs-lookup"><span data-stu-id="870f8-123">**Comparison Flags**</span></span>  
 <span data-ttu-id="870f8-124">Per altre informazioni sulle opzioni per il confronto di stringhe, vedere [Confronto di dati stringa](data-flow/comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="870f8-124">For information about the string comparison options, see [Comparing String Data](data-flow/comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="870f8-125">**Rimuovi righe con valori di ordinamento duplicati**</span><span class="sxs-lookup"><span data-stu-id="870f8-125">**Remove rows with duplicate sort values**</span></span>  
 <span data-ttu-id="870f8-126">Indica se la trasformazione copia le righe duplicate nell'output della trasformazione o se invece crea un'unica voce per tutti i duplicati in base alla stringa specificata nelle opzioni di confronto.</span><span class="sxs-lookup"><span data-stu-id="870f8-126">Indicate whether the transformation copies duplicate rows to the transformation output, or creates a single entry for all duplicates, based on the specified string comparison options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870f8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="870f8-127">See Also</span></span>  
 [<span data-ttu-id="870f8-128">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="870f8-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
