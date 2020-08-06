---
title: Selezione opzioni di Gestione pacchetti (aggiornamento guidato pacchetti SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.is.upgradewizard.selectpackagemgtoptions.f1
ms.assetid: 810fc020-51cd-43ed-9f35-af99b4f35947
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b5113ad5a1f6758a75742ca58aef04ce92168649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637980"
---
# <a name="select-package-management-options-ssis-package-upgrade-wizard"></a><span data-ttu-id="58ccd-102">Seleziona opzioni di gestione pacchetti (Aggiornamento guidato pacchetti SSIS)</span><span class="sxs-lookup"><span data-stu-id="58ccd-102">Select Package Management Options (SSIS Package Upgrade Wizard)</span></span>
  <span data-ttu-id="58ccd-103">Usare la pagina **Seleziona opzioni di gestione pacchetti** per specificare le opzioni per l'aggiornamento dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="58ccd-103">Use the **Select Package Management Options** page to specify options for upgrading packages.</span></span>  
  
 <span data-ttu-id="58ccd-104">**Per eseguire l'Aggiornamento guidato pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="58ccd-104">**To run the SSIS Package Upgrade Wizard**</span></span>  
  
-   [<span data-ttu-id="58ccd-105">Aggiornare i pacchetti di Integration Services mediante l'Aggiornamento guidato pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="58ccd-105">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="58ccd-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="58ccd-106">Options</span></span>  
 <span data-ttu-id="58ccd-107">**Aggiorna stringhe di connessione per l'uso di nuovi nomi di provider**</span><span class="sxs-lookup"><span data-stu-id="58ccd-107">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="58ccd-108">Consente di aggiornare le stringhe di connessione per utilizzare i nomi dei provider seguenti per la versione corrente di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="58ccd-108">Update the connection strings to use the names for the following providers for the current release of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="58ccd-109">Provider OLE DB per [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58ccd-109">OLE DB Provider for [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="58ccd-110">Native Client</span><span class="sxs-lookup"><span data-stu-id="58ccd-110">Native Client</span></span>  
  
 <span data-ttu-id="58ccd-111">L'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] consente di aggiornare solo le stringhe di connessione archiviate nelle gestioni connessione.</span><span class="sxs-lookup"><span data-stu-id="58ccd-111">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="58ccd-112">Non vengono aggiornate le stringhe di connessione costruite dinamicamente utilizzando il linguaggio delle espressioni di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] o il codice in un'attività Script.</span><span class="sxs-lookup"><span data-stu-id="58ccd-112">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="58ccd-113">**Convalida pacchetti di aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="58ccd-113">**Validate upgrade packages**</span></span>  
 <span data-ttu-id="58ccd-114">Consente di convalidare i pacchetti di aggiornamento e di salvare solo i pacchetti che superano la convalida.</span><span class="sxs-lookup"><span data-stu-id="58ccd-114">Validate the upgrade packages and save only those upgrade packages that pass validation.</span></span>  
  
 <span data-ttu-id="58ccd-115">Se non si seleziona questa opzione, i pacchetti di aggiornamento non verranno convalidati.</span><span class="sxs-lookup"><span data-stu-id="58ccd-115">If you do not select this option, the wizard will not validate upgrade packages.</span></span> <span data-ttu-id="58ccd-116">Pertanto, verranno salvati tutti i pacchetti di aggiornamento, indipendentemente dalla loro validità.</span><span class="sxs-lookup"><span data-stu-id="58ccd-116">Therefore, the wizard will save all upgrade packages, regardless of whether the packages are valid or not.</span></span> <span data-ttu-id="58ccd-117">I pacchetti di aggiornamento vengono salvati nella destinazione specificata alla pagina **Seleziona posizione di destinazione** della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="58ccd-117">The wizard saves upgrade packages to the destination that is specified on the **SelectDestination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="58ccd-118">La convalida influisce sulla durata del processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="58ccd-118">Validation adds time to the upgrade process.</span></span> <span data-ttu-id="58ccd-119">Si consiglia di non selezionare questa opzione per pacchetti grandi che probabilmente verranno aggiornati in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="58ccd-119">We recommend that you do not select this option for large packages that are likely to be upgraded successfully.</span></span>  
  
 <span data-ttu-id="58ccd-120">**Crea nuovi ID pacchetti**</span><span class="sxs-lookup"><span data-stu-id="58ccd-120">**Create new package IDs**</span></span>  
 <span data-ttu-id="58ccd-121">Consente di creare nuovi ID per i pacchetti di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="58ccd-121">Create new package IDs for the upgrade packages.</span></span>  
  
 <span data-ttu-id="58ccd-122">**Continua aggiornamento in caso di mancato aggiornamento dei pacchetti**</span><span class="sxs-lookup"><span data-stu-id="58ccd-122">**Continue upgrade process when a package upgrade fails**</span></span>  
 <span data-ttu-id="58ccd-123">Consente di specificare che quando un pacchetto non può essere aggiornato, l'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] continua ad aggiornare i pacchetti rimanenti.</span><span class="sxs-lookup"><span data-stu-id="58ccd-123">Specify that when a package cannot be upgraded, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard continues to upgrade the remaining packages.</span></span>  
  
 <span data-ttu-id="58ccd-124">**Conflitti di nome pacchetti**</span><span class="sxs-lookup"><span data-stu-id="58ccd-124">**Package name conflicts**</span></span>  
 <span data-ttu-id="58ccd-125">Consente di specificare come vengono gestiti i pacchetti che hanno lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="58ccd-125">Specify how the wizard should handle packages that have the same name.</span></span> <span data-ttu-id="58ccd-126">Per questa opzione sono disponibili i valori elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="58ccd-126">This option has the values listed in the following table.</span></span>  
  
 <span data-ttu-id="58ccd-127">**Sovrascrivi file di pacchetto esistenti**</span><span class="sxs-lookup"><span data-stu-id="58ccd-127">**Overwrite existing package files**</span></span>  
 <span data-ttu-id="58ccd-128">Consente di sostituire il pacchetto esistente con il pacchetto di aggiornamento con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="58ccd-128">Replaces the existing package with the upgrade package of the same name.</span></span>  
  
 <span data-ttu-id="58ccd-129">**Aggiungi suffissi numerici a nomi di pacchetti di aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="58ccd-129">**Add numeric suffixes to upgrade package names**</span></span>  
 <span data-ttu-id="58ccd-130">Consente di aggiungere un suffisso numerico al nome del pacchetto di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="58ccd-130">Adds a numeric suffix to the name of the upgrade package.</span></span>  
  
 <span data-ttu-id="58ccd-131">**Non aggiornare pacchetti**</span><span class="sxs-lookup"><span data-stu-id="58ccd-131">**Do not upgrade packages**</span></span>  
 <span data-ttu-id="58ccd-132">Consente di arrestare l'aggiornamento dei pacchetti e di visualizzare un errore quando la procedura guidata viene completata.</span><span class="sxs-lookup"><span data-stu-id="58ccd-132">Stops the packages from being upgraded and displays an error when you complete the wizard.</span></span>  
  
 <span data-ttu-id="58ccd-133">Queste opzioni non sono disponibili quando si seleziona l'opzione **Salva in posizione di origine** nella pagina **Seleziona posizione di destinazione** della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="58ccd-133">These options are not available when you select the **Save to source location** option on the **Select Destination Location** page of the wizard.</span></span>  
  
 <span data-ttu-id="58ccd-134">**Ignora configurazioni**</span><span class="sxs-lookup"><span data-stu-id="58ccd-134">**Ignore Configurations**</span></span>  
 <span data-ttu-id="58ccd-135">Consente di non caricare le configurazioni di pacchetto durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="58ccd-135">Does not load package configurations during the package upgrade.</span></span> <span data-ttu-id="58ccd-136">Se si seleziona questa opzione l'aggiornamento del pacchetto richiede meno tempo.</span><span class="sxs-lookup"><span data-stu-id="58ccd-136">Selecting this option reduces the time required to upgrade the package.</span></span>  
  
 <span data-ttu-id="58ccd-137">**Esegui backup pacchetti originali**</span><span class="sxs-lookup"><span data-stu-id="58ccd-137">**Backup original packages**</span></span>  
 <span data-ttu-id="58ccd-138">Consente di eseguire il backup dei pacchetti originali in una cartella **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="58ccd-138">Have the wizard back up the original packages to an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="58ccd-139">Viene creata la cartella **SSISBackupFolder** come sottocartella della cartella che contiene i pacchetti originali e i pacchetti aggiornati.</span><span class="sxs-lookup"><span data-stu-id="58ccd-139">The wizard creates the **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="58ccd-140">Questa opzione è disponibile solo se si specifica che i pacchetti originali e i pacchetti aggiornati sono archiviati nel file system e nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="58ccd-140">This option is available only when you specify that the original packages and the upgraded packages are stored in the file system and in the same folder.</span></span>  
  
 <span data-ttu-id="58ccd-141">Per altre informazioni, vedere [Aggiornare i pacchetti di Integration Services mediante l'Aggiornamento guidato pacchetti SSIS](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="58ccd-141">For more information, see [Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard](install-windows/upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58ccd-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58ccd-142">See Also</span></span>  
 [<span data-ttu-id="58ccd-143">Aggiornare pacchetti di Integration Services</span><span class="sxs-lookup"><span data-stu-id="58ccd-143">Upgrade Integration Services Packages</span></span>](install-windows/upgrade-integration-services-packages.md)  
  
  
