---
title: Gestione di pacchetti e cartelle a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- enumerators [Integration Services]
- packages [Integration Services], managing
- custom enumerators [Integration Services]
ms.assetid: ec59b75d-ba09-44ac-9039-9d593bb462d9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 695ff4ad020dbdfb2564b4964a55324db4248517
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723983"
---
# <a name="managing-packages-and-folders-programmatically"></a><span data-ttu-id="dd7f9-102">Gestione di pacchetti e cartelle a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="dd7f9-102">Managing Packages and Folders Programmatically</span></span>
  <span data-ttu-id="dd7f9-103">Quando si utilizzano i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a livello di programmazione, può essere necessario determinare se un singolo pacchetto o cartella esiste oppure gestire le cartelle in cui i pacchetti sono archiviati.</span><span class="sxs-lookup"><span data-stu-id="dd7f9-103">As you work programmatically with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, you may want to determine whether an individual package or folder exists, or to manage the folders in which packages are stored.</span></span> <span data-ttu-id="dd7f9-104">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> dello spazio dei nomi <xref:Microsoft.SqlServer.Dts.Runtime> fornisce un'ampia varietà di metodi e classi per soddisfare questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="dd7f9-104">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides a variety of methods to satisfy these requirements.</span></span>  
  
##  <a name="determining-whether-a-package-or-folder-exists"></a><a name="exists"></a> <span data-ttu-id="dd7f9-105">Verifica dell'esistenza di un pacchetto o di una cartella</span><span class="sxs-lookup"><span data-stu-id="dd7f9-105">Determining Whether a Package or Folder Exists</span></span>  
 <span data-ttu-id="dd7f9-106">Per determinare a livello di programmazione se un pacchetto salvato esiste, chiamare uno dei metodi seguenti prima di tentare di caricarlo ed eseguirlo:</span><span class="sxs-lookup"><span data-stu-id="dd7f9-106">To determine programmatically whether a saved package exists, call one of the following methods before attempting to load and run the package:</span></span>  
  
|<span data-ttu-id="dd7f9-107">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="dd7f9-107">Storage Location</span></span>|<span data-ttu-id="dd7f9-108">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="dd7f9-108">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="dd7f9-109">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="dd7f9-109">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.ExistsOnSqlServer%2A>|  
  
 <span data-ttu-id="dd7f9-110">Per determinare a livello di programmazione se una cartella esiste, chiamare uno dei metodi seguenti prima di tentare di elencare i pacchetti archiviati al suo interno:</span><span class="sxs-lookup"><span data-stu-id="dd7f9-110">To determine programmatically whether a folder exists, call one of the following methods before attempting to list the packages stored in the folder, :</span></span>  
  
|<span data-ttu-id="dd7f9-111">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="dd7f9-111">Storage Location</span></span>|<span data-ttu-id="dd7f9-112">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="dd7f9-112">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="dd7f9-113">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="dd7f9-113">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.FolderExistsOnSqlServer%2A>|  
  

  
##  <a name="managing-packages-and-folders"></a><a name="managing"></a> <span data-ttu-id="dd7f9-114">Gestione di pacchetti e cartelle</span><span class="sxs-lookup"><span data-stu-id="dd7f9-114">Managing Packages and Folders</span></span>  
 <span data-ttu-id="dd7f9-115">La classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> dello spazio dei nomi <xref:Microsoft.SqlServer.Dts.Runtime> fornisce metodi aggiuntivi per la gestione dei pacchetti e delle cartelle in cui sono archiviati.</span><span class="sxs-lookup"><span data-stu-id="dd7f9-115">The <xref:Microsoft.SqlServer.Dts.Runtime.Application> class of the <xref:Microsoft.SqlServer.Dts.Runtime> namespace provides additional methods for managing packages and the folders in which they are stored.</span></span>  
  
###  <a name="removing-a-package"></a><a name="managing_rempkg"></a> <span data-ttu-id="dd7f9-116">Rimozione di un pacchetto</span><span class="sxs-lookup"><span data-stu-id="dd7f9-116">Removing a Package</span></span>  
 <span data-ttu-id="dd7f9-117">Per rimuovere un pacchetto salvato a livello di programmazione, chiamare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd7f9-117">To remove a saved package programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="dd7f9-118">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="dd7f9-118">Storage Location</span></span>|<span data-ttu-id="dd7f9-119">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="dd7f9-119">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="dd7f9-120">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="dd7f9-120">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFromSqlServer%2A>|  
  

  
###  <a name="creating-a-folder"></a><a name="managing_create"></a> <span data-ttu-id="dd7f9-121">Creazione di una cartella</span><span class="sxs-lookup"><span data-stu-id="dd7f9-121">Creating a Folder</span></span>  
 <span data-ttu-id="dd7f9-122">Per creare una cartella di archiviazione a livello di programmazione, chiamare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd7f9-122">To create a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="dd7f9-123">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="dd7f9-123">Storage Location</span></span>|<span data-ttu-id="dd7f9-124">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="dd7f9-124">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="dd7f9-125">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="dd7f9-125">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.CreateFolderOnSqlServer%2A>|  
  

  
###  <a name="removing-a-folder"></a><a name="managing_remfldr"></a> <span data-ttu-id="dd7f9-126">Rimozione di una cartella</span><span class="sxs-lookup"><span data-stu-id="dd7f9-126">Removing a Folder</span></span>  
 <span data-ttu-id="dd7f9-127">Per rimuovere una cartella di archiviazione a livello di programmazione, chiamare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd7f9-127">To remove a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="dd7f9-128">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="dd7f9-128">Storage Location</span></span>|<span data-ttu-id="dd7f9-129">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="dd7f9-129">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="dd7f9-130">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="dd7f9-130">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RemoveFolderFromSqlServer%2A>|  
  
  
  
###  <a name="renaming-a-folder"></a><a name="managing_rename"></a> <span data-ttu-id="dd7f9-131">Ridenominazione di una cartella</span><span class="sxs-lookup"><span data-stu-id="dd7f9-131">Renaming a Folder</span></span>  
 <span data-ttu-id="dd7f9-132">Per rinominare una cartella di archiviazione a livello di programmazione, chiamare uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd7f9-132">To rename a storage folder programmatically, call one of the following methods:</span></span>  
  
|<span data-ttu-id="dd7f9-133">Posizione di archiviazione</span><span class="sxs-lookup"><span data-stu-id="dd7f9-133">Storage Location</span></span>|<span data-ttu-id="dd7f9-134">Metodo da chiamare</span><span class="sxs-lookup"><span data-stu-id="dd7f9-134">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="dd7f9-135">Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="dd7f9-135">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.RenameFolderOnSqlServer%2A>|  
  

  
<span data-ttu-id="dd7f9-136">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="dd7f9-136">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="dd7f9-137">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="dd7f9-137">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="dd7f9-138">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="dd7f9-138">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="dd7f9-139">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="dd7f9-139">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd7f9-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd7f9-140">See Also</span></span>  
 <span data-ttu-id="dd7f9-141">[Gestione pacchetti &#40;servizio SSIS&#41;](../service/package-management-ssis-service.md) </span><span class="sxs-lookup"><span data-stu-id="dd7f9-141">[Package Management &#40;SSIS Service&#41;](../service/package-management-ssis-service.md) </span></span>  
 [<span data-ttu-id="dd7f9-142">Enumerazione dei pacchetti disponibili a livello di codice</span><span class="sxs-lookup"><span data-stu-id="dd7f9-142">Enumerating Available Packages Programmatically</span></span>](../run-manage-packages-programmatically/enumerating-available-packages-programmatically.md)  
  
  
