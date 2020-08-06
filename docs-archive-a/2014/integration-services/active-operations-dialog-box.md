---
title: Finestra di dialogo operazioni attive | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.ssms.isoperations.executions.f1
- sql12.ssis.ssms.isoperations.general.f1
ms.assetid: 5bb0fcd6-0ce9-488a-85b8-25dddaa03cda
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 49861de7be207875c554e02d3f3b1b2f941fff64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625530"
---
# <a name="active-operations-dialog-box"></a><span data-ttu-id="e2f85-102">Finestra di dialogo Operazioni attive</span><span class="sxs-lookup"><span data-stu-id="e2f85-102">Active Operations Dialog Box</span></span>
  <span data-ttu-id="e2f85-103">Utilizzare la finestra di dialogo **Operazioni attive** per visualizzare lo stato delle operazioni di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] attualmente in esecuzione nel server di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , ad esempio distribuzione, convalida ed esecuzione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e2f85-103">Use the **Active Operations** dialog box to view the status of currently running [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] operations on the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, such as deployment, validation, and package execution.</span></span> <span data-ttu-id="e2f85-104">Questi dati vengono archiviati nel catalogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="e2f85-104">This data is stored in the SSISDB catalog.</span></span>  
  
 <span data-ttu-id="e2f85-105">Per altre informazioni sulle viste [!INCLUDE[tsql](../includes/tsql-md.md)] correlate, vedere[catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database) e [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span><span class="sxs-lookup"><span data-stu-id="e2f85-105">For more information about related [!INCLUDE[tsql](../includes/tsql-md.md)] views, see [catalog.operations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-operations-ssisdb-database), [catalog.validations &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-validations-ssisdb-database), and [catalog.executions &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-executions-ssisdb-database)</span></span>  
  
 <span data-ttu-id="e2f85-106">**Per saperne di più**</span><span class="sxs-lookup"><span data-stu-id="e2f85-106">**What do you want to do?**</span></span>  
  
1.  [<span data-ttu-id="e2f85-107">Aprire la finestra di dialogo operazioni attive</span><span class="sxs-lookup"><span data-stu-id="e2f85-107">Open the Active Operations Dialog Box</span></span>](#open_dialog)  
  
2.  [<span data-ttu-id="e2f85-108">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="e2f85-108">Configure the Options</span></span>](#options)  
  
##  <a name="open-the-active-operations-dialog-box"></a><a name="open_dialog"></a> <span data-ttu-id="e2f85-109">Apertura della finestra di dialogo Operazioni attive</span><span class="sxs-lookup"><span data-stu-id="e2f85-109">Open the Active Operations Dialog Box</span></span>  
  
1.  <span data-ttu-id="e2f85-110">Aprire [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e2f85-110">Open [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="e2f85-111">Connettersi al motore di database di Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e2f85-111">Connect Microsoft SQL Server Database Engine</span></span>  
  
3.  <span data-ttu-id="e2f85-112">In Esplora oggetti espandere il nodo **Integration Services** , fare clic con il pulsante destro del mouse su **SSISDB**, quindi fare clic su **Operazioni attive**.</span><span class="sxs-lookup"><span data-stu-id="e2f85-112">In Object Explorer, expand the **Integration Services** node, right-click **SSISDB**, and then click **Active Operations**.</span></span>  
  
##  <a name="configure-the-options"></a><a name="options"></a> <span data-ttu-id="e2f85-113">Configurare le opzioni</span><span class="sxs-lookup"><span data-stu-id="e2f85-113">Configure the Options</span></span>  
  
### <a name="options"></a><span data-ttu-id="e2f85-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e2f85-114">Options</span></span>  
 <span data-ttu-id="e2f85-115">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e2f85-115">**Type**</span></span>  
 <span data-ttu-id="e2f85-116">Consente di specificare il tipo di operazione.</span><span class="sxs-lookup"><span data-stu-id="e2f85-116">Specifies the type of operation.</span></span> <span data-ttu-id="e2f85-117">Di seguito sono riportati i valori possibili per il campo **tipo** e i valori corrispondenti nella colonna operations_type della vista Transact-SQL `catalog.operations` .</span><span class="sxs-lookup"><span data-stu-id="e2f85-117">The following are the possible values for the **Type** field and the corresponding values in the operations_type column of the Transact-SQL `catalog.operations` view.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2f85-118">Inizializzazione di Integration Services</span><span class="sxs-lookup"><span data-stu-id="e2f85-118">Integration Services initialization</span></span>|<span data-ttu-id="e2f85-119">1</span><span class="sxs-lookup"><span data-stu-id="e2f85-119">1</span></span>|  
|<span data-ttu-id="e2f85-120">Pulizia di operazioni (processo di SQL Agent)</span><span class="sxs-lookup"><span data-stu-id="e2f85-120">Operations cleanup (SQL Agent job)</span></span>|<span data-ttu-id="e2f85-121">2</span><span class="sxs-lookup"><span data-stu-id="e2f85-121">2</span></span>|  
|<span data-ttu-id="e2f85-122">Pulizia delle versioni del progetto (processo di SQL Agent)</span><span class="sxs-lookup"><span data-stu-id="e2f85-122">Project versions cleanup (SQL Agent job)</span></span>|<span data-ttu-id="e2f85-123">3</span><span class="sxs-lookup"><span data-stu-id="e2f85-123">3</span></span>|  
|<span data-ttu-id="e2f85-124">Distribuzione del progetto</span><span class="sxs-lookup"><span data-stu-id="e2f85-124">Deploy project</span></span>|<span data-ttu-id="e2f85-125">101</span><span class="sxs-lookup"><span data-stu-id="e2f85-125">101</span></span>|  
|<span data-ttu-id="e2f85-126">Ripristino del progetto</span><span class="sxs-lookup"><span data-stu-id="e2f85-126">Restore project</span></span>|<span data-ttu-id="e2f85-127">106</span><span class="sxs-lookup"><span data-stu-id="e2f85-127">106</span></span>|  
|<span data-ttu-id="e2f85-128">Creazione e avvio dell'esecuzione del pacchetto</span><span class="sxs-lookup"><span data-stu-id="e2f85-128">Create and start package execution</span></span>|<span data-ttu-id="e2f85-129">200</span><span class="sxs-lookup"><span data-stu-id="e2f85-129">200</span></span>|  
|<span data-ttu-id="e2f85-130">Arresto dell'operazione (arresto di una convalida o di un'esecuzione)</span><span class="sxs-lookup"><span data-stu-id="e2f85-130">Stop operation (stopping a validation or execution</span></span>|<span data-ttu-id="e2f85-131">202</span><span class="sxs-lookup"><span data-stu-id="e2f85-131">202</span></span>|  
|<span data-ttu-id="e2f85-132">Convalida del progetto</span><span class="sxs-lookup"><span data-stu-id="e2f85-132">Validate project</span></span>|<span data-ttu-id="e2f85-133">300</span><span class="sxs-lookup"><span data-stu-id="e2f85-133">300</span></span>|  
|<span data-ttu-id="e2f85-134">Convalida del pacchetto</span><span class="sxs-lookup"><span data-stu-id="e2f85-134">Validate package</span></span>|<span data-ttu-id="e2f85-135">301</span><span class="sxs-lookup"><span data-stu-id="e2f85-135">301</span></span>|  
|<span data-ttu-id="e2f85-136">Configurazione del catalogo</span><span class="sxs-lookup"><span data-stu-id="e2f85-136">Configure catalog</span></span>|<span data-ttu-id="e2f85-137">1000</span><span class="sxs-lookup"><span data-stu-id="e2f85-137">1000</span></span>|  
  
 <span data-ttu-id="e2f85-138">**Stop**</span><span class="sxs-lookup"><span data-stu-id="e2f85-138">**Stop**</span></span>  
 <span data-ttu-id="e2f85-139">Fare clic per arrestare un'operazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e2f85-139">Click to stop a currently running operation.</span></span>  
  
  
