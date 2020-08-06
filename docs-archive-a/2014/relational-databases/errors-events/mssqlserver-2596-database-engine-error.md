---
title: MSSQLSERVER_2596 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2596 (Database Engine error)
ms.assetid: 49ab892f-8ba3-4ba1-b562-ddf205019802
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 27b2ceed40274df4ba57c4d61a83fbc60b6a7f80
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628749"
---
# <a name="mssqlserver_2596"></a><span data-ttu-id="6648f-102">MSSQLSERVER_2596</span><span class="sxs-lookup"><span data-stu-id="6648f-102">MSSQLSERVER_2596</span></span>
    
## <a name="details"></a><span data-ttu-id="6648f-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6648f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6648f-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="6648f-104">Product Name</span></span>|<span data-ttu-id="6648f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6648f-105">SQL Server</span></span>|  
|<span data-ttu-id="6648f-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="6648f-106">Event ID</span></span>|<span data-ttu-id="6648f-107">2596</span><span class="sxs-lookup"><span data-stu-id="6648f-107">2596</span></span>|  
|<span data-ttu-id="6648f-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="6648f-108">Event Source</span></span>|<span data-ttu-id="6648f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6648f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6648f-110">Componente</span><span class="sxs-lookup"><span data-stu-id="6648f-110">Component</span></span>|<span data-ttu-id="6648f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6648f-111">SQLEngine</span></span>|  
|<span data-ttu-id="6648f-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="6648f-112">Symbolic Name</span></span>|<span data-ttu-id="6648f-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span><span class="sxs-lookup"><span data-stu-id="6648f-113">DBCC_DATABASE_IN_READ_ONLY_MODE</span></span>|  
|<span data-ttu-id="6648f-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="6648f-114">Message Text</span></span>|<span data-ttu-id="6648f-115">L'istruzione di correzione non è stata elaborata.</span><span class="sxs-lookup"><span data-stu-id="6648f-115">The repair statement was not processed.</span></span> <span data-ttu-id="6648f-116">Il database non può essere in modalità sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6648f-116">The database cannot be in read-only mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6648f-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="6648f-117">Explanation</span></span>  
 <span data-ttu-id="6648f-118">Il messaggio indica che il database è in modalità sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6648f-118">This message indicates that the database is in read-only mode.</span></span> <span data-ttu-id="6648f-119">Non è possibile implementare correzioni quando un database si trova in tale modalità.</span><span class="sxs-lookup"><span data-stu-id="6648f-119">Repairs are not possible when a database is in read-only mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6648f-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="6648f-120">User Action</span></span>  
 <span data-ttu-id="6648f-121">Impostare il database per l'accesso in lettura/scrittura utilizzando ALTER DATABASE e quindi eseguire nuovamente il comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="6648f-121">Set the database to read-write by using ALTER DATABASE, and then re-run the DBCC command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6648f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6648f-122">See Also</span></span>  
 [<span data-ttu-id="6648f-123">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6648f-123">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
