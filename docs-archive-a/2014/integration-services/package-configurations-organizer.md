---
title: Libreria configurazioni pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.packageconfigurationorganizer.f1
helpviewer_keywords:
- Package Configurations Organizer dialog box
ms.assetid: f20ae6cb-9e6a-4d24-88ff-d7a903a4e8d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 67fdc9ca0faeff57c18fdb6e4d10acca3e9963f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721579"
---
# <a name="package-configurations-organizer"></a><span data-ttu-id="91f07-102">Libreria configurazioni pacchetto</span><span class="sxs-lookup"><span data-stu-id="91f07-102">Package Configurations Organizer</span></span>
  <span data-ttu-id="91f07-103">Usare la finestra di dialogo **Libreria configurazioni pacchetto** per abilitare le configurazioni dei pacchetti, visualizzarne un elenco per il pacchetto corrente e specificare l'ordine desiderato in base a cui devono essere caricate.</span><span class="sxs-lookup"><span data-stu-id="91f07-103">Use the **Package Configurations Organizer** dialog box to enable package configurations, view a list of configurations for the current package, and specify the preferred order in which the configurations should be loaded.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91f07-104">Le configurazioni sono disponibili per il modello di distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91f07-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="91f07-105">I parametri vengono utilizzati al posto delle configurazioni per il modello di distribuzione del progetto.</span><span class="sxs-lookup"><span data-stu-id="91f07-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="91f07-106">Con il modello di distribuzione del progetto è possibile distribuire i progetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] al server [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91f07-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="91f07-107">Per altre informazioni sui modelli di distribuzione, vedere [Distribuzione di progetti e pacchetti](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="91f07-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="91f07-108">Se più configurazioni aggiornano la stessa proprietà, i valori delle configurazioni che si trovano nella parte inferiore dell'elenco sostituiscono quelli delle configurazioni nelle posizioni superiori nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="91f07-108">If multiple configurations update the same property, values from configurations listed lower in the configuration list will replace values from configurations higher in the list.</span></span> <span data-ttu-id="91f07-109">L'ultimo valore caricato nella proprietà è quello utilizzato all'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91f07-109">The last value loaded into the property is the value that is used when the package runs.</span></span> <span data-ttu-id="91f07-110">Se il pacchetto utilizza una combinazione di configurazione diretta, ad esempio un file di configurazione XML, e indiretta, ad esempio una variabile di ambiente, la configurazione indiretta che punta al percorso della configurazione diretta deve trovarsi in una posizione superiore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="91f07-110">Also, if the package uses a combination of direct configuration such as an XML configuration file and an indirect configuration such as an environment variable, the indirect configuration that points to the location of the direct configuration must be higher in the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="91f07-111">Il caricamento delle configurazioni di pacchetto nell'ordine preferito avviene a partire dall'inizio dell'elenco visualizzato nella finestra di dialogo **Libreria configurazioni pacchetto** fino alla fine dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="91f07-111">When package configurations load in the preferred order, configurations load from the top of the list shown in the **Package Configuration Organizer** dialog box to the bottom of the list.</span></span> <span data-ttu-id="91f07-112">In fase di esecuzione, tuttavia, tali configurazioni potrebbero non essere caricate nell'ordine preferito.</span><span class="sxs-lookup"><span data-stu-id="91f07-112">However, at run time, package configurations might not load in the preferred order.</span></span> <span data-ttu-id="91f07-113">In particolare, le configurazioni di pacchetto padre vengono caricate dopo quelle di altri tipi.</span><span class="sxs-lookup"><span data-stu-id="91f07-113">In particular, Parent Package Configurations load after configurations of other types.</span></span>  
  
 <span data-ttu-id="91f07-114">Le configurazioni di pacchetto aggiornano i valori delle proprietà degli oggetti pacchetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91f07-114">Package configurations update the values of properties of package objects at run time.</span></span> <span data-ttu-id="91f07-115">Quando viene caricato un pacchetto, i valori delle configurazioni sostituiscono quelli impostati durante lo sviluppo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91f07-115">When a package is loaded, the values from the configurations replace the values that were set when the package was developed.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="91f07-116">supporta diversi tipi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="91f07-116">supports different configuration types.</span></span> <span data-ttu-id="91f07-117">È possibile, ad esempio, utilizzare un file XML che contiene più configurazioni o una variabile di ambiente che ne contiene una sola.</span><span class="sxs-lookup"><span data-stu-id="91f07-117">For example, you can use an XML file that can contain multiple configurations, or an environment variable that contains a single configuration.</span></span> <span data-ttu-id="91f07-118">Per altre informazioni, vedere [Configurazioni di pacchetto](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="91f07-118">For more information, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="91f07-119">Opzioni</span><span class="sxs-lookup"><span data-stu-id="91f07-119">Options</span></span>  
 <span data-ttu-id="91f07-120">**Abilita configurazioni pacchetto**</span><span class="sxs-lookup"><span data-stu-id="91f07-120">**Enable package configurations**</span></span>  
 <span data-ttu-id="91f07-121">Selezionare questa opzione per utilizzare le configurazioni con il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91f07-121">Select to use configurations with the package.</span></span>  
  
 <span data-ttu-id="91f07-122">**Nome configurazione**</span><span class="sxs-lookup"><span data-stu-id="91f07-122">**Configuration Name**</span></span>  
 <span data-ttu-id="91f07-123">Consente di visualizzare il nome della configurazione.</span><span class="sxs-lookup"><span data-stu-id="91f07-123">View the name of the configuration.</span></span>  
  
 <span data-ttu-id="91f07-124">**Tipo configurazione**</span><span class="sxs-lookup"><span data-stu-id="91f07-124">**Configuration Type**</span></span>  
 <span data-ttu-id="91f07-125">Consente di visualizzare il tipo di percorso in cui sono archiviate le configurazioni.</span><span class="sxs-lookup"><span data-stu-id="91f07-125">View the type of the location where configurations are stored.</span></span>  
  
 <span data-ttu-id="91f07-126">**Stringa di configurazione**</span><span class="sxs-lookup"><span data-stu-id="91f07-126">**Configuration String**</span></span>  
 <span data-ttu-id="91f07-127">Consente di visualizzare il percorso in cui sono archiviati i valori della configurazione,</span><span class="sxs-lookup"><span data-stu-id="91f07-127">View the location where the configuration values are stored.</span></span> <span data-ttu-id="91f07-128">che può essere il percorso di un file, il nome di una variabile di ambiente, il nome di una variabile del pacchetto padre, una chiave del Registro di sistema o il nome di una tabella di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91f07-128">The location can be the path of a file, the name of an environment variable, the name of a parent package variable, a Registry key, or the name of a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="91f07-129">**Oggetto di destinazione**</span><span class="sxs-lookup"><span data-stu-id="91f07-129">**Target Object**</span></span>  
 <span data-ttu-id="91f07-130">Consente di visualizzare il nome dell'oggetto aggiornato dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="91f07-130">View the name of the object that the configuration updates.</span></span> <span data-ttu-id="91f07-131">Se la configurazione è un file di configurazione XML o una tabella di SQL Server, la colonna sarà vuota perché questo tipo di configurazione può includere più oggetti.</span><span class="sxs-lookup"><span data-stu-id="91f07-131">If the configuration is an XML configuration file or a SQL Server table, the column is blank because the configuration can include multiple objects.</span></span>  
  
 <span data-ttu-id="91f07-132">**Proprietà di destinazione**</span><span class="sxs-lookup"><span data-stu-id="91f07-132">**Target Property**</span></span>  
 <span data-ttu-id="91f07-133">Consente di visualizzare il nome della proprietà modificata dalla configurazione.</span><span class="sxs-lookup"><span data-stu-id="91f07-133">View the name of the property modified by the configuration.</span></span> <span data-ttu-id="91f07-134">Se il tipo di configurazione supporta più configurazioni, questa colonna sarà vuota.</span><span class="sxs-lookup"><span data-stu-id="91f07-134">This column is blank if the configuration type supports multiple configurations.</span></span>  
  
 <span data-ttu-id="91f07-135">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="91f07-135">**Add**</span></span>  
 <span data-ttu-id="91f07-136">Consente di aggiungere una configurazione tramite la Configurazione guidata pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91f07-136">Add a configuration by using the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="91f07-137">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="91f07-137">**Edit**</span></span>  
 <span data-ttu-id="91f07-138">Consente di modificare una configurazione esistente rieseguendo la Configurazione guidata pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91f07-138">Edit an existing configuration by rerunning the Package Configuration Wizard.</span></span>  
  
 <span data-ttu-id="91f07-139">**Rimuovi**</span><span class="sxs-lookup"><span data-stu-id="91f07-139">**Remove**</span></span>  
 <span data-ttu-id="91f07-140">Selezionare una configurazione e quindi fare clic su **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="91f07-140">Select a configuration, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="91f07-141">**Frecce**</span><span class="sxs-lookup"><span data-stu-id="91f07-141">**Arrows**</span></span>  
 <span data-ttu-id="91f07-142">Selezionare una configurazione e utilizzare le frecce in su o in giù per spostarla verso l'alto o il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="91f07-142">Select a configuration and use the up and down arrows to move it up or down in the list.</span></span> <span data-ttu-id="91f07-143">Le configurazioni vengono caricate nella sequenza in base a cui sono ordinate nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="91f07-143">Configurations are loaded in the sequence in which they appear in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91f07-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91f07-144">See Also</span></span>  
 [<span data-ttu-id="91f07-145">Creazione di configurazioni dei pacchetti</span><span class="sxs-lookup"><span data-stu-id="91f07-145">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
