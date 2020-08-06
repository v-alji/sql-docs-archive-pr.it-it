---
title: MSSQL_ENG014120 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014120 error
ms.assetid: 6b169a3b-30da-4981-b998-b52d61811572
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7f3484d9344a203ca8c44fee6b79605163ea069
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623178"
---
# <a name="mssql_eng014120"></a><span data-ttu-id="122e9-102">MSSQL_ENG014120</span><span class="sxs-lookup"><span data-stu-id="122e9-102">MSSQL_ENG014120</span></span>
    
## <a name="message-details"></a><span data-ttu-id="122e9-103">Dettagli messaggio</span><span class="sxs-lookup"><span data-stu-id="122e9-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="122e9-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="122e9-104">Product Name</span></span>|<span data-ttu-id="122e9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="122e9-105">SQL Server</span></span>|  
|<span data-ttu-id="122e9-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="122e9-106">Event ID</span></span>|<span data-ttu-id="122e9-107">14120</span><span class="sxs-lookup"><span data-stu-id="122e9-107">14120</span></span>|  
|<span data-ttu-id="122e9-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="122e9-108">Event Source</span></span>|<span data-ttu-id="122e9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="122e9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="122e9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="122e9-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="122e9-111">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="122e9-111">Symbolic Name</span></span>||  
|<span data-ttu-id="122e9-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="122e9-112">Message Text</span></span>|<span data-ttu-id="122e9-113">Il database di distribuzione '%s' è associato a un server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="122e9-113">Could not drop the distribution database '%s'.</span></span> <span data-ttu-id="122e9-114">Impossibile eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="122e9-114">This distributor database is associated with a Publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="122e9-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="122e9-115">Explanation</span></span>  
 <span data-ttu-id="122e9-116">Nel database di distribuzione vengono memorizzati metadati e dati di cronologia relativi a tutti i tipi di replica e alle transazioni per la replica transazionale.</span><span class="sxs-lookup"><span data-stu-id="122e9-116">The distribution database stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="122e9-117">Questo errore si verifica se si tenta di eliminare un database di distribuzione associato a uno o più server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="122e9-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="122e9-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="122e9-118">User Action</span></span>  
 <span data-ttu-id="122e9-119">Per eliminare un database di distribuzione, è innanzitutto necessario eliminare l'associazione tra il server di distribuzione e il server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="122e9-119">To drop a distribution database you must first drop the association between the Distributor and the Publisher.</span></span> <span data-ttu-id="122e9-120">Per altre informazioni, vedere [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="122e9-120">For more information, see [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122e9-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="122e9-121">See Also</span></span>  
 <span data-ttu-id="122e9-122">[Guida di riferimento a errori ed eventi &#40;replica&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="122e9-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="122e9-123">Configurare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="122e9-123">Configure Distribution</span></span>](configure-distribution.md)  
  
  
