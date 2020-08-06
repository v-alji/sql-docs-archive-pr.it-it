---
title: MSSQLSERVER_823 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 823 (Database Engine error)
ms.assetid: 0d9fce3c-3772-46ce-a7a3-4f4988dc6cae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fa5858bbdc9452a33a3d43fdd783e59556a11e57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628702"
---
# <a name="mssqlserver_823"></a><span data-ttu-id="1ea36-102">MSSQLSERVER_823</span><span class="sxs-lookup"><span data-stu-id="1ea36-102">MSSQLSERVER_823</span></span>
    
## <a name="details"></a><span data-ttu-id="1ea36-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1ea36-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ea36-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="1ea36-104">Product Name</span></span>|<span data-ttu-id="1ea36-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1ea36-105">SQL Server</span></span>|  
|<span data-ttu-id="1ea36-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="1ea36-106">Event ID</span></span>|<span data-ttu-id="1ea36-107">823</span><span class="sxs-lookup"><span data-stu-id="1ea36-107">823</span></span>|  
|<span data-ttu-id="1ea36-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="1ea36-108">Event Source</span></span>|<span data-ttu-id="1ea36-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1ea36-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1ea36-110">Componente</span><span class="sxs-lookup"><span data-stu-id="1ea36-110">Component</span></span>|<span data-ttu-id="1ea36-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1ea36-111">SQLEngine</span></span>|  
|<span data-ttu-id="1ea36-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="1ea36-112">Symbolic Name</span></span>|<span data-ttu-id="1ea36-113">B_HARDERR</span><span class="sxs-lookup"><span data-stu-id="1ea36-113">B_HARDERR</span></span>|  
|<span data-ttu-id="1ea36-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="1ea36-114">Message Text</span></span>|<span data-ttu-id="1ea36-115">Il sistema operativo ha restituito l'errore %ls a SQL Server durante un'operazione %S_MSG, all'offset %#016I64x nel file '%ls'.</span><span class="sxs-lookup"><span data-stu-id="1ea36-115">The operating system returned error %ls to SQL Server during a %S_MSG at offset %#016I64x in file '%ls'.</span></span> <span data-ttu-id="1ea36-116">Per informazioni più dettagliate, vedere i messaggi aggiuntivi nel log degli errori di SQL Server e nel registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="1ea36-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="1ea36-117">Si tratta di una condizione di errore grave a livello di sistema, che può compromettere l'integrità del database e deve essere corretta immediatamente.</span><span class="sxs-lookup"><span data-stu-id="1ea36-117">This is a severe system-level error condition that threatens database integrity and must be corrected immediately.</span></span> <span data-ttu-id="1ea36-118">Eseguire un controllo di consistenza completo del database (DBCC CHECKDB).</span><span class="sxs-lookup"><span data-stu-id="1ea36-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="1ea36-119">L'errore può essere causato da molti fattori. Per ulteriori informazioni, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1ea36-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1ea36-120">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1ea36-120">Explanation</span></span>  
 <span data-ttu-id="1ea36-121">Una richiesta di lettura o scrittura di Windows non è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="1ea36-121">A Windows read or write request has failed.</span></span> <span data-ttu-id="1ea36-122">Il messaggio include il codice di errore restituito da Windows e il testo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1ea36-122">The error code that is returned by Windows and the corresponding text are inserted into the message.</span></span> <span data-ttu-id="1ea36-123">Nel caso di una richiesta di lettura, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono eseguiti quattro tentativi prima di generare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="1ea36-123">In the read case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will have already retried the read request four times.</span></span> <span data-ttu-id="1ea36-124">Il problema è spesso dovuto a un errore hardware, ma può essere causato dal driver del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1ea36-124">This error is often the result of a hardware error, but may be caused by the device driver.</span></span> <span data-ttu-id="1ea36-125">Per ulteriori informazioni sull'errore 823, vedere [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339) .</span><span class="sxs-lookup"><span data-stu-id="1ea36-125">For more information about error 823, see [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339).</span></span> <span data-ttu-id="1ea36-126">Per altre informazioni sugli errori di I/O, vedere il capitolo 2 della pagina relativa alle [nozioni fondamentali sull'I/O in Microsoft SQL Server](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="1ea36-126">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1ea36-127">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="1ea36-127">User Action</span></span>  
 <span data-ttu-id="1ea36-128">Per ulteriori informazioni vedere il registro eventi di sistema.</span><span class="sxs-lookup"><span data-stu-id="1ea36-128">Check for additional information in the system event log.</span></span> <span data-ttu-id="1ea36-129">Contattare il produttore dell'hardware o il Servizio Supporto Tecnico Clienti Microsoft per determinare la causa e l'azione di correzione appropriata.</span><span class="sxs-lookup"><span data-stu-id="1ea36-129">Contact the hardware manufacturer or Microsoft Customer Services and Support to determine the cause and corrective action.</span></span> <span data-ttu-id="1ea36-130">Dopo la correzione dell'errore hardware, ripristinare tutti i database ed eseguire DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="1ea36-130">After the hardware error is fixed, restore all databases and run DBCC CHECKDB.</span></span>  
  
  
