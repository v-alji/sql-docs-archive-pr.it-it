---
title: Rinominare un'istanza di Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- instances of Analysis Services, renaming
- renaming instances of Analysis Services
- names [Analysis Services], renaming instances
- names [Analysis Services]
ms.assetid: 87494741-4a2e-4fed-8061-418fd1e111c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 763986d82dda7424f2187daf401424fd256ddd64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716931"
---
# <a name="rename-an-analysis-services-instance"></a><span data-ttu-id="65ee8-102">Rinominare un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="65ee8-102">Rename an Analysis Services Instance</span></span>
  <span data-ttu-id="65ee8-103">È possibile rinominare un'istanza esistente di utilizzando la finestra di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dialogo **Rinomina istanza** .</span><span class="sxs-lookup"><span data-stu-id="65ee8-103">You can rename an existing instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using the **Rename Instance** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="65ee8-104">Mentre si rinomina l'istanza, lo strumento Rinomina istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] viene eseguito con privilegi elevati, aggiornando il nome del servizio Windows, gli account di sicurezza e le voci del Registro di sistema associati a quell'istanza.</span><span class="sxs-lookup"><span data-stu-id="65ee8-104">While renaming the instance, the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool runs under elevated privileges, updating the Windows service name, security accounts, and registry entries associated with that instance.</span></span> <span data-ttu-id="65ee8-105">Per accertarsi che queste azioni vengono effettuate, eseguire questo strumento come amministratore di sistema locale.</span><span class="sxs-lookup"><span data-stu-id="65ee8-105">To ensure that these actions are performed, be sure to run this tool as a local system administrator.</span></span>  
  
 <span data-ttu-id="65ee8-106">Lo strumento Rinomina istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non modifica la cartella di programma creata per l'istanza originale.</span><span class="sxs-lookup"><span data-stu-id="65ee8-106">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool does not modify the program folder that was created for the original instance.</span></span> <span data-ttu-id="65ee8-107">Non modificare il nome della cartella di programma in base all'istanza che si sta rinominando.</span><span class="sxs-lookup"><span data-stu-id="65ee8-107">Do not modify the program folder name to match the instance you are renaming.</span></span> <span data-ttu-id="65ee8-108">La modifica del nome di una cartella di programma può impedire al programma di installazione di effettuare il ripristino o la disinstallazione di un programma.</span><span class="sxs-lookup"><span data-stu-id="65ee8-108">Changing a program folder name can prevent Setup from repairing or uninstalling the installation.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65ee8-109">L’uso dello strumento Rinomina istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] non è supportato in un ambiente cluster.</span><span class="sxs-lookup"><span data-stu-id="65ee8-109">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Instance Rename tool is not supported for use in a cluster environment.</span></span>  
  
### <a name="to-rename-an-instance-of-analysis-services"></a><span data-ttu-id="65ee8-110">Per rinominare un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="65ee8-110">To rename an instance of Analysis Services</span></span>  
  
1.  <span data-ttu-id="65ee8-111">Avviare lo strumento **Rinomina istanza** , **asinstancerename.exe**, da c:\Programmi\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span><span class="sxs-lookup"><span data-stu-id="65ee8-111">Launch the **Instance Rename** tool, **asinstancerename.exe**, from C:\Program Files\Microsoft SQL Server\110\Tools\Binn\ManagementStudio.</span></span>  
  
2.  <span data-ttu-id="65ee8-112">Nell'elenco **Istanza da rinominare** della finestra di dialogo **Rinomina istanza** selezionare l'istanza che si desidera rinominare.</span><span class="sxs-lookup"><span data-stu-id="65ee8-112">In the **Rename Instance** dialog box, in the **Instance to rename** list, select the instance that you want to rename.</span></span>  
  
