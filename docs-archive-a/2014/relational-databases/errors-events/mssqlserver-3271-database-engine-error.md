---
title: MSSQLSERVER_3271 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3271 (Database Engine error)
ms.assetid: 21b8de4b-6624-4163-9561-1a6cc8fe3d51
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56bdb5875dbba3fbe5037a308d713170a9b6f9ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627768"
---
# <a name="mssqlserver_3271"></a><span data-ttu-id="9162e-102">MSSQLSERVER_3271</span><span class="sxs-lookup"><span data-stu-id="9162e-102">MSSQLSERVER_3271</span></span>
    
## <a name="details"></a><span data-ttu-id="9162e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="9162e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9162e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="9162e-104">Product Name</span></span>|<span data-ttu-id="9162e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9162e-105">SQL Server</span></span>|  
|<span data-ttu-id="9162e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="9162e-106">Event ID</span></span>|<span data-ttu-id="9162e-107">3271</span><span class="sxs-lookup"><span data-stu-id="9162e-107">3271</span></span>|  
|<span data-ttu-id="9162e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="9162e-108">Event Source</span></span>|<span data-ttu-id="9162e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9162e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9162e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="9162e-110">Component</span></span>|<span data-ttu-id="9162e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9162e-111">SQLEngine</span></span>|  
|<span data-ttu-id="9162e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="9162e-112">Symbolic Name</span></span>|<span data-ttu-id="9162e-113">DMPIO_IO_ERROR</span><span class="sxs-lookup"><span data-stu-id="9162e-113">DMPIO_IO_ERROR</span></span>|  
|<span data-ttu-id="9162e-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="9162e-114">Message Text</span></span>|<span data-ttu-id="9162e-115">Errore di I/O irreversibile nel file "%ls:" %ls.</span><span class="sxs-lookup"><span data-stu-id="9162e-115">A nonrecoverable I/O error occurred on file "%ls:" %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9162e-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="9162e-116">Explanation</span></span>  
 <span data-ttu-id="9162e-117">Si tratta di un errore generale che si verifica quando il sistema operativo genera un errore nell'esecuzione di I/O durante un'operazione di backup o di ripristino.</span><span class="sxs-lookup"><span data-stu-id="9162e-117">This is a general error that occurs when the operating system raises an error while performing I/O during a backup or restore operation.</span></span> <span data-ttu-id="9162e-118">Nella maggior parte delle situazioni ciò è dovuto semplicemente al fatto che il supporto di backup è pieno.</span><span class="sxs-lookup"><span data-stu-id="9162e-118">In most situations the cause is simply that the backup medium is full.</span></span>  
  
 <span data-ttu-id="9162e-119">È possibile che nell'errore sia incluso testo aggiuntivo generato dal sistema operativo in cui viene indicato che il disco è pieno.</span><span class="sxs-lookup"><span data-stu-id="9162e-119">The error may include additional text from the operating system indicating that the disk is full.</span></span> <span data-ttu-id="9162e-120">Durante l'esecuzione di un'operazione di backup o di ripristino con software di backup di terze parti è possibile ricevere un ulteriore messaggio in cui viene indicato l'esito negativo del backup.</span><span class="sxs-lookup"><span data-stu-id="9162e-120">When performing a backup or restore operation with third-party backup software an additional message may occur indicating that the backup failed.</span></span> <span data-ttu-id="9162e-121">Il testo del messaggio è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="9162e-121">The message may look similar to the following text:</span></span>  
  
```  
"2005-08-02 16:05:16.04 spid55 Error: 18210, Severity: 16, State: 1.  
 2005-08-02 16:05:16.04 spid55 BackupVirtualDeviceFile  
::RequestDurableMedia: Flush failure on backup device 'VDINULL'.   
Operating system error 995(The I/O operation has been aborted because   
of either a thread exit or an application request.)."  
```  
  
 <span data-ttu-id="9162e-122">Viene indicato che il software di backup ha richiesto l'interruzione dell'operazione di backup o di ripristino.</span><span class="sxs-lookup"><span data-stu-id="9162e-122">This is an indication that the backup software requested a termination of the backup or restore operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9162e-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="9162e-123">User Action</span></span>  
 <span data-ttu-id="9162e-124">Eseguire le attività seguenti in modo appropriato:</span><span class="sxs-lookup"><span data-stu-id="9162e-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="9162e-125">Esaminare i messaggi di errore di sistema sottostanti e i messaggi di errore di SQL Server precedenti al messaggio in questione per identificare la causa del problema.</span><span class="sxs-lookup"><span data-stu-id="9162e-125">Review the underlying system error messages and SQL Server error messages preceding this one to identify the cause of the failure.</span></span>  
  
-   <span data-ttu-id="9162e-126">Verificare che il supporto di backup e ripristino disponga di spazio sufficiente.</span><span class="sxs-lookup"><span data-stu-id="9162e-126">Ensure that the backup and restore medium has sufficient space.</span></span>  
  
-   <span data-ttu-id="9162e-127">Correggere gli errori generati dal software di backup e ripristino di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9162e-127">Correct any errors raised by third-party backup and restore software.</span></span>  
  
  
