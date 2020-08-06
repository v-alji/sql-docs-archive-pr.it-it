---
title: Snapshot del database con Gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database snapshots [SQL Server], AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 7432da1c-ce2f-4cd9-af41-54c97744166b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e1e4307653b5b8150d71019a373ee073d15123f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721759"
---
# <a name="database-snapshots-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="532e1-102">Snapshot del database con gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="532e1-102">Database Snapshots with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="532e1-103">È possibile creare uno snapshot del database in un qualsiasi database primario o secondario in un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="532e1-103">You can create a database snapshot on an primary or secondary database in an availability group.</span></span> <span data-ttu-id="532e1-104">Il ruolo di replica deve essere PRIMARY o SECONDARY, non nello stato di RESOLVING.</span><span class="sxs-lookup"><span data-stu-id="532e1-104">The replica role must be either PRIMARY or SECONDARY, not in the RESOLVING state.</span></span>  
  
 <span data-ttu-id="532e1-105">È consigliabile uno stato di sincronizzazione del database corrispondente a SYNCHRONIZING o SYNCHRONIZED quando si crea uno snapshot del database.</span><span class="sxs-lookup"><span data-stu-id="532e1-105">We recommend that the database synchronization state be SYNCHRONIZING or SYNCHRONIZED when you create a database snapshot.</span></span> <span data-ttu-id="532e1-106">È tuttavia possibile creare gli snapshot del database anche se lo stato della sincronizzazione del database è NOT SYNCHRONIZING.</span><span class="sxs-lookup"><span data-stu-id="532e1-106">However, database snapshots can be created when the database synchronization state is NOT SYNCHRONIZING.</span></span>  
  
 <span data-ttu-id="532e1-107">Uno snapshot del database in una replica secondaria deve continuare a funzionare anche se la replica è disconnessa (DISCONNECTED) dalla replica primaria.</span><span class="sxs-lookup"><span data-stu-id="532e1-107">A database snapshot on a secondary replica should continue to work if the replica is DISCONNECTED from the primary replica.</span></span>  
  
 <span data-ttu-id="532e1-108">Alcune condizioni di [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] causano il riavvio del database di origine e degli snapshot del database, disconnettendo temporaneamente gli utenti.</span><span class="sxs-lookup"><span data-stu-id="532e1-108">Some [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] conditions cause both the source database and its database snapshots to be restarted, temporarily disconnecting users.</span></span> <span data-ttu-id="532e1-109">Tali condizioni sono descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="532e1-109">These conditions are as follows:</span></span>  
  
-   <span data-ttu-id="532e1-110">La replica primaria cambia i ruoli, perché la replica primaria corrente viene portata offline e poi online sulla stessa istanza del server o perché si verifica il failover del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="532e1-110">The primary replica changes roles, whether because the current primary replica goes off line and comes back online on the same server instance or because the availability group fails over.</span></span>  
  
-   <span data-ttu-id="532e1-111">Il database passa al ruolo secondario.</span><span class="sxs-lookup"><span data-stu-id="532e1-111">The database enters the secondary role.</span></span>  
  
 <span data-ttu-id="532e1-112">Se si verifica il failover della replica di disponibilità che ospita gli snapshot del database, gli snapshot del database rimangono sull'istanza del server dove sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="532e1-112">If the availability replica that hosts database snapshots is failed over, the database snapshots remain on the server instance where they were created.</span></span> <span data-ttu-id="532e1-113">Gli utenti possono continuare a utilizzare gli snapshot dopo il failover. Se le prestazioni sono una preoccupazione, è consigliabile creare snapshot del database solo sui database secondari ospitati da una replica secondaria configurata per la modalità failover manuale.</span><span class="sxs-lookup"><span data-stu-id="532e1-113">Users can continue to use the snapshots after the failover.If performance is a concern in your environment, we recommend that you create database snapshots only on secondary databases that are hosted by a secondary replica that is configured for manual failover mode.</span></span>  <span data-ttu-id="532e1-114">Se si esegue il failover manuale del gruppo di disponibilità in questa replica secondaria, è possibile creare un nuovo set di snapshot del database su un'altra replica secondaria, reindirizzare i client ai nuovi snapshot del database ed eliminare tutti gli snapshot del database dai nuovi database primari.</span><span class="sxs-lookup"><span data-stu-id="532e1-114">If you ever manually fail over the availability group to this secondary replica, you can create a new set of database snapshots on another secondary replica, redirect clients to the new database snapshots, and drop all of the database snapshots from the now primary databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532e1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="532e1-115">See Also</span></span>  
 <span data-ttu-id="532e1-116">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="532e1-116">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="532e1-117">Snapshot del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="532e1-117">Database Snapshots &#40;SQL Server&#41;</span></span>](../../../relational-databases/databases/database-snapshots-sql-server.md)  
  
  
