---
title: Durate delle transazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- lifetimes [SQL Server]
- Transact-SQL vs. managed code
ms.assetid: cb076fda-6488-4959-a6a4-7adaccf3f25c
author: rothja
ms.author: jroth
ms.openlocfilehash: 8c00050ee323cade7493d44c4c296ba4ce6811e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725975"
---
# <a name="transaction-lifetimes"></a><span data-ttu-id="ec5c9-102">Durata delle transazioni</span><span class="sxs-lookup"><span data-stu-id="ec5c9-102">Transaction Lifetimes</span></span>
  <span data-ttu-id="ec5c9-103">Vi è un'importante differenza tra le transazioni avviate nelle stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] e quelle avviate in codice gestito: il codice CLR (Common Language Runtime) non può sbilanciare lo stato della transazione all'immissione o all'uscita di una chiamata CLR.</span><span class="sxs-lookup"><span data-stu-id="ec5c9-103">There is an important difference between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and those started in managed code: common language runtime (CLR) code cannot unbalance the transaction state on entry or exit of a CLR invocation.</span></span> <span data-ttu-id="ec5c9-104">Tenere presenti le implicazioni seguenti correlate a questa differenza:</span><span class="sxs-lookup"><span data-stu-id="ec5c9-104">Be aware of the following implications of this difference:</span></span>  
  
-   <span data-ttu-id="ec5c9-105">È necessario eseguire il commit o il rollback di una transazione avviata all'interno di un frame CLR. In caso contrario, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] genera un errore quando si esce dal frame.</span><span class="sxs-lookup"><span data-stu-id="ec5c9-105">A transaction started inside a CLR frame must be committed or rolled back, or else [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] generates an error when the frame is exited.</span></span>  
  
-   <span data-ttu-id="ec5c9-106">Non è possibile eseguire il commit o il rollback di una transazione esterna all'interno del codice CLR.</span><span class="sxs-lookup"><span data-stu-id="ec5c9-106">An outer transaction cannot be committed or rolled back inside the CLR code.</span></span>  
  
-   <span data-ttu-id="ec5c9-107">Un tentativo di esecuzione del commit di una transazione non avviato nella stessa procedura provoca un errore di runtime.</span><span class="sxs-lookup"><span data-stu-id="ec5c9-107">An attempt to commit a transaction not started in the same procedure causes a run-time error.</span></span>  
  
-   <span data-ttu-id="ec5c9-108">Il tentativo di eseguire il rollback di una transazione non avviata nella stessa procedura comporta l'interruzione della risposta da parte della transazione, evitando che si verifichino altre operazioni di effetto collaterale.</span><span class="sxs-lookup"><span data-stu-id="ec5c9-108">An attempt to roll back a transaction not started in the same procedure causes the transaction to stop responding (preventing any other side-effecting operation from happening).</span></span> <span data-ttu-id="ec5c9-109">La transazione viene interrotta fino a quando il codice CLR non abbandona l'ambito.</span><span class="sxs-lookup"><span data-stu-id="ec5c9-109">The transaction discontinues until the CLR code goes out of scope.</span></span> <span data-ttu-id="ec5c9-110">Si noti che questo comportamento può risultare utile quando si rileva un errore all'interno della procedura e si desidera verificare che venga terminata l'intera transazione.</span><span class="sxs-lookup"><span data-stu-id="ec5c9-110">Note that this can be useful when you detect an error inside your procedure and want to make sure the whole transaction terminates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5c9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec5c9-111">See Also</span></span>  
 [<span data-ttu-id="ec5c9-112">Integrazione con CLR e transazioni</span><span class="sxs-lookup"><span data-stu-id="ec5c9-112">CLR Integration and Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
  
  
