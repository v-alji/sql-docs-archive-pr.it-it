---
title: Punti di interruzione Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Transact-SQL debugger, breakpoints
ms.assetid: c234430f-bd94-4d0d-9e74-2bf11681fa50
author: rothja
ms.author: jroth
ms.openlocfilehash: c9595c9627ac3cc445b1193881c2d5b772e9b71d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636007"
---
# <a name="transact-sql-breakpoints"></a><span data-ttu-id="68ec2-102">Punti di interruzione Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68ec2-102">Transact-SQL Breakpoints</span></span>
  <span data-ttu-id="68ec2-103">I punti di interruzione specificano la sospensione dell'esecuzione del debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] in un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] specifica, per consentire le visualizzazione dello stato degli elementi di codice in tale punto.</span><span class="sxs-lookup"><span data-stu-id="68ec2-103">Breakpoints specify that the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger pause execution on a specific [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, you can then view the state of the code elements at that point.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="68ec2-104">Punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="68ec2-104">Breakpoints</span></span>  
 <span data-ttu-id="68ec2-105">Quando si esegue il debugger [!INCLUDE[tsql](../../includes/tsql-md.md)] , è possibile attivare o attivare un punto di interruzione per istruzioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="68ec2-105">When running the [!INCLUDE[tsql](../../includes/tsql-md.md)] debugger, you can toggle a breakpoint on specific statements.</span></span> <span data-ttu-id="68ec2-106">Quando viene raggiunta un'istruzione con un punto di interruzione, il debugger sospende l'esecuzione per consentire la visualizzazione di informazioni di debug, ad esempio i valori presenti in variabili e parametri.</span><span class="sxs-lookup"><span data-stu-id="68ec2-106">When execution reaches a statement with a breakpoint, the debugger pauses execution so you can view debugging information, such as the values present in variables and parameters.</span></span>  
  
 <span data-ttu-id="68ec2-107">È possibile gestire i punti di interruzione singolarmente nella finestra dell'editor o collettivamente tramite la finestra **Punti di interruzione** .</span><span class="sxs-lookup"><span data-stu-id="68ec2-107">You can manage breakpoints individually in the editor window, or collectively by using the **Breakpoints** window.</span></span> <span data-ttu-id="68ec2-108">È possibile modificare i punti di interruzione per specificare elementi quali condizioni specifiche in presenza delle quali l'esecuzione deve essere sospesa oppure le azioni in caso di esecuzione del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="68ec2-108">You can edit breakpoints to specify items such as specific conditions under which execution should pause, or the actions to be taken if the breakpoint is executed.</span></span>  
  
## <a name="breakpoint-tasks"></a><span data-ttu-id="68ec2-109">Attività correlate ai punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="68ec2-109">Breakpoint Tasks</span></span>  
  
|<span data-ttu-id="68ec2-110">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="68ec2-110">Task Description</span></span>|<span data-ttu-id="68ec2-111">Argomento</span><span class="sxs-lookup"><span data-stu-id="68ec2-111">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="68ec2-112">Viene decritto come specificare l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] in corrispondenza della quale il debugger deve sospendere l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="68ec2-112">Describes how to specify the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement on which you want the debugger to pause.</span></span>|[<span data-ttu-id="68ec2-113">Attivare/disattivare un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="68ec2-113">Toggle a Breakpoint</span></span>](../spatial/point.md)|  
|<span data-ttu-id="68ec2-114">Viene descritto come disattivare temporaneamente un punto di interruzione e riattivarlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="68ec2-114">Describes how to temporarily deactivate a breakpoint, and later reactivate it.</span></span> <span data-ttu-id="68ec2-115">Viene inoltre descritto come eliminare un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="68ec2-115">Also describes how to delete a breakpoint.</span></span>|[<span data-ttu-id="68ec2-116">Abilitare, disabilitare ed eliminare punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="68ec2-116">Enable, Disable, and Delete Breakpoints</span></span>](enable-disable-and-delete-breakpoints.md)|  
|<span data-ttu-id="68ec2-117">Viene descritto come specificare una condizione che definisce se l'interruzione nel punto deve avvenire in base alla valutazione di un'espressione Transact-SQL specificata.</span><span class="sxs-lookup"><span data-stu-id="68ec2-117">Describes how to specify a condition, which defines whether breakpoint breaks based on the evaluation of a specified Transact-SQL expression.</span></span>|[<span data-ttu-id="68ec2-118">Impostare una condizione del punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="68ec2-118">Specify a Breakpoint Condition</span></span>](specify-a-breakpoint-condition.md)|  
|<span data-ttu-id="68ec2-119">Viene descritto come specificare un numero di passaggi che determina l'interruzione solo quando l'istruzione contenente il punto di interruzione è stata eseguita un determinato numero di volte.</span><span class="sxs-lookup"><span data-stu-id="68ec2-119">Describes how to specify a hit count, which causes a breakpoint to break only when the statement containing the breakpoint has been executed a specified number of times.</span></span>|[<span data-ttu-id="68ec2-120">Specificare un numero di passaggi</span><span class="sxs-lookup"><span data-stu-id="68ec2-120">Specify a Hit Count</span></span>](specify-a-hit-count.md)|  
|<span data-ttu-id="68ec2-121">Viene descritto come specificare un filtro che determina l'interruzione in corrispondenza del punto impostato solo per processi o thread specificati.</span><span class="sxs-lookup"><span data-stu-id="68ec2-121">Describes how to specify a filter, which causes a breakpoint to break for only specified processes or threads.</span></span>|[<span data-ttu-id="68ec2-122">Specificare un filtro per un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="68ec2-122">Specify a Breakpoint Filter</span></span>](specify-a-breakpoint-filter.md)|  
|<span data-ttu-id="68ec2-123">Viene descritto come specificare un'azione **Quando raggiunto** , ovvero un'operazione personalizzata eseguita quando viene eseguita l'istruzione del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="68ec2-123">Describes how to specify a **When Hit** action, which is a custom operation that is performed when the breakpoint statement is executed.</span></span> <span data-ttu-id="68ec2-124">Ne è un esempio la visualizzazione di un messaggio.</span><span class="sxs-lookup"><span data-stu-id="68ec2-124">An example would be to print a message.</span></span>|[<span data-ttu-id="68ec2-125">Specificare un'azione del punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="68ec2-125">Specify a Breakpoint Action</span></span>](specify-a-breakpoint-action.md)|  
|<span data-ttu-id="68ec2-126">Viene descritto come modificare la posizione di un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="68ec2-126">Describes how to edit the location of a breakpoint.</span></span>|[<span data-ttu-id="68ec2-127">Modificare la posizione di un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="68ec2-127">Edit a Breakpoint Location</span></span>](edit-a-breakpoint-location.md)|  
  
## <a name="see-also"></a><span data-ttu-id="68ec2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68ec2-128">See Also</span></span>  
 [<span data-ttu-id="68ec2-129">Informazioni del debugger Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="68ec2-129">Transact-SQL Debugger Information</span></span>](transact-sql-debugger-information.md)  
  
  
