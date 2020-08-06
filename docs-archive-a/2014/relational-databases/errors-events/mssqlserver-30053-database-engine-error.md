---
title: MSSQLSERVER_30053 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 8ad23889-e243-4bd7-bc3e-150403399d89
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 02d6262f93ef3dbbc9834053f864046b4dca30f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628742"
---
# <a name="mssqlserver_30053"></a><span data-ttu-id="5a048-102">MSSQLSERVER_30053</span><span class="sxs-lookup"><span data-stu-id="5a048-102">MSSQLSERVER_30053</span></span>
    
## <a name="details"></a><span data-ttu-id="5a048-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5a048-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a048-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5a048-104">Product Name</span></span>|<span data-ttu-id="5a048-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a048-105">SQL Server</span></span>|  
|<span data-ttu-id="5a048-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5a048-106">Event ID</span></span>|<span data-ttu-id="5a048-107">30053</span><span class="sxs-lookup"><span data-stu-id="5a048-107">30053</span></span>|  
|<span data-ttu-id="5a048-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5a048-108">Event Source</span></span>|<span data-ttu-id="5a048-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5a048-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5a048-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5a048-110">Component</span></span>|<span data-ttu-id="5a048-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5a048-111">SQLEngine</span></span>|  
|<span data-ttu-id="5a048-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5a048-112">Symbolic Name</span></span>|<span data-ttu-id="5a048-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a048-113">FTXT_QUERY_E_WORDBREAKINGTIMEOUT</span></span>|  
|<span data-ttu-id="5a048-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5a048-114">Message Text</span></span>|<span data-ttu-id="5a048-115">Timeout del word breaking per la stringa di query full-text.</span><span class="sxs-lookup"><span data-stu-id="5a048-115">Word breaking timed out for the full-text query string.</span></span> <span data-ttu-id="5a048-116">Questo problema può verificarsi se il word breaker impiega molto tempo per elaborare la stringa di query full-text o se è in esecuzione un numero elevato di query nel server.</span><span class="sxs-lookup"><span data-stu-id="5a048-116">This can happen if the wordbreaker took a long time to process the full-text query string, or if a large number of queries are running on the server.</span></span> <span data-ttu-id="5a048-117">Provare a eseguire nuovamente la query in un carico ridotto.</span><span class="sxs-lookup"><span data-stu-id="5a048-117">Try running the query again under a lighter load.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a048-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5a048-118">Explanation</span></span>  
 <span data-ttu-id="5a048-119">Un errore di timeout del word breaking può verificarsi nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a048-119">A word-breaking timeout error can occur in the following situations:</span></span>  
  
-   <span data-ttu-id="5a048-120">Il word breaker per il linguaggio di query non è configurato correttamente. Le impostazioni del Registro di sistema, ad esempio, non sono corrette.</span><span class="sxs-lookup"><span data-stu-id="5a048-120">The word breaker for the query language is configured incorrectly; for example, its registry settings are incorrect.</span></span>  
  
-   <span data-ttu-id="5a048-121">Il malfunzionamento del word breaker è dovuto a una stringa di query specifica.</span><span class="sxs-lookup"><span data-stu-id="5a048-121">The word breaker malfunctions for a specific query string.</span></span>  
  
-   <span data-ttu-id="5a048-122">Il word breaker restituisce troppi dati per una stringa di query specifica.</span><span class="sxs-lookup"><span data-stu-id="5a048-122">The word breaker returns too much data for a specific query string.</span></span> <span data-ttu-id="5a048-123">I dati in eccesso sono considerati un potenziale attacco con sovraccarico del buffer e di conseguenza viene arrestato il processo del daemon di filtri (fdhost.exe) che ospita i servizi di word breaking.</span><span class="sxs-lookup"><span data-stu-id="5a048-123">Excess data is treated as a potential buffer overrun attack, and shuts down the filter daemon process (fdhost.exe), which hosts the word-breaking services.</span></span>  
  
-   <span data-ttu-id="5a048-124">La configurazione del processo del daemon di filtri non è corretta.</span><span class="sxs-lookup"><span data-stu-id="5a048-124">The filter daemon process configuration is incorrect.</span></span>  
  
     <span data-ttu-id="5a048-125">I problemi di configurazione più comuni sono rappresentati dalla scadenza della password o da criteri del dominio che impediscono l'accesso dell'account del daemon di filtri.</span><span class="sxs-lookup"><span data-stu-id="5a048-125">The most common configuration problems are password expiration or a domain policy that prevents the filter daemon account from logging on.</span></span>  
  
