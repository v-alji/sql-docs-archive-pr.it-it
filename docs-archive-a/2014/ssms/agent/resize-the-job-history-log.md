---
title: Modificare le dimensioni del log di cronologia processi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], history
- resizing job history log
- size [SQL Server], job history log
- logs [SQL Server], jobs
- SQL Server Agent jobs, history
- historical information [SQL Server], jobs
ms.assetid: ddee1ce8-9d1b-4017-9894-bf7256aed95d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4c25cc43295d47b2bc19d48b5b257dbbe6bcfe9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627031"
---
# <a name="resize-the-job-history-log"></a><span data-ttu-id="e6d77-102">Modificare le dimensioni del log di cronologia processi</span><span class="sxs-lookup"><span data-stu-id="e6d77-102">Resize the Job History Log</span></span>
  <span data-ttu-id="e6d77-103">In questo argomento viene descritto come impostare i limiti delle dimensioni per i [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log della cronologia processi di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6d77-103">This topic describes how to set size limits for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job history logs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="e6d77-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="e6d77-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="e6d77-105">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e6d77-105">Security</span></span>](#Security)  
  
-   <span data-ttu-id="e6d77-106">**Per impostare le dimensioni massime dei log della cronologia dei processi utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="e6d77-106">**To set size limits for job history logs, using:**</span></span>  
  
     [<span data-ttu-id="e6d77-107">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6d77-107">SQL Server Management Studio</span></span>](#SSMS)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="e6d77-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="e6d77-108">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="e6d77-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="e6d77-109">Security</span></span>  
 <span data-ttu-id="e6d77-110">Per informazioni dettagliate, vedere [Implementazione della sicurezza di SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="e6d77-110">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="e6d77-111">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="e6d77-111">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-raw-size"></a><span data-ttu-id="e6d77-112">Per ridimensionare il log cronologia processi in base alle dimensioni dei dati non elaborati</span><span class="sxs-lookup"><span data-stu-id="e6d77-112">To resize the job history log based on raw size</span></span>  
  
1.  <span data-ttu-id="e6d77-113">In **Esplora oggetti** connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , quindi espandere l'istanza.</span><span class="sxs-lookup"><span data-stu-id="e6d77-113">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e6d77-114">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e6d77-114">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e6d77-115">Nella pagina **Cronologia** verificare che la casella di controllo **Limita dimensioni log cronologia processi**sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="e6d77-115">Select the **History** page, and then confirm that **Limit size of job history log**is checked.</span></span>  
  
4.  <span data-ttu-id="e6d77-116">Nella casella **Dimensioni massime log cronologia processi** immettere il numero massimo di righe consentito per il log cronologia processi.</span><span class="sxs-lookup"><span data-stu-id="e6d77-116">In the **Maximum job history log size** box, enter the maximum number of rows the job history log should allow.</span></span>  
  
5.  <span data-ttu-id="e6d77-117">Nella casella **Numero massimo di righe di cronologia per processo** immettere il numero massimo di righe di cronologia consentito per un processo.</span><span class="sxs-lookup"><span data-stu-id="e6d77-117">In the **Maximum job history rows per job** box, enter the maximum number of job history rows to allow for a job.</span></span>  
  
#### <a name="to-resize-the-job-history-log-based-on-time"></a><span data-ttu-id="e6d77-118">Per ridimensionare il log cronologia processi in base al tempo</span><span class="sxs-lookup"><span data-stu-id="e6d77-118">To resize the job history log based on time</span></span>  
  
1.  <span data-ttu-id="e6d77-119">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], quindi espandere questa istanza.</span><span class="sxs-lookup"><span data-stu-id="e6d77-119">In **Object Explorer**, connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="e6d77-120">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e6d77-120">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="e6d77-121">Nella scheda **Cronologia** fare clic su **Rimuovi automaticamente cronologia dell'agente**.</span><span class="sxs-lookup"><span data-stu-id="e6d77-121">Select the **History** page, and then click **Automatically remove agent history**.</span></span>  
  
4.  <span data-ttu-id="e6d77-122">Selezionare il numero appropriato di **giorno/i**, **settimana/e**o **mese/i**.</span><span class="sxs-lookup"><span data-stu-id="e6d77-122">Select the appropriate number of **Days(s)**, **Week(s)**, or **Month(s)**.</span></span>  
  
  
