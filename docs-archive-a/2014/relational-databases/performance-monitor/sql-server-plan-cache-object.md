---
title: Oggetto Plan Cache di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Plan Cache object
- SQLServer:Plan Cache
ms.assetid: 225e2b02-8d2f-4f29-9eba-f5847c36ea99
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 002cbe261c531c18bdbb2170da9694cc8abde89d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713084"
---
# <a name="sql-server-plan-cache-object"></a><span data-ttu-id="21080-102">Oggetto Plan Cache di SQL Server</span><span class="sxs-lookup"><span data-stu-id="21080-102">SQL Server, Plan Cache Object</span></span>
  <span data-ttu-id="21080-103">L'oggetto **Plan Cache** include contatori che consentono di monitorare il modo in cui [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa la memoria per archiviare oggetti quali stored procedure, istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc e preparate e trigger.</span><span class="sxs-lookup"><span data-stu-id="21080-103">The **Plan Cache** object provides counters to monitor how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses memory to store objects such as stored procedures, ad hoc and prepared [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, and triggers.</span></span> <span data-ttu-id="21080-104">È possibile monitorare contemporaneamente più istanze dell'oggetto **Plan Cache** , che rappresentano diversi tipi di piani da monitorare.</span><span class="sxs-lookup"><span data-stu-id="21080-104">Multiple instances of the **Plan Cache** object can be monitored at the same time, with each instance representing a different type of plan to monitor.</span></span>  
  
 <span data-ttu-id="21080-105">Nella tabella seguente sono descritti i contatori **SQLServer:Plan Cache**.</span><span class="sxs-lookup"><span data-stu-id="21080-105">This table describes are the **SQLServer:Plan Cache**counters.</span></span>  
  
|<span data-ttu-id="21080-106">Contatori di Plan Cache di SQL Server</span><span class="sxs-lookup"><span data-stu-id="21080-106">SQL Server Plan Cache counters</span></span>|<span data-ttu-id="21080-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21080-107">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="21080-108">**Percentuale riscontri cache**</span><span class="sxs-lookup"><span data-stu-id="21080-108">**Cache Hit Ratio**</span></span>|<span data-ttu-id="21080-109">Rapporto tra riscontri e ricerche nella cache.</span><span class="sxs-lookup"><span data-stu-id="21080-109">Ratio between cache hits and lookups.</span></span>|  
|<span data-ttu-id="21080-110">**Numero oggetti nella cache**</span><span class="sxs-lookup"><span data-stu-id="21080-110">**Cache Object Counts**</span></span>|<span data-ttu-id="21080-111">Numero di oggetti disponibili nella cache.</span><span class="sxs-lookup"><span data-stu-id="21080-111">Number of cache objects in the cache.</span></span>|  
|<span data-ttu-id="21080-112">**Pagine cache**</span><span class="sxs-lookup"><span data-stu-id="21080-112">**Cache Pages**</span></span>|<span data-ttu-id="21080-113">Numero di pagine da 8 KB usate dagli oggetti della cache.</span><span class="sxs-lookup"><span data-stu-id="21080-113">Number of 8-kilobyte (KB) pages used by cache objects.</span></span>|  
|<span data-ttu-id="21080-114">**Oggetti cache in uso**</span><span class="sxs-lookup"><span data-stu-id="21080-114">**Cache Objects in use**</span></span>|<span data-ttu-id="21080-115">Numero di oggetti della cache in uso.</span><span class="sxs-lookup"><span data-stu-id="21080-115">Number of cache objects in use.</span></span>|  
  
 <span data-ttu-id="21080-116">Per ogni contatore nell'oggetto sono disponibili le istanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="21080-116">Each counter in the object contains the following instances:</span></span>  
  
