---
title: MSSQLSERVER_18752 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 18752 (Database Engine error)
ms.assetid: 234c58d8-7a1e-4b07-a64b-32a311527980
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a463e4019875f4a233ae2920f32bc2252376a41c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627783"
---
# <a name="mssqlserver_18752"></a><span data-ttu-id="241f1-102">MSSQLSERVER_18752</span><span class="sxs-lookup"><span data-stu-id="241f1-102">MSSQLSERVER_18752</span></span>
    
## <a name="details"></a><span data-ttu-id="241f1-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="241f1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="241f1-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="241f1-104">Product Name</span></span>|<span data-ttu-id="241f1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="241f1-105">SQL Server</span></span>|  
|<span data-ttu-id="241f1-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="241f1-106">Event ID</span></span>|<span data-ttu-id="241f1-107">18752</span><span class="sxs-lookup"><span data-stu-id="241f1-107">18752</span></span>|  
|<span data-ttu-id="241f1-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="241f1-108">Event Source</span></span>|<span data-ttu-id="241f1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="241f1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="241f1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="241f1-110">Component</span></span>|<span data-ttu-id="241f1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="241f1-111">SQLEngine</span></span>|  
|<span data-ttu-id="241f1-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="241f1-112">Symbolic Name</span></span>|<span data-ttu-id="241f1-113">REPL_INUSE</span><span class="sxs-lookup"><span data-stu-id="241f1-113">REPL_INUSE</span></span>|  
|<span data-ttu-id="241f1-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="241f1-114">Message Text</span></span>|<span data-ttu-id="241f1-115">A un database può connettersi un solo agente di lettura log o una sola procedura correlata ai log (sp_repldone, sp_replcmds e sp_replshowcmds) alla volta.</span><span class="sxs-lookup"><span data-stu-id="241f1-115">Only one Log Reader Agent or log-related procedure (sp_repldone, sp_replcmds, and sp_replshowcmds) can connect to a database at a time.</span></span> <span data-ttu-id="241f1-116">Se è stata eseguita una procedura correlata ai log, eliminare la connessione utilizzata per eseguire la procedura oppure eseguire sp_replflush tramite tale connessione prima di avviare l'agente di lettura log o di eseguire un'altra procedura relativa ai log.</span><span class="sxs-lookup"><span data-stu-id="241f1-116">If you executed a log-related procedure, drop the connection over which the procedure was executed or execute sp_replflush over that connection before starting the Log Reader Agent or executing another log-related procedure.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="241f1-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="241f1-117">Explanation</span></span>  
 <span data-ttu-id="241f1-118">A un database può connettersi solo un agente di lettura log o una sola procedura correlata ai log alla volta.</span><span class="sxs-lookup"><span data-stu-id="241f1-118">Only one Log Reader agent or log-related procedure can connect to a database at a time.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="241f1-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="241f1-119">User Action</span></span>  
 <span data-ttu-id="241f1-120">Verificare che non sia in esecuzione alcun altro agente di lettura log per lo stesso database di pubblicazione e che in nessuna connessione attiva sia stata eseguita in precedenza sp_replcmds, sp_repltrans o sp_repldone senza la successiva esecuzione di sp_replflush o senza disconnessione.</span><span class="sxs-lookup"><span data-stu-id="241f1-120">Make sure no other logreader is running for the same publishing database, and no other active connection had previously run sp_replcmds/sp_repltrans/sp_repldone without running sp_replflush afterwards or disconnecting.</span></span>  
  
  
