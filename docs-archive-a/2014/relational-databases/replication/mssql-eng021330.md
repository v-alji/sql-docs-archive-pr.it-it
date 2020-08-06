---
title: MSSQL_ENG021330 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG021330 error
ms.assetid: e2bb2e21-62a7-4689-b68b-bdfba3fdd985
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4338756a641b23bfc6f52da6b3de296bb6415756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714183"
---
# <a name="mssql_eng021330"></a><span data-ttu-id="00acd-102">MSSQL_ENG021330</span><span class="sxs-lookup"><span data-stu-id="00acd-102">MSSQL_ENG021330</span></span>
    
## <a name="message-details"></a><span data-ttu-id="00acd-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="00acd-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="00acd-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="00acd-104">Product Name</span></span>|<span data-ttu-id="00acd-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="00acd-105">SQL Server</span></span>|  
|<span data-ttu-id="00acd-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="00acd-106">Event ID</span></span>|<span data-ttu-id="00acd-107">21330</span><span class="sxs-lookup"><span data-stu-id="00acd-107">21330</span></span>|  
|<span data-ttu-id="00acd-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="00acd-108">Event Source</span></span>|<span data-ttu-id="00acd-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="00acd-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="00acd-110">Componente</span><span class="sxs-lookup"><span data-stu-id="00acd-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="00acd-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="00acd-111">Symbolic Name</span></span>||  
|<span data-ttu-id="00acd-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="00acd-112">Message Text</span></span>|<span data-ttu-id="00acd-113">Impossibile creare una sottodirectory nella directory di lavoro della replica.(%1!)</span><span class="sxs-lookup"><span data-stu-id="00acd-113">Failed to create a sub-directory under the replication working directory.(%ls)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="00acd-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="00acd-114">Explanation</span></span>  
 <span data-ttu-id="00acd-115">Questo errore si può verificare quando una sottoscrizione viene inizializzata manualmente e si riscontra un problema nella creazione della directory di archiviazione degli script di replica.</span><span class="sxs-lookup"><span data-stu-id="00acd-115">This error can occur when a subscription is initialized manually, and there is a problem creating the directory in which replication scripts are stored.</span></span> <span data-ttu-id="00acd-116">L'errore può essere causato da un problema relativo alle autorizzazioni: quando una sottoscrizione viene inizializzata senza utilizzare uno snapshot, l'account con cui il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguito nel server di pubblicazione deve disporre di autorizzazioni di scrittura per la cartella snapshot nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="00acd-116">The error can be caused by a permissions issue: when a subscription is initialized without using a snapshot, the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher must have write permissions on the snapshot folder at the Distributor.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="00acd-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="00acd-117">User Action</span></span>  
 <span data-ttu-id="00acd-118">Verificare che sia stato specificato il percorso corretto della cartella snapshot e che l'account con cui il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguito nel server di pubblicazione disponga di autorizzazioni sufficienti.</span><span class="sxs-lookup"><span data-stu-id="00acd-118">Ensure that the correct path has been specified for the snapshot folder and that the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service runs at the Publisher has sufficient permissions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00acd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00acd-119">See Also</span></span>  
 <span data-ttu-id="00acd-120">[Specificare la posizione predefinita degli snapshot](snapshot-options.md#snapshot-folder-locations) </span><span class="sxs-lookup"><span data-stu-id="00acd-120">[Specify the Default Snapshot Location](snapshot-options.md#snapshot-folder-locations) </span></span>  
 <span data-ttu-id="00acd-121">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="00acd-121">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="00acd-122">Inizializzare una sottoscrizione transazionale senza uno snapshot</span><span class="sxs-lookup"><span data-stu-id="00acd-122">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
