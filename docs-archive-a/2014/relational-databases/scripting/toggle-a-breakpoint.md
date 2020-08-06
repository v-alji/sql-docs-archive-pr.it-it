---
title: Attivare/disattivare un punto di interruzione
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c477ab89-a1cd-4f2c-aa7c-40525041100f
author: rothja
ms.author: jroth
ms.openlocfilehash: 72e26e9b1d04bc2eced6bcb6d93d3c86a016d308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636008"
---
# <a name="toggle-a-breakpoint"></a><span data-ttu-id="49f9d-102">Attivare/disattivare un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="49f9d-102">Toggle a Breakpoint</span></span>
  <span data-ttu-id="49f9d-103">L'azione di definizione di un punto di interruzione in un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] è denominata impostazione/rimozione di un punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="49f9d-103">The act of setting a breakpoint on a [!INCLUDE[tsql](../../includes/tsql-md.md)] statement is called toggling a breakpoint.</span></span>  
  
## <a name="breakpoints"></a><span data-ttu-id="49f9d-104">Punti di interruzione</span><span class="sxs-lookup"><span data-stu-id="49f9d-104">Breakpoints</span></span>  
 <span data-ttu-id="49f9d-105">Una volta impostato, il punto di interruzione è rappresentato da un'icona nella barra grigia a sinistra dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="49f9d-105">Once the breakpoint has been set, it is represented by an icon in the grey bar to the left of the statement.</span></span> <span data-ttu-id="49f9d-106">L'icona è nota come glifo del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="49f9d-106">The icon is called a breakpoint glyph.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="49f9d-107">I punti di interruzione vengono applicati a un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] completa.</span><span class="sxs-lookup"><span data-stu-id="49f9d-107">breakpoints are applied to a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="49f9d-108">Quando un punto di interruzione viene attivato, il debugger evidenzia l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] associata.</span><span class="sxs-lookup"><span data-stu-id="49f9d-108">When a breakpoint is toggled on, the debugger highlights the associated [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
 <span data-ttu-id="49f9d-109">Se sono presenti più istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] su una riga, è possibile impostare/rimuovere un punto di interruzione per ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="49f9d-109">If there are multiple [!INCLUDE[tsql](../../includes/tsql-md.md)] statements on a line, you can toggle a breakpoint for each statement.</span></span> <span data-ttu-id="49f9d-110">Facendo clic nella barra grigia a sinistra della finestra, è possibile impostare/rimuovere un punto di interruzione nella prima istruzione della riga.</span><span class="sxs-lookup"><span data-stu-id="49f9d-110">Clicking in the grey bar on the left of the window toggles a breakpoint on the first statement on the line.</span></span> <span data-ttu-id="49f9d-111">Per impostare/rimuovere un punto di interruzione in un'istruzione successiva, è possibile evidenziare qualsiasi parte dell'istruzione o spostare il cursore all'interno dell'istruzione e quindi premere F9 o scegliere **Imposta/Rimuovi punto di interruzione** dal menu **Debug** .</span><span class="sxs-lookup"><span data-stu-id="49f9d-111">You can toggle a breakpoint in a subsequent statement by highlighting any part of the statement, or moving the cursor into the statement, and then either pressing F9 or clicking **Toggle Breakpoint** on the **Debug** menu.</span></span> <span data-ttu-id="49f9d-112">Se sono presenti più punti di interruzione su una riga, nella barra grigia a sinistra sarà presente il glifo di un solo punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="49f9d-112">If you have multiple breakpoints on a line, there is only one breakpoint glyph in the grey bar on the left.</span></span>  
  
 <span data-ttu-id="49f9d-113">Dopo aver attivato o disattivato un punto di interruzione, è possibile eseguirvi diverse operazioni, ad esempio modificarne le proprietà oppure disabilitarlo temporaneamente.</span><span class="sxs-lookup"><span data-stu-id="49f9d-113">After a breakpoint has been toggled, you can perform various actions on the breakpoint, such as editing its properties or temporarily disabling it.</span></span> <span data-ttu-id="49f9d-114">Per altre informazioni, vedere [Punti di interruzione Transact-SQL](transact-sql-breakpoints.md).</span><span class="sxs-lookup"><span data-stu-id="49f9d-114">For more information, see [Transact-SQL Breakpoints](transact-sql-breakpoints.md).</span></span>  
  
## <a name="toggle-a-breakpoint"></a><span data-ttu-id="49f9d-115">Attivare/disattivare un punto di interruzione</span><span class="sxs-lookup"><span data-stu-id="49f9d-115">Toggle a Breakpoint</span></span>  
 <span data-ttu-id="49f9d-116">**Per attivare o disattivare un punto di interruzione in un'istruzione Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="49f9d-116">**To toggle a breakpoint on a Transact-SQL statement**</span></span>  
  
1.  <span data-ttu-id="49f9d-117">Fare clic sulla barra grigia a sinistra dell'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49f9d-117">Click the gray bar to the left side of the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
2.  <span data-ttu-id="49f9d-118">In alternativa, evidenziare qualsiasi parte dell'istruzione o spostare il cursore all'interno dell'istruzione, quindi effettuare una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="49f9d-118">Alternatively, either highlight any part of the statement or move the cursor to the statement, and then perform either action:</span></span>  
  
    -   <span data-ttu-id="49f9d-119">Premere F9.</span><span class="sxs-lookup"><span data-stu-id="49f9d-119">Press F9.</span></span>  
  
    -   <span data-ttu-id="49f9d-120">Scegliere **Imposta/Rimuovi punto di interruzione** dal menu **Debug**.</span><span class="sxs-lookup"><span data-stu-id="49f9d-120">On the **Debug** menu, click **Toggle Breakpoint**.</span></span>  
  
  
