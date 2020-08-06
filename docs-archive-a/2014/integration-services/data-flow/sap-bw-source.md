---
title: Origine SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 749afb64-3567-4dc9-8431-783d650c25db
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d64af5e0d881e3b7dbbd2cc4e005aa3dbef3c43a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636328"
---
# <a name="sap-bw-source"></a><span data-ttu-id="2f1c2-102">Origine SAP BW</span><span class="sxs-lookup"><span data-stu-id="2f1c2-102">SAP BW Source</span></span>
  <span data-ttu-id="2f1c2-103">L'origine SAP BW è il componente di origine di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-103">The SAP BW source is the source component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="2f1c2-104">Pertanto, l'origine SAP BW estrae i dati da un sistema SAP Netweaver BW versione 7 e li rende disponibili al flusso di dati in un pacchetto di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f1c2-104">Thus, the SAP BW source extracts data from an SAP Netweaver BW version 7 system and makes this data available to the data flow in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
 <span data-ttu-id="2f1c2-105">Questa origine include un output e un output degli errori.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-105">This source has one output and one error output.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f1c2-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="2f1c2-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2f1c2-108">L'estrazione di dati da SAP Netweaver BW richiede licenze SAP aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-108">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="2f1c2-109">Contattare SAP per verificare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-109">Check with SAP to verify these requirements.</span></span>  
  
 <span data-ttu-id="2f1c2-110">Per utilizzare l'origine SAP BW, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-110">To use the SAP BW source, you have to do the following tasks:</span></span>  
  
