---
title: Connessione di attività e contenitori tramite un vincolo di precedenza predefinito | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- tasks [Integration Services], precedence constraints
- precedence constraints [Integration Services], connecting tasks
- default precedence constraints
- containers [Integration Services], precedence constraints
ms.assetid: 8f31f15f-98ff-4c35-b41f-8b8cfd148d75
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 00207172babdb41b1030e77e71a2c8bc3b99799d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722971"
---
# <a name="connect-tasks-and-containers-by-using-a-default-precedence-constraint"></a><span data-ttu-id="2228b-102">Connessione di attività e contenitori tramite un vincolo di precedenza predefinito</span><span class="sxs-lookup"><span data-stu-id="2228b-102">Connect Tasks and Containers by Using a Default Precedence Constraint</span></span>
  <span data-ttu-id="2228b-103">Un vincolo di precedenza connette due eseguibili,</span><span class="sxs-lookup"><span data-stu-id="2228b-103">Precedence constraints connect two executables.</span></span> <span data-ttu-id="2228b-104">che possono essere costituiti da qualsiasi attività oppure da un contenitore Ciclo For, Ciclo Foreach o Sequenza.</span><span class="sxs-lookup"><span data-stu-id="2228b-104">An executable can be any task or a For Loop, Foreach Loop, or Sequence container.</span></span> <span data-ttu-id="2228b-105">Questa procedura descrive l'impostazione del comportamento predefinito dei vincoli di precedenza e la connessione di eseguibili tramite i vincoli di precedenza predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2228b-105">This procedure describes how to set the default behavior for precedence constraints, and how to connect executables using the default precedence constraints.</span></span>  
  
## <a name="creating-default-precedence-constraints"></a><span data-ttu-id="2228b-106">Creazione dei vincoli di precedenza predefiniti</span><span class="sxs-lookup"><span data-stu-id="2228b-106">Creating Default Precedence Constraints</span></span>  
 <span data-ttu-id="2228b-107">Al primo utilizzo di Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] il valore predefinito di un vincolo di precedenza è `Success`.</span><span class="sxs-lookup"><span data-stu-id="2228b-107">When you first use [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, the default value of a precedence constraint is `Success`.</span></span> <span data-ttu-id="2228b-108">Eseguire la procedura seguente per configurare Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] per l'utilizzo di un valore predefinito diverso per i vincoli di precedenza.</span><span class="sxs-lookup"><span data-stu-id="2228b-108">Follow these steps to configure [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer to use a different default value for precedence constraints.</span></span>  
  
#### <a name="to-set-the-default-value-for-precedence-constraints"></a><span data-ttu-id="2228b-109">Per impostare il valore predefinito per i vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="2228b-109">To set the default value for precedence constraints</span></span>  
  
1.  <span data-ttu-id="2228b-110">Aprire [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2228b-110">Open [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="2228b-111">Scegliere **Opzioni** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="2228b-111">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="2228b-112">Nella finestra di dialogo **Opzioni** espandere **Finestre di progettazione Business Intelligence** e quindi espandere **Finestre di progettazione Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="2228b-112">In the **Options** dialog box, expand **Business Intelligence Designers,** and then expand **Integration Services Designers**.</span></span>  
  
4.  <span data-ttu-id="2228b-113">Fare clic su **Connessione automatica flusso di controllo** e selezionare **Per impostazione predefinita connetti la nuova forma alla forma selezionata**.</span><span class="sxs-lookup"><span data-stu-id="2228b-113">Click **Control Flow Auto Connect** and select **Connect a new shape to the selected shape by default**.</span></span>  
  
5.  <span data-ttu-id="2228b-114">Nell'elenco a discesa selezionare **Usa vincolo Esito negativo per la nuova forma** oppure **Usa vincolo Completamento per la nuova forma**.</span><span class="sxs-lookup"><span data-stu-id="2228b-114">In the drop-down list, choose either **Use a Failure constraint for the new shape** or **Use a Completion constraint for the new shape**.</span></span>  
  
6.  <span data-ttu-id="2228b-115">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2228b-115">Click **OK**.</span></span>  
  
#### <a name="to-create-a-default-precedence-constraint"></a><span data-ttu-id="2228b-116">Per creare un vincolo di precedenza predefinito</span><span class="sxs-lookup"><span data-stu-id="2228b-116">To create a default precedence constraint</span></span>  
  
1.  <span data-ttu-id="2228b-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="2228b-117">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="2228b-118">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="2228b-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="2228b-119">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="2228b-119">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="2228b-120">Nell'area di progettazione della scheda **Flusso di controllo** fare clic sull'attività o sul contenitore e trascinarne il connettore fino all'eseguibile a cui si desidera applicare il vincolo di precedenza.</span><span class="sxs-lookup"><span data-stu-id="2228b-120">On the design surface of the **Control Flow** tab, click the task or container and drag its connector to the executable to which you want the precedence constraint to apply.</span></span>  
  
5.  <span data-ttu-id="2228b-121">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="2228b-121">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2228b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2228b-122">See Also</span></span>  
 <span data-ttu-id="2228b-123">[Vincoli di precedenza](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="2228b-123">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="2228b-124">[Impostare il valore di un vincolo di precedenza tramite il menu di scelta rapida](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="2228b-124">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="2228b-125">[Impostare le proprietà di un vincolo di precedenza](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="2228b-125">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="2228b-126">Uso di un'espressione in un vincolo di precedenza</span><span class="sxs-lookup"><span data-stu-id="2228b-126">Use an Expression in a Precedence Constraint</span></span>](../../2014/integration-services/use-an-expression-in-a-precedence-constraint.md)  
  
  
