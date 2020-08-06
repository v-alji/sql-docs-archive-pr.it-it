---
title: 'Esercitazione: SQL Server di file di dati nel servizio di archiviazione di Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
ms.assetid: e69be67d-da1c-41ae-8c9a-6b12c8c2fb61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 21a0fc11706a0c5ee35cf71e1af69f2927adc9db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637715"
---
# <a name="tutorial-sql-server-data-files-in-azure-storage-service"></a><span data-ttu-id="3cd61-102">Esercitazione: File di dati di SQL Server nel servizio Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="3cd61-102">Tutorial: SQL Server Data Files in Azure Storage service</span></span>
  <span data-ttu-id="3cd61-103">Introduzione all'esercitazione relativa ai file di dati di SQL Server nel servizio di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3cd61-103">Welcome to the  SQL Server Data Files in Azure Storage Service tutorial.</span></span> <span data-ttu-id="3cd61-104">Questa esercitazione contiene informazioni utili sull'archiviazione dei file di dati di SQL Server direttamente nel servizio di archiviazione BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="3cd61-104">This tutorial helps you understand how to store SQL Server data files in the Azure Blob storage service directly.</span></span>  
  
 <span data-ttu-id="3cd61-105">Il supporto per l'integrazione SQL Server per il servizio di archiviazione BLOB di Azure è un miglioramento SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="3cd61-105">SQL Server integration support for the Azure Blob storage service is a SQL Server 2014 enhancement.</span></span> <span data-ttu-id="3cd61-106">Per una panoramica delle funzionalità e dei vantaggi derivanti dall'uso di questa funzionalità, vedere [SQL Server di file di dati in Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span><span class="sxs-lookup"><span data-stu-id="3cd61-106">For an overview of the functionality and benefits of using this functionality, see [SQL Server Data Files in Azure](databases/sql-server-data-files-in-microsoft-azure.md).</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="3cd61-107">Lezioni dell'esercitazione</span><span class="sxs-lookup"><span data-stu-id="3cd61-107">What you will learn</span></span>  
 <span data-ttu-id="3cd61-108">Questa esercitazione illustra come archiviare SQL Server file di dati nel servizio di archiviazione di Azure in più lezioni.</span><span class="sxs-lookup"><span data-stu-id="3cd61-108">This tutorial shows you how to store SQL Server Data Files in Azure Storage service in multiple lessons.</span></span> <span data-ttu-id="3cd61-109">Ogni lezione è incentrata su un'attività specifica.</span><span class="sxs-lookup"><span data-stu-id="3cd61-109">Each lesson is focused on a specific task.</span></span> <span data-ttu-id="3cd61-110">Per prima cosa, si apprenderà come creare un account di archiviazione e un contenitore in Azure.</span><span class="sxs-lookup"><span data-stu-id="3cd61-110">First, you will learn how to create a storage account and a container in Azure.</span></span> <span data-ttu-id="3cd61-111">Si apprenderà quindi come creare una SQL Server credenziali per poter integrare SQL Server con archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3cd61-111">Then, you will learn how to create a SQL Server credential to be able to integrate SQL Server with Azure Storage.</span></span> <span data-ttu-id="3cd61-112">Quindi, si creerà direttamente un database in archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3cd61-112">Then, you will create a database in Azure Storage directly.</span></span> <span data-ttu-id="3cd61-113">Inoltre, verranno illustrati scenari di crittografia, di migrazione e di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="3cd61-113">In addition, the tutorial will demonstrate encryption, migration, and backup and restore scenarios.</span></span>  
  
 <span data-ttu-id="3cd61-114">L'esercitazione è suddivisa in nove lezioni:</span><span class="sxs-lookup"><span data-stu-id="3cd61-114">This tutorial is divided into nine lessons:</span></span>  
  
 <span data-ttu-id="3cd61-115">**[Lezione 1: Creare account e contenitore di Archiviazione di Azure](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-115">**[Lesson 1: Create Azure Storage Account and Container](../tutorials/lesson-1-create-windows-azure-storage-account-and-container.md)**</span></span>  
 <span data-ttu-id="3cd61-116">In questa lezione viene creato un account di archiviazione di Azure e un contenitore.</span><span class="sxs-lookup"><span data-stu-id="3cd61-116">In this lesson, you create an Azure Storage account and a container.</span></span>  
  
 <span data-ttu-id="3cd61-117">**[Lezione 2. Creare un criterio per il contenitore e generare una firma di accesso condiviso &#40;chiave di&#41; SAS](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-117">**[Lesson 2. Create a policy on container and generate a Shared Access Signature &#40;SAS&#41; key](lesson-1-create-stored-access-policy-and-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="3cd61-118">In questa lezione vengono creati i criteri del contenitore BLOB e viene inoltre generata una firma di accesso condiviso.</span><span class="sxs-lookup"><span data-stu-id="3cd61-118">In this lesson, you create a policy on the Blob container and also generate a shared access signature.</span></span>  
  
 <span data-ttu-id="3cd61-119">**[Lezione 3: Creare le credenziali di SQL Server](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-119">**[Lesson 3: Create a SQL Server Credential](lesson-2-create-a-sql-server-credential-using-a-shared-access-signature.md)**</span></span>  
 <span data-ttu-id="3cd61-120">In questa lezione verranno create le credenziali per archiviare le informazioni di sicurezza usate per accedere all'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="3cd61-120">In this lesson, you create a Credential to store security information used to access the Azure storage account.</span></span>  
  
 <span data-ttu-id="3cd61-121">**[Lezione 4: Creare un database in Archiviazione di Azure](../relational-databases/lesson-3-database-backup-to-url.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-121">**[Lesson 4: Create a database in Azure Storage](../relational-databases/lesson-3-database-backup-to-url.md)**</span></span>  
 <span data-ttu-id="3cd61-122">In questa lezione viene creato un database in archiviazione di Azure usando l'opzione CREATE database FILENAME.</span><span class="sxs-lookup"><span data-stu-id="3cd61-122">In this lesson, you create a database in Azure Storage using CREATE Database FILENAME option.</span></span>  
  
 <span data-ttu-id="3cd61-123">**[Lezione 5. &#40;facoltativo&#41; crittografare il database tramite Transparent Data Encryption](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-123">**[Lesson 5. &#40;Optional&#41; Encrypt your database using TDE](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)**</span></span>  
 <span data-ttu-id="3cd61-124">In questa lezione viene crittografato il database tramite Transparent Data Encryption (TDE) e un certificato del server.</span><span class="sxs-lookup"><span data-stu-id="3cd61-124">In this lesson, you encrypt your database by using a transparent data encryption (TDE) and a server certificate.</span></span>  
  
 <span data-ttu-id="3cd61-125">**[Lezione 6: Eseguire la migrazione di un database da un computer di origine locale a un computer di destinazione in Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-125">**[Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure](lesson-5-backup-database-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="3cd61-126">In questa lezione viene eseguita la migrazione di un database da locale a una macchina virtuale in Azure tramite l'opzione CREATE DATABASE FOR Connetti.</span><span class="sxs-lookup"><span data-stu-id="3cd61-126">In this lesson, you migrate a database from on-premises to a virtual machine in Azure using CREATE DATABASE FOR ATTACH option.</span></span>  
  
 <span data-ttu-id="3cd61-127">**[Lezione 7: Spostare i file di dati in Archiviazione di Azure](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-127">**[Lesson 7: Move your data files to Azure Storage](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)**</span></span>  
 <span data-ttu-id="3cd61-128">In questa lezione si spostano i file di dati in archiviazione di Azure usando l'istruzione ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="3cd61-128">In this lesson, you move your data files to Azure Storage using ALTER DATABASE statement.</span></span>  
  
 <span data-ttu-id="3cd61-129">**[Lezione 8. Ripristinare un database in archiviazione di Azure](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-129">**[Lesson 8. Restore a database to Azure Storage](../relational-databases/lesson-7-restore-a-database-to-a-point-in-time.md)**</span></span>  
 <span data-ttu-id="3cd61-130">In questa lezione viene ripristinato un database in archiviazione di Azure utilizzando l'opzione RESTOre database MOVE.</span><span class="sxs-lookup"><span data-stu-id="3cd61-130">In this lesson, you restore a database to Azure Storage using RESTORE Database MOVE option.</span></span>  
  
 <span data-ttu-id="3cd61-131">**[Lezione 9. Ripristinare un database da archiviazione di Azure](lesson-8-restore-as-new-database-from-log-backup.md)**</span><span class="sxs-lookup"><span data-stu-id="3cd61-131">**[Lesson 9. Restore a database from Azure Storage](lesson-8-restore-as-new-database-from-log-backup.md)**</span></span>  
 <span data-ttu-id="3cd61-132">In questa lezione viene ripristinato un database da archiviazione di Azure utilizzando l'opzione RESTOre database MOVE.</span><span class="sxs-lookup"><span data-stu-id="3cd61-132">In this lesson, you restore a database from Azure Storage using RESTORE Database MOVE option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cd61-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cd61-133">See Also</span></span>  
 [<span data-ttu-id="3cd61-134">SQL Server file di dati in Azure</span><span class="sxs-lookup"><span data-stu-id="3cd61-134">SQL Server Data Files in Azure</span></span>](databases/sql-server-data-files-in-microsoft-azure.md)  
  
  
