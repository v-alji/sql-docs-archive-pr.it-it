---
title: Impostare il log di cronologia processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: 018e5c49-d3a0-4504-851a-f70996a34bb7
author: stevestein
ms.author: sstein
ms.openlocfilehash: cb42e1daaee8a3a9e5ae9cc3c09a8cc42dcbff56
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711571"
---
# <a name="set-up-the-job-history-log"></a><span data-ttu-id="58205-102">Impostare il log di cronologia processi</span><span class="sxs-lookup"><span data-stu-id="58205-102">Set Up the Job History Log</span></span>
  <span data-ttu-id="58205-103">In questo argomento viene descritto come configurare il [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log cronologia processi di Agent.</span><span class="sxs-lookup"><span data-stu-id="58205-103">This topic describes how to set up the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history log.</span></span>  
  
-   <span data-ttu-id="58205-104">**Prima di iniziare:**  [Sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="58205-104">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="58205-105">**Per impostare il log di cronologia processi usando:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="58205-105">**To setup the job history log, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="58205-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="58205-106">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="58205-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="58205-107">Security</span></span>  
 <span data-ttu-id="58205-108">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="58205-108">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="58205-109">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="58205-109">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="58205-110">**Per impostare il log di cronologia processo**</span><span class="sxs-lookup"><span data-stu-id="58205-110">**To set up the job history log**</span></span>  
  
1.  <span data-ttu-id="58205-111">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="58205-111">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="58205-112">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="58205-112">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="58205-113">Nella finestra di dialogo **Proprietà SQL Server Agent** selezionare la pagina **Cronologia** .</span><span class="sxs-lookup"><span data-stu-id="58205-113">In the **SQL Server Agent Properties** dialog box, select the **History** page.</span></span>  
  
4.  <span data-ttu-id="58205-114">È possibile scegliere una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="58205-114">Choose from the following options:</span></span>  
  
    1.  <span data-ttu-id="58205-115">Selezionare **Limita dimensioni log cronologia processo**e quindi immettere il numero massimo di righe consentito per il log di cronologia processo e il numero massimo di righe per processo.</span><span class="sxs-lookup"><span data-stu-id="58205-115">Check **Limit size of job history log**, and then type the maximum number of rows for the job history log, and the maximum number of rows per job.</span></span>  
  
    2.  <span data-ttu-id="58205-116">Selezionare **Rimuovi automaticamente cronologia dell'agente**e quindi specificare un periodo di tempo, in modo che la cronologia precedente a tale periodo venga eliminata dal log.</span><span class="sxs-lookup"><span data-stu-id="58205-116">Check **Automatically remove agent history**, and specify a time period, such that history older than this period will be purged from the log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58205-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58205-117">See Also</span></span>  
 <span data-ttu-id="58205-118">[Implementazione di processi](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="58205-118">[Implement Jobs](implement-jobs.md) </span></span>  
 <span data-ttu-id="58205-119">[Monitorare l'attività del processo](monitor-job-activity.md) </span><span class="sxs-lookup"><span data-stu-id="58205-119">[Monitor Job Activity](monitor-job-activity.md) </span></span>  
 [<span data-ttu-id="58205-120">Creazione di processi</span><span class="sxs-lookup"><span data-stu-id="58205-120">Create Jobs</span></span>](create-jobs.md)  
  
  