3.  <span data-ttu-id="65ee8-113">Immettere il nuovo nome dell'istanza nella casella **Nuovo nome istanza** .</span><span class="sxs-lookup"><span data-stu-id="65ee8-113">In the **New instance name** box, enter the new name for the instance.</span></span>  
  
4.  <span data-ttu-id="65ee8-114">Verificare che il nome utente e la password siano corretti e quindi fare clic su **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="65ee8-114">Verify that the user name and password are correct, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="65ee8-115">L'istanza di Analysis Services verrà arrestata e riavviata come parte della modifica del nome.</span><span class="sxs-lookup"><span data-stu-id="65ee8-115">The Analysis Services instance will be stopped and restarted as part of the name change.</span></span>  
  
### <a name="post-rename-checklist"></a><span data-ttu-id="65ee8-116">Elenco di controllo successivo alla ridenominazione</span><span class="sxs-lookup"><span data-stu-id="65ee8-116">Post-rename checklist</span></span>  
  
1.  <span data-ttu-id="65ee8-117">Per riprendere l'accesso ai database in esecuzione nell'istanza rinominata, sarà necessario aggiornare manualmente le connessioni dati in Excel o in altre applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="65ee8-117">To resume access to databases that are running on the renamed instance, you will need to manually update the data connections in Excel or other client applications.</span></span> <span data-ttu-id="65ee8-118">Verificare inoltre eventuali connessioni predefinite, ad esempio origini dati condivise di Reporting Services, file ODC di Excel o file di connessione BI Semantic Model che potrebbero fare riferimento all'istanza rinominata.</span><span class="sxs-lookup"><span data-stu-id="65ee8-118">Also check any predefined connections, such as Reporting Services shared data sources, Excel ODC files, or BI Semantic Model connection files that might reference the instance you just renamed.</span></span> <span data-ttu-id="65ee8-119">Per altre informazioni, vedere [Connetti ad Analysis Services](connect-to-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="65ee8-119">For more information, see [Connect to Analysis Services](connect-to-analysis-services.md).</span></span>  
  
2.  <span data-ttu-id="65ee8-120">Aggiornare script di PowerShell o script AMO utilizzati regolarmente per eseguire il backup, sincronizzare o elaborare database.</span><span class="sxs-lookup"><span data-stu-id="65ee8-120">Update PowerShell scripts or AMO scripts that you routinely use to backup, synchronize, or process databases.</span></span>  
  
