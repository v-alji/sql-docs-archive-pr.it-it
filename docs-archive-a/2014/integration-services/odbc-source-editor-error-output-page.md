---
title: Editor origine ODBC (pagina output degli errori) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.errorhandling.f1
ms.assetid: b2f6866c-db07-4cb3-9f38-889f8d2b03e6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a8e169875a26efbe0a7f1ac3d06856b393266eb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718563"
---
# <a name="odbc-source-editor-error-output-page"></a><span data-ttu-id="9ab18-102">Editor origine ODBC (pagina Output degli errori)</span><span class="sxs-lookup"><span data-stu-id="9ab18-102">ODBC Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="9ab18-103">Usare la pagina **Output degli errori** della finestra di dialogo **ODBC Source Editor** (Editor origine ODBC) per selezionare le opzioni di gestione degli errori.</span><span class="sxs-lookup"><span data-stu-id="9ab18-103">Use the **Error Output** page of the **ODBC Source Editor** dialog box to select error handling options.</span></span>  
  
 <span data-ttu-id="9ab18-104">Per sapere di più sull'origine ODBC, vedere [Origine CDC](data-flow/cdc-source.md).</span><span class="sxs-lookup"><span data-stu-id="9ab18-104">To learn more about the ODBC source, see [CDC Source](data-flow/cdc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="9ab18-105">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="9ab18-105">Task List</span></span>  
 <span data-ttu-id="9ab18-106">**Per aprire ODBC Source Editor (pagina Output degli errori)**</span><span class="sxs-lookup"><span data-stu-id="9ab18-106">**To open the ODBC Source Editor Error Output Page**</span></span>  
  
-   <span data-ttu-id="9ab18-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], aprire il pacchetto [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] che contiene l'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="9ab18-107">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="9ab18-108">Nella scheda **Flusso di dati** fare doppio clic sull'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="9ab18-108">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
-   <span data-ttu-id="9ab18-109">In **ODBC Source Editor**(Editor origine ODBC) fare clic su **Output degli errori**.</span><span class="sxs-lookup"><span data-stu-id="9ab18-109">In the **ODBC Source Editor**, click **Error Output**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9ab18-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9ab18-110">Options</span></span>  
  
### <a name="inputoutput"></a><span data-ttu-id="9ab18-111">Input/Output</span><span class="sxs-lookup"><span data-stu-id="9ab18-111">Input/Output</span></span>  
 <span data-ttu-id="9ab18-112">Consente di visualizzare il nome dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="9ab18-112">View the name of the data source.</span></span>  
  
### <a name="column"></a><span data-ttu-id="9ab18-113">Colonna</span><span class="sxs-lookup"><span data-stu-id="9ab18-113">Column</span></span>  
 <span data-ttu-id="9ab18-114">Non usato.</span><span class="sxs-lookup"><span data-stu-id="9ab18-114">Not used.</span></span>  
  
### <a name="error"></a><span data-ttu-id="9ab18-115">Errore</span><span class="sxs-lookup"><span data-stu-id="9ab18-115">Error</span></span>  
 <span data-ttu-id="9ab18-116">Consente di selezionare il modo in cui l'origine ODBC deve gestire gli errori in un flusso: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="9ab18-116">Select how the ODBC source should handle errors in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="truncation"></a><span data-ttu-id="9ab18-117">Troncamento</span><span class="sxs-lookup"><span data-stu-id="9ab18-117">Truncation</span></span>  
 <span data-ttu-id="9ab18-118">Consente di selezionare il modo in cui l'origine ODBC deve gestire il troncamento in un flusso: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="9ab18-118">Select how the ODBC source should handle truncation in a flow: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="description"></a><span data-ttu-id="9ab18-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ab18-119">Description</span></span>  
 <span data-ttu-id="9ab18-120">Non usato.</span><span class="sxs-lookup"><span data-stu-id="9ab18-120">Not used.</span></span>  
  
### <a name="set-this-value-to-selected-cells"></a><span data-ttu-id="9ab18-121">Imposta questo valore nelle celle selezionate</span><span class="sxs-lookup"><span data-stu-id="9ab18-121">Set this value to selected cells</span></span>  
 <span data-ttu-id="9ab18-122">Consente di selezionare il modo in cui l'origine ODBC gestisce tutte le celle selezionate in caso di errore o troncamento: ignorare l'errore, reindirizzare la riga o interrompere il componente.</span><span class="sxs-lookup"><span data-stu-id="9ab18-122">Select how the ODBC source handles all selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
### <a name="apply"></a><span data-ttu-id="9ab18-123">Applica</span><span class="sxs-lookup"><span data-stu-id="9ab18-123">Apply</span></span>  
 <span data-ttu-id="9ab18-124">Consente di applicare le opzioni di gestione degli errori alle celle selezionate.</span><span class="sxs-lookup"><span data-stu-id="9ab18-124">Apply the error handling options to the selected cells.</span></span>  
  
## <a name="error-handling-options"></a><span data-ttu-id="9ab18-125">Opzioni di gestione degli errori</span><span class="sxs-lookup"><span data-stu-id="9ab18-125">Error Handling Options</span></span>  
 <span data-ttu-id="9ab18-126">Utilizzare le opzioni seguenti per configurare il modo in cui l'origine ODBC gestisce errori e troncamenti.</span><span class="sxs-lookup"><span data-stu-id="9ab18-126">You use the following options to configure how the ODBC source handles errors and truncations.</span></span>  
  
### <a name="fail-component"></a><span data-ttu-id="9ab18-127">Interrompi componente</span><span class="sxs-lookup"><span data-stu-id="9ab18-127">Fail Component</span></span>  
 <span data-ttu-id="9ab18-128">Quando si verifica un errore o un troncamento l'attività Flusso di dati viene interrotta.</span><span class="sxs-lookup"><span data-stu-id="9ab18-128">The Data Flow task fails when an error or a truncation occurs.</span></span> <span data-ttu-id="9ab18-129">Questo è il comportamento predefinito.</span><span class="sxs-lookup"><span data-stu-id="9ab18-129">This is the default behavior.</span></span>  
  
### <a name="ignore-failure"></a><span data-ttu-id="9ab18-130">Ignora errore</span><span class="sxs-lookup"><span data-stu-id="9ab18-130">Ignore Failure</span></span>  
 <span data-ttu-id="9ab18-131">L'errore o il troncamento vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="9ab18-131">The error or the truncation is ignored.</span></span>  
  
### <a name="redirect-flow"></a><span data-ttu-id="9ab18-132">Reindirizza flusso</span><span class="sxs-lookup"><span data-stu-id="9ab18-132">Redirect Flow</span></span>  
 <span data-ttu-id="9ab18-133">La riga che determina l'errore o il troncamento viene inviata all'output degli errori dell'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="9ab18-133">The row that is causing the error or the truncation is directed to the error output of the ODBC source.</span></span> <span data-ttu-id="9ab18-134">Per altre informazioni, vedere [Origine ODBC](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="9ab18-134">For more information, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab18-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ab18-135">See Also</span></span>  
 <span data-ttu-id="9ab18-136">[Editor origine ODBC &#40;pagina Gestione connessione&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="9ab18-136">[ODBC Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/odbc-source-editor-connection-manager-page.md) </span></span>  
 [<span data-ttu-id="9ab18-137">Editor origine ODBC &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="9ab18-137">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-columns-page.md)  
  
  
