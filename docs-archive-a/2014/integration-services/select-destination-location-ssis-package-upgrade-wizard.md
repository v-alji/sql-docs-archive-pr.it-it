---
title: Selezionare il percorso di destinazione (aggiornamento guidato pacchetti SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectdestinationlocation.f1
ms.assetid: 89274a71-0ffe-4889-84df-f5a7d78459ef
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9411157434c3dbb9fb033f7b63b5e6041fd8f75d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637982"
---
# <a name="select-destination-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="d0f32-102">Seleziona posizione di destinazione (Aggiornamento guidato pacchetti SSIS)</span><span class="sxs-lookup"><span data-stu-id="d0f32-102">Select Destination Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="d0f32-103">Usare la pagina **Seleziona posizione di destinazione** per specificare la destinazione in cui salvare i pacchetti aggiornati.</span><span class="sxs-lookup"><span data-stu-id="d0f32-103">Use the **Select Destination Location** page to specify the destination to which to save the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0f32-104">Tale pagina è disponibile solo quando si esegue l'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] da [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="d0f32-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="d0f32-105">**Per eseguire l'Aggiornamento guidato pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="d0f32-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="d0f32-106">Aggiornare i pacchetti di Integration Services mediante l'Aggiornamento guidato pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="d0f32-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="d0f32-107">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="d0f32-107">Static Options</span></span>  
 <span data-ttu-id="d0f32-108">**Salva in posizione di origine**</span><span class="sxs-lookup"><span data-stu-id="d0f32-108">**Save to source location**</span></span>  
 <span data-ttu-id="d0f32-109">Consente di salvare i pacchetti aggiornati nella stessa posizione specificata nella pagina **Seleziona posizione di origine** della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="d0f32-109">Save the upgraded packages to the same location as specified on the **Select Source Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="d0f32-110">Se i pacchetti originali sono archiviati nel file system e si desidera eseguire il backup dei pacchetti, selezionare l'opzione **Salva in posizione di origine** .</span><span class="sxs-lookup"><span data-stu-id="d0f32-110">If the original packages are stored in the file system and you want the wizard to back up those packages, select the **Save to source location** option.</span></span> <span data-ttu-id="d0f32-111">Per altre informazioni, vedere [Aggiornare i pacchetti di Integration Services mediante l'Aggiornamento guidato pacchetti SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d0f32-111">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
 <span data-ttu-id="d0f32-112">**Seleziona nuova posizione di destinazione**</span><span class="sxs-lookup"><span data-stu-id="d0f32-112">**Select new destination location**</span></span>  
 <span data-ttu-id="d0f32-113">Consente di salvare i pacchetti aggiornati nella posizione di destinazione specificata nella pagina.</span><span class="sxs-lookup"><span data-stu-id="d0f32-113">Save the upgraded packages to the destination location that is specified on this page.</span></span>  
  
 <span data-ttu-id="d0f32-114">**Origine pacchetto**</span><span class="sxs-lookup"><span data-stu-id="d0f32-114">**Package source**</span></span>  
 <span data-ttu-id="d0f32-115">Consente di specificare la posizione di archiviazione dei pacchetti di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d0f32-115">Specify where the upgrade packages are to be stored.</span></span> <span data-ttu-id="d0f32-116">Per questa opzione sono disponibili i valori elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d0f32-116">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="d0f32-117">Valore</span><span class="sxs-lookup"><span data-stu-id="d0f32-117">Value</span></span>|<span data-ttu-id="d0f32-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0f32-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d0f32-119">**File system**</span><span class="sxs-lookup"><span data-stu-id="d0f32-119">**File System**</span></span>|<span data-ttu-id="d0f32-120">Indica che i pacchetti aggiornati devono essere salvati in una cartella nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="d0f32-120">Indicates that the upgraded packages are to be saved to a folder on the local computer.</span></span>|  
|<span data-ttu-id="d0f32-121">**Archivio pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="d0f32-121">**SSIS Package Store**</span></span>|<span data-ttu-id="d0f32-122">Indica che i pacchetti aggiornati devono essere salvati nell'archivio pacchetti Integration Services.</span><span class="sxs-lookup"><span data-stu-id="d0f32-122">Indicates that the upgraded packages are to be saved to the Integration Services package store.</span></span> <span data-ttu-id="d0f32-123">L'archivio pacchetti è costituito dal set di cartelle del file system gestito dal servizio Integration Services.</span><span class="sxs-lookup"><span data-stu-id="d0f32-123">The package store consists of the set of file system folders that the Integration Services service manages.</span></span> <span data-ttu-id="d0f32-124">Per altre informazioni, vedere [Gestione dei pacchetti &#40;servizio SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="d0f32-124">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="d0f32-125">La selezione di questo valore determina la visualizzazione delle opzioni dinamiche di **Origine pacchetto** corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d0f32-125">Selecting this value displays the corresponding **Package source** dynamics options.</span></span>|  
|<span data-ttu-id="d0f32-126">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d0f32-126">**Microsoft SQL Server**</span></span>|<span data-ttu-id="d0f32-127">Indica che i pacchetti aggiornati devono essere salvati in un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]esistente.</span><span class="sxs-lookup"><span data-stu-id="d0f32-127">Indicates that the upgraded packages are to be saved to an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="d0f32-128">La selezione di questo valore determina la visualizzazione delle opzioni dinamiche di **Origine pacchetto** corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d0f32-128">Selecting this value displays the corresponding dynamic **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="d0f32-129">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="d0f32-129">**Folder**</span></span>  
 <span data-ttu-id="d0f32-130">Digitare il nome della cartella in cui verranno salvati i pacchetti aggiornati oppure fare clic su **Sfoglia** e individuare la cartella.</span><span class="sxs-lookup"><span data-stu-id="d0f32-130">Type the name of a folder to which the upgraded packages will be saved, or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="d0f32-131">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="d0f32-131">**Browse**</span></span>  
 <span data-ttu-id="d0f32-132">Consente di individuare la cartella in cui verranno salvati i pacchetti aggiornati.</span><span class="sxs-lookup"><span data-stu-id="d0f32-132">Browse to locate the folder to which the upgraded packages will be saved.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="d0f32-133">Opzioni dinamiche di Origine pacchetto</span><span class="sxs-lookup"><span data-stu-id="d0f32-133">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="d0f32-134">Origine pacchetto = Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="d0f32-134">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="d0f32-135">**Server**</span><span class="sxs-lookup"><span data-stu-id="d0f32-135">**Server**</span></span>  
 <span data-ttu-id="d0f32-136">Digitare il nome del server in cui verranno salvati i pacchetti di aggiornamento oppure selezionare un server nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0f32-136">Type the name of the server to which the upgrade packages will be saved, or select a server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="d0f32-137">Origine pacchetto = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0f32-137">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="d0f32-138">**Server**</span><span class="sxs-lookup"><span data-stu-id="d0f32-138">**Server**</span></span>  
 <span data-ttu-id="d0f32-139">Digitare il nome del server in cui verranno salvati i pacchetti di aggiornamento oppure selezionare il server nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="d0f32-139">Type the name of the server to which the upgrade packages will be saved, or select this server in the list.</span></span>  
  
 <span data-ttu-id="d0f32-140">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="d0f32-140">**Use Windows authentication**</span></span>  
 <span data-ttu-id="d0f32-141">Selezionare questa opzione per utilizzare l'autenticazione di Windows per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="d0f32-141">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="d0f32-142">**Usa autenticazione SQL Server**</span><span class="sxs-lookup"><span data-stu-id="d0f32-142">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="d0f32-143">Selezionare questa opzione per usare l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="d0f32-143">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="d0f32-144">Se si usa l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , è necessario specificare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="d0f32-144">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="d0f32-145">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="d0f32-145">**User name**</span></span>  
 <span data-ttu-id="d0f32-146">Digitare il nome utente da usare quando si seleziona l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="d0f32-146">Type the user name to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="d0f32-147">**Password**</span><span class="sxs-lookup"><span data-stu-id="d0f32-147">**Password**</span></span>  
 <span data-ttu-id="d0f32-148">Digitare la password da usare quando si seleziona l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="d0f32-148">Type the password to be used when using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f32-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0f32-149">See Also</span></span>  
 [<span data-ttu-id="d0f32-150">Aggiornare pacchetti di Integration Services</span><span class="sxs-lookup"><span data-stu-id="d0f32-150">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
