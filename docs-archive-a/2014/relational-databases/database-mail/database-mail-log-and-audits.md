---
title: Controlli e registrazione di Posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- Database Mail [SQL Server], auditing
- logs [Database Mail]
- audits [SQL Server], Database Mail
- Database Mail [SQL Server], logging
ms.assetid: 846589ee-5fe5-4ab3-b335-0c253e569f99
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6267389f187b955982ec1c18c411f703b4562f3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725932"
---
# <a name="database-mail-log-and-audits"></a><span data-ttu-id="250b4-102">Controlli e registrazione di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="250b4-102">Database Mail Log and Audits</span></span>
  <span data-ttu-id="250b4-103">La funzionalità di registrazione di Posta elettronica database è stata progettata per fornire un modo per isolare e correggere i problemi.</span><span class="sxs-lookup"><span data-stu-id="250b4-103">The Database Mail logging functionality is designed to provide a way to isolate and correct problems.</span></span> <span data-ttu-id="250b4-104">Posta elettronica database memorizza le informazioni del log nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="250b4-104">Database Mail stores the log information in the **msdb** database.</span></span> <span data-ttu-id="250b4-105">Le informazioni sul contenuto di Posta elettronica database, dello stato dei messaggi di posta elettronica e eventuali messaggi ricevuti, come ad esempio messaggi di errore, vengono registrati da Posta elettronica database e possono essere utilizzati per scopi di diagnosi e controllo.</span><span class="sxs-lookup"><span data-stu-id="250b4-105">Information about Database Mail e-mail content, status of e-mails, and any messages received, such as errors  are logged by Database Mail and can be used for troubleshooting and auditing purposes.</span></span>  
  
## <a name="database-mail-logs"></a><span data-ttu-id="250b4-106">Log di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="250b4-106">Database Mail Logs</span></span>  
 <span data-ttu-id="250b4-107">Le tabelle presenti nel database **msdb** registrano le informazioni provenienti dal [Programma esterno di Posta elettronica database](database-mail-external-program.md).</span><span class="sxs-lookup"><span data-stu-id="250b4-107">Tables in the **msdb** database log information from the [Database Mail External Program](database-mail-external-program.md).</span></span> <span data-ttu-id="250b4-108">Le [Viste di Posta elettronica database &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) espongono le tabelle per la risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="250b4-108">[Database Mail Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/database-mail-views-transact-sql) expose the tables for troubleshooting purposes.</span></span> <span data-ttu-id="250b4-109">Nella vista [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) vengono visualizzati errori se Service Broker non è in grado di attivare il programma esterno, se il programma esterno rileva errori di rete oppure se il server SMTP (Simple Mail Transfer Protocol) rifiuta un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="250b4-109">Errors appear in the [sysmail_event_log &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sysmail-event-log-transact-sql) view if Service Broker cannot activate the external program, if the external program encounters networking errors or if the Simple Mail Transport Protocol (SMTP) server refuses an e-mail message.</span></span> <span data-ttu-id="250b4-110">Se il programma esterno non può connettersi alle tabelle di **msdb** , gli errori verranno registrati nel registro eventi applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="250b4-110">In the event that the external program cannot log to the **msdb** tables, the program logs errors to the Windows application event log.</span></span>  
  
 <span data-ttu-id="250b4-111">Le tabelle interne nel database **msdb** includono i messaggi di posta elettronica e gli allegati inviati da Posta elettronica database, insieme allo stato corrente di ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="250b4-111">Internal tables in the **msdb** database contain the e-mail messages and attachments sent from Database Mail, together with the current status of each message.</span></span> <span data-ttu-id="250b4-112">Le tabelle vengono aggiornate da Posta elettronica database all'elaborazione di ogni messaggio.</span><span class="sxs-lookup"><span data-stu-id="250b4-112">Database Mail updates these tables as each message is processed.</span></span>  
  
## <a name="database-mail-auditing-tasks"></a><span data-ttu-id="250b4-113">Attività di controllo di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="250b4-113">Database Mail Auditing tasks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="250b4-114">**Analisi e gestione dei log di Posta elettronica database**</span><span class="sxs-lookup"><span data-stu-id="250b4-114">**Reviewing and managing Database Mail logs**</span></span>|<span data-ttu-id="250b4-115">**Collegamento all'argomento**</span><span class="sxs-lookup"><span data-stu-id="250b4-115">**Link to Topic**</span></span>|  
|<span data-ttu-id="250b4-116">Controllo dello stato di recapito di un singolo messaggio</span><span class="sxs-lookup"><span data-stu-id="250b4-116">Check the delivery status of an individual message</span></span>|[<span data-ttu-id="250b4-117">Controllare lo stato di messaggi di posta elettronica inviati con Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="250b4-117">Check the Status of E-Mail Messages Sent With Database Mail</span></span>](check-the-status-of-e-mail-messages-sent-with-database-mail.md)|  
|<span data-ttu-id="250b4-118">Pulizia dei messaggi di Posta elettronica database, allegati e voci di registro</span><span class="sxs-lookup"><span data-stu-id="250b4-118">Clean up Database Mail messages, attachments, and log entries</span></span>|[<span data-ttu-id="250b4-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="250b4-119">sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql)<br /><br /> [<span data-ttu-id="250b4-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="250b4-120">sysmail_delete_log_sp &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sysmail-delete-log-sp-transact-sql)|  
|<span data-ttu-id="250b4-121">Archiviazione di messaggi di Posta elettronica database e log</span><span class="sxs-lookup"><span data-stu-id="250b4-121">Archive the Database Email Messages and Logs</span></span>|[<span data-ttu-id="250b4-122">Creare un processo di SQL Server Agent per l'archiviazione di messaggi e log eventi di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="250b4-122">Create a SQL Server Agent Job to Archive Database Mail Messages and Event Logs</span></span>](create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)|  
  
## <a name="see-also"></a><span data-ttu-id="250b4-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="250b4-123">See Also</span></span>  
 [<span data-ttu-id="250b4-124">Monitorare l'utilizzo delle risorse &#40;Monitor di sistema&#41;</span><span class="sxs-lookup"><span data-stu-id="250b4-124">Monitor Resource Usage &#40;System Monitor&#41;</span></span>](../performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
