---
title: Salvare una copia di un pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 21482a20-e420-4452-b7eb-8f9fa1929f31
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 02ee2374fddb7dbb6b17adc2a4a10707179c882d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714512"
---
# <a name="save-a-copy-of-a-package"></a><span data-ttu-id="0be07-102">Salvataggio di una copia di un pacchetto</span><span class="sxs-lookup"><span data-stu-id="0be07-102">Save a Copy of a Package</span></span>
  <span data-ttu-id="0be07-103">Questa procedura descrive come salvare una copia di un pacchetto nel file system, nell'archivio pacchetti o nel database **msdb** in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0be07-103">This procedure describes how to save a copy of a package to the file system, to the package store, or to the **msdb** database in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0be07-104">Quando si specifica il percorso di salvataggio della copia del pacchetto, è inoltre possibile modificarne il nome.</span><span class="sxs-lookup"><span data-stu-id="0be07-104">When you specify a location to save the package copy, you can also update the name of the package.</span></span>  
  
 <span data-ttu-id="0be07-105">L'archivio pacchetti può includere sia il database **msdb** che le cartelle del file system, solo **msdb**, oppure solo le cartelle del file system.</span><span class="sxs-lookup"><span data-stu-id="0be07-105">The package store can include both the **msdb** database and the folders in the file system, only **msdb**, or only folders in the file system.</span></span> <span data-ttu-id="0be07-106">In **msdb**i pacchetti vengono salvati nella tabella **sysssispackages** .</span><span class="sxs-lookup"><span data-stu-id="0be07-106">In **msdb**, packages are saved to the **sysssispackages** table.</span></span> <span data-ttu-id="0be07-107">Tale tabella include una colonna **folderid** che identifica la cartella logica alla quale il pacchetto appartiene.</span><span class="sxs-lookup"><span data-stu-id="0be07-107">This table includes a **folderid** column that identifies the logical folder to which the package belongs.</span></span> <span data-ttu-id="0be07-108">Le cartelle logiche consentono di raggruppare i pacchetti salvati in **msdb** , nello stesso modo in cui le cartelle del file system consentono di raggruppare i pacchetti salvati nel file system.</span><span class="sxs-lookup"><span data-stu-id="0be07-108">The logical folders provide a useful way to group packages saved to **msdb** in the same way that folders in the file system provide a way to group packages saved to the file system.</span></span> <span data-ttu-id="0be07-109">Le righe della tabella **sysssispackagefolders** di **msdb** definiscono le cartelle.</span><span class="sxs-lookup"><span data-stu-id="0be07-109">Rows in the **sysssispackagefolders** table in **msdb** define the folders.</span></span>  
  
 <span data-ttu-id="0be07-110">Se **msdb** non è definito come parte dell'archivio pacchetti, è possibile continuare ad associare i pacchetti a cartelle logiche esistenti se si seleziona SQL Server nell'opzione **Percorso pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="0be07-110">If **msdb** is not defined as part of the package store, you can continue to associate packages with existing logical folders when you select SQL Server in the **Package Path** option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0be07-111">Affinché sia possibile salvarne una copia, il pacchetto deve essere aperto in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0be07-111">The package must be opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer before you can save a copy of the package.</span></span>  
  
### <a name="to-save-a-copy-of-a-package"></a><span data-ttu-id="0be07-112">Per salvare una copia di un pacchetto</span><span class="sxs-lookup"><span data-stu-id="0be07-112">To save a copy of a package</span></span>  
  
1.  <span data-ttu-id="0be07-113">In Esplora soluzioni fare doppio clic sul pacchetto di cui si desidera salvare una copia.</span><span class="sxs-lookup"><span data-stu-id="0be07-113">In Solution Explorer, double-click the package of which you want to save a copy.</span></span>  
  
2.  <span data-ttu-id="0be07-114">Scegliere **Salva copia di \<package file> con nome** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="0be07-114">On the **File** menu, click **Save Copy of \<package file> As**.</span></span>  
  
3.  <span data-ttu-id="0be07-115">Nella finestra di dialogo **Salva copia del pacchetto** selezionare la posizione di un pacchetto dall'elenco **Posizione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="0be07-115">In the **Save Copy of Package** dialog box, select a package location in the **Package location** list.</span></span>  
  
4.  <span data-ttu-id="0be07-116">Se la posizione è **SQL Server** o **Archivio pacchetti SSIS**, specificare il nome di un server.</span><span class="sxs-lookup"><span data-stu-id="0be07-116">If the location is **SQL Server** or **SSIS Package Store**, provide a server name.</span></span>  
  
5.  <span data-ttu-id="0be07-117">Se si esegue il salvataggio in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], specificare il tipo di autenticazione e, se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare un nome utente e una password.</span><span class="sxs-lookup"><span data-stu-id="0be07-117">If saving to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], specify the authentication type and, if using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and password.</span></span>  
  
