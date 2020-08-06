---
title: MSSQLSERVER_1203 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1203 (Database Engine error)
ms.assetid: 33a35f00-98c8-46c6-b432-544b326b6117
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3cea816a60ccd1b90d849194766edebd2d64d0b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635649"
---
# <a name="mssqlserver_1203"></a><span data-ttu-id="db358-102">MSSQLSERVER_1203</span><span class="sxs-lookup"><span data-stu-id="db358-102">MSSQLSERVER_1203</span></span>
    
## <a name="details"></a><span data-ttu-id="db358-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="db358-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db358-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="db358-104">Product Name</span></span>|<span data-ttu-id="db358-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="db358-105">SQL Server</span></span>|  
|<span data-ttu-id="db358-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="db358-106">Event ID</span></span>|<span data-ttu-id="db358-107">1203</span><span class="sxs-lookup"><span data-stu-id="db358-107">1203</span></span>|  
|<span data-ttu-id="db358-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="db358-108">Event Source</span></span>|<span data-ttu-id="db358-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="db358-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="db358-110">Componente</span><span class="sxs-lookup"><span data-stu-id="db358-110">Component</span></span>|<span data-ttu-id="db358-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="db358-111">SQLEngine</span></span>|  
|<span data-ttu-id="db358-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="db358-112">Symbolic Name</span></span>|<span data-ttu-id="db358-113">LK_NOT</span><span class="sxs-lookup"><span data-stu-id="db358-113">LK_NOT</span></span>|  
|<span data-ttu-id="db358-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="db358-114">Message Text</span></span>|<span data-ttu-id="db358-115">Il processo con ID %d ha tentato di sbloccare una risorsa di cui non è proprietario: %.\*ls.</span><span class="sxs-lookup"><span data-stu-id="db358-115">Process ID %d attempted to unlock a resource it does not own: %.\*ls.</span></span> <span data-ttu-id="db358-116">Ripetere la transazione. L'errore potrebbe essere dovuto a una condizione basata sul tempo.</span><span class="sxs-lookup"><span data-stu-id="db358-116">Retry the transaction, because this error may be caused by a timing condition.</span></span> <span data-ttu-id="db358-117">Se il problema persiste, contattare l'amministratore del database.</span><span class="sxs-lookup"><span data-stu-id="db358-117">If the problem persists, contact the database administrator.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="db358-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="db358-118">Explanation</span></span>  
 <span data-ttu-id="db358-119">Questo errore si verifica quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è impegnato in attività diverse dalle normali operazioni di pulizia dei dati temporanei post-elaborazione e tenta di sbloccare una pagina specifica che in realtà è già sbloccata.</span><span class="sxs-lookup"><span data-stu-id="db358-119">This error occurs when [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is engaged in some activity other than ordinary post-processing cleanup and it finds that a particular page that it is trying to unlock is already unlocked.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="db358-120">Possibili cause</span><span class="sxs-lookup"><span data-stu-id="db358-120">Possible Causes</span></span>  
 <span data-ttu-id="db358-121">La causa sottostante di questo errore può essere correlata a problemi strutturali nel database interessato.</span><span class="sxs-lookup"><span data-stu-id="db358-121">The underlying cause of this error may be related to structural problems within the affected database.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="db358-122">gestisce l'acquisizione e il rilascio di pagine per mantenere il controllo della concorrenza nell'ambiente multiutente.</span><span class="sxs-lookup"><span data-stu-id="db358-122">manages the acquisition and release of pages to maintain concurrency control in the multiuser environment.</span></span> <span data-ttu-id="db358-123">Per il mantenimento di questo meccanismo vengono utilizzate diverse strutture di blocco interne che identificano la pagina e il tipo di blocco presente.</span><span class="sxs-lookup"><span data-stu-id="db358-123">This mechanism is maintained by using various internal lock structures that identify the page and the type of lock present.</span></span> <span data-ttu-id="db358-124">I blocchi vengono acquisiti per consentire l'elaborazione delle pagine interessate e rilasciati al termine dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="db358-124">Locks are acquired for processing of affected pages and released when the processing is finished.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="db358-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="db358-125">User Action</span></span>  
 <span data-ttu-id="db358-126">Eseguire DBCC CHECKDB sul database cui appartiene l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="db358-126">Execute DBCC CHECKDB against the database in which the object belongs.</span></span> <span data-ttu-id="db358-127">Se DBCC CHECKDB non restituisce errori, provare a ristabilire la connessione e a eseguire il comando.</span><span class="sxs-lookup"><span data-stu-id="db358-127">If DBCC CHECKDB reports no errors, try to reestablish the connection and execute the command.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="db358-128">Se l'esecuzione di DBCC CHECKDB con una delle clausole REPAIR non consente di correggere il problema relativo all'indice oppure non si è certi dell'effetto prodotto sui dati dall'esecuzione di DBCC CHECKDB con una clausola REPAIR, contattare il personale del supporto tecnico.</span><span class="sxs-lookup"><span data-stu-id="db358-128">If you are executing DBCC CHECKDB with one of the REPAIR clauses does not correct the index problem, or if you are not sure what effect DBCC CHECKDB with a REPAIR clause has on your data, contact your primary support provider.</span></span>  
  
  
