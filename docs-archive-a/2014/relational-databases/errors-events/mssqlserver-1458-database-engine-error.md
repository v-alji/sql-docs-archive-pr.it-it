---
title: MSSQLSERVER_1458 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1458 (Database Engine error)
ms.assetid: adc78c59-a6f2-432b-9a07-fdd1dc2b9026
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: efa45177a92402b25099be5bb3e3dcc91a5fa6d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636162"
---
# <a name="mssqlserver_1458"></a><span data-ttu-id="3823e-102">MSSQLSERVER_1458</span><span class="sxs-lookup"><span data-stu-id="3823e-102">MSSQLSERVER_1458</span></span>
    
## <a name="details"></a><span data-ttu-id="3823e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3823e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3823e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3823e-104">Product Name</span></span>|<span data-ttu-id="3823e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3823e-105">SQL Server</span></span>|  
|<span data-ttu-id="3823e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="3823e-106">Event ID</span></span>|<span data-ttu-id="3823e-107">1458</span><span class="sxs-lookup"><span data-stu-id="3823e-107">1458</span></span>|  
|<span data-ttu-id="3823e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3823e-108">Event Source</span></span>|<span data-ttu-id="3823e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3823e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3823e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3823e-110">Component</span></span>|<span data-ttu-id="3823e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3823e-111">SQLEngine</span></span>|  
|<span data-ttu-id="3823e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3823e-112">Symbolic Name</span></span>|<span data-ttu-id="3823e-113">DBM_FAILREDO_ON_PRIMARY</span><span class="sxs-lookup"><span data-stu-id="3823e-113">DBM_FAILREDO_ON_PRIMARY</span></span>|  
|<span data-ttu-id="3823e-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3823e-114">Message Text</span></span>|<span data-ttu-id="3823e-115">La copia principale del database '%.\*ls' ha rilevato l'errore % d, con stato% d e gravità% d.</span><span class="sxs-lookup"><span data-stu-id="3823e-115">The principal copy of the '%.\*ls' database encountered error %d, status %d, severity %d.</span></span> <span data-ttu-id="3823e-116">Il mirroring del database è stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="3823e-116">Database mirroring has been suspended.</span></span> <span data-ttu-id="3823e-117">Risolvere il problema e riprendere il mirroring.</span><span class="sxs-lookup"><span data-stu-id="3823e-117">Try to resolve the error condition, and resume mirroring.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3823e-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3823e-118">Explanation</span></span>  
 <span data-ttu-id="3823e-119">Il messaggio indica che il database principale ha rilevato un errore che ha causato la sospensione del mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="3823e-119">This messages indicates that the principal database encountered an error that caused database mirroring to be suspended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3823e-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3823e-120">User Action</span></span>  
 <span data-ttu-id="3823e-121">Nella maggior parte dei casi per la risoluzione di questo errore non è richiesto l'intervento dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3823e-121">Most cases of this error are self correcting.</span></span> <span data-ttu-id="3823e-122">Se il problema persiste, è in genere sufficiente riavviare l'istanza del database o del server per correggerlo.</span><span class="sxs-lookup"><span data-stu-id="3823e-122">If the problem persists, restarting the database or server instance typically corrects the problem.</span></span> <span data-ttu-id="3823e-123">Per ulteriori informazioni, ricercare nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di ogni partner l'errore associato che ha preceduto la visualizzazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="3823e-123">For more information, look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on each partner for the associated error that preceded this message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3823e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3823e-124">See Also</span></span>  
 [<span data-ttu-id="3823e-125">Monitoraggio del mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3823e-125">Monitoring Database Mirroring &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  
