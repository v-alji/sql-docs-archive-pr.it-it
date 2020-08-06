---
title: Database crittografati con Gruppi di disponibilità AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Transparent Data Encryption, AlwaysOn Availability Groups
- TDE, AlwaysOn Availability Groups
- Availability Groups [SQL Server], interoperability
ms.assetid: 09eb6ebc-3051-4fff-86a5-93524507b1fc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 91e717a896634a7df5a96253c51207831f142cff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624953"
---
# <a name="encrypted-databases-with-alwayson-availability-groups-sql-server"></a><span data-ttu-id="b5467-102">Database crittografati con gruppi di disponibilità AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b5467-102">Encrypted Databases with AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="b5467-103">In questo argomento sono contenute informazioni su come utilizzare correttamente database crittografati o recentemente decrittografati con [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5467-103">This topic contains information about the using currently encrypted or recently decrypted databases with [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="b5467-104">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="b5467-104">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="b5467-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b5467-105">Limitations and Restrictions</span></span>](#Restrictions)  
  
-   [<span data-ttu-id="b5467-106">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="b5467-106">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b5467-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="b5467-107">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="b5467-108">Se un database viene crittografato o contiene una chiave di crittografia del database (DEK), non è possibile usare [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] o [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] per aggiungere il database a un gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="b5467-108">If a database is encrypted or even contains a Database Encryption Key (DEK), you cannot use the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] to add the database to an availability group.</span></span> <span data-ttu-id="b5467-109">Anche se è stato decrittografato un database crittografato, i backup del log potrebbero contenere dati crittografati.</span><span class="sxs-lookup"><span data-stu-id="b5467-109">Even if an encrypted database has been decrypted, its log backups might contain encrypted data.</span></span> <span data-ttu-id="b5467-110">In questo caso, la sincronizzazione dei dati iniziale completa potrebbe non riuscire sul database.</span><span class="sxs-lookup"><span data-stu-id="b5467-110">In this case, full initial data synchronization could fail on the database.</span></span> <span data-ttu-id="b5467-111">Questo avviene perché l'operazione di ripristino del log potrebbe richiedere il certificato usato dalle chiavi di crittografia del database e tale certificato potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="b5467-111">This is because the restore log operation might require the certificate that was used by the database encryption keys (DEKs), and that certificate might be unavailable.</span></span>  
  
     <span data-ttu-id="b5467-112">Affinché un database decrittografato sia idoneo a essere aggiunto a un gruppo di disponibilità usando la procedura guidata:</span><span class="sxs-lookup"><span data-stu-id="b5467-112">To make a decrypted database eligible to add to an availability group using the wizard:</span></span>  
  
    1.  <span data-ttu-id="b5467-113">Creare un backup del log del database primario.</span><span class="sxs-lookup"><span data-stu-id="b5467-113">Create a log backup of the primary database.</span></span>  
  
    2.  <span data-ttu-id="b5467-114">Creare un backup del log completo del database primario.</span><span class="sxs-lookup"><span data-stu-id="b5467-114">Create a full database backup of the primary database.</span></span>  
  
    3.  <span data-ttu-id="b5467-115">Ripristinare il backup del database nell'istanza del server in cui è ospitata la replica secondaria.</span><span class="sxs-lookup"><span data-stu-id="b5467-115">Restore the database backup on the server instance that hosts the secondary replica.</span></span>  
  
    4.  <span data-ttu-id="b5467-116">Creare un nuovo backup del log dal database primario.</span><span class="sxs-lookup"><span data-stu-id="b5467-116">Create a new log backup from primary database.</span></span>  
  
    5.  <span data-ttu-id="b5467-117">Ripristinare questo backup del log sul database secondario.</span><span class="sxs-lookup"><span data-stu-id="b5467-117">Restore this log backup on the secondary database.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="b5467-118">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="b5467-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="b5467-119">Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b5467-119">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="b5467-120">Usare la Creazione guidata Gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b5467-120">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="b5467-121">Usare la procedura guidata Aggiungi database a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="b5467-121">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="b5467-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5467-122">See Also</span></span>  
 <span data-ttu-id="b5467-123">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b5467-123">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="b5467-124">Transparent Data Encryption &#40;TDE&#41;</span><span class="sxs-lookup"><span data-stu-id="b5467-124">Transparent Data Encryption &#40;TDE&#41;</span></span>](../../../relational-databases/security/encryption/transparent-data-encryption.md)  
  
  
