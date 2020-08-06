---
title: "Procedura: esecuzione dell'analisi guidata di preparazione aggiornamento | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Analysis Wizard
ms.assetid: d7d2a1e2-1179-4c05-9b0f-555b04dd1199
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7c3e5e8a52c3b166b076aedb122e68f860037edf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637053"
---
# <a name="how-to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="d87a4-102">Procedura: Esecuzione dell'Analisi guidata di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d87a4-102">How to: Run the Upgrade Advisor Analysis Wizard</span></span>
  <span data-ttu-id="d87a4-103">È possibile avviare l'Analisi guidata di Preparazione aggiornamento dalla pagina iniziale di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d87a4-103">You start the Upgrade Advisor Analysis Wizard from the Upgrade Advisor start page.</span></span> <span data-ttu-id="d87a4-104">In questo argomento viene descritto come eseguire l'Analisi guidata di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d87a4-104">This topic describes how to run the Upgrade Advisor Analysis Wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d87a4-105">Quando si esegue l'Analisi guidata di Preparazione aggiornamento, i report vengono salvati nella cartella di report predefinita.</span><span class="sxs-lookup"><span data-stu-id="d87a4-105">When you run the Upgrade Advisor Analysis Wizard, Upgrade Advisor saves the reports in the default report folder.</span></span> <span data-ttu-id="d87a4-106">Tuttavia, nel visualizzatore di report vengono visualizzati solo gli ultimi cinque report salvati.</span><span class="sxs-lookup"><span data-stu-id="d87a4-106">However, the report viewer displays only the five latest saved reports.</span></span> <span data-ttu-id="d87a4-107">Il percorso predefinito per i report è My Documents \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] upgrade Advisor\110\Reports.</span><span class="sxs-lookup"><span data-stu-id="d87a4-107">The default location for the reports is My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports.</span></span>  
  
### <a name="to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="d87a4-108">Per eseguire l'Analisi guidata di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d87a4-108">To run the Upgrade Advisor Analysis Wizard</span></span>  
  
1.  <span data-ttu-id="d87a4-109">Nella pagina iniziale di preparazione aggiornamento fare clic su **Avvia l'analisi guidata di preparazione aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="d87a4-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Analysis Wizard**.</span></span>  
  
