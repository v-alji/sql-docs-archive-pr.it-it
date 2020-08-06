---
title: Finestra di dialogo ' Impostazioni database di distribuzione ' | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.DistributorSettings.f1
helpviewer_keywords:
- Distributor Settings dialog box
ms.assetid: 8276a521-bdd1-4783-bdb6-7ab43499c0ca
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b864620f155e899868c95f58350f98e2b659c4e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624622"
---
# <a name="sql-server-replication-distributor-settings-dialog-box"></a><span data-ttu-id="1a176-102">Replica di SQL Server finestra di dialogo ' Impostazioni database di distribuzione '</span><span class="sxs-lookup"><span data-stu-id="1a176-102">SQL Server Replication 'Distributor Settings' dialog box</span></span>
  <span data-ttu-id="1a176-103">La finestra di dialogo **Impostazioni del server di distribuzione** consente di modificare le impostazioni dei server di distribuzione aggiunti al riquadro sinistro di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="1a176-103">The **Distributor Settings** dialog box enables you to change settings for Distributors that were added to the left pane in Replication Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="1a176-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1a176-104">Options</span></span>  
 <span data-ttu-id="1a176-105">**Connetti automaticamente all'avvio di Monitoraggio replica**</span><span class="sxs-lookup"><span data-stu-id="1a176-105">**Connect automatically when Replication Monitor starts**</span></span>  
 <span data-ttu-id="1a176-106">Selezionare questa opzione per consentire la connessione di Monitoraggio replica al server di distribuzione e per recuperare informazioni sullo stato.</span><span class="sxs-lookup"><span data-stu-id="1a176-106">Select to let Replication Monitor connect to the Distributor and retrieve status information.</span></span>  
  
 <span data-ttu-id="1a176-107">**Connection**</span><span class="sxs-lookup"><span data-stu-id="1a176-107">**Connection**</span></span>  
 <span data-ttu-id="1a176-108">Fare clic su questa opzione per visualizzare la finestra di dialogo **Connetti al server** .</span><span class="sxs-lookup"><span data-stu-id="1a176-108">Click to display the **Connect to Server** dialog box.</span></span> <span data-ttu-id="1a176-109">In questo modo sarà possibile visualizzare e modificare le proprietà e le credenziali di connessione utilizzate da Monitoraggio replica per la connessione al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1a176-109">This enables you to view and change the connection properties and credentials that Replication Monitor uses to connect to the Distributor.</span></span>  
  
 <span data-ttu-id="1a176-110">**Aggiorna automaticamente lo stato del server di distribuzione e delle sue pubblicazioni**</span><span class="sxs-lookup"><span data-stu-id="1a176-110">**Automatically refresh the status of this Distributor and its publications**</span></span>  
 <span data-ttu-id="1a176-111">Selezionare questa opzione per consentire l'aggiornamento automatico dello stato del server di distribuzione da parte di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="1a176-111">Select to let Replication Monitor automatically refresh the status for the Distributor.</span></span> <span data-ttu-id="1a176-112">Se questa opzione è selezionata, tramite Monitoraggio replica viene eseguito il polling del server di distribuzione per ottenere informazioni sullo stato in base all'intervallo di polling impostato utilizzando l'opzione **Frequenza di aggiornamento** .</span><span class="sxs-lookup"><span data-stu-id="1a176-112">If this option is selected, Replication Monitor polls the Distributor for status information based on the polling interval set by the **Refresh rate** option.</span></span> <span data-ttu-id="1a176-113">Per ulteriori informazioni sull'aggiornamento in Monitoraggio replica, vedere [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span><span class="sxs-lookup"><span data-stu-id="1a176-113">For more information about refresh in Replication Monitor, see [Caching, Refresh, and Replication Monitor Performance](monitor/caching-refresh-and-replication-monitor-performance.md).</span></span>  
  
 <span data-ttu-id="1a176-114">**Frequenza di aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="1a176-114">**Refresh rate**</span></span>  
 <span data-ttu-id="1a176-115">Immettere un valore, espresso in secondi, per specificare la frequenza di polling del server di distribuzione per ottenere informazioni sullo stato da parte di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="1a176-115">Enter a value (in seconds) to specify how frequently Replication Monitor should poll the Distributor for status.</span></span> <span data-ttu-id="1a176-116">Valori inferiori comportano polling più frequenti.</span><span class="sxs-lookup"><span data-stu-id="1a176-116">Lower values result in more frequent polling.</span></span> <span data-ttu-id="1a176-117">Questa condizione può influire sulle prestazioni nel server di distribuzione qualora si stiano monitorando molti server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="1a176-117">This can affect performance at the Distributor if you are monitoring many Publishers.</span></span> <span data-ttu-id="1a176-118">È consigliabile eseguire prove sul sistema per determinare un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="1a176-118">We recommend that you test your system to determine an appropriate value.</span></span> <span data-ttu-id="1a176-119">L'impostazione **Frequenza di aggiornamento** viene utilizzata anche se si seleziona **Aggiornamento automatico** in una delle finestre dei dettagli di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="1a176-119">The **Refresh rate** setting is also used if you select **Auto Refresh** in any of the detail windows in Replication Monitor.</span></span>  
  
 <span data-ttu-id="1a176-120">**Mostra tutti i server di pubblicazione di questo server di distribuzione nel gruppo seguente**</span><span class="sxs-lookup"><span data-stu-id="1a176-120">**Show all Publishers of this Distributor in the following group**</span></span>  
 <span data-ttu-id="1a176-121">Selezionare un gruppo di server di pubblicazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1a176-121">Select a Publisher group from the list.</span></span> <span data-ttu-id="1a176-122">Il server di pubblicazione viene visualizzato in questo gruppo nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="1a176-122">The Publisher is displayed under this group in the left pane.</span></span> <span data-ttu-id="1a176-123">I gruppi consentono di organizzare i server di pubblicazione e non influiscono sul funzionamento della replica.</span><span class="sxs-lookup"><span data-stu-id="1a176-123">Groups provide a way for you to organize Publishers and do not affect how replication functions.</span></span>  
  
 <span data-ttu-id="1a176-124">**Nuovo gruppo**</span><span class="sxs-lookup"><span data-stu-id="1a176-124">**New Group**</span></span>  
 <span data-ttu-id="1a176-125">Fare clic su questa opzione per creare un nuovo gruppo di server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="1a176-125">Click to create a new Publisher group.</span></span> <span data-ttu-id="1a176-126">Un gruppo di server di pubblicazione consente di organizzare facilmente i server di pubblicazione all'interno di Monitoraggio replica.</span><span class="sxs-lookup"><span data-stu-id="1a176-126">A Publisher group provides a way for you to conveniently organize Publishers within Replication Monitor.</span></span> <span data-ttu-id="1a176-127">I gruppi non influiscono sulla replica dei dati o sulla relazione tra i server in una topologia di replica.</span><span class="sxs-lookup"><span data-stu-id="1a176-127">Groups do not affect the replication of data or the relationship among servers in a replication topology.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a176-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a176-128">See Also</span></span>  
 <span data-ttu-id="1a176-129">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="1a176-129">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 [<span data-ttu-id="1a176-130">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="1a176-130">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
