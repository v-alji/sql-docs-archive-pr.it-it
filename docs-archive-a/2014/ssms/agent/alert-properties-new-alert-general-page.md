---
title: Proprietà avviso-nuovo avviso (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.general.f1
ms.assetid: f5c11610-62e3-44df-9800-a5dc35be4a09
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471b0062ecc805e83020495e422f8914baec5f71
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722228"
---
# <a name="alert-properties-new-alert-general-page"></a><span data-ttu-id="10bf5-102">Proprietà avviso-nuovo avviso (pagina generale)</span><span class="sxs-lookup"><span data-stu-id="10bf5-102">Alert Properties-New Alert (General Page)</span></span>
  <span data-ttu-id="10bf5-103">Utilizzare questa pagina per visualizzare e modificare le proprietà generali degli [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avvisi di Agent.</span><span class="sxs-lookup"><span data-stu-id="10bf5-103">Use this page to view and modify the general properties of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="10bf5-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="10bf5-104">Options</span></span>  
 <span data-ttu-id="10bf5-105">**Nome**</span><span class="sxs-lookup"><span data-stu-id="10bf5-105">**Name**</span></span>  
 <span data-ttu-id="10bf5-106">Consente di modificare il nome dell'avviso.</span><span class="sxs-lookup"><span data-stu-id="10bf5-106">Change the name of the alert.</span></span>  
  
 <span data-ttu-id="10bf5-107">**Attiva**</span><span class="sxs-lookup"><span data-stu-id="10bf5-107">**Enable**</span></span>  
 <span data-ttu-id="10bf5-108">Consente di abilitare l'avviso.</span><span class="sxs-lookup"><span data-stu-id="10bf5-108">Enable the alert.</span></span> <span data-ttu-id="10bf5-109">Se l'avviso non è abilitato, le azioni specificate nell'avviso non verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="10bf5-109">When the alert is not enabled, the actions specified in the alert do not occur.</span></span>  
  
 <span data-ttu-id="10bf5-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="10bf5-110">**Type**</span></span>  
 <span data-ttu-id="10bf5-111">Consente di selezionare il tipo di avviso:</span><span class="sxs-lookup"><span data-stu-id="10bf5-111">Select the type of alert:</span></span>  
  
-   <span data-ttu-id="10bf5-112">**Avviso per evento di SQL Server** risponde ai messaggi nel registro degli eventi di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="10bf5-112">**SQL Server event alert** responds to messages in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows event log.</span></span>  
  
-   <span data-ttu-id="10bf5-113">**Avviso relativo alle prestazioni di SQL Server** risponde a una specifica condizione in un contatore delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="10bf5-113">**SQL Server performance condition alert** responds to a specific condition in a performance counter.</span></span>  
  
-   <span data-ttu-id="10bf5-114">**Avviso per evento WMI** risponde a un evento del servizio Strumentazione gestione Windows (WMI, Windows Management Instrumentation).</span><span class="sxs-lookup"><span data-stu-id="10bf5-114">**WMI event alert** responds to a Windows Management Instrumentation (WMI) event.</span></span>  
  
## <a name="sql-server-event-alert-options"></a><span data-ttu-id="10bf5-115">Opzioni di Avviso per evento di SQL Server</span><span class="sxs-lookup"><span data-stu-id="10bf5-115">SQL Server Event Alert Options</span></span>  
 <span data-ttu-id="10bf5-116">**Nome database**</span><span class="sxs-lookup"><span data-stu-id="10bf5-116">**Database name**</span></span>  
 <span data-ttu-id="10bf5-117">Consente di specificare un database per l'evento o **tutti i database** per rispondere a un messaggio indipendentemente dal database in cui si verifica l'evento.</span><span class="sxs-lookup"><span data-stu-id="10bf5-117">Specify a database for the event, or **all databases** to respond to a message regardless of the database where the event occurs.</span></span>  
  
 <span data-ttu-id="10bf5-118">**Numero di errore**</span><span class="sxs-lookup"><span data-stu-id="10bf5-118">**Error number**</span></span>  
 <span data-ttu-id="10bf5-119">Consente di specificare che l'evento risponde a un errore e di indicare il numero dell'errore.</span><span class="sxs-lookup"><span data-stu-id="10bf5-119">Specify that this event responds to an error, and specify the error number.</span></span>  
  
 <span data-ttu-id="10bf5-120">**Gravità**</span><span class="sxs-lookup"><span data-stu-id="10bf5-120">**Severity**</span></span>  
 <span data-ttu-id="10bf5-121">Consente di specificare che l'evento risponde a tutti messaggi con uno specifico livello di gravità e di indicare tale livello.</span><span class="sxs-lookup"><span data-stu-id="10bf5-121">Specify that this event responds to any message with a specific severity level, and specify the severity level.</span></span>  
  
 <span data-ttu-id="10bf5-122">**Genera avviso quando il messaggio contiene**</span><span class="sxs-lookup"><span data-stu-id="10bf5-122">**Raise alert when message contains**</span></span>  
 <span data-ttu-id="10bf5-123">Consente di applicare un filtro agli eventi in base a una stringa specifica.</span><span class="sxs-lookup"><span data-stu-id="10bf5-123">Filter events by a specific string.</span></span> <span data-ttu-id="10bf5-124">Se questa opzione è selezionata, l'avviso risponde solo agli eventi contenenti la stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="10bf5-124">When this option is selected, the alert only responds to events that contain a specific string.</span></span>  
  
 <span data-ttu-id="10bf5-125">**Testo del messaggio**</span><span class="sxs-lookup"><span data-stu-id="10bf5-125">**Message text**</span></span>  
 <span data-ttu-id="10bf5-126">Consente di specificare la stringa da utilizzare come filtro per gli eventi.</span><span class="sxs-lookup"><span data-stu-id="10bf5-126">Specify the string to use to filter events.</span></span>  
  
## <a name="sql-server-performance-condition-alerts"></a><span data-ttu-id="10bf5-127">Opzioni di Avviso relativo alle prestazioni di SQL Server</span><span class="sxs-lookup"><span data-stu-id="10bf5-127">SQL Server Performance Condition Alerts</span></span>  
 <span data-ttu-id="10bf5-128">**Object**</span><span class="sxs-lookup"><span data-stu-id="10bf5-128">**Object**</span></span>  
 <span data-ttu-id="10bf5-129">Consente di specificare l'oggetto prestazioni da monitorare.</span><span class="sxs-lookup"><span data-stu-id="10bf5-129">Specify the performance object to monitor.</span></span>  
  
 <span data-ttu-id="10bf5-130">**Contatore**</span><span class="sxs-lookup"><span data-stu-id="10bf5-130">**Counter**</span></span>  
 <span data-ttu-id="10bf5-131">Consente di specificare il contatore all'interno dell'oggetto prestazioni da monitorare.</span><span class="sxs-lookup"><span data-stu-id="10bf5-131">Specify the counter within the performance object to monitor.</span></span>  
  
 <span data-ttu-id="10bf5-132">**Istanza**</span><span class="sxs-lookup"><span data-stu-id="10bf5-132">**Instance**</span></span>  
 <span data-ttu-id="10bf5-133">Consente di specificare l'istanza del contatore da monitorare.</span><span class="sxs-lookup"><span data-stu-id="10bf5-133">Specify the instance of the counter to monitor.</span></span>  
  
 <span data-ttu-id="10bf5-134">**Avvisa se il contatore**</span><span class="sxs-lookup"><span data-stu-id="10bf5-134">**Alert if counter**</span></span>  
 <span data-ttu-id="10bf5-135">Consente di specificare il comportamento del contatore a cui risponde l'evento.</span><span class="sxs-lookup"><span data-stu-id="10bf5-135">Specify the behavior of the counter that the alert responds to.</span></span> <span data-ttu-id="10bf5-136">È ad esempio possibile impostare questa opzione in modo che l'avviso risponda a una condizione in cui il valore del contatore **Spazio disponibile in tempdb (KB)** scende al di sotto di un determinata soglia o il valore di **Compilazioni SQL/sec** supera un determinato livello.</span><span class="sxs-lookup"><span data-stu-id="10bf5-136">For example, you may want the alert to respond to a condition where the value of the **Free space in tempdb (KB)** counter falls below a certain value, or you may want the alert to respond to a condition where the **SQL Compilations/sec** rises above a certain value.</span></span>  
  
 <span data-ttu-id="10bf5-137">**Valore**</span><span class="sxs-lookup"><span data-stu-id="10bf5-137">**Value**</span></span>  
 <span data-ttu-id="10bf5-138">Consente di specificare un valore per il contatore.</span><span class="sxs-lookup"><span data-stu-id="10bf5-138">Specify a value for the counter.</span></span>  
  
## <a name="wmi-event-alert-options"></a><span data-ttu-id="10bf5-139">Opzioni di Avviso per evento WMI</span><span class="sxs-lookup"><span data-stu-id="10bf5-139">WMI Event Alert Options</span></span>  
 <span data-ttu-id="10bf5-140">**Spazio dei nomi**</span><span class="sxs-lookup"><span data-stu-id="10bf5-140">**Namespace**</span></span>  
 <span data-ttu-id="10bf5-141">Consente di specificare lo spazio dei nomi da utilizzare per l'istruzione WQL (WMI Query Language).</span><span class="sxs-lookup"><span data-stu-id="10bf5-141">Specify the namespace to use for the WMI Query Language (WQL) statement.</span></span> <span data-ttu-id="10bf5-142">Sono supportati solo gli spazi dei nomi sul computer in cui è in esecuzione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="10bf5-142">Only namespaces on the computer that runs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent are supported.</span></span>  
  
 <span data-ttu-id="10bf5-143">**Query**</span><span class="sxs-lookup"><span data-stu-id="10bf5-143">**Query**</span></span>  
 <span data-ttu-id="10bf5-144">Consente di specificare l'istruzione WQL che identifica l'evento al quale risponde l'avviso.</span><span class="sxs-lookup"><span data-stu-id="10bf5-144">Specify the WQL statement that identifies the event that the alert responds to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10bf5-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10bf5-145">See Also</span></span>  
 <span data-ttu-id="10bf5-146">[Avvisi](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="10bf5-146">[Alerts](alerts.md) </span></span>  
 <span data-ttu-id="10bf5-147">[Utilizzo di WQL con il provider WMI per eventi del server](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span><span class="sxs-lookup"><span data-stu-id="10bf5-147">[Using WQL with the WMI Provider for Server Events](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md) </span></span>  
 <span data-ttu-id="10bf5-148">[Creare un avviso usando un numero di errore](create-an-alert-using-an-error-number.md) </span><span class="sxs-lookup"><span data-stu-id="10bf5-148">[Create an Alert Using an Error Number](create-an-alert-using-an-error-number.md) </span></span>  
 [<span data-ttu-id="10bf5-149">Creazione di un avviso utilizzando i livelli di gravità</span><span class="sxs-lookup"><span data-stu-id="10bf5-149">Create an Alert Using Severity Level</span></span>](create-an-alert-using-severity-level.md)  
  
  
