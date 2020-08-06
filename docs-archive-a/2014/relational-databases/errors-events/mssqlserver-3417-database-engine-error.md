---
title: MSSQLSERVER_3417 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3417 (Database Engine error)
ms.assetid: 005829c8-cf57-4828-818a-bbe8ee2e00f0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 680e5a4266c7d0d9aaacb7b3deb9525a002077e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636109"
---
# <a name="mssqlserver_3417"></a><span data-ttu-id="134c4-102">MSSQLSERVER_3417</span><span class="sxs-lookup"><span data-stu-id="134c4-102">MSSQLSERVER_3417</span></span>
    
## <a name="details"></a><span data-ttu-id="134c4-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="134c4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="134c4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="134c4-104">Product Name</span></span>|<span data-ttu-id="134c4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="134c4-105">SQL Server</span></span>|  
|<span data-ttu-id="134c4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="134c4-106">Event ID</span></span>|<span data-ttu-id="134c4-107">3417</span><span class="sxs-lookup"><span data-stu-id="134c4-107">3417</span></span>|  
|<span data-ttu-id="134c4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="134c4-108">Event Source</span></span>|<span data-ttu-id="134c4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="134c4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="134c4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="134c4-110">Component</span></span>|<span data-ttu-id="134c4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="134c4-111">SQLEngine</span></span>|  
|<span data-ttu-id="134c4-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="134c4-112">Symbolic Name</span></span>|<span data-ttu-id="134c4-113">REC_BADMASTER</span><span class="sxs-lookup"><span data-stu-id="134c4-113">REC_BADMASTER</span></span>|  
|<span data-ttu-id="134c4-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="134c4-114">Message Text</span></span>|<span data-ttu-id="134c4-115">Impossibile recuperare il database master.</span><span class="sxs-lookup"><span data-stu-id="134c4-115">Cannot recover the master database.</span></span> <span data-ttu-id="134c4-116">Impossibile eseguire SQL Server.</span><span class="sxs-lookup"><span data-stu-id="134c4-116">SQL Server is unable to run.</span></span> <span data-ttu-id="134c4-117">Ripristinare il master da un backup completo, correggerlo o ricompilarlo.</span><span class="sxs-lookup"><span data-stu-id="134c4-117">Restore master from a full backup, repair it, or rebuild it.</span></span> <span data-ttu-id="134c4-118">Per ulteriori informazioni sulla ricompilazione del database master, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="134c4-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="134c4-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="134c4-119">Explanation</span></span>  
 <span data-ttu-id="134c4-120">Non è possibile avviare il database **master** in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="134c4-120">SQL Server cannot start the **master** database.</span></span> <span data-ttu-id="134c4-121">Se non è possibile portare online il database **master** o **tempdb**, non è possibile eseguire SQL Server.</span><span class="sxs-lookup"><span data-stu-id="134c4-121">If the **master** or **tempdb** cannot be brought online, SQL Server cannot run.</span></span> <span data-ttu-id="134c4-122">Questo errore in genere è preceduto da altri errori.</span><span class="sxs-lookup"><span data-stu-id="134c4-122">This error is usually preceded by other errors.</span></span> <span data-ttu-id="134c4-123">Esaminare i log degli errori per individuare la causa radice.</span><span class="sxs-lookup"><span data-stu-id="134c4-123">Review error logs to find the root cause.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="134c4-124">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="134c4-124">User Action</span></span>  
 <span data-ttu-id="134c4-125">Ripristinare il backup del database oppure correggere il database.</span><span class="sxs-lookup"><span data-stu-id="134c4-125">Restore backup of the database or repair the database.</span></span>  
  
  
