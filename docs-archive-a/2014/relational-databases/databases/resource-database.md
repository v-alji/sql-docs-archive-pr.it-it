---
title: Database delle risorse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system objects [SQL Server]
- read-only databases
- mssqlsystemresource.mdf file
- Resource database [SQL Server]
ms.assetid: d592b2b4-bc36-4eb9-9385-8fe4dff0dced
author: stevestein
ms.author: sstein
ms.openlocfilehash: cca2f9e1ff6069a608beb1df1880b37e15f4e869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627800"
---
# <a name="resource-database"></a><span data-ttu-id="7b9df-102">Database Resource</span><span class="sxs-lookup"><span data-stu-id="7b9df-102">Resource Database</span></span>
  <span data-ttu-id="7b9df-103">Il database Resource è un database di sola lettura che contiene tutti gli oggetti di sistema inclusi in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b9df-103">The Resource database is a read-only database that contains all the system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7b9df-104">Gli oggetti di sistema, ad esempio sys.objects, sono archiviati fisicamente nel database Resource in modo persistente, ma nello schema sys di ogni database ne è presente un'implementazione logica.</span><span class="sxs-lookup"><span data-stu-id="7b9df-104">system objects, such as sys.objects, are physically persisted in the Resource database, but they logically appear in the sys schema of every database.</span></span> <span data-ttu-id="7b9df-105">Il database Resource non contiene dati o metadati degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7b9df-105">The Resource database does not contain user data or user metadata.</span></span>  
  
 <span data-ttu-id="7b9df-106">Il database delle risorse consente di semplificare e rendere più rapida la procedura di aggiornamento a una nuova versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b9df-106">The Resource database makes upgrading to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an easier and faster procedure.</span></span> <span data-ttu-id="7b9df-107">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]la procedura di aggiornamento prevede l'eliminazione e la creazione di oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="7b9df-107">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], upgrading required dropping and creating system objects.</span></span> <span data-ttu-id="7b9df-108">Dal momento che il file del database Resource contiene tutti gli oggetti di sistema, l'aggiornamento viene ora eseguito semplicemente copiando il singolo file del database Resource sul server locale.</span><span class="sxs-lookup"><span data-stu-id="7b9df-108">Because the Resource database file contains all system objects, an upgrade is now accomplished simply by copying the single Resource database file to the local server.</span></span>  
  
## <a name="physical-properties-of-resource"></a><span data-ttu-id="7b9df-109">Proprietà fisiche del database Resource</span><span class="sxs-lookup"><span data-stu-id="7b9df-109">Physical Properties of Resource</span></span>  
 <span data-ttu-id="7b9df-110">I nomi di file fisici del database Resource sono mssqlsystemresource.mdf e mssqlsystemresource.ldf.</span><span class="sxs-lookup"><span data-stu-id="7b9df-110">The physical file names of the Resource database are mssqlsystemresource.mdf and mssqlsystemresource.ldf.</span></span> <span data-ttu-id="7b9df-111">I file si trovano in \<*drive*>:\Programmi\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ e non devono essere spostati.</span><span class="sxs-lookup"><span data-stu-id="7b9df-111">These files are located in \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ and should not be moved.</span></span> <span data-ttu-id="7b9df-112">A ogni istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è associato un solo file mssqlsystemresource.mdf e istanze diverse non condividono il file.</span><span class="sxs-lookup"><span data-stu-id="7b9df-112">Each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one and only one associated mssqlsystemresource.mdf file, and instances do not share this file.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="7b9df-113">Gli aggiornamenti e i Service Pack forniscono talvolta un nuovo database delle risorse che viene installato nella cartella BINN.</span><span class="sxs-lookup"><span data-stu-id="7b9df-113">Upgrades and service packs sometimes provide a new resource database which is installed to the BINN folder.</span></span> <span data-ttu-id="7b9df-114">Non è consigliabile né possibile modificare il percorso del database delle risorse.</span><span class="sxs-lookup"><span data-stu-id="7b9df-114">Changing the location of the resource database is not supported or recommended.</span></span>  
  
