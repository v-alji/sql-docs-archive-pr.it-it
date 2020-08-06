---
title: Database di sistema | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system databases [SQL Server]
- displaying system database data
- modifying system data
- viewing system database data
ms.assetid: 30468a7c-4225-4d35-aa4a-ffa7da4f1282
author: stevestein
ms.author: sstein
ms.openlocfilehash: 65deee685c2205a7c6e41ed86f71c69639555d7c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711991"
---
# <a name="system-databases"></a><span data-ttu-id="da8ac-102">Database di sistema.</span><span class="sxs-lookup"><span data-stu-id="da8ac-102">System Databases</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="da8ac-103">sono inclusi i database di sistema seguenti.</span><span class="sxs-lookup"><span data-stu-id="da8ac-103">includes the following system databases.</span></span>  
  
|<span data-ttu-id="da8ac-104">Database di sistema</span><span class="sxs-lookup"><span data-stu-id="da8ac-104">System database</span></span>|<span data-ttu-id="da8ac-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da8ac-105">Description</span></span>|  
|---------------------|-----------------|  
|[<span data-ttu-id="da8ac-106">Database master</span><span class="sxs-lookup"><span data-stu-id="da8ac-106">master Database</span></span>](master-database.md)|<span data-ttu-id="da8ac-107">Registra tutte le informazioni di sistema per un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da8ac-107">Records all the system-level information for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="da8ac-108">Database msdb</span><span class="sxs-lookup"><span data-stu-id="da8ac-108">msdb Database</span></span>](msdb-database.md)|<span data-ttu-id="da8ac-109">Utilizzato da SQL Server Agent per la pianificazione di avvisi e processi.</span><span class="sxs-lookup"><span data-stu-id="da8ac-109">Is used by SQL Server Agent for scheduling alerts and jobs.</span></span>|  
|[<span data-ttu-id="da8ac-110">Database model</span><span class="sxs-lookup"><span data-stu-id="da8ac-110">model Database</span></span>](model-database.md)|<span data-ttu-id="da8ac-111">Utilizzato come modello per tutti i database creati in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da8ac-111">Is used as the template for all databases created on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="da8ac-112">Le modifiche apportate al database **model** , ad esempio per quanto riguarda dimensioni, regole di confronto, modello di recupero e altre opzioni del database, vengono applicate a tutti i database creati successivamente.</span><span class="sxs-lookup"><span data-stu-id="da8ac-112">Modifications made to the **model** database, such as database size, collation, recovery model, and other database options, are applied to any databases created afterward.</span></span>|  
|[<span data-ttu-id="da8ac-113">Database Resource</span><span class="sxs-lookup"><span data-stu-id="da8ac-113">Resource Database</span></span>](resource-database.md)|<span data-ttu-id="da8ac-114">Database di sola lettura che contiene gli oggetti di sistema inclusi in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da8ac-114">Is a read-only database that contains system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="da8ac-115">Gli oggetti di sistema sono fisicamente mantenuti nel database **Resource** ma appaiono logicamente nello schema **sys** di ogni database.</span><span class="sxs-lookup"><span data-stu-id="da8ac-115">System objects are physically persisted in the **Resource** database, but they logically appear in the **sys** schema of every database.</span></span>|  
|[<span data-ttu-id="da8ac-116">Database tempdb</span><span class="sxs-lookup"><span data-stu-id="da8ac-116">tempdb Database</span></span>](tempdb-database.md)|<span data-ttu-id="da8ac-117">Area di lavoro per l'archiviazione di oggetti temporanei o set di risultati intermedi.</span><span class="sxs-lookup"><span data-stu-id="da8ac-117">Is a workspace for holding temporary objects or intermediate result sets.</span></span>|  
  
## <a name="modifying-system-data"></a><span data-ttu-id="da8ac-118">modifica dei dati di sistema</span><span class="sxs-lookup"><span data-stu-id="da8ac-118">Modifying System Data</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="da8ac-119">non supporta l'aggiornamento diretto delle informazioni da parte degli utenti in oggetti di sistema, ad esempio tabelle di sistema, stored procedure di sistema e viste del catalogo.</span><span class="sxs-lookup"><span data-stu-id="da8ac-119">does not support users directly updating the information in system objects such as system tables, system stored procedures, and catalog views.</span></span> <span data-ttu-id="da8ac-120">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] offre, tuttavia, un set completo di strumenti di amministrazione che consentono agli utenti di amministrare completamente il sistema e gestire tutti gli utenti e gli oggetti di un database.</span><span class="sxs-lookup"><span data-stu-id="da8ac-120">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a complete set of administrative tools that let users fully administer their system and manage all users and objects in a database.</span></span> <span data-ttu-id="da8ac-121">tra cui:</span><span class="sxs-lookup"><span data-stu-id="da8ac-121">These include the following:</span></span>  
  
