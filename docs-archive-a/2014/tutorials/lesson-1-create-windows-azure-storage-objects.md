---
title: 'Lezione 1: creare oggetti di archiviazione di Azure | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 74edd1fd-ab00-46f7-9e29-7ba3f1a446c5
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d46c6d22ffd92dbf8035bff140960af8ef56122d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625102"
---
# <a name="lesson-1-create-azure-storage-objects"></a><span data-ttu-id="4f66f-102">Lezione 1: Creare oggetti di Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="4f66f-102">Lesson 1: Create Azure Storage Objects</span></span>
  <span data-ttu-id="4f66f-103">Prima di creare i backup di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nell'archiviazione del cloud, è necessario creare prima un account di archiviazione e, successivamente, un contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="4f66f-103">Before you can create [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backups on cloud storage, you must first create a storage account, and then a blob container.</span></span> <span data-ttu-id="4f66f-104">Nella lezione 1 vengono illustrati i passaggi per accedere al portale di gestione di Azure, creando un account di archiviazione e un contenitore BLOB.</span><span class="sxs-lookup"><span data-stu-id="4f66f-104">Lesson 1 walks you through the steps of Logging into the Azure Management Portal, creating a storage account and a blob container.</span></span>  
  
## <a name="create-a-storage-account"></a><span data-ttu-id="4f66f-105">Creare un account di archiviazione</span><span class="sxs-lookup"><span data-stu-id="4f66f-105">Create a storage Account</span></span>  
 <span data-ttu-id="4f66f-106">Per creare un account di archiviazione dal portale di gestione di Azure, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="4f66f-106">To create a storage account from the Azure Management Portal, use the following steps:</span></span>  
  
