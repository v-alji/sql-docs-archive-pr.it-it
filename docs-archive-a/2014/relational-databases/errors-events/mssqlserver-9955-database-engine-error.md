---
title: MSSQLSERVER_9955 | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9955 (Database Engine error)
ms.assetid: 77f30570-7790-4747-b372-eac71c036e19
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56b9f9b4b7923f8973bd7167c3c1bf77e92300c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627729"
---
# <a name="mssqlserver_9955"></a><span data-ttu-id="f04d4-102">MSSQLSERVER_9955</span><span class="sxs-lookup"><span data-stu-id="f04d4-102">MSSQLSERVER_9955</span></span>
    
## <a name="details"></a><span data-ttu-id="f04d4-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f04d4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f04d4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f04d4-104">Product Name</span></span>|<span data-ttu-id="f04d4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f04d4-105">SQL Server</span></span>|  
|<span data-ttu-id="f04d4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f04d4-106">Event ID</span></span>|<span data-ttu-id="f04d4-107">9955</span><span class="sxs-lookup"><span data-stu-id="f04d4-107">9955</span></span>|  
|<span data-ttu-id="f04d4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f04d4-108">Event Source</span></span>|<span data-ttu-id="f04d4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f04d4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f04d4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f04d4-110">Component</span></span>|<span data-ttu-id="f04d4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f04d4-111">SQLEngine</span></span>|  
|<span data-ttu-id="f04d4-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f04d4-112">Symbolic Name</span></span>|<span data-ttu-id="f04d4-113">FTXT2_MSSEARCHACCESSDENY</span><span class="sxs-lookup"><span data-stu-id="f04d4-113">FTXT2_MSSEARCHACCESSDENY</span></span>|  
|<span data-ttu-id="f04d4-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f04d4-114">Message Text</span></span>|<span data-ttu-id="f04d4-115">Impossibile creare la named pipe '%ls' per comunicare con il daemon di filtri full-text (errore di Windows: %d).</span><span class="sxs-lookup"><span data-stu-id="f04d4-115">SQL Server failed to create named pipe '%ls' to communicate with the full-text filter daemon (Windows error: %d).</span></span> <span data-ttu-id="f04d4-116">Una named pipe esiste già per il processo host del daemon di filtri, il sistema non dispone di risorse sufficienti oppure la ricerca del numero di identificazione di sicurezza (SID) per il gruppo account del daemon di filtri non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f04d4-116">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span> <span data-ttu-id="f04d4-117">Per risolvere il problema, interrompere eventuali processi del daemon di filtri full-text in esecuzione e, se necessario, riconfigurare l'account di servizio dell'utilità di avvio del daemon full-text.</span><span class="sxs-lookup"><span data-stu-id="f04d4-117">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon launcher service account.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f04d4-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f04d4-118">Explanation</span></span>  
 <span data-ttu-id="f04d4-119">Questo messaggio viene visualizzato quando in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è possibile creare una named pipe per comunicare con il daemon di filtri full-text.</span><span class="sxs-lookup"><span data-stu-id="f04d4-119">This message occurs because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failed to create a named pipe to communicate with the full-text filter daemon.</span></span> <span data-ttu-id="f04d4-120">Una named pipe esiste già per il processo host del daemon di filtri, il sistema non dispone di risorse sufficienti oppure la ricerca del numero di identificazione di sicurezza (SID) per il gruppo account del daemon di filtri non è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f04d4-120">Either a named pipe already exists for a filter daemon host process, the system is low on resources, or the security identification number (SID) lookup for the filter daemon account group failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f04d4-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f04d4-121">User Action</span></span>  
 <span data-ttu-id="f04d4-122">Per risolvere il problema, interrompere eventuali processi del daemon di filtri full-text in esecuzione e, se necessario, riconfigurare l'account host del daemon full-text utilizzando Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f04d4-122">To resolve this error, terminate any running full-text filter daemon processes, and if necessary reconfigure the full-text daemon host account by using the SQL Server Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04d4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f04d4-123">See Also</span></span>  
 <span data-ttu-id="f04d4-124">[Gestione configurazione SQL Server](../sql-server-configuration-manager.md) </span><span class="sxs-lookup"><span data-stu-id="f04d4-124">[SQL Server Configuration Manager](../sql-server-configuration-manager.md) </span></span>  
 <span data-ttu-id="f04d4-125">[Impostare l'account del servizio per l'utilità di avvio del daemon filtri full-text](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span><span class="sxs-lookup"><span data-stu-id="f04d4-125">[Set the Service Account for the Full-text Filter Daemon Launcher](../search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md) </span></span>  
 [<span data-ttu-id="f04d4-126">Ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="f04d4-126">Full-Text Search</span></span>](../search/full-text-search.md)  
  
  