-   [<span data-ttu-id="2f1c2-111">Preparare gli oggetti SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="2f1c2-111">Prepare the SAP Netweaver BW objects</span></span>](#bkmk_Prepare_Objects)  
  
-   [<span data-ttu-id="2f1c2-112">Connettersi al sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="2f1c2-112">Connect to the SAP Netweaver BW system</span></span>](#bkmk_Connect_Database)  
  
-   [<span data-ttu-id="2f1c2-113">Configurare l'origine SAP BW</span><span class="sxs-lookup"><span data-stu-id="2f1c2-113">Configure the SAP BW source</span></span>](#bkmk_Configure_Source)  
  
##  <a name="preparing-the-sap-netweaver-bw-objects-that-the-source-requires"></a><a name="bkmk_Prepare_Objects"></a> <span data-ttu-id="2f1c2-114">Preparazione degli oggetti SAP Netweaver BW richiesti dall'origine</span><span class="sxs-lookup"><span data-stu-id="2f1c2-114">Preparing the SAP Netweaver BW Objects That the Source Requires</span></span>  
 <span data-ttu-id="2f1c2-115">L'origine SAP BW richiede la presenza di determinati oggetti nel sistema SAP Netweaver BW per funzionare.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-115">The SAP BW source requires that certain objects are in the SAP Netweaver BW system before the source can function.</span></span> <span data-ttu-id="2f1c2-116">Se questi oggetti non esistono ancora, è necessario eseguire questi passaggi per crearli e configurarli nel sistema SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-116">If these objects do not already exist, you have to follow these steps to create and configure these objects in the SAP Netweaver BW system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f1c2-117">Per ulteriori dettagli sugli oggetti e sui passaggi di configurazione, vedere la documentazione di SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-117">For additional details about these objects and these configuration steps, see the SAP Netweaver BW documentation.</span></span>  
  
1.  <span data-ttu-id="2f1c2-118">Accedere al sistema SAP Netweaver BW tramite la GUI SAP, immettere il codice di transazione SM59 e creare una destinazione RFC:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-118">Log on to SAP Netweaver BW through the SAP GUI, enter transaction code SM59, and create an RFC destination:</span></span>  
  
    1.  <span data-ttu-id="2f1c2-119">In **Tipo di connessione**selezionare **TCP/IP**.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-119">For **Connection Type**, select **TCP/IP**.</span></span>  
  
    2.  <span data-ttu-id="2f1c2-120">In **Tipo di attivazione**selezionare **Programma server registrato**.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-120">For **Activation Type**, select **Registered Server Program**.</span></span>  
  
    3.  <span data-ttu-id="2f1c2-121">In **Communication Type with Target System**(Tipo di comunicazione con sistema di destinazione) selezionare **Non-Unicode (Inactive MDMP Settings)** (Non Unicode (Impostazioni MDMP inattive)).</span><span class="sxs-lookup"><span data-stu-id="2f1c2-121">For **Communication Type with Target System**, select **Non-Unicode (Inactive MDMP Settings)**.</span></span>  
  
    4.  <span data-ttu-id="2f1c2-122">Assegnare un ID programma appropriato.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-122">Assign an appropriate Program ID.</span></span>  
  
2.  <span data-ttu-id="2f1c2-123">Creare una destinazione di hub aperto:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-123">Create an Open Hub Destination:</span></span>  
  
    1.  <span data-ttu-id="2f1c2-124">Passare alla workbench dell'amministratore (codice di transazione RSA1) e, nel riquadro sinistro, selezionare **Open Hub Destination**(Destinazione hub aperto).</span><span class="sxs-lookup"><span data-stu-id="2f1c2-124">Go to the Administrator Workbench (transaction code RSA1) and, in the left pane, select **Open Hub Destination**.</span></span>  
  
    2.  <span data-ttu-id="2f1c2-125">Nel riquadro centrale fare clic con il pulsante destro del mouse su un'InfoArea, quindi selezionare **"Create Open Hub Destination"** (Crea destinazione di hub aperto).</span><span class="sxs-lookup"><span data-stu-id="2f1c2-125">In the middle pane, right-click an InfoArea, and then select **"Create Open Hub Destination"**.</span></span>  
  
    3.  <span data-ttu-id="2f1c2-126">Per **Tipo destinazione**selezionare **"Strumento di terze parti"** , quindi immettere la destinazione RFC creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-126">For **Destination Type**, select **"Third Party Tool"**, and then enter the previously created RFC Destination.</span></span>  
  
    4.  <span data-ttu-id="2f1c2-127">Salvare e attivare la nuova destinazione di hub aperto.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-127">Save and activate the new Open Hub Destination.</span></span>  
  
3.  <span data-ttu-id="2f1c2-128">Creare un processo di trasferimento dati (DTP):</span><span class="sxs-lookup"><span data-stu-id="2f1c2-128">Create a Data Transfer Process (DTP):</span></span>  
  
    1.  <span data-ttu-id="2f1c2-129">Nel riquadro centrale dell'InfoArea, fare clic con il pulsante destro del mouse sulla destinazione creata in precedenza, quindi selezionare **"Create data transfer process"** (Crea processo di trasferimento dati).</span><span class="sxs-lookup"><span data-stu-id="2f1c2-129">In the middle pane of the InfoArea, right-click the previously created destination, and then select **"Create data transfer process"**.</span></span>  
  
    2.  <span data-ttu-id="2f1c2-130">Configurare, salvare e attivare il DTP.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-130">Configure, save, and activate the DTP.</span></span>  
  
    3.  <span data-ttu-id="2f1c2-131">Nel menu fare clic su **Vai a**, quindi fare clic su **Impostazioni per gestioni batch**.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-131">On the menu, click **Goto**, and then click **Settings for Batch Manager**.</span></span>  
  
    4.  <span data-ttu-id="2f1c2-132">Aggiornare **Numero di processi** su 1 per l'elaborazione seriale.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-132">Update **Number of processes** to 1 for serial processing.</span></span>  
  
4.  <span data-ttu-id="2f1c2-133">Creare una catena di processi:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-133">Create a process chain:</span></span>  
  
    1.  <span data-ttu-id="2f1c2-134">Quando si configura la catena di processi, selezionare **Avvia utilizzando catena di metadati o API** per **Opzioni di pianificazione** di **Processo di avvio**, quindi aggiungere il DTP creato in precedenza come nodo successivo.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-134">When configuring the process chain, select the **Start Using Metadata Chain or API** as the **Scheduling Options** of the **Start Process**, and then add the previously created DTP as the subsequent node.</span></span>  
  
    2.  <span data-ttu-id="2f1c2-135">Salvare e attivare la catena di processi.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-135">Save and activate the process chain.</span></span>  
  
     <span data-ttu-id="2f1c2-136">L'origine SAP BW può chiamare la catena di processi per attivare il processo di trasferimento dati.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-136">The SAP BW source can call the process chain to activate the data transfer process.</span></span>  
  
##  <a name="connecting-to-the-sap-netweaver-bw-system"></a><a name="bkmk_Connect_Database"></a> <span data-ttu-id="2f1c2-137">Connessione al sistema SAP Netweaver BW</span><span class="sxs-lookup"><span data-stu-id="2f1c2-137">Connecting to the SAP Netweaver BW System</span></span>  
 <span data-ttu-id="2f1c2-138">Per connettersi al sistema SAP Netweaver BW versione 7, l'origine SAP BW utilizza la gestione connessione SAP BW che fa parte di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-138">To connect to the SAP Netweaver BW version 7 system, the SAP BW source uses the SAP BW connection manager that is part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package.</span></span> <span data-ttu-id="2f1c2-139">La gestione connessione SAP BW è l'unica gestione connessione di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che può essere utilizzata dall'origine SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-139">The SAP BW connection manager is the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] connection manager that the SAP BW source can use.</span></span>  
  
 <span data-ttu-id="2f1c2-140">Per ulteriori informazioni sulla gestione connessione SAP BW, vedere [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2f1c2-140">For more information about the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
##  <a name="configuring-the-sap-bw-source"></a><a name="bkmk_Configure_Source"></a> <span data-ttu-id="2f1c2-141">Configurazione dell'origine SAP BW</span><span class="sxs-lookup"><span data-stu-id="2f1c2-141">Configuring the SAP BW Source</span></span>  
 <span data-ttu-id="2f1c2-142">Per configurare l'origine SAP BW, procedere nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-142">You can configure the SAP BW source in the following ways:</span></span>  
  
-   <span data-ttu-id="2f1c2-143">Cercare e selezionare la destinazione OHS (Open Hub Service) da utilizzare per estrarre i dati.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-143">Look up and select the Open Hub Service (OHS) destination to use to extract data.</span></span>  
  
-   <span data-ttu-id="2f1c2-144">Selezionare uno dei metodi seguenti per estrarre i dati:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-144">Select one of the following methods for extracting data:</span></span>  
  
    -   <span data-ttu-id="2f1c2-145">Attivare una catena di processi.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-145">Trigger a process chain.</span></span> <span data-ttu-id="2f1c2-146">In questo caso, il pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] avvia il processo di estrazione.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-146">In this case, the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="2f1c2-147">Attendere la notifica dal sistema SAP Netweaver BW per iniziare un'estrazione.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-147">Wait for notification from the SAP Netweaver BW system to begin an extraction.</span></span> <span data-ttu-id="2f1c2-148">In questo caso, il sistema SAP Netweaver BW avvia il processo di estrazione.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-148">In this case, the SAP Netweaver BW system starts the extraction process.</span></span>  
  
    -   <span data-ttu-id="2f1c2-149">Recuperare i dati associati a un ID richiesta specifico.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-149">Retrieve the data that is associated with a particular Request ID.</span></span> <span data-ttu-id="2f1c2-150">In questo caso, il sistema SAP Netweaver BW ha già estratto i dati in una tabella interna e il pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] legge solo i dati.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-150">In this case, the SAP Netweaver BW system has already extracted the data to an internal table, and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package just reads the data.</span></span>  
  
-   <span data-ttu-id="2f1c2-151">A seconda del metodo selezionato per estrarre dati, fornire le informazioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-151">Depending on the method selected for extracting data, provide the following additional information:</span></span>  
  
    -   <span data-ttu-id="2f1c2-152">Per l'opzione **P - Attivazione catena processi** , fornire il nome host del gateway, il nome del servizio gateway, l'ID programma per la destinazione RFC e il nome della catena di processi.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-152">For the **P - Trigger Process Chain** option, provide the gateway host name, gateway service name, program ID for the RFC destination, and name of the process chain.</span></span>  
  
    -   <span data-ttu-id="2f1c2-153">Per l'opzione **W - Attesa notifica** , fornire il nome host del gateway, il nome del server gateway e l'ID programma per la destinazione RFC.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-153">For the **W - Wait for Notify** option, provide the gateway host name, the gateway server name, and the program ID for the RFC destination.</span></span> <span data-ttu-id="2f1c2-154">È inoltre possibile specificare il timeout (in secondi).</span><span class="sxs-lookup"><span data-stu-id="2f1c2-154">You can also specify the timeout (in seconds).</span></span> <span data-ttu-id="2f1c2-155">Il timeout è il periodo di tempo massimo di attesa della notifica da parte dell'origine.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-155">The timeout is the maximum period of time that the source will wait to be notified.</span></span>  
  
    -   <span data-ttu-id="2f1c2-156">Per l'opzione **E - Solo estrazione** , fornire l'ID richiesta.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-156">For the **E - Extract Only** option, provide the Request ID.</span></span>  
  
-   <span data-ttu-id="2f1c2-157">Specificare le regole per la conversione di stringhe.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-157">Specify rules for string conversion.</span></span> <span data-ttu-id="2f1c2-158">Convertire, ad esempio, tutte le stringhe a seconda che il sistema SAP Netweaver BW sia Unicode oppure no; in alternativa, convertire tutte le stringhe in `varchar` o `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-158">(For example, convert all strings depending on whether the SAP Netweaver BW system is Unicode or not, or convert all strings to `varchar` or `nvarchar`).</span></span>  
  
-   <span data-ttu-id="2f1c2-159">Utilizzare le opzioni selezionate per visualizzare in anteprima i dati da estrarre.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-159">Use the options that you have selected to preview the data to be extracted.</span></span>  
  
 <span data-ttu-id="2f1c2-160">È inoltre possibile abilitare la registrazione delle chiamate di funzioni RFC da parte dell'origine.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-160">You can also enable logging of RFC function calls by the source.</span></span> <span data-ttu-id="2f1c2-161">Tale registrazione è separata dalla registrazione facoltativa che è possibile abilitare nei pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] . Abilitare la registrazione delle chiamate di funzioni RFC quando si configura la gestione connessione SAP BW che verrà utilizzata dall'origine.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-161">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) You enable logging of RFC function calls when you configure the SAP BW connection manager that the source will use.</span></span> <span data-ttu-id="2f1c2-162">Per ulteriori informazioni sulla configurazione della gestione connessione SAP BW, vedere [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="2f1c2-162">For more information about how to configure the SAP BW connection manager, see [SAP BW Connection Manager](../connection-manager/sap-bw-connection-manager.md).</span></span>  
  
 <span data-ttu-id="2f1c2-163">Se non si conoscono tutti i valori richiesti per configurare l'origine, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-163">If you do not know all the values that are required to configure the source, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="2f1c2-164">Per una procedura dettagliata che illustra come configurare e utilizzare la gestione connessione, l'origine e la destinazione SAP BW, vedere il white paper [Utilizzo dei servizi di integrazione SQL Server 2008 con SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="2f1c2-164">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="2f1c2-165">Nel white paper viene anche indicato come configurare gli oggetti necessari in SAP BW.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-165">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="2f1c2-166">Utilizzo di Progettazione SSIS per configurare l'origine</span><span class="sxs-lookup"><span data-stu-id="2f1c2-166">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="2f1c2-167">Per ulteriori informazioni sulle proprietà dell'origine SAP BW che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-167">For more information about the properties of the SAP BW source that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2f1c2-168">Editor origine SAP BW &#40;pagina Gestione connessione&#41;</span><span class="sxs-lookup"><span data-stu-id="2f1c2-168">SAP BW Source Editor &#40;Connection Manager Page&#41;</span></span>](sap-bw-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="2f1c2-169">Editor origine SAP BW &#40;pagina Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="2f1c2-169">SAP BW Source Editor &#40;Columns Page&#41;</span></span>](sap-bw-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="2f1c2-170">Editor origine SAP BW &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="2f1c2-170">SAP BW Source Editor &#40;Error Output Page&#41;</span></span>](sap-bw-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="2f1c2-171">Editor origine SAP BW &#40;pagina Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="2f1c2-171">SAP BW Source Editor &#40;Advanced Page&#41;</span></span>](sap-bw-source-editor-advanced-page.md)  
  
 <span data-ttu-id="2f1c2-172">Quando si configura l'origine SAP BW, è inoltre possibile utilizzare varie finestre di dialogo per cercare gli oggetti SAP Netweaver BW o visualizzare in anteprima i dati di origine.</span><span class="sxs-lookup"><span data-stu-id="2f1c2-172">While you are configuring the SAP BW source, you can also use various dialog boxes to look up SAP Netweaver BW objects or to preview the source data.</span></span> <span data-ttu-id="2f1c2-173">Per ulteriori informazioni su queste finestre di dialogo, fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f1c2-173">For more information about these dialog boxes, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2f1c2-174">Cerca destinazione RFC</span><span class="sxs-lookup"><span data-stu-id="2f1c2-174">Look Up RFC Destination</span></span>](look-up-rfc-destination.md)  
  
-   [<span data-ttu-id="2f1c2-175">Cerca ProcessChain</span><span class="sxs-lookup"><span data-stu-id="2f1c2-175">Look Up Process Chain</span></span>](look-up-process-chain.md)  
  
-   [<span data-ttu-id="2f1c2-176">Log richieste</span><span class="sxs-lookup"><span data-stu-id="2f1c2-176">Request Log</span></span>](request-log.md)  
  
-   [<span data-ttu-id="2f1c2-177">Anteprima</span><span class="sxs-lookup"><span data-stu-id="2f1c2-177">Preview</span></span>](preview.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f1c2-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f1c2-178">See Also</span></span>  
 [<span data-ttu-id="2f1c2-179">Componenti di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="2f1c2-179">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
