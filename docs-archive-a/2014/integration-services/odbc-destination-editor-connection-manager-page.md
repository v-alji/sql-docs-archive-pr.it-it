---
title: Editor destinazione ODBC (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.connection.f1
ms.assetid: f6d9c6c2-e4c4-468b-9e0d-af7b9609614d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e4fc1073bb187c0864d2991459a358a7f81d066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718582"
---
# <a name="odbc-destination-editor-connection-manager-page"></a><span data-ttu-id="12deb-102">Editor destinazione ODBC (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="12deb-102">ODBC Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="12deb-103">Utilizzare la pagina **Gestione connessione** della finestra di dialogo **ODBC Destination Editor** per selezionare la gestione connessione ODBC per la destinazione.</span><span class="sxs-lookup"><span data-stu-id="12deb-103">Use the **Connection Manager** page of the **ODBC Destination Editor** dialog box to select the ODBC connection manager for the destination.</span></span> <span data-ttu-id="12deb-104">Tramite questa pagina è inoltre possibile selezionare una tabella o una vista del database</span><span class="sxs-lookup"><span data-stu-id="12deb-104">This page also lets you select a table or view from the database</span></span>  
  
 <span data-ttu-id="12deb-105">Per ulteriori informazioni sulla destinazione ODBC, vedere [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="12deb-105">For more information about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="12deb-106">**Per aprire ODBC Destination Editor (pagina Gestione connessione)**</span><span class="sxs-lookup"><span data-stu-id="12deb-106">**To open the ODBC Destination Editor Connection Manager Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="12deb-107">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="12deb-107">Task List</span></span>  
  
-   <span data-ttu-id="12deb-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], aprire il pacchetto [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] con la destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="12deb-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="12deb-109">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione ODBC.</span><span class="sxs-lookup"><span data-stu-id="12deb-109">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="12deb-110">In **ODBC Destination Editor**, fare clic su **Gestione connessione**.</span><span class="sxs-lookup"><span data-stu-id="12deb-110">In the **ODBC Destination Editor**, click **Connection Manager**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="12deb-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="12deb-111">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="12deb-112">Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="12deb-112">Connection manager</span></span>  
 <span data-ttu-id="12deb-113">Consente di selezionare una gestione connessione ODBC esistente nell'elenco o di creare una nuova connessione facendo clic su Nuova.</span><span class="sxs-lookup"><span data-stu-id="12deb-113">Select an existing ODBC connection manager from the list, or click New to create a new connection.</span></span> <span data-ttu-id="12deb-114">La connessione può essere a qualsiasi database supportato da ODBC.</span><span class="sxs-lookup"><span data-stu-id="12deb-114">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="12deb-115">Nuovo</span><span class="sxs-lookup"><span data-stu-id="12deb-115">New</span></span>  
 <span data-ttu-id="12deb-116">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="12deb-116">Click **New**.</span></span> <span data-ttu-id="12deb-117">Viene visualizzata la finestra di dialogo **Configura gestione connessione ODBC** in cui è possibile creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="12deb-117">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="12deb-118">Modalità di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="12deb-118">Data Access Mode</span></span>  
 <span data-ttu-id="12deb-119">Consente di selezionare il metodo di caricamento dei dati nella destinazione.</span><span class="sxs-lookup"><span data-stu-id="12deb-119">Select the method for loading data to the destination.</span></span> <span data-ttu-id="12deb-120">Le opzioni disponibili vengono visualizzate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="12deb-120">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="12deb-121">Opzione</span><span class="sxs-lookup"><span data-stu-id="12deb-121">Option</span></span>|<span data-ttu-id="12deb-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12deb-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="12deb-123">Nome tabella - Batch</span><span class="sxs-lookup"><span data-stu-id="12deb-123">Table Name - Batch</span></span>|<span data-ttu-id="12deb-124">Selezionare questa opzione per configurare la destinazione ODBC per l'utilizzo della modalità batch.</span><span class="sxs-lookup"><span data-stu-id="12deb-124">Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="12deb-125">Se si seleziona questa opzione, sono disponibili le opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="12deb-125">When you select this option the following options are available:</span></span>|  
||<span data-ttu-id="12deb-126">**Nome tabella o vista**: selezionare una tabella o vista disponibile nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="12deb-126">**Name of the table or the view**: Select an available table or view from the list.</span></span><br /><br /> <span data-ttu-id="12deb-127">Questo elenco contiene solo le prime 1000 tabelle.</span><span class="sxs-lookup"><span data-stu-id="12deb-127">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="12deb-128">Se il database contiene più di 1000 tabelle, è possibile digitare l'inizio di un nome di tabella o usare il carattere jolly (\*) per immettere qualsiasi parte del nome e visualizzare la tabella o le tabelle che si vuole usare.</span><span class="sxs-lookup"><span data-stu-id="12deb-128">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span><br /><br /> <span data-ttu-id="12deb-129">**Dimensioni batch**: digitare la dimensione del batch per il caricamento bulk.</span><span class="sxs-lookup"><span data-stu-id="12deb-129">**Batch size**: Type the size of the batch for bulk loading.</span></span> <span data-ttu-id="12deb-130">Si tratta del numero di righe caricato come un batch</span><span class="sxs-lookup"><span data-stu-id="12deb-130">This is the number of rows loaded as a batch</span></span>|  
|<span data-ttu-id="12deb-131">Nome tabella - Riga per riga</span><span class="sxs-lookup"><span data-stu-id="12deb-131">Table Name - Row by Row</span></span>|<span data-ttu-id="12deb-132">Selezionare questa opzione per configurare la destinazione ODBC per l'inserimento di una riga per volta nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="12deb-132">Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="12deb-133">Se si seleziona questa opzione, è disponibile l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="12deb-133">When you select this option the following option is available:</span></span>|  
||<span data-ttu-id="12deb-134">**Nome tabella o vista**: selezionare una tabella o vista disponibile del database dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="12deb-134">**Name of the table or the view**: Select an available table or view from the database from the list.</span></span><br /><br /> <span data-ttu-id="12deb-135">Questo elenco contiene solo le prime 1000 tabelle.</span><span class="sxs-lookup"><span data-stu-id="12deb-135">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="12deb-136">Se il database contiene più di 1000 tabelle, è possibile digitare l'inizio di un nome di tabella o utilizzare il carattere jolly (\*) per immettere qualsiasi parte del nome e visualizzare la tabella o le tabelle che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="12deb-136">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="12deb-137">Anteprima</span><span class="sxs-lookup"><span data-stu-id="12deb-137">Preview</span></span>  
 <span data-ttu-id="12deb-138">Fare clic su **Anteprima** per visualizzare fino a 200 dati per la tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="12deb-138">Click **Preview** to view up to 200 rows of data for the table that you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12deb-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12deb-139">See Also</span></span>  
 <span data-ttu-id="12deb-140">[Proprietà personalizzate della destinazione ODBC](data-flow/odbc-destination-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="12deb-140">[ODBC Destination Custom Properties](data-flow/odbc-destination-custom-properties.md) </span></span>  
 <span data-ttu-id="12deb-141">[Editor destinazione ODBC pagina mapping &#40;&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="12deb-141">[ODBC Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="12deb-142">Editor destinazione ODBC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="12deb-142">ODBC Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-error-output-page.md)  
  
  