## <a name="backing-up-and-restoring-the-resource-database"></a><span data-ttu-id="7b9df-115">Backup e ripristino del database Resource</span><span class="sxs-lookup"><span data-stu-id="7b9df-115">Backing Up and Restoring the Resource Database</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7b9df-116">non è in grado di eseguire il backup del database delle risorse.</span><span class="sxs-lookup"><span data-stu-id="7b9df-116">cannot back up the Resource database.</span></span> <span data-ttu-id="7b9df-117">È possibile eseguire un backup basato su file o basato su disco gestendo il file mssqlsystemresource.mdf come un file binario (con estensione exe), anziché come un file di database, ma non è possibile utilizzare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per ripristinare i backup.</span><span class="sxs-lookup"><span data-stu-id="7b9df-117">You can perform your own file-based or a disk-based backup by treating the mssqlsystemresource.mdf file as if it were a binary (.EXE) file, rather than a database file, but you cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to restore your backups.</span></span> <span data-ttu-id="7b9df-118">Il ripristino di una copia di backup di mssqlsystemresource.mdf può essere eseguito solo manualmente, prestando attenzione a non sovrascrivere il database Resource corrente con una versione non aggiornata e potenzialmente non sicura.</span><span class="sxs-lookup"><span data-stu-id="7b9df-118">Restoring a backup copy of mssqlsystemresource.mdf can only be done manually, and you must be careful not to overwrite the current Resource database with an out-of-date or potentially insecure version.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7b9df-119">Dopo aver ripristinato un backup di mssqlsystemresource.mdf, è necessario riapplicare eventuali aggiornamenti successivi.</span><span class="sxs-lookup"><span data-stu-id="7b9df-119">After restoring a backup of mssqlsystemresource.mdf, you must reapply any subsequent updates.</span></span>  
  
## <a name="accessing-the-resource-database"></a><span data-ttu-id="7b9df-120">Accesso al database Resource</span><span class="sxs-lookup"><span data-stu-id="7b9df-120">Accessing the Resource Database</span></span>  
 <span data-ttu-id="7b9df-121">È consigliabile che il database Resource venga modificato esclusivamente da o dietro indicazione di uno specialista del Servizio Supporto Tecnico Clienti Microsoft (CSS, Client Support Services).</span><span class="sxs-lookup"><span data-stu-id="7b9df-121">The Resource database should only be modified by or at the direction of a Microsoft Customer Support Services (CSS) specialist.</span></span> <span data-ttu-id="7b9df-122">L'ID del database Resource è sempre 32767.</span><span class="sxs-lookup"><span data-stu-id="7b9df-122">The ID of the Resource database is always 32767.</span></span> <span data-ttu-id="7b9df-123">Altri importanti valori associati al database Resource sono il numero di versione e la data e ora del suo ultimo aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="7b9df-123">Other important values associated with the Resource database are the version number and the last time that the database was updated.</span></span>  
  
 <span data-ttu-id="7b9df-124">**Per determinare il numero di versione del database delle** risorse **, usare**:</span><span class="sxs-lookup"><span data-stu-id="7b9df-124">**To determine the version number of the** Resource **database, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceVersion');  
GO  
```  
  
 <span data-ttu-id="7b9df-125">**Per determinare data e ora dell'ultimo aggiornamento del database delle** risorse **, usare**:</span><span class="sxs-lookup"><span data-stu-id="7b9df-125">**To determine when the** Resource **database was last updated, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceLastUpdateDateTime');  
GO  
```  
  
 <span data-ttu-id="7b9df-126">**Per accedere a definizioni SQL di oggetti di sistema, utilizzare la funzione OBJECT_DEFINITION:**</span><span class="sxs-lookup"><span data-stu-id="7b9df-126">**To access SQL definitions of system objects, use the OBJECT_DEFINITION function:**</span></span>  
  
```  
SELECT OBJECT_DEFINITION(OBJECT_ID('sys.objects'));  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="7b9df-127">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="7b9df-127">Related Content</span></span>  
 [<span data-ttu-id="7b9df-128">Database di sistema.</span><span class="sxs-lookup"><span data-stu-id="7b9df-128">System Databases</span></span>](system-databases.md)  
  
 [<span data-ttu-id="7b9df-129">Connessione di diagnostica per gli amministratori di database</span><span class="sxs-lookup"><span data-stu-id="7b9df-129">Diagnostic Connection for Database Administrators</span></span>](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)  
  
 [<span data-ttu-id="7b9df-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b9df-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
 [<span data-ttu-id="7b9df-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7b9df-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
 [<span data-ttu-id="7b9df-132">Avvio di SQL Server in modalità utente singolo</span><span class="sxs-lookup"><span data-stu-id="7b9df-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
