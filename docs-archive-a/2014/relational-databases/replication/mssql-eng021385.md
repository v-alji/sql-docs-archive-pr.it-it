---
title: MSSQL_ENG021385 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021385 error
ms.assetid: a2c0444f-d97b-4760-8905-3574791c2e26
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b73d3216f07cb44d750a37149634258648f1bd48
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714176"
---
# <a name="mssql_eng021385"></a><span data-ttu-id="e54a4-102">MSSQL_ENG021385</span><span class="sxs-lookup"><span data-stu-id="e54a4-102">MSSQL_ENG021385</span></span>
    
## <a name="message-details"></a><span data-ttu-id="e54a4-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="e54a4-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e54a4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e54a4-104">Product Name</span></span>|<span data-ttu-id="e54a4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e54a4-105">SQL Server</span></span>|  
|<span data-ttu-id="e54a4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e54a4-106">Event ID</span></span>|<span data-ttu-id="e54a4-107">21385</span><span class="sxs-lookup"><span data-stu-id="e54a4-107">21385</span></span>|  
|<span data-ttu-id="e54a4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e54a4-108">Event Source</span></span>|<span data-ttu-id="e54a4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e54a4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e54a4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e54a4-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="e54a4-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e54a4-111">Symbolic Name</span></span>||  
|<span data-ttu-id="e54a4-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e54a4-112">Message Text</span></span>|<span data-ttu-id="e54a4-113">Lo snapshot non è in grado di elaborare la pubblicazione '%s',</span><span class="sxs-lookup"><span data-stu-id="e54a4-113">Snapshot failed to process publication '%s'.</span></span> <span data-ttu-id="e54a4-114">probabilmente perché sono in corso attività di modifica dello schema o di aggiunta di nuovi articoli.</span><span class="sxs-lookup"><span data-stu-id="e54a4-114">Possibly due to active schema change activity or new articles being added.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e54a4-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e54a4-115">Explanation</span></span>  
 <span data-ttu-id="e54a4-116">Questo errore viene generato se l'agente snapshot viene eseguito quando il database di pubblicazione è sottoposto a modifiche, ad esempio l'aggiunta o l'eliminazione di articoli e l'esecuzione di modifiche dello schema negli oggetti pubblicati.</span><span class="sxs-lookup"><span data-stu-id="e54a4-116">This error is raised if the Snapshot Agent starts running when there are ongoing changes to the publication database, including adding or dropping articles and performing schema changes on published objects.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e54a4-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e54a4-117">User Action</span></span>  
 <span data-ttu-id="e54a4-118">Riavviare l'agente snapshot dopo che sono state apportate tutte le modifiche al database di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="e54a4-118">Restart the Snapshot Agent after changes to the publication database are complete.</span></span> <span data-ttu-id="e54a4-119">Per altre informazioni, vedere [Avviare e arrestare un agente di replica &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) e [Concetti di base relativi ai file eseguibili dell'agente di replica](concepts/replication-agent-executables-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="e54a4-119">For more information, see [Start and Stop a Replication Agent &#40;SQL Server Management Studio&#41;](agents/start-and-stop-a-replication-agent-sql-server-management-studio.md) and [Replication Agent Executables Concepts](concepts/replication-agent-executables-concepts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54a4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e54a4-120">See Also</span></span>  
 [<span data-ttu-id="e54a4-121">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="e54a4-121">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
