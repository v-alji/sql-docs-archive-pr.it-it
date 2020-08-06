---
title: Più transazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], multiple
- multiple transactions
ms.assetid: c3664a94-be89-40c0-a3a0-84b74a7fedbe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ff909c92a23c965047edc0fcf278e17e4c76d94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628803"
---
# <a name="multiple-transactions"></a><span data-ttu-id="eb2af-102">Più transazioni</span><span class="sxs-lookup"><span data-stu-id="eb2af-102">Multiple Transactions</span></span>
  <span data-ttu-id="eb2af-103">Un pacchetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] potrebbe includere transazioni non correlate.</span><span class="sxs-lookup"><span data-stu-id="eb2af-103">It is possible for a package to include unrelated transactions in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="eb2af-104">Quando un contenitore all'interno di una gerarchia di contenitori nidificati non supporta le transazioni, i contenitori di livello superiore o inferiore nella gerarchia avviano transazioni distinte se sono configurati per il supporto di transazioni.</span><span class="sxs-lookup"><span data-stu-id="eb2af-104">Any time a container in the middle of a nested container hierarchy does not support transactions, the containers above or below it in the hierarchy start separate transactions if they are configured to support transactions.</span></span> <span data-ttu-id="eb2af-105">Viene quindi eseguito il commit o il rollback delle transazioni a partire dall'attività più interna della gerarchia fino al livello del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="eb2af-105">The transactions commit or roll back in order from the innermost task in the nested container hierarchy to the package.</span></span> <span data-ttu-id="eb2af-106">Dopo il commit della transazione più interna, tuttavia, viene eseguito il rollback solo in caso di interruzione di una transazione esterna.</span><span class="sxs-lookup"><span data-stu-id="eb2af-106">However, after the inner transaction commits, it does not roll back if an outer transaction is aborted.</span></span>

## <a name="illustration-of-multiple-transactions"></a><span data-ttu-id="eb2af-107">Illustrazione di più transazioni</span><span class="sxs-lookup"><span data-stu-id="eb2af-107">Illustration of Multiple Transactions</span></span>
 <span data-ttu-id="eb2af-108">Si supponga, ad esempio, che un pacchetto includa un contenitore Sequenza con due contenitori Ciclo Foreach ognuno dei quali include due attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="eb2af-108">For example, a package has a Sequence container that holds two Foreach Loop containers, and each container include two Execute SQL tasks.</span></span> <span data-ttu-id="eb2af-109">A differenza del contenitore Sequenza e delle attività Esegui SQL, i contenitori Ciclo Foreach non supportano transazioni.</span><span class="sxs-lookup"><span data-stu-id="eb2af-109">The Sequence container supports transactions, the Foreach Loop containers do not, and the Execute SQL tasks do.</span></span> <span data-ttu-id="eb2af-110">In questo esempio, ogni attività Esegui SQL avvia la propria transazione e non viene eseguito il rollback in caso di interruzione della transazione nell'attività Sequenza.</span><span class="sxs-lookup"><span data-stu-id="eb2af-110">In this example, each Execute SQL task would start its own transaction and would not roll back if the transaction on the Sequence task was aborted.</span></span>

 <span data-ttu-id="eb2af-111">Le proprietà TransactionOption del contenitore Sequenza, del contenitore Ciclo Foreach e delle attività Esegui SQL vengono impostate nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="eb2af-111">The TransactionOption properties of the Sequence container, Foreach Loop container and the Execute SQL tasks are set as follows:</span></span>

-   <span data-ttu-id="eb2af-112">La proprietà TransactionOption del contenitore Sequenza viene impostata su **Required**.</span><span class="sxs-lookup"><span data-stu-id="eb2af-112">The TransactionOption property of the Sequence container is set to **Required**.</span></span>

-   <span data-ttu-id="eb2af-113">La proprietà TransactionOption dei contenitori Ciclo Foreach viene impostata su **NotSupported**.</span><span class="sxs-lookup"><span data-stu-id="eb2af-113">The TransactionOption properties of the Foreach Loop containers are set to **NotSupported**.</span></span>

-   <span data-ttu-id="eb2af-114">La proprietà TransactionOption dell'attività Esegui SQL viene impostata su **Required**.</span><span class="sxs-lookup"><span data-stu-id="eb2af-114">The TransactionOption properties of the Execute SQL tasks are set to **Required**.</span></span>

 <span data-ttu-id="eb2af-115">Nella figura seguente vengono illustrate le cinque transazioni non correlate del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="eb2af-115">The following diagram shows the five unrelated transactions in the package.</span></span> <span data-ttu-id="eb2af-116">Una transazione viene avviata nel contenitore Sequenza e le altre quattro vengono avviate dalle attività Esegui SQL.</span><span class="sxs-lookup"><span data-stu-id="eb2af-116">One transaction is started by the Sequence container and four transactions are started by the Execute SQL tasks.</span></span>

 <span data-ttu-id="eb2af-117">![Implementazione di più transazioni](media/mw-dts-trans2.gif "Implementazione di più transazioni")</span><span class="sxs-lookup"><span data-stu-id="eb2af-117">![Implementation of multiple transactions](media/mw-dts-trans2.gif "Implementation of multiple transactions")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="eb2af-118">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="eb2af-118">Related Tasks</span></span>
 [<span data-ttu-id="eb2af-119">Configurazione di un pacchetto per l'utilizzo di transazioni</span><span class="sxs-lookup"><span data-stu-id="eb2af-119">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)


