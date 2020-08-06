---
title: Editor origine CDC (pagina output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.errorhandling.f1
ms.assetid: 8a4c2cb8-fd2f-4c45-824f-b93473a8981e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b39532304fddfa90fabe8cafe2a6caf5b1fb5c8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636838"
---
# <a name="cdc-source-editor-error-output-page"></a><span data-ttu-id="74232-102">Editor origine CDC (pagina Output degli errori)</span><span class="sxs-lookup"><span data-stu-id="74232-102">CDC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="74232-103">Usare la pagina **Output degli errori** della finestra di dialogo **Editor origine CDC** per selezionare le opzioni di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="74232-103">Use the **Error Output** page of the **CDC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="74232-104">Per ulteriori informazioni sull'origine CDC, vedere [CDC Source](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="74232-104">To learn more about the CDC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="74232-105">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="74232-105">Task List</span></span>  
 <span data-ttu-id="74232-106">**Per aprire CDC Source Editor (pagina Output degli errori)**</span><span class="sxs-lookup"><span data-stu-id="74232-106">**To open the CDC Source Editor Error Output Page**</span></span>  
  
1.  <span data-ttu-id="74232-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], aprire il pacchetto [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] che contiene l'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="74232-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the CDC source.</span></span>  
  
2.  <span data-ttu-id="74232-108">Nella scheda **Flusso di dati** fare doppio clic sull'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="74232-108">On the **Data Flow** tab, double-click the CDC source.</span></span>  
  
3.  <span data-ttu-id="74232-109">In **Editor origine CDC**fare clic su **Output degli errori**.</span><span class="sxs-lookup"><span data-stu-id="74232-109">In the **CDC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="74232-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="74232-110">Options</span></span>  
 <span data-ttu-id="74232-111">**Input/Output**</span><span class="sxs-lookup"><span data-stu-id="74232-111">**Input/Output**</span></span>  
 <span data-ttu-id="74232-112">Consente di visualizzare il nome dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="74232-112">View the name of the data source.</span></span>  
  
 <span data-ttu-id="74232-113">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="74232-113">**Column**</span></span>  
 <span data-ttu-id="74232-114">Consente di visualizzare le colonne esterne (di origine) selezionate nella pagina **Gestione connessione** della finestra di dialogo **Editor origine CDC** .</span><span class="sxs-lookup"><span data-stu-id="74232-114">View the external (source) columns that you selected on the **Connection Manager** page of the **CDC Source Editor** dialog box.</span></span>  
  
 <span data-ttu-id="74232-115">**Error (Errore) (Error (Errore)e)**</span><span class="sxs-lookup"><span data-stu-id="74232-115">**Error**</span></span>  
 <span data-ttu-id="74232-116">Consente di selezionare il modo in cui l'origine CDC deve gestire gli errori in un flusso: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="74232-116">Select how the CDC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="74232-117">**Troncamento**</span><span class="sxs-lookup"><span data-stu-id="74232-117">**Truncation**</span></span>  
 <span data-ttu-id="74232-118">Consente di selezionare il modo in cui l'origine CDC deve gestire il troncamento in un flusso: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="74232-118">Select how the CDC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="74232-119">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="74232-119">**Description**</span></span>  
 <span data-ttu-id="74232-120">Non usato.</span><span class="sxs-lookup"><span data-stu-id="74232-120">Not used.</span></span>  
  
 <span data-ttu-id="74232-121">**Imposta questo valore nelle celle selezionate**</span><span class="sxs-lookup"><span data-stu-id="74232-121">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="74232-122">Consente di selezionare il modo in cui l'origine CDC gestisce tutte le celle selezionate in caso di errore o troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="74232-122">Select how the CDC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="74232-123">**Applica**</span><span class="sxs-lookup"><span data-stu-id="74232-123">**Apply**</span></span>  
 <span data-ttu-id="74232-124">Consente di applicare le opzioni di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="74232-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="74232-125">Opzioni di gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="74232-125">Error Handling Options</span></span>  
 <span data-ttu-id="74232-126">Utilizzare le opzioni seguenti per configurare il modo in cui l'origine CDC gestisce errori e troncamenti.</span><span class="sxs-lookup"><span data-stu-id="74232-126">You use the following options to configure how the CDC source handles errors and truncations.</span></span>  
  
 <span data-ttu-id="74232-127">**Interrompi componente**</span><span class="sxs-lookup"><span data-stu-id="74232-127">**Fail Component**</span></span>  
 <span data-ttu-id="74232-128">Quando si verifica un errore o un troncamento l'attività Flusso di dati viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="74232-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="74232-129">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="74232-129">This is the default behavior.</span></span>  
  
 <span data-ttu-id="74232-130">**Ignora errore**</span><span class="sxs-lookup"><span data-stu-id="74232-130">**Ignore Failure**</span></span>  
 <span data-ttu-id="74232-131">L'errore o il troncamento viene ignorato e la riga di dati viene indirizzata all'output dell'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="74232-131">The error or the truncation is ignored and the data row is directed to the CDC source output.</span></span>  
  
 <span data-ttu-id="74232-132">**Reindirizza flusso**</span><span class="sxs-lookup"><span data-stu-id="74232-132">**Redirect Flow**</span></span>  
 <span data-ttu-id="74232-133">La riga di dati contenente l'errore o il troncamento viene indirizzata all'output degli errori dell'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="74232-133">The error or the truncation data row is directed to the error output of the CDC source.</span></span> <span data-ttu-id="74232-134">In questo caso, viene utilizzata la gestione degli errori dell'origine CDC.</span><span class="sxs-lookup"><span data-stu-id="74232-134">In this case the CDC source error handling is used.</span></span> <span data-ttu-id="74232-135">Per altre informazioni, vedere [Origine CDC](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="74232-135">For more information, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74232-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74232-136">See Also</span></span>  
 <span data-ttu-id="74232-137">[Editor origine CDC &#40;pagina Gestione connessione&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="74232-137">[CDC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/cdc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="74232-138">Editor origine CDC &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="74232-138">CDC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/cdc-source-editor-columns-page.md)  
  
  
