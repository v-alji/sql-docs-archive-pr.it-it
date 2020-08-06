---
title: MSSQL_ENG020598 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020598 error
ms.assetid: 1c3032f2-23d1-4ead-94ee-16ac4d75cd0c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8cef26001c353dea94ec9b658dfb38285231bc20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714191"
---
# <a name="mssql_eng020598"></a><span data-ttu-id="0161a-102">MSSQL_ENG020598</span><span class="sxs-lookup"><span data-stu-id="0161a-102">MSSQL_ENG020598</span></span>
    
## <a name="message-details"></a><span data-ttu-id="0161a-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="0161a-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0161a-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0161a-104">Product Name</span></span>|<span data-ttu-id="0161a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0161a-105">SQL Server</span></span>|  
|<span data-ttu-id="0161a-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0161a-106">Event ID</span></span>|<span data-ttu-id="0161a-107">20598</span><span class="sxs-lookup"><span data-stu-id="0161a-107">20598</span></span>|  
|<span data-ttu-id="0161a-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0161a-108">Event Source</span></span>|<span data-ttu-id="0161a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0161a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0161a-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0161a-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="0161a-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0161a-111">Symbolic Name</span></span>||  
|<span data-ttu-id="0161a-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0161a-112">Message Text</span></span>|<span data-ttu-id="0161a-113">Impossibile trovare la riga nel Sottoscrittore durante l'applicazione del comando replicato.</span><span class="sxs-lookup"><span data-stu-id="0161a-113">The row was not found at the Subscriber when applying the replicated command.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0161a-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0161a-114">Explanation</span></span>  
 <span data-ttu-id="0161a-115">Questo errore viene generato nella replica transazionale se l'agente di distribuzione tenta di aggiornare una riga nel Sottoscrittore mentre la riga è stata eliminata o la chiave primaria della riga è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="0161a-115">This error is raised in transactional replication if the Distribution Agent attempts to update a row at the Subscriber, but the row has been deleted or the primary key of the row has been changed.</span></span> <span data-ttu-id="0161a-116">Per impostazione predefinita, i Sottoscrittori di pubblicazioni transazionali devono essere considerati di sola lettura poiché le modifiche non vengono trasferite al server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0161a-116">By default, Subscribers to transactional publications should be treated as read-only, because changes are not propagated back to the Publisher.</span></span> <span data-ttu-id="0161a-117">Nella replica transazionale, gli utenti possono eseguire modifiche nel Sottoscrittore solo se utilizzano sottoscrizioni aggiornabili o la replica peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="0161a-117">For transactional replication, user changes should be made at the Subscriber only if updatable subscriptions or peer-to-peer replication is used.</span></span> <span data-ttu-id="0161a-118">Per informazioni sulle opzioni menzionate, vedere [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) e [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="0161a-118">For information about these options, see [Updatable Subscriptions for Transactional Replication](transactional/updatable-subscriptions-for-transactional-replication.md) and [Peer-to-Peer Transactional Replication](transactional/peer-to-peer-transactional-replication.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0161a-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0161a-119">User Action</span></span>  
 <span data-ttu-id="0161a-120">**Per risolvere il problema:**</span><span class="sxs-lookup"><span data-stu-id="0161a-120">**To resolve this problem:**</span></span>  
  
1.  <span data-ttu-id="0161a-121">Se si desidera che la replica continui mentre si identifica l'origine dell'errore, specificare il parametro **-SkipErrors 20598** per l'agente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0161a-121">If replication must continue while you identify the source of the error, specify the parameter **-SkipErrors 20598** for the Distribution Agent.</span></span> <span data-ttu-id="0161a-122">In questo modo l'agente ignorerà le modifiche che generano l'errore 20598 e consentirà la replica delle altre modifiche.</span><span class="sxs-lookup"><span data-stu-id="0161a-122">This allows the agent to skip changes that result in error 20598, while allowing other changes to be replicated.</span></span>  
  
2.  <span data-ttu-id="0161a-123">Identificare le righe eliminate o che presentano una chiave primaria diversa nel Sottoscrittore rispetto alle righe corrispondenti nel server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="0161a-123">Identify which rows at the Subscriber have been deleted or have a different primary key than the corresponding rows at the Publisher.</span></span> <span data-ttu-id="0161a-124">È possibile utilizzare la [tablediff Utility](../../tools/tablediff-utility.md) per determinare quali righe risultano diverse nei database di pubblicazione e di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="0161a-124">You can use the [tablediff Utility](../../tools/tablediff-utility.md) to determine which rows are different in the publication and subscription databases.</span></span> <span data-ttu-id="0161a-125">Per informazioni sull'uso di questa utilità con database di replica, vedere [Confrontare tabelle replicate al fine di individuare le differenze &#40;programmazione della replica&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span><span class="sxs-lookup"><span data-stu-id="0161a-125">For information about using this utility with replicated databases, see [Compare Replicated Tables for Differences &#40;Replication Programming&#41;](administration/compare-replicated-tables-for-differences-replication-programming.md).</span></span>  
  
3.  <span data-ttu-id="0161a-126">Correggere le righe nel Sottoscrittore utilizzando l'utilità **tablediff** o un altro metodo.</span><span class="sxs-lookup"><span data-stu-id="0161a-126">Correct the rows at the Subscriber using the **tablediff** utility or another method.</span></span>  
  
4.  <span data-ttu-id="0161a-127">(Facoltativo) Rimuovere il parametro **-SkipErrors** .</span><span class="sxs-lookup"><span data-stu-id="0161a-127">(Optional) Remove the **-SkipErrors** parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0161a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0161a-128">See Also</span></span>  
 [<span data-ttu-id="0161a-129">Guida di riferimento a errori ed eventi &#40;replica&#41;</span><span class="sxs-lookup"><span data-stu-id="0161a-129">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
