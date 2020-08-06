---
title: Forzare un server di destinazione a eseguire il polling del server master | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- forcing master server polling
- polling master servers [SQL Server]
- master servers [SQL Server], polling
- target servers [SQL Server], polling the master server
ms.assetid: f1189a47-5ac3-45e2-9c5f-847810672279
author: stevestein
ms.author: sstein
ms.openlocfilehash: b37bf19bfe8e8fb55c29c8d94c28a341d06df5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623722"
---
# <a name="force-a-target-server-to-poll-the-master-server"></a><span data-ttu-id="68b2b-102">Forzare un server di destinazione a eseguire il polling del server master</span><span class="sxs-lookup"><span data-stu-id="68b2b-102">Force a Target Server to Poll the Master Server</span></span>
  <span data-ttu-id="68b2b-103">In questo argomento viene descritta la procedura per il polling forzato del server di destinazione al server master.</span><span class="sxs-lookup"><span data-stu-id="68b2b-103">This topic describes how to force a target server to poll the master server.</span></span> <span data-ttu-id="68b2b-104">Il server di destinazione deve essere registrato nel server master.</span><span class="sxs-lookup"><span data-stu-id="68b2b-104">The target server must be a registered server on the master server.</span></span>  
  
 <span data-ttu-id="68b2b-105">Un processo è una serie specificata di azioni eseguite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="68b2b-105">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="68b2b-106">Un processo multiserver è un processo eseguito da un server master in uno o più server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="68b2b-106">A multiserver job is a job that a master server runs on one or more target servers.</span></span> <span data-ttu-id="68b2b-107">Ogni server di destinazione può eseguire contemporaneamente una sola istanza dello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="68b2b-107">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="68b2b-108">Ogni server di destinazione esegue periodicamente il polling del server master, scarica una copia dei nuovi processi assegnati al server di destinazione, quindi si disconnette.</span><span class="sxs-lookup"><span data-stu-id="68b2b-108">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="68b2b-109">Il server di destinazione esegue il processo in locale, quindi si riconnette al server master per caricare lo stato del risultato del processo una volta terminato.</span><span class="sxs-lookup"><span data-stu-id="68b2b-109">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68b2b-110">Se il server master non è accessibile quando il server di destinazione tenta di caricare lo stato del processo, per tale stato viene eseguito lo spooling fino a quando non è possibile accedere al server master.</span><span class="sxs-lookup"><span data-stu-id="68b2b-110">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
-   <span data-ttu-id="68b2b-111">**Prima di iniziare:**  [Limitazioni e restrizioni](#Restrictions), [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="68b2b-111">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="68b2b-112">**Per forzare un server di destinazione a eseguire il polling del server master con:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="68b2b-112">**To force a target server to poll the master server, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="68b2b-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="68b2b-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="68b2b-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="68b2b-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="68b2b-115">Il server di destinazione deve essere registrato nel server master.</span><span class="sxs-lookup"><span data-stu-id="68b2b-115">The target server must be a registered server on the master server.</span></span> <span data-ttu-id="68b2b-116">È necessario eseguire le istruzioni fornite in questo argomento dal server master.</span><span class="sxs-lookup"><span data-stu-id="68b2b-116">You must run the instructions given in this topic from the master server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="68b2b-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="68b2b-117">Security</span></span>  
 <span data-ttu-id="68b2b-118">Per informazioni dettagliate, vedere [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) e [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="68b2b-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="68b2b-119">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="68b2b-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="68b2b-120">**Per forzare un server di destinazione a eseguire il polling del server master**</span><span class="sxs-lookup"><span data-stu-id="68b2b-120">**To force a target server to poll the master server**</span></span>  
  
1.  <span data-ttu-id="68b2b-121">In **Esplora oggetti**espandere il server master.</span><span class="sxs-lookup"><span data-stu-id="68b2b-121">In **Object Explorer**, expand the master server.</span></span>  
  
2.  <span data-ttu-id="68b2b-122">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e fare clic su **Gestione server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-122">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="68b2b-123">Selezionare un server di destinazione e fare clic su **Forza polling**.</span><span class="sxs-lookup"><span data-stu-id="68b2b-123">Click a target server, and then click **Force Poll**.</span></span>  
  
  
