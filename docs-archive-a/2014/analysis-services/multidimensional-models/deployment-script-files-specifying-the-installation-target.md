---
title: Impostazione della destinazione di installazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- installation targets [Analysis Services]
- Analysis Services deployments, installation targets
- Analysis Services Deployment Wizard, installation targets
- deploying [Analysis Services], installation targets
- modifying installation targets
ms.assetid: cb706817-6f63-4771-92c3-b70030bbce3d
author: minewiskan
ms.author: owend
ms.openlocfilehash: e830fc353898e3ec835b338e84765a0cad0de43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629643"
---
# <a name="specifying-the-installation-target"></a><span data-ttu-id="7fee7-102">Impostazione della destinazione di installazione</span><span class="sxs-lookup"><span data-stu-id="7fee7-102">Specifying the Installation Target</span></span>
  <span data-ttu-id="7fee7-103">La [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] distribuzione guidata legge le informazioni sulla destinazione di installazione dal \<*project name*> file con estensione deploymenttargets.</span><span class="sxs-lookup"><span data-stu-id="7fee7-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the installation target information from the \<*project name*>.deploymenttargets file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="7fee7-104">crea questo file quando si compila il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="7fee7-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="7fee7-105">utilizza il database e il server specificati nella pagina **distribuzione** della finestra di *\<project name>* dialogo Pagine delle **proprietà** per creare il file con \<*project name*> estensione targets.</span><span class="sxs-lookup"><span data-stu-id="7fee7-105">uses the database and server specified on the **Deployment** page of the *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.targets file.</span></span>  
  
## <a name="modifying-the-installation-target-for-deployment"></a><span data-ttu-id="7fee7-106">Modifica della destinazione di installazione per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="7fee7-106">Modifying the Installation Target for Deployment</span></span>  
 <span data-ttu-id="7fee7-107">In alcuni casi potrebbe essere necessario distribuire un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] su un database o un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] diversi da quelli specificati nella pagina **Distribuzione** .</span><span class="sxs-lookup"><span data-stu-id="7fee7-107">In some situations, you may need to deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that is different than the one specified on the **Deployment** page.</span></span> <span data-ttu-id="7fee7-108">Potrebbe essere utile ad esempio distribuire il progetto su un server di prova prima della distribuzione e successivamente distribuire il progetto su un server di produzione dopo il completamento delle prove.</span><span class="sxs-lookup"><span data-stu-id="7fee7-108">For example, you may want to deploy the project to a server for testing before deployment, and then deploy it to a production server after testing is finished.</span></span> <span data-ttu-id="7fee7-109">Quando il progetto è completato e testato, potrebbe essere opportuno distribuirlo su più server di produzione in un cluster con bilanciamento del carico di rete o su un server dell'area di gestione temporanea e un server di produzione.</span><span class="sxs-lookup"><span data-stu-id="7fee7-109">You may also want to deploy a completed and tested project to multiple production servers in a Network Load Balancing cluster, or to a staging server and a production server.</span></span>  
  
 <span data-ttu-id="7fee7-110">Per distribuire un progetto [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] su un database o un'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] diversi, è possibile modificare la destinazione di installazione nel file di input utilizzando uno dei metodi descritti nella procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="7fee7-110">To deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a different database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, you can change the installation target in the input file by using one of the methods described in the following procedure.</span></span>  
  
#### <a name="to-change-the-installation-target-after-the-input-files-have-been-generated"></a><span data-ttu-id="7fee7-111">Per modificare la destinazione di installazione dopo la generazione dei file di input.</span><span class="sxs-lookup"><span data-stu-id="7fee7-111">To change the installation target after the input files have been generated</span></span>  
  
-   <span data-ttu-id="7fee7-112">Eseguire Distribuzione guidata di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in modo interattivo.</span><span class="sxs-lookup"><span data-stu-id="7fee7-112">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="7fee7-113">Nella pagina **Destinazione installazione** , specificare una nuova destinazione per il database e l'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7fee7-113">On the **Installation Target** page, specify a new destination for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database.</span></span>  
  
     <span data-ttu-id="7fee7-114">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7fee7-114">-or-</span></span>  
  
-   <span data-ttu-id="7fee7-115">Eseguire Distribuzione guidata di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] attraverso il prompt dei comandi e impostarla in modo che venga eseguita in modalità file di risposte.</span><span class="sxs-lookup"><span data-stu-id="7fee7-115">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="7fee7-116">Per altre informazioni sulla modalità file di risposte, vedere [Esecuzione della Distribuzione guidata Analysis Services](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7fee7-116">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="7fee7-117">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7fee7-117">-or-</span></span>  
  
-   <span data-ttu-id="7fee7-118">Modificare il \<*project name*> file con estensione deploymenttargets utilizzando un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="7fee7-118">Modify the \<*project name*>.deploymenttargets file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fee7-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fee7-119">See Also</span></span>  
 <span data-ttu-id="7fee7-120">[Impostazione delle opzioni di distribuzione di partizioni e ruoli](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="7fee7-120">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 <span data-ttu-id="7fee7-121">[Specifica delle impostazioni di configurazione per la distribuzione della soluzione](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="7fee7-121">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="7fee7-122">Impostazione delle opzioni di elaborazione</span><span class="sxs-lookup"><span data-stu-id="7fee7-122">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
