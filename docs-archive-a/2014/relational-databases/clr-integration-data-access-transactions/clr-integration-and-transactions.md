---
title: Integrazione e transazioni CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- managed code [SQL Server], transactions
- common language runtime [SQL Server], transactions
- System.Transactions namespace
- transactions [CLR integration]
ms.assetid: 381d206e-06e2-48d0-8206-295fcf06ac98
author: rothja
ms.author: jroth
ms.openlocfilehash: de72a2113aeb568decbdc9b5ee0174160cc0d3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725980"
---
# <a name="clr-integration-and-transactions"></a><span data-ttu-id="04da5-102">Integrazione con CLR e transazioni</span><span class="sxs-lookup"><span data-stu-id="04da5-102">CLR Integration and Transactions</span></span>
  <span data-ttu-id="04da5-103">Tramite lo spazio dei nomi `System.Transactions` vengono forniti un framework di transazioni pienamente integrato con ADO.NET e l'integrazione con CRL di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04da5-103">The `System.Transactions` namespace provides a transaction framework that is fully integrated with ADO.NET and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] common language runtime (CLR) integration.</span></span> <span data-ttu-id="04da5-104">`System.Transactions` e ADO.NET funzionano insieme per estendere e semplificare l'utilizzo di transazioni locali e distribuite nelle applicazioni gestite.</span><span class="sxs-lookup"><span data-stu-id="04da5-104">`System.Transactions` and ADO.NET work together to extend and simplify the use of local and distributed transactions in managed applications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04da5-105">Una procedura CLR definita dall'utente non può stabilire una connessione allo stesso server nel quale viene eseguita, ovvero una connessione loopback, ed essere integrata nella stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="04da5-105">A CLR user-defined procedure (UDP) cannot establish a connection to the same server it is running on (a loopback connection) and enlist in the same transaction.</span></span> <span data-ttu-id="04da5-106">Un eventuale tentativo di connessione verrà bloccato e il controllo non verrà restituito alla procedura definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="04da5-106">If this is attempted, the connection attempt will be blocked and control will not be passed back to the UDP.</span></span> <span data-ttu-id="04da5-107">Verrà pertanto generato un errore di timeout (messaggio 1206) nella procedura definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="04da5-107">This will result in a timeout error (Msg 1206) on the UDP.</span></span>  
  
 <span data-ttu-id="04da5-108">Per ulteriori informazioni sulle transazioni e su .NET Framework, vedere gli argomenti relativi all'esecuzione e all'utilizzo di transazioni in .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="04da5-108">For more information about transactions and the .NET Framework, see "Performing Transactions" and "Leveraging Transactions" in the .NET Framework SDK.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04da5-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="04da5-109">In This Section</span></span>  
 [<span data-ttu-id="04da5-110">Promozione delle transazioni</span><span class="sxs-lookup"><span data-stu-id="04da5-110">Transaction Promotion</span></span>](transaction-promotion.md)  
 <span data-ttu-id="04da5-111">Viene illustrata la possibilità di promuovere le transazioni e viene spiegato come utilizzare tale caratteristica.</span><span class="sxs-lookup"><span data-stu-id="04da5-111">Describes the ability to promote transactions, and how to use this feature.</span></span>  
  
 [<span data-ttu-id="04da5-112">Accesso alla transazione corrente</span><span class="sxs-lookup"><span data-stu-id="04da5-112">Accessing the Current Transaction</span></span>](accessing-the-current-transaction.md)  
 <span data-ttu-id="04da5-113">Viene illustrato come accedere a una transazione attualmente in esecuzione in-process in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04da5-113">Describes how to access a transaction currently running in-process on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="04da5-114">Utilizzo di System.Transactions</span><span class="sxs-lookup"><span data-stu-id="04da5-114">Using System.Transactions</span></span>](../native-client-ole-db-transactions/transactions.md)  
 <span data-ttu-id="04da5-115">Viene illustrato come utilizzare l'API `System.Transactions` nell'applicazione gestita.</span><span class="sxs-lookup"><span data-stu-id="04da5-115">Describes how to use the `System.Transactions` application programming interface (API) in your managed application.</span></span>  
  
 [<span data-ttu-id="04da5-116">Durata delle transazioni</span><span class="sxs-lookup"><span data-stu-id="04da5-116">Transaction Lifetimes</span></span>](transaction-lifetimes.md)  
 <span data-ttu-id="04da5-117">Viene illustrata la differenza in termini di durata tra le transazioni avviate in stored procedure [!INCLUDE[tsql](../../includes/tsql-md.md)] e quelle avviate in applicazioni CLR.</span><span class="sxs-lookup"><span data-stu-id="04da5-117">Describes the difference in lifetime between transactions started in [!INCLUDE[tsql](../../includes/tsql-md.md)] stored procedures and transactions started in CLR applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04da5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04da5-118">See Also</span></span>  
 [<span data-ttu-id="04da5-119">Accesso ai dati da oggetti di database CLR</span><span class="sxs-lookup"><span data-stu-id="04da5-119">Data Access from CLR Database Objects</span></span>](../clr-integration/data-access/data-access-from-clr-database-objects.md)  
  
  
