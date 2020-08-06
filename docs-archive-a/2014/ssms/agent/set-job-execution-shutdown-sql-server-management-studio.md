---
title: Impostare l'arresto dell'esecuzione del processo (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
- SQL Server Agent jobs, execution shutdowns
ms.assetid: ac23e88f-53fc-41de-bb16-0c27c002d5a5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e60807676c3c54faf1d44de318ff0a31c2e20b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636526"
---
# <a name="set-job-execution-shutdown-sql-server-management-studio"></a><span data-ttu-id="43ee0-102">Set Job Execution Shutdown (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="43ee0-102">Set Job Execution Shutdown (SQL Server Management Studio)</span></span>
  <span data-ttu-id="43ee0-103">In questo argomento viene descritto come impostare il periodo di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attesa di Agent prima che l'esecuzione dei processi venga completata prima che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] l'agente venga terminato in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="43ee0-103">This topic describes how to set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="43ee0-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="43ee0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="43ee0-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="43ee0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="43ee0-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="43ee0-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="43ee0-107">**Per impostare il tempo di arresto per un processo di SQL Server Agent utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="43ee0-107">**To set a shutdown time for a SQL Server Agent job, using:**</span></span>  
  
     [<span data-ttu-id="43ee0-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43ee0-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="43ee0-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="43ee0-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="43ee0-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="43ee0-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="43ee0-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="43ee0-111">Permissions</span></span>  
 <span data-ttu-id="43ee0-112">Per impostazione predefinita, i membri del ruolo predefinito del server **sysadmin** possono impostare il periodo di attesa di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent prima di terminare l'esecuzione dei processi, trascorso il quale [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent stesso viene interrotto.</span><span class="sxs-lookup"><span data-stu-id="43ee0-112">By default, members of the **sysadmin** fixed server role can set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span> <span data-ttu-id="43ee0-113">Gli altri utenti devono essere membri di uno dei ruoli predefiniti del database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent seguenti nel database **msdb** :</span><span class="sxs-lookup"><span data-stu-id="43ee0-113">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="43ee0-114">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="43ee0-114">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="43ee0-115">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="43ee0-115">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="43ee0-116">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="43ee0-116">**SQLAgentOperatorRole**</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="43ee0-117">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="43ee0-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-execution-shutdown"></a><span data-ttu-id="43ee0-118">Per impostare l'arresto dell'esecuzione del processo</span><span class="sxs-lookup"><span data-stu-id="43ee0-118">To set job execution shutdown</span></span>  
  
1.  <span data-ttu-id="43ee0-119">In **Esplora oggetti** fare clic sul segno più per espandere il server in cui si desidera impostare un intervallo per l'arresto dell'esecuzione del processo.</span><span class="sxs-lookup"><span data-stu-id="43ee0-119">In **Object Explorer,** , click the plus sign to expand the server where you want to set a job execution shutdown interval.</span></span>  
  
2.  <span data-ttu-id="43ee0-120">Fare clic con il pulsante destro del mouse su **SQL Server Agent** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="43ee0-120">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="43ee0-121">In **Selezione pagina**selezionare **Sistema processi**.</span><span class="sxs-lookup"><span data-stu-id="43ee0-121">Under **Select a page**, select **Job System**.</span></span>  
  
4.  <span data-ttu-id="43ee0-122">Impostare l'opzione **Intervallo di time-out chiusura** (in secondi) per aumentare o ridurre l'intervallo di time-out di chiusura.</span><span class="sxs-lookup"><span data-stu-id="43ee0-122">Set the **Shutdown time-out interval** in seconds to increase or decrease the shutdown time-out interval.</span></span> <span data-ttu-id="43ee0-123">Questo valore determina l'intervallo di attesa del completamento dell'esecuzione dei processi da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, trascorso il quale viene interrotto anche [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="43ee0-123">This determines how long [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span>  
  
  
