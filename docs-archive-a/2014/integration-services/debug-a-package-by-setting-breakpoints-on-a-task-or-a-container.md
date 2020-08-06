---
title: Eseguire il debug di un pacchetto impostando punti di interruzione in un'attività o in un contenitore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], breakpoints
- breakpoints [Integration Services]
- tasks [Integration Services], breakpoints
ms.assetid: e7fa106a-2221-403a-bb74-efc9f12bb450
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 21e334faff95e63e59bbf9c40fdf7e479de949da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625471"
---
# <a name="debug-a-package-by-setting-breakpoints-on-a-task-or-a-container"></a><span data-ttu-id="3c9b8-102">Debug di un pacchetto impostando punti di interruzione in un'attività o in un contenitore</span><span class="sxs-lookup"><span data-stu-id="3c9b8-102">Debug a Package by Setting Breakpoints on a Task or a Container</span></span>
  <span data-ttu-id="3c9b8-103">In questa procedura viene descritto come impostare punti di interruzione in un pacchetto, in un'attività o in un contenitore Ciclo For, Ciclo Foreach o Sequenza.</span><span class="sxs-lookup"><span data-stu-id="3c9b8-103">This procedure describes how to set breakpoints in a package, a task, a For Loop container, a Foreach Loop container, or a Sequence container.</span></span>  
  
### <a name="to-set-breakpoints-in-a-package-a-task-or-a-container"></a><span data-ttu-id="3c9b8-104">Per impostare punti di interruzione in un pacchetto, in un'attività o in un contenitore</span><span class="sxs-lookup"><span data-stu-id="3c9b8-104">To set breakpoints in a package, a task, or a container</span></span>  
  
1.  <span data-ttu-id="3c9b8-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="3c9b8-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="3c9b8-106">Fare doppio clic sul pacchetto in cui si desidera impostare punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="3c9b8-106">Double-click the package in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="3c9b8-107">In Progettazione SSIS eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c9b8-107">In SSIS Designer, do the following:</span></span>  
  
    -   <span data-ttu-id="3c9b8-108">Per impostare punti di interruzione nell'oggetto di pacchetto, nella scheda **Flusso di controllo** posizionare il cursore in un punto qualsiasi dello sfondo dell'area di progettazione, fare clic con il pulsante destro del mouse e quindi scegliere **Modifica punti di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="3c9b8-108">To set breakpoints in the package object, click the **Control Flow** tab, place the cursor anywhere on the background of the design surface, right-click, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="3c9b8-109">Per impostare punti di interruzione nel flusso di controllo di un pacchetto, nella scheda **Flusso di controllo** fare clic con il pulsante destro del mouse su un'attività o su un contenitore Ciclo For, Ciclo Foreach o Sequenza e quindi scegliere **Modifica punti di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="3c9b8-109">To set breakpoints in a package control flow, click the **Control Flow** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
    -   <span data-ttu-id="3c9b8-110">Per impostare punti di interruzione in un gestore evento, nella scheda **Gestore evento** fare clic con il pulsante destro del mouse su un'attività o su un contenitore Ciclo For, Ciclo Foreach o Sequenza e quindi scegliere **Modifica punti di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="3c9b8-110">To set breakpoints in an event handler, click the **Event Handler** tab, right-click a task, a For Loop container, a Foreach Loop container, or a Sequence container, and then click **Edit Breakpoints**.</span></span>  
  
4.  <span data-ttu-id="3c9b8-111">Nella finestra di dialogo **Imposta punti di interruzione\<container name>** selezionare il punto di interruzione da abilitare.</span><span class="sxs-lookup"><span data-stu-id="3c9b8-111">In the **Set Breakpoints \<container name>** dialog box, select the breakpoints to enable.</span></span>  
  
5.  <span data-ttu-id="3c9b8-112">Facoltativamente, modificare il tipo di passaggi e il numero di passaggi per ogni punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="3c9b8-112">Optionally, modify the hit count type and the hit count number for each breakpoint.</span></span>  
  
6.  <span data-ttu-id="3c9b8-113">Per salvare il pacchetto, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="3c9b8-113">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9b8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c9b8-114">See Also</span></span>  
 <span data-ttu-id="3c9b8-115">[Risoluzione dei problemi relativi agli strumenti per lo sviluppo dei pacchetti](troubleshooting/troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="3c9b8-115">[Troubleshooting Tools for Package Development](troubleshooting/troubleshooting-tools-for-package-development.md) </span></span>  
 <span data-ttu-id="3c9b8-116">[Eseguire il debug di uno script impostando punti di interruzione in un'attività script e in un componente script](data-flow/transformations/script-component.md) </span><span class="sxs-lookup"><span data-stu-id="3c9b8-116">[Debug a Script by Setting Breakpoints in a Script Task and Script Component](data-flow/transformations/script-component.md) </span></span>  
 <span data-ttu-id="3c9b8-117">[Codifica e debug dell'attività script](control-flow/script-task.md) </span><span class="sxs-lookup"><span data-stu-id="3c9b8-117">[Coding and Debugging the Script Task](control-flow/script-task.md) </span></span>  
 [<span data-ttu-id="3c9b8-118">Codifica e debug del componente script</span><span class="sxs-lookup"><span data-stu-id="3c9b8-118">Coding and Debugging the Script Component</span></span>](extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md)  
  
  
