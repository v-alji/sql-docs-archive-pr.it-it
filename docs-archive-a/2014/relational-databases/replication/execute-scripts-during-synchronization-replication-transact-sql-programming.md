---
title: Eseguire script durante la sincronizzazione (programmazione Transact-SQL della replica) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synchronization [SQL Server replication], scripts
- scripts [SQL Server replication], synchronization and
- sp_addscriptexec
ms.assetid: b58a0877-4e43-4fab-a281-24e6022d3fb1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bc217ad160a0238cc4247600d65eb32f156071f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624606"
---
# <a name="execute-scripts-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="55808-102">Esecuzione di script durante la sincronizzazione (programmazione Transact-SQL della replica)</span><span class="sxs-lookup"><span data-stu-id="55808-102">Execute Scripts During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="55808-103">La replica supporta l'esecuzione di script su richiesta per i Sottoscrittori di pubblicazioni transazionali e di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="55808-103">Replication supports on demand script execution for Subscribers to transactional and merge publications.</span></span> <span data-ttu-id="55808-104">Con questa funzionalità lo script viene copiato nella directory di lavoro della replica e quindi viene applicato al Sottoscrittore tramite **sqlcmd** .</span><span class="sxs-lookup"><span data-stu-id="55808-104">This functionality copies the script to the replication working directory and then uses **sqlcmd** to apply the script at the Subscriber.</span></span> <span data-ttu-id="55808-105">Per impostazione predefinita, se si verifica un errore durante l'applicazione dello script per una sottoscrizione di una pubblicazione transazionale, l'agente di distribuzione verrà arrestato.</span><span class="sxs-lookup"><span data-stu-id="55808-105">By default, if there is a failure when applying the script for a subscription to a transactional publication, the Distribution Agent will stop.</span></span> <span data-ttu-id="55808-106">È possibile specificare uno script [!INCLUDE[tsql](../../includes/tsql-md.md)] da eseguire a livello di programmazione tramite le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="55808-106">You can specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script to execute programmatically using replication stored procedures.</span></span>  
  
### <a name="to-specify-a-script-to-run-for-all-subscribers-to-a-snapshot-transactional-or-merge-publication"></a><span data-ttu-id="55808-107">Per specificare uno script da eseguire per tutti i Sottoscrittori di una pubblicazione snapshot, transazionale o di tipo merge</span><span class="sxs-lookup"><span data-stu-id="55808-107">To specify a script to run for all Subscribers to a snapshot, transactional or merge publication</span></span>  
  
1.  <span data-ttu-id="55808-108">Comporre e testare lo script [!INCLUDE[tsql](../../includes/tsql-md.md)] che verrà eseguito su richiesta.</span><span class="sxs-lookup"><span data-stu-id="55808-108">Compose and test the [!INCLUDE[tsql](../../includes/tsql-md.md)] script that will be executed on demand.</span></span>  
  
2.  <span data-ttu-id="55808-109">Salvare il file script in un percorso in cui sia accessibile all'agente snapshot per la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="55808-109">Save the script file to a location where it can be accessed by the Snapshot Agent for the publication.</span></span>  
  
3.  <span data-ttu-id="55808-110">Nel database di pubblicazione del server di pubblicazione eseguire [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55808-110">At the Publisher on the publication database, execute [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span> <span data-ttu-id="55808-111">Specificare \*\* \@ Publication**, il nome del file di script con il percorso UNC completo creato nel passaggio 2 per \*\* \@ scriptfile**e uno dei valori seguenti per \*\* \@ SkipError\*\*:</span><span class="sxs-lookup"><span data-stu-id="55808-111">Specify **\@publication**, the name of the script file with full UNC path created in step 2 for **\@scriptfile**, and one of the following values for **\@skiperror**:</span></span>  
  
    -   <span data-ttu-id="55808-112">**0** : l'agente arresterà l'esecuzione dello script se viene rilevato un errore.</span><span class="sxs-lookup"><span data-stu-id="55808-112">**0** - the agent will stop executing the script if an error is encountered.</span></span>  
  
    -   <span data-ttu-id="55808-113">**1** : l'agente registrerà gli errori e continuerà l'esecuzione dello script quando vengono rilevati errori.</span><span class="sxs-lookup"><span data-stu-id="55808-113">**1** - the agent will log errors and continue executing the script when errors are encountered.</span></span>  
  
4.  <span data-ttu-id="55808-114">Lo script specificato verrà eseguito in ogni Sottoscrittore la volta successiva che l'agente verrà eseguito per sincronizzare la sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="55808-114">The specified script will be executed at each Subscriber when the agent next runs to synchronize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55808-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55808-115">See Also</span></span>  
 [<span data-ttu-id="55808-116">Sincronizzare i dati</span><span class="sxs-lookup"><span data-stu-id="55808-116">Synchronize Data</span></span>](synchronize-data.md)  
  
  
