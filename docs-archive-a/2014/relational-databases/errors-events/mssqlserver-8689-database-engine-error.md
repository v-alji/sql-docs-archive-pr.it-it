---
title: MSSQLSERVER_8689 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8689 (Database Engine error)
ms.assetid: 99467a32-6576-4272-a076-b16c06933f2a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2cdca0a3cd9ce47ccb39ebeaf8fd1cd260aafbd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714368"
---
# <a name="mssqlserver_8689"></a><span data-ttu-id="c4db4-102">MSSQLSERVER_8689</span><span class="sxs-lookup"><span data-stu-id="c4db4-102">MSSQLSERVER_8689</span></span>
    
## <a name="details"></a><span data-ttu-id="c4db4-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="c4db4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c4db4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="c4db4-104">Product Name</span></span>|<span data-ttu-id="c4db4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="c4db4-105">SQL Server</span></span>|  
|<span data-ttu-id="c4db4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="c4db4-106">Event ID</span></span>|<span data-ttu-id="c4db4-107">8689</span><span class="sxs-lookup"><span data-stu-id="c4db4-107">8689</span></span>|  
|<span data-ttu-id="c4db4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="c4db4-108">Event Source</span></span>|<span data-ttu-id="c4db4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="c4db4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="c4db4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="c4db4-110">Component</span></span>|<span data-ttu-id="c4db4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="c4db4-111">SQLEngine</span></span>|  
|<span data-ttu-id="c4db4-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="c4db4-112">Symbolic Name</span></span>|<span data-ttu-id="c4db4-113">USEPLAN_ERR_NO_DB</span><span class="sxs-lookup"><span data-stu-id="c4db4-113">USEPLAN_ERR_NO_DB</span></span>|  
|<span data-ttu-id="c4db4-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="c4db4-114">Message Text</span></span>|<span data-ttu-id="c4db4-115">Il database '%.\*ls' specificato nell'hint USE PLAN non esiste.</span><span class="sxs-lookup"><span data-stu-id="c4db4-115">Database '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="c4db4-116">Specificare un database esistente.</span><span class="sxs-lookup"><span data-stu-id="c4db4-116">Specify an existing database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c4db4-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="c4db4-117">Explanation</span></span>  
 <span data-ttu-id="c4db4-118">Un database specificato nell'hint USE PLAN non esiste.</span><span class="sxs-lookup"><span data-stu-id="c4db4-118">A database that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c4db4-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="c4db4-119">User Action</span></span>  
 <span data-ttu-id="c4db4-120">Verificare che tutti i database specificati nell'hint USE PLAN esistano.</span><span class="sxs-lookup"><span data-stu-id="c4db4-120">Ensure all databases that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4db4-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4db4-121">See Also</span></span>  
 <span data-ttu-id="c4db4-122">[Hint di query &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="c4db4-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="c4db4-123">Guide di piano</span><span class="sxs-lookup"><span data-stu-id="c4db4-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
