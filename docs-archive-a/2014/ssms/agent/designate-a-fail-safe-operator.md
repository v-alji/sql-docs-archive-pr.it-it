---
title: Impostare un operatore alternativo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- fail-safe operator [SQL Server]
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 0f4eb513-5c0a-4523-974e-e85c1deeb57f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 714ed78875bd289f2fe2d64a5699c59bce58ced0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722203"
---
# <a name="designate-a-fail-safe-operator"></a><span data-ttu-id="61d2f-102">Impostazione di un operatore alternativo</span><span class="sxs-lookup"><span data-stu-id="61d2f-102">Designate a Fail-Safe Operator</span></span>
  <span data-ttu-id="61d2f-103">Un operatore alternativo è un utente che riceve l'avviso nel caso in cui l'operatore designato non sia raggiungibile.</span><span class="sxs-lookup"><span data-stu-id="61d2f-103">A fail-safe operator is a user who receives the alert if the designated operator cannot be reached.</span></span> <span data-ttu-id="61d2f-104">In questo argomento viene descritto come impostare un operatore alternativo per la ricezione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] notifiche di avviso di Agent in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="61d2f-104">This topic describes how to set a fail-safe operator to receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="61d2f-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="61d2f-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="61d2f-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="61d2f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="61d2f-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="61d2f-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="61d2f-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="61d2f-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="61d2f-109">**Per impostare un operatore alternativo utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="61d2f-109">**To designate a fail-safe operator, using:**</span></span>  
  
     [<span data-ttu-id="61d2f-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61d2f-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="61d2f-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="61d2f-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="61d2f-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="61d2f-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="61d2f-113">Le opzioni Cercapersone e **net send** verranno rimosse da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in una versione futura di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="61d2f-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="61d2f-114">Evitare pertanto di utilizzarle in un nuovo progetto di sviluppo e prevedere interventi di modifica nelle applicazioni in cui sono state implementate.</span><span class="sxs-lookup"><span data-stu-id="61d2f-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="61d2f-115">Si noti che per inviare notifiche tramite posta elettronica e cercapersone agli operatori, è necessario configurare SQL Server Agent per l'utilizzo di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="61d2f-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="61d2f-116">Per ulteriori informazioni, vedere [Procedura: Assegnazione di avvisi a un operatore (SQL Server Management Studio)](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="61d2f-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="61d2f-117">è incluso un semplice strumento grafico per la gestione dei processi, che è lo strumento consigliato per la creazione e la gestione dell'infrastruttura dei processi.</span><span class="sxs-lookup"><span data-stu-id="61d2f-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="61d2f-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="61d2f-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="61d2f-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="61d2f-119">Permissions</span></span>  
 <span data-ttu-id="61d2f-120">Solo i membri del ruolo predefinito del server **sysadmin** possono definire operatori alternativi.</span><span class="sxs-lookup"><span data-stu-id="61d2f-120">Only members of the **sysadmin** fixed server role can designate fail-safe operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="61d2f-121">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="61d2f-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-a-fail-safe-operator"></a><span data-ttu-id="61d2f-122">Per impostare un operatore alternativo</span><span class="sxs-lookup"><span data-stu-id="61d2f-122">To designate a fail-safe operator</span></span>  
  
1.  <span data-ttu-id="61d2f-123">In **Esplora oggetti** fare clic sul segno più per espandere il server che contiene l'operatore di SQL Server Agent che si vuole definire come alternativo.</span><span class="sxs-lookup"><span data-stu-id="61d2f-123">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent operator that you want to designate as a fail-safe.</span></span>  
  
2.  <span data-ttu-id="61d2f-124">Fare clic con il pulsante destro del mouse su **SQL Server Agent** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="61d2f-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="61d2f-125">Nella finestra di dialogo **proprietà SQL Server Agent-**_server_name_ , in **Selezione pagina**selezionare **sistema avvisi**.</span><span class="sxs-lookup"><span data-stu-id="61d2f-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Alert System**.</span></span>  
 
4.  <span data-ttu-id="61d2f-126">In **Operatore alternativo**selezionare **Abilita operatore alternativo**.</span><span class="sxs-lookup"><span data-stu-id="61d2f-126">Under **Fail-safe operator**, select **Enable fail-safe operator**.</span></span>  
  
5.  <span data-ttu-id="61d2f-127">Nell'elenco **Operatore** selezionare l'operatore che si vuole rendere alternativo.</span><span class="sxs-lookup"><span data-stu-id="61d2f-127">In the **Operator** list, select the operator that you want to make a fail-safe.</span></span>  
  
6.  <span data-ttu-id="61d2f-128">Selezionare tutte le caselle di controllo necessarie a specificare come l'operatore riceverà la notifica: **Posta elettronica**, **Cercapersone**o **Net Send**.</span><span class="sxs-lookup"><span data-stu-id="61d2f-128">Select either any or all of the following check boxes to specify how the operator will be notified: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="61d2f-129">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="61d2f-129">When finished, click **OK**.</span></span>  
  
  
