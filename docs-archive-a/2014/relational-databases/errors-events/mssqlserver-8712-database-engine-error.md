---
title: MSSQLSERVER_8712 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8712 (Database Engine error)
ms.assetid: 292fb3bc-062e-41e4-a566-b5d3d0b21977
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 9285d4846cac5af2dd6e87ab55d5fd0610586d07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638414"
---
# <a name="mssqlserver_8712"></a><span data-ttu-id="8c0bc-102">MSSQLSERVER_8712</span><span class="sxs-lookup"><span data-stu-id="8c0bc-102">MSSQLSERVER_8712</span></span>
    
## <a name="details"></a><span data-ttu-id="8c0bc-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8c0bc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c0bc-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8c0bc-104">Product Name</span></span>|<span data-ttu-id="8c0bc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8c0bc-105">SQL Server</span></span>|  
|<span data-ttu-id="8c0bc-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8c0bc-106">Event ID</span></span>|<span data-ttu-id="8c0bc-107">8712</span><span class="sxs-lookup"><span data-stu-id="8c0bc-107">8712</span></span>|  
|<span data-ttu-id="8c0bc-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8c0bc-108">Event Source</span></span>|<span data-ttu-id="8c0bc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8c0bc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8c0bc-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8c0bc-110">Component</span></span>|<span data-ttu-id="8c0bc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8c0bc-111">SQLEngine</span></span>|  
|<span data-ttu-id="8c0bc-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="8c0bc-112">Symbolic Name</span></span>|<span data-ttu-id="8c0bc-113">USEPLAN_ERR_NO_INDEX</span><span class="sxs-lookup"><span data-stu-id="8c0bc-113">USEPLAN_ERR_NO_INDEX</span></span>|  
|<span data-ttu-id="8c0bc-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8c0bc-114">Message Text</span></span>|<span data-ttu-id="8c0bc-115">L'indice '%.\*ls' specificato nell'hint USE PLAN non esiste.</span><span class="sxs-lookup"><span data-stu-id="8c0bc-115">Index '%.\*ls', specified in the USE PLAN hint, does not exist.</span></span> <span data-ttu-id="8c0bc-116">Specificare un indice esistente o creare un indice con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="8c0bc-116">Specify an existing index, or create an index with the specified name.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8c0bc-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8c0bc-117">Explanation</span></span>  
 <span data-ttu-id="8c0bc-118">Un indice specificato nell'hint USE PLAN non esiste.</span><span class="sxs-lookup"><span data-stu-id="8c0bc-118">An index that is specified in the USE PLAN hint does not exist.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8c0bc-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8c0bc-119">User Action</span></span>  
 <span data-ttu-id="8c0bc-120">Verificare che tutti gli indici specificati nell'hint USE PLAN esistano.</span><span class="sxs-lookup"><span data-stu-id="8c0bc-120">Ensure all indexes that are specified in the USE PLAN hint exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0bc-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c0bc-121">See Also</span></span>  
 <span data-ttu-id="8c0bc-122">[Hint di query &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span><span class="sxs-lookup"><span data-stu-id="8c0bc-122">[Query Hints &#40;Transact-SQL&#41;](/sql/t-sql/queries/hints-transact-sql-query) </span></span>  
 [<span data-ttu-id="8c0bc-123">Guide di piano</span><span class="sxs-lookup"><span data-stu-id="8c0bc-123">Plan Guides</span></span>](../performance/plan-guides.md)  
  
  
