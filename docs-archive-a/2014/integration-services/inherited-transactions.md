---
title: Transazioni ereditate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], inherited
- child packages
- inherited transactions [Integration Services]
ms.assetid: 90db5564-d41e-4cfe-8c9e-4e68d41eff1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ecb480420fe9f2492c29fad37ee3cc6e6501e3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628898"
---
# <a name="inherited-transactions"></a><span data-ttu-id="76877-102">Transazioni ereditate</span><span class="sxs-lookup"><span data-stu-id="76877-102">Inherited Transactions</span></span>
  <span data-ttu-id="76877-103">Un pacchetto può eseguire un altro pacchetto tramite l'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="76877-103">A package can run another package by using the Execute Package task.</span></span> <span data-ttu-id="76877-104">Il pacchetto figlio, ovvero il pacchetto eseguito dall'attività Esegui pacchetto, può creare la propria transazione del pacchetto o ereditare quella del padre.</span><span class="sxs-lookup"><span data-stu-id="76877-104">The child package, which is the package run by the Execute Package task, may create its own package transaction, or it may inherit the parent package transaction.</span></span>  
  
 <span data-ttu-id="76877-105">Un pacchetto figlio eredita la transazione del pacchetto padre se sono soddisfatte le due condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="76877-105">A child package inherits the parent package transaction if both of the following are true:</span></span>  
  
-   <span data-ttu-id="76877-106">Il pacchetto viene richiamato da un'attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="76877-106">The package is invoked by an Execute Package task.</span></span>  
  
-   <span data-ttu-id="76877-107">Anche l'attività Esegui pacchetto che richiama il pacchetto partecipa alla transazione del pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="76877-107">The Execute Package task that invoked the package also joined the parent package transaction.</span></span>  
  
 <span data-ttu-id="76877-108">I contenitori e le attività del pacchetto figlio possono partecipare alla transazione del pacchetto padre solo se il pacchetto figlio partecipa alla transazione.</span><span class="sxs-lookup"><span data-stu-id="76877-108">Containers and tasks in the child package cannot join the parent package transaction unless the child package itself joins the transaction.</span></span>  
  
## <a name="illustration-of-package-transactions"></a><span data-ttu-id="76877-109">Illustrazione delle transazioni del pacchetto</span><span class="sxs-lookup"><span data-stu-id="76877-109">Illustration of Package Transactions</span></span>  
 <span data-ttu-id="76877-110">Nella figura seguente sono illustrati tre pacchetti che utilizzano transazioni.</span><span class="sxs-lookup"><span data-stu-id="76877-110">In the following diagram, there are three packages that all use transactions.</span></span> <span data-ttu-id="76877-111">Ogni pacchetto include più attività.</span><span class="sxs-lookup"><span data-stu-id="76877-111">Each package contains multiple tasks.</span></span> <span data-ttu-id="76877-112">Per evidenziare il comportamento delle transazioni, sono visualizzate solo le attività Esegui pacchetto.</span><span class="sxs-lookup"><span data-stu-id="76877-112">To emphasize the behavior of the transactions, only the Execute Package tasks are shown.</span></span> <span data-ttu-id="76877-113">Il pacchetto A esegue i pacchetti B e C. Il pacchetto B esegue a sua volta i pacchetti D ed E e il pacchetto C esegue il pacchetto F.</span><span class="sxs-lookup"><span data-stu-id="76877-113">Package A runs packages B and C. In turn, package B runs packages D and E, and package C runs package F.</span></span>  
  
 <span data-ttu-id="76877-114">Ai pacchetti e alle attività sono associati gli attributi di transazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="76877-114">Packages and tasks have the following transaction attributes:</span></span>  
  
-   <span data-ttu-id="76877-115">**TransactionOption** è impostata su **Required** per i pacchetti A e C</span><span class="sxs-lookup"><span data-stu-id="76877-115">**TransactionOption** is set to **Required** on packages A and C</span></span>  
  
-   <span data-ttu-id="76877-116">**TransactionOption** è impostata su **Supported** per i pacchetti B e D e per le attività Esegui pacchetto B, Esegui pacchetto D e Esegui pacchetto F.</span><span class="sxs-lookup"><span data-stu-id="76877-116">**TransactionOption** is set to **Supported** on packages B and D, and on the tasks Execute Package B, Execute Package D, and Execute Package F.</span></span>  
  
-   <span data-ttu-id="76877-117">**TransactionOption** è impostata su **NotSupported** per il pacchetto E e per le attività Esegui pacchetto C e Esegui pacchetto E.</span><span class="sxs-lookup"><span data-stu-id="76877-117">**TransactionOption** is set to **NotSupported** on package E, and on the tasks Execute Package C and Execute Package E.</span></span>  
  
 <span data-ttu-id="76877-118">![Flusso di transazioni ereditate](media/mw-dts-executepack.gif "Flusso di transazioni ereditate")</span><span class="sxs-lookup"><span data-stu-id="76877-118">![Flow of inherited transactions](media/mw-dts-executepack.gif "Flow of inherited transactions")</span></span>  
  
 <span data-ttu-id="76877-119">Solo i pacchetti B, D e F possono ereditare transazioni dal pacchetto padre.</span><span class="sxs-lookup"><span data-stu-id="76877-119">Only packages B, D, and F can inherit transactions from their parent packages.</span></span>  
  
 <span data-ttu-id="76877-120">I pacchetti B e D ereditano la transazione avviata dal pacchetto A.</span><span class="sxs-lookup"><span data-stu-id="76877-120">Packages B and D inherit the transaction that was started by package A.</span></span>  
  
 <span data-ttu-id="76877-121">Il pacchetto F eredita la transazione avviata dal pacchetto C.</span><span class="sxs-lookup"><span data-stu-id="76877-121">Package F inherits the transaction that was started by package C.</span></span>  
  
 <span data-ttu-id="76877-122">I pacchetti A e C controllano le proprie transazioni.</span><span class="sxs-lookup"><span data-stu-id="76877-122">Packages A and C control their own transactions.</span></span>  
  
 <span data-ttu-id="76877-123">Il pacchetto E non utilizza transazioni.</span><span class="sxs-lookup"><span data-stu-id="76877-123">Package E does not use transactions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="76877-124">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="76877-124">Related Tasks</span></span>  
 [<span data-ttu-id="76877-125">Configurazione di un pacchetto per l'utilizzo di transazioni</span><span class="sxs-lookup"><span data-stu-id="76877-125">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
