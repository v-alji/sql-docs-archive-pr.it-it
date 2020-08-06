---
title: "Per la connessione dati viene utilizzata l'autenticazione di Windows e le credenziali utente non possono essere delegate. Impossibile aggiornare le connessioni seguenti: dati PowerPivot | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d2006df1-d244-4786-b272-49d8996cc88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: be4c61ad4514f3aa4f6f1eda1fe44ad97c4c064f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626954"
---
# <a name="the-data-connection-uses-windows-authentication-and-user-credentials-could-not-be-delegated-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="facdd-103">Per la connessione dati viene utilizzata l'autenticazione di Windows e le credenziali utente non possono essere delegate.</span><span class="sxs-lookup"><span data-stu-id="facdd-103">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="facdd-104">Impossibile aggiornare le connessioni seguenti: Dati di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="facdd-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="facdd-105">Per cartelle di lavoro di Excel contenenti dati PowerPivot, in Excel Services viene restituito questo errore se non è possibile connettersi a un'istanza del server PowerPivot in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="facdd-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to a PowerPivot server instance in SharePoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="facdd-106">Dettagli</span><span class="sxs-lookup"><span data-stu-id="facdd-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="facdd-107">Si applica a</span><span class="sxs-lookup"><span data-stu-id="facdd-107">Applies to</span></span>|<span data-ttu-id="facdd-108">PowerPivot per SharePoint</span><span class="sxs-lookup"><span data-stu-id="facdd-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="facdd-109">Versione prodotto</span><span class="sxs-lookup"><span data-stu-id="facdd-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="facdd-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="facdd-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="facdd-111">Causa</span><span class="sxs-lookup"><span data-stu-id="facdd-111">Cause</span></span>|<span data-ttu-id="facdd-112">Errore di connessione nel tentativo di utilizzare un provider di dati PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="facdd-112">Connection failed when attempting to use a PowerPivot data provider.</span></span>|  
|<span data-ttu-id="facdd-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="facdd-113">Message Text</span></span>|<span data-ttu-id="facdd-114">Per la connessione dati viene utilizzata l'autenticazione di Windows e le credenziali utente non possono essere delegate.</span><span class="sxs-lookup"><span data-stu-id="facdd-114">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="facdd-115">Impossibile aggiornare le connessioni seguenti: Dati di PowerPivot</span><span class="sxs-lookup"><span data-stu-id="facdd-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="facdd-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="facdd-116">Explanation</span></span>  
 <span data-ttu-id="facdd-117">Questo messaggio di errore può avere più cause.</span><span class="sxs-lookup"><span data-stu-id="facdd-117">There are multiple causes for this error message.</span></span> <span data-ttu-id="facdd-118">Il fattore comune a tutte è che tramite Excel Services non è possibile ottenere un'identità utente di Windows valida da un token di attestazione in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="facdd-118">The common factor behind all of them is that Excel Services cannot get a valid Windows user identity from a claims token in SharePoint.</span></span> <span data-ttu-id="facdd-119">Nel caso di cartelle di lavoro di Excel contenenti dati PowerPivot, questo errore si verifica quando sussiste una delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="facdd-119">In the case of Excel workbooks that contain PowerPivot data, this error occurs when any of the following conditions exist:</span></span>  
  
-   <span data-ttu-id="facdd-120">Claims nel Servizio token Windows non è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="facdd-120">The Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="facdd-121">È possibile confermare la causa di questo errore visualizzando il file registro di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="facdd-121">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="facdd-122">Se nei registri di SharePoint è incluso il messaggio "Impossibile trovare l'endpoint di pipe di 'net.pipe://localhost/s 4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' nel computer locale", Claims nel Servizio token Windows non è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="facdd-122">If the SharePoint logs include the message "The pipe endpoint 'net.pipe://localhost/s4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' could not be found on your local machine", the Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="facdd-123">Per avviarlo, utilizzare Amministrazione centrale, quindi verificare che il servizio sia in esecuzione nell'applicazione console Servizi.</span><span class="sxs-lookup"><span data-stu-id="facdd-123">To start it, use Central Administration and then verify the service is running in the Services console application.</span></span>  
  