2.  <span data-ttu-id="d87a4-110">Nella pagina \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] componenti\*\* immettere il nome del server da analizzare nella casella **nome server** , quindi fare clic su **rileva**.</span><span class="sxs-lookup"><span data-stu-id="d87a4-110">On the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components** page, enter the name of the server to scan in the **Server name** box, and then click **Detect**.</span></span> <span data-ttu-id="d87a4-111">Utilizzare le linee guida seguenti per il nome del server:</span><span class="sxs-lookup"><span data-stu-id="d87a4-111">Use the following guidelines for the server name:</span></span>  
  
    -   <span data-ttu-id="d87a4-112">Per analizzare le istanze non cluster, immettere il nome del computer.</span><span class="sxs-lookup"><span data-stu-id="d87a4-112">To scan nonclustered instances, enter the computer name.</span></span>  
  
    -   <span data-ttu-id="d87a4-113">Per analizzare istanze cluster, immettere il nome [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtuale.</span><span class="sxs-lookup"><span data-stu-id="d87a4-113">To scan clustered instances, enter the virtual [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name.</span></span>  
  
    -   <span data-ttu-id="d87a4-114">Per analizzare i componenti non cluster installati in un nodo di un cluster, immettere il nome del nodo.</span><span class="sxs-lookup"><span data-stu-id="d87a4-114">To scan nonclustered components that are installed on a node of a cluster, enter the node name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="d87a4-115">Preparazione aggiornamento non supporta la connessione a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che non sia impostata per utilizzare la porta standard (1433) per le connessioni client.</span><span class="sxs-lookup"><span data-stu-id="d87a4-115">Upgrade Advisor does not support connecting to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is not set to use the standard port (1433) for client connections.</span></span> <span data-ttu-id="d87a4-116">Se si desidera connettersi a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che non utilizza la porta standard (1433), creare un alias utilizzando l'indirizzo IP e la porta.</span><span class="sxs-lookup"><span data-stu-id="d87a4-116">If you want to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that does not use the standard port (1433), create an alias using the IP address and the port.</span></span> <span data-ttu-id="d87a4-117">Per ulteriori informazioni sulla configurazione dei protocolli client e sulla creazione di un alias per le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanze, vedere [configure client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="d87a4-117">For more information about configuring client protocols and creating an alias for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
    >   
    >  <span data-ttu-id="d87a4-118">Se non è [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installato nel computer in cui si esegue Preparazione aggiornamento, fare clic su **Start**, quindi eseguire `cliconfg` .</span><span class="sxs-lookup"><span data-stu-id="d87a4-118">If you do not have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer on which you are running Upgrade Advisor, click **Start**, and then run  `cliconfg`.</span></span> <span data-ttu-id="d87a4-119">Verrà visualizzata la finestra di dialogo \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilità di rete client\*\* .</span><span class="sxs-lookup"><span data-stu-id="d87a4-119">This opens the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility** dialog box.</span></span> <span data-ttu-id="d87a4-120">Utilizzare la scheda **alias** per creare l'alias.</span><span class="sxs-lookup"><span data-stu-id="d87a4-120">Use the **Alias** tab to create the alias.</span></span>  
  
3.  <span data-ttu-id="d87a4-121">Esaminare l'elenco dei componenti rilevati, modificare le selezioni secondo necessità e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d87a4-121">Review the list of components detected, modify the selections as necessary, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d87a4-122">Nella pagina **parametri connessione** selezionare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che si desidera analizzare, selezionare il metodo di autenticazione e, se necessario, immettere le informazioni sul nome utente e la password e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="d87a4-122">On the **Connection Parameters** page, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you want to scan, select the authentication method and, if necessary, enter user name and password information, and then click **Next**.</span></span>  
  
     <span data-ttu-id="d87a4-123">Il nome dell'istanza predefinita è MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="d87a4-123">The default instance name is MSSQLSERVER.</span></span>  
  
5.  <span data-ttu-id="d87a4-124">Per i componenti selezionati, immettere le informazioni richieste.</span><span class="sxs-lookup"><span data-stu-id="d87a4-124">For selected components, enter the requested information.</span></span> <span data-ttu-id="d87a4-125">Per ulteriori informazioni sulle singole finestre di dialogo, vedere Guida di [riferimento all'interfaccia utente di preparazione aggiornamento](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="d87a4-125">For more information about individual dialog boxes, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
6.  <span data-ttu-id="d87a4-126">Nella pagina **Conferma impostazioni di preparazione aggiornamento** verificare le informazioni immesse.</span><span class="sxs-lookup"><span data-stu-id="d87a4-126">On the **Confirm Upgrade Advisor Setting** page, review the information that you entered.</span></span> <span data-ttu-id="d87a4-127">È possibile selezionare \*\*Invia report a [!INCLUDE[msCoName](../../includes/msconame-md.md)] \*\* se si desidera inviare il report di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d87a4-127">You can select **Send reports to [!INCLUDE[msCoName](../../includes/msconame-md.md)]** if you want to submit your upgrade report.</span></span> <span data-ttu-id="d87a4-128">È inoltre possibile consultare l'informativa sulla privacy.</span><span class="sxs-lookup"><span data-stu-id="d87a4-128">You can also review the privacy policy.</span></span>  
  
7.  <span data-ttu-id="d87a4-129">Fare clic su **Esegui** per analizzare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d87a4-129">Click **Run** to analyze the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
8.  <span data-ttu-id="d87a4-130">Al termine dell'analisi, fare clic su **Avvia report** per visualizzare i problemi di aggiornamento rilevati.</span><span class="sxs-lookup"><span data-stu-id="d87a4-130">When the analysis is finished, click **Launch Report** to view the detected upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d87a4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d87a4-131">See Also</span></span>  
 <span data-ttu-id="d87a4-132">[Procedura: avvio di preparazione aggiornamento](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="d87a4-132">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="d87a4-133">[Esecuzione di preparazione aggiornamento &#40;interfaccia utente&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="d87a4-133">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 [<span data-ttu-id="d87a4-134">Uso di Preparazione aggiornamento</span><span class="sxs-lookup"><span data-stu-id="d87a4-134">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
