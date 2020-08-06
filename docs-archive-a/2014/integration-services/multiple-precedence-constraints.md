---
title: Più vincoli di precedenza | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- multiple precedence constraints
- precedence executables [Integration Services]
- precedence constraints [Integration Services], multiple
- constrained executables [Integration Services]
ms.assetid: 71c53ead-3d19-4bc1-aafd-e5b32595b420
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16fefbbf886818989131710876564fc9e147a56a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628802"
---
# <a name="multiple-precedence-constraints"></a><span data-ttu-id="572a5-102">Più vincoli di precedenza</span><span class="sxs-lookup"><span data-stu-id="572a5-102">Multiple Precedence Constraints</span></span>
  <span data-ttu-id="572a5-103">Un vincolo di precedenza consente di connettere due eseguibili, ad esempio due attività, due contenitori o un'attività e un contenitore.</span><span class="sxs-lookup"><span data-stu-id="572a5-103">A precedence constraint connects two executables: two tasks, two containers, or one of each.</span></span> <span data-ttu-id="572a5-104">Gli elementi connessi sono noti come eseguibile con precedenza ed eseguibile soggetto al vincolo.</span><span class="sxs-lookup"><span data-stu-id="572a5-104">They are known as the precedence executable and the constrained executable.</span></span> <span data-ttu-id="572a5-105">A un eseguibile soggetto a vincolo possono essere applicati più vincoli di precedenza.</span><span class="sxs-lookup"><span data-stu-id="572a5-105">A constrained executable can have multiple precedence constraints.</span></span> <span data-ttu-id="572a5-106">Per altre informazioni, vedere [Vincoli di precedenza](control-flow/precedence-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="572a5-106">For more information, see [Precedence Constraints](control-flow/precedence-constraints.md).</span></span>  
  
 <span data-ttu-id="572a5-107">Raggruppando più vincoli è possibile definire scenari complessi, che consentono di implementare flussi di controllo complessi nei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="572a5-107">Assembling complex constraint scenarios by grouping constraints enables you to implement complex control flow in packages.</span></span> <span data-ttu-id="572a5-108">Nella figura seguente, ad esempio, l'attività D è collegata all'attività A da un vincolo `Success`, l'attività D è collegata all'attività B da un vincolo `Failure` e l'attività D è collegata all'attività C da un vincolo `Success`.</span><span class="sxs-lookup"><span data-stu-id="572a5-108">For example, in the following illustration, Task D is linked to Task A by a `Success` constraint, Task D is linked to Task B by a `Failure` constraint, and Task D is linked to Task C by a `Success` constraint.</span></span> <span data-ttu-id="572a5-109">I vincoli di precedenza tra le attività D e A, tra le attività D e B e tra le attività D e C sono legati da una relazione logica *e* .</span><span class="sxs-lookup"><span data-stu-id="572a5-109">The precedence constraints between Task D and Task A, between Task D and Task B, and between Task D and Task C participate in a logical *and* relationship.</span></span> <span data-ttu-id="572a5-110">L'attività D viene quindi eseguita solo se l'attività A viene completata, l'attività B non viene eseguita e l'attività C deve essere eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="572a5-110">Therefore, for Task D to run, Task A must run successfully, Task B must fail, and Task C must run successfully.</span></span>  
  
 <span data-ttu-id="572a5-111">![Attività collegate in base ai vincoli di precedenza](media/precedenceconstraints.gif "Attività collegate in base ai vincoli di precedenza")</span><span class="sxs-lookup"><span data-stu-id="572a5-111">![Tasks linked by precedence constraints](media/precedenceconstraints.gif "Tasks linked by precedence constraints")</span></span>  
  
## <a name="logicaland-property"></a><span data-ttu-id="572a5-112">Proprietà LogicalAnd</span><span class="sxs-lookup"><span data-stu-id="572a5-112">LogicalAnd Property</span></span>  
 <span data-ttu-id="572a5-113">Se a un'attività o contenitore sono applicati più vincoli, la proprietà `LogicalAnd` specificherà se il corrispondente vincolo di precedenza viene valutato singolarmente o insieme ad altri vincoli.</span><span class="sxs-lookup"><span data-stu-id="572a5-113">If a task or a container has multiple constraints, the `LogicalAnd` property specifies whether a precedence constraint is evaluated singly or in concert with other constraints.</span></span>  
  
 <span data-ttu-id="572a5-114">È possibile impostare la `LogicalAnd` proprietà utilizzando **Editor vincoli di precedenza** in [!INCLUDE[ssIS](../includes/ssis-md.md)] progettazione o nella finestra proprietà [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] fornita da.</span><span class="sxs-lookup"><span data-stu-id="572a5-114">You can set the `LogicalAnd` property using the **Precedence Constraint Editor** in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, or in the Properties window that [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="572a5-115">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="572a5-115">Related Tasks</span></span>  
 [<span data-ttu-id="572a5-116">Impostazione delle proprietà di un vincolo di precedenza</span><span class="sxs-lookup"><span data-stu-id="572a5-116">Set the Properties of a Precedence Constraint</span></span>](../../2014/integration-services/set-the-properties-of-a-precedence-constraint.md)  
  
  
