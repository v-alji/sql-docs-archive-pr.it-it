---
title: Aggiornare i pacchetti di Integration Services mediante l'Aggiornamento guidato pacchetti SSIS | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, upgrading
- upgrading Integration Services packages
ms.assetid: 9359275a-48f5-4d1e-8ae7-e797759e3ccf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bcafd1c9750d8333639ca2d315512a2c2b8759c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628893"
---
# <a name="upgrade-integration-services-packages-using-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="1ef65-102">Aggiornare i pacchetti di Integration Services mediante l'Aggiornamento guidato pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="1ef65-102">Upgrade Integration Services Packages Using the SSIS Package Upgrade Wizard</span></span>
  <span data-ttu-id="1ef65-103">È possibile aggiornare i pacchetti creati nelle versioni precedenti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] al formato [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilizzato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ef65-103">You can upgrade packages that were created in earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] format that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1ef65-104">fornisce l'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] che consente di semplificare il processo.</span><span class="sxs-lookup"><span data-stu-id="1ef65-104">provides the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard to help in this process.</span></span> <span data-ttu-id="1ef65-105">Poiché è possibile configurare la procedura guidata in modo da eseguire il backup dei pacchetti originali, sarà possibile continuare a utilizzarli nel caso in cui si riscontrino difficoltà nell'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="1ef65-105">Because you can configure the wizard to backup up your original packages, you can continue to use the original packages if you experience upgrade difficulties.</span></span>  
  
 <span data-ttu-id="1ef65-106">L'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] viene installato durante l'installazione di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ef65-106">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is installed when [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ef65-107">L'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] è disponibile in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Standard Edition, Enterprise Edition e Developer Edition.</span><span class="sxs-lookup"><span data-stu-id="1ef65-107">The [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard is available in the Standard, Enterprise, and Developer Editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1ef65-108">Per informazioni su come aggiornare i pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , vedere [Aggiornare pacchetti di Integration Services](upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="1ef65-108">For more information about how to upgrade [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, see [Upgrade Integration Services Packages](upgrade-integration-services-packages.md).</span></span>  
  
 <span data-ttu-id="1ef65-109">Nella parte restante dell'argomento viene descritto come eseguire la procedura guidata e il backup dei pacchetti originali.</span><span class="sxs-lookup"><span data-stu-id="1ef65-109">The remainder of this topic describes how to run the wizard and back up the original packages.</span></span>  
  
## <a name="running-the-ssis-package-upgrade-wizard"></a><span data-ttu-id="1ef65-110">Esecuzione dell'Aggiornamento guidato pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="1ef65-110">Running the SSIS Package Upgrade Wizard</span></span>  
 <span data-ttu-id="1ef65-111">È possibile eseguire l'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] da [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]o dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="1ef65-111">You can run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], or at the command prompt.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-data-tools"></a><span data-ttu-id="1ef65-112">Per eseguire la procedura guidata da SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="1ef65-112">To run the wizard from SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="1ef65-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]creare o aprire un progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ef65-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="1ef65-114">In Esplora soluzioni fare clic con il pulsante destro del mouse sul nodo **Pacchetti SSIS** , quindi scegliere **Aggiorna tutti i pacchetti** per aggiornare tutti i pacchetti all'interno di questo nodo.</span><span class="sxs-lookup"><span data-stu-id="1ef65-114">In Solution Explorer, right-click the **SSIS Packages** node, and then click **Upgrade All Packages** to upgrade all the packages under this node.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1ef65-115">Quando si apre un progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenente pacchetti di [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] o [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)], in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] viene automaticamente visualizzata la finestra dell'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ef65-115">When you open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] packages, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] automatically opens the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
#### <a name="to-run-the-wizard-from-sql-server-management-studio"></a><span data-ttu-id="1ef65-116">Per eseguire la procedura guidata da SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1ef65-116">To run the wizard from SQL Server Management Studio</span></span>  
  
