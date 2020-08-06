---
title: MSSQLSERVER_9003 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6f67e4184ea54be6bcd5c2a74d3c0e0711b702f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635059"
---
# <a name="mssqlserver_9003"></a><span data-ttu-id="8d5d6-102">MSSQLSERVER_9003</span><span class="sxs-lookup"><span data-stu-id="8d5d6-102">MSSQLSERVER_9003</span></span>
    
## <a name="details"></a><span data-ttu-id="8d5d6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8d5d6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d5d6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8d5d6-104">Product Name</span></span>|<span data-ttu-id="8d5d6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8d5d6-105">SQL Server</span></span>|  
|<span data-ttu-id="8d5d6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8d5d6-106">Event ID</span></span>|<span data-ttu-id="8d5d6-107">9003</span><span class="sxs-lookup"><span data-stu-id="8d5d6-107">9003</span></span>|  
|<span data-ttu-id="8d5d6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8d5d6-108">Event Source</span></span>|<span data-ttu-id="8d5d6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8d5d6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8d5d6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8d5d6-110">Component</span></span>|<span data-ttu-id="8d5d6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8d5d6-111">SQLEngine</span></span>|  
|<span data-ttu-id="8d5d6-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="8d5d6-112">Symbolic Name</span></span>|<span data-ttu-id="8d5d6-113">LOG_INVALID_LSN</span><span class="sxs-lookup"><span data-stu-id="8d5d6-113">LOG_INVALID_LSN</span></span>|  
|<span data-ttu-id="8d5d6-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8d5d6-114">Message Text</span></span>|<span data-ttu-id="8d5d6-115">Il numero di analisi log %S_LSN passato alla funzione di analisi dei log nel database '%.\*ls' non è valido.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-115">The log scan number %S_LSN passed to log scan in database '%.\*ls' is not valid.</span></span> <span data-ttu-id="8d5d6-116">L'errore può indicare la presenza di dati danneggiati o un problema di mancata corrispondenza tra il file di log (con estensione ldf) e il file di dati (con estensione mdf).</span><span class="sxs-lookup"><span data-stu-id="8d5d6-116">This error may indicate data corruption or that the log file (.ldf) does not match the data file (.mdf).</span></span> <span data-ttu-id="8d5d6-117">Se l'errore si è verificato durante la replica, ricreare la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-117">If this error occurred during replication, re-create the publication.</span></span> <span data-ttu-id="8d5d6-118">Se invece il problema provoca un errore all'avvio, eseguire il ripristino da un backup.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-118">Otherwise, restore from backup if the problem results in a failure during startup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8d5d6-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8d5d6-119">Explanation</span></span>  
 <span data-ttu-id="8d5d6-120">Un componente ha passato un numero di sequenza del file di log (LSN) non valido allo strumento di gestione del log per il database.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-120">A component passed an invalid log sequence number to the log manager for the database.</span></span> <span data-ttu-id="8d5d6-121">L'errore potrebbe verificarsi durante la replica oppure in presenza di dati danneggiati o di incoerenza tra il file di dati primario e il log.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-121">This could be replication, corruption, or an inconsistency between the primary data file and the log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d5d6-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8d5d6-122">User Action</span></span>  
 <span data-ttu-id="8d5d6-123">Se l'errore si è verificato durante la replica, ricreare la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-123">If this occurred during replication, recreate the publication.</span></span> <span data-ttu-id="8d5d6-124">In caso contrario, eseguire un ripristino dal backup.</span><span class="sxs-lookup"><span data-stu-id="8d5d6-124">Otherwise, restore from backup.</span></span>  
  
  
