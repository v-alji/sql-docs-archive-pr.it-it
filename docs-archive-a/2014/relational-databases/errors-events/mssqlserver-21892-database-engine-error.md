---
title: MSSQLSERVER_21892 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21892 (Database Engine error)
ms.assetid: 199818e8-28f4-440e-ad85-7bea88f51153
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5fd3bfa1213f0569293991d6bd759619c6e7b596
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723911"
---
# <a name="mssqlserver_21892"></a><span data-ttu-id="182e6-102">MSSQLSERVER_21892</span><span class="sxs-lookup"><span data-stu-id="182e6-102">MSSQLSERVER_21892</span></span>
    
## <a name="details"></a><span data-ttu-id="182e6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="182e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="182e6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="182e6-104">Product Name</span></span>|<span data-ttu-id="182e6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="182e6-105">SQL Server</span></span>|  
|<span data-ttu-id="182e6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="182e6-106">Event ID</span></span>|<span data-ttu-id="182e6-107">21892</span><span class="sxs-lookup"><span data-stu-id="182e6-107">21892</span></span>|  
|<span data-ttu-id="182e6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="182e6-108">Event Source</span></span>|<span data-ttu-id="182e6-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="182e6-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="182e6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="182e6-110">Component</span></span>|<span data-ttu-id="182e6-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="182e6-111">SQLEngine</span></span>|  
|<span data-ttu-id="182e6-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="182e6-112">Symbolic Name</span></span>|<span data-ttu-id="182e6-113">SQLErrorNum21892</span><span class="sxs-lookup"><span data-stu-id="182e6-113">SQLErrorNum21892</span></span>|  
|<span data-ttu-id="182e6-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="182e6-114">Message Text</span></span>|<span data-ttu-id="182e6-115">Impossibile eseguire una query su sys.availability_replicas nel database primario del gruppo di disponibilità associato al nome di rete virtuale '%s' per i nomi server delle repliche membro: errore = %d, messaggio di errore = %s.'.</span><span class="sxs-lookup"><span data-stu-id="182e6-115">Unable to query sys.availability_replicas at the availability group primary associated with virtual network name '%s' for the server names of the member replicas: error = %d, error message = %s.',</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="182e6-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="182e6-116">Explanation</span></span>  
 <span data-ttu-id="182e6-117">In `sp_validate_replica_hosts_as_publishers` viene eseguita una query sul database primario corrente del gruppo di disponibilità associato al server di pubblicazione reindirizzato, per determinare le istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che ospitano le repliche del membro.</span><span class="sxs-lookup"><span data-stu-id="182e6-117">`sp_validate_replica_hosts_as_publishers` queries the current primary of the availability group associated with the redirected publisher, to determine the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that host the member replicas.</span></span>  <span data-ttu-id="182e6-118">In caso di errore di questa query, viene restituito l'errore 21892.</span><span class="sxs-lookup"><span data-stu-id="182e6-118">When this query fails, error 21892 is returned.</span></span>  
  
 <span data-ttu-id="182e6-119">`sp_validate_replica_hosts_as_publishers` è presente in genere al primo utilizzo del server collegato temporaneo, pertanto, se ci sono problemi di connettività, è probabile che si presentino prima con `sp_validate_replica_hosts_as_publishers`.</span><span class="sxs-lookup"><span data-stu-id="182e6-119">`sp_validate_replica_hosts_as_publishers` is typically on of the first use of the temporary linked server, so if there are connectivity problems they are likely to appear first with `sp_validate_replica_hosts_as_publishers`.</span></span> <span data-ttu-id="182e6-120">A differenza di `sp_validate_redirected_publisher`, il server collegato utilizzato da `sp_validate_replica_hosts_as_publishers` utilizza sempre le credenziali del chiamante in caso di connessione a uno dei host di replica del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="182e6-120">Unlike `sp_validate_redirected_publisher`, the linked server used by `sp_validate_replica_hosts_as_publishers` always uses the credentials of the caller when connecting to any of the availability group replica hosts.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="182e6-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="182e6-121">User Action</span></span>  
 <span data-ttu-id="182e6-122">In caso di esecuzione di questa stored procedure, assicurarsi che sia in esecuzione da un accesso valido su tutte le repliche.</span><span class="sxs-lookup"><span data-stu-id="182e6-122">When running this stored procedure, made certain that you run from a login that is valid on all of the replicas.</span></span> <span data-ttu-id="182e6-123">L'accesso richiede autorizzazioni sufficienti per eseguire una query sulle tabelle di metadati del gruppo di disponibilità nonché eseguire una query sulle tabelle di metadati delle sottoscrizioni nella replica del database del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="182e6-123">The login will require sufficient authorization to query availability group metadata tables as well as to query the subscription metadata tables in the publisher database replica.</span></span>  
  
 <span data-ttu-id="182e6-124">Esaminare l'errore originale cui si fa riferimento per determinare la causa dell'errore ed eseguire azioni correttive appropriate.</span><span class="sxs-lookup"><span data-stu-id="182e6-124">Examine the original referenced error to determine the cause of the failure and appropriate corrective action.</span></span>  
  
  
