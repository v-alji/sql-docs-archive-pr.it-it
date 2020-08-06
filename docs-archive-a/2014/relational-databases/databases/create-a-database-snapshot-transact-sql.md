---
title: Creare uno snapshot del database (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], creating
ms.assetid: 187fbba3-c555-4030-9bdf-0f01994c5230
author: stevestein
ms.author: sstein
ms.openlocfilehash: bae68c2d507e1dd3809e76a9d842b765d72234e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725904"
---
# <a name="create-a-database-snapshot-transact-sql"></a><span data-ttu-id="45273-102">Creare uno snapshot del database (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="45273-102">Create a Database Snapshot (Transact-SQL)</span></span>
  <span data-ttu-id="45273-103">L'unico modo per creare uno snapshot del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è utilizzando [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45273-103">The only way to create a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database snapshot is to use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="45273-104">non supporta la creazione di snapshot del database.</span><span class="sxs-lookup"><span data-stu-id="45273-104">does not support the creation of database snapshots.</span></span>  
  
-   <span data-ttu-id="45273-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="45273-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="45273-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="45273-106">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="45273-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="45273-107">Security</span></span>](#Security)  
  
     [<span data-ttu-id="45273-108">Procedura consigliata: Denominazione degli snapshot del database</span><span class="sxs-lookup"><span data-stu-id="45273-108">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   <span data-ttu-id="45273-109">**Per creare uno snapshot del database tramite:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="45273-109">**To create a database snapshot, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="45273-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="45273-110">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="45273-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="45273-111">Prerequisites</span></span>  
 <span data-ttu-id="45273-112">Il database di origine, in cui può essere utilizzato qualsiasi modello di recupero, deve soddisfare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="45273-112">The source database, which can use any recovery model, must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="45273-113">L'istanza del server deve essere in esecuzione in un'edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che supporta gli snapshot del database.</span><span class="sxs-lookup"><span data-stu-id="45273-113">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports database snapshot.</span></span> <span data-ttu-id="45273-114">Per informazioni sul supporto per gli snapshot del database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , vedere [funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="45273-114">For information about support for database snapshots in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="45273-115">Il database di origine deve essere online, a meno che non si tratti di un database mirror nell'ambito di una sessione di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="45273-115">The source database must be online, unless the database is a mirror database within a database mirroring session.</span></span>  
  
-   <span data-ttu-id="45273-116">Per creare uno snapshot del database in un database mirror, è necessario che il database si trovi nello[stato di mirroring](../../database-engine/database-mirroring/mirroring-states-sql-server.md)sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="45273-116">To create a database snapshot on a mirror database, the database must be in the synchronized[mirroring state](../../database-engine/database-mirroring/mirroring-states-sql-server.md).</span></span>  
  
-   <span data-ttu-id="45273-117">Non è possibile configurare il database di origine come un database condiviso scalabile.</span><span class="sxs-lookup"><span data-stu-id="45273-117">The source database cannot be configured as a scalable shared database.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="45273-118">Per informazioni relative ad altre considerazioni rilevanti, vedere [Snapshot del database &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="45273-118">For information about other significant considerations, see [Database Snapshots &#40;SQL Server&#41;](database-snapshots-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="45273-119">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="45273-119">Recommendations</span></span>  
 <span data-ttu-id="45273-120">In questa sezione vengono illustrate le procedure consigliate seguenti:</span><span class="sxs-lookup"><span data-stu-id="45273-120">This section discusses the following best practices:</span></span>  
  
-   [<span data-ttu-id="45273-121">Procedura consigliata: Denominazione degli snapshot del database</span><span class="sxs-lookup"><span data-stu-id="45273-121">Best Practice: Naming Database Snapshots</span></span>](#Naming)  
  
-   [<span data-ttu-id="45273-122">Procedura consigliata: Limitazione del numero di snapshot del database</span><span class="sxs-lookup"><span data-stu-id="45273-122">Best Practice: Limiting the Number of Database Snapshots</span></span>](#Limiting_Number)  
  
-   [<span data-ttu-id="45273-123">Procedura consigliata: Connessioni client a uno snapshot del database</span><span class="sxs-lookup"><span data-stu-id="45273-123">Best Practice: Client Connections to a Database Snapshot</span></span>](#Client_Connections)  
  
####  <a name="best-practice-naming-database-snapshots"></a><a name="Naming"></a> <span data-ttu-id="45273-124">Procedura consigliata: Denominazione degli snapshot del database</span><span class="sxs-lookup"><span data-stu-id="45273-124">Best Practice: Naming Database Snapshots</span></span>  
 <span data-ttu-id="45273-125">Prima di creare gli snapshot è importante considerare il nome da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="45273-125">Before creating snapshots, it is important to consider how to name them.</span></span> <span data-ttu-id="45273-126">Ogni snapshot del database richiede un nome di database univoco.</span><span class="sxs-lookup"><span data-stu-id="45273-126">Each database snapshot requires a unique database name.</span></span> <span data-ttu-id="45273-127">Per semplificare l'amministrazione, il nome di uno snapshot può contenere informazioni utili a identificare il database, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="45273-127">For administrative ease, the name of a snapshot can incorporate information that identifies the database, such as:</span></span>  
  
-   <span data-ttu-id="45273-128">Nome del database di origine.</span><span class="sxs-lookup"><span data-stu-id="45273-128">The name of the source database.</span></span>  
  
-   <span data-ttu-id="45273-129">Indicazione che si tratta di uno snapshot.</span><span class="sxs-lookup"><span data-stu-id="45273-129">An indication that the new name is for a snapshot.</span></span>  
  
-   <span data-ttu-id="45273-130">Data e ora di creazione dello snapshot, un numero di sequenza o altre informazioni utili a distinguere gli snapshot sequenziali su un determinato database.</span><span class="sxs-lookup"><span data-stu-id="45273-130">The creation date and time of the snapshot, a sequence number, or some other information, such as time of day, to distinguish sequential snapshots on a given database.</span></span>  
  
 <span data-ttu-id="45273-131">Si consideri ad esempio una serie di snapshot del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="45273-131">For example, consider a series of snapshots for the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="45273-132">Ogni giorno fra le 6 e le 18 vengono creati tre snapshot, a intervalli di 6 ore,</span><span class="sxs-lookup"><span data-stu-id="45273-132">Three daily snapshots are created at 6-hour intervals between 6 A.M.</span></span> <span data-ttu-id="45273-133">su un ciclo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="45273-133">and 6 P.M., based on a 24-hour clock.</span></span> <span data-ttu-id="45273-134">Ogni snapshot viene mantenuto per 24 ore prima di essere eliminato e sostituito da un nuovo snapshot con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="45273-134">Each daily snapshot is kept for 24 hours before being dropped and replaced by a new snapshot of the same name.</span></span> <span data-ttu-id="45273-135">Si noti che il nome di ogni snapshot indica l'ora, ma non il giorno:</span><span class="sxs-lookup"><span data-stu-id="45273-135">Note that each snapshot name indicates the hour, but not the day:</span></span>  
  
```  
AdventureWorks_snapshot_0600  
AdventureWorks_snapshot_1200  
AdventureWorks_snapshot_1800  
```  
  
 <span data-ttu-id="45273-136">In alternativa, se l'orario di creazione di questi snapshot giornalieri cambia da un giorno all'altro, può essere preferibile una convenzione di denominazione più generica, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="45273-136">Alternatively, if the creation time of these daily snapshots varies from day to day, a less precise naming convention might be preferable, for example:</span></span>  
  
```  
AdventureWorks_snapshot_morning  
AdventureWorks_snapshot_noon  
AdventureWorks_snapshot_evening  
```  
  
####  <a name="best-practice-limiting-the-number-of-database-snapshots"></a><a name="Limiting_Number"></a> <span data-ttu-id="45273-137">Procedura consigliata: Limitazione del numero di snapshot del database</span><span class="sxs-lookup"><span data-stu-id="45273-137">Best Practice: Limiting the Number of Database Snapshots</span></span>  
 <span data-ttu-id="45273-138">Creando una serie di snapshot a intervalli di tempo si acquisiscono snapshot sequenziali del database di origine.</span><span class="sxs-lookup"><span data-stu-id="45273-138">Creating a series of snapshots over time captures sequential snapshots of the source database.</span></span> <span data-ttu-id="45273-139">Ogni snapshot viene mantenuto finché non viene esplicitamente eliminato.</span><span class="sxs-lookup"><span data-stu-id="45273-139">Each snapshot persists until it is explicitly dropped.</span></span> <span data-ttu-id="45273-140">Poiché ogni snapshot continua a crescere man mano che le pagine originali vengono aggiornate, per conservare spazio su disco è consigliabile eliminare un vecchio snapshot prima di crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="45273-140">Because each snapshot will continue to grow as original pages are updated, you may want to conserve disk space by deleting an older snapshot after creating a new snapshot.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45273-141">Se si desidera ripristinare uno snapshot del database è necessario eliminare tutti gli altri snapshot dal database.</span><span class="sxs-lookup"><span data-stu-id="45273-141">If you want to revert to a database snapshot, you need to delete any other snapshots from that database.</span></span>  
  
####  <a name="best-practice-client-connections-to-a-database-snapshot"></a><a name="Client_Connections"></a> <span data-ttu-id="45273-142">Procedura consigliata: Connessioni client a uno snapshot del database</span><span class="sxs-lookup"><span data-stu-id="45273-142">Best Practice: Client Connections to a Database Snapshot</span></span>  
 <span data-ttu-id="45273-143">Per utilizzare uno snapshot del database, i client devono sapere dove reperirlo.</span><span class="sxs-lookup"><span data-stu-id="45273-143">To use a database snapshot, clients need to know where to find it.</span></span> <span data-ttu-id="45273-144">Gli utenti possono leggere da uno snapshot del database durante la creazione o l'eliminazione di un altro snapshot.</span><span class="sxs-lookup"><span data-stu-id="45273-144">Users can read from one database snapshot while another is being created or deleted.</span></span> <span data-ttu-id="45273-145">Quando si sostituisce uno snapshot esistente con un nuovo snapshot, tuttavia, è necessario reindirizzare i client al nuovo snapshot.</span><span class="sxs-lookup"><span data-stu-id="45273-145">However, when you substitute a new snapshot for an existing one, you need to redirect clients to the new snapshot.</span></span> <span data-ttu-id="45273-146">Gli utenti possono connettersi manualmente a uno snapshot del database tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="45273-146">Users can manually connect to a database snapshot by means of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="45273-147">Per supportare un ambiente di produzione, è tuttavia consigliabile creare una soluzione a livello di programmazione che indirizzi in modo trasparente i client che scrivono report all'ultimo snapshot del database.</span><span class="sxs-lookup"><span data-stu-id="45273-147">However, to support a production environment, you should create a programmatic solution that transparently directs report-writing clients to the latest database snapshot of the database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="45273-148">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="45273-148">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="45273-149">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="45273-149">Permissions</span></span>  
 <span data-ttu-id="45273-150">Se un utente può creare un database, può creare anche uno snapshot del database; tuttavia, per creare uno snapshot di un database mirror, è necessario essere membro del ruolo del server predefinito **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="45273-150">Any user who can create a database can create a database snapshot; however, to create a snapshot of a mirror database, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="how-to-create-a-database-snapshot-using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="45273-151">Come creare uno snapshot del database utilizzando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="45273-151">How to Create a Database Snapshot (Using Transact-SQL)</span></span>  
 <span data-ttu-id="45273-152">**Per creare uno snapshot del database**</span><span class="sxs-lookup"><span data-stu-id="45273-152">**To create a database snapshot**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45273-153">Per un esempio di questa procedura, vedere [Esempi (Transact-SQL)](#TsqlExample)più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="45273-153">For an example of this procedure, see [Examples (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="45273-154">In base alla dimensione attuale del database di origine, assicurarsi che lo spazio su disco sia sufficiente per lo snapshot del database.</span><span class="sxs-lookup"><span data-stu-id="45273-154">Based on the current size of the source database, ensure that you have sufficient disk space to hold the database snapshot.</span></span> <span data-ttu-id="45273-155">La dimensione massima di uno snapshot del database corrisponde alla dimensione del database di origine al momento della creazione dello snapshot.</span><span class="sxs-lookup"><span data-stu-id="45273-155">The maximum size of a database snapshot is the size of the source database at snapshot creation.</span></span> <span data-ttu-id="45273-156">Per altre informazioni, vedere [Visualizzare le dimensioni del file sparse di uno snapshot del database &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="45273-156">For more information, see [View the Size of the Sparse File of a Database Snapshot &#40;Transact-SQL&#41;](view-the-size-of-the-sparse-file-of-a-database-snapshot-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="45273-157">Generare un'istruzione CREATE DATABASE sui file che utilizzano la clausola AS SNAPSHOT OF.</span><span class="sxs-lookup"><span data-stu-id="45273-157">Issue a CREATE DATABASE statement on the files using the AS SNAPSHOT OF clause.</span></span> <span data-ttu-id="45273-158">Per creare uno snapshot, è necessario specificare il nome logico di ogni file di database del database di origine.</span><span class="sxs-lookup"><span data-stu-id="45273-158">Creating a snapshot requires specifying the logical name of every database file of the source database.</span></span> <span data-ttu-id="45273-159">La sintassi è la seguente:</span><span class="sxs-lookup"><span data-stu-id="45273-159">The syntax is as follows:</span></span>  
  
     <span data-ttu-id="45273-160">CREATE DATABASE *database_snapshot_name*</span><span class="sxs-lookup"><span data-stu-id="45273-160">CREATE DATABASE *database_snapshot_name*</span></span>  
  
     <span data-ttu-id="45273-161">ON</span><span class="sxs-lookup"><span data-stu-id="45273-161">ON</span></span>  
  
     <span data-ttu-id="45273-162">(</span><span class="sxs-lookup"><span data-stu-id="45273-162">(</span></span>  
  
     <span data-ttu-id="45273-163">NAME =*logical_file_name*,</span><span class="sxs-lookup"><span data-stu-id="45273-163">NAME =*logical_file_name*,</span></span>  
  
     <span data-ttu-id="45273-164">FILENAME ='*os_file_name*'</span><span class="sxs-lookup"><span data-stu-id="45273-164">FILENAME ='*os_file_name*'</span></span>  
  
     <span data-ttu-id="45273-165">) [ ,...*n* ]</span><span class="sxs-lookup"><span data-stu-id="45273-165">) [ ,...*n* ]</span></span>  
  
     <span data-ttu-id="45273-166">AS SNAPSHOT OF *source_database_name*</span><span class="sxs-lookup"><span data-stu-id="45273-166">AS SNAPSHOT OF *source_database_name*</span></span>  
  
     <span data-ttu-id="45273-167">[;]</span><span class="sxs-lookup"><span data-stu-id="45273-167">[;]</span></span>  
  
     <span data-ttu-id="45273-168">Dove *source_\*\*database_name* è il database di origine, *logical_file_name* è il nome logico usato in SQL Server quando si fa riferimento al file, *os_file_name* rappresenta il nome e il percorso usati dal sistema operativo quando si crea il file e *database_snapshot_name* è il nome dello snapshot in base a cui si vuole ripristinare il database.</span><span class="sxs-lookup"><span data-stu-id="45273-168">Where *source_\*\*database_name* is the source database, *logical_file_name i*s the logical name used in SQL Server when referencing the file, *os_file_name* is the path and file name used by the operating system when you create the file, and *database_snapshot_name* is the name of the snapshot to which you want to revert the database.</span></span> <span data-ttu-id="45273-169">Per una descrizione completa di questa sintassi, vedere [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="45273-169">For a full description of this syntax, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="45273-170">Quando si crea uno snapshot del database, i file di log, i file offline, i file in fase di ripristino e i file inattivi non sono consentiti nell'istruzione CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="45273-170">When you create a database snapshot, log files, offline files, restoring files, and defunct files are not allowed in the CREATE DATABASE statement.</span></span>  
  
###  <a name="examples-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="45273-171">Esempi (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="45273-171">Examples (Transact-SQL)</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45273-172">L'estensione `.ss` utilizzata negli esempi è arbitraria.</span><span class="sxs-lookup"><span data-stu-id="45273-172">The `.ss` extension used in the examples is arbitrary.</span></span>  
  
 <span data-ttu-id="45273-173">Questa sezione contiene gli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="45273-173">This section contains the following examples:</span></span>  
  
-   <span data-ttu-id="45273-174">R.</span><span class="sxs-lookup"><span data-stu-id="45273-174">A.</span></span> [<span data-ttu-id="45273-175">Creazione di uno snapshot del database AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="45273-175">Creating a snapshot on the AdventureWorks database</span></span>](#Creating_on_AW)  
  
-   <span data-ttu-id="45273-176">B.</span><span class="sxs-lookup"><span data-stu-id="45273-176">B.</span></span> [<span data-ttu-id="45273-177">Creazione di uno snapshot del database Sales</span><span class="sxs-lookup"><span data-stu-id="45273-177">Creating a snapshot on the Sales database</span></span>](#Creating_on_Sales)  
  
####  <a name="a-creating-a-snapshot-on-the-adventureworks-database"></a><a name="Creating_on_AW"></a> <span data-ttu-id="45273-178">A.</span><span class="sxs-lookup"><span data-stu-id="45273-178">A.</span></span> <span data-ttu-id="45273-179">Creazione di uno snapshot del database AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="45273-179">Creating a snapshot on the AdventureWorks database</span></span>  
 <span data-ttu-id="45273-180">In questo esempio viene creato uno snapshot del database `AdventureWorks` .</span><span class="sxs-lookup"><span data-stu-id="45273-180">This example creates a database snapshot on the `AdventureWorks` database.</span></span> <span data-ttu-id="45273-181">Il nome dello snapshot, `AdventureWorks_dbss_1800`, e il nome del file sparse corrispondente, `AdventureWorks_data_1800.ss`, indicano l'ora di creazione, ovvero le 18.00 (1800).</span><span class="sxs-lookup"><span data-stu-id="45273-181">The snapshot name, `AdventureWorks_dbss_1800`, and the file name of its sparse file, `AdventureWorks_data_1800.ss`, indicate the creation time, 6 P.M (1800 hours).</span></span>  
  
```  
CREATE DATABASE AdventureWorks_dbss1800 ON  
( NAME = AdventureWorks_Data, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Data\AdventureWorks_data_1800.ss' )  
AS SNAPSHOT OF AdventureWorks;  
GO  
```  
  
####  <a name="b-creating-a-snapshot-on-the-sales-database"></a><a name="Creating_on_Sales"></a> <span data-ttu-id="45273-182">B.</span><span class="sxs-lookup"><span data-stu-id="45273-182">B.</span></span> <span data-ttu-id="45273-183">Creazione di uno snapshot del database Sales</span><span class="sxs-lookup"><span data-stu-id="45273-183">Creating a snapshot on the Sales database</span></span>  
 <span data-ttu-id="45273-184">In questo esempio viene creato uno snapshot, `sales_snapshot1200`, del database `Sales` .</span><span class="sxs-lookup"><span data-stu-id="45273-184">This example creates a database snapshot, `sales_snapshot1200`, on the `Sales` database.</span></span> <span data-ttu-id="45273-185">Questo database è stato creato nell'esempio "creazione di un database con filegroup" in [create database &#40;SQL Server&#41;Transact-SQL ](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="45273-185">This database was created in the example, "Creating a database that has filegroups," in [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span>  
  
```  
--Creating sales_snapshot1200 as snapshot of the  
--Sales database:  
CREATE DATABASE sales_snapshot1200 ON  
( NAME = SPri1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri1dat_1200.ss'),  
( NAME = SPri2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SPri2dt_1200.ss'),  
( NAME = SGrp1Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\mssql\data\SG1Fi1dt_1200.ss'),  
( NAME = SGrp1Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG1Fi2dt_1200.ss'),  
( NAME = SGrp2Fi1_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi1dt_1200.ss'),  
( NAME = SGrp2Fi2_dat, FILENAME =   
'C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\data\SG2Fi2dt_1200.ss')  
AS SNAPSHOT OF Sales;  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="45273-186">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="45273-186">Related Tasks</span></span>  
  
-   [<span data-ttu-id="45273-187">Visualizzazione di uno snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45273-187">View a Database Snapshot &#40;SQL Server&#41;</span></span>](view-a-database-snapshot-sql-server.md)  
  
-   [<span data-ttu-id="45273-188">Ripristinare un database a uno snapshot del database</span><span class="sxs-lookup"><span data-stu-id="45273-188">Revert a Database to a Database Snapshot</span></span>](revert-a-database-to-a-database-snapshot.md)  
  
-   [<span data-ttu-id="45273-189">Eliminare uno snapshot del database &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="45273-189">Drop a Database Snapshot &#40;Transact-SQL&#41;</span></span>](drop-a-database-snapshot-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="45273-190">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45273-190">See Also</span></span>  
 <span data-ttu-id="45273-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="45273-191">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 [<span data-ttu-id="45273-192">Snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="45273-192">Database Snapshots &#40;SQL Server&#41;</span></span>](database-snapshots-sql-server.md)  
  
  
