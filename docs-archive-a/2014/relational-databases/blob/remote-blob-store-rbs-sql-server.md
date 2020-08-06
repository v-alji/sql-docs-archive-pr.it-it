---
title: Archivio Blob remoto (RBS) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- Remote Blob Store (RBS) [SQL Server]
- RBS (Remote Blob Store) [SQL Server]
ms.assetid: 31c947cf-53e9-4ff4-939b-4c1d034ea5b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f3425474ec3b9013355536424ffcf55d9426b9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712048"
---
# <a name="remote-blob-store-rbs-sql-server"></a><span data-ttu-id="de631-102">Archivio Blob remoto (RBS) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="de631-102">Remote Blob Store (RBS) (SQL Server)</span></span>
  <span data-ttu-id="de631-103">Archivio BLOB remoti (RBS) di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è un componente aggiuntivo facoltativo che consente agli amministratori di database di archiviare oggetti binari di grandi dimensioni in soluzioni di archiviazione apposite anziché direttamente nel server di database principale.</span><span class="sxs-lookup"><span data-stu-id="de631-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Remote BLOB Store (RBS) is an optional add-on component that lets database administrators store binary large objects in commodity storage solutions instead of directly on the main database server.</span></span>  
  
 <span data-ttu-id="de631-104">Tale componente è incluso nei supporti di installazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] ma non viene installato dal programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="de631-104">RBS is included on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
 <span data-ttu-id="de631-105">Per altre informazioni su RBS, vedere [Risorse di RBS](#rbsresources) in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="de631-105">For more information about RBS, see [RBS Resources](#rbsresources) in this topic.</span></span>  
  
## <a name="benefits-of-rbs"></a><span data-ttu-id="de631-106">Vantaggi di RBS</span><span class="sxs-lookup"><span data-stu-id="de631-106">Benefits of RBS</span></span>  
 <span data-ttu-id="de631-107">RBS offre i seguenti vantaggi:</span><span class="sxs-lookup"><span data-stu-id="de631-107">RBS provides the following benefits:</span></span>  
  
### <a name="optimized-database-storage-and-performance"></a><span data-ttu-id="de631-108">Archiviazione e prestazioni ottimizzate del database</span><span class="sxs-lookup"><span data-stu-id="de631-108">Optimized database storage and performance</span></span>  
 <span data-ttu-id="de631-109">L'archiviazione di BLOB nel database può utilizzare grandi quantità di spazio file e risorse server costose.</span><span class="sxs-lookup"><span data-stu-id="de631-109">Storing BLOBs in the database can consume large amounts of file space and expensive server resources.</span></span> <span data-ttu-id="de631-110">RBS consente di trasferire in modo efficiente BLOB in una soluzione di archiviazione dedicata selezionata e di archiviare i relativi riferimenti nel database.</span><span class="sxs-lookup"><span data-stu-id="de631-110">RBS efficiently transfers the BLOBs to a dedicated storage solution of your choosing, and stores references to them in the database.</span></span> <span data-ttu-id="de631-111">In questo modo vengono liberate l'archiviazione su server per i dati strutturati e le risorse server per le operazioni del database.</span><span class="sxs-lookup"><span data-stu-id="de631-111">This frees server storage for structured data, and frees server resources for database operations.</span></span>  
  
### <a name="efficient-management-of-blobs"></a><span data-ttu-id="de631-112">Gestione efficiente di BLOB</span><span class="sxs-lookup"><span data-stu-id="de631-112">Efficient management of BLOBs</span></span>  
 <span data-ttu-id="de631-113">Diverse funzionalità di RBS supportano la gestione semplice di BLOB archiviati:</span><span class="sxs-lookup"><span data-stu-id="de631-113">Several RBS features support the convenient management of stored BLOBs:</span></span>  
  
-   <span data-ttu-id="de631-114">BLOB gestiti con transazioni ACID (Atomic Consistency Isolation Durable).</span><span class="sxs-lookup"><span data-stu-id="de631-114">BLOBS are managed with ACID (atomic consistency isolation durable) transactions.</span></span>  
  
-   <span data-ttu-id="de631-115">BLOB organizzati in raccolte.</span><span class="sxs-lookup"><span data-stu-id="de631-115">BLOBs are organized into collections.</span></span>  
  
-   <span data-ttu-id="de631-116">Garbage Collection, verifica coerenza e altre funzioni di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="de631-116">Garbage collection, consistency checking, and other maintenance functions are included.</span></span>  
  
### <a name="standardized-api"></a><span data-ttu-id="de631-117">API standardizzata</span><span class="sxs-lookup"><span data-stu-id="de631-117">Standardized API</span></span>  
 <span data-ttu-id="de631-118">RBS definisce un set di API che fornisce un modello di programmazione standardizzato affinché le applicazioni possano accedere e modificare gli archivi BLOB.</span><span class="sxs-lookup"><span data-stu-id="de631-118">RBS defines a set of APIs that provide a standardized programming model for applications to access and modify any BLOB store.</span></span> <span data-ttu-id="de631-119">Ogni archivio BLOB può specificare la propria libreria del provider che consente il collegamento alla libreria client di RBS e di specificare la modalità di archiviazione e accesso ai BLOB.</span><span class="sxs-lookup"><span data-stu-id="de631-119">Each BLOB store can specify its own provider library, which plugs into the RBS client library and specifies how BLOBs are stored and accessed.</span></span>  
  
 <span data-ttu-id="de631-120">Molti fornitori di soluzioni di archiviazione di terze parti hanno sviluppato provider RBS conformi a queste API standard e in grado di supportare l'archiviazione BLOB su varie piattaforme di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="de631-120">A number of third-party storage solution vendors have developed RBS providers that conform to these standard APIs and support BLOB storage on various storage platforms.</span></span>  
  
## <a name="rbs-requirements"></a><span data-ttu-id="de631-121">Requisiti di RBS</span><span class="sxs-lookup"><span data-stu-id="de631-121">RBS Requirements</span></span>  
 <span data-ttu-id="de631-122">Per RBS è necessaria l'edizione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise per il server di database principale in cui vengono archiviati i metadati BLOB.</span><span class="sxs-lookup"><span data-stu-id="de631-122">RBS requires [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise for the main database server in which the BLOB metadata is stored.</span></span> <span data-ttu-id="de631-123">Tuttavia, se si utilizza il provider FILESTREAM fornito, è possibile archiviare BLOB nell'edizione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard.</span><span class="sxs-lookup"><span data-stu-id="de631-123">However, if you use the supplied FILESTREAM provider, you can store the BLOBs themselves on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard.</span></span>  
  
 <span data-ttu-id="de631-124">In RBS è incluso un provider FILESTREAM che consente di utilizzare tale componente per l'archiviazione di BLOB in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de631-124">RBS includes a FILESTREAM provider that lets you use RBS to store BLOBs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="de631-125">Se si desidera utilizzare RBS per l'archiviazione di BLOB in una soluzione di archiviazione diversa, è necessario utilizzare un provider RBS di terze parti sviluppato per tale soluzione di archiviazione o sviluppare un provider RBS personalizzato utilizzando l'API di RBS.</span><span class="sxs-lookup"><span data-stu-id="de631-125">If you want use RBS to store BLOBs in a different storage solution, you have to use a third party RBS provider developed for that storage solution, or develop a custom RBS provider using the RBS API.</span></span> <span data-ttu-id="de631-126">Un provider di esempio che consenta di archiviare BLOB nel file system NTFS è disponibile come risorsa per l'apprendimento in [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190).</span><span class="sxs-lookup"><span data-stu-id="de631-126">A sample provider that stores BLOBs in the NTFS file system is available as a learning resource on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190).</span></span>  
  
