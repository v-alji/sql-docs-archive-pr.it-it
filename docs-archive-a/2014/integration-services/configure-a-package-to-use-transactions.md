---
title: Configurare un pacchetto per l'utilizzo di transazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], configuring packages to use
ms.assetid: 8bf14957-27b4-456b-81d9-e1a0e0ca94b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f469c2439deb2d16ac9046a1628e82c34e39b31d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713400"
---
# <a name="configure-a-package-to-use-transactions"></a><span data-ttu-id="62f64-102">Configurazione di un pacchetto per l'utilizzo di transazioni</span><span class="sxs-lookup"><span data-stu-id="62f64-102">Configure a Package to Use Transactions</span></span>
  <span data-ttu-id="62f64-103">Quando si configura un pacchetto per l'utilizzo di transazioni, sono disponibili due opzioni:</span><span class="sxs-lookup"><span data-stu-id="62f64-103">When you configure a package to use transactions, you have two options:</span></span>  
  
-   <span data-ttu-id="62f64-104">Utilizzare una sola transazione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62f64-104">Have a single transaction for the package.</span></span> <span data-ttu-id="62f64-105">In questo caso, è il pacchetto stesso che *inizializza* questa transazione, mentre le singole attività e i contenitori del pacchetto partecipano a questa unica transazione.</span><span class="sxs-lookup"><span data-stu-id="62f64-105">In this case, it is the package itself that *initiates* this transaction, whereas individual tasks and containers in the package participate in this single transaction.</span></span>  
  
-   <span data-ttu-id="62f64-106">Utilizzare più transazioni nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62f64-106">Have multiple transactions in the package.</span></span> <span data-ttu-id="62f64-107">In questo caso, il pacchetto supporta le transazioni, ma sono le singole attività e i contenitori del pacchetto a inizializzare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="62f64-107">In this case, the package supports transactions, but individual tasks and containers in the package actually initiate the transactions.</span></span>  
  
 <span data-ttu-id="62f64-108">Nelle procedure seguenti viene descritto come configurare entrambe le opzioni.</span><span class="sxs-lookup"><span data-stu-id="62f64-108">The following procedures describe how to configure both options.</span></span>  
  
## <a name="configuring-a-single-transaction"></a><span data-ttu-id="62f64-109">Configurazione di una transazione singola</span><span class="sxs-lookup"><span data-stu-id="62f64-109">Configuring a Single Transaction</span></span>  
 <span data-ttu-id="62f64-110">In questo caso, il pacchetto stesso inizializza un'unica transazione.</span><span class="sxs-lookup"><span data-stu-id="62f64-110">In this option, the package itself initiates a single transaction.</span></span> <span data-ttu-id="62f64-111">Il pacchetto viene configurato per avviare la transazione impostando la proprietà TransactionOption del pacchetto su `Required` .</span><span class="sxs-lookup"><span data-stu-id="62f64-111">You configure the package to initiate this transaction by setting the TransactionOption property of the package to `Required`.</span></span>  
  
 <span data-ttu-id="62f64-112">In questa unica transazione verranno quindi inserite le attività e i contenitori specifici.</span><span class="sxs-lookup"><span data-stu-id="62f64-112">Next, you enlist specific tasks and containers in this single transaction.</span></span> <span data-ttu-id="62f64-113">Per integrare un'attività o un contenitore in una transazione, impostare la proprietà TransactionOption dell'attività o del contenitore su `Supported` .</span><span class="sxs-lookup"><span data-stu-id="62f64-113">To enlist a task or container in a transaction, you set the TransactionOption property of that task or container to `Supported`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-a-single-transaction"></a><span data-ttu-id="62f64-114">Per configurare un pacchetto per l'utilizzo di una transazione singola</span><span class="sxs-lookup"><span data-stu-id="62f64-114">To configure a package to use a single transaction</span></span>  
  
1.  <span data-ttu-id="62f64-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto che si desidera configurare per l'utilizzo di una transazione.</span><span class="sxs-lookup"><span data-stu-id="62f64-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use a transaction.</span></span>  
  
2.  <span data-ttu-id="62f64-116">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="62f64-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="62f64-117">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="62f64-117">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="62f64-118">Fare clic con il pulsante destro del mouse in un punto qualsiasi dello sfondo dell'area di progettazione del flusso di controllo, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="62f64-118">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="62f64-119">Nella finestra **Proprietà** impostare la proprietà TransactionOption su `Required` .</span><span class="sxs-lookup"><span data-stu-id="62f64-119">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
6.  <span data-ttu-id="62f64-120">Nell'area di progettazione della scheda **Flusso di controllo** fare clic con il pulsante destro del mouse sull'attività o il contenitore che si vuole integrare nella transazione e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="62f64-120">On the design surface of the **ControlFlow** tab, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="62f64-121">Nella finestra **Proprietà** impostare la proprietà TransactionOption su `Supported` .</span><span class="sxs-lookup"><span data-stu-id="62f64-121">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62f64-122">Per integrare una connessione in una transazione, integrare nella transazione le attività che la utilizzano.</span><span class="sxs-lookup"><span data-stu-id="62f64-122">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="62f64-123">Per altre informazioni, vedere [Connessioni in Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="62f64-123">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
8.  <span data-ttu-id="62f64-124">Ripetere i passaggi 6 e 7 per ogni attività e ogni contenitore che si desidera registrare nella transazione.</span><span class="sxs-lookup"><span data-stu-id="62f64-124">Repeat steps 6 and 7 for each task and container that you want to enroll in the transaction.</span></span>  
  
