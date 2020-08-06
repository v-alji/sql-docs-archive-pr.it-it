---
title: Lezione 8. Ripristinare un database in archiviazione di Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9f99670-e1de-441e-972c-69faffcac17a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: adec725d1b519fb67560dc572823ba0a116aaa54
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637292"
---
# <a name="lesson-8-restore-a-database-to-azure-storage"></a><span data-ttu-id="c294e-103">Lezione 8.</span><span class="sxs-lookup"><span data-stu-id="c294e-103">Lesson 8.</span></span> <span data-ttu-id="c294e-104">Ripristinare un database in Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="c294e-104">Restore a database to Azure Storage</span></span>
  <span data-ttu-id="c294e-105">In questa lezione verrà illustrato come creare un file di backup in locale e quindi ripristinarlo in archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="c294e-105">In this lesson, you will learn how to create a backup file locally and then restore it to Azure Storage.</span></span> <span data-ttu-id="c294e-106">Si noti che è possibile fare in modo che il database sia in locale o in una macchina virtuale in Azure.</span><span class="sxs-lookup"><span data-stu-id="c294e-106">Note that you can have your database either on either on-premises or in a virtual machine in Azure.</span></span> <span data-ttu-id="c294e-107">È possibile seguire questa lezione anche senza aver completato le lezioni 4, 5, 6 e 7.</span><span class="sxs-lookup"><span data-stu-id="c294e-107">To follow this lesson, you do not need to complete Lesson 4, 5, 6, and 7.</span></span>  
  
 <span data-ttu-id="c294e-108">Per questa lezione si presuppone che l'utente abbia già completato i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c294e-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="c294e-109">Si ha un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="c294e-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="c294e-110">È stato creato un contenitore nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="c294e-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="c294e-111">Creazione dei criteri in un contenitore con diritti di lettura, scrittura ed elenco.</span><span class="sxs-lookup"><span data-stu-id="c294e-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="c294e-112">Generazione di una chiave SAS.</span><span class="sxs-lookup"><span data-stu-id="c294e-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="c294e-113">La credenziale di SQL Server viene creata nel computer di origine in base alla firma di accesso condiviso (SAS, Shared Access Signature).</span><span class="sxs-lookup"><span data-stu-id="c294e-113">You have created a SQL Server credential on the source machine based on Shared Access Signature.</span></span>  
  
-   <span data-ttu-id="c294e-114">È stato creato un database nel computer di origine.</span><span class="sxs-lookup"><span data-stu-id="c294e-114">You have created a database in the source machine.</span></span>  
  
 <span data-ttu-id="c294e-115">Per ripristinare un database in archiviazione di Azure, è possibile seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c294e-115">To restore a database to Azure Storage, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="c294e-116">Nel computer di origine, avviare SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="c294e-116">In the source machine, start SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="c294e-117">Quando si è connessi al database appena creato, aprire la finestra Query.</span><span class="sxs-lookup"><span data-stu-id="c294e-117">When connected to the newly created database, open the query window.</span></span> <span data-ttu-id="c294e-118">Eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="c294e-118">Run the following statement:</span></span>  
  
    ```sql  
  
    USE TestDB3Restore;   
    GO   
    BACKUP DATABASE TestDB3Restore   
    TO DISK = 'C:\BACKUP\TestDB3Restore.Bak'   
       WITH FORMAT,   
       NAME = 'Full Backup of TestDB3Restore'   
    GO  
  
    ```  
  
3.  <span data-ttu-id="c294e-119">Quindi, copiare ed eseguire le istruzioni seguenti nella finestra Query.</span><span class="sxs-lookup"><span data-stu-id="c294e-119">Next, copy and run the following statements in the Query window.</span></span>  
  
    ```sql  
  
    USE master;   
    GO   
    RESTORE DATABASE TestDB3Restore    
    FROM DISK = 'C:\BACKUP\TestDB3Restore.bak'    
    WITH REPLACE,   
    MOVE 'TestDB3Restore' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore.mdf',     
    MOVE 'TestDB3Restore_log' TO 'https://teststorageaccnt.blob.core.windows.net/testcontainrestore/TestDB3Restore_log.ldf';   
    GO  
  
    ```  
  
     <span data-ttu-id="c294e-120">Al termine del passaggio, i file di dati (estensione mdf e ldf) vengono elencati nel portale di gestione.</span><span class="sxs-lookup"><span data-stu-id="c294e-120">At the end of this step, your container should list data (.mdf) and (.ldf) files on the Management Portal.</span></span>  
  
 <span data-ttu-id="c294e-121">Per ripristinare un database con file di dati e di log che puntano ad archiviazione di Azure usando SQL Server Management Studio interfaccia utente, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="c294e-121">To restore a database with data and log files pointing to Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="c294e-122">In **Esplora oggetti**fare clic sul nome del server per espandere l'albero del server.</span><span class="sxs-lookup"><span data-stu-id="c294e-122">In **Object Explorer**, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="c294e-123">Espandere **database**, quindi selezionare il database.</span><span class="sxs-lookup"><span data-stu-id="c294e-123">Expand **Databases**, and, select your database.</span></span>  
  
