---
title: Configurare un contenitore ciclo for | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- containers [Integration Services], For Loop
- For Loop containers
ms.assetid: b9cd7ea7-b198-4a35-8b16-6acf09611ca5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9cb33ea5b7f3f59baad3c94f6bc845c281613ec9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624875"
---
# <a name="configure-a-for-loop-container"></a><span data-ttu-id="89915-102">Configurazione di un contenitore Ciclo For</span><span class="sxs-lookup"><span data-stu-id="89915-102">Configure a For Loop Container</span></span>
  <span data-ttu-id="89915-103">Questa procedura descrive come configurare un contenitore Ciclo For tramite la finestra di dialogo **Editor ciclo For** .</span><span class="sxs-lookup"><span data-stu-id="89915-103">This procedure describes how to configure a For Loop container by using the **For Loop Editor** dialog box.</span></span>  
  
### <a name="to-configure-the-for-loop-container"></a><span data-ttu-id="89915-104">Per configurare il contenitore Ciclo For</span><span class="sxs-lookup"><span data-stu-id="89915-104">To configure the For Loop container</span></span>  
  
1.  <span data-ttu-id="89915-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]fare doppio clic sul contenitore Ciclo For per aprire la finestra di dialogo **Editor ciclo For**.</span><span class="sxs-lookup"><span data-stu-id="89915-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], double-click the For Loop container to open the **For Loop Editor**.</span></span>  
  
2.  <span data-ttu-id="89915-106">Facoltativamente, modificare il nome e la descrizione del contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="89915-106">Optionally, modify the name and description of the For Loop container.</span></span>  
  
3.  <span data-ttu-id="89915-107">Facoltativamente, digitare un'espressione di inizializzazione nella casella di testo **InitExpression** .</span><span class="sxs-lookup"><span data-stu-id="89915-107">Optionally, type an initialization expression in the **InitExpression** text box.</span></span>  
  
4.  <span data-ttu-id="89915-108">Digitare un'espressione di valutazione nella casella di testo **EvalExpression** .</span><span class="sxs-lookup"><span data-stu-id="89915-108">Type an evaluation expression in the **EvalExpression** text box.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="89915-109">L'espressione deve restituire un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="89915-109">The expression must evaluate to a Boolean.</span></span> <span data-ttu-id="89915-110">Quando l'espressione restituisce `false`, l'esecuzione del ciclo viene arrestata.</span><span class="sxs-lookup"><span data-stu-id="89915-110">When the expression evaluates to `false`, the loop stops running.</span></span>  
  
5.  <span data-ttu-id="89915-111">Facoltativamente, digitare un'espressione di assegnazione nella casella di testo **AssignExpression** .</span><span class="sxs-lookup"><span data-stu-id="89915-111">Optionally, type an assignment expression in the **AssignExpression** text box.</span></span>  
  
6.  <span data-ttu-id="89915-112">Facoltativamente, fare clic su **Espressioni** e, nella pagina **Espressioni** , creare espressioni di proprietà per le proprietà del contenitore Ciclo For.</span><span class="sxs-lookup"><span data-stu-id="89915-112">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the For Loop container.</span></span> <span data-ttu-id="89915-113">Per altre informazioni, vedere [Aggiunta o modifica di un'espressione di proprietà](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="89915-113">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
7.  <span data-ttu-id="89915-114">Fare clic su **OK** per chiudere la finestra **Editor ciclo For**.</span><span class="sxs-lookup"><span data-stu-id="89915-114">Click **OK** to close the **For Loop Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89915-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89915-115">See Also</span></span>  
 <span data-ttu-id="89915-116">[Contenitore ciclo for](control-flow/for-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="89915-116">[For Loop Container](control-flow/for-loop-container.md) </span></span>  
 <span data-ttu-id="89915-117">[Integration Services &#40;espressioni di&#41; SSIS](expressions/integration-services-ssis-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="89915-117">[Integration Services &#40;SSIS&#41; Expressions](expressions/integration-services-ssis-expressions.md) </span></span>  
 [<span data-ttu-id="89915-118">utilizzo delle espressioni di proprietà nei pacchetti</span><span class="sxs-lookup"><span data-stu-id="89915-118">Use Property Expressions in Packages</span></span>](expressions/use-property-expressions-in-packages.md)  
  
  
