---
title: MSSQLSERVER_8525 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "8525"
helpviewer_keywords:
- 8525 (Database Engine error)
ms.assetid: 297867c1-691e-4d6b-a3be-a7575015ecfa
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 36db48ca2a9afd08dadcd12abc13b9978e227b00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635072"
---
# <a name="mssqlserver_8525"></a><span data-ttu-id="bab4f-102">MSSQLSERVER_8525</span><span class="sxs-lookup"><span data-stu-id="bab4f-102">MSSQLSERVER_8525</span></span>
    
## <a name="details"></a><span data-ttu-id="bab4f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="bab4f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bab4f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="bab4f-104">Product Name</span></span>|<span data-ttu-id="bab4f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bab4f-105">SQL Server</span></span>|  
|<span data-ttu-id="bab4f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="bab4f-106">Event ID</span></span>|<span data-ttu-id="bab4f-107">8525</span><span class="sxs-lookup"><span data-stu-id="bab4f-107">8525</span></span>|  
|<span data-ttu-id="bab4f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="bab4f-108">Event Source</span></span>|<span data-ttu-id="bab4f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="bab4f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="bab4f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="bab4f-110">Component</span></span>|<span data-ttu-id="bab4f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="bab4f-111">SQLEngine</span></span>|  
|<span data-ttu-id="bab4f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="bab4f-112">Symbolic Name</span></span>||  
|<span data-ttu-id="bab4f-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="bab4f-113">Message Text</span></span>|<span data-ttu-id="bab4f-114">La transazione distribuita è stata completata.</span><span class="sxs-lookup"><span data-stu-id="bab4f-114">Distributed transaction completed.</span></span> <span data-ttu-id="bab4f-115">Integrare questa sessione in una nuova transazione o nella transazione NULL.</span><span class="sxs-lookup"><span data-stu-id="bab4f-115">Either enlist this session in a new transaction or the NULL transaction.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bab4f-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bab4f-116">Explanation</span></span>  
 <span data-ttu-id="bab4f-117">Il modello di programmazione per l'uso di Distributed Transaction Coordinator con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] richiede alle applicazioni l'integrazione esplicita in una transazione distribuita o l'esclusione esplicita da essa.</span><span class="sxs-lookup"><span data-stu-id="bab4f-117">The programming model for using the Distributed Transaction Coordinator with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires applications to explicitly enlist to and defect from a distributed transaction.</span></span>  
  
 <span data-ttu-id="bab4f-118">Questo errore si verifica quando vengono soddisfatte le quattro condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bab4f-118">This error occurs when the following four conditions are met:</span></span>  
  
-   <span data-ttu-id="bab4f-119">L'applicazione è stata integrata in una transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="bab4f-119">The application has enlisted into a distributed transaction.</span></span>  
  
-   <span data-ttu-id="bab4f-120">La transazione di cui è stato eseguito il commit o il rollback, è stata interrotta per un motivo qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="bab4f-120">The transaction has ended, either committed or rolled back, for any reason.</span></span>  
  
-   <span data-ttu-id="bab4f-121">L'applicazione utente non è stata esclusa in modo esplicito da una transazione distribuita o integrata in modo esplicito in una nuova transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="bab4f-121">The user application has not explicitly defected from a distributed transaction or explicitly enlisted into a new distributed transaction.</span></span>  
  
-   <span data-ttu-id="bab4f-122">L'applicazione tenta di eseguire qualsiasi operazione transazionale, ad eccezione dell'esclusione da una transazione distribuita esistente o dell'integrazione in una nuova transazione distribuita, ad esempio l'esecuzione di una query o l'avvio di una transazione locale.</span><span class="sxs-lookup"><span data-stu-id="bab4f-122">The application tries to do any transactional operation other than defecting from existing distributed transaction or enlisting to a new distributed transaction, such as issuing a query or starting a local transaction.</span></span>  
  
 <span data-ttu-id="bab4f-123">Lo stato di errore 1 viene utilizzato quando l'applicazione esegue un'operazione che consente di creare transazioni locali. Lo stato 2 viene utilizzato quando l'applicazione tenta l'integrazione in una sessione associata.</span><span class="sxs-lookup"><span data-stu-id="bab4f-123">Error state 1 is used when the application performs an operation that creates local transactions, and state 2 is used when application tries to enlist to a bound session.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bab4f-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="bab4f-124">User Action</span></span>  
 <span data-ttu-id="bab4f-125">Dopo l'integrazione in una transazione distribuita, l'applicazione deve essere esclusa in modo esplicito dalla transazione distribuita o integrata in un'altra transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="bab4f-125">After an application has enlisted into a distributed transaction, the application must explicitly defect from the distributed transaction or enlist to another distributed transaction.</span></span> <span data-ttu-id="bab4f-126">Ciò determina l'esclusione implicita da una transazione inclusa in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bab4f-126">This will implicitly defect from a previous enlisted transaction.</span></span> <span data-ttu-id="bab4f-127">Per informazioni sulla sintassi esatta da utilizzare per l'esclusione da una transazione distribuita o l'inclusione in essa, vedere il manuale dell'interfaccia di programmazione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bab4f-127">For the exact syntax to defect from or enlist to a distributed transaction, see the programming interface manual for the application.</span></span>  
  
  
