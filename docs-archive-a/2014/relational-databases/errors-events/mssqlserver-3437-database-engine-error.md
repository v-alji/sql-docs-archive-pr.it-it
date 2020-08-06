---
title: MSSQLSERVER_3437 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3437 (Database Engine error)
ms.assetid: b38216e2-b650-43bd-97af-061d54f60031
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ed8f2050f6f1b38bc5f3fcb7a9700b80e52f2763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636102"
---
# <a name="mssqlserver_3437"></a><span data-ttu-id="c17bd-102">MSSQLSERVER_3437</span><span class="sxs-lookup"><span data-stu-id="c17bd-102">MSSQLSERVER_3437</span></span>
    
## <a name="details"></a><span data-ttu-id="c17bd-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c17bd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c17bd-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="c17bd-104">Product Name</span></span>|<span data-ttu-id="c17bd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c17bd-105">SQL Server</span></span>|  
|<span data-ttu-id="c17bd-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="c17bd-106">Event ID</span></span>|<span data-ttu-id="c17bd-107">3437</span><span class="sxs-lookup"><span data-stu-id="c17bd-107">3437</span></span>|  
|<span data-ttu-id="c17bd-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="c17bd-108">Event Source</span></span>|<span data-ttu-id="c17bd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c17bd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c17bd-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c17bd-110">Component</span></span>|<span data-ttu-id="c17bd-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c17bd-111">SQLEngine</span></span>|  
|<span data-ttu-id="c17bd-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="c17bd-112">Symbolic Name</span></span>|<span data-ttu-id="c17bd-113">NODTC</span><span class="sxs-lookup"><span data-stu-id="c17bd-113">NODTC</span></span>|  
|<span data-ttu-id="c17bd-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="c17bd-114">Message Text</span></span>|<span data-ttu-id="c17bd-115">Errore durante il recupero del database '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="c17bd-115">An error occurred while recovering database '%.\*ls'.</span></span> <span data-ttu-id="c17bd-116">Impossibile connettersi a Microsoft Distributed Transaction Coordinator (MS DTC) per controllare lo stato di avanzamento della transazione %S_XID.</span><span class="sxs-lookup"><span data-stu-id="c17bd-116">Unable to connect to Microsoft Distributed Transaction Coordinator (MS DTC) to check the completion status of transaction %S_XID.</span></span> <span data-ttu-id="c17bd-117">Correggere MS DTC, quindi eseguire nuovamente il recupero.</span><span class="sxs-lookup"><span data-stu-id="c17bd-117">Fix MS DTC, and run recovery again.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c17bd-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="c17bd-118">Explanation</span></span>  
 <span data-ttu-id="c17bd-119">Una o più transazioni distribuite in cui viene utilizzato [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) sono risultate incomplete alla chiusura del database.</span><span class="sxs-lookup"><span data-stu-id="c17bd-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="c17bd-120">Non è stato possibile recuperare il database perché [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è in grado di connettersi a MS DTC per completare le transazioni o eseguirne il rollback.</span><span class="sxs-lookup"><span data-stu-id="c17bd-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot connect to MS DTC to complete or roll back the transactions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c17bd-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c17bd-121">User Action</span></span>  
 <span data-ttu-id="c17bd-122">Per recuperare il database, è necessario risolvere dapprima il problema relativo a MS DTC.</span><span class="sxs-lookup"><span data-stu-id="c17bd-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="c17bd-123">Per analizzare il problema relativo a MS DTC, esaminare i registri eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="c17bd-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="c17bd-124">Se non è possibile risolvere il problema e recuperare il database, ripristinare un backup del database.</span><span class="sxs-lookup"><span data-stu-id="c17bd-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