6.  <span data-ttu-id="0be07-118">Per specificare il percorso del pacchetto, digitarlo oppure fare clic sul pulsante Sfoglia **(...)** per specificare il percorso del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0be07-118">To specify the package path, either type the path or click the browse button **(...)** to specify the location of the package.</span></span> <span data-ttu-id="0be07-119">Il nome predefinito del pacchetto è Pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0be07-119">The default name of the package is Package.</span></span> <span data-ttu-id="0be07-120">In alternativa, modificare il nome del pacchetto in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="0be07-120">Optionally, update the package name to one that suits your needs.</span></span>  
  
     <span data-ttu-id="0be07-121">Se per l'opzione **Percorso pacchetto** si seleziona **SQL Server** , il percorso del pacchetto sarà composto dalle cartelle logiche di **msdb** più il nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0be07-121">If you select **SQL Server** as the **Package Path** option, the package path consists of logical folders in **msdb** and the package name.</span></span> <span data-ttu-id="0be07-122">Ad esempio, se il pacchetto DownloadMonthlyData è associato alla cartella Finance della cartella MSDB (il nome predefinito della cartella logica radice di **msdb**), il percorso del pacchetto denominato DownloadMonthlyData sarà MSDB/Finance/DownloadMonthlyData.</span><span class="sxs-lookup"><span data-stu-id="0be07-122">For example, if the package DownloadMonthlyData is associated with the Finance folder within the MSDB folder (the default name of the root logical folder in **msdb**), the package path for the package named DownloadMonthlyData is MSDB/Finance/DownloadMonthlyData</span></span>  
  
     <span data-ttu-id="0be07-123">Se per l'opzione **Percorso pacchetto** si seleziona **Archivio pacchetti SSIS** , il percorso del pacchetto corrisponderà alla cartella gestita dal servizio Integration Services.</span><span class="sxs-lookup"><span data-stu-id="0be07-123">If you select **SSIS Package Store** as the **Package Path** option, the package path consists of the folder that the Integration Services service manages.</span></span> <span data-ttu-id="0be07-124">Ad esempio, se il pacchetto UpdateDeductions si trova nella cartella HumanResources all'interno della cartella del file system gestita dal servizio, il percorso del pacchetto sarà /File System/HumanResources/UpdateDeductions. Analogamente, se il pacchetto PostResumes è associato alla cartella HumanResources della cartella MSDB, il percorso del pacchetto sarà MSDB/HumanResources/PostResumes.</span><span class="sxs-lookup"><span data-stu-id="0be07-124">For example, if the package UpdateDeductions is located in the HumanResources folder within the file system folder that the service manages, the package path is /File System/HumanResources/UpdateDeductions; likewise, if the package PostResumes is associated with the HumanResources folder within the MSDB folder, the package path is MSDB/HumanResources/PostResumes.</span></span>  
  
     <span data-ttu-id="0be07-125">Se per l'opzione **Percorso pacchetto** si seleziona **File system** , il percorso del pacchetto corrisponderà alla posizione nel file system più il nome del file.</span><span class="sxs-lookup"><span data-stu-id="0be07-125">If you select **File System** as the **Package Path** option, the package path is the location in the file system and the file name.</span></span> <span data-ttu-id="0be07-126">Ad esempio, se il nome del pacchetto è UpdateDemographics, il relativo percorso sarà C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span><span class="sxs-lookup"><span data-stu-id="0be07-126">For example, if the package name is UpdateDemographics the package path is C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span></span>  
  
7.  <span data-ttu-id="0be07-127">Controllare il livello di protezione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0be07-127">Review the package protection level.</span></span>  
  
8.  <span data-ttu-id="0be07-128">Facoltativamente, per modificare il livello di protezione fare clic sul pulsante Sfoglia **(...)** accanto alla casella **Livello di protezione**.</span><span class="sxs-lookup"><span data-stu-id="0be07-128">Optionally, click the browse button **(...)** by the **Protection level** box to change the protection level.</span></span>  
  
    -   <span data-ttu-id="0be07-129">Nella finestra di dialogo **Livello di protezione pacchetto** selezionare un livello di protezione diverso.</span><span class="sxs-lookup"><span data-stu-id="0be07-129">In the **Package Protection Level** dialog box, select a different protection level.</span></span>  
  
    -   <span data-ttu-id="0be07-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0be07-130">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0be07-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0be07-131">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0be07-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0be07-132">See Also</span></span>  
 <span data-ttu-id="0be07-133">[Integration Services &#40;pacchetti&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="0be07-133">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="0be07-134">Configurazione del servizio Integration Services &#40;servizio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="0be07-134">Configuring the Integration Services Service &#40;SSIS Service&#41;</span></span>](service/integration-services-service-ssis-service.md)  
  
  
