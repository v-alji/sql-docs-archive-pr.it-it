---
title: Programma esterno di Posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- external programs [Database Mail]
- DatabaseMail90.exe
- Database Mail [SQL Server], external programs
ms.assetid: bc124164-eb6e-4b7f-bf66-98a3113d02f7
author: stevestein
ms.author: sstein
ms.openlocfilehash: 698fc8d97a565b4181552691a0260486c9c43bfd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725948"
---
# <a name="database-mail-external-program"></a><span data-ttu-id="1a11f-102">Programma esterno di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="1a11f-102">Database Mail External Program</span></span>
  <span data-ttu-id="1a11f-103">L'eseguibile esterno di Posta elettronica database è **DatabaseMail.exe**, situato nella **directory MSSQL\Binn** dell'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a11f-103">The Database Mail external executable is **DatabaseMail.exe**, located in the **MSSQL\Binn directory** of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation.</span></span> <span data-ttu-id="1a11f-104">Posta elettronica database utilizza l'attivazione di Service Broker per avviare il programma esterno in presenza di messaggi di posta elettronica da elaborare.</span><span class="sxs-lookup"><span data-stu-id="1a11f-104">Database Mail uses Service Broker activation to start the external program when there are e-mail messages to be processed.</span></span> <span data-ttu-id="1a11f-105">Posta elettronica database avvia un'istanza del programma esterno.</span><span class="sxs-lookup"><span data-stu-id="1a11f-105">Database Mail starts one instance of the external program.</span></span> <span data-ttu-id="1a11f-106">Il programma esterno viene eseguito nel contesto di sicurezza dell'account di servizio per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a11f-106">The external program runs in the security context of the service account for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="1a11f-107">**Contenuto dell'argomento**</span><span class="sxs-lookup"><span data-stu-id="1a11f-107">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="1a11f-108">Concetti relativi al Programma esterno di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="1a11f-108">Database Mail External Program Concepts</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="1a11f-109">Attività correlate alla configurazione del Programma esterno di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="1a11f-109">Tasks Related to Configuring Database Mail External Program</span></span>](#RelatedTasks)  
  
##  <a name="database-mail-external-program-concepts"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="1a11f-110">Concetti relativi al Programma esterno di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="1a11f-110">Database Mail External Program Concepts</span></span>  
 <span data-ttu-id="1a11f-111">All'avvio del programma esterno, il programma viene connesso a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzando l'autenticazione di Windows e viene avviata l'elaborazione dei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1a11f-111">When the external program starts, the program connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using Windows Authentication and begins processing e-mail messages.</span></span> <span data-ttu-id="1a11f-112">In assenza di messaggi da inviare per il periodo di timeout specificato, il programma viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="1a11f-112">When there have been no messages to send for the specified time-out period, the program exits.</span></span> <span data-ttu-id="1a11f-113">È possibile configurare il tempo di attesa da parte del programma prima della chiusura utilizzando Configurazione guidata posta elettronica database oppure le stored procedure di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="1a11f-113">You can configure the amount of time that the program waits before exiting by using either Database Mail Configuration Wizard or the Database Mail stored procedures.</span></span> <span data-ttu-id="1a11f-114">Per altre informazioni, vedere [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1a11f-114">For more information, see [sysmail_configure_sp &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql).</span></span>  
  
 <span data-ttu-id="1a11f-115">Il programma esterno archivia le informazioni in tabelle di sistema nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="1a11f-115">The external program stores information in system tables in the **msdb** database.</span></span> <span data-ttu-id="1a11f-116">Se il programma esterno non è in grado di comunicare con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], registra gli errori nel registro eventi applicazioni di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="1a11f-116">If the external program cannot communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the program logs errors to the Microsoft Windows application event log.</span></span> <span data-ttu-id="1a11f-117">La registrazione aggiuntiva dei messaggi è disponibile quando il livello di registrazione è impostato su **Dettagliati** nella finestra di dialogo **Configurazione parametri di sistema** della **Configurazione guidata posta elettronica database**.</span><span class="sxs-lookup"><span data-stu-id="1a11f-117">Additional message logging is provided when the logging level is set to **Verbose** in the **Configure System Parameters** dialog box of the **Database Mail Configuration Wizard**.</span></span>  
  
 <span data-ttu-id="1a11f-118">Si noti che, per motivi di efficienza, il programma esterno memorizza nella cache le informazioni relative a profili e account.</span><span class="sxs-lookup"><span data-stu-id="1a11f-118">Notice that, for efficiency, the external program caches account and profile information.</span></span> <span data-ttu-id="1a11f-119">Pertanto, le modifiche alla configurazione di profili e account potrebbero non venire trasmesse al programma esterno per alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="1a11f-119">Therefore, configuration changes to accounts and profiles may not be reflected in the external program for a few minutes.</span></span>  
  
##  <a name="tasks-related-to-configuring-database-mail-external-program"></a><a name="RelatedTasks"></a> <span data-ttu-id="1a11f-120">Attività correlate alla configurazione del Programma esterno di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="1a11f-120">Tasks Related to Configuring Database Mail External Program</span></span>  
  
|<span data-ttu-id="1a11f-121">Attività di configurazione</span><span class="sxs-lookup"><span data-stu-id="1a11f-121">Configuration Task</span></span>|<span data-ttu-id="1a11f-122">Collegamento all'argomento</span><span class="sxs-lookup"><span data-stu-id="1a11f-122">Topic Link</span></span>|  
|------------------------|----------------|  
|<span data-ttu-id="1a11f-123">Specificare l'ora che il Programma Esterno prima di uscire.</span><span class="sxs-lookup"><span data-stu-id="1a11f-123">Specify the time that the External Program before exiting.</span></span>|[<span data-ttu-id="1a11f-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1a11f-124">sysmail_configure_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-configure-sp-transact-sql)|  
  
## <a name="see-also"></a><span data-ttu-id="1a11f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a11f-125">See Also</span></span>  
 <span data-ttu-id="1a11f-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="1a11f-126">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="1a11f-127">[Controlli e registrazione di Posta elettronica database](database-mail-log-and-audits.md) </span><span class="sxs-lookup"><span data-stu-id="1a11f-127">[Database Mail Log and Audits](database-mail-log-and-audits.md) </span></span>  
 [<span data-ttu-id="1a11f-128">Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="1a11f-128">Database Mail</span></span>](database-mail.md)  
  
  
