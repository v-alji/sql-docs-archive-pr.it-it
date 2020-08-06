---
title: Selezione percorso di origine (aggiornamento guidato pacchetti SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectsourcelocation.f1
ms.assetid: 429f146e-edb4-4401-a225-f2c8468971c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e24eec77dc87a6215f9d686cf5af964cc244d68d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712136"
---
# <a name="select-source-location-ssis-package-upgrade-wizard"></a><span data-ttu-id="afa50-102">Seleziona posizione di origine (Aggiornamento guidato pacchetti SSIS)</span><span class="sxs-lookup"><span data-stu-id="afa50-102">Select Source Location (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="afa50-103">Usare la pagina **Seleziona posizione di origine** per specificare l'origine da cui eseguire l'aggiornamento dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="afa50-103">Use the **Select Source Location** page to specify the source from which to upgrade packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="afa50-104">Tale pagina è disponibile solo quando si esegue l'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] da [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] o dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="afa50-104">This page is only available when you run the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or at the command prompt.</span></span>  
  
 <span data-ttu-id="afa50-105">**Per eseguire l'Aggiornamento guidato pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="afa50-105">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="afa50-106">Aggiornare i pacchetti di Integration Services mediante l'Aggiornamento guidato pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="afa50-106">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="static-options"></a><span data-ttu-id="afa50-107">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="afa50-107">Static Options</span></span>  
 <span data-ttu-id="afa50-108">**Origine pacchetto**</span><span class="sxs-lookup"><span data-stu-id="afa50-108">**Package source**</span></span>  
 <span data-ttu-id="afa50-109">Selezionare il percorso di archiviazione che contiene i pacchetti da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="afa50-109">Select the storage location that contains the packages to be upgraded.</span></span> <span data-ttu-id="afa50-110">Per questa opzione sono disponibili i valori elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="afa50-110">This option has the values listed in the following table.</span></span>  
  
|<span data-ttu-id="afa50-111">Valore</span><span class="sxs-lookup"><span data-stu-id="afa50-111">Value</span></span>|<span data-ttu-id="afa50-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="afa50-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="afa50-113">**File system**</span><span class="sxs-lookup"><span data-stu-id="afa50-113">**File System**</span></span>|<span data-ttu-id="afa50-114">Indica che i pacchetti da aggiornare si trovano in una cartella nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="afa50-114">Indicates that the packages to be upgraded are in a folder on the local computer.</span></span><br /><br /> <span data-ttu-id="afa50-115">Per eseguire il backup dei pacchetti originali prima dell'aggiornamento, è necessario archiviare i pacchetti originali nel file system.</span><span class="sxs-lookup"><span data-stu-id="afa50-115">To have the wizard back up the original packages before upgrading those packages, the original packages must be stored in the file system.</span></span> <span data-ttu-id="afa50-116">Per ulteriori informazioni, vedere l'argomento relativo alla procedura.</span><span class="sxs-lookup"><span data-stu-id="afa50-116">For more information, see How To Topic.</span></span>|  
|<span data-ttu-id="afa50-117">**Archivio pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="afa50-117">**SSIS Package Store**</span></span>|<span data-ttu-id="afa50-118">Indica che i pacchetti da aggiornare si trovano nell'archivio pacchetti.</span><span class="sxs-lookup"><span data-stu-id="afa50-118">Indicates that the packages to be upgraded are in the package store.</span></span> <span data-ttu-id="afa50-119">L'archivio pacchetti è costituito dal set di cartelle del file system gestito dal servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="afa50-119">The package store consists of the set of file system folders that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span> <span data-ttu-id="afa50-120">Per altre informazioni, vedere [Gestione dei pacchetti &#40;servizio SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="afa50-120">For more information, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span><br /><br /> <span data-ttu-id="afa50-121">La selezione di questo valore determina la visualizzazione delle opzioni dinamiche di **Origine pacchetto** corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="afa50-121">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
|<span data-ttu-id="afa50-122">**Microsoft SQL Server**</span><span class="sxs-lookup"><span data-stu-id="afa50-122">**Microsoft SQL Server**</span></span>|<span data-ttu-id="afa50-123">Indica che i pacchetti da aggiornare provengono da un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]esistente.</span><span class="sxs-lookup"><span data-stu-id="afa50-123">Indicates the packages to be upgraded are from an existing instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span><br /><br /> <span data-ttu-id="afa50-124">La selezione di questo valore determina la visualizzazione delle opzioni dinamiche di **Origine pacchetto** corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="afa50-124">Selecting this value displays the corresponding **Package source** dynamic options.</span></span>|  
  
 <span data-ttu-id="afa50-125">**Cartella**</span><span class="sxs-lookup"><span data-stu-id="afa50-125">**Folder**</span></span>  
 <span data-ttu-id="afa50-126">Digitare il nome di una cartella che contiene i pacchetti da aggiornare o fare clic su **Sfoglia** e individuare la cartella.</span><span class="sxs-lookup"><span data-stu-id="afa50-126">Type the name of a folder that contains the packages you want to upgrade or click **Browse** and locate the folder.</span></span>  
  
 <span data-ttu-id="afa50-127">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="afa50-127">**Browse**</span></span>  
 <span data-ttu-id="afa50-128">Consente di individuare la cartella che contiene i pacchetti da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="afa50-128">Browse to locate the folder that contains the packages you want to upgrade.</span></span>  
  
## <a name="package-source-dynamic-options"></a><span data-ttu-id="afa50-129">Opzioni dinamiche di Origine pacchetto</span><span class="sxs-lookup"><span data-stu-id="afa50-129">Package Source Dynamic Options</span></span>  
  
### <a name="package-source--ssis-package-store"></a><span data-ttu-id="afa50-130">Origine pacchetto = Archivio pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="afa50-130">Package source = SSIS Package Store</span></span>  
 <span data-ttu-id="afa50-131">**Server**</span><span class="sxs-lookup"><span data-stu-id="afa50-131">**Server**</span></span>  
 <span data-ttu-id="afa50-132">Digitare il nome del server che contiene i pacchetti da aggiornare oppure selezionare il server nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="afa50-132">Type the name of the server that has the packages to be upgraded, or select this server in the list.</span></span>  
  
### <a name="package-source--microsoft-sql-server"></a><span data-ttu-id="afa50-133">Origine pacchetto = Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="afa50-133">Package source = Microsoft SQL Server</span></span>  
 <span data-ttu-id="afa50-134">**Server**</span><span class="sxs-lookup"><span data-stu-id="afa50-134">**Server**</span></span>  
 <span data-ttu-id="afa50-135">Digitare il nome del server che contiene i pacchetti da aggiornare oppure selezionare il server dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="afa50-135">Type the name of the server that has the packages to be upgraded, or select this server from the list.</span></span>  
  
 <span data-ttu-id="afa50-136">**Usa autenticazione di Windows**</span><span class="sxs-lookup"><span data-stu-id="afa50-136">**Use Windows authentication**</span></span>  
 <span data-ttu-id="afa50-137">Selezionare questa opzione per utilizzare l'autenticazione di Windows per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="afa50-137">Select to use Windows Authentication to connect to the server.</span></span>  
  
 <span data-ttu-id="afa50-138">**Usa autenticazione SQL Server**</span><span class="sxs-lookup"><span data-stu-id="afa50-138">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="afa50-139">Selezionare questa opzione per usare l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="afa50-139">Select to use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to connect to the server.</span></span> <span data-ttu-id="afa50-140">Se si usa l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , è necessario specificare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="afa50-140">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="afa50-141">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="afa50-141">**User name**</span></span>  
 <span data-ttu-id="afa50-142">Digitare il nome utente usato dall'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="afa50-142">Type the user name that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
 <span data-ttu-id="afa50-143">**Password**</span><span class="sxs-lookup"><span data-stu-id="afa50-143">**Password**</span></span>  
 <span data-ttu-id="afa50-144">Digitare la password usata dall'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per la connessione al server.</span><span class="sxs-lookup"><span data-stu-id="afa50-144">Type the password that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication will use to connect to the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa50-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afa50-145">See Also</span></span>  
 [<span data-ttu-id="afa50-146">Aggiornare pacchetti di Integration Services</span><span class="sxs-lookup"><span data-stu-id="afa50-146">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
