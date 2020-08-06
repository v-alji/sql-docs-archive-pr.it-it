---
title: Aggiornamento di Monitoraggio attività processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.refresh.f1
ms.assetid: 413a368e-fd2b-4e1f-b370-002cdbc85bab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f290825f8a776c954ef802b184f7600aea5dc9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628682"
---
# <a name="job-activity-monitor-refresh"></a><span data-ttu-id="f0a15-102">Aggiornamento di Monitoraggio attività processi</span><span class="sxs-lookup"><span data-stu-id="f0a15-102">Job Activity Monitor Refresh</span></span>
  <span data-ttu-id="f0a15-103">Utilizzare la finestra di dialogo **Impostazioni aggiornamento** per configurare la frequenza di acquisizione di nuove informazioni sull'attività del server da parte di Monitoraggio attività processi.</span><span class="sxs-lookup"><span data-stu-id="f0a15-103">Use the **Refresh Settings** dialog box to configure how often Job Activity Monitor obtains new information about server activity.</span></span> <span data-ttu-id="f0a15-104">Monitoraggio attività processi deve eseguire query sul server monitorato per ottenere informazioni per la griglia Monitoraggio attività processi.</span><span class="sxs-lookup"><span data-stu-id="f0a15-104">Job Activity Monitor must run queries on the monitored server to obtain information for the Job Activity Monitor grid.</span></span> <span data-ttu-id="f0a15-105">Quando l'intervallo di aggiornamento automatico è impostato su un valore inferiore a 30 secondi, il tempo impiegato per eseguire queste query può ridurre le prestazioni del server.</span><span class="sxs-lookup"><span data-stu-id="f0a15-105">When the auto-refresh interval is set to less than 30 seconds, the time used to run these queries can affect server performance.</span></span>  
  
 <span data-ttu-id="f0a15-106">Per aprire questa finestra di dialogo fare clic su **Visualizza impostazioni di aggiornamento**nella sezione **Stato** di Monitoraggio attività processi.</span><span class="sxs-lookup"><span data-stu-id="f0a15-106">To open this dialog, click **View refresh settings**, in the **Status** section of Job Activity Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0a15-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f0a15-107">Options</span></span>  
 <span data-ttu-id="f0a15-108">**Aggiorna automaticamente ogni**</span><span class="sxs-lookup"><span data-stu-id="f0a15-108">**Auto-refresh every**</span></span>  
 <span data-ttu-id="f0a15-109">Selezionare questa opzione per iniziare l'aggiornamento automatico delle informazioni di Monitoraggio attività.</span><span class="sxs-lookup"><span data-stu-id="f0a15-109">Check to initiate automatic refreshing of Activity Monitor information.</span></span> <span data-ttu-id="f0a15-110">Questa opzione è deselezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f0a15-110">This is off by default.</span></span>  
  
 <span data-ttu-id="f0a15-111">**secondi**</span><span class="sxs-lookup"><span data-stu-id="f0a15-111">**seconds**</span></span>  
 <span data-ttu-id="f0a15-112">Il numero di secondi che intercorrono tra i tentativi di aggiornamento automatici.</span><span class="sxs-lookup"><span data-stu-id="f0a15-112">The number of seconds between auto-refresh attempts.</span></span> <span data-ttu-id="f0a15-113">Il valore predefinito è 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="f0a15-113">Defaults to 60 seconds.</span></span> <span data-ttu-id="f0a15-114">Quando questa opzione è impostata su un valore uguale o inferiore a 5 l'aggiornamento viene eseguito comunque ogni 5 secondi.</span><span class="sxs-lookup"><span data-stu-id="f0a15-114">Refreshes every 5 seconds when set to 5 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a15-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0a15-115">See Also</span></span>  
 [<span data-ttu-id="f0a15-116">Monitoraggio delle attività del processo</span><span class="sxs-lookup"><span data-stu-id="f0a15-116">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