|<span data-ttu-id="21080-117">Istanza di Plan Cache</span><span class="sxs-lookup"><span data-stu-id="21080-117">Plan Cache instance</span></span>|<span data-ttu-id="21080-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21080-118">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="21080-119">**_Total**</span><span class="sxs-lookup"><span data-stu-id="21080-119">**_Total**</span></span>|<span data-ttu-id="21080-120">Informazioni relative a tutti i tipi di istanze della cache.</span><span class="sxs-lookup"><span data-stu-id="21080-120">Information for all types of cache instances.</span></span>|  
|<span data-ttu-id="21080-121">**Piani SQL**</span><span class="sxs-lookup"><span data-stu-id="21080-121">**Sql Plans**</span></span>|<span data-ttu-id="21080-122">Piani di query prodotti da una query [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc, incluse le query con parametri automatici, oppure da istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] preparate tramite **sp_prepare** o **sp_cursorprepare**.</span><span class="sxs-lookup"><span data-stu-id="21080-122">Query plans produced from an ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] query, including auto-parameterized queries, or from [!INCLUDE[tsql](../../includes/tsql-md.md)] statements prepared using **sp_prepare** or **sp_cursorprepare**.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="21080-123">memorizza nella cache i piani delle istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] ad hoc per poterli riusare nel caso venga rieseguita la stessa istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="21080-123">caches the plans for ad hoc [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for later reuse if the identical [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is later executed.</span></span> <span data-ttu-id="21080-124">Anche le query con parametri dell'utente, sebbene non siano state preparate esplicitamente, vengono monitorate come piani SQL preparati.</span><span class="sxs-lookup"><span data-stu-id="21080-124">User-parameterized queries (even if not explicitly prepared) are also monitored as Prepared SQL Plans.</span></span>|  
|<span data-ttu-id="21080-125">**Piani per gli oggetti**</span><span class="sxs-lookup"><span data-stu-id="21080-125">**Object Plans**</span></span>|<span data-ttu-id="21080-126">Piani di query generati creando una stored procedure, una funzione o un trigger.</span><span class="sxs-lookup"><span data-stu-id="21080-126">Query plans generated by creating a stored procedure, function, or trigger.</span></span>|  
|<span data-ttu-id="21080-127">**Alberi associati**</span><span class="sxs-lookup"><span data-stu-id="21080-127">**Bound Trees**</span></span>|<span data-ttu-id="21080-128">Alberi normalizzati per viste, regole, colonne calcolate e vincoli CHECK.</span><span class="sxs-lookup"><span data-stu-id="21080-128">Normalized trees for views, rules, computed columns, and check constraints.</span></span>|  
|<span data-ttu-id="21080-129">**Stored procedure estese**</span><span class="sxs-lookup"><span data-stu-id="21080-129">**Extended Stored Procedures**</span></span>|<span data-ttu-id="21080-130">Informazioni di catalogo relative alle stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="21080-130">Catalog information for extended stores procedures.</span></span>|  
|<span data-ttu-id="21080-131">**Tabelle temporanee e variabili tabella**</span><span class="sxs-lookup"><span data-stu-id="21080-131">**Temporary Tables & Table Variables**</span></span>|<span data-ttu-id="21080-132">Informazioni della cache relative a tabelle temporanee e variabili tabella.</span><span class="sxs-lookup"><span data-stu-id="21080-132">Cache information related to temporary tables and table variables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21080-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21080-133">See Also</span></span>  
 <span data-ttu-id="21080-134">[Opzioni di configurazione del server Server Memory](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="21080-134">[Server Memory Server Configuration Options](../../database-engine/configure-windows/server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="21080-135">[Oggetto di Gestione buffer di SQL Server](sql-server-buffer-manager-object.md) </span><span class="sxs-lookup"><span data-stu-id="21080-135">[SQL Server, Buffer Manager Object](sql-server-buffer-manager-object.md) </span></span>  
 [<span data-ttu-id="21080-136">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="21080-136">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](monitor-resource-usage-system-monitor.md)  
  
  