1.  <span data-ttu-id="4f66f-107">Accedere al portale di gestione di Azure utilizzando il proprio account.</span><span class="sxs-lookup"><span data-stu-id="4f66f-107">Log in to the Azure Management Portal using your account.</span></span> <span data-ttu-id="4f66f-108">Se non si dispone di un account Azure, [visitare la versione di valutazione gratuita di 3 mesi di Azure](https://go.microsoft.com/fwlink/?LinkId=271927).</span><span class="sxs-lookup"><span data-stu-id="4f66f-108">If you do not have an Azure account, [visit Azure 3-Month free trial](https://go.microsoft.com/fwlink/?LinkId=271927).</span></span>  
  
     <span data-ttu-id="4f66f-109">![Schermata di accesso di Azure](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Schermata di accesso di Azure")</span><span class="sxs-lookup"><span data-stu-id="4f66f-109">![Azure Login Screen](../../2014/tutorials/media/windowazurelogin-backuptocloud.gif "Azure Login Screen")</span></span>  
  
2.  <span data-ttu-id="4f66f-110">Per creare un account di archiviazione, seguire le istruzioni dettagliate riportate in [questo](https://go.microsoft.com/fwlink/?LinkId=271926)articolo.</span><span class="sxs-lookup"><span data-stu-id="4f66f-110">Use the step by step instructions detailed [here](https://go.microsoft.com/fwlink/?LinkId=271926), to create a storage account.</span></span>  
  
3.  <span data-ttu-id="4f66f-111">Passare all'account di archiviazione creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="4f66f-111">Browse to the storage account you created in previous step.</span></span> <span data-ttu-id="4f66f-112">Dal centro inferiore della pagina Web fare clic su **Gestisci chiavi**.</span><span class="sxs-lookup"><span data-stu-id="4f66f-112">From the bottom center of the web page, click **MANAGE KEYS**.</span></span> <span data-ttu-id="4f66f-113">Verranno visualizzate le informazioni sull'account.</span><span class="sxs-lookup"><span data-stu-id="4f66f-113">The account information is displayed.</span></span> <span data-ttu-id="4f66f-114">Copiare il nome dell'account di archiviazione e le chiavi di accesso.</span><span class="sxs-lookup"><span data-stu-id="4f66f-114">Copy the storage account name, and the Access Keys.</span></span> <span data-ttu-id="4f66f-115">Queste informazioni sono necessarie per creare le credenziali archiviate di SQL.</span><span class="sxs-lookup"><span data-stu-id="4f66f-115">This information is required to create SQL Stored Credentials.</span></span> <span data-ttu-id="4f66f-116">In [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queste informazioni vengono utilizzate per accedere all'account di archiviazione e per creare i backup.</span><span class="sxs-lookup"><span data-stu-id="4f66f-116">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] uses this information to access the storage account and create backups.</span></span>  
  
     <span data-ttu-id="4f66f-117">![Screenshot delle chiavi dell'account di archiviazione di Azure](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Screenshot delle chiavi dell'account di archiviazione di Azure")</span><span class="sxs-lookup"><span data-stu-id="4f66f-117">![Screen shot of Azure Storage Account Keys](../../2014/tutorials/media/manageaccesskeys-backuptocloud.gif "Screen shot of Azure Storage Account Keys")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f66f-118">Inoltre, è possibile creare un account di archiviazione a livello di programmazione tramite le API REST.</span><span class="sxs-lookup"><span data-stu-id="4f66f-118">You can also create a storage account programmatically using REST APIs.</span></span> <span data-ttu-id="4f66f-119">Per altre informazioni, vedere [creare un account di archiviazione](https://go.microsoft.com/fwlink/?LinkId=271928).</span><span class="sxs-lookup"><span data-stu-id="4f66f-119">For more information, see [Create Storage Account](https://go.microsoft.com/fwlink/?LinkId=271928).</span></span>  
  
### <a name="create-a-blob-container"></a><span data-ttu-id="4f66f-120">Creare un contenitore BLOB</span><span class="sxs-lookup"><span data-stu-id="4f66f-120">Create a Blob Container</span></span>  
 <span data-ttu-id="4f66f-121">Un contenitore fornisce un raggruppamento di un set di BLOB.</span><span class="sxs-lookup"><span data-stu-id="4f66f-121">A container provides a grouping of a set of blobs.</span></span> <span data-ttu-id="4f66f-122">Tutti i BLOB devono essere inclusi in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="4f66f-122">All blobs must be in a container.</span></span> <span data-ttu-id="4f66f-123">Un account può contenere un numero illimitato di contenitori, tuttavia ne deve contenere almeno uno.</span><span class="sxs-lookup"><span data-stu-id="4f66f-123">An account can contain an unlimited number of containers, but must have at least one container.</span></span> <span data-ttu-id="4f66f-124">In un contenitore è possibile archiviare un numero illimitato di BLOB.</span><span class="sxs-lookup"><span data-stu-id="4f66f-124">A container can store an unlimited number of blobs.</span></span>  
  
 <span data-ttu-id="4f66f-125">Per creare un contenitore, attenersi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4f66f-125">To create a Container, use the following steps:</span></span>  
  
1.  <span data-ttu-id="4f66f-126">Selezionare l'account di archiviazione, fare clic sulla scheda **contenitori** , quindi su **Aggiungi contenitore** nella parte inferiore della schermata che consente di aprire una nuova finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4f66f-126">Select the storage account, click the **CONTAINERS** tab and click **ADD CONTAINER** at the bottom of the screen which opens a new dialog box.</span></span>  
  
     <span data-ttu-id="4f66f-127">![Creazione di un contenitore nel portale di gestione](../../2014/tutorials/media/backuptocloud.gif "Creazione di un contenitore nel portale di gestione")</span><span class="sxs-lookup"><span data-stu-id="4f66f-127">![Creating a Container in the Management Portal](../../2014/tutorials/media/backuptocloud.gif "Creating a Container in the Management Portal")</span></span>  
  
2.  <span data-ttu-id="4f66f-128">Immettere il nome associato al contenitore.</span><span class="sxs-lookup"><span data-stu-id="4f66f-128">Enter the name for the container.</span></span> <span data-ttu-id="4f66f-129">Prendere nota del nome del contenitore specificato.</span><span class="sxs-lookup"><span data-stu-id="4f66f-129">Make a note of the container name you specified.</span></span> <span data-ttu-id="4f66f-130">Queste informazioni vengono utilizzate nell'URL (percorso del file di backup) nelle istruzioni T-SQL nelle lezioni 3 e 4.</span><span class="sxs-lookup"><span data-stu-id="4f66f-130">This information is used in the URL (path to backup file) in the T-SQL statements in lesson 3 and 4.</span></span>  
  
3.  <span data-ttu-id="4f66f-131">Selezionare privato per **tipo di accesso**.</span><span class="sxs-lookup"><span data-stu-id="4f66f-131">Select Private for **Access Type**.</span></span> <span data-ttu-id="4f66f-132">È consigliabile creare contenitori privati per proteggere i file di backup.</span><span class="sxs-lookup"><span data-stu-id="4f66f-132">We recommend creating private containers for securing your backup files.</span></span>  
  
     <span data-ttu-id="4f66f-133">![Creazione di un nuovo contenitore BLOB](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Creazione di un nuovo contenitore BLOB")</span><span class="sxs-lookup"><span data-stu-id="4f66f-133">![Creating a new blob container](../../2014/tutorials/media/backuptocloud-newblobcontainer.gif "Creating a new blob container")</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f66f-134">L'autenticazione per l'account di archiviazione è obbligatorio per il backup e ripristino di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] anche se si sceglie di creare un contenitore pubblico.</span><span class="sxs-lookup"><span data-stu-id="4f66f-134">Authentication to the storage account is required for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] backup and restore even if you choose to create a public container.</span></span>  
    >   
    >  <span data-ttu-id="4f66f-135">Inoltre, è possibile creare un contenitore a livello di programmazione tramite le API REST.</span><span class="sxs-lookup"><span data-stu-id="4f66f-135">You can also create a container programmatically using REST APIs.</span></span> <span data-ttu-id="4f66f-136">Per altre informazioni, vedere [create container](https://go.microsoft.com/fwlink/?LinkId=271946).</span><span class="sxs-lookup"><span data-stu-id="4f66f-136">For more information, see [Create Container](https://go.microsoft.com/fwlink/?LinkId=271946).</span></span>  
  
### <a name="next-lesson"></a><span data-ttu-id="4f66f-137">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="4f66f-137">Next Lesson</span></span>  
 <span data-ttu-id="4f66f-138">[Lezione 2: creare una credenziale SQL Server](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span><span class="sxs-lookup"><span data-stu-id="4f66f-138">[Lesson 2: Create a SQL Server Credential](../../2014/tutorials/lesson-2-create-a-sql-server-credential.md).</span></span>  
  
  
