---
title: MSSQLSERVER_17132 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17132 (Database Engine error)
ms.assetid: d1d198bd-6730-4394-bd5f-28f320c01a38
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 609b9cea138db15cefd002f494620b5a1da7b208
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715352"
---
# <a name="mssqlserver_17132"></a><span data-ttu-id="e9ad3-102">MSSQLSERVER_17132</span><span class="sxs-lookup"><span data-stu-id="e9ad3-102">MSSQLSERVER_17132</span></span>
    
## <a name="details"></a><span data-ttu-id="e9ad3-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e9ad3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e9ad3-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e9ad3-104">Product Name</span></span>|<span data-ttu-id="e9ad3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9ad3-105">SQL Server</span></span>|  
|<span data-ttu-id="e9ad3-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e9ad3-106">Event ID</span></span>|<span data-ttu-id="e9ad3-107">17132</span><span class="sxs-lookup"><span data-stu-id="e9ad3-107">17132</span></span>|  
|<span data-ttu-id="e9ad3-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e9ad3-108">Event Source</span></span>|<span data-ttu-id="e9ad3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e9ad3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e9ad3-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e9ad3-110">Component</span></span>|<span data-ttu-id="e9ad3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e9ad3-111">SQLEngine</span></span>|  
|<span data-ttu-id="e9ad3-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e9ad3-112">Symbolic Name</span></span>|<span data-ttu-id="e9ad3-113">INIT_NODESSPACE</span><span class="sxs-lookup"><span data-stu-id="e9ad3-113">INIT_NODESSPACE</span></span>|  
|<span data-ttu-id="e9ad3-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e9ad3-114">Message Text</span></span>|<span data-ttu-id="e9ad3-115">Impossibile avviare il server. Memoria insufficiente per il descrittore.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-115">Server startup failed due to insufficient memory for descriptor.</span></span> <span data-ttu-id="e9ad3-116">Ridurre il carico di memoria non essenziale o aumentare la memoria del sistema.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-116">Reduce non-essential memory load or increase system memory.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e9ad3-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e9ad3-117">Explanation</span></span>  
 <span data-ttu-id="e9ad3-118">Impossibile allocare memoria sufficiente per archiviare il descrittore interno del server.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-118">Failed to allocate enough memory to store server internal descriptor.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e9ad3-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e9ad3-119">User Action</span></span>  
 <span data-ttu-id="e9ad3-120">Aggiungere una quantità maggiore di memoria al computer.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-120">Add more memory to the machine.</span></span> <span data-ttu-id="e9ad3-121">Potrebbe essere utile eseguire alcuni passaggi generici per la risoluzione dei problemi relativi alla memoria.</span><span class="sxs-lookup"><span data-stu-id="e9ad3-121">Generic memory troubleshooting steps may be useful.</span></span>  
  
  
