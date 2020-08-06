---
title: Debug degli script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Script task [Integration Services], debugging
- debugging [Integration Services], scripts
- scripts [Integration Services], debugging
ms.assetid: fddf57d8-8607-4f88-85a0-1b683087b491
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a7926f806f20f76c7aaac0c22b970addc5e93a78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721567"
---
# <a name="debugging-script"></a><span data-ttu-id="d73a6-102">Debug degli script</span><span class="sxs-lookup"><span data-stu-id="d73a6-102">Debugging Script</span></span>
  <span data-ttu-id="d73a6-103">Gli script usati nell'attività Script e nel componente script vengono scritti in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="d73a6-103">You write the scripts that the Script task and Script component use, in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
 <span data-ttu-id="d73a6-104">VSTA consente di impostare punti di interruzione negli script.</span><span class="sxs-lookup"><span data-stu-id="d73a6-104">You set and script breakpoints in VSTA.</span></span> <span data-ttu-id="d73a6-105">I punti di interruzione possono essere gestiti in VSTA o tramite la finestra di dialogo **Imposta punti di interruzione** disponibile in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d73a6-105">You can manage breakpoints in VSTA, but you can also manage the breakpoints using the **Set Breakpoints** dialog box that [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer provides.</span></span> <span data-ttu-id="d73a6-106">Per altre informazioni, vedere [Debug del flusso di controllo](debugging-control-flow.md).</span><span class="sxs-lookup"><span data-stu-id="d73a6-106">For more information, see [Debugging Control Flow](debugging-control-flow.md).</span></span>  
  
 <span data-ttu-id="d73a6-107">Nella finestra di dialogo **Imposta punti di interruzione** sono inclusi i punti di interruzione degli script.</span><span class="sxs-lookup"><span data-stu-id="d73a6-107">The **Set Breakpoints** dialog box includes the script breakpoints.</span></span> <span data-ttu-id="d73a6-108">Tali punti di interruzione vengono visualizzati nella parte inferiore dell'elenco dei punti di interruzione, insieme al numero di riga e al nome della funzione in cui sono stati impostati.</span><span class="sxs-lookup"><span data-stu-id="d73a6-108">These breakpoints appear at the bottom of the breakpoint list, and display the line number and the name of the function in which the breakpoint appears.</span></span> <span data-ttu-id="d73a6-109">È possibile eliminare un punto di interruzione di uno script dalla finestra di dialogo **Imposta punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="d73a6-109">You can delete a script breakpoint from the **Set Breakpoints** dialog box.</span></span>  
  
 <span data-ttu-id="d73a6-110">In fase di esecuzione i punti di interruzione impostati per le righe di codice nello script vengono integrati con quelli impostati per il pacchetto o le attività e i contenitori inclusi nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d73a6-110">At run time, the breakpoints set on lines of code in script are integrated with the breakpoints set on the package or the tasks and containers in the package.</span></span> <span data-ttu-id="d73a6-111">È possibile eseguire il debugger da un punto di interruzione in uno script a un punto di interruzione impostato per un pacchetto, un'attività o un contenitore e viceversa.</span><span class="sxs-lookup"><span data-stu-id="d73a6-111">The debugger can run from a breakpoint in the script to a breakpoint set on the package, task, or container, and vice versa.</span></span> <span data-ttu-id="d73a6-112">Si considerino ad esempio un pacchetto in cui sono impostati punti di interruzione per le condizioni di interruzione che si verificano quando il pacchetto riceve gli eventi **OnPreExecute** e **OnPostExecute** e un'attività Script con punti di interruzione impostati per le righe dello script incluso.</span><span class="sxs-lookup"><span data-stu-id="d73a6-112">For example, a package might have breakpoints set on the break conditions that occur when the package receives the **OnPreExecute** and **OnPostExecute** events, and also have a Script task that has breakpoints on lines of its script.</span></span> <span data-ttu-id="d73a6-113">In questo scenario tramite il pacchetto è possibile sospendere l'esecuzione in corrispondenza della condizione di interruzione associata all'evento **OnPreExecute** , continuare l'esecuzione fino ai punti di interruzione impostati nello script e infine continuare l'esecuzione fino alla condizione di interruzione associata all'evento **OnPostExecute** .</span><span class="sxs-lookup"><span data-stu-id="d73a6-113">In this scenario, the package can suspend execution on the break condition associated with the **OnPreExecute** event, run to the breakpoints in the script, and finally run to the break condition associated with the **OnPostExecute** event.</span></span>  
  
 <span data-ttu-id="d73a6-114">Per altre informazioni sul debug dell'attività e sul componente Script, vedere [Scrittura di codice e debug dell'attività Script](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) e [Codifica e debug del componente Script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="d73a6-114">For more information about debugging the Script task and Script component, see [Coding and Debugging the Script Task](../extending-packages-scripting/task/coding-and-debugging-the-script-task.md) and [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>  
  
### <a name="to-set-a-breakpoint-in-visual-studio-for-applications"></a><span data-ttu-id="d73a6-115">Per impostare un punto di interruzione in Visual Studio for Applications</span><span class="sxs-lookup"><span data-stu-id="d73a6-115">To set a breakpoint in Visual Studio for Applications</span></span>  
  
-   [<span data-ttu-id="d73a6-116">Eseguire il debug di uno script impostando punti di interruzione in un'attività e in un componente Script</span><span class="sxs-lookup"><span data-stu-id="d73a6-116">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>](../extending-packages-scripting/debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="d73a6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d73a6-117">See Also</span></span>  
 [<span data-ttu-id="d73a6-118">Strumenti per la risoluzione dei problemi di sviluppo di pacchetti</span><span class="sxs-lookup"><span data-stu-id="d73a6-118">Troubleshooting Tools for Package Development</span></span>](troubleshooting-tools-for-package-development.md)  
  
  
