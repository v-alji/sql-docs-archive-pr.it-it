---
title: Editor trasformazione Ricerca (pagina colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.columns.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: 690ffef5-fd59-4e95-a27d-4fcf0d6b1c0b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b768076d8acbcaef8cbff21783a7697020e027eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628810"
---
# <a name="lookup-transformation-editor-columns-page"></a><span data-ttu-id="c17e3-102">Editor trasformazione Ricerca (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="c17e3-102">Lookup Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="c17e3-103">Utilizzare la pagina **Colonne** della finestra di dialogo **Editor trasformazione Ricerca** per specificare il join tra la tabella di origine e la tabella di riferimento e selezionare colonne di ricerca nella tabella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c17e3-103">Use the **Columns** page of the **Lookup Transformation Editor** dialog box to specify the join between the source table and the reference table, and to select lookup columns from the reference table.</span></span>  
  
 <span data-ttu-id="c17e3-104">Per ulteriori informazioni sulla trasformazione Ricerca, vedere [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c17e3-104">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c17e3-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c17e3-105">Options</span></span>  
 <span data-ttu-id="c17e3-106">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="c17e3-106">**Available Input Columns**</span></span>  
 <span data-ttu-id="c17e3-107">Consente di visualizzare l'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="c17e3-107">View the list of available input columns.</span></span> <span data-ttu-id="c17e3-108">Le colonne di input sono le colonne nel flusso di dati provenienti da un'origine connessa.</span><span class="sxs-lookup"><span data-stu-id="c17e3-108">The input columns are the columns in the data flow from a connected source.</span></span> <span data-ttu-id="c17e3-109">Le colonne di input e le colonne di ricerca devono contenere tipi di dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c17e3-109">The input columns and lookup column must have matching data types.</span></span>  
  
 <span data-ttu-id="c17e3-110">Effettuare un'operazione di trascinamento della selezione per eseguire il mapping delle colonne di input disponibili alle colonne di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c17e3-110">Use a drag-and-drop operation to map available input columns to lookup columns.</span></span>  
  
 <span data-ttu-id="c17e3-111">È anche possibile eseguire il mapping delle colonne di input alle colonne di ricerca mediante la tastiera, evidenziando una colonna nella tabella **Colonne di input disponibili** , premendo il tasto MENU SCELTA RAPIDA, quindi facendo clic su **Modifica mapping**.</span><span class="sxs-lookup"><span data-stu-id="c17e3-111">You can also map input columns to lookup columns using the keyboard, by highlighting a column in the **Available Input Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="c17e3-112">**Colonne di ricerca disponibili**</span><span class="sxs-lookup"><span data-stu-id="c17e3-112">**Available Lookup Columns**</span></span>  
 <span data-ttu-id="c17e3-113">Consente di visualizzare l'elenco delle colonne di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c17e3-113">View the list of lookup columns.</span></span> <span data-ttu-id="c17e3-114">Le colonne di ricerca sono colonne nella tabella di riferimento nelle quali si desidera cercare i valori corrispondenti alle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="c17e3-114">The lookup columns are columns in the reference table in which you want to look up values that match the input columns.</span></span>  
  
 <span data-ttu-id="c17e3-115">Eseguire un'operazione di trascinamento della selezione per eseguire il mapping delle colonne di ricerca disponibili alle colonne di input.</span><span class="sxs-lookup"><span data-stu-id="c17e3-115">Use a drag-and-drop operation to map available lookup columns to input columns.</span></span>  
  
 <span data-ttu-id="c17e3-116">Utilizzare le caselle di controllo per selezionare le colonne di ricerca nella tabella di riferimento su cui eseguire operazioni di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c17e3-116">Use the check boxes to select lookup columns in the reference table on which to perform lookup operations.</span></span>  
  
 <span data-ttu-id="c17e3-117">È anche possibile eseguire il mapping delle colonne di ricerca alle colonne di input mediante la tastiera, evidenziando una colonna nella tabella **Colonne di ricerca disponibili** , premendo il tasto MENU SCELTA RAPIDA, quindi facendo clic su **Modifica mapping**.</span><span class="sxs-lookup"><span data-stu-id="c17e3-117">You can also map lookup columns to input columns using the keyboard, by highlighting a column in the **Available Lookup Columns** table, pressing the Application key, and then clicking **Edit Mappings**.</span></span>  
  
 <span data-ttu-id="c17e3-118">**Colonna di ricerca**</span><span class="sxs-lookup"><span data-stu-id="c17e3-118">**Lookup Column**</span></span>  
 <span data-ttu-id="c17e3-119">Consente di visualizzare le colonne di ricerca selezionate.</span><span class="sxs-lookup"><span data-stu-id="c17e3-119">View the selected lookup columns.</span></span> <span data-ttu-id="c17e3-120">Le selezioni effettuate vengono riflesse nelle selezioni delle caselle di controllo nella tabella **Colonne di ricerca disponibili** .</span><span class="sxs-lookup"><span data-stu-id="c17e3-120">The selections are reflected in the check box selections in the **Available Lookup Columns** table.</span></span>  
  
 <span data-ttu-id="c17e3-121">**Operazione di ricerca**</span><span class="sxs-lookup"><span data-stu-id="c17e3-121">**Lookup Operation**</span></span>  
 <span data-ttu-id="c17e3-122">Consente di selezionare un'operazione di ricerca da eseguire sulla colonna di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c17e3-122">Select a lookup operation from the list to perform on the lookup column.</span></span>  
  
 <span data-ttu-id="c17e3-123">**Alias di output**</span><span class="sxs-lookup"><span data-stu-id="c17e3-123">**Output Alias**</span></span>  
 <span data-ttu-id="c17e3-124">Consente di digitare un alias per l'output relativo a ogni colonna di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c17e3-124">Type an alias for the output for each lookup column.</span></span> <span data-ttu-id="c17e3-125">Per impostazione predefinita viene suggerito il nome della colonna di ricerca. È comunque possibile scegliere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="c17e3-125">The default is the name of the lookup column; however, you can select any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17e3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c17e3-126">See Also</span></span>  
 <span data-ttu-id="c17e3-127">[Editor trasformazione Ricerca &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c17e3-127">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="c17e3-128">[Editor trasformazione Ricerca &#40;pagina connessione&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="c17e3-128">[Lookup Transformation Editor &#40;Connection Page&#41;](../../2014/integration-services/lookup-transformation-editor-connection-page.md) </span></span>  
 <span data-ttu-id="c17e3-129">[Editor trasformazione Ricerca &#40;pagina avanzate&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="c17e3-129">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="c17e3-130">[Editor trasformazione Ricerca &#40;pagina output degli errori&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c17e3-130">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="c17e3-131">Ricerca fuzzy - trasformazione</span><span class="sxs-lookup"><span data-stu-id="c17e3-131">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
