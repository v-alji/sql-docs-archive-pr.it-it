---
title: Impostazione delle opzioni di distribuzione di partizioni e ruoli | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- partitions [Analysis Services], deployment options
- Analysis Services deployments, roles
- Analysis Services deployments, partitions
- Analysis Services Deployment Wizard, roles
- Analysis Services Deployment Wizard, partitions
- deploying [Analysis Services], roles
- roles [Analysis Services], deployment options
- deploying [Analysis Services], partitions
- modifying role deployments
- modifying partition deployments
ms.assetid: e9b9ca57-a5cc-4fc0-87b5-305257038d56
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8c8dd7bcb482c2d28a18e3039f5acb777b121202
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636906"
---
# <a name="specifying-partition-and-role-deployment-options"></a><span data-ttu-id="7b488-102">Impostazione delle opzioni di distribuzione dei ruoli e delle partizioni</span><span class="sxs-lookup"><span data-stu-id="7b488-102">Specifying Partition and Role Deployment Options</span></span>
  <span data-ttu-id="7b488-103">La [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] distribuzione guidata legge le opzioni di distribuzione delle partizioni e dei ruoli dal \<*project name*> file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7b488-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the partition and role deployment options from the \<*project name*>.deploymentoptions file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="7b488-104">crea questo file quando si compila il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="7b488-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="7b488-105">Usa le opzioni di distribuzione dei ruoli e delle partizioni del progetto corrente quando \<*project name*> viene creato il file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7b488-105">uses the partition and role deployment options of the current project when the \<*project name*>.deploymentoptions file is created.</span></span> <span data-ttu-id="7b488-106">Per altre informazioni sulle impostazioni di configurazione, vedere [Informazioni sui file di input utilizzati per creare uno script di distribuzione](deployment-script-files-input-used-to-create-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="7b488-106">For more information about configuration settings, see [Understanding the Input Files Used to Create the Deployment Script](deployment-script-files-input-used-to-create-deployment-script.md).</span></span>  
  
## <a name="reviewing-the-partition-and-role-deployment-options"></a><span data-ttu-id="7b488-107">Esame delle opzioni di distribuzione dei ruoli e delle partizioni</span><span class="sxs-lookup"><span data-stu-id="7b488-107">Reviewing the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="7b488-108">Di seguito sono riportate le opzioni di distribuzione del \<*project name*> file con estensione deploymentoptions:</span><span class="sxs-lookup"><span data-stu-id="7b488-108">The deployment options in the \<*project name*>.deploymentoptions file include the following:</span></span>  
  
 <span data-ttu-id="7b488-109">**Opzioni di distribuzione delle partizioni**</span><span class="sxs-lookup"><span data-stu-id="7b488-109">**Partition deployment options**</span></span>  
 <span data-ttu-id="7b488-110">Il \<*project name*> file con estensione deploymentoptions specifica se le partizioni esistenti nel database di destinazione vengono mantenute o sovrascritte (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="7b488-110">The \<*project name*>.deploymentoptions file specifies whether existing partitions in the destination database are retained or overwritten (default).</span></span> <span data-ttu-id="7b488-111">Se le partizioni esistenti vengono mantenute, verranno distribuite solo le nuove partizioni, e le partizioni e le progettazioni delle aggregazioni in tutti i gruppi di misure esistenti non saranno modificate.</span><span class="sxs-lookup"><span data-stu-id="7b488-111">If existing partitions are retained, only new partitions will be deployed, and the partitions and aggregation designs on all existing measure groups are left unchanged.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b488-112">Se il gruppo di misure contenente la partizione viene eliminato, la partizione viene eliminata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7b488-112">If the measure group in which the partition exists is deleted, the partition is automatically deleted.</span></span>  
  
 <span data-ttu-id="7b488-113">**Opzioni di distribuzione dei ruoli**</span><span class="sxs-lookup"><span data-stu-id="7b488-113">**Role deployment options**</span></span>  
 <span data-ttu-id="7b488-114">Il \<*project name*> file con estensione deploymentoptions specifica una delle opzioni di distribuzione dei ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b488-114">The \<*project name*>.deploymentoptions file specifies one of the following role deployment options:</span></span>  
  
-   <span data-ttu-id="7b488-115">I ruoli e i membri di ruolo esistenti contenuti nel database di destinazione vengono mantenuti e vengono distribuiti solo i nuovi ruoli e membri di ruolo.</span><span class="sxs-lookup"><span data-stu-id="7b488-115">Existing roles and role members in the destination database are retained, and only new roles and role members are deployed.</span></span>  
  
-   <span data-ttu-id="7b488-116">Tutti i membri e ruoli esistenti contenuti nel database di destinazione vengono sostituiti dai ruoli e dai membri distribuiti.</span><span class="sxs-lookup"><span data-stu-id="7b488-116">All existing roles and members in the destination database are replaced by the roles and members being deployed.</span></span>  
  
-   <span data-ttu-id="7b488-117">I ruoli e i membri di ruolo esistenti contenuti nel database di destinazione vengono mantenuti e non viene distribuito nessun nuovo ruolo.</span><span class="sxs-lookup"><span data-stu-id="7b488-117">Existing roles and role members in the destination database are retained, and no new roles are deployed.</span></span>  
  
-   <span data-ttu-id="7b488-118">**Nota** Quando vengono mantenuti i ruoli e i membri esistenti, le autorizzazioni associate a tali ruoli vengono reimpostate su nessuna autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="7b488-118">**Note** When existing roles and members are retained, the permissions associated with those roles are reset to none.</span></span> <span data-ttu-id="7b488-119">Le autorizzazioni di sicurezza sono contenute negli oggetti da esse protetti, non nei ruoli di sicurezza a cui sono associate.</span><span class="sxs-lookup"><span data-stu-id="7b488-119">Security permissions are contained by the objects they secure, not by the security roles with which they are associated.</span></span> <span data-ttu-id="7b488-120">Per ulteriori informazioni su come utilizzare questo comportamento utilizzando la distribuzione guidata Analysis Services, vedere "Mantieni ruoli e membri" nella Microsoft Knowledge base.</span><span class="sxs-lookup"><span data-stu-id="7b488-120">For more information about how to work with this behavior by using the Analysis Service Deployment Wizard, see 'Retain Roles and Members' in the Microsoft Knowledge Base.</span></span>  
  
## <a name="modifying-the-partition-and-role-deployment-options"></a><span data-ttu-id="7b488-121">Modifica delle opzioni di distribuzione dei ruoli e delle partizioni</span><span class="sxs-lookup"><span data-stu-id="7b488-121">Modifying the Partition and Role Deployment Options</span></span>  
 <span data-ttu-id="7b488-122">Potrebbe essere necessario distribuire il [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto utilizzando diverse opzioni di partizione e ruolo rispetto a quelle archiviate nel \<*project name*> file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7b488-122">You may have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project using different partition and role options than those stored in the \<*project name*>.deploymentoptions file.</span></span> <span data-ttu-id="7b488-123">È possibile, ad esempio, mantenere le partizioni, i ruoli e i membri del ruolo esistenti, anziché sostituire tutte le partizioni, i ruoli e i membri esistenti, come indicato nel \<*project name*> file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7b488-123">For example, you may want to retain existing partitions, roles, and role members, instead of replacing all existing partitions, roles, and members as indicated in the \<*project name*>.deploymentoptions file.</span></span>  
  
 <span data-ttu-id="7b488-124">Per modificare la distribuzione di partizioni e ruoli in un [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto, non è possibile modificare le impostazioni delle partizioni e dei ruoli all'interno del progetto perché nella finestra *\<project name>* di dialogo **pagine delle proprietà** di non vengono [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] visualizzate tali opzioni.</span><span class="sxs-lookup"><span data-stu-id="7b488-124">To modify the deployment of partitions and roles in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, you cannot change the partition and roles settings within the project because the *\<project name>* **Properties Pages** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] does not display these options.</span></span> <span data-ttu-id="7b488-125">Se si desidera modificare le opzioni di distribuzione per ruoli e partizioni, è necessario modificare queste informazioni all'interno del \<*project name*> file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7b488-125">If you want to change the deployment options for roles and partitions, you must change this information within the \<*project name*>.deploymentoptions file itself.</span></span> <span data-ttu-id="7b488-126">Nella procedura seguente viene descritto come modificare le opzioni di distribuzione di partizioni e ruoli all'interno del \<*project name*> file con estensione deploymentoptions.</span><span class="sxs-lookup"><span data-stu-id="7b488-126">The following procedure describes how to change the partition and role deployment options within the \<*project name*>.deploymentoptions file.</span></span>  
  
#### <a name="to-change-the-deployment-of-partitions-or-roles-after-the-input-files-have-been-generated"></a><span data-ttu-id="7b488-127">Per modificare la distribuzione delle partizioni o dei ruoli dopo la generazione dei file di input</span><span class="sxs-lookup"><span data-stu-id="7b488-127">To change the deployment of partitions or roles after the input files have been generated</span></span>  
  
-   <span data-ttu-id="7b488-128">Eseguire Distribuzione guidata di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in modo interattivo e specificare nuove opzioni di distribuzione delle partizioni e dei ruoli nella pagina relativa alle **opzioni partizioni e ruoli della distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="7b488-128">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively, and on the **Partition and Role Deployment Options** page, specify new deployment options for the partitions and roles.</span></span>  
  
     <span data-ttu-id="7b488-129">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7b488-129">-or-</span></span>  
  
-   <span data-ttu-id="7b488-130">Eseguire Distribuzione guidata di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] attraverso il prompt dei comandi e impostarla in modo che venga eseguita in modalità file di risposte.</span><span class="sxs-lookup"><span data-stu-id="7b488-130">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt, and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="7b488-131">Per ulteriori informazioni sulla modalità file di risposte, vedere [esecuzione della distribuzione guidata Analysis Services](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7b488-131">(For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).)</span></span>  
  
     <span data-ttu-id="7b488-132">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7b488-132">-or-</span></span>  
  
-   <span data-ttu-id="7b488-133">Aprire il \<*project name*> deploymentoptions in qualsiasi editor di testo e modificare manualmente le opzioni.</span><span class="sxs-lookup"><span data-stu-id="7b488-133">Open the \<*project name*>.deploymentoptions in any text editor and manually change the options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b488-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b488-134">See Also</span></span>  
 <span data-ttu-id="7b488-135">[Impostazione della destinazione di installazione](deployment-script-files-specifying-the-installation-target.md) </span><span class="sxs-lookup"><span data-stu-id="7b488-135">[Specifying the Installation Target](deployment-script-files-specifying-the-installation-target.md) </span></span>  
 <span data-ttu-id="7b488-136">[Specifica delle impostazioni di configurazione per la distribuzione della soluzione](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7b488-136">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="7b488-137">Impostazione delle opzioni di elaborazione</span><span class="sxs-lookup"><span data-stu-id="7b488-137">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
