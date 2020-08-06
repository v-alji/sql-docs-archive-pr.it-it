---
title: MSSQLSERVER_1105 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1105 (Database Engine error)
ms.assetid: e7f4ad02-8c7f-4bb9-9781-2c86253f2138
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dea326fab7edd6a5c155c8f0182bffc044505eb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624247"
---
# <a name="mssqlserver_1105"></a><span data-ttu-id="1d8a6-102">MSSQLSERVER_1105</span><span class="sxs-lookup"><span data-stu-id="1d8a6-102">MSSQLSERVER_1105</span></span>
    
## <a name="details"></a><span data-ttu-id="1d8a6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1d8a6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d8a6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="1d8a6-104">Product Name</span></span>|<span data-ttu-id="1d8a6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1d8a6-105">SQL Server</span></span>|  
|<span data-ttu-id="1d8a6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="1d8a6-106">Event ID</span></span>|<span data-ttu-id="1d8a6-107">1105</span><span class="sxs-lookup"><span data-stu-id="1d8a6-107">1105</span></span>|  
|<span data-ttu-id="1d8a6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="1d8a6-108">Event Source</span></span>|<span data-ttu-id="1d8a6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1d8a6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1d8a6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1d8a6-110">Component</span></span>|<span data-ttu-id="1d8a6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1d8a6-111">SQLEngine</span></span>|  
|<span data-ttu-id="1d8a6-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="1d8a6-112">Symbolic Name</span></span>|<span data-ttu-id="1d8a6-113">NO_MORE_SPACE_IN_FG</span><span class="sxs-lookup"><span data-stu-id="1d8a6-113">NO_MORE_SPACE_IN_FG</span></span>|  
|<span data-ttu-id="1d8a6-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="1d8a6-114">Message Text</span></span>|<span data-ttu-id="1d8a6-115">Impossibile allocare spazio per l'oggetto '%.\*ls'%.\*ls nel database'%.\*ls'. Il filegroup '%.\*ls' è pieno.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-115">Could not allocate space for object '%.\*ls'%.\*ls in database '%.\*ls' because the '%.\*ls' filegroup is full.</span></span> <span data-ttu-id="1d8a6-116">Liberare spazio su disco eliminando i file non necessari, eliminando oggetti dal filegroup, aggiungendo file al filegroup oppure attivando l'aumento automatico delle dimensioni per i file esistenti nel filegroup.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-116">Create disk space by deleting unneeded files, dropping objects in the filegroup, adding additional files to the filegroup, or setting autogrowth on for existing files in the filegroup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1d8a6-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1d8a6-117">Explanation</span></span>  
 <span data-ttu-id="1d8a6-118">Nel filegroup indicato non vi è spazio disponibile su disco.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-118">No disk space is available in a filegroup.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1d8a6-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="1d8a6-119">User Action</span></span>  
 <span data-ttu-id="1d8a6-120">Eseguire le azioni seguenti per tentare di liberare spazio sufficiente nel filegroup:</span><span class="sxs-lookup"><span data-stu-id="1d8a6-120">The following actions may make space available in the filegroup:</span></span>  
  
-   <span data-ttu-id="1d8a6-121">Attivare l'aumento automatico delle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-121">Turn on autogrow.</span></span>  
  
-   <span data-ttu-id="1d8a6-122">Aggiungere altri file al gruppo di file.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-122">Add more files to the file group.</span></span>  
  
-   <span data-ttu-id="1d8a6-123">Liberare spazio su disco eliminando indici o tabelle che non sono più necessari.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-123">Free disk space by dropping index or tables that are no longer needed.</span></span>  
  
-   <span data-ttu-id="1d8a6-124">Per ulteriori informazioni, vedere "Risoluzione dei problemi relativi a spazio su disco insufficiente" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-124">For more information, see "Troubleshooting Insufficient Data Disk Space" in SQL Server Books Online.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1d8a6-125">Se un indice si trova in diversi file, `ALTER INDEX REORGANIZE` può restituire un errore 1105 quando uno dei file è pieno.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-125">When an index is located on several files, `ALTER INDEX REORGANIZE` can return error 1105 when one of the files is full.</span></span> <span data-ttu-id="1d8a6-126">Il processo di riorganizzazione viene bloccato quando il processo prova a spostare le righe nel file pieno.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-126">The reorganization process is blocked when the process tries to move rows to the full file.</span></span> <span data-ttu-id="1d8a6-127">Per risolvere questo problema relativo a tale limitazione, eseguire `ALTER INDEX REBUILD` anziché `ALTER INDEX REORGANIZE` o modificare il limite di aumento delle dimensioni dei file pieni.</span><span class="sxs-lookup"><span data-stu-id="1d8a6-127">To work around this limitation perform an `ALTER INDEX REBUILD` instead of `ALTER INDEX REORGANIZE` or increase the file growth limit of any files that are full.</span></span>  
  
  
