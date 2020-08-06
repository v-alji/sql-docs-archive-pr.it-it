---
title: Opzione di configurazione del server common criteria compliance enabled | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- common criteria compliance
helpviewer_keywords:
- CC (common criteria) [Database Engine]
- common criteria compliance [Database Engine]
- Risidual Information Protection [Database Engine]
- RIP (Residual Information Protection)
ms.assetid: 61766eea-c450-408d-af33-fbe7ef8c9ff2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6722d05351b8b9e80240abb4edef0633a97b6da0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624358"
---
# <a name="common-criteria-compliance-enabled-server-configuration-option"></a><span data-ttu-id="fe727-102">Opzione di configurazione del server common criteria compliance enabled</span><span class="sxs-lookup"><span data-stu-id="fe727-102">common criteria compliance enabled Server Configuration Option</span></span>
  <span data-ttu-id="fe727-103">L'opzione Attiva conformità criteri comuni attiva gli elementi seguenti, necessari per i criteri comuni.</span><span class="sxs-lookup"><span data-stu-id="fe727-103">The common criteria compliance enabled option enables the following elements that are required for the Common Criteria.</span></span>  
  
|<span data-ttu-id="fe727-104">Criteri</span><span class="sxs-lookup"><span data-stu-id="fe727-104">Criteria</span></span>|<span data-ttu-id="fe727-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fe727-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="fe727-106">Protezione delle informazioni residuali (RIP, Residual Information Protection)</span><span class="sxs-lookup"><span data-stu-id="fe727-106">Residual Information Protection (RIP)</span></span>|<span data-ttu-id="fe727-107">RIP richiede la sovrascrittura di una allocazione di memoria con uno schema di bit noto prima che la memoria venga riallocata a una nuova risorsa.</span><span class="sxs-lookup"><span data-stu-id="fe727-107">RIP requires a memory allocation to be overwritten with a known pattern of bits before memory is reallocated to a new resource.</span></span> <span data-ttu-id="fe727-108">La conformità allo standard RIP consente una maggior sicurezza, ma la sovrascrittura dell'allocazione di memoria può rallentare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="fe727-108">Meeting the RIP standard can contribute to improved security; however, overwriting the memory allocation can slow performance.</span></span> <span data-ttu-id="fe727-109">La sovrascrittura viene eseguita dopo l'attivazione dell'opzione common criteria compliance enabled.</span><span class="sxs-lookup"><span data-stu-id="fe727-109">After the common criteria compliance enabled option is enabled, the overwriting occurs.</span></span>|  
|<span data-ttu-id="fe727-110">Possibilità di visualizzare le statistiche relative agli accessi</span><span class="sxs-lookup"><span data-stu-id="fe727-110">The ability to view login statistics</span></span>|<span data-ttu-id="fe727-111">Dopo l'attivazione dell'opzione common criteria compliance enabled, viene attivato il controllo degli accessi.</span><span class="sxs-lookup"><span data-stu-id="fe727-111">After the common criteria compliance enabled option is enabled, login auditing is enabled.</span></span> <span data-ttu-id="fe727-112">Ogni volta che un utente accede a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vengono rese disponibili le informazioni su data e ora dell'ultimo accesso riuscito, su data e ora dell'ultimo accesso non riuscito e sul numero di tentativi eseguiti tra l'ultimo accesso riuscito e l'accesso corrente.</span><span class="sxs-lookup"><span data-stu-id="fe727-112">Each time a user successfully logs in to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], information about the last successful login time, the last unsuccessful login time, and the number of attempts between the last successful and current login times is made available.</span></span> <span data-ttu-id="fe727-113">Queste statistiche di accesso possono essere visualizzate eseguendo una query sulla vista a gestione dinamica [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="fe727-113">These login statistics can be viewed by querying the [sys.dm_exec_sessions](/sql/relational-databases/system-dynamic-management-views/sys-dm-exec-sessions-transact-sql) dynamic management view.</span></span>|  
|<span data-ttu-id="fe727-114">La colonna GRANT non deve eseguire l'override della tabella DENY</span><span class="sxs-lookup"><span data-stu-id="fe727-114">That column GRANT should not override table DENY</span></span>|<span data-ttu-id="fe727-115">Dopo l'attivazione dell'opzione common criteria compliance enabled, un'istruzione DENY a livello di tabella ha la precedenza su un'istruzione GRANT a livello di colonna.</span><span class="sxs-lookup"><span data-stu-id="fe727-115">After the common criteria compliance enabled option is enabled, a table-level DENY takes precedence over a column-level GRANT.</span></span> <span data-ttu-id="fe727-116">Se l'opzione non è abilitata, un'istruzione GRANT a livello di colonna ha la precedenza su un'istruzione DENY a livello di tabella.</span><span class="sxs-lookup"><span data-stu-id="fe727-116">When the option is not enabled, a column-level GRANT takes precedence over a table-level DENY.</span></span>|  
  
 <span data-ttu-id="fe727-117">L'opzione Common Criteria Compliance Enabled è un'opzione avanzata.</span><span class="sxs-lookup"><span data-stu-id="fe727-117">The common criteria compliance enabled option is an advanced option.</span></span> <span data-ttu-id="fe727-118">I criteri comuni vengono valutati e certificati solo per l'edizione Enterprise e l'edizione Datacenter.</span><span class="sxs-lookup"><span data-stu-id="fe727-118">Common criteria is only evaluated and certified for the Enterprise edition and Datacenter edition.</span></span> <span data-ttu-id="fe727-119">Per lo stato più aggiornato della certificazione con criteri comuni, vedere il sito Web [Criteri comuni per Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="fe727-119">For the latest status of common criteria certification, see the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fe727-120">Oltre ad attivare l'opzione common criteria compliance enabled, è necessario scaricare ed eseguire uno script che completi la configurazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la conformità al livello di garanzia di valutazione 4+ (EAL4+) dei criteri comuni.</span><span class="sxs-lookup"><span data-stu-id="fe727-120">In addition to enabling the common criteria compliance enabled option, you also must download and run a script that finishes configuring [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to comply with Common Criteria Evaluation Assurance Level 4+ (EAL4+).</span></span> <span data-ttu-id="fe727-121">È possibile scaricare questo script dal sito Web relativo ai [criteri comuni per Microsoft SQL Server](https://go.microsoft.com/fwlink/?LinkId=616319) .</span><span class="sxs-lookup"><span data-stu-id="fe727-121">You can download this script from the [Microsoft SQL Server Common Criteria](https://go.microsoft.com/fwlink/?LinkId=616319) Web site.</span></span>  
  
 <span data-ttu-id="fe727-122">Se si utilizza la stored procedure di sistema sp_configure per modificare l'impostazione, è possibile modificare common criteria compliance enabled solo quando il valore di show advanced options è impostato su 1.</span><span class="sxs-lookup"><span data-stu-id="fe727-122">If you are using the sp_configure system stored procedure to change the setting, you can change common criteria compliance enabled only when show advanced options is set to 1.</span></span> <span data-ttu-id="fe727-123">L'impostazione diventa effettiva dopo il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="fe727-123">The setting takes effect after the server is restarted.</span></span> <span data-ttu-id="fe727-124">I possibili valori sono 0 e 1:</span><span class="sxs-lookup"><span data-stu-id="fe727-124">The possible values are 0 and 1:</span></span>  
  
-   <span data-ttu-id="fe727-125">0 indica che la conformità ai criteri comuni non è abilitata.</span><span class="sxs-lookup"><span data-stu-id="fe727-125">0 indicates that common criteria compliance is not enabled.</span></span> <span data-ttu-id="fe727-126">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="fe727-126">This is the default.</span></span>  
  
-   <span data-ttu-id="fe727-127">1 indica che la conformità ai criteri comuni è abilitata.</span><span class="sxs-lookup"><span data-stu-id="fe727-127">1 indicates that common criteria compliance is enabled.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="fe727-128">Esempi</span><span class="sxs-lookup"><span data-stu-id="fe727-128">Examples</span></span>  
 <span data-ttu-id="fe727-129">Nell'esempio seguente viene abilitata la conformità ai criteri comuni.</span><span class="sxs-lookup"><span data-stu-id="fe727-129">The following example enables common criteria compliance.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'common criteria compliance enabled', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe727-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe727-130">See Also</span></span>  
 [<span data-ttu-id="fe727-131">Opzioni di configurazione del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe727-131">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
