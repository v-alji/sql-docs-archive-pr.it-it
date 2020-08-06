---
title: MSSQLSERVER_3619 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3619 (Database Engine error)
ms.assetid: 7d94f8d9-65ca-4fde-9c17-7b83e94a3779
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2328ee6366d47130a02c444bce65b7b655af7965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636101"
---
# <a name="mssqlserver_3619"></a><span data-ttu-id="e7ac4-102">MSSQLSERVER_3619</span><span class="sxs-lookup"><span data-stu-id="e7ac4-102">MSSQLSERVER_3619</span></span>
    
## <a name="details"></a><span data-ttu-id="e7ac4-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e7ac4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7ac4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e7ac4-104">Product Name</span></span>|<span data-ttu-id="e7ac4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e7ac4-105">SQL Server</span></span>|  
|<span data-ttu-id="e7ac4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e7ac4-106">Event ID</span></span>|<span data-ttu-id="e7ac4-107">3619</span><span class="sxs-lookup"><span data-stu-id="e7ac4-107">3619</span></span>|  
|<span data-ttu-id="e7ac4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e7ac4-108">Event Source</span></span>|<span data-ttu-id="e7ac4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e7ac4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e7ac4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e7ac4-110">Component</span></span>|<span data-ttu-id="e7ac4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e7ac4-111">SQLEngine</span></span>|  
|<span data-ttu-id="e7ac4-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e7ac4-112">Symbolic Name</span></span>|<span data-ttu-id="e7ac4-113">SYS_NOLOG</span><span class="sxs-lookup"><span data-stu-id="e7ac4-113">SYS_NOLOG</span></span>|  
|<span data-ttu-id="e7ac4-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e7ac4-114">Message Text</span></span>|<span data-ttu-id="e7ac4-115">Impossibile scrivere un record di checkpoint nel database con ID %d perché nel log non è disponibile spazio.</span><span class="sxs-lookup"><span data-stu-id="e7ac4-115">Could not write a checkpoint record in database ID %d because the log is out of space.</span></span> <span data-ttu-id="e7ac4-116">Rivolgersi all'amministratore di sistema per troncare il log o per allocare più spazio per i file dei log del database.</span><span class="sxs-lookup"><span data-stu-id="e7ac4-116">Contact the database administrator to truncate the log or allocate more space to the database log files.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e7ac4-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e7ac4-117">Explanation</span></span>  
 <span data-ttu-id="e7ac4-118">Lo spazio nel log delle transazioni è esaurito.</span><span class="sxs-lookup"><span data-stu-id="e7ac4-118">The transaction log is out of disk space.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e7ac4-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e7ac4-119">User Action</span></span>  
 <span data-ttu-id="e7ac4-120">Troncare il log per liberare spazio oppure allocare ulteriore spazio per il log.</span><span class="sxs-lookup"><span data-stu-id="e7ac4-120">Truncate the log to release some space, or allocate more space to the log.</span></span> <span data-ttu-id="e7ac4-121">Per ulteriori informazioni, vedere "Risoluzione dei problemi relativi a un log delle transazioni pieno (Errore 9002)" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e7ac4-121">For more information see, "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
  
