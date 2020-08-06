---
title: MSSQLSERVER_17065 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17065 (Database Engine error)
ms.assetid: 63c2ba5a-be34-461e-bee1-03c25b396cd2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47aebfa29b60a1c2ae50c6699946312996d26e6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636153"
---
# <a name="mssqlserver_17065"></a><span data-ttu-id="6ab50-102">MSSQLSERVER_17065</span><span class="sxs-lookup"><span data-stu-id="6ab50-102">MSSQLSERVER_17065</span></span>
    
## <a name="details"></a><span data-ttu-id="6ab50-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6ab50-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6ab50-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6ab50-104">Product Name</span></span>|<span data-ttu-id="6ab50-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6ab50-105">SQL Server</span></span>|  
|<span data-ttu-id="6ab50-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="6ab50-106">Event ID</span></span>|<span data-ttu-id="6ab50-107">17065</span><span class="sxs-lookup"><span data-stu-id="6ab50-107">17065</span></span>|  
|<span data-ttu-id="6ab50-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6ab50-108">Event Source</span></span>|<span data-ttu-id="6ab50-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6ab50-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6ab50-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6ab50-110">Component</span></span>|<span data-ttu-id="6ab50-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6ab50-111">SQLEngine</span></span>|  
|<span data-ttu-id="6ab50-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="6ab50-112">Symbolic Name</span></span>|<span data-ttu-id="6ab50-113">SQLASSERT_BOTH</span><span class="sxs-lookup"><span data-stu-id="6ab50-113">SQLASSERT_BOTH</span></span>|  
|<span data-ttu-id="6ab50-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6ab50-114">Message Text</span></span>|<span data-ttu-id="6ab50-115">Asserzione SQL Server: File: \<%s>, riga = %d Asserzione non riuscita = '%s' %s.</span><span class="sxs-lookup"><span data-stu-id="6ab50-115">SQL Server Assertion: File: \<%s>, line = %d Failed Assertion = '%s' %s.</span></span> <span data-ttu-id="6ab50-116">L'errore può essere correlato agli intervalli di tempo.</span><span class="sxs-lookup"><span data-stu-id="6ab50-116">This error may be timing-related.</span></span> <span data-ttu-id="6ab50-117">Se dopo aver rieseguito l'istruzione l'errore persiste, utilizzare DBCC CHECKDB per verificare l'integrità strutturale del database oppure riavviare il server per verificare che le strutture di dati in memoria non siano danneggiate.</span><span class="sxs-lookup"><span data-stu-id="6ab50-117">If the error persists after rerunning the statement, use DBCC CHECKDB to check the database for structural integrity, or restart the server to ensure in-memory data structures are not corrupted.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6ab50-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6ab50-118">Explanation</span></span>  
 <span data-ttu-id="6ab50-119">Questo errore può essere causato da errori temporanei, correlati agli intervalli di tempo o da un danno dei dati in memoria o su disco.</span><span class="sxs-lookup"><span data-stu-id="6ab50-119">This error can be caused by transient, timing-related errors, or by in-memory or on-disk data corruption.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6ab50-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6ab50-120">User Action</span></span>  
 <span data-ttu-id="6ab50-121">Eseguire nuovamente l'istruzione che ha causato l'attivazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6ab50-121">Rerun the statement that caused the exception to fire.</span></span> <span data-ttu-id="6ab50-122">Se l'errore è causato da un evento correlato agli intervalli di tempo, è possibile che non si ripeta.</span><span class="sxs-lookup"><span data-stu-id="6ab50-122">If the error was caused by a timing-related event, the error may not recur.</span></span> <span data-ttu-id="6ab50-123">Se il problema persiste, eseguire DBCC CHECKDB per verificare il danno su disco.</span><span class="sxs-lookup"><span data-stu-id="6ab50-123">If the problem persists, run DBCC CHECKDB to check for on-disk corruption.</span></span> <span data-ttu-id="6ab50-124">Riavviare il server per assicurarsi che le strutture di dati in memoria non siano danneggiate.</span><span class="sxs-lookup"><span data-stu-id="6ab50-124">Restart the server to ensure the in-memory data structures are not corrupted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ab50-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ab50-125">See Also</span></span>  
 [<span data-ttu-id="6ab50-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6ab50-126">DBCC CHECKDB &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)  
  
  
