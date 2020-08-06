---
title: MSSQLSERVER_8966 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8966 (Database Engine error)
ms.assetid: 6b1150fd-9dfd-4df9-8f08-8eca237667db
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d3a12d5d0732ba8694db3d4c7dcae1eac59d28b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638413"
---
# <a name="mssqlserver_8966"></a><span data-ttu-id="657cb-102">MSSQLSERVER_8966</span><span class="sxs-lookup"><span data-stu-id="657cb-102">MSSQLSERVER_8966</span></span>
    
## <a name="details"></a><span data-ttu-id="657cb-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="657cb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="657cb-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="657cb-104">Product Name</span></span>|<span data-ttu-id="657cb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="657cb-105">SQL Server</span></span>|  
|<span data-ttu-id="657cb-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="657cb-106">Event ID</span></span>|<span data-ttu-id="657cb-107">8966</span><span class="sxs-lookup"><span data-stu-id="657cb-107">8966</span></span>|  
|<span data-ttu-id="657cb-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="657cb-108">Event Source</span></span>|<span data-ttu-id="657cb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="657cb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="657cb-110">Componente</span><span class="sxs-lookup"><span data-stu-id="657cb-110">Component</span></span>|<span data-ttu-id="657cb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="657cb-111">SQLEngine</span></span>|  
|<span data-ttu-id="657cb-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="657cb-112">Symbolic Name</span></span>|<span data-ttu-id="657cb-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span><span class="sxs-lookup"><span data-stu-id="657cb-113">DBCC3_FAILED_TO_READ_AND_LATCH_PAGE</span></span>|  
|<span data-ttu-id="657cb-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="657cb-114">Message Text</span></span>|<span data-ttu-id="657cb-115">Impostare leggere e impostare un latch nella pagina P_ID con tipo di latch TYPE.</span><span class="sxs-lookup"><span data-stu-id="657cb-115">Unable to read and latch page P_ID with latch type TYPE.</span></span> <span data-ttu-id="657cb-116">Impossibile eseguire OPERATION.</span><span class="sxs-lookup"><span data-stu-id="657cb-116">OPERATION failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="657cb-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="657cb-117">Explanation</span></span>  
 <span data-ttu-id="657cb-118">L'operazione di lettura della pagina non è stata eseguita oppure non è stato possibile impostare un latch in una pagina PFS o GAM.</span><span class="sxs-lookup"><span data-stu-id="657cb-118">The page read failed or a latch could not be taken on a PFS or GAM page.</span></span> <span data-ttu-id="657cb-119">È possibile che nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] siano segnalati timeout del latch o altri messaggi associati.</span><span class="sxs-lookup"><span data-stu-id="657cb-119">There may be latch time-out or other accompanying messages in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="657cb-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="657cb-120">User Action</span></span>  
 <span data-ttu-id="657cb-121">Controllare il log degli errori di SQL Server per esaminare i messaggi contenuti e risolvere gli errori.</span><span class="sxs-lookup"><span data-stu-id="657cb-121">Review the SQL error log for accompanying messages and resolve these errors.</span></span>  
  
  
