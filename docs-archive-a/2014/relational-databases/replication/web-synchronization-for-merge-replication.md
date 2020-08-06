---
title: Sincronizzazione Web per la replica di tipo merge | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication synchronization [SQL Server replication]
- Internet [SQL Server replication], synchronization
- synchronization [SQL Server replication], Web Synchronization
- Web publishing [SQL Server replication], synchronization
- Web synchronization, about
- Web synchronization
ms.assetid: 84785aba-b2c1-4821-9e9d-a363c73dcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ef7bf5a6f77d593a90508a0b69d02f8c0db04407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636682"
---
# <a name="web-synchronization-for-merge-replication"></a><span data-ttu-id="1607b-102">Sincronizzazione Web per la replica di tipo merge</span><span class="sxs-lookup"><span data-stu-id="1607b-102">Web Synchronization for Merge Replication</span></span>
  <span data-ttu-id="1607b-103">La sincronizzazione tramite il Web per la replica di tipo merge consente di replicare i dati utilizzando il protocollo HTTPS e si rivela utile negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="1607b-103">Web synchronization for merge replication lets you replicate data by using the HTTPS protocol, and is useful for the following scenarios:</span></span>

-   <span data-ttu-id="1607b-104">Sincronizzazione di dati da utenti mobili su Internet.</span><span class="sxs-lookup"><span data-stu-id="1607b-104">Synchronizing data from mobile users over the Internet.</span></span>