## <a name="configuring-multiple-transactions"></a><span data-ttu-id="62f64-125">Configurazione di più transazioni</span><span class="sxs-lookup"><span data-stu-id="62f64-125">Configuring Multiple Transactions</span></span>  
 <span data-ttu-id="62f64-126">In questo caso, il pacchetto supporta le transazioni ma non ne avvia alcuna.</span><span class="sxs-lookup"><span data-stu-id="62f64-126">In this option, the package itself supports transactions but does not start a transaction.</span></span> <span data-ttu-id="62f64-127">Il pacchetto viene configurato per supportare le transazioni impostando la proprietà TransactionOption del pacchetto su `Supported` .</span><span class="sxs-lookup"><span data-stu-id="62f64-127">You configure the package to support transactions by setting the TransactionOption property of the package to `Supported`.</span></span>  
  
 <span data-ttu-id="62f64-128">Configurare quindi le attività e i contenitori desiderati all'interno del pacchetto in modo che inizializzino la transazione o vengano eseguiti con essa.</span><span class="sxs-lookup"><span data-stu-id="62f64-128">Next, you configure the desired tasks and containers inside the package to initiate or participate in transactions.</span></span> <span data-ttu-id="62f64-129">Per configurare un'attività o un contenitore per avviare una transazione, impostare la proprietà TransactionOption dell'attività o del contenitore su `Required` .</span><span class="sxs-lookup"><span data-stu-id="62f64-129">To configure a task or container to initiate a transaction, you set the TransactionOption property of that task or container to `Required`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-multiple-transactions"></a><span data-ttu-id="62f64-130">Per configurare un pacchetto per l'utilizzo di più transazioni</span><span class="sxs-lookup"><span data-stu-id="62f64-130">To configure a package to use multiple transactions</span></span>  
  
1.  <span data-ttu-id="62f64-131">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenente il pacchetto che si desidera configurare per l'utilizzo delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="62f64-131">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use transaction.s</span></span>  
  
2.  <span data-ttu-id="62f64-132">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="62f64-132">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="62f64-133">Fare clic sulla scheda **Flusso di controllo** .</span><span class="sxs-lookup"><span data-stu-id="62f64-133">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="62f64-134">Fare clic con il pulsante destro del mouse in un punto qualsiasi dello sfondo dell'area di progettazione del flusso di controllo, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="62f64-134">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="62f64-135">Nella finestra **Proprietà** impostare la proprietà TransactionOption su `Supported` .</span><span class="sxs-lookup"><span data-stu-id="62f64-135">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62f64-136">Il pacchetto supporta le transazioni, ma le transazioni vengono avviate da attività o contenitori nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="62f64-136">The package supports transactions, but the transactions are started by task or containers in the package.</span></span>  
  
6.  <span data-ttu-id="62f64-137">Nell'area di progettazione della scheda **Flusso di controllo** fare clic con il pulsante destro del mouse sull'attività o il contenitore del pacchetto per il quale si vuole avviare una transazione e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="62f64-137">On the design surface of the **ControlFlow** tab, right-click the task or the container in the package for which you want to start a transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="62f64-138">Nella finestra **Proprietà** impostare la proprietà TransactionOption su `Required` .</span><span class="sxs-lookup"><span data-stu-id="62f64-138">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
8.  <span data-ttu-id="62f64-139">Se la transazione viene avviata da un contenitore, fare clic con il pulsante destro del mouse sull'attività o il contenitore che si vuole includere nella transazione e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="62f64-139">If a transaction is started by a container, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
9. <span data-ttu-id="62f64-140">Nella finestra **Proprietà** impostare la proprietà TransactionOption su `Supported` .</span><span class="sxs-lookup"><span data-stu-id="62f64-140">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="62f64-141">Per integrare una connessione in una transazione, integrare nella transazione le attività che la utilizzano.</span><span class="sxs-lookup"><span data-stu-id="62f64-141">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="62f64-142">Per altre informazioni, vedere [Connessioni in Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="62f64-142">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
10. <span data-ttu-id="62f64-143">Ripetere i passaggi da 6 a 9 per ogni attività e ogni contenitore che avvierà una transazione.</span><span class="sxs-lookup"><span data-stu-id="62f64-143">Repeat steps 6 through 9 for each task and container that starts a transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62f64-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62f64-144">See Also</span></span>  
 [<span data-ttu-id="62f64-145">Transazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="62f64-145">Integration Services Transactions</span></span>](integration-services-transactions.md)  
  
  
