---
title: MSSQLSERVER_17128 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17128 (Database Engine error)
ms.assetid: 7b15a5e6-fd41-47ce-ba87-54f72acea4bb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e08c668acd0a8b2decb14da338b8d1f1e650de5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714400"
---
# <a name="mssqlserver_17128"></a><span data-ttu-id="f8e2b-102">MSSQLSERVER_17128</span><span class="sxs-lookup"><span data-stu-id="f8e2b-102">MSSQLSERVER_17128</span></span>
    
## <a name="details"></a><span data-ttu-id="f8e2b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f8e2b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8e2b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f8e2b-104">Product Name</span></span>|<span data-ttu-id="f8e2b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f8e2b-105">SQL Server</span></span>|  
|<span data-ttu-id="f8e2b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f8e2b-106">Event ID</span></span>|<span data-ttu-id="f8e2b-107">17128</span><span class="sxs-lookup"><span data-stu-id="f8e2b-107">17128</span></span>|  
|<span data-ttu-id="f8e2b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f8e2b-108">Event Source</span></span>|<span data-ttu-id="f8e2b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f8e2b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f8e2b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f8e2b-110">Component</span></span>|<span data-ttu-id="f8e2b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f8e2b-111">SQLEngine</span></span>|  
|<span data-ttu-id="f8e2b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f8e2b-112">Symbolic Name</span></span>|<span data-ttu-id="f8e2b-113">INIT_NOBUFSPACE</span><span class="sxs-lookup"><span data-stu-id="f8e2b-113">INIT_NOBUFSPACE</span></span>|  
|<span data-ttu-id="f8e2b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f8e2b-114">Message Text</span></span>|<span data-ttu-id="f8e2b-115">initdata: memoria non disponibile per i buffer del kernel.</span><span class="sxs-lookup"><span data-stu-id="f8e2b-115">initdata: No memory for kernel buffers.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f8e2b-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f8e2b-116">Explanation</span></span>  
 <span data-ttu-id="f8e2b-117">Non è stato possibile eseguire le allocazioni o le prenotazioni iniziali di memoria per il pool di buffer. SQL Server viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="f8e2b-117">The buffer pool's initial memory allocations or reservations have failed, and SQL Server exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f8e2b-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f8e2b-118">User Action</span></span>  
 <span data-ttu-id="f8e2b-119">Questo errore si verifica in genere quando SQL Server viene avviato in un computer con requisiti di sistema estremamente inferiori rispetto a quelli minimi necessari.</span><span class="sxs-lookup"><span data-stu-id="f8e2b-119">Usually caused by starting SQL Server on an extremely small machine - far smaller than the minimum system requirements.</span></span>  
  
  
