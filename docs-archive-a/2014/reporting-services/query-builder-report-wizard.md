---
title: Generatore di query (creazione guidata report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.dataview.vdtquerydesigner.f1
- sql12.rtp.rptwizard.querybuilder.f1
helpviewer_keywords:
- Query Builder [Reporting Services]
ms.assetid: 1b0904ea-28c1-448e-b56c-c0fdfbc8b222
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 34369bc72fadae75afbc93eb03c0e40509dd27a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623874"
---
# <a name="query-builder-report-wizard"></a><span data-ttu-id="c274c-102">Generatore di query (Creazione guidata report)</span><span class="sxs-lookup"><span data-stu-id="c274c-102">Query Builder (Report Wizard)</span></span>
  <span data-ttu-id="c274c-103">Utilizzare un generatore di query per specificare una query che recuperi un set di risultati da utilizzare in un report.</span><span class="sxs-lookup"><span data-stu-id="c274c-103">Use the Query Builder to specify a query that retrieves a result set to use in a report.</span></span> <span data-ttu-id="c274c-104">È possibile scegliere tra due generatori di query:</span><span class="sxs-lookup"><span data-stu-id="c274c-104">You can choose between two query builders:</span></span>  
  
-   <span data-ttu-id="c274c-105">Il generatore di query generico predefinito offre un'area di lavoro estremamente semplice per l'impostazione di query e la visualizzazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="c274c-105">The text-based query builder (default) provides a simple workspace for specifying a query and viewing the results.</span></span> <span data-ttu-id="c274c-106">È possibile specificare più istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] , la sintassi della query o dei comandi per estensioni per l'elaborazione dati personalizzata e query che vengono specificate come espressioni.</span><span class="sxs-lookup"><span data-stu-id="c274c-106">You can specify multiple [!INCLUDE[tsql](../includes/tsql-md.md)] statements, query or command syntax for custom data processing extensions, and queries that are specified as expressions.</span></span> <span data-ttu-id="c274c-107">Poiché il generatore di query generico non esegue la pre-elaborazione della query e può gestire qualsiasi tipo di sintassi della query, rappresenta lo strumento di compilazione delle query predefinito per Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="c274c-107">Because the generic query builder does not preprocess the query and can accommodate any kind of query syntax, it is the default query builder tool for Report Designer.</span></span>  
  
-   <span data-ttu-id="c274c-108">Il generatore di query grafico offre una rappresentazione visiva più efficace.</span><span class="sxs-lookup"><span data-stu-id="c274c-108">The graphical query builder provides a richer visual experience.</span></span> <span data-ttu-id="c274c-109">Viene utilizzato in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] e in altre parti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c274c-109">It is used in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] and in other parts of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c274c-110">È possibile utilizzare il generatore di query grafico se non si desidera creare espressioni o istruzioni SQL in più parti.</span><span class="sxs-lookup"><span data-stu-id="c274c-110">You can use the graphical query builder if you are not creating expressions or multi-part SQL statements.</span></span>  
  
     <span data-ttu-id="c274c-111">Per passare al generatore di query grafico, attivare o disattivare il pulsante **Modifica come testo** nell'angolo in alto a sinistra della finestra.</span><span class="sxs-lookup"><span data-stu-id="c274c-111">To switch to the graphical query builder, toggle the **Edit As Text** button in the top left corner of the window.</span></span>  
  
 <span data-ttu-id="c274c-112">È inoltre possibile importare una query da un altro report.</span><span class="sxs-lookup"><span data-stu-id="c274c-112">You can also import a query from another report.</span></span>  
  
