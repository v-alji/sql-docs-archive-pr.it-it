---
title: 'Lezione 6: eseguire la migrazione di un database da un computer di origine locale a un computer di destinazione in Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: d9134ade-7b03-4c5c-8ed3-3bc369a61691
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b9af8a260493561f9728d1677b7667bd3f36cb46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635580"
---
# <a name="lesson-6-migrate-a-database-from-a-source-machine-on-premises-to-a-destination-machine-in-azure"></a><span data-ttu-id="976e5-102">Lezione 6: Eseguire la migrazione di un database da un computer di origine locale a un computer di destinazione in Azure</span><span class="sxs-lookup"><span data-stu-id="976e5-102">Lesson 6: Migrate a database from a source machine on-premises to a destination machine in Azure</span></span>
  <span data-ttu-id="976e5-103">In questa lezione si presuppone che si disponga già di un altro SQL Server, che potrebbe trovarsi in un altro computer locale o in una macchina virtuale in Azure.</span><span class="sxs-lookup"><span data-stu-id="976e5-103">This lesson assumes that you already have another SQL Server, which might reside in another on-premises computer or in a virtual machine in Azure.</span></span> <span data-ttu-id="976e5-104">Per informazioni su come creare una macchina virtuale SQL Server in Azure, vedere [provisioning di una macchina virtuale SQL Server in Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span><span class="sxs-lookup"><span data-stu-id="976e5-104">For information on how to create a SQL Server virtual machine in Azure, see [Provisioning a SQL Server Virtual Machine on Azure](https://www.windowsazure.com/manage/windows/common-tasks/install-sql-server/).</span></span> <span data-ttu-id="976e5-105">Dopo il provisioning di una macchina virtuale SQL Server in Azure, verificare che sia possibile connettersi a un'istanza di SQL Server in questa macchina virtuale tramite SQL Server Management Studio in un altro computer.</span><span class="sxs-lookup"><span data-stu-id="976e5-105">After provisioning a SQL Server virtual machine in Azure, make sure that you can connect to an instance of SQL Server in this virtual machine via SQL Server Management Studio in another computer.</span></span>  
  
 <span data-ttu-id="976e5-106">Per questa lezione si presuppone che l'utente abbia già completato i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="976e5-106">This lesson also assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="976e5-107">Si ha un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="976e5-107">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="976e5-108">È stato creato un contenitore nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="976e5-108">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="976e5-109">Creazione dei criteri in un contenitore con diritti di lettura, scrittura ed elenco.</span><span class="sxs-lookup"><span data-stu-id="976e5-109">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="976e5-110">Generazione di una chiave SAS.</span><span class="sxs-lookup"><span data-stu-id="976e5-110">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="976e5-111">Creazione di una credenziale di SQL Server nel computer di origine.</span><span class="sxs-lookup"><span data-stu-id="976e5-111">You have created a SQL Server credential on the source machine.</span></span>  
  
-   <span data-ttu-id="976e5-112">È già stata creata una destinazione SQL Server macchina virtuale in Azure.</span><span class="sxs-lookup"><span data-stu-id="976e5-112">You already have created a destination SQL Server virtual machine in Azure.</span></span> <span data-ttu-id="976e5-113">È consigliabile crearla selezionando un'immagine della piattaforma che prevede SQL Server 2014.</span><span class="sxs-lookup"><span data-stu-id="976e5-113">We recommend that you create it by selecting a platform image that includes SQL Server 2014.</span></span>  
  
 <span data-ttu-id="976e5-114">Per eseguire la migrazione di un database da SQL Server locale a un'altra macchina virtuale in Azure, è possibile seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="976e5-114">To migrate a database from SQL Server on-premises to another virtual machine in Azure, you can follow these steps:</span></span>  
  
1.  <span data-ttu-id="976e5-115">Nel computer di origine, ovvero un computer locale in questa esercitazione, aprire una finestra di query in SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="976e5-115">In the source machine (which is an on-premises computer in this tutorial), open a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="976e5-116">Scollegare il database per spostarlo in un altro computer attenendosi alle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="976e5-116">Detach your database to move it to another machine by executing these statements:</span></span>  
  
    ```  
    -- Detach the database in the source machine   
    USE master  
    EXEC sp_detach_db 'TestDB1', 'true';  
    ```  
  
2.  <span data-ttu-id="976e5-117">Se è necessario trasferire un database in un computer di destinazione, è necessario innanzitutto prepararlo.</span><span class="sxs-lookup"><span data-stu-id="976e5-117">If you need to transfer a database to a destination machine, first you must prepare it.</span></span> <span data-ttu-id="976e5-118">Per preparare il computer di destinazione, è necessario innanzitutto creare le credenziale di SQL Server nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="976e5-118">To prepare your destination machine, first you need to create a SQL Server credential in the destination machine.</span></span> <span data-ttu-id="976e5-119">Se è un database crittografato, è necessario importare il certificato dal computer di origine al computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="976e5-119">If it is an encrypted database, you need to import the certificate from the source machine to the destination machine as well.</span></span>  
  
    1.  <span data-ttu-id="976e5-120">Per creare una credenziale di SQL Server nel computer di destinazione, effettuare i passaggi riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="976e5-120">To create a SQL Server Credential in the destination machine, follow these steps:</span></span>  
  
        1.  <span data-ttu-id="976e5-121">Connettersi al computer di destinazione tramite SQL Server Management Studio presente nel computer di origine.</span><span class="sxs-lookup"><span data-stu-id="976e5-121">Connect to the destination machine via SQL Server Management Studio in your source computer.</span></span>  <span data-ttu-id="976e5-122">In alternativa, avviare direttamente SQL Server Management Studio nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="976e5-122">Or, start SQL Server Management Studio in your destination computer directly.</span></span>  
  
        2.  <span data-ttu-id="976e5-123">Sulla barra degli strumenti Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="976e5-123">On the Standard tool bar, click **New Query**.</span></span>  
  
        3.  <span data-ttu-id="976e5-124">Copiare e incollare l'esempio seguente nella finestra Query e modificare se necessario.</span><span class="sxs-lookup"><span data-stu-id="976e5-124">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="976e5-125">L'istruzione seguente crea una credenziale SQL Server per archiviare il certificato di accesso condiviso del contenitore di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="976e5-125">The following statement creates a SQL Server Credential to store your storage container's Shared Access Certificate.</span></span>  
  
            ```sql  
  
            USE master   
            GO   
            CREATE CREDENTIAL [http://teststorageaccnt.blob.core.windows.net/testcontainer]   
            WITH IDENTITY='SHARED ACCESS SIGNATURE',   
            SECRET = 'your SAS key'   
            GO  
  
            ```  
  
        4.  <span data-ttu-id="976e5-126">Per visualizzare tutte le credenziali disponibili, è possibile eseguire l'istruzione seguente nella finestra della query:</span><span class="sxs-lookup"><span data-stu-id="976e5-126">To see all available credentials, you can run the following statement in the query window:</span></span>  
  
            ```sql  
            SELECT * from sys.credentials   
            ```  
  
        5.  <span data-ttu-id="976e5-127">Una volta connessi a un server di destinazione, aprire la finestra di query ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="976e5-127">When connected to the destination server, open query window, and run:</span></span>  
  
            ```sql  
  
            -- Create a master key and a server certificate   
            USE master   
            GO   
            CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'MySQLKey01'; -- You may use a different password.   
            GO   
            CREATE CERTIFICATE MySQLCert   
            FROM FILE = 'C:\certs\MySQLCert.CER'   
            WITH PRIVATE KEY   
            (   
            FILE = 'C:\certs\MySQLPrivateKeyFile.PVK',   
            DECRYPTION BY PASSWORD = 'MySQLKey01'   
            );   
            GO  
  
            ```  
  
             <span data-ttu-id="976e5-128">Al termine del passaggio, nel computer di destinazione è stato importato il certificato di crittografia di cui è stato eseguito il backup dal computer di origine.</span><span class="sxs-lookup"><span data-stu-id="976e5-128">At the end of this step, the destination machine has imported the encryption certificate that was backed up from the source machine.</span></span> <span data-ttu-id="976e5-129">Successivamente, è possibile allegare file di dati nel computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="976e5-129">Next, you can attach the data files in the destination machine.</span></span>  
  
    2.  <span data-ttu-id="976e5-130">Quindi, creare un database con i file di dati e di log che puntano ai file esistenti in archiviazione di Azure usando l'opzione FOR Connetti.</span><span class="sxs-lookup"><span data-stu-id="976e5-130">Then, create a database with data and log files pointing to the existing files in Azure Storage by using FOR ATTACH option.</span></span> <span data-ttu-id="976e5-131">Nella finestra di query, eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="976e5-131">In the query window, run the following statement:</span></span>  
  
        ```sql  
  
        --Create a database on the destination server   
        CREATE DATABASE TestDB1onDest   
        ON   
        (NAME = TestDB1_data,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf' )   
        LOG ON   
         (NAME = TestDB1_log,   
            FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
        FOR ATTACH   
        GO  
  
        ```  
  
    3.  <span data-ttu-id="976e5-132">In Esplora oggetti, fare clic su Database, quindi fare clic con il pulsante destro del mouse su Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="976e5-132">On the Object Explorer, click Databases, right-click Refresh.</span></span> <span data-ttu-id="976e5-133">Sarà possibile vedere nell'elenco il nuovo database creato TestDB1onDest.</span><span class="sxs-lookup"><span data-stu-id="976e5-133">You should be able to see the newly created database TestDB1onDest listed.</span></span>  
  
    4.  <span data-ttu-id="976e5-134">Quindi, nella finestra di query eseguire l'istruzione seguente:</span><span class="sxs-lookup"><span data-stu-id="976e5-134">Next, run the following statement in the query window:</span></span>  
  
        ```sql  
  
        USE TestDB1onDest   
        SELECT * FROM Table1;   
        GO  
  
        ```  
  
         <span data-ttu-id="976e5-135">Vengono elencati tutti i dati immessi nella lezione 4.</span><span class="sxs-lookup"><span data-stu-id="976e5-135">This should list all the data you entered in Lesson 4.</span></span>  
  
 <span data-ttu-id="976e5-136">Si noti che il database crittografato è stato trasferito in un'altra istanza di calcolo senza spostamento di dati.</span><span class="sxs-lookup"><span data-stu-id="976e5-136">Note that the encrypted database was transferred to another compute instance with no data movement.</span></span>  
  
 <span data-ttu-id="976e5-137">Per creare un database con file di dati e di log che puntano ai file esistenti in archiviazione di Azure usando SQL Server Management Studio interfaccia utente, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="976e5-137">To create a database with data and log files pointing to the existing files in Azure Storage using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="976e5-138">In **Esplora oggetti**connettersi a un'istanza del motore di database di SQL Server e, successivamente, espanderla.</span><span class="sxs-lookup"><span data-stu-id="976e5-138">In **Object Explorer**, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="976e5-139">Fare clic con il pulsante destro del mouse su **Database**, quindi scegliere **Nuovo database**.</span><span class="sxs-lookup"><span data-stu-id="976e5-139">Right-click **Databases**, and then click **New Database**.</span></span> <span data-ttu-id="976e5-140">Quindi, fare clic con il pulsante destro del mouse su TestDB1.</span><span class="sxs-lookup"><span data-stu-id="976e5-140">Then, right-click TestDB1.</span></span> <span data-ttu-id="976e5-141">Fare clic su Attività e quindi su Scollega.</span><span class="sxs-lookup"><span data-stu-id="976e5-141">Click Tasks, and then click Detach.</span></span> <span data-ttu-id="976e5-142">Nella finestra di dialogo Scollega, selezionare Interrompi connessioni.</span><span class="sxs-lookup"><span data-stu-id="976e5-142">In the Detach dialog window, check Drop Connections.</span></span> <span data-ttu-id="976e5-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="976e5-143">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="976e5-144">Connettersi al computer di destinazione con SQL Server 2014 CTP2 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="976e5-144">Connect to the destination machine, which has SQL Server 2014 CTP2 or later.</span></span> <span data-ttu-id="976e5-145">Per preparare il computer di destinazione, è necessario creare una credenziale di SQL Server nel computer di destinazione che punti allo stesso contenitore in cui è stato inserito TestDB1.</span><span class="sxs-lookup"><span data-stu-id="976e5-145">To prepare your destination machine, you need to create a SQL Server credential in the destination machine to point to the same container that you put TestDB1 in.</span></span> <span data-ttu-id="976e5-146">Se si intende eseguire il collegamento di nuovo nello stesso computer, non è necessario creare un'altra credenziale.</span><span class="sxs-lookup"><span data-stu-id="976e5-146">If you are going to re-attach in the same computer, you do not need to create another credential.</span></span>  
  
4.  <span data-ttu-id="976e5-147">In **Esplora oggetti**fare clic con il pulsante destro del mouse su **Database** , quindi fare clic su **Collega**.</span><span class="sxs-lookup"><span data-stu-id="976e5-147">In **Object Explorer**, right-click **Databases** and click **Attach**.</span></span>  
  
5.  <span data-ttu-id="976e5-148">Nella finestra di dialogo **Collega database** scegliere **Aggiungi**per specificare il database da collegare.</span><span class="sxs-lookup"><span data-stu-id="976e5-148">In the **Attach Databases** dialog box, to specify the database to be attached, click **Add**.</span></span> <span data-ttu-id="976e5-149">Nella finestra di dialogo **Individua file di database** :</span><span class="sxs-lookup"><span data-stu-id="976e5-149">In the **Locate Database Files** dialog window:</span></span>  
  
     <span data-ttu-id="976e5-150">Per il percorso del file di dati del database, digitare: `https://teststorageaccnt.blob.core.windows.net/testcontainer/` .</span><span class="sxs-lookup"><span data-stu-id="976e5-150">For Database Data File Location, type: `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span>  
  
     <span data-ttu-id="976e5-151">Per nome file, digitare: `TestDB1Data.mdf` .</span><span class="sxs-lookup"><span data-stu-id="976e5-151">For File name, type: `TestDB1Data.mdf`.</span></span>  
  
6.  <span data-ttu-id="976e5-152">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="976e5-152">Click **OK**.</span></span>  
  
     <span data-ttu-id="976e5-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="976e5-153">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-6-7.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="976e5-154">**Lezione successiva:**</span><span class="sxs-lookup"><span data-stu-id="976e5-154">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="976e5-155">Lezione 7: Spostare i file di dati in Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="976e5-155">Lesson 7: Move your data files to Azure Storage</span></span>](../relational-databases/lesson-6-generate-activity-and-backup-log-using-file-snapshot-backup.md)  
  
