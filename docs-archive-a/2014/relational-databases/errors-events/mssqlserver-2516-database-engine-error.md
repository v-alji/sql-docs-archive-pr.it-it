---
title: MSSQLSERVER_2516 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2516 (Database Engine error)
ms.assetid: 79ed14b5-f53c-40c6-8334-8a083f732207
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6be0809b3560d94bb883cf3a4acfa3d2c484b8b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713196"
---
# <a name="mssqlserver_2516"></a><span data-ttu-id="6fe5e-102">MSSQLSERVER_2516</span><span class="sxs-lookup"><span data-stu-id="6fe5e-102">MSSQLSERVER_2516</span></span>
    
## <a name="details"></a><span data-ttu-id="6fe5e-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6fe5e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6fe5e-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6fe5e-104">Product Name</span></span>|<span data-ttu-id="6fe5e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6fe5e-105">SQL Server</span></span>|  
|<span data-ttu-id="6fe5e-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="6fe5e-106">Event ID</span></span>|<span data-ttu-id="6fe5e-107">2516</span><span class="sxs-lookup"><span data-stu-id="6fe5e-107">2516</span></span>|  
|<span data-ttu-id="6fe5e-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6fe5e-108">Event Source</span></span>|<span data-ttu-id="6fe5e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6fe5e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6fe5e-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6fe5e-110">Component</span></span>|<span data-ttu-id="6fe5e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6fe5e-111">SQLEngine</span></span>|  
|<span data-ttu-id="6fe5e-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="6fe5e-112">Symbolic Name</span></span>|<span data-ttu-id="6fe5e-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span><span class="sxs-lookup"><span data-stu-id="6fe5e-113">DBCC_REPAIR_DIFF_MAP_INVALIDATED</span></span>|  
|<span data-ttu-id="6fe5e-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6fe5e-114">Message Text</span></span>|<span data-ttu-id="6fe5e-115">La correzione ha invalidato la mappa di bit differenziale per il database NAME.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-115">Repair has invalidated the differential bitmap for database NAME.</span></span> <span data-ttu-id="6fe5e-116">La catena di backup differenziale è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-116">The differential backup chain is broken.</span></span> <span data-ttu-id="6fe5e-117">Prima di eseguire un backup differenziale è necessario eseguire un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-117">You must perform a full database backup before you can perform a differential backup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6fe5e-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6fe5e-118">Explanation</span></span>  
 <span data-ttu-id="6fe5e-119">Questo messaggio informativo viene restituito quando si corregge l'errore MSSQLEngine_2515.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-119">This informational message is returned when error MSSQLEngine_2515 is repaired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6fe5e-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6fe5e-120">User Action</span></span>  
 <span data-ttu-id="6fe5e-121">Eseguire un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="6fe5e-121">Perform a full database backup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe5e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fe5e-122">See Also</span></span>  
 [<span data-ttu-id="6fe5e-123">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6fe5e-123">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
  
