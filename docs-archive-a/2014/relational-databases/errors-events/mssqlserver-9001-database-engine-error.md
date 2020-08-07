---
title: MSSQLSERVER_9001 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9001 (Database Engine error)
ms.assetid: a54de936-90c6-4845-aa96-29d32f154601
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e61894d0d071fbdb36dcfb77895c46c61d0bbd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719950"
---
# <a name="mssqlserver_9001"></a><span data-ttu-id="f0945-102">MSSQLSERVER_9001</span><span class="sxs-lookup"><span data-stu-id="f0945-102">MSSQLSERVER_9001</span></span>
    
## <a name="details"></a><span data-ttu-id="f0945-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f0945-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0945-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f0945-104">Product Name</span></span>|<span data-ttu-id="f0945-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0945-105">SQL Server</span></span>|  
|<span data-ttu-id="f0945-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f0945-106">Event ID</span></span>|<span data-ttu-id="f0945-107">9001</span><span class="sxs-lookup"><span data-stu-id="f0945-107">9001</span></span>|  
|<span data-ttu-id="f0945-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f0945-108">Event Source</span></span>|<span data-ttu-id="f0945-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f0945-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f0945-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f0945-110">Component</span></span>|<span data-ttu-id="f0945-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f0945-111">SQLEngine</span></span>|  
|<span data-ttu-id="f0945-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f0945-112">Symbolic Name</span></span>|<span data-ttu-id="f0945-113">LOG_NOT_AVAIL</span><span class="sxs-lookup"><span data-stu-id="f0945-113">LOG_NOT_AVAIL</span></span>|  
|<span data-ttu-id="f0945-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f0945-114">Message Text</span></span>|<span data-ttu-id="f0945-115">Il log per il database '%.\*ls' non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="f0945-115">The log for database '%.\*ls' is not available.</span></span> <span data-ttu-id="f0945-116">Controllare il registro eventi per i messaggi di errore correlati.</span><span class="sxs-lookup"><span data-stu-id="f0945-116">Check the event log for related error messages.</span></span> <span data-ttu-id="f0945-117">Risolvere eventuali errori e riavviare il database.</span><span class="sxs-lookup"><span data-stu-id="f0945-117">Resolve any errors and restart the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f0945-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f0945-118">Explanation</span></span>  
 <span data-ttu-id="f0945-119">Il log del database è stato messo offline.</span><span class="sxs-lookup"><span data-stu-id="f0945-119">The database log was taken offline.</span></span> <span data-ttu-id="f0945-120">In genere questa situazione implica un errore irreversibile per cui è necessario riavviare il database.</span><span class="sxs-lookup"><span data-stu-id="f0945-120">Usually this signifies a catastrophic failure that requires the database to restart.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f0945-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f0945-121">User Action</span></span>  
 <span data-ttu-id="f0945-122">Diagnosticare altri errori e riavviare l'istanza di SQL Server qualora il riavvio non sia già stato eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f0945-122">Diagnose other errors and restart the instance of SQL Server if it has not already restarted itself.</span></span>  
  
  
