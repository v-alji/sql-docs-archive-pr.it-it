---
title: MSSQLSERVER_1462 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1462 (Database Engine error)
ms.assetid: 680e9c1c-a9d6-4765-b601-956d0a83324c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 704b847bde2d7b4da9da91b4b24bfe2b9e2afa07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636159"
---
# <a name="mssqlserver_1462"></a><span data-ttu-id="ca914-102">MSSQLSERVER_1462</span><span class="sxs-lookup"><span data-stu-id="ca914-102">MSSQLSERVER_1462</span></span>
    
## <a name="details"></a><span data-ttu-id="ca914-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="ca914-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca914-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="ca914-104">Product Name</span></span>|<span data-ttu-id="ca914-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ca914-105">SQL Server</span></span>|  
|<span data-ttu-id="ca914-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="ca914-106">Event ID</span></span>|<span data-ttu-id="ca914-107">1462</span><span class="sxs-lookup"><span data-stu-id="ca914-107">1462</span></span>|  
|<span data-ttu-id="ca914-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="ca914-108">Event Source</span></span>|<span data-ttu-id="ca914-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="ca914-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="ca914-110">Componente</span><span class="sxs-lookup"><span data-stu-id="ca914-110">Component</span></span>|<span data-ttu-id="ca914-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="ca914-111">SQLEngine</span></span>|  
|<span data-ttu-id="ca914-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="ca914-112">Symbolic Name</span></span>|<span data-ttu-id="ca914-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span><span class="sxs-lookup"><span data-stu-id="ca914-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span></span>|  
|<span data-ttu-id="ca914-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="ca914-114">Message Text</span></span>|<span data-ttu-id="ca914-115">Mirroring del database disabilitato a causa di un'operazione di rollforward non riuscita.</span><span class="sxs-lookup"><span data-stu-id="ca914-115">Database mirroring is disabled due to a failed redo operation.</span></span> <span data-ttu-id="ca914-116">Impossibile riprendere.</span><span class="sxs-lookup"><span data-stu-id="ca914-116">Unable to resume.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ca914-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="ca914-117">Explanation</span></span>  
 <span data-ttu-id="ca914-118">Il mirroring del database non è riuscito a eseguire un'operazione di rollforward di un record di log nel mirror.</span><span class="sxs-lookup"><span data-stu-id="ca914-118">Database mirroring failed to redo a log record on the mirror.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="ca914-119">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="ca914-119">Possible Causes</span></span>  
 <span data-ttu-id="ca914-120">La causa più probabile è che un'operazione di aggiunta file è stata completata nel database principale ma non è stata eseguita nel database mirror perché i nomi file o le strutture di directory del server principale e del server mirror sono diverse.</span><span class="sxs-lookup"><span data-stu-id="ca914-120">The most likely cause is that an add-file operation completed on the principal database but then failed on the mirror database because file names or directory structures differ on the principal server and mirror server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ca914-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="ca914-121">User Action</span></span>  
 <span data-ttu-id="ca914-122">Esaminare il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per individuare la causa dell'errore.</span><span class="sxs-lookup"><span data-stu-id="ca914-122">Look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the cause of this error.</span></span> <span data-ttu-id="ca914-123">Provare a eliminare la causa del problema e a riprendere il mirroring nel database.</span><span class="sxs-lookup"><span data-stu-id="ca914-123">Try to resolve the cause and resume mirroring on the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca914-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca914-124">See Also</span></span>  
 [<span data-ttu-id="ca914-125">Risolvere i problemi relativi alla configurazione del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ca914-125">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
