---
title: Impostare il tempo e l'intervallo di inattività della CPU (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- CPU [SQL Server], idle conditions
- time [SQL Server], CPU idle and duration
- duration of CPU idle [SQL Server]
- SQL Server Agent, CPU idle conditions
- idle time [SQL Server]
ms.assetid: 8647b465-d899-4cc7-9640-134a506d0a2e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1660f6d70977b8f590a18adf952a6a19f32a26cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726416"
---
# <a name="set-cpu-idle-time-and-duration-sql-server-management-studio"></a><span data-ttu-id="a8c36-102">Impostazione del tempo e della durata di inattività della CPU (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="a8c36-102">Set CPU Idle Time and Duration (SQL Server Management Studio)</span></span>
  <span data-ttu-id="a8c36-103">In questo argomento viene illustrato come definire la condizione di inattività della CPU per il server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8c36-103">This topic explains how to define the CPU idle condition for your server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="a8c36-104">La definizione di inattività della CPU influisce sul modo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui Agent risponde agli eventi.</span><span class="sxs-lookup"><span data-stu-id="a8c36-104">The CPU idle definition influences how [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent responds to events.</span></span> <span data-ttu-id="a8c36-105">Si supponga, ad esempio, di considerare la CPU inattiva quando l'utilizzo medio scende sotto il 10% e rimane tale per 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="a8c36-105">For example, suppose that you define the CPU idle condition as when the average CPU usage falls below 10 percent and remains at this level for 10 minutes.</span></span> <span data-ttu-id="a8c36-106">Se sono stati definiti processi da eseguire quando la CPU del server raggiunge una condizione di inattività, questi verranno avviati quando l'utilizzo della CPU scende sotto il 10% e rimane tale per 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="a8c36-106">Then if you have defined jobs to execute whenever the server CPU reaches an idle condition, the job will start when the CPU usage falls below 10 percent and remains at that level for 10 minutes.</span></span> <span data-ttu-id="a8c36-107">Se si tratta di processi che influiscono significativamente sulle prestazioni del server, la corretta definizione della condizione di inattività della CPU è particolarmente importante.</span><span class="sxs-lookup"><span data-stu-id="a8c36-107">If this is a job that significantly impacts the performance of your server, how you define the CPU idle condition is important.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a8c36-108">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a8c36-108">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-cpu-idle-time-and-duration"></a><span data-ttu-id="a8c36-109">Per impostare il tempo e l'intervallo di inattività della CPU</span><span class="sxs-lookup"><span data-stu-id="a8c36-109">To set CPU idle time and duration</span></span>  
  
1.  <span data-ttu-id="a8c36-110">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="a8c36-110">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="a8c36-111">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Proprietà**e selezionare la pagina **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="a8c36-111">Right-click **SQL Server Agent**, click **Properties**, and select the **Advanced** page.</span></span>  
  
3.  <span data-ttu-id="a8c36-112">In **Condizione di inattività CPU**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8c36-112">Under **Idle CPU condition**, do the following:</span></span>  
  
    -   <span data-ttu-id="a8c36-113">Selezionare la casella di controllo **Imposta condizione di inattività CPU**.</span><span class="sxs-lookup"><span data-stu-id="a8c36-113">Check **Define idle CPU condition.**</span></span>  
  
    -   <span data-ttu-id="a8c36-114">Specificare una percentuale nella casella **L'uso medio della CPU è inferiore al** (per tutte le CPU).</span><span class="sxs-lookup"><span data-stu-id="a8c36-114">Specify a percentage for the **Average CPU usage falls below** (across all CPUs) box.</span></span> <span data-ttu-id="a8c36-115">In questo modo verrà impostato il livello di utilizzo al di sotto del quale la CPU viene considerata inattiva.</span><span class="sxs-lookup"><span data-stu-id="a8c36-115">This sets the usage level that the CPU must fall below before it is considered idle.</span></span>  
  
    -   <span data-ttu-id="a8c36-116">Specificare un numero di secondi nella casella **per almeno** .</span><span class="sxs-lookup"><span data-stu-id="a8c36-116">Specify a number of seconds for the **And remains below this level for** box.</span></span> <span data-ttu-id="a8c36-117">In questo modo verrà impostato l'intervallo relativo all'utilizzo minimo trascorso il quale la CPU viene considerata inattiva.</span><span class="sxs-lookup"><span data-stu-id="a8c36-117">This sets the duration that the minimum CPU usage must remain at before it is considered idle.</span></span>  
  
  
