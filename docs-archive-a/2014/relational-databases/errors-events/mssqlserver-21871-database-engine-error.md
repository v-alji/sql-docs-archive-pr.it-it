---
title: MSSQLSERVER_21871 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21871 (Database Engine error)
ms.assetid: d3215378-9282-444f-a18b-00b96fd0133d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f26211da21829a0a898dfb36ff9fefd453c7ad44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715323"
---
# <a name="mssqlserver_21871"></a><span data-ttu-id="484e1-102">MSSQLSERVER_21871</span><span class="sxs-lookup"><span data-stu-id="484e1-102">MSSQLSERVER_21871</span></span>
    
## <a name="details"></a><span data-ttu-id="484e1-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="484e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="484e1-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="484e1-104">Product Name</span></span>|<span data-ttu-id="484e1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="484e1-105">SQL Server</span></span>|  
|<span data-ttu-id="484e1-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="484e1-106">Event ID</span></span>|<span data-ttu-id="484e1-107">21871</span><span class="sxs-lookup"><span data-stu-id="484e1-107">21871</span></span>|  
|<span data-ttu-id="484e1-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="484e1-108">Event Source</span></span>|<span data-ttu-id="484e1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="484e1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="484e1-110">Componente</span><span class="sxs-lookup"><span data-stu-id="484e1-110">Component</span></span>|<span data-ttu-id="484e1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="484e1-111">SQLEngine</span></span>|  
|<span data-ttu-id="484e1-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="484e1-112">Symbolic Name</span></span>|<span data-ttu-id="484e1-113">SQLErrorNum21871</span><span class="sxs-lookup"><span data-stu-id="484e1-113">SQLErrorNum21871</span></span>|  
|<span data-ttu-id="484e1-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="484e1-114">Message Text</span></span>|<span data-ttu-id="484e1-115">Il server di pubblicazione %s del database %s non è stato reindirizzato.</span><span class="sxs-lookup"><span data-stu-id="484e1-115">Publisher %s of database %s has not been redirected.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="484e1-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="484e1-116">Explanation</span></span>  
 <span data-ttu-id="484e1-117">`sp_validate_replica_hosts_as_publishers` controlla la tabella MSredirected_publishers nel database di distribuzione per individuare una voce per il server di pubblicazione identificato e il database del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="484e1-117">`sp_validate_replica_hosts_as_publishers` checks the table MSredirected_publishers in the distribution database for an entry for the identified publisher and publisher database.</span></span>  <span data-ttu-id="484e1-118">`sp_validate_replica_hosts_as_publishers` restituisce l'errore 21871 quando non viene trovata alcuna voce.</span><span class="sxs-lookup"><span data-stu-id="484e1-118">`sp_validate_replica_hosts_as_publishers` returns error 21871 when no entry is found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="484e1-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="484e1-119">User Action</span></span>  
 <span data-ttu-id="484e1-120">`sp_validate_replica_hosts_as_publishers` è attinente solo per i server di pubblicazione reindirizzati.</span><span class="sxs-lookup"><span data-stu-id="484e1-120">`sp_validate_replica_hosts_as_publishers` is only relevant for redirected publishers.</span></span> <span data-ttu-id="484e1-121">Se un database del server di pubblicazione è membro di un gruppo di disponibilità, utilizzare la stored procedure `sp_redirect_publisher` per associare il server di pubblicazione e il database del server di pubblicazione al nome del listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="484e1-121">If the publisher database is a member of an availability group, use the stored procedure `sp_redirect_publisher` to associate the publisher and publisher database with the Availability Group Listener Name of the availability group.</span></span>  
  
  