-   <span data-ttu-id="da8ac-122">Utilità di amministrazione, ad esempio [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da8ac-122">Administration utilities, such as [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="da8ac-123">API SQL-SMO.</span><span class="sxs-lookup"><span data-stu-id="da8ac-123">SQL-SMO API.</span></span> <span data-ttu-id="da8ac-124">Consente ai programmatori di includere nelle proprie applicazioni funzionalità complete di amministrazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da8ac-124">This lets programmers include complete functionality for administering [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in their applications.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="da8ac-125">.</span><span class="sxs-lookup"><span data-stu-id="da8ac-125">scripts and stored procedures.</span></span> <span data-ttu-id="da8ac-126">Possono utilizzare stored procedure di sistema e istruzioni DDL [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da8ac-126">These can use system stored procedures and [!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statements.</span></span>  
  
 <span data-ttu-id="da8ac-127">Questi strumenti  proteggono le applicazioni dalle modifiche negli oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="da8ac-127">These tools shield applications from changes in the system objects.</span></span> <span data-ttu-id="da8ac-128">Talvolta, ad esempio, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve modificare le tabelle di sistema nelle nuove versioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per garantire il supporto per nuove funzionalità aggiunte alla versione.</span><span class="sxs-lookup"><span data-stu-id="da8ac-128">For example, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sometimes has to change the system tables in new versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to support new functionality that is being added in that version.</span></span> <span data-ttu-id="da8ac-129">Le applicazioni che eseguono istruzioni SELECT che fanno riferimento diretto alle tabelle di sistema spesso si basano sul formato precedente delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="da8ac-129">Applications issuing SELECT statements that directly reference system tables are frequently dependent on the old format of the system tables.</span></span> <span data-ttu-id="da8ac-130">Può capitare che, per eseguire l'aggiornamento a una nuova versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , le aziende debbano prima riscrivere le applicazioni che eseguono la selezione dalle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="da8ac-130">Sites may not be able to upgrade to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until they have rewritten applications that are selecting from system tables.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="da8ac-131">tratta stored procedure di sistema, DDL e SQL-SMO come interfacce pubblicate e fa il possibile per mantenerne la compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="da8ac-131">considers the system stored procedures, DDL, and SQL-SMO published interfaces, and works to maintain the backward compatibility of these interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="da8ac-132">non supporta i trigger definiti nelle tabelle di sistema, in quanto potrebbero modificare il funzionamento del sistema.</span><span class="sxs-lookup"><span data-stu-id="da8ac-132">does not support triggers defined on the system tables, because they might modify the operation of the system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da8ac-133">I database di sistema non possono trovarsi in directory di condivisione UNC.</span><span class="sxs-lookup"><span data-stu-id="da8ac-133">System databases cannot reside on UNC share directories.</span></span>  
  
## <a name="viewing-system-database-data"></a><span data-ttu-id="da8ac-134">visualizzazione dei dati di database di sistema</span><span class="sxs-lookup"><span data-stu-id="da8ac-134">Viewing System Database Data</span></span>  
 <span data-ttu-id="da8ac-135">È sconsigliabile definire istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] che eseguono query dirette sulle tabelle di sistema, a meno che non si tratti dell'unico modo per ottenere le informazioni richieste dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da8ac-135">You should not code [!INCLUDE[tsql](../../includes/tsql-md.md)] statements that directly query the system tables, unless that is the only way to obtain the information that is required by the application.</span></span> <span data-ttu-id="da8ac-136">Le applicazioni devono invece ottenere le informazioni di sistema e del catalogo utilizzando gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="da8ac-136">Instead, applications should obtain catalog and system information by using the following:</span></span>  
  
-   <span data-ttu-id="da8ac-137">Viste del catalogo di sistema</span><span class="sxs-lookup"><span data-stu-id="da8ac-137">System catalog views</span></span>  
  
-   <span data-ttu-id="da8ac-138">SQL-SMO</span><span class="sxs-lookup"><span data-stu-id="da8ac-138">SQL-SMO</span></span>  
  
-   <span data-ttu-id="da8ac-139">Interfaccia di Strumentazione gestione Windows (WMI, Windows Management Instrumentation)</span><span class="sxs-lookup"><span data-stu-id="da8ac-139">Windows Management Instrumentation (WMI) interface</span></span>  
  
-   <span data-ttu-id="da8ac-140">Funzioni, metodi, attributi o proprietà del catalogo dell'API dei dati utilizzata dall'applicazione, ad esempio ADO, OLE DB o ODBC</span><span class="sxs-lookup"><span data-stu-id="da8ac-140">Catalog functions, methods, attributes, or properties of the data API used in the application, such as ADO, OLE DB, or ODBC.</span></span>  
  
-   [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="da8ac-141">Funzioni predefinite e stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="da8ac-141">system stored procedures and built-in functions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="da8ac-142">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="da8ac-142">Related Tasks</span></span>  
 [<span data-ttu-id="da8ac-143">Backup e ripristino di database di sistema &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="da8ac-143">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="da8ac-144">Nascondi oggetti di sistema in Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="da8ac-144">Hide System Objects in Object Explorer</span></span>](../../ssms/object/object-explorer.md)  
  
## <a name="related-content"></a><span data-ttu-id="da8ac-145">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="da8ac-145">Related Content</span></span>  
 [<span data-ttu-id="da8ac-146">Viste del catalogo &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="da8ac-146">Catalog Views &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/catalog-views-transact-sql)  
  
 [<span data-ttu-id="da8ac-147">Database</span><span class="sxs-lookup"><span data-stu-id="da8ac-147">Databases</span></span>](databases.md)  
  
  
