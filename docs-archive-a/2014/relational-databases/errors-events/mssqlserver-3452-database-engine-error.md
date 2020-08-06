---
title: MSSQLSERVER_3452 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3452 (Database Engine error)
ms.assetid: bf838f02-7186-4b33-b01e-361b0c02de1f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 662d342064e8094400a6b672e21704877b4d0448
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623306"
---
# <a name="mssqlserver_3452"></a><span data-ttu-id="77f22-102">MSSQLSERVER_3452</span><span class="sxs-lookup"><span data-stu-id="77f22-102">MSSQLSERVER_3452</span></span>
    
## <a name="details"></a><span data-ttu-id="77f22-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="77f22-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77f22-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="77f22-104">Product Name</span></span>|<span data-ttu-id="77f22-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="77f22-105">SQL Server</span></span>|  
|<span data-ttu-id="77f22-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="77f22-106">Event ID</span></span>|<span data-ttu-id="77f22-107">3452</span><span class="sxs-lookup"><span data-stu-id="77f22-107">3452</span></span>|  
|<span data-ttu-id="77f22-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="77f22-108">Event Source</span></span>|<span data-ttu-id="77f22-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="77f22-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="77f22-110">Componente</span><span class="sxs-lookup"><span data-stu-id="77f22-110">Component</span></span>|<span data-ttu-id="77f22-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="77f22-111">SQLEngine</span></span>|  
|<span data-ttu-id="77f22-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="77f22-112">Symbolic Name</span></span>|<span data-ttu-id="77f22-113">REC_CHECKIDENTITY</span><span class="sxs-lookup"><span data-stu-id="77f22-113">REC_CHECKIDENTITY</span></span>|  
|<span data-ttu-id="77f22-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="77f22-114">Message Text</span></span>|<span data-ttu-id="77f22-115">Durante il recupero del database '%.\*ls' (%d) è stata rilevata una possibile inconsistenza dei valori Identity nella tabella con ID %d.</span><span class="sxs-lookup"><span data-stu-id="77f22-115">Recovery of database '%.\*ls' (%d) detected possible identity value inconsistency in table ID %d.</span></span> <span data-ttu-id="77f22-116">Eseguire DBCC CHECKIDENT ('%.\*ls').</span><span class="sxs-lookup"><span data-stu-id="77f22-116">Run DBCC CHECKIDENT ('%.\*ls').</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77f22-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="77f22-117">Explanation</span></span>  
 <span data-ttu-id="77f22-118">Durante l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], nel processo di recupero dei valori Identity nel database è stata rilevata un'incoerenza tra i metadati.</span><span class="sxs-lookup"><span data-stu-id="77f22-118">During the upgrade to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the process to recover the identity values in the database found an inconsistency in the metadata.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77f22-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="77f22-119">User Action</span></span>  
 <span data-ttu-id="77f22-120">Eseguire DBCC CHECKIDENT.</span><span class="sxs-lookup"><span data-stu-id="77f22-120">Run DBCC CHECKIDENT.</span></span>  
  
  
