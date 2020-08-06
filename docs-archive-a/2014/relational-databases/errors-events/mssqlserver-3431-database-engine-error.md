---
title: MSSQLSERVER_3431 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3431 (Database Engine error)
ms.assetid: 9541217f-e5c6-4a12-a19a-006058f1d3f3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9b62047a25d71ca05dc3ab03651e5672353bc0a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636107"
---
# <a name="mssqlserver_3431"></a><span data-ttu-id="25b2b-102">MSSQLSERVER_3431</span><span class="sxs-lookup"><span data-stu-id="25b2b-102">MSSQLSERVER_3431</span></span>
    
## <a name="details"></a><span data-ttu-id="25b2b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="25b2b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25b2b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="25b2b-104">Product Name</span></span>|<span data-ttu-id="25b2b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25b2b-105">SQL Server</span></span>|  
|<span data-ttu-id="25b2b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="25b2b-106">Event ID</span></span>|<span data-ttu-id="25b2b-107">3431</span><span class="sxs-lookup"><span data-stu-id="25b2b-107">3431</span></span>|  
|<span data-ttu-id="25b2b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="25b2b-108">Event Source</span></span>|<span data-ttu-id="25b2b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25b2b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25b2b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="25b2b-110">Component</span></span>|<span data-ttu-id="25b2b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="25b2b-111">SQLEngine</span></span>|  
|<span data-ttu-id="25b2b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="25b2b-112">Symbolic Name</span></span>|<span data-ttu-id="25b2b-113">UNRESOLVED_XACT</span><span class="sxs-lookup"><span data-stu-id="25b2b-113">UNRESOLVED_XACT</span></span>|  
|<span data-ttu-id="25b2b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="25b2b-114">Message Text</span></span>|<span data-ttu-id="25b2b-115">Impossibile recuperare il database '%.\*ls' (ID di database %d) perché i risultati di una transazione non sono stati risolti.</span><span class="sxs-lookup"><span data-stu-id="25b2b-115">Could not recover database '%.\*ls' (database ID %d) because of unresolved transaction outcomes.</span></span> <span data-ttu-id="25b2b-116">Le transazioni di Microsoft Distributed Transaction Coordinator (MS DTC) sono state preparate, ma l'applicazione non è stata in grado di determinarne la risoluzione.</span><span class="sxs-lookup"><span data-stu-id="25b2b-116">Microsoft Distributed Transaction Coordinator (MS DTC) transactions were prepared, but MS DTC was unable to determine the resolution.</span></span> <span data-ttu-id="25b2b-117">Per risolvere il problema, correggere MS DTC, eseguire un ripristino da un backup completo oppure correggere il database.</span><span class="sxs-lookup"><span data-stu-id="25b2b-117">To resolve, either fix MS DTC, restore from a full backup, or repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25b2b-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="25b2b-118">Explanation</span></span>  
 <span data-ttu-id="25b2b-119">Una o più transazioni distribuite in cui viene utilizzato [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) sono risultate incomplete alla chiusura del database.</span><span class="sxs-lookup"><span data-stu-id="25b2b-119">One or more distributed transactions that were using [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) were incomplete when the database was shut down.</span></span> <span data-ttu-id="25b2b-120">Non è stato possibile recuperare il database perché [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è in grado di completare le transazioni o di eseguirne il rollback senza disporre di ulteriori informazioni restituite da MS DTC.</span><span class="sxs-lookup"><span data-stu-id="25b2b-120">Recovery of this database failed because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot complete the transactions or roll back the transactions without more information from MS DTC.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25b2b-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="25b2b-121">User Action</span></span>  
 <span data-ttu-id="25b2b-122">Per recuperare il database, è necessario risolvere dapprima il problema relativo a MS DTC.</span><span class="sxs-lookup"><span data-stu-id="25b2b-122">To recover this database, you must first resolve the problem with MS DTC.</span></span> <span data-ttu-id="25b2b-123">Per analizzare il problema relativo a MS DTC, esaminare i registri eventi di Windows.</span><span class="sxs-lookup"><span data-stu-id="25b2b-123">To investigate the problem with MS DTC, examine the Windows event logs.</span></span> <span data-ttu-id="25b2b-124">Se non è possibile risolvere il problema e recuperare il database, ripristinare un backup del database.</span><span class="sxs-lookup"><span data-stu-id="25b2b-124">If you cannot resolve the problem with MS DTC and recover the database, restore a backup of database.</span></span>  
  
  
