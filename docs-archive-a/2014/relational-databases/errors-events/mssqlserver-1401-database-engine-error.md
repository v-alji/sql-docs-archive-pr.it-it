---
title: MSSQLSERVER_1401 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1401 (Database Engine error)
ms.assetid: 02928770-aa63-4509-8713-406c73e4cedc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 720263939e2f1685649fc41896e8ea10907d92ac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636173"
---
# <a name="mssqlserver_1401"></a><span data-ttu-id="62ee4-102">MSSQLSERVER_1401</span><span class="sxs-lookup"><span data-stu-id="62ee4-102">MSSQLSERVER_1401</span></span>
    
## <a name="details"></a><span data-ttu-id="62ee4-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="62ee4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62ee4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="62ee4-104">Product Name</span></span>|<span data-ttu-id="62ee4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="62ee4-105">SQL Server</span></span>|  
|<span data-ttu-id="62ee4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="62ee4-106">Event ID</span></span>|<span data-ttu-id="62ee4-107">1401</span><span class="sxs-lookup"><span data-stu-id="62ee4-107">1401</span></span>|  
|<span data-ttu-id="62ee4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="62ee4-108">Event Source</span></span>|<span data-ttu-id="62ee4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="62ee4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="62ee4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="62ee4-110">Component</span></span>|<span data-ttu-id="62ee4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="62ee4-111">SQLEngine</span></span>|  
|<span data-ttu-id="62ee4-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="62ee4-112">Symbolic Name</span></span>|<span data-ttu-id="62ee4-113">DBM_MASTERSTARTUP</span><span class="sxs-lookup"><span data-stu-id="62ee4-113">DBM_MASTERSTARTUP</span></span>|  
|<span data-ttu-id="62ee4-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="62ee4-114">Message Text</span></span>|<span data-ttu-id="62ee4-115">Avvio della routine del thread master del mirroring del database non riuscito per il motivo seguente: %ls.</span><span class="sxs-lookup"><span data-stu-id="62ee4-115">Startup of the database-mirroring master thread routine failed for the following reason: %ls.</span></span> <span data-ttu-id="62ee4-116">Eliminare la causa dell'errore, quindi riavviare il servizio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="62ee4-116">Correct the cause of this error, and restart the SQL Server service.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="62ee4-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="62ee4-117">Explanation</span></span>  
 <span data-ttu-id="62ee4-118">L'avvio del thread di controllo del mirroring non è riuscito.</span><span class="sxs-lookup"><span data-stu-id="62ee4-118">Startup of the mirroring control thread failed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62ee4-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="62ee4-119">User Action</span></span>  
 <span data-ttu-id="62ee4-120">Nel log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cercare l'errore associato che ha preceduto la visualizzazione di questo messaggio.</span><span class="sxs-lookup"><span data-stu-id="62ee4-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, look for the associated error that preceded this message.</span></span> <span data-ttu-id="62ee4-121">Eliminare la causa dell'errore e quindi riavviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="62ee4-121">Correct the cause of this error, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service (MSSQLSERVER).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62ee4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62ee4-122">See Also</span></span>  
 [<span data-ttu-id="62ee4-123">Avviare, arrestare, sospendere, riprendere, riavviare il motore di database, SQL Server Agent o SQL Server Browser</span><span class="sxs-lookup"><span data-stu-id="62ee4-123">Start, Stop, Pause, Resume, Restart the Database Engine, SQL Server Agent, or SQL Server Browser Service</span></span>](../../database-engine/configure-windows/start-stop-pause-resume-restart-sql-server-services.md)  
  
  
