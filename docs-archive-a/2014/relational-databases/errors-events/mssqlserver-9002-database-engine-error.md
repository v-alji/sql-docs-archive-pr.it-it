---
title: MSSQLSERVER_9002 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9002 (Database Engine error)
ms.assetid: 2e50841f-2b99-45f4-aec5-aa4add70cbeb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b40fe70db8849d09f9296a06cbeed65a9c71e5a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635060"
---
# <a name="mssqlserver_9002"></a><span data-ttu-id="e5ad9-102">MSSQLSERVER_9002</span><span class="sxs-lookup"><span data-stu-id="e5ad9-102">MSSQLSERVER_9002</span></span>
    
## <a name="details"></a><span data-ttu-id="e5ad9-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="e5ad9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e5ad9-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="e5ad9-104">Product Name</span></span>|<span data-ttu-id="e5ad9-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e5ad9-105">SQL Server</span></span>|  
|<span data-ttu-id="e5ad9-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="e5ad9-106">Event ID</span></span>|<span data-ttu-id="e5ad9-107">9002</span><span class="sxs-lookup"><span data-stu-id="e5ad9-107">9002</span></span>|  
|<span data-ttu-id="e5ad9-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="e5ad9-108">Event Source</span></span>|<span data-ttu-id="e5ad9-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e5ad9-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e5ad9-110">Componente</span><span class="sxs-lookup"><span data-stu-id="e5ad9-110">Component</span></span>|<span data-ttu-id="e5ad9-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e5ad9-111">SQLEngine</span></span>|  
|<span data-ttu-id="e5ad9-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="e5ad9-112">Symbolic Name</span></span>|<span data-ttu-id="e5ad9-113">LOG_IS_FULL</span><span class="sxs-lookup"><span data-stu-id="e5ad9-113">LOG_IS_FULL</span></span>|  
|<span data-ttu-id="e5ad9-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="e5ad9-114">Message Text</span></span>|<span data-ttu-id="e5ad9-115">Il log delle transazioni per il database '%.\*ls' è pieno.</span><span class="sxs-lookup"><span data-stu-id="e5ad9-115">The transaction log for database '%.\*ls' is full.</span></span> <span data-ttu-id="e5ad9-116">Per sapere perché non è possibile riutilizzare lo spazio nel log, vedere la colonna log_reuse_wait_desc in sys.databases.</span><span class="sxs-lookup"><span data-stu-id="e5ad9-116">To find out why space in the log cannot be reused, see the log_reuse_wait_desc column in sys.databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e5ad9-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="e5ad9-117">Explanation</span></span>  
 <span data-ttu-id="e5ad9-118">Lo spazio nel log del database è esaurito.</span><span class="sxs-lookup"><span data-stu-id="e5ad9-118">The database log is out of space.</span></span> <span data-ttu-id="e5ad9-119">Nella colonna **log_reuse_wait_desc** in **sys.databases** viene descritto il motivo per cui non è possibile usare di nuovo lo spazio nel log.</span><span class="sxs-lookup"><span data-stu-id="e5ad9-119">The **log_reuse_wait_desc** column in **sys.databases** describes why space in the log cannot be reused.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e5ad9-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="e5ad9-120">User Action</span></span>  
 <span data-ttu-id="e5ad9-121">Usare **sys.databases** per determinare perché il log è pieno e quindi correggere tale condizione.</span><span class="sxs-lookup"><span data-stu-id="e5ad9-121">Use **sys.databases** to determine why the log is full and then correct the condition.</span></span> <span data-ttu-id="e5ad9-122">Per ulteriori informazioni, vedere l'articolo sulla risoluzione dei problemi relativi a un log delle transazioni pieno (Errore 9002) nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e5ad9-122">For more information, see "Troubleshooting a Full Transaction Log (Error 9002)" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ad9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5ad9-123">See Also</span></span>  
 <span data-ttu-id="e5ad9-124">[Risolvere i problemi relativi a un log delle transazioni completo &#40;Errore di SQL Server 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span><span class="sxs-lookup"><span data-stu-id="e5ad9-124">[Troubleshoot a Full Transaction Log &#40;SQL Server Error 9002&#41;](../logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md) </span></span>  
 [<span data-ttu-id="e5ad9-125">sys.databases &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e5ad9-125">sys.databases &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-databases-transact-sql)  
  
  
