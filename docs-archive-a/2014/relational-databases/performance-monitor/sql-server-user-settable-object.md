---
title: Oggetto User Settable di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- User Settable object
- SQLServer:User Settable
ms.assetid: 633de3ef-533c-4f0c-9c7b-c105129d8e94
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7243ab4767c8de93dccf4556f136a94b47554d3d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713071"
---
# <a name="sql-server-user-settable-object"></a><span data-ttu-id="19809-102">Oggetto Definibile dall'utente di SQLServer</span><span class="sxs-lookup"><span data-stu-id="19809-102">SQL Server, User Settable Object</span></span>
  <span data-ttu-id="19809-103">L'oggetto **Definibile dall'utente** di Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consente di creare istanze di contatore personalizzate.</span><span class="sxs-lookup"><span data-stu-id="19809-103">The **User Settable** object in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to create custom counter instances.</span></span> <span data-ttu-id="19809-104">Utilizzare istanze di contatore personalizzate per monitorare gli aspetti del server non monitorati dai contatori esistenti, quali i componenti specifici del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzato (ad esempio, il numero di ordini registrati o l'inventario dei prodotti).</span><span class="sxs-lookup"><span data-stu-id="19809-104">Use custom counter instances to monitor aspects of the server not monitored by existing counters, such as components unique to your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database (for example, the number of customer orders logged or the product inventory).</span></span>  
  
 <span data-ttu-id="19809-105">L'oggetto **Definibile dall'utente** contiene 10 istanze del contatore di query: da **User counter 1** (Contatore utente 1) a **User counter 10** (Contatore utente 10).</span><span class="sxs-lookup"><span data-stu-id="19809-105">The **User Settable** object contains 10 instances of the query counter: **User counter 1** through **User counter 10**.</span></span> <span data-ttu-id="19809-106">Tali contatori corrispondono alle stored procedure di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da **sp_user_counter1** a **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="19809-106">These counters map to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures **sp_user_counter1** through **sp_user_counter10**.</span></span> <span data-ttu-id="19809-107">Quando le stored procedure vengono eseguite dalle applicazioni utente, i valori impostati dalle stored procedure vengono visualizzati in Monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="19809-107">As these stored procedures are executed by user applications, the values set by the stored procedures are displayed in System Monitor.</span></span> <span data-ttu-id="19809-108">Un contatore può monitorare qualsiasi valore integer, ad esempio una stored procedure che esegue il conteggio degli ordini di un prodotto specifico ricevuti in un giorno.</span><span class="sxs-lookup"><span data-stu-id="19809-108">A counter can monitor any single integer value (for example, a stored procedure that counts how many orders for a particular product have occurred in one day).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19809-109">Il polling delle stored procedure dei contatori utente non viene eseguito automaticamente da Monitoraggio di sistema.</span><span class="sxs-lookup"><span data-stu-id="19809-109">The user counter stored procedures are not polled automatically by System Monitor.</span></span> <span data-ttu-id="19809-110">Per aggiornare i valori dei contatori, è necessario che le stored procedure vengano eseguite in modo esplicito da un'applicazione utente.</span><span class="sxs-lookup"><span data-stu-id="19809-110">They must be explicitly executed by a user application for the counter values to be updated.</span></span> <span data-ttu-id="19809-111">Utilizzare un trigger per aggiornare automaticamente il valore del contatore.</span><span class="sxs-lookup"><span data-stu-id="19809-111">Use a trigger to update the value of the counter automatically.</span></span> <span data-ttu-id="19809-112">Ad esempio, per creare un contatore che esegue il monitoraggio del numero di righe di una tabella, creare un trigger INSERT e DELETE nella tabella per eseguire l'istruzione seguente: `SELECT COUNT(*) FROM table`.</span><span class="sxs-lookup"><span data-stu-id="19809-112">For example, to create a counter that monitors the number of rows in a table, create an INSERT and DELETE trigger on the table that executes the following statement: `SELECT COUNT(*) FROM table`.</span></span> <span data-ttu-id="19809-113">Ogni volta che il trigger viene attivato da un'operazione INSERT o DELETE eseguita nella tabella, il contatore di Monitoraggio di sistema viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="19809-113">Whenever the trigger is fired because of an INSERT or DELETE operation occurring on the table, the System Monitor counter is automatically updated.</span></span>  
  
 <span data-ttu-id="19809-114">Nella tabella seguente viene descritto l'oggetto **User Settable** di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19809-114">This table describes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **User Settable** object.</span></span>  
  
|<span data-ttu-id="19809-115">Contatori di SQLServer:Definibile dall'utente</span><span class="sxs-lookup"><span data-stu-id="19809-115">SQL Server User Settable counters</span></span>|<span data-ttu-id="19809-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19809-116">Description</span></span>|  
|---------------------------------------|-----------------|  
|<span data-ttu-id="19809-117">**Query**</span><span class="sxs-lookup"><span data-stu-id="19809-117">**Query**</span></span>|<span data-ttu-id="19809-118">L'oggetto **Definibile dall'utente** contiene il contatore di query.</span><span class="sxs-lookup"><span data-stu-id="19809-118">The **User Settable** object contains the query counter.</span></span> <span data-ttu-id="19809-119">Gli utenti configurano il valore delle istanze **User counter** all'interno dell'oggetto query.</span><span class="sxs-lookup"><span data-stu-id="19809-119">Users configure the **User counters** within the query object.</span></span>|  
  
 <span data-ttu-id="19809-120">Questa tabella illustra le **istanze** del contatore **Query** .</span><span class="sxs-lookup"><span data-stu-id="19809-120">This table describes the **instances** of the **Query** counter.</span></span>  
  
|<span data-ttu-id="19809-121">Istanze del contatore Query</span><span class="sxs-lookup"><span data-stu-id="19809-121">Query counter instances</span></span>|<span data-ttu-id="19809-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19809-122">Description</span></span>|  
|-----------------------------|-----------------|  
|<span data-ttu-id="19809-123">**User counter 1**</span><span class="sxs-lookup"><span data-stu-id="19809-123">**User counter 1**</span></span>|<span data-ttu-id="19809-124">Definito tramite **sp_user_counter1**.</span><span class="sxs-lookup"><span data-stu-id="19809-124">Defined using **sp_user_counter1**.</span></span>|  
|<span data-ttu-id="19809-125">**User counter 2**</span><span class="sxs-lookup"><span data-stu-id="19809-125">**User counter 2**</span></span>|<span data-ttu-id="19809-126">Definito tramite **sp_user_counter2**.</span><span class="sxs-lookup"><span data-stu-id="19809-126">Defined using **sp_user_counter2**.</span></span>|  
|<span data-ttu-id="19809-127">**User counter 3**</span><span class="sxs-lookup"><span data-stu-id="19809-127">**User counter 3**</span></span>|<span data-ttu-id="19809-128">Definito tramite **sp_user_counter3**.</span><span class="sxs-lookup"><span data-stu-id="19809-128">Defined using **sp_user_counter3**.</span></span>|  
|<span data-ttu-id="19809-129">...</span><span class="sxs-lookup"><span data-stu-id="19809-129">...</span></span>||  
|<span data-ttu-id="19809-130">**User counter 10**</span><span class="sxs-lookup"><span data-stu-id="19809-130">**User counter 10**</span></span>|<span data-ttu-id="19809-131">Definito tramite **sp_user_counter10**.</span><span class="sxs-lookup"><span data-stu-id="19809-131">Defined using **sp_user_counter10**.</span></span>|  
  
 <span data-ttu-id="19809-132">Per utilizzare le stored procedure dei contatori utente, eseguirle dall'applicazione utente con un solo parametro integer che rappresenta il nuovo valore del contatore.</span><span class="sxs-lookup"><span data-stu-id="19809-132">To make use of the user counter stored procedures, execute them from your own application with a single integer parameter representing the new value for the counter.</span></span> <span data-ttu-id="19809-133">Ad esempio, per impostare **User counter 1** sul valore 10, eseguire l'istruzione Transact-SQL seguente:</span><span class="sxs-lookup"><span data-stu-id="19809-133">For example, to set **User counter 1** to the value 10, execute this Transact-SQL statement:</span></span>  
  
```  
EXECUTE sp_user_counter1 10  
```  
  
 <span data-ttu-id="19809-134">Le stored procedure dei contatori utente possono essere chiamate da qualsiasi posizione da cui possono essere chiamate le altre stored procedure, ad esempio le stored procedure personalizzate.</span><span class="sxs-lookup"><span data-stu-id="19809-134">The user counter stored procedures can be called from anywhere other stored procedures can be called, such as your own stored procedures.</span></span> <span data-ttu-id="19809-135">Ad esempio, è possibile creare la stored procedure seguente per eseguire il conteggio del numero di connessioni e tentativi di connessione eseguiti dall'avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="19809-135">For example, you can create the following stored procedure to count the number of connections and attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was started:</span></span>  
  
```  
DROP PROC My_Proc  
GO  
CREATE PROC My_Proc  
AS   
   EXECUTE sp_user_counter1 @@CONNECTIONS  
GO  
```  
  
 <span data-ttu-id="19809-136">La funzione @@CONNECTIONS restituisce il numero di connessioni o di tentativi di connessione eseguiti dall'avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19809-136">The @@CONNECTIONS function returns the number of connections or attempted connections since an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] started.</span></span> <span data-ttu-id="19809-137">Il valore viene passato alla stored procedure **sp_user_counter1** come parametro.</span><span class="sxs-lookup"><span data-stu-id="19809-137">This value is passed to the **sp_user_counter1** stored procedure as the parameter.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="19809-138">Le query definite nelle stored procedure dei contatori utente dovrebbero essere il più semplici possibile.</span><span class="sxs-lookup"><span data-stu-id="19809-138">Make the queries defined in the user counter stored procedures as simple as possible.</span></span> <span data-ttu-id="19809-139">Le query che impegnano molta memoria e che eseguono operazioni di ordinamento e di hashing di ampia portata o le query che eseguono grandi quantità di operazioni di I/O richiedono l'utilizzo di numerose risorse e possono determinare un peggioramento delle prestazioni del sistema.</span><span class="sxs-lookup"><span data-stu-id="19809-139">Memory-intensive queries that perform substantial sort or hash operations or queries that perform large amounts of I/O are expensive to execute and can impact performance.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="19809-140">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="19809-140">Permissions</span></span>  
 <span data-ttu-id="19809-141">**sp_user_counter** è disponibile per tutti gli utenti, ma è possibile limitarne l'uso per qualsiasi contatore di query.</span><span class="sxs-lookup"><span data-stu-id="19809-141">**sp_user_counter** is available for all users but can be restricted for any query counter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19809-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19809-142">See Also</span></span>  
 [<span data-ttu-id="19809-143">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="19809-143">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
