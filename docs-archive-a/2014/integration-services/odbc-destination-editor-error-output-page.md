---
title: Editor destinazione ODBC (pagina output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.errorhandling.f1
ms.assetid: 0a743f8d-2a51-4296-9976-8104f5ca22d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 475a2e00d67b221ddf05fdd273317fbab5248cd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718581"
---
# <a name="odbc-destination-editor-error-output-page"></a><span data-ttu-id="a3811-102">Editor destinazione ODBC (pagina Output errori)</span><span class="sxs-lookup"><span data-stu-id="a3811-102">ODBC Destination Editor (Error Output Page)</span></span>
  <span data-ttu-id="a3811-103">Utilizzare la pagina **Output degli errori** della finestra di dialogo **ODBC Destination Editor** per selezionare le opzioni di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="a3811-103">Use the **Error Output** page of the **ODBC Destination Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="a3811-104">Per ulteriori informazioni sulla destinazione ODBC, vedere [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="a3811-104">To learn more about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="a3811-105">**Per aprire ODBC Destination Editor (pagina Output degli errori)**</span><span class="sxs-lookup"><span data-stu-id="a3811-105">**To open the ODBC Destination Editor Error Output Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="a3811-106">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="a3811-106">Task List</span></span>  
  
-   <span data-ttu-id="a3811-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], aprire il pacchetto [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] con la destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="a3811-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="a3811-108">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="a3811-108">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="a3811-109">In **ODBC Destination Editor**, fare clic su **Output degli errori**.</span><span class="sxs-lookup"><span data-stu-id="a3811-109">In the **ODBC Destination Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a3811-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a3811-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="a3811-111">Input/Output</span><span class="sxs-lookup"><span data-stu-id="a3811-111">Input/Output</span></span>  
 <span data-ttu-id="a3811-112">Consente di visualizzare il nome dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="a3811-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="a3811-113">Colonna</span><span class="sxs-lookup"><span data-stu-id="a3811-113">Column</span></span>  
 <span data-ttu-id="a3811-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="a3811-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="a3811-115">Errore</span><span class="sxs-lookup"><span data-stu-id="a3811-115">Error</span></span>  
 <span data-ttu-id="a3811-116">Consente di selezionare il modo in cui la destinazione ODBC deve gestire gli errori in un flusso: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="a3811-116">Select how the ODBC destination should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="a3811-117">Troncamento</span><span class="sxs-lookup"><span data-stu-id="a3811-117">Truncation</span></span>  
 <span data-ttu-id="a3811-118">Consente di selezionare il modo in cui la destinazione ODBC deve gestire il troncamento in un flusso: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="a3811-118">Select how the ODBC destination should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="a3811-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3811-119">Description</span></span>  
 <span data-ttu-id="a3811-120">Consente di visualizzare una descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="a3811-120">View a description of the error.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="a3811-121">Imposta questo valore nelle celle selezionate</span><span class="sxs-lookup"><span data-stu-id="a3811-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="a3811-122">Consente di selezionare il modo in cui la destinazione ODBC gestisce tutte le celle selezionate in caso di errore o troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="a3811-122">Select how the ODBC destination handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="a3811-123">Applica</span><span class="sxs-lookup"><span data-stu-id="a3811-123">Apply</span></span>  
 <span data-ttu-id="a3811-124">Consente di applicare le opzioni di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="a3811-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="a3811-125">Opzioni di gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="a3811-125">Error Handling Options</span></span>  
 <span data-ttu-id="a3811-126">Utilizzare le opzioni seguenti per configurare il modo in cui la destinazione ODBC gestisce errori e troncamenti.</span><span class="sxs-lookup"><span data-stu-id="a3811-126">You use the following options to configure how the ODBC destination handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="a3811-127">Interrompi componente</span><span class="sxs-lookup"><span data-stu-id="a3811-127">Fail Component</span></span>  
 <span data-ttu-id="a3811-128">Quando si verifica un errore o un troncamento l'attività Flusso di dati viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="a3811-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="a3811-129">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="a3811-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="a3811-130">Ignora errore</span><span class="sxs-lookup"><span data-stu-id="a3811-130">Ignore Failure</span></span>  
 <span data-ttu-id="a3811-131">L'errore o il troncamento vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="a3811-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="a3811-132">Reindirizza flusso</span><span class="sxs-lookup"><span data-stu-id="a3811-132">Redirect Flow</span></span>  
 <span data-ttu-id="a3811-133">La riga che determina l'errore o il troncamento viene inviata all'output degli errori della destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="a3811-133">The row that is causing the error or the truncation is directed to the error output of the ODBC destination.</span></span> <span data-ttu-id="a3811-134">Per ulteriori informazioni, vedere Destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="a3811-134">For more information, see ODBC Destination.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3811-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3811-135">See Also</span></span>  
 <span data-ttu-id="a3811-136">[Editor destinazione ODBC &#40;pagina Gestione connessione&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="a3811-136">[ODBC Destination Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-destination-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="a3811-137">ODBC Destination Editor &#40;pagina Mapping&#41;</span><span class="sxs-lookup"><span data-stu-id="a3811-137">ODBC Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-mappings-page.md)  
  
  