-   <span data-ttu-id="1ef65-117">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]connettersi a [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], espandere il nodo **Pacchetti archiviati** e fare clic con il pulsante destro del mouse sul nodo **File system** o **MSDB** , quindi scegliere **Aggiorna pacchetti**.</span><span class="sxs-lookup"><span data-stu-id="1ef65-117">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], expand the **Stored Packages** node, and right-click the **File System** or **MSDB** node, and then click **Upgrade Packages**.</span></span>  
  
#### <a name="to-run-the-wizard-at-the-command-prompt"></a><span data-ttu-id="1ef65-118">Per eseguire la procedura guidata dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="1ef65-118">To run the wizard at the command prompt</span></span>  
  
-   <span data-ttu-id="1ef65-119">Al prompt dei comandi, eseguire il file SSISUpgrade.exe dalla cartella c:\Programmi\Microsoft **SQL Server\120\DTS\Binn**</span><span class="sxs-lookup"><span data-stu-id="1ef65-119">At the command prompt, run the SSISUpgrade.exe file from the **C:\Program Files\Microsoft SQL Server\120\DTS\Binn** folder.</span></span>  
  
## <a name="backing-up-the-original-packages"></a><span data-ttu-id="1ef65-120">Esecuzione del backup dei pacchetti originali</span><span class="sxs-lookup"><span data-stu-id="1ef65-120">Backing Up the Original Packages</span></span>  
 <span data-ttu-id="1ef65-121">Per eseguire il backup dei pacchetti originali, è necessario che i pacchetti originali e i pacchetti aggiornati siano archiviati nella stessa cartella del file system.</span><span class="sxs-lookup"><span data-stu-id="1ef65-121">To back up the original packages, both the original packages and the upgraded packages must be stored in the same folder in the file system.</span></span> <span data-ttu-id="1ef65-122">A seconda di come viene eseguita la procedura guidata, è possibile che il percorso di archiviazione venga selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1ef65-122">Depending on how you run the wizard, this storage location might be automatically selected.</span></span>  
  
-   <span data-ttu-id="1ef65-123">Quando si esegue l'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] da [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], la procedura guidata archivia automaticamente i pacchetti originali e i pacchetti aggiornati nella stessa cartella del file system.</span><span class="sxs-lookup"><span data-stu-id="1ef65-123">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], the wizard automatically stores both the original packages and upgraded packages in the same folder in the file system.</span></span>  
  
-   <span data-ttu-id="1ef65-124">Quando si esegue l'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o dal prompt dei comandi, è possibile specificare percorsi di archiviazione diversi per i pacchetti originali e per quelli aggiornati.</span><span class="sxs-lookup"><span data-stu-id="1ef65-124">When you run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, you can specify different storage locations for the original and upgraded packages.</span></span> <span data-ttu-id="1ef65-125">Per eseguire il backup dei pacchetti originali, accertarsi di specificare che sia i pacchetti originali che quelli aggiornati sono archiviati nella stessa cartella del file system.</span><span class="sxs-lookup"><span data-stu-id="1ef65-125">To back up the original packages, make sure to specify that both the original and upgraded packages are stored in the same folder in the file system.</span></span> <span data-ttu-id="1ef65-126">Se si specificano altre opzione di archiviazione, la procedura guidata non sarà in grado di eseguire il backup dei pacchetti originali.</span><span class="sxs-lookup"><span data-stu-id="1ef65-126">If you specify any other storage options, the wizard will not be able to back up the original packages.</span></span>  
  
 <span data-ttu-id="1ef65-127">Quando esegue il backup dei pacchetti originali, la procedura guidata archivia una copia di tali pacchetti nella cartella **SSISBackupFolder** .</span><span class="sxs-lookup"><span data-stu-id="1ef65-127">When the wizard backs up the original packages, the wizard stores a copy of the original packages in an **SSISBackupFolder** folder.</span></span> <span data-ttu-id="1ef65-128">La cartella **SSISBackupFolder** viene creata come sottocartella della cartella che contiene i pacchetti originali e i pacchetti aggiornati.</span><span class="sxs-lookup"><span data-stu-id="1ef65-128">The wizard creates this **SSISBackupFolder** folder as a subfolder to the folder that contains the original packages and the upgraded packages.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-management-studio-or-at-the-command-prompt"></a><span data-ttu-id="1ef65-129">Per eseguire il backup dei pacchetti originali in SQL Server Management Studio o dal prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="1ef65-129">To back up the original packages in SQL Server Management Studio or at the command prompt</span></span>  
  
