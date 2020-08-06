---
title: MSSQLSERVER_9692 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9692 (Database Engine error)
ms.assetid: 02399d6e-ab5e-4f30-8a3e-2bb1e8c135b5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b6ba95771aafffa5a322ffa1b7443419936addd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627740"
---
# <a name="mssqlserver_9692"></a><span data-ttu-id="f3625-102">MSSQLSERVER_9692</span><span class="sxs-lookup"><span data-stu-id="f3625-102">MSSQLSERVER_9692</span></span>
    
## <a name="details"></a><span data-ttu-id="f3625-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f3625-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3625-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f3625-104">Product Name</span></span>|<span data-ttu-id="f3625-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f3625-105">SQL Server</span></span>|  
|<span data-ttu-id="f3625-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f3625-106">Event ID</span></span>|<span data-ttu-id="f3625-107">9692</span><span class="sxs-lookup"><span data-stu-id="f3625-107">9692</span></span>|  
|<span data-ttu-id="f3625-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f3625-108">Event Source</span></span>|<span data-ttu-id="f3625-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f3625-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f3625-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f3625-110">Component</span></span>|<span data-ttu-id="f3625-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f3625-111">SQLEngine</span></span>|  
|<span data-ttu-id="f3625-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f3625-112">Symbolic Name</span></span>|<span data-ttu-id="f3625-113">SB2_CANT_LISTEN_PORT_IN_USE</span><span class="sxs-lookup"><span data-stu-id="f3625-113">SB2_CANT_LISTEN_PORT_IN_USE</span></span>|  
|<span data-ttu-id="f3625-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f3625-114">Message Text</span></span>|<span data-ttu-id="f3625-115">Il trasporto di protocollo %S_MSG non può restare in attesa sulla porta %d perché è in uso da un altro processo.</span><span class="sxs-lookup"><span data-stu-id="f3625-115">The %S_MSG protocol transport cannot listen on port %d because it is in use by another process.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f3625-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f3625-116">Explanation</span></span>  
 <span data-ttu-id="f3625-117">Un altro programma in esecuzione nel computer sta utilizzando la porta TCP indicata.</span><span class="sxs-lookup"><span data-stu-id="f3625-117">Another program on the computer is using the TCP port indicated.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f3625-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f3625-118">User Action</span></span>  
 <span data-ttu-id="f3625-119">Eseguire `netstat -aon` per determinare quale programma sta utilizzando la porta.</span><span class="sxs-lookup"><span data-stu-id="f3625-119">Run `netstat -aon` to determine what program is using the port.</span></span> <span data-ttu-id="f3625-120">Disabilitare l'applicazione oppure specificare una porta diversa per Service Broker.</span><span class="sxs-lookup"><span data-stu-id="f3625-120">Disable that application or specify a different port for Service Broker.</span></span>  
  
  
