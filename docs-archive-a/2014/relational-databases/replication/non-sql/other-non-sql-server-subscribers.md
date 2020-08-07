---
title: Altri Sottoscrittori non SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- non-SQL Server Subscribers, other types
ms.assetid: 96b8beb9-38e8-4ce4-97ca-c0f8656b73b4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3849ca717e82bcf1bed5769190c9f898209a454a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623152"
---
# <a name="other-non-sql-server-subscribers"></a><span data-ttu-id="ef154-102">Altri Sottoscrittori non SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef154-102">Other Non-SQL Server Subscribers</span></span>
  <span data-ttu-id="ef154-103">Per un elenco di Sottoscrittori non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supportati da [!INCLUDE[msCoName](../../../includes/msconame-md.md)], vedere [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="ef154-103">For a list of non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers supported by [!INCLUDE[msCoName](../../../includes/msconame-md.md)], see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span> <span data-ttu-id="ef154-104">In questo argomento vengono fornite informazioni sui requisiti per i driver ODBC e i provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="ef154-104">This topic includes information about requirements for ODBC drivers and OLE DB providers.</span></span>  
  
## <a name="odbc-driver-requirements"></a><span data-ttu-id="ef154-105">Requisiti per i driver ODBC</span><span class="sxs-lookup"><span data-stu-id="ef154-105">ODBC Driver Requirements</span></span>  
 <span data-ttu-id="ef154-106">Il driver ODBC deve soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef154-106">The ODBC driver:</span></span>  
  
-   <span data-ttu-id="ef154-107">Deve essere conforme a ODBC di livello 1.</span><span class="sxs-lookup"><span data-stu-id="ef154-107">Must be ODBC level-1 compliant.</span></span>  
  
-   <span data-ttu-id="ef154-108">Deve essere affidabile e compatibile con l'architettura del processore, Intel o Alpha, e con la piattaforma, a 32 o a 64 bit, in cui è in esecuzione il server di distribuzione [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ef154-108">Must be thread-safe, and for the processor architecture (Intel or Alpha) and platform (32 bit or 64 bit) on which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor runs.</span></span>  
  
-   <span data-ttu-id="ef154-109">Deve essere in grado di eseguire transazioni.</span><span class="sxs-lookup"><span data-stu-id="ef154-109">Must be transaction capable.</span></span>  
  
-   <span data-ttu-id="ef154-110">Deve supportare il linguaggio DDL (Data Definition Language).</span><span class="sxs-lookup"><span data-stu-id="ef154-110">Must support the Data Definition Language (DDL).</span></span>  
  
-   <span data-ttu-id="ef154-111">Non può essere di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="ef154-111">Cannot be read-only.</span></span>  
  
-   <span data-ttu-id="ef154-112">Deve supportare nomi di tabella lunghi, ad esempio **MSreplication_subscriptions**.</span><span class="sxs-lookup"><span data-stu-id="ef154-112">Must support long table names such as **MSreplication_subscriptions**.</span></span>  
  
## <a name="replicating-using-ole-db-interfaces"></a><span data-ttu-id="ef154-113">Esecuzione della replica tramite interfacce OLE DB</span><span class="sxs-lookup"><span data-stu-id="ef154-113">Replicating Using OLE DB Interfaces</span></span>  
 <span data-ttu-id="ef154-114">Per la replica transazionale i provider OLE DB devono supportare gli oggetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef154-114">OLE DB providers must support these objects for transactional replication:</span></span>  
  
-   <span data-ttu-id="ef154-115">**DataSource**</span><span class="sxs-lookup"><span data-stu-id="ef154-115">**DataSource** object</span></span>  
  
-   <span data-ttu-id="ef154-116">**Session**</span><span class="sxs-lookup"><span data-stu-id="ef154-116">**Session** object</span></span>  
  
-   <span data-ttu-id="ef154-117">**Command**</span><span class="sxs-lookup"><span data-stu-id="ef154-117">**Command** object</span></span>  
  
-   <span data-ttu-id="ef154-118">**Rowset**</span><span class="sxs-lookup"><span data-stu-id="ef154-118">**Rowset** object</span></span>  
  
-   <span data-ttu-id="ef154-119">**Error**</span><span class="sxs-lookup"><span data-stu-id="ef154-119">**Error** object</span></span>  
  
### <a name="datasource-object-interfaces"></a><span data-ttu-id="ef154-120">Interfacce per oggetti DataSource</span><span class="sxs-lookup"><span data-stu-id="ef154-120">DataSource Object Interfaces</span></span>  
 <span data-ttu-id="ef154-121">Per la connessione a un'origine dei dati sono necessarie le interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef154-121">The following interfaces are required to connect to a data source:</span></span>  
  
-   `IDBInitialize`  
  
-   `IDBCreateSession`  
  
-   `IDBProperties`  
  
 <span data-ttu-id="ef154-122">Se il provider supporta l'interfaccia **IDBInfo**, che viene usata in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per il recupero di informazioni quali l'identificatore tra virgolette, la lunghezza massima delle istruzioni SQL e il numero massimo di caratteri nei nomi di colonne e tabelle.</span><span class="sxs-lookup"><span data-stu-id="ef154-122">If the provider supports the **IDBInfo** interface, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses the interface to retrieve information such as the quoted identifier character, maximum SQL statement length, and maximum number of characters in table and column names.</span></span>  
  
### <a name="session-object-interfaces"></a><span data-ttu-id="ef154-123">Interfacce per oggetti Session</span><span class="sxs-lookup"><span data-stu-id="ef154-123">Session Object Interfaces</span></span>  
 <span data-ttu-id="ef154-124">Sono necessarie le interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef154-124">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="ef154-125">**IDBCreateCommand**</span><span class="sxs-lookup"><span data-stu-id="ef154-125">**IDBCreateCommand**</span></span>  
  
-   <span data-ttu-id="ef154-126">**ITransaction**</span><span class="sxs-lookup"><span data-stu-id="ef154-126">**ITransaction**</span></span>  
  
-   <span data-ttu-id="ef154-127">**ITransactionLocal**</span><span class="sxs-lookup"><span data-stu-id="ef154-127">**ITransactionLocal**</span></span>  
  
-   <span data-ttu-id="ef154-128">**IDBSchemaRowset**</span><span class="sxs-lookup"><span data-stu-id="ef154-128">**IDBSchemaRowset**</span></span>  
  
### <a name="command-object-interfaces"></a><span data-ttu-id="ef154-129">Interfacce per oggetti Command</span><span class="sxs-lookup"><span data-stu-id="ef154-129">Command Object Interfaces</span></span>  
 <span data-ttu-id="ef154-130">Sono necessarie le interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef154-130">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="ef154-131">**ICommand**</span><span class="sxs-lookup"><span data-stu-id="ef154-131">**ICommand**</span></span>  
  
-   <span data-ttu-id="ef154-132">**ICommandProperties**</span><span class="sxs-lookup"><span data-stu-id="ef154-132">**ICommandProperties**</span></span>  
  
-   <span data-ttu-id="ef154-133">**ICommandText**</span><span class="sxs-lookup"><span data-stu-id="ef154-133">**ICommandText**</span></span>  
  
-   <span data-ttu-id="ef154-134">**ICommandPrepare**</span><span class="sxs-lookup"><span data-stu-id="ef154-134">**ICommandPrepare**</span></span>  
  
-   <span data-ttu-id="ef154-135">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="ef154-135">**IColumnsInfo**</span></span>  
  
-   <span data-ttu-id="ef154-136">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="ef154-136">**IAccessor**</span></span>  
  
-   <span data-ttu-id="ef154-137">**ICommandWithParameters**</span><span class="sxs-lookup"><span data-stu-id="ef154-137">**ICommandWithParameters**</span></span>  
  
 <span data-ttu-id="ef154-138">L'interfaccia**IAccessor** è necessaria per la creazione di funzioni di accesso ai parametri.</span><span class="sxs-lookup"><span data-stu-id="ef154-138">**IAccessor** is necessary to create parameter accessors.</span></span> <span data-ttu-id="ef154-139">Se il provider supporta **interfaccia IColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizza tale interfaccia per determinare se una colonna è una colonna Identity.</span><span class="sxs-lookup"><span data-stu-id="ef154-139">If the provider supports **IColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses that interface to determine whether a column is an identity column.</span></span>  
  
### <a name="rowset-object-interfaces"></a><span data-ttu-id="ef154-140">Interfacce per oggetti Rowset</span><span class="sxs-lookup"><span data-stu-id="ef154-140">Rowset Object Interfaces</span></span>  
 <span data-ttu-id="ef154-141">Sono necessarie le interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef154-141">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="ef154-142">**IRowset**</span><span class="sxs-lookup"><span data-stu-id="ef154-142">**IRowset**</span></span>  
  
-   <span data-ttu-id="ef154-143">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="ef154-143">**IAccessor**</span></span>  
  
-   <span data-ttu-id="ef154-144">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="ef154-144">**IColumnsInfo**</span></span>  
  
 <span data-ttu-id="ef154-145">In un'applicazione può essere necessario aprire un set di righe di una tabella replicata creata nel database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="ef154-145">An application should open a rowset on a replicated table that is created in the subscription database.</span></span> <span data-ttu-id="ef154-146">Le interfacce**IColumnsInfo** e **IAccessor** consentono di accedere ai dati del set di righe.</span><span class="sxs-lookup"><span data-stu-id="ef154-146">**IColumnsInfo** and **IAccessor** are needed to access data in the rowset.</span></span>  
  
### <a name="error-object-interfaces"></a><span data-ttu-id="ef154-147">Interfacce per oggetti Error</span><span class="sxs-lookup"><span data-stu-id="ef154-147">Error Object Interfaces</span></span>  
 <span data-ttu-id="ef154-148">Per la gestione degli errori, utilizzare le interfacce seguenti:</span><span class="sxs-lookup"><span data-stu-id="ef154-148">Use the following interfaces to manage errors:</span></span>  
  
-   <span data-ttu-id="ef154-149">**IErrorRecords**</span><span class="sxs-lookup"><span data-stu-id="ef154-149">**IErrorRecords**</span></span>  
  
-   <span data-ttu-id="ef154-150">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="ef154-150">**IErrorInfo**</span></span>  
  
 <span data-ttu-id="ef154-151">Utilizzare l'interfaccia **ISQLErrorInfo** se è supportata dal provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="ef154-151">Use **ISQLErrorInfo** if it is supported by the OLE DB provider.</span></span>  
  
 <span data-ttu-id="ef154-152">Per ulteriori informazioni sul provider OLE DB, vedere la relativa documentazione.</span><span class="sxs-lookup"><span data-stu-id="ef154-152">For more information about the OLE DB provider, see the documentation supplied with your OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef154-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef154-153">See Also</span></span>  
 [<span data-ttu-id="ef154-154">Sottoscrittori non SQL Server</span><span class="sxs-lookup"><span data-stu-id="ef154-154">Non-SQL Server Subscribers</span></span>](non-sql-server-subscribers.md)  
  
  
