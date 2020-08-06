---
title: Risolvere i problemi relativi a processi multiserver che usano proxy | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- proxies [SQL Server Agent], multiserver jobs
- jobs [SQL Server Agent], multiserver jobs using proxies
ms.assetid: fc579bd3-010c-4f72-8b5c-d0cc18a1f280
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19de975ef5e1f22c93cec72a5014a01da5b03dd8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714987"
---
# <a name="troubleshoot-multiserver-jobs-that-use-proxies"></a><span data-ttu-id="38995-102">Risolvere i problemi relativi a processi multiserver che utilizzano proxy</span><span class="sxs-lookup"><span data-stu-id="38995-102">Troubleshoot Multiserver Jobs That Use Proxies</span></span>
  <span data-ttu-id="38995-103">I processi distribuiti con passaggi associati a un proxy vengono eseguiti nel contesto dell'account proxy nel server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="38995-103">Distributed jobs whose steps are associated with a proxy run under the context of the proxy account on the target server.</span></span> <span data-ttu-id="38995-104">Se si verificano errori quando i passaggi di processo che usano account proxy vengono scaricati dal server master, controllare la colonna **error_message** nella tabella **sysdownloadlist** del database **msdb** per verificare l'eventuale presenza dei messaggi di errore seguenti:</span><span class="sxs-lookup"><span data-stu-id="38995-104">If job steps that use proxy accounts fail when downloaded from the master server, check the **error_message** column in the **sysdownloadlist** table in the **msdb** database for the following error messages:</span></span>  
  
-   <span data-ttu-id="38995-105">"Per questo passaggio del processo è necessario un account proxy, ma l'individuazione dei proxy è disabilitata nel server di destinazione."</span><span class="sxs-lookup"><span data-stu-id="38995-105">"The job step requires a proxy account, however proxy matching is disabled on the target server."</span></span>  
  
     <span data-ttu-id="38995-106">Per correggere l'errore, impostare **\ HKEY_LOCAL_MACHINE \SOFTWARE\MICROSOFT\MICROSOFT SQL Server\MSSQL.** _ \<n_> **\SQLServerAgent\AllowDownloadedJobsToMatchProxyName su** sottochiave del registro di sistema a **1 (true)**.</span><span class="sxs-lookup"><span data-stu-id="38995-106">To resolve this error, set the **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL.**_\<n_>**\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** registry subkey to **1 (true)**.</span></span> <span data-ttu-id="38995-107">Per impostazione predefinita, questa sottochiave è impostata su **0** ( `false` ).</span><span class="sxs-lookup"><span data-stu-id="38995-107">By default, this subkey is set to **0** (`false`).</span></span> <span data-ttu-id="38995-108">Il valore di **MSSQL.**\<*n*></span><span class="sxs-lookup"><span data-stu-id="38995-108">The value of **MSSQL.**\<*n*></span></span> <span data-ttu-id="38995-109">nome dell'istanza. ad esempio **MSSQL. 1** o **MSSQL. 3**.</span><span class="sxs-lookup"><span data-stu-id="38995-109">is the instance name; for example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
-   <span data-ttu-id="38995-110">"Impossibile trovare il proxy."</span><span class="sxs-lookup"><span data-stu-id="38995-110">"Proxy not found."</span></span>  
  
     <span data-ttu-id="38995-111">Per risolvere il problema, verificare che nel server di destinazione sia disponibile un account proxy con lo stesso nome dell'account proxy del server master utilizzato per l'esecuzione del passaggio del processo.</span><span class="sxs-lookup"><span data-stu-id="38995-111">To resolve this error, make sure a proxy account exists on the target server with the same name as the master server proxy account under which the job step runs.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38995-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38995-112">See Also</span></span>  
 [<span data-ttu-id="38995-113">Creazione di un ambiente multiserver</span><span class="sxs-lookup"><span data-stu-id="38995-113">Create a Multiserver Environment</span></span>](create-a-multiserver-environment.md)  
  
  