3.  <span data-ttu-id="65ee8-121">Aggiornare le proprietà del progetto per i progetti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] usati in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="65ee8-121">Update project properties for [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projects that you work with in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="65ee8-122">Per le istanze del server in modalità tabulare, accertarsi di aggiornare la proprietà Server dell'area di lavoro nel file con estensione model.bim e la proprietà Server nel progetto.</span><span class="sxs-lookup"><span data-stu-id="65ee8-122">For tabular mode server instances, be sure to update the Workspace Server property on the model.bim file, as well as the Server property on the project.</span></span>  
  
4.  <span data-ttu-id="65ee8-123">A seconda di come è stato specificato l'account del servizio, potrebbe essere necessario aggiornare gli account di accesso al database o le autorizzazioni per i file che concedono diritti di accesso ai dati del servizio (ad esempio, se si utilizza l'account del servizio per elaborare dati o accedere a oggetti collegati su un altro server).</span><span class="sxs-lookup"><span data-stu-id="65ee8-123">Depending on how you specified the service account, you might need to update database logins or file permissions that grant data access rights to the service (for example, if you use the service account to process data or access linked objects on another server).</span></span>  
  
     <span data-ttu-id="65ee8-124">L'aggiornamento di un account di accesso al database o delle autorizzazioni per i file sarà necessario se per il provisioning del servizio è stato utilizzato un account virtuale.</span><span class="sxs-lookup"><span data-stu-id="65ee8-124">Updating a database login or file permissions will be necessary if you used a virtual account to provision the service.</span></span> <span data-ttu-id="65ee8-125">Gli account virtuali sono basati sul nome dell'istanza, pertanto se si rinomina l'istanza, verrà aggiornato contemporaneamente anche l'account virtuale.</span><span class="sxs-lookup"><span data-stu-id="65ee8-125">Virtual accounts are based on the instance name, so if you rename the instance, the virtual account is also updated at the same time.</span></span> <span data-ttu-id="65ee8-126">Ciò significa che qualsiasi account di accesso o autorizzazione precedente creata per l'istanza precedente non sarà più valida.</span><span class="sxs-lookup"><span data-stu-id="65ee8-126">This means that any previous logins or permissions that you created for the previous instance are no longer valid.</span></span>  
  
     <span data-ttu-id="65ee8-127">Di seguito ne viene illustrato un esempio.</span><span class="sxs-lookup"><span data-stu-id="65ee8-127">The following example provides an illustration.</span></span> <span data-ttu-id="65ee8-128">Si supponga di avere installato un server in modalità tabulare come istanza denominata "tabulare" utilizzando l'account virtuale predefinito, ottenendo la seguente configurazione:</span><span class="sxs-lookup"><span data-stu-id="65ee8-128">Suppose you installed a tabular mode server as an instance named "Tabular" using the default virtual account, resulting in the following configuration:</span></span>  
  
    1.  <span data-ttu-id="65ee8-129">Nome istanza = \<server> \TABULAR</span><span class="sxs-lookup"><span data-stu-id="65ee8-129">Instance name = \<server>\TABULAR</span></span>  
  
    2.  <span data-ttu-id="65ee8-130">Nome servizio = MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="65ee8-130">Service name = MSOLAP$TABULAR</span></span>  
  
    3.  <span data-ttu-id="65ee8-131">Account virtuale = NT Service\ MSOLAP$TABULAR</span><span class="sxs-lookup"><span data-stu-id="65ee8-131">Virtual account = NT Service\ MSOLAP$TABULAR</span></span>  
  
     <span data-ttu-id="65ee8-132">Si supponga ora di rinominare l'istanza in "TAB2".</span><span class="sxs-lookup"><span data-stu-id="65ee8-132">Now suppose you rename the instance to "TAB2".</span></span> <span data-ttu-id="65ee8-133">Come un risultato della modifica del nome, la configurazione sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="65ee8-133">As a result of the name change, your configuration would now look like the following:</span></span>  
  
    1.  <span data-ttu-id="65ee8-134">Nome istanza = \<server> \TAB2</span><span class="sxs-lookup"><span data-stu-id="65ee8-134">Instance name = \<server>\TAB2</span></span>  
  
    2.  <span data-ttu-id="65ee8-135">Nome servizio = MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="65ee8-135">Service name = MSOLAP$TAB2</span></span>  
  
    3.  <span data-ttu-id="65ee8-136">Account virtuale =NT Service\ MSOLAP$TAB2</span><span class="sxs-lookup"><span data-stu-id="65ee8-136">Virtual account = NT Service\ MSOLAP$TAB2</span></span>  
  
     <span data-ttu-id="65ee8-137">Come si può notare, le autorizzazioni per database e file precedentemente concesse a "NT Service \ MSOLAP $ TABULAr" non sono più valide.</span><span class="sxs-lookup"><span data-stu-id="65ee8-137">As you can see, database and file permissions that were previously granted to "NT Service\ MSOLAP$TABULAR" are no longer valid.</span></span> <span data-ttu-id="65ee8-138">Per garantire che le attività e le operazioni eseguite dal servizio vengano eseguite come prima, ora è necessario concedere nuove autorizzazioni per database e file a "NT Service \ MSOLAP $ TAB2".</span><span class="sxs-lookup"><span data-stu-id="65ee8-138">To ensure that tasks and operations performed by the service run as before, you would now need to grant new database and file permissions to "NT Service\ MSOLAP$TAB2".</span></span>  
  
  