-   <span data-ttu-id="1607b-105">Sincronizzazione di dati tra database di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attraverso un firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="1607b-105">Synchronizing data between [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases across a corporate firewall.</span></span>

 <span data-ttu-id="1607b-106">Tale funzionalità può essere ad esempio utilizzata dai rappresentanti in trasferta,</span><span class="sxs-lookup"><span data-stu-id="1607b-106">For example, a traveling sales representative can use Web synchronization.</span></span> <span data-ttu-id="1607b-107">come nel caso dei rappresentanti della società [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)]in visita a diversi magazzini e fornitori nelle rispettive aree.</span><span class="sxs-lookup"><span data-stu-id="1607b-107">The company, [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], has sales representatives that travel to various stores and suppliers throughout their regions.</span></span> <span data-ttu-id="1607b-108">In occasione di viaggi di lunga durata essi alloggiano in alberghi e hanno bisogno di uno strumento di semplice utilizzo per caricare i dati delle vendite e scaricare eventuali aggiornamenti dei prodotti alla fine di ogni giornata.</span><span class="sxs-lookup"><span data-stu-id="1607b-108">On longer trips the representatives stay in hotels and need a convenient way to upload sales data and download any product updates at the end of each day.</span></span>

 <span data-ttu-id="1607b-109">Si supponga che il reparto IT di [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] abbia configurato ogni computer portatile con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e abilitato la replica di tipo merge per l'utilizzo della sincronizzazione tramite il Web.</span><span class="sxs-lookup"><span data-stu-id="1607b-109">The [!INCLUDE[ssSampleDBCoShort](../../includes/sssampledbcoshort-md.md)] IT department has configured each portable computer with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and has enabled merge replication to use Web synchronization.</span></span> <span data-ttu-id="1607b-110">L'agente di merge in ogni computer portatile dispone di un URL Internet che punta ai componenti di replica installati in un computer in cui è in esecuzione [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="1607b-110">The Merge Agent on each portable computer has an Internet URL that points to the replication components that are installed on a computer that is running [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS).</span></span> <span data-ttu-id="1607b-111">Questi componenti sincronizzano il Sottoscrittore con il server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="1607b-111">These components synchronize the Subscriber with the Publisher.</span></span> <span data-ttu-id="1607b-112">Ogni rappresentante potrà connettersi mediante qualsiasi connessione Internet disponibile senza utilizzare una connessione remota, nonché caricare e scaricare i dati appropriati.</span><span class="sxs-lookup"><span data-stu-id="1607b-112">Each representative can now connect through any available Internet connection without using a remote dial-up connection, and can upload and download the appropriate data.</span></span> <span data-ttu-id="1607b-113">Poiché la connessione Internet utilizza il protocollo SSL (Secure Sockets Layer), non è richiesta una rete privata virtuale (VPN).</span><span class="sxs-lookup"><span data-stu-id="1607b-113">The Internet connection uses Secure Sockets Layer (SSL); therefore, a virtual private network (VPN) is not required.</span></span>

 <span data-ttu-id="1607b-114">Per informazioni sulla configurazione dei componenti necessari per la sincronizzazione tramite il Web, vedere [Configurare la sincronizzazione Web](configure-web-synchronization.md), [Configurare IIS per la sincronizzazione Web](configure-iis-for-web-synchronization.md) e [Configurare IIS 7 per la sincronizzazione Web](configure-iis-7-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="1607b-114">For information about how to configure the components that are required for Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md), [Configure IIS for Web Synchronization](configure-iis-for-web-synchronization.md), and [Configure IIS 7 for Web Synchronization](configure-iis-7-for-web-synchronization.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="1607b-115">La sincronizzazione Web è progettata per sincronizzare i dati mediante computer portatili, dispositivi palmari e altri client</span><span class="sxs-lookup"><span data-stu-id="1607b-115">Web synchronization is designed for synchronizing data with portable computers, handheld devices, and other clients.</span></span> <span data-ttu-id="1607b-116">e non è adatta per le applicazioni caratterizzate da un elevato traffico tra server.</span><span class="sxs-lookup"><span data-stu-id="1607b-116">Web synchronization is not intended for high-volume server-to-server applications.</span></span>

## <a name="overview-of-how-web-synchronization-works"></a><span data-ttu-id="1607b-117">Panoramica del funzionamento della sincronizzazione Web</span><span class="sxs-lookup"><span data-stu-id="1607b-117">Overview of How Web Synchronization Works</span></span>
 <span data-ttu-id="1607b-118">Quando si utilizza la sincronizzazione tramite il Web, gli aggiornamenti nel Sottoscrittore vengono assemblati e inviati come messaggio XML al computer che esegue IIS mediante il protocollo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1607b-118">When Web synchronization is used, updates at the Subscriber are packaged and sent as an XML message to the computer that is running IIS by using the HTTPS protocol.</span></span> <span data-ttu-id="1607b-119">Il computer che esegue IIS invia quindi i comandi al server di pubblicazione in un formato binario, generalmente utilizzando il protocollo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="1607b-119">The computer that is running IIS then sends the commands to the Publisher in a binary format, typically by using TCP/IP.</span></span> <span data-ttu-id="1607b-120">Gli aggiornamenti del server di pubblicazione vengono inviati al computer che esegue IIS e quindi assemblati come messaggio XML per il recapito nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="1607b-120">Updates at the Publisher are sent to the computer that is running IIS and then packaged as an XML message for delivery to the Subscriber.</span></span>

 <span data-ttu-id="1607b-121">Nella figura seguente sono illustrati alcuni dei componenti coinvolti nel processo di sincronizzazione tramite il Web per la replica di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="1607b-121">The following illustration shows some of the components that are involved in Web synchronization for merge replication.</span></span>

 <span data-ttu-id="1607b-122">![Componenti e flusso di dati per la sincronizzazione Web](media/web-sync01.gif "Componenti e flusso di dati per la sincronizzazione Web")</span><span class="sxs-lookup"><span data-stu-id="1607b-122">![Web synchronization components and data flow](media/web-sync01.gif "Web synchronization components and data flow")</span></span>

 <span data-ttu-id="1607b-123">La sincronizzazione tramite il Web è disponibile solo per le sottoscrizioni pull e pertanto un agente di merge verrà sempre eseguito sul Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="1607b-123">Web synchronization is an option only for pull subscriptions; therefore, a Merge Agent will always run on the Subscriber.</span></span> <span data-ttu-id="1607b-124">Tale agente può essere l'agente di merge standard, il controllo ActiveX dell'agente di merge o un'applicazione che consente la sincronizzazione tramite gli oggetti RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="1607b-124">This Merge Agent can be the standard Merge Agent, the Merge Agent ActiveX control, or an application that provides synchronization through Replication Management Objects (RMO).</span></span> <span data-ttu-id="1607b-125">Per specificare il percorso del computer che esegue IIS, utilizzare il parametro **-InternetUrl** per l'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="1607b-125">To specify the location of the computer that is running IIS, use the **-InternetUrl** parameter for the Merge Agent.</span></span>

 <span data-ttu-id="1607b-126">Il listener per la replica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (replisapi.dll) viene configurato sul computer che esegue IIS ed è responsabile della gestione dei messaggi inviati al server dal server di pubblicazione e dai Sottoscrittori.</span><span class="sxs-lookup"><span data-stu-id="1607b-126">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener (Replisapi.dll) is configured on the computer that is running IIS and is responsible for handling messages that are sent to the server from the Publisher and Subscribers.</span></span> <span data-ttu-id="1607b-127">Ogni nodo nella topologia gestisce il flusso di dati XML mediante replrec.dll, ovvero Riconciliatore replica di tipo merge (Merge Replication Reconciler).</span><span class="sxs-lookup"><span data-stu-id="1607b-127">Each node in the topology handles the XML data stream by using the Merge Replication Reconciler (Replrec.dll).</span></span>

 <span data-ttu-id="1607b-128">Per tutti i computer che partecipano alla sincronizzazione tramite il Web è necessario[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1607b-128">[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] or a later version is required for all computers that participate in Web synchronization.</span></span>

### <a name="synchronization-process"></a><span data-ttu-id="1607b-129">Processo di sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="1607b-129">Synchronization Process</span></span>
 <span data-ttu-id="1607b-130">La sincronizzazione prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1607b-130">The following steps occur during synchronization:</span></span>

1.  <span data-ttu-id="1607b-131">L'agente di merge viene avviato nel Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="1607b-131">The Merge Agent is started at the Subscriber.</span></span> <span data-ttu-id="1607b-132">L'agente esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1607b-132">The agent does the following:</span></span>

    1.  <span data-ttu-id="1607b-133">Stabilisce una connessione SQL con il database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="1607b-133">Makes an SQL connection to the subscription database.</span></span>

    2.  <span data-ttu-id="1607b-134">Estrae tutte le modifiche dal database.</span><span class="sxs-lookup"><span data-stu-id="1607b-134">Extracts any changes from the database.</span></span>

    3.  <span data-ttu-id="1607b-135">Invia una richiesta HTTPS al computer che esegue IIS.</span><span class="sxs-lookup"><span data-stu-id="1607b-135">Makes an HTTPS request to the computer that is running IIS.</span></span>

    4.  <span data-ttu-id="1607b-136">Carica le modifiche ai dati come messaggio XML.</span><span class="sxs-lookup"><span data-stu-id="1607b-136">Uploads data changes as an XML message.</span></span>

2.  <span data-ttu-id="1607b-137">I componenti Listener per la replica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e Riconciliatore replica di tipo merge (Merge Replication Reconciler) ospitati nel computer con IIS eseguono le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1607b-137">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener and Merge Replication Reconciler that are hosted on the computer that is running IIS do the following:</span></span>

    1.  <span data-ttu-id="1607b-138">Rispondono alla richiesta HTTPS.</span><span class="sxs-lookup"><span data-stu-id="1607b-138">Respond to the HTTPS request.</span></span>

    2.  <span data-ttu-id="1607b-139">Stabiliscono una connessione SQL con il database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="1607b-139">Make an SQL connection to the publication database.</span></span>

    3.  <span data-ttu-id="1607b-140">Applicano le modifiche caricate al database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="1607b-140">Apply the upload changes to the publication database.</span></span>

    4.  <span data-ttu-id="1607b-141">Estraggono le modifiche scaricate per il Sottoscrittore.</span><span class="sxs-lookup"><span data-stu-id="1607b-141">Extract the download changes for the Subscriber.</span></span>

    5.  <span data-ttu-id="1607b-142">Inviano una risposta HTTPS all'agente di merge.</span><span class="sxs-lookup"><span data-stu-id="1607b-142">Send an HTTPS response back to the Merge Agent.</span></span>

3.  <span data-ttu-id="1607b-143">L'agente di merge nel Sottoscrittore accetta la risposta HTTPS e applica nel database di sottoscrizione le modifiche scaricate.</span><span class="sxs-lookup"><span data-stu-id="1607b-143">The Merge Agent at the Subscriber then accepts the HTTPS response and applies the download changes to the subscription database.</span></span>

## <a name="see-also"></a><span data-ttu-id="1607b-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1607b-144">See Also</span></span>
 <span data-ttu-id="1607b-145">[Configurare](configure-web-synchronization.md) [topologie di sincronizzazione Web per la sincronizzazione Web](topologies-for-web-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="1607b-145">[Configure Web Synchronization](configure-web-synchronization.md) [Topologies for Web Synchronization](topologies-for-web-synchronization.md)</span></span>


