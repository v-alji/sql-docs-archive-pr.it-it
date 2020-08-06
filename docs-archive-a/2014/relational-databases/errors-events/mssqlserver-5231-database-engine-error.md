---
title: MSSQLSERVER_5231 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5231 (Database Engine error)
ms.assetid: 6954ae84-ed0b-4f4c-9d0a-e73f3d71476c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 68f40ac3a566280526757bd8b83c784954ba3dde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713183"
---
# <a name="mssqlserver_5231"></a><span data-ttu-id="da0c2-102">MSSQLSERVER_5231</span><span class="sxs-lookup"><span data-stu-id="da0c2-102">MSSQLSERVER_5231</span></span>
    
## <a name="details"></a><span data-ttu-id="da0c2-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="da0c2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da0c2-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="da0c2-104">Product Name</span></span>|<span data-ttu-id="da0c2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="da0c2-105">SQL Server</span></span>|  
|<span data-ttu-id="da0c2-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="da0c2-106">Event ID</span></span>|<span data-ttu-id="da0c2-107">5231</span><span class="sxs-lookup"><span data-stu-id="da0c2-107">5231</span></span>|  
|<span data-ttu-id="da0c2-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="da0c2-108">Event Source</span></span>|<span data-ttu-id="da0c2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="da0c2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="da0c2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="da0c2-110">Component</span></span>|<span data-ttu-id="da0c2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="da0c2-111">SQLEngine</span></span>|  
|<span data-ttu-id="da0c2-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="da0c2-112">Symbolic Name</span></span>|<span data-ttu-id="da0c2-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span><span class="sxs-lookup"><span data-stu-id="da0c2-113">DBCC4_DEADLOCK_SKIPPED_OBJECT</span></span>|  
|<span data-ttu-id="da0c2-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="da0c2-114">Message Text</span></span>|<span data-ttu-id="da0c2-115">ID oggetto O_ID (oggetto 'NAME'): si è verificato un deadlock durante il tentativo di bloccare questo oggetto per la verifica.</span><span class="sxs-lookup"><span data-stu-id="da0c2-115">Object ID O_ID (object 'NAME'): A deadlock occurred while trying to lock this object for checking.</span></span> <span data-ttu-id="da0c2-116">L'oggetto è stato ignorato e non verrà elaborato.</span><span class="sxs-lookup"><span data-stu-id="da0c2-116">This object has been skipped and will not be processed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="da0c2-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="da0c2-117">Explanation</span></span>  
 <span data-ttu-id="da0c2-118">Si è verificato un deadlock durante il tentativo da parte di DBCC di bloccare l'oggetto e DBCC è stato scelto come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="da0c2-118">A deadlock occurred when DBCC was trying to lock the object, and DBCC was chosen as the deadlock victim.</span></span> <span data-ttu-id="da0c2-119">L'oggetto non verrà elaborato.</span><span class="sxs-lookup"><span data-stu-id="da0c2-119">The object will not be processed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="da0c2-120">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="da0c2-120">User Action</span></span>  
 <span data-ttu-id="da0c2-121">nessuno</span><span class="sxs-lookup"><span data-stu-id="da0c2-121">None</span></span>  
  
  
