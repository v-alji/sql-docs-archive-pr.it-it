---
title: Editor gestione connessione SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ec970319-e749-4753-8675-9cf76ed99669
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 527af979fc9c92062f24e1fe161b93e88ed4ab4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714511"
---
# <a name="sap-bw-connection-manager-editor"></a><span data-ttu-id="cfbec-102">Editor gestione connessione SAP BW</span><span class="sxs-lookup"><span data-stu-id="cfbec-102">SAP BW Connection Manager Editor</span></span>
  <span data-ttu-id="cfbec-103">Utilizzare l' **Editor gestione connessione SAP BW** per specificare le proprietà per la connessione a un sistema SAP Netweaver BW versione 7.</span><span class="sxs-lookup"><span data-stu-id="cfbec-103">Use the **SAP BW Connection Manager Editor** to specify the properties to use to connect to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="cfbec-104">La gestione connessione SAP BW offre connettività a un sistema SAP Netweaver BW 7 per l'utilizzo da parte dell'origine o della destinazione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cfbec-104">The SAP BW connection manager provides connectivity to an SAP Netweaver BW 7 system for use by the SAP BW source or destination.</span></span> <span data-ttu-id="cfbec-105">Per sapere di più sulla gestione connessione SAP BW di [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 per SAP BW, vedere [Gestione connessione SAP BW](connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cfbec-105">To learn more about the SAP BW connection manager of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Connection Manager](connection-manager/sap-bw-connection-manager.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cfbec-106">La documentazione per Microsoft Connector 1.1 for SAP BW presuppone la conoscenza dell'ambiente SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="cfbec-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="cfbec-107">Per ulteriori informazioni su SAP Netweaver BW o per informazioni su come configurare oggetti e processi di SAP Netweaver BW, vedere la documentazione SAP.</span><span class="sxs-lookup"><span data-stu-id="cfbec-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="cfbec-108">**Per aprire l'editor gestione connessione SAP BW**</span><span class="sxs-lookup"><span data-stu-id="cfbec-108">**To open the SAP BW Connection Manager Editor**</span></span>  
  
1.  <span data-ttu-id="cfbec-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene la gestione connessione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cfbec-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that contains the SAP BW connection manager.</span></span>  
  
