---
title: 'Esercitazione: Backup e ripristino di SQL Server nel servizio di archiviazione Blob di Azure| Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 9e1d94ce-2c93-45d1-ae2a-2a7d1fa094c4
author: rothja
ms.author: jroth
ms.openlocfilehash: d15200968011cdb314829736512f39730782dc0e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713020"
---
# <a name="tutorial-sql-server-backup-and-restore-to-azure-blob-storage-service"></a><span data-ttu-id="9e8ed-102">Esercitazione: Backup e ripristino di SQL Server nel servizio di archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="9e8ed-102">Tutorial: SQL Server Backup and Restore to Azure Blob Storage Service</span></span>
  <span data-ttu-id="9e8ed-103">Introduzione all'Introduzione con SQL Server backup e ripristino con il servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-103">Welcome to the Getting Started with SQL Server Backup and Restore with Azure Blob Storage Service tutorial.</span></span> <span data-ttu-id="9e8ed-104">Questa esercitazione contiene nozioni utili sulla scrittura di backup nel servizio di archiviazione Blob di Azure e sul ripristino dallo stesso.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-104">This tutorial helps you understand how to write backups to and restore from the Azure Blob storage service.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="9e8ed-105">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="9e8ed-105">What You Will Learn</span></span>  
 <span data-ttu-id="9e8ed-106">In questa esercitazione viene illustrato come creare un account di archiviazione di Windows, un contenitore BLOB, la creazione di credenziali per l'accesso all'account di archiviazione, la scrittura di un backup nel servizio BLOB e l'esecuzione di un ripristino semplice.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-106">This tutorial shows you how to create a Windows Storage account, a blob container, creating credentials to access the storage account, writing a backup to the blob service, and performing a simple restore.</span></span> <span data-ttu-id="9e8ed-107">Questa esercitazione è suddivisa in quattro lezioni:</span><span class="sxs-lookup"><span data-stu-id="9e8ed-107">This tutorial is divided into four lessons:</span></span>  
  
 [<span data-ttu-id="9e8ed-108">Lezione 1: creare oggetti di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="9e8ed-108">Lesson 1: Create Azure Storage Objects</span></span>](../tutorials/lesson-1-create-windows-azure-storage-objects.md)  
 <span data-ttu-id="9e8ed-109">In questa lezione verranno creati un account di archiviazione e un contenitore BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-109">In this lesson, you create an Azure storage account and a blob container.</span></span>  
  
 [<span data-ttu-id="9e8ed-110">Lezione 2: Creare le credenziali di SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e8ed-110">Lesson 2: Create a SQL Server Credential</span></span>](../tutorials/lesson-2-create-a-sql-server-credential.md)  
 <span data-ttu-id="9e8ed-111">In questa lezione verranno create le credenziali per archiviare le informazioni di sicurezza usate per accedere all'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-111">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 [<span data-ttu-id="9e8ed-112">Lezione 3: Scrivere un backup completo del database nel servizio Archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="9e8ed-112">Lesson 3: Write a Full Database Backup to the Azure Blob Storage Service</span></span>](../tutorials/lesson-3-write-a-full-database-backup-to-the-windows-azure-blob-storage-service.md)  
 <span data-ttu-id="9e8ed-113">In questa lezione verrà eseguita un'istruzione T-SQL per scrivere un backup del database AdventureWorks2012 nel servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-113">In this lesson, you issue a T-SQL statement to write a backup of the AdventureWorks2012 database to the Azure Blob storage service.</span></span>  
  
 [<span data-ttu-id="9e8ed-114">Lezione 4: Eseguire un ripristino da un backup completo del database</span><span class="sxs-lookup"><span data-stu-id="9e8ed-114">Lesson 4: Perform a Restore From a Full Database Backup</span></span>](../tutorials/lesson-4-perform-a-restore-from-a-full-database-backup.md)  
 <span data-ttu-id="9e8ed-115">In questa lezione verrà eseguita un'istruzione T-SQL per il ripristino dal backup del database creato nella lezione precedente.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-115">In this lesson, you issue a T-SQL statement to restore from the database backup you created in the previous lesson.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="9e8ed-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e8ed-116">Requirements</span></span>  
 <span data-ttu-id="9e8ed-117">Per completare l'esercitazione è necessario conoscere i concetti di backup e ripristino di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e la sintassi T-SQL.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-117">To complete this tutorial, you must be familiar with [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore concepts and T-SQL syntax.</span></span> <span data-ttu-id="9e8ed-118">Per utilizzare l'esercitazione, il sistema deve soddisfare i requisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-118">To use this tutorial, your system must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="9e8ed-119">Un'istanza di [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] e il database AdventureWorks2012 installati.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-119">An instance of [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], and AdventureWorks2012 database installed.</span></span>  
  
     <span data-ttu-id="9e8ed-120">L'istanza di SQL Server può essere in locale o in una macchina virtuale di Azure.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-120">The SQL Server instance can be on-premises or in an Azure Virtual Machine.</span></span>  
  
     <span data-ttu-id="9e8ed-121">È possibile utilizzare un database utente al posto di AdventureWorks2012 e modificare la sintassi tsql di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="9e8ed-121">You can use a user database in place of AdventureWorks2012, and modify the tsql syntax accordingly.</span></span>  
  
-   <span data-ttu-id="9e8ed-122">All'account utente usato per eseguire i comandi BACKUP o RESTORE deve essere associato il ruolo del database **db_backup operator** con autorizzazioni **Modifica qualsiasi credenziale** .</span><span class="sxs-lookup"><span data-stu-id="9e8ed-122">The user account that is used to issue BACKUP or RESTORE commands should be in the **db_backup operator** database role with **Alter any credential** permissions.</span></span>  
  
### <a name="additional-reading"></a><span data-ttu-id="9e8ed-123">Altre letture</span><span class="sxs-lookup"><span data-stu-id="9e8ed-123">Additional Reading</span></span>  
 <span data-ttu-id="9e8ed-124">Di seguito sono indicati alcuni argomenti consigliati per comprendere i concetti e le procedure consigliate quando si utilizza il servizio di archiviazione BLOB di Azure per i backup di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9e8ed-124">Following are some recommended reading to understand the concepts, best practices when using Azure Blob storage service for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups.</span></span>  
  
1.  [<span data-ttu-id="9e8ed-125">Backup e ripristino di SQL Server con il servizio Archiviazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="9e8ed-125">SQL Server Backup and Restore with Azure Blob Storage Service</span></span>](backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service.md)  
  
2.  [<span data-ttu-id="9e8ed-126">Procedure consigliate e risoluzione dei problemi per il backup di SQL Server nell'URL</span><span class="sxs-lookup"><span data-stu-id="9e8ed-126">SQL Server Backup to URL Best Practices and Troubleshooting</span></span>](backup-restore/sql-server-backup-to-url-best-practices-and-troubleshooting.md)  
  
  
