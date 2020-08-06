---
title: MSSQLSERVER_905 | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 905 (Database Engine error)
ms.assetid: c828bb2e-e554-4f81-b76c-2b3740d2b944
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7dd3c8c5a287e2d123e2a9d1430ecd49b27f29f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627747"
---
# <a name="mssqlserver_905"></a><span data-ttu-id="2a8a2-102">MSSQLSERVER_905</span><span class="sxs-lookup"><span data-stu-id="2a8a2-102">MSSQLSERVER_905</span></span>
    
## <a name="details"></a><span data-ttu-id="2a8a2-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2a8a2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a8a2-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="2a8a2-104">Product Name</span></span>|<span data-ttu-id="2a8a2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2a8a2-105">SQL Server</span></span>|  
|<span data-ttu-id="2a8a2-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="2a8a2-106">Event ID</span></span>|<span data-ttu-id="2a8a2-107">905</span><span class="sxs-lookup"><span data-stu-id="2a8a2-107">905</span></span>|  
|<span data-ttu-id="2a8a2-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="2a8a2-108">Event Source</span></span>|<span data-ttu-id="2a8a2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="2a8a2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="2a8a2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="2a8a2-110">Component</span></span>|<span data-ttu-id="2a8a2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="2a8a2-111">SQLEngine</span></span>|  
|<span data-ttu-id="2a8a2-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="2a8a2-112">Symbolic Name</span></span>|<span data-ttu-id="2a8a2-113">DBSTARTUP_EE_PARTITIONING</span><span class="sxs-lookup"><span data-stu-id="2a8a2-113">DBSTARTUP_EE_PARTITIONING</span></span>|  
|<span data-ttu-id="2a8a2-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="2a8a2-114">Message Text</span></span>|<span data-ttu-id="2a8a2-115">Impossibile avviare il database '%.\*ls' in questa edizione di SQL Server, perché contiene la funzione di partizione '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="2a8a2-115">Database '%.\*ls' cannot be started in this edition of SQL Server because it contains a partition function '%.\*ls'.</span></span> <span data-ttu-id="2a8a2-116">Il partizionamento è supportato solo in SQL Server Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2a8a2-116">Only Enterprise edition of SQL Server supports partitioning.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2a8a2-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="2a8a2-117">Explanation</span></span>  
 <span data-ttu-id="2a8a2-118">Il database contiene uno o più tabelle o indici partizionati.</span><span class="sxs-lookup"><span data-stu-id="2a8a2-118">The database contains one or more partitioned tables or indexes.</span></span> <span data-ttu-id="2a8a2-119">Il partizionamento non è supportato in questa edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a8a2-119">This edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot use partitioning.</span></span> <span data-ttu-id="2a8a2-120">Il database non può pertanto essere avviato in modo corretto.</span><span class="sxs-lookup"><span data-stu-id="2a8a2-120">Therefore, the database cannot be started correctly.</span></span> <span data-ttu-id="2a8a2-121">Le tabelle e gli indici partizionati sono disponibili solo in alcune edizioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a8a2-121">Partitioned tables and indexes are not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2a8a2-122">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="2a8a2-122">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2a8a2-123">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="2a8a2-123">User Action</span></span>  
 <span data-ttu-id="2a8a2-124">Scollegare il database utilizzando la stored procedure sp_detach_db.</span><span class="sxs-lookup"><span data-stu-id="2a8a2-124">Detach the database by using the sp_detach_db stored procedure.</span></span> <span data-ttu-id="2a8a2-125">Se necessario, spostare i file, quindi collegare il database a un'istanza di un'edizione supportata di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando CREATE DATABASE con l'opzione FOR ATTACH o FOR ATTACH_REBUILD_LOG.</span><span class="sxs-lookup"><span data-stu-id="2a8a2-125">Move the files if it is needed, and then attach the database to an instance of a supported [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] edition by using the CREATE DATABASE with the FOR ATTACH or FOR ATTACH_REBUILD_LOG option.</span></span> <span data-ttu-id="2a8a2-126">Disabilitare il partizionamento in tutte le tabelle e rimuovere le funzioni di partizionamento.</span><span class="sxs-lookup"><span data-stu-id="2a8a2-126">Disable partitioning on all tables and remove the partitioning functions.</span></span> <span data-ttu-id="2a8a2-127">Scollegare di nuovo il database e ricollegarlo al server corrente.</span><span class="sxs-lookup"><span data-stu-id="2a8a2-127">Detach the database again, and reattach the database to the current server.</span></span>  
  
  
