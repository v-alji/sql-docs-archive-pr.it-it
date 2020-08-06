---
title: Eseguire il polling dei server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- target servers [SQL Server], polling interval
- polling master servers [SQL Server]
- server polling [SQL Server]
- master servers [SQL Server], polling
- polling interval [SQL Server]
ms.assetid: 96f5fd43-3edd-4418-9dd0-4d34e618890e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6370e53083d2cf818e8c8b09752d49e092755a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630242"
---
# <a name="poll-servers"></a><span data-ttu-id="bc70f-102">Polling dei server</span><span class="sxs-lookup"><span data-stu-id="bc70f-102">Poll Servers</span></span>
  <span data-ttu-id="bc70f-103">Quando viene implementata un'amministrazione multiserver, i server di destinazione contattano periodicamente il server master per caricare le informazioni relative ai processi eseguiti e per eseguire il download di nuovi processi.</span><span class="sxs-lookup"><span data-stu-id="bc70f-103">When multiserver administration is implemented, target servers periodically contact the master server to upload information on jobs that have been executed, and download new jobs.</span></span> <span data-ttu-id="bc70f-104">L'operazione in cui viene contattato il server master, chiamata *polling del server* , viene eseguita a *intervalli di polling*regolari.</span><span class="sxs-lookup"><span data-stu-id="bc70f-104">The process of contacting the master server is called *server polling,* which takes place at regular *polling intervals.*</span></span>  
  
## <a name="polling-intervals"></a><span data-ttu-id="bc70f-105">Intervalli di polling</span><span class="sxs-lookup"><span data-stu-id="bc70f-105">Polling Intervals</span></span>  
 <span data-ttu-id="bc70f-106">L'intervallo di polling, la cui impostazione predefinita è un minuto, controlla la frequenza con cui il server di destinazione contatta il server master per eseguire il download delle istruzioni e per caricare i risultati dell'esecuzione dei processi.</span><span class="sxs-lookup"><span data-stu-id="bc70f-106">The polling interval (one minute by default) controls how frequently the target server connects to the master server to download instructions and upload the results of job execution.</span></span>  
  
 <span data-ttu-id="bc70f-107">Quando un server di destinazione esegue il polling del server master, legge le operazioni assegnate al server di destinazione dalla tabella **sysdownloadlist** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="bc70f-107">When a target server polls the master server, it reads the operations assigned to the target server from the **sysdownloadlist** table in the **msdb** database.</span></span> <span data-ttu-id="bc70f-108">Queste operazioni controllano i processi multiserver e vari aspetti del funzionamento del server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bc70f-108">These operations control multiserver jobs and various aspects of the behavior of a target server.</span></span> <span data-ttu-id="bc70f-109">Sono esempi di operazioni l'eliminazione, l'inserimento e l'avvio di un processo o l'aggiornamento dell'intervallo di polling di un server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bc70f-109">Examples of operations include deleting a job, inserting a job, starting a job, and updating the polling interval of a target server.</span></span>  
  
 <span data-ttu-id="bc70f-110">Le operazioni vengono inviate alla tabella **sysdownloadlist** in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc70f-110">Operations are posted to the **sysdownloadlist** table in either of the following ways:</span></span>  
  
-   <span data-ttu-id="bc70f-111">In modo esplicito tramite la stored procedure **sp_post_msx_operation** .</span><span class="sxs-lookup"><span data-stu-id="bc70f-111">Explicitly by using the **sp_post_msx_operation** stored procedure.</span></span>  
  
-   <span data-ttu-id="bc70f-112">In modo implicito tramite altre stored procedure di processo.</span><span class="sxs-lookup"><span data-stu-id="bc70f-112">Implicitly by using other job stored procedures.</span></span>  
  
 <span data-ttu-id="bc70f-113">Se si utilizzano stored procedure di processo per modificare passaggi o pianificazioni di processo multiserver, oppure oggetti SQL-DMO (SQL Distributed Management Object) per controllare processi multiserver, eseguire il comando seguente dopo la modifica delle pianificazioni o dei passaggi di un processo multiserver:</span><span class="sxs-lookup"><span data-stu-id="bc70f-113">If you use job stored procedures to modify multiserver job schedules or job steps, or SQL Distributed Management Objects (SQL-DMO) to control multiserver jobs, issue the following command after modifying a multiserver job's steps or schedules:</span></span>  
  
```  
EXECUTE msdb.dbo.sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 <span data-ttu-id="bc70f-114">Il comando consente di mantenere i server di destinazione sincronizzati con la definizione del processo corrente.</span><span class="sxs-lookup"><span data-stu-id="bc70f-114">Issue this command keeps the target servers synchronized with the current job definition.</span></span>  
  
 <span data-ttu-id="bc70f-115">Non è necessario inviare operazioni in modo esplicito se si utilizza:</span><span class="sxs-lookup"><span data-stu-id="bc70f-115">You do not have to post operations explicitly if you use the following:</span></span>  
  
-   <span data-ttu-id="bc70f-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per controllare i processi multiserver.</span><span class="sxs-lookup"><span data-stu-id="bc70f-116">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to control multiserver jobs.</span></span>  
  
-   <span data-ttu-id="bc70f-117">Stored procedure di processo che non modificano pianificazioni o passaggi di processo.</span><span class="sxs-lookup"><span data-stu-id="bc70f-117">Job stored procedures that do not modify job schedules or job steps.</span></span>  
  
 <span data-ttu-id="bc70f-118">**Per forzare un server di destinazione a eseguire il polling del server master**</span><span class="sxs-lookup"><span data-stu-id="bc70f-118">**To force a target server to poll the master server**</span></span>  
  
-   [<span data-ttu-id="bc70f-119">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bc70f-119">SQL Server Management Studio</span></span>](force-a-target-server-to-poll-the-master-server.md)  
  
-   [<span data-ttu-id="bc70f-120">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bc70f-120">Transact-SQL</span></span>](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="bc70f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc70f-121">See Also</span></span>  
 [<span data-ttu-id="bc70f-122">Gestione di eventi</span><span class="sxs-lookup"><span data-stu-id="bc70f-122">Manage Events</span></span>](manage-events.md)  
  
  
