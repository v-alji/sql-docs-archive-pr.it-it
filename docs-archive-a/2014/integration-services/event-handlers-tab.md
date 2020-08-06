---
title: Scheda gestori eventi | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.eventhandlerwindow.f1
ms.assetid: 94fc8916-8032-490c-b9d5-ded8b6217e49
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a5f25a9b0d602a3189feab797b7ef9c333decabb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629515"
---
# <a name="event-handlers-tab"></a><span data-ttu-id="5d5e9-102">Scheda Gestori eventi</span><span class="sxs-lookup"><span data-stu-id="5d5e9-102">Event Handlers Tab</span></span>
  <span data-ttu-id="5d5e9-103">Utilizzare la scheda **Gestori eventi** dello strumento Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] per compilare un flusso di controllo in un pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5d5e9-103">Use the **Event Handlers** tab of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to build a control flow in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="5d5e9-104">Un gestore di evento viene eseguito in risposta a un evento generato dal pacchetto oppure da un'attività o da un contenitore incluso nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-104">An event handler runs in response to an event raised by the package or by a task or container in the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5d5e9-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5d5e9-105">Options</span></span>  
 <span data-ttu-id="5d5e9-106">**File eseguibile**</span><span class="sxs-lookup"><span data-stu-id="5d5e9-106">**Executable**</span></span>  
 <span data-ttu-id="5d5e9-107">Consente di selezionare il file eseguibile per il quale si desidera compilare un gestore di evento.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-107">Select the executable for which you want to build an event handler.</span></span> <span data-ttu-id="5d5e9-108">Il file eseguibile può essere il pacchetto oppure un'attività o un contenitore incluso nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-108">The executable can be the package, or a task or containers in the package.</span></span>  
  
 <span data-ttu-id="5d5e9-109">**Gestore dell'evento**</span><span class="sxs-lookup"><span data-stu-id="5d5e9-109">**Event handler**</span></span>  
 <span data-ttu-id="5d5e9-110">Consente di selezionare un gestore di evento.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-110">Select a type of event handler.</span></span> <span data-ttu-id="5d5e9-111">Creare il gestore di evento trascinando gli elementi dalla **casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-111">Create the event handler by dragging items from the **Toolbox**.</span></span>  
  
 <span data-ttu-id="5d5e9-112">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="5d5e9-112">**Delete**</span></span>  
 <span data-ttu-id="5d5e9-113">Dopo aver selezionato un gestore di evento, fare clic su **Elimina** per rimuoverlo dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-113">Select an event handler, and remove it from the package by clicking **Delete**.</span></span>  
  
 <span data-ttu-id="5d5e9-114">**Fare clic qui per creare un \<event handler name> per il file eseguibile \<executable name>**</span><span class="sxs-lookup"><span data-stu-id="5d5e9-114">**Click here to create an \<event handler name> for the executable \<executable name>**</span></span>  
 <span data-ttu-id="5d5e9-115">Fare clic per creare il gestore di evento.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-115">Click to create the event handler.</span></span>  
  
 <span data-ttu-id="5d5e9-116">Creare il flusso di controllo trascinando gli oggetti grafici che rappresentano i contenitori e le attività di [!INCLUDE[ssIS](../includes/ssis-md.md)] dalla **casella degli strumenti** all'area di progettazione della scheda **Gestori eventi** e quindi trascinando il connettore per collegare gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-116">Create the control flow by dragging graphical objects that represent [!INCLUDE[ssIS](../includes/ssis-md.md)] tasks and containers from the **Toolbox** to the design surface of the **Event Handlers** tab, and then connecting the objects by using precedence constraints to define the sequence in which they run.</span></span>  
  
 <span data-ttu-id="5d5e9-117">È inoltre possibile fare clic con il pulsante destro del mouse sull'area di progettazione, quindi scegliere **Aggiungi annotazione**dal menu per aggiungere annotazioni.</span><span class="sxs-lookup"><span data-stu-id="5d5e9-117">Additionally, to add annotations, right-click the design surface, and then on the menu, click **Add Annotation**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d5e9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d5e9-118">See Also</span></span>  
 <span data-ttu-id="5d5e9-119">[Gestori eventi di Integration Services &#40;SSIS&#41;](integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="5d5e9-119">[Integration Services &#40;SSIS&#41; Event Handlers](integration-services-ssis-event-handlers.md) </span></span>  
 <span data-ttu-id="5d5e9-120">[Flusso di controllo](control-flow/control-flow.md) </span><span class="sxs-lookup"><span data-stu-id="5d5e9-120">[Control Flow](control-flow/control-flow.md) </span></span>  
 <span data-ttu-id="5d5e9-121">[Progettazione SSIS](ssis-designer.md) </span><span class="sxs-lookup"><span data-stu-id="5d5e9-121">[SSIS Designer](ssis-designer.md) </span></span>  
 [<span data-ttu-id="5d5e9-122">Gestori eventi di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5d5e9-122">Integration Services &#40;SSIS&#41; Event Handlers</span></span>](integration-services-ssis-event-handlers.md)  
  
  
