---
title: Editor vincoli di precedenza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.precedenceconstraint.f1
helpviewer_keywords:
- Precedence Constraint Editor dialog box
ms.assetid: b10d4330-6e35-4037-b309-ef56efcd60c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b6853d1974f4276361d60e1d73b34c72a366a7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626131"
---
# <a name="precedence-constraint-editor"></a><span data-ttu-id="97df2-102">Editor vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="97df2-102">Precedence Constraint Editor</span></span>
  <span data-ttu-id="97df2-103">Utilizzare la finestra di dialogo **Editor vincoli di precedenza** per configurare i vincoli di precedenza.</span><span class="sxs-lookup"><span data-stu-id="97df2-103">Use the **Precedence Constraint Editor** dialog box to configure precedence constraints.</span></span>  
  
## <a name="options"></a><span data-ttu-id="97df2-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="97df2-104">Options</span></span>  
 <span data-ttu-id="97df2-105">**Operazione di valutazione**</span><span class="sxs-lookup"><span data-stu-id="97df2-105">**Evaluation operation**</span></span>  
 <span data-ttu-id="97df2-106">Consente di specificare l'operazione di valutazione utilizzata dal vincolo di precedenza.</span><span class="sxs-lookup"><span data-stu-id="97df2-106">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="97df2-107">Le operazioni sono: **Vincolo**, **Espressione**, **Espressione e vincolo** e **Espressione o vincolo**.</span><span class="sxs-lookup"><span data-stu-id="97df2-107">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
 <span data-ttu-id="97df2-108">**Valore**</span><span class="sxs-lookup"><span data-stu-id="97df2-108">**Value**</span></span>  
 <span data-ttu-id="97df2-109">Specificare il valore del vincolo: **Esito positivo**, **Esito negativo** o **Completamento**.</span><span class="sxs-lookup"><span data-stu-id="97df2-109">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97df2-110"> La riga del vincolo di precedenza è di colore verde in caso di **Esito positivo**, evidenziata per **Esito negativo**e blu per **Completamento**.</span><span class="sxs-lookup"><span data-stu-id="97df2-110">The precedence constraint line is green for **Success**, highlighted for **Failure**, and blue for **Completion**.</span></span>  
  
 <span data-ttu-id="97df2-111">**Espressione**</span><span class="sxs-lookup"><span data-stu-id="97df2-111">**Expression**</span></span>  
 <span data-ttu-id="97df2-112">Se si usano le operazioni **Espressione**, **Espressione e vincolo**o **Espressione o vincolo**, digitare un'espressione o avviare Generatore di espressioni per creare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="97df2-112">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression or launch the Expression Builder to create the expression.</span></span> <span data-ttu-id="97df2-113">L'espressione deve restituire un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="97df2-113">The expression must evaluate to a Boolean.</span></span>  
  
 <span data-ttu-id="97df2-114">**Test**</span><span class="sxs-lookup"><span data-stu-id="97df2-114">**Test**</span></span>  
 <span data-ttu-id="97df2-115">Consente di convalidare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="97df2-115">Validate the expression.</span></span>  
  
 <span data-ttu-id="97df2-116">**AND logico**</span><span class="sxs-lookup"><span data-stu-id="97df2-116">**Logical AND**</span></span>  
 <span data-ttu-id="97df2-117">Selezionare questa opzione per specificare che devono essere valutati contemporaneamente più vincoli di precedenza nello stesso file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="97df2-117">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="97df2-118">Tutti i vincoli devono restituire `True`.</span><span class="sxs-lookup"><span data-stu-id="97df2-118">All constraints must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97df2-119">Questo tipo di vincolo di precedenza viene visualizzato come riga di colore verde, evidenziata o blu continua.</span><span class="sxs-lookup"><span data-stu-id="97df2-119">This type of precedence constraint appears as a solid green, highlighted or blue line.</span></span>  
  
 <span data-ttu-id="97df2-120">**OR logico**</span><span class="sxs-lookup"><span data-stu-id="97df2-120">**Logical OR**</span></span>  
 <span data-ttu-id="97df2-121">Selezionare questa opzione per specificare che devono essere valutati contemporaneamente più vincoli di precedenza nello stesso file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="97df2-121">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="97df2-122">Almeno un vincolo deve restituire `True`.</span><span class="sxs-lookup"><span data-stu-id="97df2-122">At least one constraint must evaluate to `True`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="97df2-123">Questo tipo di vincolo di precedenza viene visualizzato come riga di colore verde, evidenziata o blu tratteggiata.</span><span class="sxs-lookup"><span data-stu-id="97df2-123">This type of precedence constraint appears as a dotted green, highlighted, or blue line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97df2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97df2-124">See Also</span></span>  
 <span data-ttu-id="97df2-125">[Vincoli di precedenza](control-flow/precedence-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="97df2-125">[Precedence Constraints](control-flow/precedence-constraints.md) </span></span>  
 <span data-ttu-id="97df2-126">[Attività di Integration Services](control-flow/integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="97df2-126">[Integration Services Tasks](control-flow/integration-services-tasks.md) </span></span>  
 <span data-ttu-id="97df2-127">[Contenitori di Integration Services](control-flow/integration-services-containers.md) </span><span class="sxs-lookup"><span data-stu-id="97df2-127">[Integration Services Containers](control-flow/integration-services-containers.md) </span></span>  
 [<span data-ttu-id="97df2-128">Espressioni di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="97df2-128">Integration Services &#40;SSIS&#41; Expressions</span></span>](expressions/integration-services-ssis-expressions.md)  
  
  
