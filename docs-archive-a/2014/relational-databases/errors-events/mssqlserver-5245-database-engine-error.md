---
title: MSSQLSERVER_5245 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5245 (Database Engine error)
ms.assetid: 6005c9ec-ccdd-4def-9eb4-37cdb599ddb3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f98c831642580587552bf60c604d84c38fffca8c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636094"
---
# <a name="mssqlserver_5245"></a><span data-ttu-id="0b1b6-102">MSSQLSERVER_5245</span><span class="sxs-lookup"><span data-stu-id="0b1b6-102">MSSQLSERVER_5245</span></span>
    
## <a name="details"></a><span data-ttu-id="0b1b6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="0b1b6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b1b6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="0b1b6-104">Product Name</span></span>|<span data-ttu-id="0b1b6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b1b6-105">SQL Server</span></span>|  
|<span data-ttu-id="0b1b6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="0b1b6-106">Event ID</span></span>|<span data-ttu-id="0b1b6-107">5245</span><span class="sxs-lookup"><span data-stu-id="0b1b6-107">5245</span></span>|  
|<span data-ttu-id="0b1b6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="0b1b6-108">Event Source</span></span>|<span data-ttu-id="0b1b6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0b1b6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0b1b6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="0b1b6-110">Component</span></span>|<span data-ttu-id="0b1b6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0b1b6-111">SQLEngine</span></span>|  
|<span data-ttu-id="0b1b6-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="0b1b6-112">Symbolic Name</span></span>|<span data-ttu-id="0b1b6-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span><span class="sxs-lookup"><span data-stu-id="0b1b6-113">DBCC4_TABLE_LOCK_TIMEOUT_EXCEEDED</span></span>|  
|<span data-ttu-id="0b1b6-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="0b1b6-114">Message Text</span></span>|<span data-ttu-id="0b1b6-115">ID oggetto O_ID (oggetto 'NAME'): DBCC non è in grado di ottenere un blocco sull'oggetto. Timeout della richiesta di blocco.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-115">Object ID O_ID (object 'NAME'): DBCC could not obtain a lock on this object because the lock request time-out period was exceeded.</span></span> <span data-ttu-id="0b1b6-116">L'oggetto è stato ignorato e non verrà elaborato.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0b1b6-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="0b1b6-117">Explanation</span></span>  
 <span data-ttu-id="0b1b6-118">Si è verificato un timeout di blocco mentre DBCC era in attesa di un blocco a livello di tabella per l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-118">A lock time-out occurred while DBCC was waiting on a table lock for the specified object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b1b6-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="0b1b6-119">User Action</span></span>  
 <span data-ttu-id="0b1b6-120">Eseguire di nuovo il comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="0b1b6-120">Rerun the DBCC command.</span></span>  
  
  
