---
title: Informazioni sulla pubblicazione, avvisi (pubblicazione snapshot, SQL Server 2005 e versioni successive) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.publicationinfo.warningsandagents.snapshot.f1
ms.assetid: 7aa2eb52-b6b7-4dd3-8483-8ef00d9f0435
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a3ae662a339e1e211ce4f46a588f4d7de65bf5e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717904"
---
# <a name="publication-information-warnings-snapshot-publication-sql-server-2005-and-later"></a><span data-ttu-id="c630a-102">Informazioni sulla pubblicazione, Avvisi (pubblicazione snapshot, SQL Server 2005 e versioni successive)</span><span class="sxs-lookup"><span data-stu-id="c630a-102">Publication Information, Warnings (Snapshot Publication, SQL Server 2005 and Later)</span></span>
  <span data-ttu-id="c630a-103">La scheda **Avvisi** è disponibile per i server di distribuzione che eseguono [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="c630a-103">The **Warnings** tab is available for Distributors that are running [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span> <span data-ttu-id="c630a-104">La scheda **Avvisi** consente di eseguire le attività seguenti per la pubblicazione selezionata:</span><span class="sxs-lookup"><span data-stu-id="c630a-104">The **Warnings** tab allows you to perform the following tasks for the selected publication:</span></span>  
  
-   <span data-ttu-id="c630a-105">Abilitazione di avvisi.</span><span class="sxs-lookup"><span data-stu-id="c630a-105">Enable warnings.</span></span>  
  
-   <span data-ttu-id="c630a-106">Specificare valori soglia associati agli avvisi.</span><span class="sxs-lookup"><span data-stu-id="c630a-106">Specify thresholds associated with warnings.</span></span>  
  
-   <span data-ttu-id="c630a-107">Definire messaggi di avviso associati ad avvisi.</span><span class="sxs-lookup"><span data-stu-id="c630a-107">Define alerts associated with warnings.</span></span>  
  
## <a name="warnings-thresholds-and-alerts"></a><span data-ttu-id="c630a-108">Avvisi, soglie e messaggi di avviso</span><span class="sxs-lookup"><span data-stu-id="c630a-108">Warnings, Thresholds, and Alerts</span></span>  
 <span data-ttu-id="c630a-109">Per impostazione predefinita, Monitoraggio replica visualizza avvisi per le sottoscrizioni non inizializzate, includendo lo stato **Sottoscrizione non inizializzata** come avviso nella colonna **Stato** delle pagine contenenti informazioni sulla sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="c630a-109">By default, Replication Monitor displays warnings for uninitialized subscriptions: a status of **Uninitialized subscription** is displayed as a warning in the **Status** column of pages that include subscription information.</span></span> <span data-ttu-id="c630a-110">Per le pubblicazioni snapshot, è inoltre possibile specificare che l'imminente scadenza della sottoscrizione venga notificata tramite un avviso impostando l'opzione **Avvisa se una sottoscrizione scade entro il valore soglia**.</span><span class="sxs-lookup"><span data-stu-id="c630a-110">For snapshot publications, you can also specify that imminent subscription expiration results in a warning by setting the option **Warn if a subscription will expire within the threshold**.</span></span> <span data-ttu-id="c630a-111">Se il valore soglia specificato viene raggiunto o superato, lo stato della sottoscrizione viene visualizzato come **Scadenza imminente/Scaduta** , a meno che non sia necessario visualizzare un problema con una priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="c630a-111">If the specified threshold is met or exceeded, the subscription status is displayed as **Expiring soon/Expired** (unless an issue with a higher priority needs to be displayed).</span></span>  
  
 <span data-ttu-id="c630a-112">Oltre a visualizzare un avviso in Monitoraggio replica, il raggiungimento di un valore soglia può inoltre attivare un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="c630a-112">In addition to displaying a warning in Replication Monitor, reaching a threshold can also trigger an alert.</span></span> <span data-ttu-id="c630a-113">Gli avvisi vengono definiti facendo clic su **Configura avvisi** e specificando le informazioni appropriate nella finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="c630a-113">Alerts are defined by clicking **Configure Alerts** and providing information in the **Configure Replication Alerts** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c630a-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="c630a-114">Options</span></span>  
 <span data-ttu-id="c630a-115">**Enabled**</span><span class="sxs-lookup"><span data-stu-id="c630a-115">**Enabled**</span></span>  
 <span data-ttu-id="c630a-116">Selezionare questa opzione per abilitare un avviso e specificare un valore soglia.</span><span class="sxs-lookup"><span data-stu-id="c630a-116">Select to enable a warning and specify a threshold.</span></span>  
  
 <span data-ttu-id="c630a-117">**Warning**</span><span class="sxs-lookup"><span data-stu-id="c630a-117">**Warning**</span></span>  
 <span data-ttu-id="c630a-118">Descrizione dell'avviso associato al valore soglia.</span><span class="sxs-lookup"><span data-stu-id="c630a-118">A description of the warning associated with a threshold.</span></span>  
  
 <span data-ttu-id="c630a-119">**Soglia**</span><span class="sxs-lookup"><span data-stu-id="c630a-119">**Threshold**</span></span>  
 <span data-ttu-id="c630a-120">Consente di specificare un valore per la soglia.</span><span class="sxs-lookup"><span data-stu-id="c630a-120">Specify a value for the threshold.</span></span>  
  
 <span data-ttu-id="c630a-121">**Configura avvisi**</span><span class="sxs-lookup"><span data-stu-id="c630a-121">**Configure Alerts**</span></span>  
 <span data-ttu-id="c630a-122">Selezionare una riga nella griglia **Avvisi** e fare clic su **Configura avvisi** per aprire la finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="c630a-122">Select a row in the **Warnings** grid, and click **Configure Alerts** to launch the **Configure Replication Alerts** dialog box.</span></span> <span data-ttu-id="c630a-123">Tramite questa finestra di dialogo è possibile definire un avviso associato al valore soglia e all'avviso selezionati.</span><span class="sxs-lookup"><span data-stu-id="c630a-123">The dialog box allows you to define an alert, which is associated with the selected threshold and warning.</span></span>  
  
 <span data-ttu-id="c630a-124">**Ignora modifiche**</span><span class="sxs-lookup"><span data-stu-id="c630a-124">**Discard Changes**</span></span>  
 <span data-ttu-id="c630a-125">Fare clic su questo pulsante per ignorare le eventuali modifiche apportate agli avvisi e alle soglie.</span><span class="sxs-lookup"><span data-stu-id="c630a-125">Click to discard any changes to warnings and thresholds.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c630a-126">La scelta del pulsante **Ignora modifiche** non influisce sugli avvisi definiti nella finestra di dialogo **Configura avvisi di replica** .</span><span class="sxs-lookup"><span data-stu-id="c630a-126">Clicking **Discard Changes** does not affect alerts defined in the **Configure Replication Alerts** dialog box.</span></span>  
  
 <span data-ttu-id="c630a-127">**Salva modifiche**</span><span class="sxs-lookup"><span data-stu-id="c630a-127">**Save Changes**</span></span>  
 <span data-ttu-id="c630a-128">Fare clic su questo pulsante per salvare le eventuali modifiche apportate agli avvisi e alle soglie.</span><span class="sxs-lookup"><span data-stu-id="c630a-128">Click to save any changes to warnings and thresholds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c630a-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c630a-129">See Also</span></span>  
 <span data-ttu-id="c630a-130">[Avviare Monitoraggio replica](monitor/start-the-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c630a-130">[Start the Replication Monitor](monitor/start-the-replication-monitor.md) </span></span>  
 <span data-ttu-id="c630a-131">[Visualizzare le informazioni ed eseguire attività usando Monitoraggio replica](monitor/view-information-and-perform-tasks-replication-monitor.md) </span><span class="sxs-lookup"><span data-stu-id="c630a-131">[View Information and Perform Tasks using Replication Monitor](monitor/view-information-and-perform-tasks-replication-monitor.md) </span></span>  
 [<span data-ttu-id="c630a-132">Monitoraggio della replica</span><span class="sxs-lookup"><span data-stu-id="c630a-132">Monitoring Replication</span></span>](monitoring-replication.md)  
  
  