-   <span data-ttu-id="facdd-124">Un controller di dominio non è disponibile per la convalida dell'identità utente.</span><span class="sxs-lookup"><span data-stu-id="facdd-124">A domain controller is not available to validate the user identity.</span></span> <span data-ttu-id="facdd-125">Claims nel Servizio token Windows non utilizza le credenziali memorizzate nella cache.</span><span class="sxs-lookup"><span data-stu-id="facdd-125">The Claims to Windows Token Service does not use cached credentials.</span></span> <span data-ttu-id="facdd-126">Convalida l'identità utente per ogni connessione.</span><span class="sxs-lookup"><span data-stu-id="facdd-126">It validates the user identity for each connection.</span></span> <span data-ttu-id="facdd-127">È possibile confermare la causa di questo errore visualizzando il file registro di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="facdd-127">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="facdd-128">Se nei registri di SharePoint è incluso il messaggio "Impossibile recuperare WindowsIdentity da IClaimsIdentity", l'identità utente non può essere autenticata.</span><span class="sxs-lookup"><span data-stu-id="facdd-128">If the SharePoint logs include the message "Failed to get WindowsIdentity from IClaimsIdentity", the user identity could not be authenticated.</span></span>  
  
-   <span data-ttu-id="facdd-129">I computer devono essere membri dello stesso dominio o trovarsi in domini in cui è disponibile una relazione di trust bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="facdd-129">The computers must be members of the same domain or in domains that have a two-way trust relationship.</span></span>  
  
-   <span data-ttu-id="facdd-130">È necessario utilizzare account utente di dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="facdd-130">You must use Windows domain user accounts.</span></span> <span data-ttu-id="facdd-131">Gli account devono disporre di un UPN (Universal Principal Name).</span><span class="sxs-lookup"><span data-stu-id="facdd-131">The accounts must have a Universal Principal Name (UPN).</span></span>  
  
-   <span data-ttu-id="facdd-132">L'account servizio di Excel Services deve disporre delle autorizzazioni di Active Directory per eseguire una query sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="facdd-132">The Excel Services service account must have Active Directory permissions to query the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="facdd-133">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="facdd-133">User Action</span></span>  
 <span data-ttu-id="facdd-134">Utilizzare le istruzioni seguenti per controllare lo stato di Claims nel Servizio token Windows.</span><span class="sxs-lookup"><span data-stu-id="facdd-134">Use the following instructions to check the status of the Claims to Windows Token Service.</span></span>  
  
 <span data-ttu-id="facdd-135">Per tutti gli altri scenari, controllare con l'amministratore di rete.</span><span class="sxs-lookup"><span data-stu-id="facdd-135">For all other scenarios, check with your network administrator.</span></span>  
  
#### <a name="enable-claims-to-windows-token-service"></a><span data-ttu-id="facdd-136">Abilitare Claims nel Servizio token Windows</span><span class="sxs-lookup"><span data-stu-id="facdd-136">Enable Claims to Windows Token Service</span></span>  
  
1.  <span data-ttu-id="facdd-137">In Impostazioni sistema di amministrazione centrale fare clic **su Gestisci servizi nel server**.</span><span class="sxs-lookup"><span data-stu-id="facdd-137">In Central Administration, in System Settings, click **Manage services on server**.</span></span>  
  
2.  <span data-ttu-id="facdd-138">Selezionare **Attestazioni per il servizio token Windows**e quindi fare clic su **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="facdd-138">Select **Claims to Windows Token Service**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="facdd-139">Nella console Servizi verificare che anche il servizio sia in esecuzione:</span><span class="sxs-lookup"><span data-stu-id="facdd-139">Verify the service is also running in the Services console:</span></span>  
  
    1.  <span data-ttu-id="facdd-140">In Strumenti di amministrazione fare clic su Servizi.</span><span class="sxs-lookup"><span data-stu-id="facdd-140">In Administrative Tools, click Services.</span></span>  
  
    2.  <span data-ttu-id="facdd-141">Avviare Claims nel Servizio token Windows nel caso non sia in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="facdd-141">Start the Claims to Windows Token Service if it is not running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="facdd-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="facdd-142">See Also</span></span>  
 [<span data-ttu-id="facdd-143">Configurare gli account del servizio PowerPivot</span><span class="sxs-lookup"><span data-stu-id="facdd-143">Configure PowerPivot Service Accounts</span></span>](configure-power-pivot-service-accounts.md)  
  
  
