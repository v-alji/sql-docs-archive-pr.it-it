---
title: MSSQLSERVER_825 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 825 (Database Engine error)
ms.assetid: f69f8214-5af1-4769-878b-117ad6eaff52
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3b17dfac371ad3c805fdbb0b5d3269fc451dd9d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627759"
---
# <a name="mssqlserver_825"></a><span data-ttu-id="0c12c-102">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="0c12c-102">MSSQLSERVER_825</span></span>
    
## <a name="details"></a><span data-ttu-id="0c12c-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0c12c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c12c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0c12c-104">Product Name</span></span>|<span data-ttu-id="0c12c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0c12c-105">SQL Server</span></span>|  
|<span data-ttu-id="0c12c-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0c12c-106">Event ID</span></span>|<span data-ttu-id="0c12c-107">825</span><span class="sxs-lookup"><span data-stu-id="0c12c-107">825</span></span>|  
|<span data-ttu-id="0c12c-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0c12c-108">Event Source</span></span>|<span data-ttu-id="0c12c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0c12c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0c12c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0c12c-110">Component</span></span>|<span data-ttu-id="0c12c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0c12c-111">SQLEngine</span></span>|  
|<span data-ttu-id="0c12c-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0c12c-112">Symbolic Name</span></span>|<span data-ttu-id="0c12c-113">B_RETRYWORKED</span><span class="sxs-lookup"><span data-stu-id="0c12c-113">B_RETRYWORKED</span></span>|  
|<span data-ttu-id="0c12c-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0c12c-114">Message Text</span></span>|<span data-ttu-id="0c12c-115">Operazione di lettura del file '%ls', offset %#016I64x, riuscita dopo %d tentativo/i con errore: %ls.</span><span class="sxs-lookup"><span data-stu-id="0c12c-115">A read of the file '%ls' at offset %#016I64x succeeded after failing %d time(s) with error: %ls.</span></span> <span data-ttu-id="0c12c-116">Per informazioni più dettagliate, vedere i messaggi aggiuntivi nel log degli errori di SQL Server e nel registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="0c12c-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="0c12c-117">Questa condizione di errore può costituire un rischio per l'integrità del database e deve essere risolta.</span><span class="sxs-lookup"><span data-stu-id="0c12c-117">This error condition threatens database integrity and must be corrected.</span></span> <span data-ttu-id="0c12c-118">Eseguire un controllo di consistenza completo del database (DBCC CHECKDB).</span><span class="sxs-lookup"><span data-stu-id="0c12c-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="0c12c-119">L'errore può essere causato da molti fattori. Per ulteriori informazioni, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c12c-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0c12c-120">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0c12c-120">Explanation</span></span>  
 <span data-ttu-id="0c12c-121">Questo messaggio segnala che è stato necessario eseguire nuovamente l'operazione di lettura almeno una volta e indica un problema grave relativo ai componenti hardware del disco.</span><span class="sxs-lookup"><span data-stu-id="0c12c-121">This message indicates that the read operation had to be reissued at least one time, and indicates a major problem with the disk hardware.</span></span> <span data-ttu-id="0c12c-122">Non indica attualmente un problema relativo a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], tuttavia, se irrisolto, il problema relativo al disco potrebbe causare perdite di dati o il danneggiamento del database.</span><span class="sxs-lookup"><span data-stu-id="0c12c-122">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem, but the disk problem could cause data loss or database corruption if it is not resolved.</span></span> <span data-ttu-id="0c12c-123">Il log degli eventi di sistema potrebbe includere eventi correlati che consentono di diagnosticare il problema.</span><span class="sxs-lookup"><span data-stu-id="0c12c-123">The system event log may contain related events that help to diagnose the problem.</span></span> <span data-ttu-id="0c12c-124">Per altre informazioni sugli errori di I/O, vedere il capitolo 2 della pagina relativa alle [nozioni fondamentali sull'I/O in Microsoft SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="0c12c-124">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0c12c-125">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0c12c-125">User Action</span></span>  
 <span data-ttu-id="0c12c-126">Le azioni seguenti possono contribuire a identificare e risolvere il problema sottostante:</span><span class="sxs-lookup"><span data-stu-id="0c12c-126">The following actions may help you identify and resolve the underlying problem:</span></span>  
  
-   <span data-ttu-id="0c12c-127">Esaminare il log degli errori e il testo delle variabili di questo messaggio per individuare eventuali indizi che consentano di spiegare il problema.</span><span class="sxs-lookup"><span data-stu-id="0c12c-127">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="0c12c-128">Controllare il sistema di dischi.</span><span class="sxs-lookup"><span data-stu-id="0c12c-128">Check your disk system.</span></span> <span data-ttu-id="0c12c-129">Il problema potrebbe essere correlato ai dischi, ai controller dei dischi, alle schede di array o ai driver dei dischi.</span><span class="sxs-lookup"><span data-stu-id="0c12c-129">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="0c12c-130">Contattare il produttore dei dischi e richiedere le utilità più recenti per verificare lo stato del sistema di dischi.</span><span class="sxs-lookup"><span data-stu-id="0c12c-130">Contact the disk manufacturer for the latest utilities for checking the status of your disk system.</span></span>  
  
-   <span data-ttu-id="0c12c-131">Contattare il produttore dei dischi e richiedere gli ultimi aggiornamenti dei driver.</span><span class="sxs-lookup"><span data-stu-id="0c12c-131">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
  