## <a name="rbs-security"></a><span data-ttu-id="de631-127">Sicurezza relativa a RBS</span><span class="sxs-lookup"><span data-stu-id="de631-127">RBS Security</span></span>  
 <span data-ttu-id="de631-128">Quando si utilizza un provider personalizzato per archiviare BLOB esterni a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile che siano disponibili altri processi che consentono di ignorare il sistema di sicurezza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de631-128">When you use a custom provider to store BLOBs outside of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they may be available to other processes that bypass the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security system.</span></span> <span data-ttu-id="de631-129">Accertarsi di proteggere i BLOB archiviati con autorizzazioni e opzioni di crittografia adatte al supporto di archiviazione utilizzato dal provider personalizzato.</span><span class="sxs-lookup"><span data-stu-id="de631-129">Make sure that you protect the stored BLOBs with permissions and encryption options that are appropriate to the storage medium used by the custom provider.</span></span>  
  
##  <a name="rbs-resources"></a><a name="rbsresources"></a><span data-ttu-id="de631-130">Risorse di RBS</span><span class="sxs-lookup"><span data-stu-id="de631-130">RBS Resources</span></span>  
 <span data-ttu-id="de631-131">**Documentazione di RBS**</span><span class="sxs-lookup"><span data-stu-id="de631-131">**RBS documentation**</span></span>  
 <span data-ttu-id="de631-132">La documentazione di RBS è inclusa nel pacchetto di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="de631-132">The RBS documentation is included in the Windows installer package.</span></span> <span data-ttu-id="de631-133">Per consultare la documentazione di RBS senza installare tale componente, è possibile visualizzare la versione [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] della documentazione[ disponibile online in MSDN Library](https://go.microsoft.com/fwlink/?LinkId=210192).</span><span class="sxs-lookup"><span data-stu-id="de631-133">If you want to review the RBS documentation without installing RBS, you can view the [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] version of the documentation [online in the MSDN Library](https://go.microsoft.com/fwlink/?LinkId=210192).</span></span>  
  
 <span data-ttu-id="de631-134">**White paper su RBS**</span><span class="sxs-lookup"><span data-stu-id="de631-134">**RBS white paper**</span></span>  
 <span data-ttu-id="de631-135">Il [white paper sull'archiviazione di BLOB remoti](https://go.microsoft.com/fwlink/?LinkId=210422), disponibile per il download come documento di Microsoft Word, contiene informazioni dettagliate sull'installazione e la configurazione di RBS.</span><span class="sxs-lookup"><span data-stu-id="de631-135">The white paper "[Remote BLOB Storage](https://go.microsoft.com/fwlink/?LinkId=210422)", which is available for download as a Microsoft Word document, provides detailed information about installing and configuring RBS.</span></span>  
  
 <span data-ttu-id="de631-136">**Esempi di RBS**</span><span class="sxs-lookup"><span data-stu-id="de631-136">**RBS samples**</span></span>  
 <span data-ttu-id="de631-137">Negli esempi di RBS disponibili in [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190) viene illustrato come sviluppare un'applicazione RBS e come sviluppare e installare un provider RBS personalizzato.</span><span class="sxs-lookup"><span data-stu-id="de631-137">The RBS samples available on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190) demonstrate how to develop an RBS application, and how to develop and install a custom RBS provider.</span></span>  
  
 <span data-ttu-id="de631-138">**Blog di RBS**</span><span class="sxs-lookup"><span data-stu-id="de631-138">**RBS blog**</span></span>  
 <span data-ttu-id="de631-139">Nel [blog di RBS](https://go.microsoft.com/fwlink/?LinkId=210315) sono disponibili informazioni aggiuntive sulla distribuzione e gestione di RBS.</span><span class="sxs-lookup"><span data-stu-id="de631-139">The [RBS blog](https://go.microsoft.com/fwlink/?LinkId=210315) provides additional information to help you understand, deploy, and maintain RBS.</span></span>  
  
  
