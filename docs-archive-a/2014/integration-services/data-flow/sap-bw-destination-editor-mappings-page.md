---
title: Editor destinazione SAP BW (pagina Mapping) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: dfa1f1d6-6b64-4331-bdc5-eaa8b7aa41a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c4c2803be3e2649f7425a2974dae8ac0a80fae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712220"
---
# <a name="sap-bw-destination-editor-mappings-page"></a><span data-ttu-id="65e66-102">Editor destinazione SAP BW (pagina Mapping)</span><span class="sxs-lookup"><span data-stu-id="65e66-102">SAP BW Destination Editor (Mappings Page)</span></span>
  <span data-ttu-id="65e66-103">Usare la pagina **Mapping** dell' **Editor destinazione SAP BW** per eseguire il mapping delle colonne di input alle colonne di destinazione.</span><span class="sxs-lookup"><span data-stu-id="65e66-103">Use the **Mappings** page of the **SAP BW Destination Editor** to map input columns to destination columns.</span></span>  
  
 <span data-ttu-id="65e66-104">Per altre informazioni sulla destinazione SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Destinazione SAP BW](sap-bw-destination.md).</span><span class="sxs-lookup"><span data-stu-id="65e66-104">To learn more about the SAP BW destination of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Destination](sap-bw-destination.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="65e66-105">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="65e66-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="65e66-106">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="65e66-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="65e66-107">**Per aprire la pagina Mapping**</span><span class="sxs-lookup"><span data-stu-id="65e66-107">**To open the Mappings page**</span></span>  
  
1.  <span data-ttu-id="65e66-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene la destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="65e66-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW destination.</span></span>  
  
2.  <span data-ttu-id="65e66-109">Nella scheda **Flusso di dati** fare doppio clic sulla destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="65e66-109">On the **Data Flow** tab, double-click the SAP BW destination.</span></span>  
  
3.  <span data-ttu-id="65e66-110">Nell' **Editor destinazione SAP BW**fare clic su **Mapping** per aprire la pagina **Mapping** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="65e66-110">In the **SAP BW Destination Editor**, click **Mappings** to open the **Mappings** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="65e66-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="65e66-111">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65e66-112">Se non si conoscono tutti i valori richiesti per configurare la destinazione, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="65e66-112">If you do not know all the values that are required to configure the destination, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="65e66-113">La pagina **Mapping** dell' **Editor destinazione SAP BW** contiene due sezioni:</span><span class="sxs-lookup"><span data-stu-id="65e66-113">The **Mappings** page of the **SAP BW Destination Editor consists** of two sections:</span></span>  
  
-   <span data-ttu-id="65e66-114">Nella sezione superiore sono visualizzate le colonne di input e di destinazione disponibili ed è possibile creare mapping tra i due tipi di colonne.</span><span class="sxs-lookup"><span data-stu-id="65e66-114">The upper section shows the available input and destination columns and lets you create mappings between these two types of columns.</span></span>  
  
-   <span data-ttu-id="65e66-115">Nella sezione inferiore è riportata una tabella che mostra i mapping tra le colonne di input e le colonne di output.</span><span class="sxs-lookup"><span data-stu-id="65e66-115">The lower section is a table that lists which input columns have been mapped to which output columns.</span></span>  
  
### <a name="upper-section-options"></a><span data-ttu-id="65e66-116">Opzioni della sezione superiore</span><span class="sxs-lookup"><span data-stu-id="65e66-116">Upper Section Options</span></span>  
 <span data-ttu-id="65e66-117">Nella sezione superiore sono presenti le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="65e66-117">The upper section has the following options:</span></span>  
  
 <span data-ttu-id="65e66-118">**Colonne di input disponibili**</span><span class="sxs-lookup"><span data-stu-id="65e66-118">**Available Input Columns**</span></span>  
 <span data-ttu-id="65e66-119">Consente di visualizzare l'elenco delle colonne di input disponibili.</span><span class="sxs-lookup"><span data-stu-id="65e66-119">View the list of available input columns.</span></span>  
  
 <span data-ttu-id="65e66-120">Per eseguire il mapping di una colonna di input a una colonna di destinazione, trascinare una colonna dall'elenco **Colonne di input disponibili** su una colonna dell'elenco **Colonne di destinazione disponibili** .</span><span class="sxs-lookup"><span data-stu-id="65e66-120">To map an input column to a destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="65e66-121">**Colonne di destinazione disponibili**</span><span class="sxs-lookup"><span data-stu-id="65e66-121">**Available Destination Columns**</span></span>  
 <span data-ttu-id="65e66-122">Consente di visualizzare l'elenco delle colonne di destinazione disponibili.</span><span class="sxs-lookup"><span data-stu-id="65e66-122">View the list of available destination columns.</span></span>  
  
 <span data-ttu-id="65e66-123">Per eseguire il mapping di una colonna di input a una colonna di destinazione, trascinare una colonna dall'elenco **Colonne di input disponibili** su una colonna dell'elenco **Colonne di destinazione disponibili** .</span><span class="sxs-lookup"><span data-stu-id="65e66-123">To map an input column to destination column, drag a column from the **Available Input Columns** list and drop that column onto a column in the **Available Destination Columns** list.</span></span>  
  
 <span data-ttu-id="65e66-124">Nella sezione superiore è inoltre presente un menu di scelta rapida che è possibile aprire facendo clic con il pulsante destro del mouse sullo sfondo.</span><span class="sxs-lookup"><span data-stu-id="65e66-124">The upper section also has a context menu that you can open by right-clicking on the background.</span></span> <span data-ttu-id="65e66-125">Nel menu di scelta rapida sono presenti le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="65e66-125">This context menu contains the following options:</span></span>  
  
-   <span data-ttu-id="65e66-126">**Seleziona tutti i mapping**</span><span class="sxs-lookup"><span data-stu-id="65e66-126">**Select All Mappings**</span></span>  
  
-   <span data-ttu-id="65e66-127">**Elimina mapping selezionati**</span><span class="sxs-lookup"><span data-stu-id="65e66-127">**Delete Selected Mappings**</span></span>  
  
-   <span data-ttu-id="65e66-128">**Mappa elementi tramite corrispondenza nomi**</span><span class="sxs-lookup"><span data-stu-id="65e66-128">**Map Items by Matching Names**</span></span>  
  
### <a name="lower-section-columns"></a><span data-ttu-id="65e66-129">Colonne della sezione inferiore</span><span class="sxs-lookup"><span data-stu-id="65e66-129">Lower Section Columns</span></span>  
 <span data-ttu-id="65e66-130">La sezione inferiore è una tabella dei mapping e contiene le colonne seguenti:</span><span class="sxs-lookup"><span data-stu-id="65e66-130">The lower section is a table of the mappings, and has the following columns:</span></span>  
  
 <span data-ttu-id="65e66-131">**Colonna di input**</span><span class="sxs-lookup"><span data-stu-id="65e66-131">**Input Column**</span></span>  
 <span data-ttu-id="65e66-132">Visualizzare le colonne di input selezionate.</span><span class="sxs-lookup"><span data-stu-id="65e66-132">View the input columns that you have selected.</span></span>  
  
 <span data-ttu-id="65e66-133">Per eseguire il mapping di un'altra colonna di input alla stessa colonna di destinazione, selezionare un'altra colonna di input nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="65e66-133">To map a different input column to the same destination column, select a different input column in the list.</span></span> <span data-ttu-id="65e66-134">Per rimuovere un mapping, selezionare **\<ignore>** per escludere la colonna di input dall'output.</span><span class="sxs-lookup"><span data-stu-id="65e66-134">To remove a mapping, select **\<ignore>** to exclude the input column from the output.</span></span>  
  
 <span data-ttu-id="65e66-135">**Colonna di destinazione**</span><span class="sxs-lookup"><span data-stu-id="65e66-135">**Destination Column**</span></span>  
 <span data-ttu-id="65e66-136">Visualizzare ogni colonna di destinazione disponibile, indipendentemente dal fatto che ne venga eseguito il mapping.</span><span class="sxs-lookup"><span data-stu-id="65e66-136">View each available destination column, regardless of whether that column is mapped or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65e66-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65e66-137">See Also</span></span>  
 <span data-ttu-id="65e66-138">[Editor destinazione SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-destination-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="65e66-138">[SAP BW Destination Editor &#40;Connection Manager Page&#41;](sap-bw-destination-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="65e66-139">[Editor destinazione SAP BW &#40;pagina Output degli errori&#41;](sap-bw-destination-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="65e66-139">[SAP BW Destination Editor &#40;Error Output Page&#41;](sap-bw-destination-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="65e66-140">[Editor destinazione SAP BW &#40;pagina Avanzate&#41;](sap-bw-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="65e66-140">[SAP BW Destination Editor &#40;Advanced Page&#41;](sap-bw-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="65e66-141">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="65e66-141">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
