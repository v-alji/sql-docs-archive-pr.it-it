---
title: Usare un'espressione in un vincolo di precedenza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- precedence constraints [Integration Services], adding expressions
- expressions [Integration Services], adding
ms.assetid: 601038bb-3b17-42ac-b09d-5b3a82fb6564
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a997efa448a8381cc8251cd4cbf69dc59f8968e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716412"
---
# <a name="use-an-expression-in-a-precedence-constraint"></a><span data-ttu-id="98826-102">Utilizzo di un'espressione in un vincolo di precedenza</span><span class="sxs-lookup"><span data-stu-id="98826-102">Use an Expression in a Precedence Constraint</span></span>
  <span data-ttu-id="98826-103">Questa procedura descrive come aggiungere un'espressione a un vincolo di precedenza tramite la finestra di dialogo **Editor vincoli di precedenza** .</span><span class="sxs-lookup"><span data-stu-id="98826-103">This procedure describes how to add an expression to a precedence constraint by using the **Precedence Constraint Editor** dialog box.</span></span> <span data-ttu-id="98826-104">È possibile aggiungere un'espressione a un vincolo di precedenza solo se il pacchetto include almeno due eseguibili, costituiti da attività o contenitori, connessi da un vincolo di precedenza.</span><span class="sxs-lookup"><span data-stu-id="98826-104">Before you can add an expression to a precedence constraint, the package must include at least two executables, either tasks or containers, and they must be connected by a precedence constraint.</span></span>  
  
### <a name="to-add-an-expression-to-a-precedence-constraint"></a><span data-ttu-id="98826-105">Per aggiungere un'espressione a un vincolo di precedenza</span><span class="sxs-lookup"><span data-stu-id="98826-105">To add an expression to a precedence constraint</span></span>  
  
1.  <span data-ttu-id="98826-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="98826-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="98826-107">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="98826-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="98826-108">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="98826-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="98826-109">Nell'area di progettazione della scheda **Flusso di controllo** fare doppio clic sul vincolo di precedenza.</span><span class="sxs-lookup"><span data-stu-id="98826-109">On the design surface of the **Control Flow** tab, double-click the precedence constraint.</span></span> <span data-ttu-id="98826-110">Verrà aperta la finestra di dialogo **Editor vincoli di precedenza** .</span><span class="sxs-lookup"><span data-stu-id="98826-110">The **Precedence Constraint Editor** opens.</span></span>  
  
5.  <span data-ttu-id="98826-111">Selezionare **Espressione**, **Espressione e vincolo**o **Espressione o vincolo** nell'elenco **Operazione valutazione** .</span><span class="sxs-lookup"><span data-stu-id="98826-111">Select **Expression**, **Expression and Constraint**, or **Expression or Constraint** in the **Evaluation operation** list.</span></span>  
  
6.  <span data-ttu-id="98826-112">Digitare un'espressione nella casella di testo **Espressione** o avviare Generatore di espressioni per creare un'espressione.</span><span class="sxs-lookup"><span data-stu-id="98826-112">Type an expression in the **Expression** text box or launch the Expression Builder to create an expression.</span></span>  
  
7.  <span data-ttu-id="98826-113">Per convalidare la sintassi dell'espressione, fare clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="98826-113">To validate the expression syntax, click **Test**.</span></span>  
  
8.  <span data-ttu-id="98826-114">Per salvare il pacchetto aggiornato, scegliere **Salva elementi selezionati** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="98826-114">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98826-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98826-115">See Also</span></span>  
 <span data-ttu-id="98826-116">[Vincoli di precedenza](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="98826-116">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="98826-117">[Connessione di attività e contenitori tramite un vincolo di precedenza predefinito](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="98826-117">[Connect Tasks and Containers by Using a Default Precedence Constraint](../../2014/integration-services/connect-tasks-and-containers-by-using-a-default-precedence-constraint.md) </span></span>  
 <span data-ttu-id="98826-118">[Impostare il valore di un vincolo di precedenza tramite il menu di scelta rapida](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span><span class="sxs-lookup"><span data-stu-id="98826-118">[Set the Value of a Precedence Constraint by Using the Shortcut Menu](../../2014/integration-services/set-the-value-of-a-precedence-constraint-by-using-the-shortcut-menu.md) </span></span>  
 <span data-ttu-id="98826-119">[Impostare le proprietà di un vincolo di precedenza](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="98826-119">[Set the Properties of a Precedence Constraint](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md) </span></span>  
 [<span data-ttu-id="98826-120">Espressioni di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="98826-120">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
