---
title: 'Lezione 4: creare un database in archiviazione di Azure | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a9ae1501-b614-49d3-b975-6569da8350b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 50fca85111d5897b738e577e7735049e0b055a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637295"
---
# <a name="lesson-4-create-a-database-in-azure-storage"></a><span data-ttu-id="36a6b-102">Lezione 4: Creare un database in Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="36a6b-102">Lesson 4: Create a database in Azure Storage</span></span>
  <span data-ttu-id="36a6b-103">In questa lezione verrà illustrato come creare un database usando la funzionalità file di dati di SQL Server in Azure.</span><span class="sxs-lookup"><span data-stu-id="36a6b-103">In this lesson, you will learn how to create a database using the SQL Server Data Files in Azure feature.</span></span> <span data-ttu-id="36a6b-104">Si noti che prima di questa lezione, è necessario aver completato le lezioni 1, 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="36a6b-104">Note that before this lesson, you must complete the Lesson 1, 2, and 3.</span></span> <span data-ttu-id="36a6b-105">La lezione 3 è un passaggio molto importante perché è necessario archiviare le informazioni sul contenitore di archiviazione di Azure e il nome dei criteri e la chiave SAS associati nell'archivio delle credenziali SQL Server prima della lezione 4.</span><span class="sxs-lookup"><span data-stu-id="36a6b-105">Lesson 3 is a very important step because you need to store the information about your Azure storage container and its associated policy name and SAS key in the SQL Server credential store before Lesson 4.</span></span>  
  
 <span data-ttu-id="36a6b-106">Per ogni contenitore di archiviazione utilizzato da un file di dati o di log, è necessario creare una credenziale di SQL Server il cui nome corrisponda al percorso del contenitore.</span><span class="sxs-lookup"><span data-stu-id="36a6b-106">For each storage container used by a data or log file, you must create a SQL Server Credential whose name matches the container path.</span></span> <span data-ttu-id="36a6b-107">Quindi, è possibile creare un nuovo database in archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="36a6b-107">Then, you can create a new database in Azure Storage</span></span>  
  
 <span data-ttu-id="36a6b-108">Per questa lezione si presuppone che l'utente abbia già completato i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="36a6b-108">This lesson assumes that you already completed the following steps:</span></span>  
  
-   <span data-ttu-id="36a6b-109">Si ha un account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="36a6b-109">You have an Azure Storage account.</span></span>  
  
-   <span data-ttu-id="36a6b-110">È stato creato un contenitore nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="36a6b-110">You have created a container under your Azure Storage account.</span></span>  
  
-   <span data-ttu-id="36a6b-111">Creazione dei criteri in un contenitore con diritti di lettura, scrittura ed elenco.</span><span class="sxs-lookup"><span data-stu-id="36a6b-111">You have created a policy on a container with read, write, and list rights.</span></span> <span data-ttu-id="36a6b-112">Generazione di una chiave SAS.</span><span class="sxs-lookup"><span data-stu-id="36a6b-112">You also generated a SAS key.</span></span>  
  
-   <span data-ttu-id="36a6b-113">Creazione di una credenziale di SQL Server nel computer di origine.</span><span class="sxs-lookup"><span data-stu-id="36a6b-113">You have created a SQL Server credential on the source machine.</span></span>  
  
 <span data-ttu-id="36a6b-114">Per creare un database in Azure usando la funzionalità SQL Server i file di dati in archiviazione di Azure, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="36a6b-114">To create a database in Azure using the SQL Server Data Files in Azure Storage feature, follow these steps:</span></span>  
  
1.  <span data-ttu-id="36a6b-115">Connettersi a SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="36a6b-115">Connect to SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="36a6b-116">In Esplora oggetti connettersi all'istanza del motore di database installato.</span><span class="sxs-lookup"><span data-stu-id="36a6b-116">In Object Explorer, connect to the instance of Database Engine installed.</span></span>  
  
3.  <span data-ttu-id="36a6b-117">Sulla barra degli strumenti Standard fare clic su Nuova query.</span><span class="sxs-lookup"><span data-stu-id="36a6b-117">On the Standard tool bar, click New Query.</span></span>  
  
4.  <span data-ttu-id="36a6b-118">Copiare e incollare l'esempio seguente nella finestra Query e modificare se necessario.</span><span class="sxs-lookup"><span data-stu-id="36a6b-118">Copy and paste the following example into the query window, modify as needed.</span></span> <span data-ttu-id="36a6b-119">Si noti che il campo FILENAME fa riferimento al percorso URI del file di database nel contenitore di archiviazione e deve iniziare con HTTPS.</span><span class="sxs-lookup"><span data-stu-id="36a6b-119">Note that the FILENAME field refers to the URI path of the database file in storage container and it must start with https.</span></span>  
  
    ```  
  
    --Create a database that uses a SQL Server credential    
    CREATE DATABASE TestDB1    
    ON   
    (NAME = TestDB1_data,   
       FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Data.mdf')   
     LOG ON   
    (NAME = TestDB1_log,   
        FILENAME = 'https://teststorageaccnt.blob.core.windows.net/testcontainer/TestDB1Log.ldf')   
    GO  
  
    ```  
  
     <span data-ttu-id="36a6b-120">Aggiungere alcuni dati al database.</span><span class="sxs-lookup"><span data-stu-id="36a6b-120">Add some data to your database.</span></span>  
  
    ```  
  
    USE TestDB1;   
    GO   
    CREATE TABLE Table1 (Col1 int primary key, Col2 varchar(20));   
    GO   
    INSERT INTO Table1 (Col1, Col2) VALUES (1, 'string1'), (2, 'string2');   
    GO  
  
    ```  
  
