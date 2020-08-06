---
title: MSSQL_ENG014121 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014121 error
ms.assetid: c8595854-cce1-4566-ad64-d565555caded
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04d4cbdd2197745d2d795814d88c4f7bc28eb90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623179"
---
# <a name="mssql_eng014121"></a><span data-ttu-id="c51be-102">MSSQL_ENG014121</span><span class="sxs-lookup"><span data-stu-id="c51be-102">MSSQL_ENG014121</span></span>
    
## <a name="message-details"></a><span data-ttu-id="c51be-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="c51be-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c51be-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="c51be-104">Product Name</span></span>|<span data-ttu-id="c51be-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c51be-105">SQL Server</span></span>|  
|<span data-ttu-id="c51be-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="c51be-106">Event ID</span></span>|<span data-ttu-id="c51be-107">14121</span><span class="sxs-lookup"><span data-stu-id="c51be-107">14121</span></span>|  
|<span data-ttu-id="c51be-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="c51be-108">Event Source</span></span>|<span data-ttu-id="c51be-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c51be-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c51be-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c51be-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="c51be-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="c51be-111">Symbolic Name</span></span>||  
|<span data-ttu-id="c51be-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="c51be-112">Message Text</span></span>|<span data-ttu-id="c51be-113">Al server di distribuzione '%s' sono associati database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c51be-113">Could not drop the Distributor '%s'.</span></span> <span data-ttu-id="c51be-114">Impossibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="c51be-114">This Distributor has associated distribution databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c51be-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="c51be-115">Explanation</span></span>  
 <span data-ttu-id="c51be-116">Un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] configurata come server di distribuzione non può essere rimossa dal ruolo di server di distribuzione poiché all'istanza sono associati database di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c51be-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Distributor cannot be removed from the role of Distributor because there are distribution databases associated with the instance.</span></span> <span data-ttu-id="c51be-117">Questo errore si verifica se si tenta di eliminare un database di distribuzione associato a uno o più server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="c51be-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c51be-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c51be-118">User Action</span></span>  
 <span data-ttu-id="c51be-119">Per trovare i nomi dei server di pubblicazione e dei database di distribuzione associati a questo server di distribuzione, eseguire [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) da qualsiasi database nel server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c51be-119">To find the names of any Publishers and distribution databases associated with this Distributor, execute [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) from any database on the Distributor.</span></span>  
  
 <span data-ttu-id="c51be-120">Eseguire [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) per tutti i database di distribuzione associati al server di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c51be-120">Execute [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) for any distribution databases associated with this Distributor.</span></span> <span data-ttu-id="c51be-121">Dopo la rimozione di tutte le associazioni di database di distribuzione, è possibile disabilitare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c51be-121">After all distribution database associations are removed, you can disable distribution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c51be-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c51be-122">See Also</span></span>  
 <span data-ttu-id="c51be-123">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="c51be-123">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="c51be-124">Configurare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="c51be-124">Configure Distribution</span></span>](configure-distribution.md)  
  
  
