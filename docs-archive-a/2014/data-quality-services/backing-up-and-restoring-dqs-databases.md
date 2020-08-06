---
title: Backup e ripristino di database DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3091f62-2234-4a80-a615-cf14c2a1da85
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 489664d8c64a99d1ea4dcec79b93e5b01b28f649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624977"
---
# <a name="backing-up-and-restoring-dqs-databases"></a><span data-ttu-id="05d29-102">Backup e ripristino di database DQS</span><span class="sxs-lookup"><span data-stu-id="05d29-102">Backing Up and Restoring DQS Databases</span></span>
  <span data-ttu-id="05d29-103">In questo argomento viene descritto come eseguire il backup e il ripristino dei database DQS.</span><span class="sxs-lookup"><span data-stu-id="05d29-103">This topic describes how to back up and restore the DQS databases.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="05d29-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="05d29-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="05d29-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="05d29-105">Prerequisites</span></span>  
  
-   <span data-ttu-id="05d29-106">È necessario conoscere o ricordare la password per la chiave master del database fornita durante l'installazione del server DQS.</span><span class="sxs-lookup"><span data-stu-id="05d29-106">You must know or remember the password for the database master key that you provided during the DQS server installation.</span></span>  
  
-   <span data-ttu-id="05d29-107">Assicurarsi che non vi siano attività o processi in esecuzione in DQS.</span><span class="sxs-lookup"><span data-stu-id="05d29-107">Ensure that there are no running activities or processes in DQS.</span></span> <span data-ttu-id="05d29-108">È possibile verificare utilizzando la schermata **Monitoraggio attività** .</span><span class="sxs-lookup"><span data-stu-id="05d29-108">This can be verified using the **Activity Monitoring** screen.</span></span> <span data-ttu-id="05d29-109">Per informazioni dettagliate su funzionamento di questa schermata, vedere [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span><span class="sxs-lookup"><span data-stu-id="05d29-109">For detailed information about working in this screen, see [Monitor DQS Activities](../../2014/data-quality-services/monitor-dqs-activities.md).</span></span>  
  
-   <span data-ttu-id="05d29-110">Assicurarsi che non vi siano utenti connessi al server DQS.</span><span class="sxs-lookup"><span data-stu-id="05d29-110">Ensure that there are no users logged on the DQS server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="05d29-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="05d29-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="05d29-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="05d29-112">Permissions</span></span>  
  
-   <span data-ttu-id="05d29-113">Per poter effettuare operazioni di backup e ripristino, è necessario che l'account utente di Windows sia membro del ruolo predefinito del server sysadmin nell'istanza di SQL Server in cui è installato.</span><span class="sxs-lookup"><span data-stu-id="05d29-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance to perform the backup and restore operations.</span></span>  
  
-   <span data-ttu-id="05d29-114">È necessario disporre del ruolo dqs_administrator sul database DQS_MAIN per interrompere qualsiasi attività in esecuzione o arrestare processi in corso in DQS.</span><span class="sxs-lookup"><span data-stu-id="05d29-114">You must have the dqs_administrator role on the DQS_MAIN database to terminate any running activities or stop any running processes in DQS.</span></span>  
  
##  <a name="backup-and-restore-dqs-databases"></a><a name="BackupRestore"></a> <span data-ttu-id="05d29-115">Backup e ripristino di database DQS</span><span class="sxs-lookup"><span data-stu-id="05d29-115">Backup and Restore DQS Databases</span></span>  
  
1.  <span data-ttu-id="05d29-116">Avviare Microsoft SQL Server Management Studio e connettersi all'istanza di SQL Server appropriata.</span><span class="sxs-lookup"><span data-stu-id="05d29-116">Start Microsoft SQL Server Management Studio, and connect to the appropriate SQL Server instance.</span></span>  
  
2.  <span data-ttu-id="05d29-117">In Esplora oggetti espandere il nodo **Database** .</span><span class="sxs-lookup"><span data-stu-id="05d29-117">In Object Explorer, expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="05d29-118">Eseguire il backup del database DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="05d29-118">Back up the DQS_STAGING_DATA database.</span></span> <span data-ttu-id="05d29-119">Per istruzioni dettagliate per il backup di un database di SQL Server, vedere [Creare un backup completo del database &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="05d29-119">For step-by-step instructions for backing a SQL Server database, see [Create a Full Database Backup &#40;SQL Server&#41;](../relational-databases/backup-restore/create-a-full-database-backup-sql-server.md).</span></span>  
  
4.  <span data-ttu-id="05d29-120">Eseguire il backup del database DQS_PROJECTS.</span><span class="sxs-lookup"><span data-stu-id="05d29-120">Back up the DQS_PROJECTS database.</span></span>  
  
5.  <span data-ttu-id="05d29-121">Eseguire il backup del database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="05d29-121">Back up the DQS_MAIN database.</span></span>  
  
6.  <span data-ttu-id="05d29-122">Disconnettersi dall'istanza corrente di SQL Server e connettersi all'istanza di SQL Server in cui si desidera ripristinare i database.</span><span class="sxs-lookup"><span data-stu-id="05d29-122">Disconnect from the current instance of SQL Server, and connect to the SQL Server instance where you want to restore these databases.</span></span>  
  
7.  <span data-ttu-id="05d29-123">Ripristinare il database DQS_MAIN.</span><span class="sxs-lookup"><span data-stu-id="05d29-123">Restore DQS_MAIN database.</span></span> <span data-ttu-id="05d29-124">Per istruzioni dettagliate per il ripristino di un database di SQL Server, vedere [ripristino di un backup di database &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="05d29-124">For step-by-step instructions to restore a SQL Server database, see [Restore a Database Backup &#40;SQL Server Management Studio&#41;](../relational-databases/backup-restore/restore-a-database-backup-using-ssms.md).</span></span>  
  
8.  <span data-ttu-id="05d29-125">Ripristinare il database DQS_PROJECTS.</span><span class="sxs-lookup"><span data-stu-id="05d29-125">Restore the DQS_PROJECTS database.</span></span>  
  
9. <span data-ttu-id="05d29-126">Ripristinare il database DQS_STAGING_DATA.</span><span class="sxs-lookup"><span data-stu-id="05d29-126">Restore the DQS_STAGING_DATA database.</span></span>  
  
10. <span data-ttu-id="05d29-127">In Esplora oggetti fare clic con il pulsante destro del mouse sul server, quindi fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="05d29-127">In Object Explorer, right-click the server, and then click **New Query**.</span></span>  
  
11. <span data-ttu-id="05d29-128">Nella finestra dell'editor di query copiare le istruzioni SQL seguenti e sostituire *\<PASSWORD>* con la password specificata durante l'installazione di DQS per la chiave master del database:</span><span class="sxs-lookup"><span data-stu-id="05d29-128">In the Query Editor window, copy the following SQL statements, and replace *\<PASSWORD>* with the password that you provided during the DQS installation for the database master key:</span></span>  
  
    ```sql  
    USE [DQS_MAIN]  
    GO  
    EXECUTE [internal_core].[RestoreDQDatabases] '<PASSWORD>'  
    GO  
    ```  
  
12. <span data-ttu-id="05d29-129">Premere F5 per eseguire le istruzioni.</span><span class="sxs-lookup"><span data-stu-id="05d29-129">Press F5 to execute the statements.</span></span> <span data-ttu-id="05d29-130">Esaminare il riquadro **Risultati** per verificare che le istruzioni siano state eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="05d29-130">Check the **Results** pane to verify that the statements have executed successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05d29-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05d29-131">See Also</span></span>  
 [<span data-ttu-id="05d29-132">Manage DQS Databases</span><span class="sxs-lookup"><span data-stu-id="05d29-132">Manage DQS Databases</span></span>](../../2014/data-quality-services/manage-dqs-databases.md)  
  
  
