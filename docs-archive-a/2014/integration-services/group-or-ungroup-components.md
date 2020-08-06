---
title: Raggruppare o separare componenti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- grouping containers
- tasks [Integration Services], grouping
- containers [Integration Services], grouping
- grouping tasks
ms.assetid: 34320838-c271-4f8c-90b3-1254690890bb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f6811dffca41a12fe0afeeeb334e0107ac127c12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624832"
---
# <a name="group-or-ungroup-components"></a><span data-ttu-id="4995f-102">Raggruppare o separare componenti</span><span class="sxs-lookup"><span data-stu-id="4995f-102">Group or Ungroup Components</span></span>
  <span data-ttu-id="4995f-103">Le schede **Flusso di controllo**, **Flusso di dati**e **Gestori eventi** in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] supportano il raggruppamento comprimibile.</span><span class="sxs-lookup"><span data-stu-id="4995f-103">The **Control Flow**, **Data Flow**, and **Event Handlers** tabs in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer supports collapsible grouping.</span></span> <span data-ttu-id="4995f-104">Se un pacchetto include molti contenitori, è possibile che le schede contengano un numero di elementi talmente elevato da impedire di visualizzare contemporaneamente tutti gli elementi del flusso di controllo del pacchetto e di individuare l'elemento che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="4995f-104">If a package has many components, the tabs can become crowded, making it difficult to view all the components at one time and to locate the item with which you want to work.</span></span> <span data-ttu-id="4995f-105">La funzionalità raggruppamento comprimibile consente di risparmiare spazio nell'area di lavoro e semplificare la gestione di pacchetti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="4995f-105">The collapsible grouping feature can conserve space on the work surface and make it easier to work with large packages.</span></span>  
  
 <span data-ttu-id="4995f-106">È possibile selezionare i componenti che si desidera raggruppare, eseguire il raggruppamento, quindi espandere o comprimere i gruppi in base alle proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="4995f-106">You select the components that you want to group, group them, and then expand or collapse the groups to suit your work.</span></span> <span data-ttu-id="4995f-107">Espandendo un gruppo sarà possibile accedere alle proprietà dei componenti inclusi.</span><span class="sxs-lookup"><span data-stu-id="4995f-107">Expanding a group provides access to the properties of the components in the group.</span></span> <span data-ttu-id="4995f-108">I vincoli di precedenza che connettono attività e contenitori vengono automaticamente inclusi nel gruppo.</span><span class="sxs-lookup"><span data-stu-id="4995f-108">The precedence constraints that connect tasks and containers are automatically included in the group.</span></span>  
  
 <span data-ttu-id="4995f-109">Di seguito sono riportate alcune considerazioni per il raggruppamento di componenti.</span><span class="sxs-lookup"><span data-stu-id="4995f-109">The following are considerations for grouping components.</span></span>  
  
-   <span data-ttu-id="4995f-110">Per raggruppare componenti, il flusso di controllo, il flusso di dati o il gestore eventi deve contenere più di un componente.</span><span class="sxs-lookup"><span data-stu-id="4995f-110">To group components, the control flow, data flow, or event handler must contain more than one component.</span></span>  
  
-   <span data-ttu-id="4995f-111">I gruppi possono inoltre essere nidificati, consentendo la creazione di sottogruppi.</span><span class="sxs-lookup"><span data-stu-id="4995f-111">Groups can also be nested, making it possible to create groups within groups.</span></span> <span data-ttu-id="4995f-112">Nell'area di progettazione è possibile implementare più gruppi non nidificati, ma un componente può appartenere a un solo gruppo, a meno che i gruppi non siano nidificati.</span><span class="sxs-lookup"><span data-stu-id="4995f-112">The design surface can implement multiple un-nested groups, but a component can belong to only one group, unless the groups are nested.</span></span>  
  
-   <span data-ttu-id="4995f-113">Quando si salva un pacchetto, in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] viene salvato anche il raggruppamento, ma quest'ultimo non ha alcun effetto sull'esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4995f-113">When a package is saved, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the grouping, but the grouping has no effect on package execution.</span></span> <span data-ttu-id="4995f-114">La possibilità di raggruppare componenti è una funzionalità della fase di progettazione e non influisce sul comportamento di un pacchetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4995f-114">The ability to group components is a design-time feature; it does not affect the run-time behavior of the package.</span></span>  
  
### <a name="to-group-components"></a><span data-ttu-id="4995f-115">Per raggruppare componenti</span><span class="sxs-lookup"><span data-stu-id="4995f-115">To group components</span></span>  
  
1.  <span data-ttu-id="4995f-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="4995f-116">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4995f-117">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4995f-117">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4995f-118">Fare clic sulla scheda **Flusso di controllo**, **Flusso di dati**o **Gestori eventi** .</span><span class="sxs-lookup"><span data-stu-id="4995f-118">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="4995f-119">Nell'area di progettazione della scheda selezionare i componenti da raggruppare, fare clic con il pulsante destro del mouse su un componente selezionato e quindi scegliere **Raggruppa**.</span><span class="sxs-lookup"><span data-stu-id="4995f-119">On the design surface of the tab, select the components you want to group, right-click a selected component, and then click **Group**.</span></span>  
  
5.  <span data-ttu-id="4995f-120">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="4995f-120">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-ungroup-components"></a><span data-ttu-id="4995f-121">Per separare componenti</span><span class="sxs-lookup"><span data-stu-id="4995f-121">To ungroup components</span></span>  
  
1.  <span data-ttu-id="4995f-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="4995f-122">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="4995f-123">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="4995f-123">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="4995f-124">Fare clic sulla scheda **Flusso di controllo**, **Flusso di dati**o **Gestori eventi** .</span><span class="sxs-lookup"><span data-stu-id="4995f-124">Click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="4995f-125">Nell'area di progettazione della scheda selezionare il gruppo che contiene il componente da separare, fare clic con il pulsante destro del mouse e quindi scegliere **Separa**.</span><span class="sxs-lookup"><span data-stu-id="4995f-125">On the design surface of the tab, select the group that contains the component you want to ungroup, right-click, and then click **Ungroup**.</span></span>  
  
5.  <span data-ttu-id="4995f-126">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="4995f-126">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4995f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4995f-127">See Also</span></span>  
 [<span data-ttu-id="4995f-128">Aggiunta o eliminazione di un'attività o un contenitore in un flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="4995f-128">Add or Delete a Task or a Container in a Control Flow</span></span>](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)  
     
 [<span data-ttu-id="4995f-129">Connettere attività e contenitori tramite un vincolo di precedenza predefinito</span><span class="sxs-lookup"><span data-stu-id="4995f-129">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md)  
  
  
