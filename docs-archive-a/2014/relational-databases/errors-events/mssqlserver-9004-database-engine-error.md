---
title: MSSQLSERVER_9004 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9004 (Database Engine error)
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 910665b4349e5b13c5abb4fd687dcf0c6fc122cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627748"
---
# <a name="mssqlserver_9004"></a><span data-ttu-id="9d32d-102">MSSQLSERVER_9004</span><span class="sxs-lookup"><span data-stu-id="9d32d-102">MSSQLSERVER_9004</span></span>
    
## <a name="details"></a><span data-ttu-id="9d32d-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9d32d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d32d-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="9d32d-104">Product Name</span></span>|<span data-ttu-id="9d32d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9d32d-105">SQL Server</span></span>|  
|<span data-ttu-id="9d32d-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="9d32d-106">Event ID</span></span>|<span data-ttu-id="9d32d-107">9004</span><span class="sxs-lookup"><span data-stu-id="9d32d-107">9004</span></span>|  
|<span data-ttu-id="9d32d-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="9d32d-108">Event Source</span></span>|<span data-ttu-id="9d32d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9d32d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9d32d-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9d32d-110">Component</span></span>|<span data-ttu-id="9d32d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9d32d-111">SQLEngine</span></span>|  
|<span data-ttu-id="9d32d-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="9d32d-112">Symbolic Name</span></span>|<span data-ttu-id="9d32d-113">LOG_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="9d32d-113">LOG_CORRUPT</span></span>|  
|<span data-ttu-id="9d32d-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="9d32d-114">Message Text</span></span>|<span data-ttu-id="9d32d-115">Si è verificato un errore durante l'elaborazione del log del database '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="9d32d-115">An error occurred while processing the log for database '%.\*ls'.</span></span>  <span data-ttu-id="9d32d-116">Se possibile, ripristinarlo da un backup.</span><span class="sxs-lookup"><span data-stu-id="9d32d-116">If possible, restore from backup.</span></span> <span data-ttu-id="9d32d-117">Se non è disponibile un backup, potrebbe essere necessario ricompilare il log.</span><span class="sxs-lookup"><span data-stu-id="9d32d-117">If a backup is not available, it might be necessary to rebuild the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9d32d-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9d32d-118">Explanation</span></span>  
 <span data-ttu-id="9d32d-119">Si è verificato un errore nell'elaborazione del log durante un'operazione di rollback, recupero o replica.</span><span class="sxs-lookup"><span data-stu-id="9d32d-119">An error was encountered while processing the log during rollback, recovery, or replication.</span></span> <span data-ttu-id="9d32d-120">Potrebbe trattarsi di un errore rilevato dal sistema operativo o di un errore di consistenza interno rilevato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d32d-120">This could indicate an error detected by the operating system-or an internal consistency error detected by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9d32d-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="9d32d-121">User Action</span></span>  
 <span data-ttu-id="9d32d-122">Per correggere l'errore, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d32d-122">One of the following actions will correct this error:</span></span>  
  
-   <span data-ttu-id="9d32d-123">Eseguire il ripristino da un backup.</span><span class="sxs-lookup"><span data-stu-id="9d32d-123">Restore from a backup.</span></span>  
  
-   <span data-ttu-id="9d32d-124">Ricompilare il log.</span><span class="sxs-lookup"><span data-stu-id="9d32d-124">Rebuild the log.</span></span>  
  
 <span data-ttu-id="9d32d-125">Esaminare inoltre il registro eventi e il log degli errori di sistema per individuare le cause all'interno del sistema che possono aver generato il problema.</span><span class="sxs-lookup"><span data-stu-id="9d32d-125">Also, check system event and error logs to identify issues within the system that may have caused the problem.</span></span>  
  
  