1.  <span data-ttu-id="1ef65-130">Salvare i pacchetti originali in un percorso del file system.</span><span class="sxs-lookup"><span data-stu-id="1ef65-130">Save the original packages to a location on the file system.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1ef65-131">L'opzione di backup della procedura guidata funziona solo con i pacchetti archiviati nel file system.</span><span class="sxs-lookup"><span data-stu-id="1ef65-131">The backup option in the wizard only works with packages that have been stored to the file system.</span></span>  
  
2.  <span data-ttu-id="1ef65-132">Eseguire l'Aggiornamento guidato pacchetti [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[ssIS](../../includes/ssis-md.md)] o dal prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="1ef65-132">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or at the command prompt, run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
3.  <span data-ttu-id="1ef65-133">Nella pagina **Seleziona posizione di origine** della procedura guidata impostare la proprietà **Origine pacchetto** su **File system**.</span><span class="sxs-lookup"><span data-stu-id="1ef65-133">On the **Select Source Location** page of the wizard, set the **Package source** property to **File System**.</span></span>  
  
4.  <span data-ttu-id="1ef65-134">Nella pagina **Seleziona posizione di destinazione** della procedura guidata selezionare **Salva in posizione di origine** per salvare i pacchetti aggiornati nello stesso percorso dei pacchetti originali.</span><span class="sxs-lookup"><span data-stu-id="1ef65-134">On the **Select Destination Location** page of the wizard, select **Save to source location** tosave the upgraded packages to the same location as the original packages.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1ef65-135">L'opzione di backup della procedura guidata è disponibile solo se i pacchetti aggiornati vengono archiviati nella stessa cartella dei pacchetti originali.</span><span class="sxs-lookup"><span data-stu-id="1ef65-135">The backup option in the wizard is available only when the upgraded packages are stored in the same folder as the original packages.</span></span>  
  
5.  <span data-ttu-id="1ef65-136">Nella pagina **Seleziona opzioni di gestione pacchetti** della procedura guidata selezionare l'opzione **Esegui backup pacchetti originali** .</span><span class="sxs-lookup"><span data-stu-id="1ef65-136">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
#### <a name="to-back-up-the-original-packages-in-sql-server-data-tools"></a><span data-ttu-id="1ef65-137">Per eseguire il backup dei pacchetti originali in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="1ef65-137">To back up the original packages in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="1ef65-138">Salvare i pacchetti originali in un percorso del file system.</span><span class="sxs-lookup"><span data-stu-id="1ef65-138">Save the original packages to a location on the file system.</span></span>  
  
2.  <span data-ttu-id="1ef65-139">Nella pagina **Seleziona opzioni di gestione pacchetti** della procedura guidata selezionare l'opzione **Esegui backup pacchetti originali** .</span><span class="sxs-lookup"><span data-stu-id="1ef65-139">On the **Select Package Management Options** page of the wizard, select the **Backup original packages** option.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="1ef65-140">L'opzione **Esegui backup pacchetti originali** non viene visualizzata quando si apre [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] un [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] progetto di o in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] , che avvia automaticamente la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="1ef65-140">The **Backup original packages** option is not displayed when you open a [!INCLUDE[ssISversion2005](../../includes/ssisversion2005-md.md)] or [!INCLUDE[ssISversion10](../../includes/ssisversion10-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], which automatically launches the wizard.</span></span>  
  
3.  <span data-ttu-id="1ef65-141">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]eseguire l'Aggiornamento guidato pacchetti [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ef65-141">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], run the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Upgrade Wizard.</span></span>  
  
  