3.  <span data-ttu-id="c294e-124">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Ripristina**.</span><span class="sxs-lookup"><span data-stu-id="c294e-124">Right-click the database, point to **Tasks**, and then click **Restore**.</span></span>  
  
4.  <span data-ttu-id="c294e-125">Nella sezione origine **ripristino** della pagina **generale** fare clic su dispositivo di **origine** .</span><span class="sxs-lookup"><span data-stu-id="c294e-125">On the **General** page, in the **Restore** source section, click **Source** device.</span></span>  
  
5.  <span data-ttu-id="c294e-126">Fare clic sul pulsante Sfoglia per la casella di testo dispositivo di **origine** , che consente di aprire la finestra di dialogo **Seleziona dispositivi di backup** .</span><span class="sxs-lookup"><span data-stu-id="c294e-126">Click the browse button for the **Source** device text box, which opens the **Select Backup Devices** dialog box.</span></span>  
  
6.  <span data-ttu-id="c294e-127">Nella casella di testo supporti di backup selezionare **file**, quindi fare clic sul pulsante **Aggiungi** per individuare il file di backup (con estensione bak).</span><span class="sxs-lookup"><span data-stu-id="c294e-127">In the Backup media text box, select **File**, and click the **Add** button to locate the backup (.bak) file.</span></span> <span data-ttu-id="c294e-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c294e-128">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="c294e-129">Fare clic su **file** nella prima pagina.</span><span class="sxs-lookup"><span data-stu-id="c294e-129">Click **Files** on the first page.</span></span>  
  
8.  <span data-ttu-id="c294e-130">Nella sezione **Ripristina file di database** come digitare quanto segue nel campo **Ripristina come** :</span><span class="sxs-lookup"><span data-stu-id="c294e-130">In the **Restore Database Files** as section, under **Restore As** field, type the followings:</span></span>  
  
     <span data-ttu-id="c294e-131">Per file di dati, digitare: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf` .</span><span class="sxs-lookup"><span data-stu-id="c294e-131">For data file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS.mdf`.</span></span> <span data-ttu-id="c294e-132">Per file di log, digitare: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf` .</span><span class="sxs-lookup"><span data-stu-id="c294e-132">For log file, type: `https://teststorageaccnt.blob.core.windows.net/testrestoressms/TestRESSMS_log.ldf`.</span></span>  
  
     <span data-ttu-id="c294e-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="c294e-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-8.gif "SQL 14 CTP2")</span></span>  
  
9. <span data-ttu-id="c294e-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c294e-134">Click **OK**.</span></span>  
  
 <span data-ttu-id="c294e-135">Una volta eseguito il ripristino, accedere al portale di gestione.</span><span class="sxs-lookup"><span data-stu-id="c294e-135">When the restore is done, log in to the Management Portal.</span></span> <span data-ttu-id="c294e-136">È possibile visualizzare i file con estensione mdf e ldf nel contenitore come segue:</span><span class="sxs-lookup"><span data-stu-id="c294e-136">You should be able to see the .mdf and .ldf files in the container as follows:</span></span>  
  
 <span data-ttu-id="c294e-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="c294e-137">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-8-9.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="c294e-138">**Lezione successiva:**</span><span class="sxs-lookup"><span data-stu-id="c294e-138">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="c294e-139">Lezione 9. Ripristinare un database da archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="c294e-139">Lesson 9. Restore a database from Azure Storage</span></span>](../relational-databases/lesson-8-restore-as-new-database-from-log-backup.md)  
  
  
