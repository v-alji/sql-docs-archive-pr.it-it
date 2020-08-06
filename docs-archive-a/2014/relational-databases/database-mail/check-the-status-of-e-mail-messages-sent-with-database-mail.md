---
title: Controllare lo stato di messaggi di posta elettronica inviati con Posta elettronica database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- e-mail [SQL Server], status information
- mail [SQL Server], status information
- Database Mail [SQL Server], message status
- status information [Database Mail]
ms.assetid: eb290f24-b52f-46bc-84eb-595afee6a5f3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1642c456cd64484dede64f8127ff2f979f2242e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637882"
---
# <a name="check-the-status-of-e-mail-messages-sent-with-database-mail"></a><span data-ttu-id="52a08-102">Controllare lo stato di messaggi di posta elettronica inviati con Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="52a08-102">Check the Status of E-Mail Messages Sent With Database Mail</span></span>
  <span data-ttu-id="52a08-103">In questo argomento viene illustrato come controllare lo stato del messaggio di posta elettronica inviato utilizzando Posta elettronica database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52a08-103">This topic describes how to check the status of the e-mail message sent using Database Mail  in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="52a08-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="52a08-104">**Before you begin:**</span></span>  
  
-   <span data-ttu-id="52a08-105">**Per visualizzare lo stato del messaggio di posta elettronica inviato usando Posta elettronica database:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="52a08-105">**To view the status of the e-mail sent using Database Mail, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="52a08-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="52a08-106">Before You Begin</span></span>  
 <span data-ttu-id="52a08-107">Posta elettronica database conserva copie dei messaggi di posta elettronica in uscita e le visualizza nelle viste **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**e **sysmail_faileditems** del database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="52a08-107">Database Mail keeps copies of outgoing e-mail messages and displays them in the **sysmail_allitems**, **sysmail_sentitems**, **sysmail_unsentitems**, **sysmail_faileditems** views of the **msdb** database.</span></span> <span data-ttu-id="52a08-108">Il programma esterno Posta elettronica database registra l'attività e visualizza il log tramite il registro eventi applicazioni di Windows e la vista **sysmail_event_log** nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="52a08-108">The Database Mail external program logs activity and displays the log through the Windows Application Event Log and the **sysmail_event_log** view in the **msdb** database.</span></span> <span data-ttu-id="52a08-109">Per controllare lo stato di un messaggio di posta elettronica, è necessario eseguire una query su questa tabella.</span><span class="sxs-lookup"><span data-stu-id="52a08-109">To check the status of an e-mail message, run a query against this view.</span></span> <span data-ttu-id="52a08-110">I messaggi di posta elettronica possono avere uno dei quattro stati seguenti: **inviato**, **non inviato**, **nuovo tentativo in corso**e **non riuscito**.</span><span class="sxs-lookup"><span data-stu-id="52a08-110">E-mail messages have one of four possible statuses: **sent**, **unsent**, **retrying**, and **failed**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="52a08-111">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="52a08-111">Using Transact-SQL</span></span>  
 <span data-ttu-id="52a08-112">**Per visualizzare lo stato della posta elettronica inviata utilizzando Posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="52a08-112">**To view the status of the e-mail sent using Database Mail**</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="52a08-113">Per un esempio di questa procedura, vedere [Esempio (Transact-SQL)](#TsqlExample)più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="52a08-113">For an example of this procedure, see [Example (Transact-SQL)](#TsqlExample), later in this section.</span></span>  
  
1.  <span data-ttu-id="52a08-114">Selezionare dalla tabella **sysmail_allitems** specificando i messaggi di interesse tramite **mailitem_id** o **sent_status**.</span><span class="sxs-lookup"><span data-stu-id="52a08-114">Select from the **sysmail_allitems** table, specifying the messages of interest by **mailitem_id** or **sent_status**.</span></span>  
  
2.  <span data-ttu-id="52a08-115">Per controllare lo stato restituito dal programma esterno per i messaggi di posta elettronica, unire in join **sysmail_allitems** alla vista **sysmail_event_log** nella colonna **mailitem_id** , come illustrato nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="52a08-115">To check the status returned from the external program for the e-mail messages, join **sysmail_allitems** to **sysmail_event_log** view on the **mailitem_id** column, as shown in the following section.</span></span>  
  
     <span data-ttu-id="52a08-116">Per impostazione predefinita, il programma esterno non registra le informazioni relative ai messaggi inviati correttamente.</span><span class="sxs-lookup"><span data-stu-id="52a08-116">By default, the external program does not log information about messages that were successfully sent.</span></span> <span data-ttu-id="52a08-117">Per registrare tutti i messaggi, impostare il livello di registrazione su dettagliato utilizzando la pagina **Configurazione parametri di sistema** di **Configurazione guidata Posta elettronica database**.</span><span class="sxs-lookup"><span data-stu-id="52a08-117">To log all messages, set the logging level to verbose using the **Configure System Parameters** page of the **Database Mail Configuration Wizard.**</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="52a08-118">Esempio (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="52a08-118">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="52a08-119">Nell'esempio seguente sono elencate le informazioni relative a eventuali messaggi di posta elettronica inviati a `danw` che il programma esterno non è stato in grado di inviare correttamente.</span><span class="sxs-lookup"><span data-stu-id="52a08-119">The following example lists information about any e-mail messages sent to `danw` that the external program could not send successfully.</span></span> <span data-ttu-id="52a08-120">L'istruzione elenca oggetto, data e ora del mancato invio del messaggio da parte del programma esterno e il messaggio di errore dal log di Posta elettronica database.</span><span class="sxs-lookup"><span data-stu-id="52a08-120">The statement lists the subject, the date and time that the external program failed to send the message, and the error message from the Database Mail log.</span></span>  
  
```  
USE msdb ;  
GO  
  
-- Show the subject, the time that the mail item row was last  
-- modified, and the log information.  
-- Join sysmail_faileditems to sysmail_event_log   
-- on the mailitem_id column.  
-- In the WHERE clause list items where danw was in the recipients,  
-- copy_recipients, or blind_copy_recipients.  
-- These are the items that would have been sent  
-- to danw.  
  
SELECT items.subject,  
    items.last_mod_date  
    ,l.description FROM dbo.sysmail_faileditems as items  
INNER JOIN dbo.sysmail_event_log AS l  
    ON items.mailitem_id = l.mailitem_id  
WHERE items.recipients LIKE '%danw%'    
    OR items.copy_recipients LIKE '%danw%'   
    OR items.blind_copy_recipients LIKE '%danw%'  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="52a08-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52a08-121">See Also</span></span>  
 [<span data-ttu-id="52a08-122">Controlli e registrazione di Posta elettronica database</span><span class="sxs-lookup"><span data-stu-id="52a08-122">Database Mail Log and Audits</span></span>](database-mail-log-and-audits.md)  
  
  
