---
title: Eseguire il debug di uno script impostando punti di interruzione in un'attività e in un componente Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- breakpoints [Integration Services]
- scripts [Integration Services], breakpoints
ms.assetid: 6c03464f-3f7d-4882-b7f8-8e396f8e2944
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 45e7ffc6680c33e3b17b9b39fba0aabd8fa4028c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626155"
---
# <a name="debug-a-script-by-setting-breakpoints-in-a-script-task-and-script-component"></a><span data-ttu-id="f6226-102">Eseguire il debug di uno script impostando punti di interruzione in un'attività e in un componente Script</span><span class="sxs-lookup"><span data-stu-id="f6226-102">Debug a Script by Setting Breakpoints in a Script Task and Script Component</span></span>
  <span data-ttu-id="f6226-103">In questa procedura viene descritto come impostare i punti di interruzione negli script utilizzati nell'attività e nel componente Script.</span><span class="sxs-lookup"><span data-stu-id="f6226-103">This procedure describes how to set breakpoints in the scripts that are used in the Script task and Script component.</span></span>  
  
 <span data-ttu-id="f6226-104">Dopo aver impostato i punti di interruzione nello script, nella finestra di dialogo **Imposta punti di interruzione - \<object name>** vengono elencati i punti di interruzione con quelli predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f6226-104">After you set breakpoints in the script, the **Set Breakpoints - \<object name>** dialog box lists the breakpoints, along with the built-in breakpoints.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f6226-105">In determinate circostanze, i punti di interruzione nell'attività Script e il componente Script vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="f6226-105">Under certain circumstances, breakpoints in the Script task and Script component are ignored.</span></span> <span data-ttu-id="f6226-106">Per ulteriori informazioni, vedere la sezione **debug dell'attività script** in [codifica e debug dell'attività script](../control-flow/script-task.md) e la sezione **debug del componente script** in [codifica e debug del componente script] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="f6226-106">For more information, see the **Debugging the Script Task** section in [Coding and Debugging the Script Task](../control-flow/script-task.md) and the **Debugging the Script Component** section in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md.</span></span>  
  
### <a name="to-set-a-breakpoint-in-script"></a><span data-ttu-id="f6226-107">Per impostare un punto di interruzione in uno script</span><span class="sxs-lookup"><span data-stu-id="f6226-107">To set a breakpoint in script</span></span>  
  
1.  <span data-ttu-id="f6226-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="f6226-108">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="f6226-109">Fare doppio clic sul pacchetto che include lo script in cui si desidera impostare i punti di interruzione.</span><span class="sxs-lookup"><span data-stu-id="f6226-109">Double-click the package that contains the script in which you want to set breakpoints.</span></span>  
  
3.  <span data-ttu-id="f6226-110">Per aprire l'attività Script, fare clic sulla scheda **Flusso di controllo**, quindi fare doppio clic sull'attività.</span><span class="sxs-lookup"><span data-stu-id="f6226-110">To open the Script task, click the **Control Flow** tab, and then double-click the Script task.</span></span>  
  
4.  <span data-ttu-id="f6226-111">Per aprire il componente Script, fare clic sulla scheda **Flusso di dati**, quindi fare doppio clic sul componente.</span><span class="sxs-lookup"><span data-stu-id="f6226-111">To open the Script component, click the **Data Flow** tab, and then double-click the Script component.</span></span>  
  
5.  <span data-ttu-id="f6226-112">Fare clic su **Script**, quindi su **Modifica script**.</span><span class="sxs-lookup"><span data-stu-id="f6226-112">Click **Script** and then click **Edit Script**.</span></span>  
  
6.  <span data-ttu-id="f6226-113">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) individuare la riga di script in cui si vuole impostare un punto di interruzione, fare clic con il pulsante destro del mouse sulla riga, scegliere **Punto di interruzione** e quindi fare clic su **Inserisci punto di interruzione**.</span><span class="sxs-lookup"><span data-stu-id="f6226-113">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA), locate the line of script on which you want to set a breakpoint, right-click that line, point to **Breakpoint**, and then click **Insert Breakpoint**.</span></span>  
  
     <span data-ttu-id="f6226-114">Nella riga di codice verrà visualizzata l'icona del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="f6226-114">The breakpoint icon appears on the line of code.</span></span>  
  
7.  <span data-ttu-id="f6226-115">Scegliere **Esci** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="f6226-115">On the **File** menu, click **Exit**.</span></span>  
  
8.  <span data-ttu-id="f6226-116">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6226-116">Click **OK**.</span></span>  
  
9. <span data-ttu-id="f6226-117">Per salvare il pacchetto, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="f6226-117">To save the package, click **Save Selected Items** on the **File** menu.</span></span>  
  
  
