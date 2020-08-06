---
title: Eseguire un pacchetto in SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, running
- SSIS packages, running
- packages [Integration Services], running
- SQL Server Integration Services packages, running
ms.assetid: 318e6beb-5540-4101-82a5-18c9d47f0570
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 31ca2390ef6bb04b63e4de9978193aed8884da36
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713240"
---
# <a name="run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="8c260-102">Eseguire un pacchetto in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="8c260-102">Run a Package in SQL Server Data Tools</span></span>
  <span data-ttu-id="8c260-103">I pacchetti vengono eseguiti in genere in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] durante lo sviluppo, il debug e il test di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="8c260-103">You typically run packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] during the development, debugging, and testing of packages.</span></span> <span data-ttu-id="8c260-104">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] l'esecuzione dei pacchetti è sempre immediata.</span><span class="sxs-lookup"><span data-stu-id="8c260-104">When you run a package from [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the package always runs immediately.</span></span>  
  
 <span data-ttu-id="8c260-105">Durante l'esecuzione di un pacchetto, in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] viene visualizzato lo stato dell'esecuzione nella scheda **Stato** . È possibile visualizzare l'ora di inizio e di fine del pacchetto e delle attività e contenitori del pacchetto, oltre a informazioni sulle attività o contenitori che hanno avuto esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8c260-105">While a package is running, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer displays the progress of package execution on the **Progress** tab. You can view the start and finish time of the package and its tasks and containers, in addition to information about any tasks or containers in the package that failed.</span></span> <span data-ttu-id="8c260-106">Dopo l'esecuzione del pacchetto, nella scheda **Risultati esecuzione** sono disponibili le informazioni di run-time. Per altre informazioni, vedere la sezione "Report di stato" nell'argomento [Debug del flusso di controllo](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="8c260-106">After the package finishes running, the run-time information remains available on the **Execution Results** tab. For more information, see the section, "Progress Reporting," in the topic, [Debugging Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="8c260-107">**Distribuzione in fase di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="8c260-107">**Design-time deployment**.</span></span> <span data-ttu-id="8c260-108">Quando si esegue un pacchetto in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], il pacchetto viene compilato e quindi distribuito in una cartella.</span><span class="sxs-lookup"><span data-stu-id="8c260-108">When you run a package in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], the package is built and then deployed to a folder.</span></span> <span data-ttu-id="8c260-109">Prima di eseguire il pacchetto è possibile specificare la cartella in cui deve essere distribuito.</span><span class="sxs-lookup"><span data-stu-id="8c260-109">Before you run the package, you can specify the folder to which the package is deployed.</span></span> <span data-ttu-id="8c260-110">Se non si specifica alcuna cartella, per impostazione predefinita viene usata la cartella **bin** .</span><span class="sxs-lookup"><span data-stu-id="8c260-110">If you do not specify a folder, the **bin** folder is used by default.</span></span> <span data-ttu-id="8c260-111">Questo tipo di distribuzione è detto distribuzione in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8c260-111">This type of deployment is called design-time deployment.</span></span>  
  
### <a name="to-run-a-package-in-sql-server-data-tools"></a><span data-ttu-id="8c260-112">Per eseguire un pacchetto in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="8c260-112">To run a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="8c260-113">In Esplora soluzioni, se la soluzione contiene più progetti, fare clic con il pulsante destro del mouse sul progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto e quindi scegliere **Imposta come oggetto di avvio** per impostare il progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="8c260-113">In Solution Explorer, if your solution contains multiple projects, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package, and then click **Set as StartUp Object** to set the startup project.</span></span>  
  
2.  <span data-ttu-id="8c260-114">In Esplora soluzioni, se il progetto contiene più pacchetti, fare clic con il pulsante destro del mouse su un pacchetto e quindi scegliere **Imposta come oggetto di avvio** per impostare il pacchetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="8c260-114">In Solution Explorer, if your project contains multiple packages, right-click a package, and then click **Set as StartUp Object** to set the startup package.</span></span>  
  
3.  <span data-ttu-id="8c260-115">Per eseguire un pacchetto, attenersi a una delle procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c260-115">To run a package, use one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="8c260-116">Aprire il pacchetto da eseguire e quindi fare clic sul pulsante **Avvia debug** sulla barra dei menu oppure premere F5.</span><span class="sxs-lookup"><span data-stu-id="8c260-116">Open the package that you want to run and then click **Start Debugging** on the menu bar, or press F5.</span></span> <span data-ttu-id="8c260-117">Al termine dell'esecuzione del pacchetto premere MAIUSC+F5 per tornare alla modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="8c260-117">After the package finishes running, press Shift+F5 to return to design mode.</span></span>  
  
    -   <span data-ttu-id="8c260-118">In Esplora soluzioni fare clic con il pulsante destro del mouse sul pacchetto e quindi scegliere **Esegui pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="8c260-118">In Solution Explorer, right-click the package, and then click **Execute Package**.</span></span>  
  
### <a name="to-specify-a-different-folder-for-design-time-deployment"></a><span data-ttu-id="8c260-119">Per specificare una cartella diversa per la distribuzione in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="8c260-119">To specify a different folder for design-time deployment</span></span>  
  
1.  <span data-ttu-id="8c260-120">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla cartella del progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto da eseguire e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8c260-120">In Solution Explorer, right-click the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project folder that contains the package you want to run, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8c260-121">Nella finestra di dialogo **Pagine delle proprietà di \<project name>** fare clic su **Compila**.</span><span class="sxs-lookup"><span data-stu-id="8c260-121">In the **\<project name> Property Pages** dialog box, click **Build**.</span></span>  
  
3.  <span data-ttu-id="8c260-122">Aggiornare il valore della proprietà OutputPath per specificare la cartella da usare per la distribuzione in fase di progettazione e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c260-122">Update the value in the OutputPath property to specify the folder you want to use for design-time deployment, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c260-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c260-123">See Also</span></span>  
 <span data-ttu-id="8c260-124">[Esecuzione di progetti e pacchetti](packages/run-integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="8c260-124">[Execution of Projects and Packages](packages/run-integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="8c260-125">Pacchetti di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8c260-125">Integration Services &#40;SSIS&#41; Packages</span></span>](../../2014/integration-services/integration-services-ssis-packages.md)  
  
  
