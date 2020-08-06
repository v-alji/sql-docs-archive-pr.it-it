---
title: Editor origine SAP BW (pagina Colonne) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c2ec8bb7-be9b-4783-ad88-32512de784b0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba605360d01abc520cedfbc457dd89319ed83c52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722931"
---
# <a name="sap-bw-source-editor-columns-page"></a><span data-ttu-id="1da00-102">Editor origine SAP BW (pagina Colonne)</span><span class="sxs-lookup"><span data-stu-id="1da00-102">SAP BW Source Editor (Columns Page)</span></span>
  <span data-ttu-id="1da00-103">Usare la pagina **Colonne** della finestra di dialogo **Editor origine SAP BW** per eseguire il mapping di una colonna di output a ogni colonna esterna (di origine).</span><span class="sxs-lookup"><span data-stu-id="1da00-103">Use the **Columns** page of the **SAP BW Source Editor** to map an output column to each external (source) column.</span></span>  
  
 <span data-ttu-id="1da00-104">Per altre informazioni sul componente di origine SAP BW di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, vedere [Origine SAP BW](sap-bw-source.md).</span><span class="sxs-lookup"><span data-stu-id="1da00-104">To learn more about the SAP BW source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Source](sap-bw-source.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1da00-105">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="1da00-105">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="1da00-106">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="1da00-106">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1da00-107">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="1da00-107">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="1da00-108">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="1da00-108">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="1da00-109">**Per aprire la pagina Colonne**</span><span class="sxs-lookup"><span data-stu-id="1da00-109">**To open the Columns page**</span></span>  
  
1.  <span data-ttu-id="1da00-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene l'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1da00-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that contains the SAP BW source.</span></span>  
  
2.  <span data-ttu-id="1da00-111">Nella scheda **Flusso di dati** fare doppio clic sull'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="1da00-111">On the **Data Flow** tab, double-click the SAP BW source.</span></span>  
  
3.  <span data-ttu-id="1da00-112">Nell' **Editor origine SAP BW**fare clic su **Colonne** per aprire la pagina **Colonne** dell'editor.</span><span class="sxs-lookup"><span data-stu-id="1da00-112">In the **SAP BW Source Editor**, click **Columns** to open the **Columns** page of the editor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1da00-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1da00-113">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1da00-114">Se non si conoscono tutti i valori richiesti per configurare l'origine, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="1da00-114">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="1da00-115">**Colonne esterne disponibili**</span><span class="sxs-lookup"><span data-stu-id="1da00-115">**Available External Columns**</span></span>  
 <span data-ttu-id="1da00-116">Visualizzare l'elenco delle colonne esterne disponibili nell'origine dati, quindi selezionare le colonne da includere nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="1da00-116">View the list of available external columns in the data source, and then select the columns to be included in the data flow.</span></span>  
  
 <span data-ttu-id="1da00-117">Per includere una colonna nel flusso di dati, selezionare la casella di controllo corrispondente a tale colonna.</span><span class="sxs-lookup"><span data-stu-id="1da00-117">To include a column in the data flow, select the check box that corresponds to that column.</span></span> <span data-ttu-id="1da00-118">L'ordine di selezione delle caselle di controllo determina l'ordine di restituzione delle colonne.</span><span class="sxs-lookup"><span data-stu-id="1da00-118">The order in which you select the check boxes determines the order in which columns will be output.</span></span> <span data-ttu-id="1da00-119">La prima casella di controllo selezionata sarà la prima colonna di output, la seconda casella di controllo sarà la seconda colonna di output e così via.</span><span class="sxs-lookup"><span data-stu-id="1da00-119">That is, the first check box that you select will be the first output column, the second check box will be the second output columns, and so on.</span></span>  
  
 <span data-ttu-id="1da00-120">**Colonna esterna**</span><span class="sxs-lookup"><span data-stu-id="1da00-120">**External Column**</span></span>  
 <span data-ttu-id="1da00-121">Visualizzare le colonne (di origine) esterne selezionate.</span><span class="sxs-lookup"><span data-stu-id="1da00-121">View the selected external (source) columns.</span></span> <span data-ttu-id="1da00-122">Le colonne selezionate sono visualizzate nell'ordine di visualizzazione delle colonne di output corrispondenti quando si configurano i componenti a valle che utilizzano i dati di tale origine.</span><span class="sxs-lookup"><span data-stu-id="1da00-122">The selected columns appear in the order in which you will see their corresponding output columns when you configure downstream components that consume data from this source.</span></span>  
  
 <span data-ttu-id="1da00-123">Per modificare l'ordine delle colonne, nell'elenco **Colonne esterne disponibili** deselezionare le caselle di controllo per tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="1da00-123">To change the order of the columns, in the **Available External Columns** list, clear the check boxes for all columns.</span></span> <span data-ttu-id="1da00-124">Selezionare quindi le colonne nell'ordine in cui si desidera visualizzarle.</span><span class="sxs-lookup"><span data-stu-id="1da00-124">Then, select the columns in the order that you want them to appear.</span></span>  
  
 <span data-ttu-id="1da00-125">**Colonna di output**</span><span class="sxs-lookup"><span data-stu-id="1da00-125">**Output Column**</span></span>  
 <span data-ttu-id="1da00-126">Consente di specificare un nome univoco per ogni colonna di output.</span><span class="sxs-lookup"><span data-stu-id="1da00-126">Provide a unique name for each output column.</span></span> <span data-ttu-id="1da00-127">L'impostazione predefinita è il nome della colonna (di origine) esterna selezionata.</span><span class="sxs-lookup"><span data-stu-id="1da00-127">The default is the name of the selected external (source) column.</span></span> <span data-ttu-id="1da00-128">Tuttavia, è possibile immettere qualsiasi nome descrittivo univoco.</span><span class="sxs-lookup"><span data-stu-id="1da00-128">However, you can enter any unique, descriptive name.</span></span> [!INCLUDE[ssIS](../../includes/ssis-md.md)] <span data-ttu-id="1da00-129">verranno visualizzati i nomi di **Colonna di output** per le colonne quando si configurano i componenti a valle che utilizzano i dati di questa origine.</span><span class="sxs-lookup"><span data-stu-id="1da00-129">Designer will display the **Output Column** names for the columns when you configure downstream components that consume data from this source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1da00-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1da00-130">See Also</span></span>  
 <span data-ttu-id="1da00-131">[Editor origine SAP BW &#40;pagina Gestione connessione&#41;](sap-bw-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="1da00-131">[SAP BW Source Editor &#40;Connection Manager Page&#41;](sap-bw-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="1da00-132">[Editor origine SAP BW &#40;pagina Output degli errori&#41;](sap-bw-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="1da00-132">[SAP BW Source Editor &#40;Error Output Page&#41;](sap-bw-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="1da00-133">[Editor origine SAP BW &#40;pagina Avanzate&#41;](sap-bw-source-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="1da00-133">[SAP BW Source Editor &#40;Advanced Page&#41;](sap-bw-source-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="1da00-134">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="1da00-134">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  
