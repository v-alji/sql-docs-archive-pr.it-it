---
title: Copiare oggetti di pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- control flow [Integration Services], copying objects
- copying package objects [Integration Services]
- data flow [Integration Services], copying objects
- connection managers [Integration Services], copying
ms.assetid: 99b85e5c-d6bd-4e7c-afe4-51f6ce151c2f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3219f0023c9a28ed270adeb6fd2b795e3459c3e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626205"
---
# <a name="copy-package-objects"></a><span data-ttu-id="07ded-102">Copia di oggetti di pacchetto</span><span class="sxs-lookup"><span data-stu-id="07ded-102">Copy Package Objects</span></span>
  <span data-ttu-id="07ded-103">In questo argomento viene descritta la procedura per copiare elementi di un flusso di controllo, elementi di un flusso di dati e gestioni connessioni all'interno di un pacchetto o tra pacchetti diversi.</span><span class="sxs-lookup"><span data-stu-id="07ded-103">This topic describes how to copy control flow items, data flow items, and connection managers within a package or between packages.</span></span>  
  
### <a name="to-copy-control-and-data-flow-items"></a><span data-ttu-id="07ded-104">Per copiare elementi di un flusso di controllo o di un flusso di dati</span><span class="sxs-lookup"><span data-stu-id="07ded-104">To copy control and data flow items</span></span>  
  
1.  <span data-ttu-id="07ded-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente i pacchetti da usare.</span><span class="sxs-lookup"><span data-stu-id="07ded-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the packages that you want work with.</span></span>  
  
2.  <span data-ttu-id="07ded-106">In Esplora soluzioni fare doppio clic sui pacchetti tra cui si desidera copiare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="07ded-106">In Solution Explorer, double-click the packages that you want to copy between.</span></span>  
  
3.  <span data-ttu-id="07ded-107">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] fare clic sulla scheda corrispondente al pacchetto che contiene gli elementi da copiare e quindi fare clic sulla scheda **Flusso di controllo**, **Flusso di dati**o **Gestori eventi** .</span><span class="sxs-lookup"><span data-stu-id="07ded-107">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the tab for the package that contains the items to copy and click the **Control Flow**, **Data Flow**, or **Event Handlers** tab.</span></span>  
  
4.  <span data-ttu-id="07ded-108">Selezionare gli elementi del flusso di controllo o di dati che si desidera copiare.</span><span class="sxs-lookup"><span data-stu-id="07ded-108">Select the control flow or data flow items to copy.</span></span> <span data-ttu-id="07ded-109">È possibile selezionare un elemento alla volta, facendo clic sugli elementi desiderati mentre si tiene premuto il tasto MAIUSC, oppure selezionarli come gruppo, trascinando il puntatore del mouse sugli elementi desiderati.</span><span class="sxs-lookup"><span data-stu-id="07ded-109">You can either select items one at a time by pressing the Shift key and clicking the item or select items as a group by dragging the pointer across the items you want to select.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="07ded-110">Quando si selezionano due elementi connessi, i vincoli di precedenza e i percorsi che li connettono non vengono selezionati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="07ded-110">The precedence constraints and paths that connect items are not selected automatically when you select the two items that they connect.</span></span> <span data-ttu-id="07ded-111">Per copiare un flusso di lavoro ordinato, come un segmento di un flusso di controllo o di dati, assicurarsi di copiare anche i percorsi e i vincoli di precedenza.</span><span class="sxs-lookup"><span data-stu-id="07ded-111">To copy an ordered workflow-a segment of control flow or data flow-make sure to also copy the precedence constrains and the paths.</span></span>  
  
5.  <span data-ttu-id="07ded-112">Fare clic con il pulsante destro del mouse su un elemento selezionato e quindi scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="07ded-112">Right-click a selected item and click **Copy**.</span></span>  
  
6.  <span data-ttu-id="07ded-113">Se si copiano elementi in un pacchetto diverso, fare clic sul pacchetto in cui si desidera copiare gli elementi e quindi fare clic sulla scheda corrispondente al tipo di elemento.</span><span class="sxs-lookup"><span data-stu-id="07ded-113">If copying items to a different package, click the package that you want to copy to, and then click the appropriate tab for the item type.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="07ded-114">È possibile copiare un flusso di dati in un pacchetto solo se il pacchetto contiene almeno un'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="07ded-114">You cannot copy a data flow to a package unless the package contains at least one Data Flow task.</span></span>  
  
7.  <span data-ttu-id="07ded-115">Fare clic con il pulsante destro del mouse e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="07ded-115">Right-click and click **Paste**.</span></span>  
  
### <a name="to-copy-connection-managers"></a><span data-ttu-id="07ded-116">Per copiare gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="07ded-116">To copy connection managers</span></span>  
  
1.  <span data-ttu-id="07ded-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto da usare.</span><span class="sxs-lookup"><span data-stu-id="07ded-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package that you want to work with.</span></span>  
  
2.  <span data-ttu-id="07ded-118">In Esplora soluzioni fare doppio clic sul pacchetto.</span><span class="sxs-lookup"><span data-stu-id="07ded-118">In Solution Explorer, double-click the package.</span></span>  
  
3.  <span data-ttu-id="07ded-119">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] fare clic sulla scheda **Flusso di controllo**, **Flusso di dati**o **Gestori eventi** .</span><span class="sxs-lookup"><span data-stu-id="07ded-119">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
4.  <span data-ttu-id="07ded-120">Nella sezione **Gestioni connessioni** fare clic con il pulsante destro del mouse sulla gestione connessione e quindi scegliere **Copia**.</span><span class="sxs-lookup"><span data-stu-id="07ded-120">In the **Connection Managers** area, right-click the connection manager, and then click **Copy**.</span></span> <span data-ttu-id="07ded-121">È possibile copiare una sola gestione connessione alla volta.</span><span class="sxs-lookup"><span data-stu-id="07ded-121">You can copy only one connection manager at a time.</span></span>  
  
5.  <span data-ttu-id="07ded-122">Se si copiano elementi in un pacchetto diverso, fare clic sul pacchetto in cui si vogliono copiare gli elementi e quindi fare clic sulla scheda **Flusso di controllo**, **Flusso di dati**o **Gestori eventi** .</span><span class="sxs-lookup"><span data-stu-id="07ded-122">If you are copying items to a different package, click the package that you want to copy to and then click the **Control Flow**, **Data Flow**, or **Event Handler** tab.</span></span>  
  
6.  <span data-ttu-id="07ded-123">Fare clic con il pulsante destro del mouse nella sezione **Gestioni connessioni** e scegliere **Incolla**.</span><span class="sxs-lookup"><span data-stu-id="07ded-123">Right-click in the **Connection Managers** area and click **Paste**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ded-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07ded-124">See Also</span></span>  
 <span data-ttu-id="07ded-125">[Flusso di controllo](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="07ded-125">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="07ded-126">[Flusso di dati](data-flow/data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="07ded-126">[Data Flow](data-flow/data-flow.md) </span></span>  
 <span data-ttu-id="07ded-127">[Connessioni in Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="07ded-127">[Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="07ded-128">Copia di elementi di progetto</span><span class="sxs-lookup"><span data-stu-id="07ded-128">Copy Project Items</span></span>](../../2014/integration-services/copy-project-items.md)  
  
  