5.  <span data-ttu-id="36a6b-121">Per visualizzare il nuovo TestDB1 nell'istanza locale di SQL Server, aggiornare i database in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="36a6b-121">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span>  
  
6.  <span data-ttu-id="36a6b-122">Analogamente, per vedere il nuovo database creato nell'account di archiviazione, connettersi all'account di archiviazione tramite SQL Server Management Studio (SSMS).</span><span class="sxs-lookup"><span data-stu-id="36a6b-122">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS).</span></span> <span data-ttu-id="36a6b-123">Per informazioni su come connettersi a una risorsa di archiviazione di Azure usando SQL Server Management Studio, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="36a6b-123">For information on how to connect to an Azure storage using SQL Server Management Studio, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="36a6b-124">Innanzitutto, ottenere le informazioni sull'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="36a6b-124">First, get the storage account information.</span></span> <span data-ttu-id="36a6b-125">Accedere al portale di gestione.</span><span class="sxs-lookup"><span data-stu-id="36a6b-125">Log in to the Management Portal.</span></span> <span data-ttu-id="36a6b-126">Successivamente, fare clic su **Archiviazione** e scegliere l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="36a6b-126">Then, click **Storage** and choose your storage account.</span></span> <span data-ttu-id="36a6b-127">Una volta selezionato un account di archiviazione, fare clic su **Gestisci chiavi di accesso** nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="36a6b-127">When a storage account is selected, click **Manage Access Keys** at the bottom of the page.</span></span> <span data-ttu-id="36a6b-128">Verrà aperta una finestra di dialogo simile:</span><span class="sxs-lookup"><span data-stu-id="36a6b-128">This opens a similar dialog window:</span></span>  
  
         <span data-ttu-id="36a6b-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="36a6b-129">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-1.gif "SQL 14 CTP2")</span></span>  
  
    2.  <span data-ttu-id="36a6b-130">Copiare i valori di **nome account di archiviazione** e **chiave di accesso primaria** nella finestra di dialogo **Connetti ad archiviazione di Azure** in SSMS.</span><span class="sxs-lookup"><span data-stu-id="36a6b-130">Copy the **Storage Account Name** and **Primary Access Key** values to the **Connect to Azure Storage** dialog window in SSMS.</span></span> <span data-ttu-id="36a6b-131">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="36a6b-131">Then, click **Connect**.</span></span> <span data-ttu-id="36a6b-132">In questo modo le informazioni sui contenitori di account di archiviazione vengono portate in SSMS come illustrato nella schermata seguente:</span><span class="sxs-lookup"><span data-stu-id="36a6b-132">This brings the information about storage account containers to SSMS as shown in the following screenshot:</span></span>  
  
         <span data-ttu-id="36a6b-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="36a6b-133">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="36a6b-134">Lo screenshot seguente illustra il nuovo database creato nell'ambiente locale e in quello di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="36a6b-134">The following screenshot demonstrates the new created database both in on-premises and Azure Storage environment.</span></span>  
  
 <span data-ttu-id="36a6b-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="36a6b-135">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-2b.gif "SQL 14 CTP2")</span></span>  
  
 <span data-ttu-id="36a6b-136">**Nota:** Se sono presenti riferimenti attivi ai file di dati in un contenitore, qualsiasi tentativo di eliminare la credenziale associata di SQL Server non riesce.</span><span class="sxs-lookup"><span data-stu-id="36a6b-136">**Note:** If there are any active references to data files in a container, any attempts to delete the associated SQL Server credential fails.</span></span> <span data-ttu-id="36a6b-137">Analogamente, se esiste già un lease in un file di database specifico in un BLOB e si desidera eliminarlo, è necessario innanzitutto arrestare il lease nel BLOB.</span><span class="sxs-lookup"><span data-stu-id="36a6b-137">Similarly, if there is already a lease on a specific database file in a blob and you want to delete it, first you need to break the lease on the blob.</span></span> <span data-ttu-id="36a6b-138">Per interrompere il lease, è possibile usare [Lease Blob](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span><span class="sxs-lookup"><span data-stu-id="36a6b-138">To break the lease, you can use [Lease Blob](https://msdn.microsoft.com/library/azure/ee691972.aspx).</span></span>  
  
 <span data-ttu-id="36a6b-139">Con questa nuova funzionalità, è possibile configurare SQL Server in modo che qualsiasi istruzione CREATE DATABASE imposta come valore predefinito un database abilitato al cloud.</span><span class="sxs-lookup"><span data-stu-id="36a6b-139">Using this new feature, you can configure SQL Server so that any CREATE DATABASE statement will default to a cloud enabled database.</span></span> <span data-ttu-id="36a6b-140">In altre parole, è possibile impostare i percorsi predefiniti di log e dati nelle proprietà dell'istanza di SQL Server Management Studio Server in modo che ogni volta che si crea un database, tutti i file di database (con estensione MDF e ldf) vengono creati come BLOB di pagine in archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="36a6b-140">In other words, you can set default data and log locations in SQL Server Management Studio Server instance properties so anytime you create a database, all database files (.mdf, .ldf) are created as page blobs in Azure Storage.</span></span>  
  
 <span data-ttu-id="36a6b-141">Per creare un database in archiviazione di Azure usando SQL Server Management Studio interfaccia utente, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="36a6b-141">To create a database in Azure Storage by using SQL Server Management Studio user interface, perform these steps:</span></span>  
  
1.  <span data-ttu-id="36a6b-142">In Esplora oggetti, connettersi a un'istanza del motore di database di SQL Server ed espanderla.</span><span class="sxs-lookup"><span data-stu-id="36a6b-142">In Object Explorer, connect to an instance of the SQL Server Database Engine and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="36a6b-143">Fare clic con il pulsante destro del mouse su Database, quindi scegliere Nuovo database.</span><span class="sxs-lookup"><span data-stu-id="36a6b-143">Right-click Databases, and then click New Database.</span></span>  
  
3.  <span data-ttu-id="36a6b-144">Nella finestra di dialogo Nuovo database digitare un nome di database.</span><span class="sxs-lookup"><span data-stu-id="36a6b-144">In the New Database dialog window, type a database name.</span></span>  
  
4.  <span data-ttu-id="36a6b-145">Modificare i valori predefiniti dei file di dati primario e di log delle transazioni, fare clic sulla cella appropriata nella griglia File di database, quindi immettere il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="36a6b-145">Change the default values of the primary data and transaction log files, in the Database files grid, click the appropriate cell and enter the new value.</span></span> <span data-ttu-id="36a6b-146">Specificare inoltre il percorso per la posizione del file.</span><span class="sxs-lookup"><span data-stu-id="36a6b-146">Also, specify the path for the file location.</span></span> <span data-ttu-id="36a6b-147">Per il percorso, digitare il percorso URL del contenitore di archiviazione, ad esempio `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span><span class="sxs-lookup"><span data-stu-id="36a6b-147">For Path, type the URL path of the storage container, such as `https://teststorageaccnt.blob.core.windows.net/testcontainer/`.</span></span> <span data-ttu-id="36a6b-148">Per FileName, digitare i nomi dei file fisici dei file di database (con estensione mdf e ldf).</span><span class="sxs-lookup"><span data-stu-id="36a6b-148">For FileName, type the physical file names of the database files (.mdf, .ldf).</span></span>  
  
     <span data-ttu-id="36a6b-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span><span class="sxs-lookup"><span data-stu-id="36a6b-149">![SQL 14 CTP2](../tutorials/media/ss-was-tutlesson-4-6-4.gif "SQL 14 CTP2")</span></span>  
  
     <span data-ttu-id="36a6b-150">Per ulteriori informazioni, vedere [Aggiungere file di dati o file di log a un database](databases/add-data-or-log-files-to-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="36a6b-150">For more information, see [Add Data or Log Files to a Database](databases/add-data-or-log-files-to-a-database.md).</span></span>  
  
5.  <span data-ttu-id="36a6b-151">Mantenere tutti gli altri valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="36a6b-151">Keep all other default values.</span></span>  
  
6.  <span data-ttu-id="36a6b-152">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="36a6b-152">Click OK.</span></span>  
  
 <span data-ttu-id="36a6b-153">Per visualizzare il nuovo TestDB1 nell'istanza locale di SQL Server, aggiornare i database in Esplora oggetti.</span><span class="sxs-lookup"><span data-stu-id="36a6b-153">To see the new TestDB1 in your on-premises SQL Server, refresh databases in the Object Explorer.</span></span> <span data-ttu-id="36a6b-154">Analogamente, per visualizzare il database appena creato nell'account di archiviazione, connettersi all'account di archiviazione tramite SQL Server Management Studio (SSMS) come illustrato precedentemente in questa lezione.</span><span class="sxs-lookup"><span data-stu-id="36a6b-154">Similarly, to see the newly created database in your storage account, connect to your storage account via SQL Server Management Studio (SSMS) as explained earlier in this lesson.</span></span>  
  
 <span data-ttu-id="36a6b-155">**Lezione successiva:**</span><span class="sxs-lookup"><span data-stu-id="36a6b-155">**Next Lesson:**</span></span>  
  
 [<span data-ttu-id="36a6b-156">Lezione 5. &#40;facoltativo&#41; crittografare il database tramite Transparent Data Encryption</span><span class="sxs-lookup"><span data-stu-id="36a6b-156">Lesson 5. &#40;Optional&#41; Encrypt your database using TDE</span></span>](../relational-databases/lesson-4-restore-database-to-virtual-machine-from-url.md)  
  
  
