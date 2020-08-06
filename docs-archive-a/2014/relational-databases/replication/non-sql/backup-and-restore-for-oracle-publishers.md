---
title: Backup e ripristino di server di pubblicazione Oracle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], Oracle publishing
- backups [SQL Server replication], Oracle publishing
- Oracle publishing [SQL Server replication], backup and restore
- restoring [SQL Server replication], Oracle publishing
ms.assetid: e5f181d0-cacf-442b-8b7a-202b3cfc358b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6b994c34e4f4bebc010fe6d71bbd43f6e557cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624060"
---
# <a name="backup-and-restore-for-oracle-publishers"></a><span data-ttu-id="836e8-102">Backup e ripristino di server di pubblicazione Oracle</span><span class="sxs-lookup"><span data-stu-id="836e8-102">Backup and Restore for Oracle Publishers</span></span>
  <span data-ttu-id="836e8-103">Durante il backup e il ripristino, attenersi alle linee guida seguenti:</span><span class="sxs-lookup"><span data-stu-id="836e8-103">Follow these guidelines when backing up and restoring:</span></span>  
  
-   <span data-ttu-id="836e8-104">Verificare che l'agente di lettura log non sia in esecuzione e che non siano in corso altre attività di database sulle tabelle pubblicate durante il backup del server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="836e8-104">Ensure the Log Reader Agent does not run and that other database activity on the published tables does not occur while the Publisher is being backed up.</span></span>  
  
-   <span data-ttu-id="836e8-105">Eseguire il backup del server di pubblicazione e del server di distribuzione contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="836e8-105">Backup up the Publisher and Distributor at the same time.</span></span>  
  
-   <span data-ttu-id="836e8-106">Se è necessario ripristinare il server di pubblicazione o il server di distribuzione, reinizializzare tutte le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="836e8-106">If the Publisher or Distributor must be restored, reinitialize all subscriptions.</span></span>  
  
-   <span data-ttu-id="836e8-107">Per ripristinare un Sottoscrittore da un backup senza reinizializzarne le sottoscrizioni, devono essere ancora disponibili le transazioni recapitate al database di distribuzione dopo il completamento dell'ultimo backup del database di sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="836e8-107">To restore a Subscriber from a backup (without having to reinitialize subscriptions), the transactions delivered to the distribution database after the last subscription database backup was completed must still be available.</span></span> <span data-ttu-id="836e8-108">Il periodo di tempo in cui sono disponibili le transazioni dipende dalle impostazioni di memorizzazione per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="836e8-108">The length of time transactions are available depends on distribution retention settings.</span></span> <span data-ttu-id="836e8-109">Per informazioni su queste impostazioni, vedere [Scadenza e disattivazione delle sottoscrizioni](../subscription-expiration-and-deactivation.md).</span><span class="sxs-lookup"><span data-stu-id="836e8-109">For information on these settings, see [Subscription Expiration and Deactivation](../subscription-expiration-and-deactivation.md).</span></span>  
  
-   <span data-ttu-id="836e8-110">Se il server di pubblicazione o il server di distribuzione risulta non sincronizzato in seguito a un ripristino di database, gli agenti di replica registrano messaggi di errore.</span><span class="sxs-lookup"><span data-stu-id="836e8-110">If the Publisher or Distributor becomes out of sync as the result of a database restore, the replication agents log error messages.</span></span> <span data-ttu-id="836e8-111">A questo punto, è necessario eliminare e ricreare tutte le pubblicazioni e le sottoscrizioni significative:</span><span class="sxs-lookup"><span data-stu-id="836e8-111">At this point, you must drop and recreate all relevant publications and subscriptions:</span></span>  
  
    1.  <span data-ttu-id="836e8-112">Creare script per la definizione delle pubblicazioni e delle sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="836e8-112">Script the definition of the publications and subscriptions.</span></span> <span data-ttu-id="836e8-113">Per altre informazioni, vedere [Scripting Replication](../scripting-replication.md).</span><span class="sxs-lookup"><span data-stu-id="836e8-113">For more information, see [Scripting Replication](../scripting-replication.md).</span></span>  
  
         <span data-ttu-id="836e8-114">Se la definizione delle pubblicazioni è stata modificata tra le versioni degli stati del server di pubblicazione e del server di distribuzione, sarà necessario modificare gli script.</span><span class="sxs-lookup"><span data-stu-id="836e8-114">If the definition of the publications has changed between the versions of the Publisher and Distributor states, you will need to modify the scripts.</span></span>  
  
    2.  <span data-ttu-id="836e8-115">Eliminare le pubblicazioni e le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="836e8-115">Drop the publications and subscriptions.</span></span>  
  
    3.  <span data-ttu-id="836e8-116">Eseguire gli script creati nel passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="836e8-116">Run the scripts created in step 1.</span></span>  
  
     <span data-ttu-id="836e8-117">Se è necessario eliminare e riconfigurare il server di pubblicazione, eliminare il sinonimo public **MSSQLSERVERDISTRIBUTOR** e l'utente di replica Oracle configurato con l'opzione **CASCADE** per rimuovere tutti gli oggetti di replica dal server di pubblicazione Oracle.</span><span class="sxs-lookup"><span data-stu-id="836e8-117">If the Publisher must be dropped and reconfigured, drop the **MSSQLSERVERDISTRIBUTOR** public synonym and the configured Oracle replication user with the **CASCADE** option to remove all replication objects from the Oracle Publisher.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836e8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="836e8-118">See Also</span></span>  
 <span data-ttu-id="836e8-119">[Backup e ripristino di database replicati](../administration/back-up-and-restore-replicated-databases.md) </span><span class="sxs-lookup"><span data-stu-id="836e8-119">[Back Up and Restore Replicated Databases](../administration/back-up-and-restore-replicated-databases.md) </span></span>  
 <span data-ttu-id="836e8-120">[Configurare un server di pubblicazione Oracle](configure-an-oracle-publisher.md) </span><span class="sxs-lookup"><span data-stu-id="836e8-120">[Configure an Oracle Publisher](configure-an-oracle-publisher.md) </span></span>  
 [<span data-ttu-id="836e8-121">Panoramica della pubblicazione Oracle</span><span class="sxs-lookup"><span data-stu-id="836e8-121">Oracle Publishing Overview</span></span>](oracle-publishing-overview.md)  
  
  
