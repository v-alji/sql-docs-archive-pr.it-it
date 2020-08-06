---
title: Impostare l'intervallo di polling per i server di destinazione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- interval for polling [SQL Server]
- target servers [SQL Server], polling interval
- polling interval [SQL Server]
ms.assetid: 4ffbbefa-77fb-442e-a77c-cb8c6cab9f3c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 36517f60a99a1a844f6d14d489587eef1de9cb13
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726412"
---
# <a name="set-the-polling-interval-for-target-servers"></a><span data-ttu-id="1b5f9-102">Impostare l'intervallo di polling per i server di destinazione</span><span class="sxs-lookup"><span data-stu-id="1b5f9-102">Set the Polling Interval for Target Servers</span></span>
  <span data-ttu-id="1b5f9-103">In questo argomento viene descritto come impostare la frequenza con cui [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent aggiorna le informazioni dal master ai server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-103">This topic describes how to set the frequency that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent refreshes information from the master to the target servers.</span></span> <span data-ttu-id="1b5f9-104">Un processo è una serie specificata di azioni eseguite da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-104">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="1b5f9-105">Un processo multiserver è un processo eseguito da un server master in uno o più server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-105">A multiserver job is a job that a master server runs on one or more target servers.</span></span>  
  
-   <span data-ttu-id="1b5f9-106">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="1b5f9-106">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="1b5f9-107">**Per impostare l'intervallo di polling per i server di destinazione usando:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span><span class="sxs-lookup"><span data-stu-id="1b5f9-107">**To set the polling interval for target servers, using:**  [SQL Server Management Studio](#SSMS), [Transact-SQL](#TSQL)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1b5f9-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1b5f9-108">Before You Begin</span></span>  
 <span data-ttu-id="1b5f9-109">Ogni server di destinazione può eseguire contemporaneamente una sola istanza dello stesso processo.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-109">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="1b5f9-110">Ogni server di destinazione esegue periodicamente il polling del server master, scarica una copia dei nuovi processi assegnati al server di destinazione, quindi si disconnette.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-110">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="1b5f9-111">Il server di destinazione esegue il processo in locale, quindi si riconnette al server master per caricare lo stato del risultato del processo una volta terminato.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-111">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1b5f9-112">Se il server master non è accessibile quando il server di destinazione tenta di caricare lo stato del processo, per tale stato viene eseguito lo spooling fino a quando non è possibile accedere al server master.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-112">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1b5f9-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1b5f9-113">Security</span></span>  
 <span data-ttu-id="1b5f9-114">Per informazioni dettagliate, vedere [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) e [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="1b5f9-114">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="1b5f9-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1b5f9-115">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="1b5f9-116">**Per impostare l'intervallo di polling per i server di destinazione**</span><span class="sxs-lookup"><span data-stu-id="1b5f9-116">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="1b5f9-117">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-117">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1b5f9-118">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e fare clic su **Gestione server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="1b5f9-119">Nella scheda **Stato server di destinazione** fare clic su **Invia istruzioni**.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-119">On the **Target Server Status** tab, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="1b5f9-120">Nell'elenco **Tipo istruzione** selezionare **Imposta intervallo di polling**.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-120">In the **Instruction type** list, select **Set polling interval**.</span></span>  
  
5.  <span data-ttu-id="1b5f9-121">Nella casella **Intervallo di polling** immettere un numero di secondi compreso tra 10 e 28.800 per indicare l'intervallo di esecuzione del polling dal server di destinazione al server master.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-121">In the **Polling interval** box, enter the number of seconds from 10 through 28,800 that must pass before the target server polls the master server.</span></span>  
  
6.  <span data-ttu-id="1b5f9-122">In **Destinatari**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1b5f9-122">Under **Recipients**, do one of the following:</span></span>  
  
    1.  <span data-ttu-id="1b5f9-123">Fare clic su **Tutti i server di destinazione** se tutti i server di destinazione condividono lo stesso intervallo di polling.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-123">Click **All target servers** if all target servers share the same polling interval.</span></span>  
  
    2.  <span data-ttu-id="1b5f9-124">Fare clic su **Solo i server di destinazione seguenti** se non tutti i server di destinazione condividono lo stesso intervallo di polling e quindi selezionare ogni server di destinazione che utilizzerà l'intervallo specifico.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-124">Click **These target servers** if not all target servers share the same polling interval, and then select each target server that will use this polling interval.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="1b5f9-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b5f9-125">Using Transact-SQL</span></span>  
 <span data-ttu-id="1b5f9-126">**Per impostare l'intervallo di polling per i server di destinazione**</span><span class="sxs-lookup"><span data-stu-id="1b5f9-126">**To set the polling interval for target servers**</span></span>  
  
1.  <span data-ttu-id="1b5f9-127">In Esplora oggetti connettersi a un'istanza del motore di database ed espanderla.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-127">In Object Explorer, connect to an instance of the Database Engine, and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="1b5f9-128">Sulla barra degli strumenti fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-128">On the toolbar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1b5f9-129">Nella finestra query utilizzare il [sp_post_msx_operation &#40;sistema Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) stored procedure per impostare l'intervallo di polling per i server di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1b5f9-129">In the query window, use the [sp_post_msx_operation &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql) system stored procedure to set the polling interval for target servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5f9-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b5f9-130">See Also</span></span>  
 [<span data-ttu-id="1b5f9-131">dbo.sysdownload &#40;&#41;Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1b5f9-131">dbo.sysdownloadlist &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-tables/dbo-sysdownloadlist-transact-sql)  
  
  
