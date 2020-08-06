---
title: MSSQLSERVER_10003 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 10003 (Database Engine error)
ms.assetid: 9e2cb199-f077-4d88-8117-1b7550afc696
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8ea44fc9591602bfc8279924e10a1803d0d5a87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624250"
---
# <a name="mssqlserver_10003"></a><span data-ttu-id="36546-102">MSSQLSERVER_10003</span><span class="sxs-lookup"><span data-stu-id="36546-102">MSSQLSERVER_10003</span></span>
    
## <a name="details"></a><span data-ttu-id="36546-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="36546-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36546-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="36546-104">Product Name</span></span>|<span data-ttu-id="36546-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="36546-105">SQL Server</span></span>|  
|<span data-ttu-id="36546-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="36546-106">Event ID</span></span>|<span data-ttu-id="36546-107">10003</span><span class="sxs-lookup"><span data-stu-id="36546-107">10003</span></span>|  
|<span data-ttu-id="36546-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="36546-108">Event Source</span></span>|<span data-ttu-id="36546-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="36546-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="36546-110">Componente</span><span class="sxs-lookup"><span data-stu-id="36546-110">Component</span></span>|<span data-ttu-id="36546-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="36546-111">SQLEngine</span></span>|  
|<span data-ttu-id="36546-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="36546-112">Symbolic Name</span></span>|<span data-ttu-id="36546-113">HR_E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="36546-113">HR_E_OUTOFMEMORY</span></span>|  
|<span data-ttu-id="36546-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="36546-114">Message Text</span></span>|<span data-ttu-id="36546-115">Memoria insufficiente per il provider.</span><span class="sxs-lookup"><span data-stu-id="36546-115">The provider ran out of memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="36546-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="36546-116">Explanation</span></span>  
 <span data-ttu-id="36546-117">La condizione di memoria di sistema insufficiente ha causato l'esaurimento della memoria del provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="36546-117">Low system memory has caused the OLE DB provider to run out of memory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36546-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="36546-118">User Action</span></span>  
 <span data-ttu-id="36546-119">Riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36546-119">Restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="36546-120">Se l'operazione non è risolutiva, riavviare il computer.</span><span class="sxs-lookup"><span data-stu-id="36546-120">If that does not help, restart the computer.</span></span> <span data-ttu-id="36546-121">Se il problema persiste, raccogliere gli eventi di traccia OLE DB mediante [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] e fornire questi dati al Servizio Supporto Tecnico Clienti Microsoft per il provider OLE DB.</span><span class="sxs-lookup"><span data-stu-id="36546-121">If the problem persists, collect OLE DB trace events using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] and provide this data to product support for the OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36546-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36546-122">See Also</span></span>  
 <span data-ttu-id="36546-123">[Modelli e autorizzazioni di SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="36546-123">[SQL Server Profiler Templates and Permissions](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="36546-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="36546-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