-   <span data-ttu-id="5a048-126">Un carico di lavoro di query molto elevato è in esecuzione nell'istanza server. Ad esempio, il word breaker impiega molto tempo per elaborare la stringa della query full-text o un numero elevato di query sono in esecuzione nel server.</span><span class="sxs-lookup"><span data-stu-id="5a048-126">A very heavy query workload is running on the server instance; for example, the word-breaker took a long time to process the full-text query string, or a large number of queries are running on the server.</span></span> <span data-ttu-id="5a048-127">Si tratta tuttavia della causa meno probabile.</span><span class="sxs-lookup"><span data-stu-id="5a048-127">Note that this is the least likely cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a048-128">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5a048-128">User Action</span></span>  
 <span data-ttu-id="5a048-129">Selezionare l'azione dell'utente adatta alla probabile causa del timeout, come segue:</span><span class="sxs-lookup"><span data-stu-id="5a048-129">Select the user action that is appropriate to the probable cause of the timeout, as follows:</span></span>  
  
|<span data-ttu-id="5a048-130">Possibile causa</span><span class="sxs-lookup"><span data-stu-id="5a048-130">Probable cause</span></span>|<span data-ttu-id="5a048-131">Azione utente</span><span class="sxs-lookup"><span data-stu-id="5a048-131">User action</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5a048-132">Il word breaker per il linguaggio di query non è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="5a048-132">The word breaker for the query language is configured incorrectly.</span></span>|<span data-ttu-id="5a048-133">Se si utilizza un word breaker di terze parti, è possibile che non sia stato registrato correttamente nel sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5a048-133">If you are using a third-party word breaker it might be incorrectly registered with the operating system.</span></span> <span data-ttu-id="5a048-134">In questo caso, registrare nuovamente il word breaker.</span><span class="sxs-lookup"><span data-stu-id="5a048-134">In this case, re-register the word breaker.</span></span> <span data-ttu-id="5a048-135">Per altre informazioni, vedere [Ripristinare i word breaker usati dalla ricerca alla versione precedente](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span><span class="sxs-lookup"><span data-stu-id="5a048-135">For more information, see [Revert the Word Breakers Used by Search to the Previous Version](../search/revert-the-word-breakers-used-by-search-to-the-previous-version.md).</span></span>|  
|<span data-ttu-id="5a048-136">Il malfunzionamento del word breaker è dovuto a una stringa di query specifica.</span><span class="sxs-lookup"><span data-stu-id="5a048-136">The word breaker malfunctions for a specific query string.</span></span>|<span data-ttu-id="5a048-137">Se il word breaker è supportato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a048-137">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="5a048-138">Il word breaker restituisce troppi dati per una stringa di query specifica.</span><span class="sxs-lookup"><span data-stu-id="5a048-138">The word breaker returns too much data for a specific query string.</span></span>|<span data-ttu-id="5a048-139">Se il word breaker è supportato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contattare il Servizio Supporto Tecnico Clienti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a048-139">If the word breaker is supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], contact Microsoft Customer Service and Support.</span></span>|  
|<span data-ttu-id="5a048-140">La configurazione del processo del daemon di filtri non è corretta.</span><span class="sxs-lookup"><span data-stu-id="5a048-140">The filter daemon process configuration is incorrect.</span></span>|<span data-ttu-id="5a048-141">Assicurarsi che venga utilizzata la password corrente e che i criteri di dominio non stiano impedendo l'accesso dell'account del daemon di filtri.</span><span class="sxs-lookup"><span data-stu-id="5a048-141">Ensure that you are using the current password and that a domain policy is not preventing the filter daemon account from logging on.</span></span>|  
|<span data-ttu-id="5a048-142">Nell'istanza del server è in esecuzione un carico di lavoro molto elevato di query.</span><span class="sxs-lookup"><span data-stu-id="5a048-142">A very heavy query workload is running on the server instance.</span></span>|<span data-ttu-id="5a048-143">Provare a eseguire nuovamente la query in un carico ridotto.</span><span class="sxs-lookup"><span data-stu-id="5a048-143">Try running the query again under a lighter load.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a048-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a048-144">See Also</span></span>  
 <span data-ttu-id="5a048-145">[Impostare l'account del servizio per l'utilità di avvio del daemon filtri full-text](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="5a048-145">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 <span data-ttu-id="5a048-146">[Ricerca full-text](../search/full-text-search.md) </span><span class="sxs-lookup"><span data-stu-id="5a048-146">[Full-Text Search](../search/full-text-search.md) </span></span>  
 <span data-ttu-id="5a048-147">[sp_help_fulltext_system_components &#40;&#41;Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="5a048-147">[sp_help_fulltext_system_components &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql) </span></span>  
 <span data-ttu-id="5a048-148">[Configurare e gestire Word breaker e stemmer per la ricerca](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span><span class="sxs-lookup"><span data-stu-id="5a048-148">[Configure and Manage Word Breakers and Stemmers for Search](../search/configure-and-manage-word-breakers-and-stemmers-for-search.md) </span></span>  
 [<span data-ttu-id="5a048-149">Configurare e gestire filtri per la ricerca</span><span class="sxs-lookup"><span data-stu-id="5a048-149">Configure and Manage Filters for Search</span></span>](../search/configure-and-manage-filters-for-search.md)  
  
  