## <a name="query-builder-options"></a><span data-ttu-id="c274c-113">Opzioni relative al generatore di query</span><span class="sxs-lookup"><span data-stu-id="c274c-113">Query Builder Options</span></span>  
 <span data-ttu-id="c274c-114">**Modifica come testo**</span><span class="sxs-lookup"><span data-stu-id="c274c-114">**Edit As Text**</span></span>  
 <span data-ttu-id="c274c-115">Consente di passare tra una progettazione di query basata su testo e una grafica, se sono supportate entrambe dalla query.</span><span class="sxs-lookup"><span data-stu-id="c274c-115">Toggles between the text-based and graphical query designers, if both will work for the query.</span></span>  
  
 <span data-ttu-id="c274c-116">**Importa**</span><span class="sxs-lookup"><span data-stu-id="c274c-116">**Import**</span></span>  
 <span data-ttu-id="c274c-117">Consente di aprire la finestra di dialogo **Importa query** e di visualizzare i file con estensione rdl e sql per qualsiasi report disponibile.</span><span class="sxs-lookup"><span data-stu-id="c274c-117">Opens the **Import Query** dialog box and displays .rdl and .sql files for any available report.</span></span> <span data-ttu-id="c274c-118">È possibile utilizzare la query importata così com'è oppure modificarla nel generatore di query.</span><span class="sxs-lookup"><span data-stu-id="c274c-118">You can use the imported query as it is, or you can modify it in the query builder.</span></span>  
  
 <span data-ttu-id="c274c-119">**! (Esegui)**</span><span class="sxs-lookup"><span data-stu-id="c274c-119">**! (Run)**</span></span>  
 <span data-ttu-id="c274c-120">Consente di eseguire la query e di restituire un set di risultati nel caso in cui la query sia valida.</span><span class="sxs-lookup"><span data-stu-id="c274c-120">Runs the query and returns a result set if the query is valid.</span></span> <span data-ttu-id="c274c-121">Si noti che non è possibile eseguire la query nel caso in cui questa sia un'espressione.</span><span class="sxs-lookup"><span data-stu-id="c274c-121">Note that you cannot execute the query if it is an expression.</span></span> <span data-ttu-id="c274c-122">Per verificare una query basata su un'espressione, è necessario visualizzare l'anteprima del report.</span><span class="sxs-lookup"><span data-stu-id="c274c-122">To verify an expression-based query, you must preview the report.</span></span>  
  
 <span data-ttu-id="c274c-123">**Tipo di comando**</span><span class="sxs-lookup"><span data-stu-id="c274c-123">**Command type**</span></span>  
 <span data-ttu-id="c274c-124">Consente di specificare direttamente testo, stored procedure o tabelle.</span><span class="sxs-lookup"><span data-stu-id="c274c-124">Specifies text, stored procedure, or table direct.</span></span> <span data-ttu-id="c274c-125">La disponibilità di un determinato tipo di comando dipende dall'estensione per l'elaborazione dati specificata.</span><span class="sxs-lookup"><span data-stu-id="c274c-125">Availability of a command type depends on the data processing extension you specified.</span></span>  
  
 <span data-ttu-id="c274c-126">**Riquadro query**</span><span class="sxs-lookup"><span data-stu-id="c274c-126">**Query pane**</span></span>  
 <span data-ttu-id="c274c-127">Consente di digitare la query.</span><span class="sxs-lookup"><span data-stu-id="c274c-127">Type the query.</span></span>  
  
 <span data-ttu-id="c274c-128">**Riquadro risultati**</span><span class="sxs-lookup"><span data-stu-id="c274c-128">**Result pane**</span></span>  
 <span data-ttu-id="c274c-129">Visualizza il set di risultati restituito da una query.</span><span class="sxs-lookup"><span data-stu-id="c274c-129">Shows the result set returned from the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c274c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c274c-130">See Also</span></span>  
 <span data-ttu-id="c274c-131">[Set di set di impostazioni e set di impostazioni di set di report incorporati &#40;Generatore report e SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c274c-131">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c274c-132">Guida della Creazione guidata report</span><span class="sxs-lookup"><span data-stu-id="c274c-132">Report Wizard Help</span></span>](../../2014/reporting-services/report-wizard-help.md)  
  
  
