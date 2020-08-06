---
title: Concetti di base sui pacchetti SSIS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package requirements
ms.assetid: b0c86c35-e3d3-4724-9a96-4087e9d74bf3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7c58ddc13b5c149b84fa550f312782b02786d062
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718510"
---
# <a name="ssis-package-essentials"></a><span data-ttu-id="46ee4-102">Concetti di base sui pacchetti SSIS</span><span class="sxs-lookup"><span data-stu-id="46ee4-102">SSIS Package Essentials</span></span>
  <span data-ttu-id="46ee4-103">Un pacchetto è l'oggetto che consente di implementare la funzionalità [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per estrarre, trasformare e caricare i dati.</span><span class="sxs-lookup"><span data-stu-id="46ee4-103">A package is the object that implements [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] functionality to extract, transform, and load data.</span></span> <span data-ttu-id="46ee4-104">Un pacchetto viene creato utilizzando la finestra di progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46ee4-104">You create a package by using the [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="46ee4-105">oppure eseguendo Importazione/Esportazione guidata [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o Creazione guidata progetto connessioni in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="46ee4-105">You can also create a package by running the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard or the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Connections Project Wizard.</span></span> <span data-ttu-id="46ee4-106">Per ulteriori informazioni, [creare pacchetti in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) in Progettazione SSIS e [importazione guidata progetto](../../2014/integration-services/import-project-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="46ee4-106">For more information, [Create Packages in SQL Server Data Tools](create-packages-in-sql-server-data-tools.md) in SSIS Designer and [Import Project Wizard](../../2014/integration-services/import-project-wizard.md).</span></span>  
  
 <span data-ttu-id="46ee4-107">Un pacchetto di base include i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="46ee4-107">A basic package includes the following elements:</span></span>  
  
 <span data-ttu-id="46ee4-108">**Elementi del flusso di controllo**</span><span class="sxs-lookup"><span data-stu-id="46ee4-108">**Control flow elements**</span></span>  
 <span data-ttu-id="46ee4-109">Questi elementi obbligatori eseguono varie funzioni, come fornire la struttura e controllare l'ordine di esecuzione degli elementi.</span><span class="sxs-lookup"><span data-stu-id="46ee4-109">These required elements perform various functions, provide structure, and control the order in which elements run.</span></span> <span data-ttu-id="46ee4-110">Gli elementi del flusso di controllo principale sono attività, contenitori e vincoli di precedenza.</span><span class="sxs-lookup"><span data-stu-id="46ee4-110">The main control flow elements are tasks, containers, and precedence constraints.</span></span> <span data-ttu-id="46ee4-111">In un pacchetto deve esserci almeno un elemento del flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="46ee4-111">There must be at least one control flow element in a package.</span></span>  
  
 <span data-ttu-id="46ee4-112">Per altre informazioni, vedere [Flusso di controllo](control-flow/control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="46ee4-112">For more information, see [Control Flow](control-flow/control-flow.md).</span></span>  
  
 <span data-ttu-id="46ee4-113">**Elementi dei flussi di dati**</span><span class="sxs-lookup"><span data-stu-id="46ee4-113">**Data flow elements**</span></span>  
 <span data-ttu-id="46ee4-114">Questi elementi facoltativi estraggono, modificano e caricano dati nelle origini dati.</span><span class="sxs-lookup"><span data-stu-id="46ee4-114">These optional elements extract data, modify data, and load data into data sources.</span></span> <span data-ttu-id="46ee4-115">Gli elementi del flusso di dati principali sono origini, trasformazioni e destinazioni.</span><span class="sxs-lookup"><span data-stu-id="46ee4-115">The main data flow elements are sources, transformations, and destinations.</span></span> <span data-ttu-id="46ee4-116">Nel pacchetto non deve esserci alcun elemento del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="46ee4-116">There does not have to be any data flow elements in package.</span></span>  
  
 <span data-ttu-id="46ee4-117">Per altre informazioni, vedere [Flusso di dati](data-flow/data-flow.md).</span><span class="sxs-lookup"><span data-stu-id="46ee4-117">For more information, see [Data Flow](data-flow/data-flow.md).</span></span>  
  
 <span data-ttu-id="46ee4-118">Per un esempio di come creare un pacchetto di base, vedere [lezione 1: creazione del progetto e del pacchetto di base](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="46ee4-118">For an example of how to create a basic package, see [Lesson 1: Creating the Project and Basic Package](lesson-1-create-a-project-and-basic-package-with-ssis.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="46ee4-119">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="46ee4-119">Related Tasks</span></span>  
  
-   [<span data-ttu-id="46ee4-120">Creare pacchetti in SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="46ee4-120">Create Packages in SQL Server Data Tools</span></span>](create-packages-in-sql-server-data-tools.md)  
  
-   [<span data-ttu-id="46ee4-121">Aggiunta o eliminazione di un'attività o un contenitore in un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="46ee4-121">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
  
-   [<span data-ttu-id="46ee4-122">Impostazione delle proprietà di un'attività o di un contenitore</span><span class="sxs-lookup"><span data-stu-id="46ee4-122">Set the Properties of a Task or Container</span></span>](../../2014/integration-services/set-the-properties-of-a-task-or-container.md)  
  
-   [<span data-ttu-id="46ee4-123">Aggiunta o eliminazione di un componente in un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="46ee4-123">Add or Delete a Component in a Data Flow</span></span>](data-flow/add-or-delete-a-component-in-a-data-flow.md)  
  
## <a name="related-content"></a><span data-ttu-id="46ee4-124">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="46ee4-124">Related Content</span></span>  
  
1.  <span data-ttu-id="46ee4-125">Video, [Creazione di un pacchetto di base (video di SQL Server)](https://go.microsoft.com/fwlink/?LinkId=131023), nel sito MSDN.Microsoft.com</span><span class="sxs-lookup"><span data-stu-id="46ee4-125">Video, [Creating a Basic Package (SQL Server Video)](https://go.microsoft.com/fwlink/?LinkId=131023), on MSDN.Microsoft.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ee4-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46ee4-126">See Also</span></span>  
 <span data-ttu-id="46ee4-127">[Integration Services &#40;pacchetti&#41; SSIS](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="46ee4-127">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="46ee4-128">Vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="46ee4-128">Precedence Constraints</span></span>](control-flow/precedence-constraints.md)  
  
  