2.  <span data-ttu-id="cfbec-110">Nella scheda **Flusso di controllo** dell'area Gestioni connessioni, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cfbec-110">In the Connection Managers area on the **Control Flow** tab, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="cfbec-111">Fare doppio clic sulla gestione connessione SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cfbec-111">Double-click the SAP BW connection manager.</span></span>  
  
         <span data-ttu-id="cfbec-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="cfbec-112">-or-</span></span>  
  
    -   <span data-ttu-id="cfbec-113">Fare clic con il tasto destro del mouse sulla gestione connessione SAP BW, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="cfbec-113">Right-click the SAP BW connection manager, and then select **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="cfbec-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cfbec-114">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfbec-115">Se non si conoscono tutti i valori richiesti per configurare la gestione connessione, può essere necessario consultare l'amministratore SAP.</span><span class="sxs-lookup"><span data-stu-id="cfbec-115">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="cfbec-116">**Client**</span><span class="sxs-lookup"><span data-stu-id="cfbec-116">**Client**</span></span>  
 <span data-ttu-id="cfbec-117">Specificare il numero client del sistema.</span><span class="sxs-lookup"><span data-stu-id="cfbec-117">Specify the client number of the system.</span></span>  
  
 <span data-ttu-id="cfbec-118">**Lingua**</span><span class="sxs-lookup"><span data-stu-id="cfbec-118">**Language**</span></span>  
 <span data-ttu-id="cfbec-119">Specificare la lingua utilizzata dal sistema.</span><span class="sxs-lookup"><span data-stu-id="cfbec-119">Specify the language that the system uses.</span></span> <span data-ttu-id="cfbec-120">Ad esempio, specificare **IT** per l'italiano.</span><span class="sxs-lookup"><span data-stu-id="cfbec-120">For example, specify **EN** for English.</span></span>  
  
 <span data-ttu-id="cfbec-121">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="cfbec-121">**User name**</span></span>  
 <span data-ttu-id="cfbec-122">Specificare il nome utente che verrà utilizzato per connettersi al sistema.</span><span class="sxs-lookup"><span data-stu-id="cfbec-122">Specify the user name that will be used to connect to the system.</span></span>  
  
 <span data-ttu-id="cfbec-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="cfbec-123">**Password**</span></span>  
 <span data-ttu-id="cfbec-124">Specificare la password che verrà utilizzata con il nome utente.</span><span class="sxs-lookup"><span data-stu-id="cfbec-124">Specify the password that will be used with the user name.</span></span>  
  
 <span data-ttu-id="cfbec-125">**Usa server applicazioni singolo**</span><span class="sxs-lookup"><span data-stu-id="cfbec-125">**Use single application server**</span></span>  
 <span data-ttu-id="cfbec-126">Connettersi a un server applicazioni singolo.</span><span class="sxs-lookup"><span data-stu-id="cfbec-126">Connect to a single application server.</span></span>  
  
 <span data-ttu-id="cfbec-127">Per connettersi a un gruppo di server con carico bilanciato, usare in alternativa l'opzione **Usa bilanciamento del carico** .</span><span class="sxs-lookup"><span data-stu-id="cfbec-127">To connect to a group of load-balanced servers, use the **Use load balancing** option instead.</span></span>  
  
 <span data-ttu-id="cfbec-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="cfbec-128">**Host**</span></span>  
 <span data-ttu-id="cfbec-129">In caso di connessione a un server applicazioni singolo, specificare il nome host.</span><span class="sxs-lookup"><span data-stu-id="cfbec-129">If connecting to a single application server, specify the host name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfbec-130">Questa opzione è disponibile solo se è stata selezionata l'opzione **Usa server applicazioni singolo** .</span><span class="sxs-lookup"><span data-stu-id="cfbec-130">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="cfbec-131">**Numero di sistema**</span><span class="sxs-lookup"><span data-stu-id="cfbec-131">**System number**</span></span>  
 <span data-ttu-id="cfbec-132">In caso di connessione a un server applicazioni singolo, specificare il numero del sistema.</span><span class="sxs-lookup"><span data-stu-id="cfbec-132">If connecting to a single application server, specify the system number.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfbec-133">Questa opzione è disponibile solo se è stata selezionata l'opzione **Usa server applicazioni singolo** .</span><span class="sxs-lookup"><span data-stu-id="cfbec-133">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="cfbec-134">**Usa bilanciamento del carico**</span><span class="sxs-lookup"><span data-stu-id="cfbec-134">**Use load balancing**</span></span>  
 <span data-ttu-id="cfbec-135">Connettersi a un gruppo di server con carico bilanciato.</span><span class="sxs-lookup"><span data-stu-id="cfbec-135">Connect to a group of load-balanced servers.</span></span>  
  
 <span data-ttu-id="cfbec-136">Per connettersi a un server applicazioni singolo, usare in alternativa l'opzione **Usa server applicazioni singolo** .</span><span class="sxs-lookup"><span data-stu-id="cfbec-136">To connect to a single application server, use the **Use single application server** option instead.</span></span>  
  
 <span data-ttu-id="cfbec-137">**Server messaggi**</span><span class="sxs-lookup"><span data-stu-id="cfbec-137">**Message server**</span></span>  
 <span data-ttu-id="cfbec-138">In caso di connessione a un gruppo di server con carico bilanciato, specificare il nome del server messaggi.</span><span class="sxs-lookup"><span data-stu-id="cfbec-138">If connecting to a group of load-balanced servers, specify the name of the message server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfbec-139">Questa opzione è disponibile solo se è stata selezionata l'opzione **Usa bilanciamento del carico** .</span><span class="sxs-lookup"><span data-stu-id="cfbec-139">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="cfbec-140">**Gruppo**</span><span class="sxs-lookup"><span data-stu-id="cfbec-140">**Group**</span></span>  
 <span data-ttu-id="cfbec-141">In caso di connessione a un gruppo di server con carico bilanciato, specificare il nome del gruppo di server.</span><span class="sxs-lookup"><span data-stu-id="cfbec-141">If connecting to a group of load-balanced servers, specify the name of the server group name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfbec-142">Questa opzione è disponibile solo se è stata selezionata l'opzione **Usa bilanciamento del carico** .</span><span class="sxs-lookup"><span data-stu-id="cfbec-142">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="cfbec-143">**SID**</span><span class="sxs-lookup"><span data-stu-id="cfbec-143">**SID**</span></span>  
 <span data-ttu-id="cfbec-144">In caso di connessione a un gruppo di server con carico bilanciato, specificare l'ID sistema per la connessione.</span><span class="sxs-lookup"><span data-stu-id="cfbec-144">If connecting to a group of load-balanced servers, specify the System ID for the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cfbec-145">Questa opzione è disponibile solo se è stata selezionata l'opzione **Usa bilanciamento del carico** .</span><span class="sxs-lookup"><span data-stu-id="cfbec-145">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="cfbec-146">**Directory log**</span><span class="sxs-lookup"><span data-stu-id="cfbec-146">**Log directory**</span></span>  
 <span data-ttu-id="cfbec-147">Abilitare la registrazione per i componenti di [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 per SAP BW.</span><span class="sxs-lookup"><span data-stu-id="cfbec-147">Enable logging for the components of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 <span data-ttu-id="cfbec-148">Per abilitare la registrazione, specificare una directory per i file di log creati prima e dopo ogni chiamata di funzione RFC.</span><span class="sxs-lookup"><span data-stu-id="cfbec-148">To enable logging, specify a directory for the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="cfbec-149">Questa funzionalità di registrazione crea molti file di log in formato XML.</span><span class="sxs-lookup"><span data-stu-id="cfbec-149">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="cfbec-150">Poiché questi file di log contengono anche tutte le righe di dati trasferiti, è possibile che occupino una grande quantità di spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="cfbec-150">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="cfbec-151">Se i dati trasferiti contengono informazioni riservate, anche i file di log conterranno tali informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="cfbec-151">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
 <span data-ttu-id="cfbec-152">Per specificare la directory di log, è possibile immettere il percorso della directory manualmente oppure fare clic su **Sfoglia** e passare alla directory di log.</span><span class="sxs-lookup"><span data-stu-id="cfbec-152">To specify the log directory, you can either enter the directory path manually, or click **Browse** and browse to the log directory.</span></span>  
  
 <span data-ttu-id="cfbec-153">Se non si seleziona una directory di log, la registrazione non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="cfbec-153">If you do not select a log directory, logging is not enabled.</span></span>  
  
 <span data-ttu-id="cfbec-154">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="cfbec-154">**Browse**</span></span>  
 <span data-ttu-id="cfbec-155">Sfogliare per selezionare una cartella per la directory di log.</span><span class="sxs-lookup"><span data-stu-id="cfbec-155">Browse to select a folder for the log directory.</span></span>  
  
 <span data-ttu-id="cfbec-156">**Test connessione**</span><span class="sxs-lookup"><span data-stu-id="cfbec-156">**Test Connection**</span></span>  
 <span data-ttu-id="cfbec-157">Verificare la connessione utilizzando i valori forniti.</span><span class="sxs-lookup"><span data-stu-id="cfbec-157">Test the connection using the values that you have provided.</span></span> <span data-ttu-id="cfbec-158">Dopo avere fatto clic su **Test connessione**viene visualizzata una finestra di messaggio che indica se la connessione ha avuto esito positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="cfbec-158">After clicking **Test Connection**, a message box appears and indicates whether the connection succeeded or failed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfbec-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfbec-159">See Also</span></span>  
 [<span data-ttu-id="cfbec-160">Guida (F1) di Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="cfbec-160">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
  
  
