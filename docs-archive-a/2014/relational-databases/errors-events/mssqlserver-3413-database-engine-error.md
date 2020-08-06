---
title: MSSQLSERVER_3413 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3413 (Database Engine error)
ms.assetid: 3fa07637-ba93-4633-aaf2-ade7d18bc487
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a5d59ea61cff7051c3e1163a463c29443c553923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636113"
---
# <a name="mssqlserver_3413"></a><span data-ttu-id="beec1-102">MSSQLSERVER_3413</span><span class="sxs-lookup"><span data-stu-id="beec1-102">MSSQLSERVER_3413</span></span>
    
## <a name="details"></a><span data-ttu-id="beec1-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="beec1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="beec1-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="beec1-104">Product Name</span></span>|<span data-ttu-id="beec1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="beec1-105">SQL Server</span></span>|  
|<span data-ttu-id="beec1-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="beec1-106">Event ID</span></span>|<span data-ttu-id="beec1-107">3413</span><span class="sxs-lookup"><span data-stu-id="beec1-107">3413</span></span>|  
|<span data-ttu-id="beec1-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="beec1-108">Event Source</span></span>|<span data-ttu-id="beec1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="beec1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="beec1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="beec1-110">Component</span></span>|<span data-ttu-id="beec1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="beec1-111">SQLEngine</span></span>|  
|<span data-ttu-id="beec1-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="beec1-112">Symbolic Name</span></span>|<span data-ttu-id="beec1-113">MARKDB</span><span class="sxs-lookup"><span data-stu-id="beec1-113">MARKDB</span></span>|  
|<span data-ttu-id="beec1-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="beec1-114">Message Text</span></span>|<span data-ttu-id="beec1-115">ID di database %d.</span><span class="sxs-lookup"><span data-stu-id="beec1-115">Database ID %d.</span></span> <span data-ttu-id="beec1-116">Impossibile contrassegnare il database come sospetto.</span><span class="sxs-lookup"><span data-stu-id="beec1-116">Could not mark database as suspect.</span></span> <span data-ttu-id="beec1-117">Analisi Getnext per NC su sys.databases.database_id non riuscita.</span><span class="sxs-lookup"><span data-stu-id="beec1-117">Getnext NC scan on sys.databases.database_id failed.</span></span> <span data-ttu-id="beec1-118">Per identificare la causa e correggere gli eventuali problemi associati, fare riferimento agli errori precedenti nel log degli errori.</span><span class="sxs-lookup"><span data-stu-id="beec1-118">Refer to previous errors in the error log to identify the cause and correct any associated problems.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="beec1-119">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="beec1-119">Explanation</span></span>  
 <span data-ttu-id="beec1-120">Si è verificato un errore imprevisto durante il tentativo di contrassegnare un database utente come SUSPECT nel catalogo.</span><span class="sxs-lookup"><span data-stu-id="beec1-120">There was an unexpected failure while trying to mark a user database as SUSPECT in the catalog.</span></span> <span data-ttu-id="beec1-121">Lo stato SUSPECT non sarà persistente.</span><span class="sxs-lookup"><span data-stu-id="beec1-121">The SUSPECT state will not be persisted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="beec1-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="beec1-122">User Action</span></span>  
 <span data-ttu-id="beec1-123">Vedere gli errori precedenti e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="beec1-123">See previous errors and correct the problem.</span></span>  
  
  
