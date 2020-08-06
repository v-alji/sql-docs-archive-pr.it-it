---
title: Attività Invia messaggi| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.f1
helpviewer_keywords:
- mail [Integration Services]
- Send Mail task
- e-mail [Integration Services]
- messages [Integration Services]
- sending messages
ms.assetid: fe0b7cbc-fe8e-4fe2-95b4-2953efff5869
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c93723f3c443705acc14226ce07f456da4d5a884
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625505"
---
# <a name="send-mail-task"></a><span data-ttu-id="c1d4d-102">Invia messaggi - attività</span><span class="sxs-lookup"><span data-stu-id="c1d4d-102">Send Mail Task</span></span>
  <span data-ttu-id="c1d4d-103">L'attività Invia messaggi consente di inviare un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-103">The Send Mail task sends an e-mail message.</span></span> <span data-ttu-id="c1d4d-104">Tramite l'attività Invia messaggi un pacchetto può inviare messaggi quando le attività nel flusso di lavoro del pacchetto vengono completate o non riescono oppure in risposta a un evento generato dal pacchetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-104">By using the Send Mail task, a package can send messages if tasks in the package workflow succeed or fail, or send messages in response to an event that the package raises at run time.</span></span> <span data-ttu-id="c1d4d-105">È ad esempio possibile utilizzare questa attività per notificare all'amministratore di un database l'esito positivo o negativo dell'attività Backup database.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-105">For example, the task can notify a database administrator about the success or failure of the Backup Database task.</span></span>  
  
 <span data-ttu-id="c1d4d-106">Per configurare l'attività Invia messaggi, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c1d4d-106">You can configure the Send Mail task in the following ways:</span></span>  
  
-   <span data-ttu-id="c1d4d-107">Specificare il testo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-107">Provide the message text for the e-mail message.</span></span>  
  
-   <span data-ttu-id="c1d4d-108">Specificare l'oggetto del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-108">Provide a subject line for the e-mail message.</span></span>  
  
-   <span data-ttu-id="c1d4d-109">Impostare il livello di priorità del messaggio.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-109">Set the priority level of the message.</span></span> <span data-ttu-id="c1d4d-110">L'attività supporta tre livelli di priorità: normale, medio e alto.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-110">The task supports three priority levels: normal, low, and high.</span></span>  
  
-   <span data-ttu-id="c1d4d-111">Specificare i destinatari nelle righe A, Cc e Ccn.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-111">Specify the recipients on the To, Cc, and Bcc lines.</span></span> <span data-ttu-id="c1d4d-112">Per specificare più destinatari, separarli con punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-112">If the task specifies multiple recipients, they are separated by semicolons.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1d4d-113">Le righe A, Cc e Ccn presentano il limite di 256 caratteri ognuna, in conformità agli standard Internet.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-113">The To, Cc, and Bcc lines are limited to 256 characters each in accordance with Internet standards.</span></span>  
  
-   <span data-ttu-id="c1d4d-114">Includere eventuali allegati.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-114">Include attachments.</span></span> <span data-ttu-id="c1d4d-115">Per specificare più allegati, separarli con una barra verticale (|).</span><span class="sxs-lookup"><span data-stu-id="c1d4d-115">If the task specifies multiple attachments, they are separated by the pipe (|) character.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1d4d-116">Se un file allegato non esiste al momento dell'esecuzione del pacchetto, verrà generato un errore.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-116">If an attachment file does not exist when the package runs, an error occurs.</span></span>  
  
-   <span data-ttu-id="c1d4d-117">Specificare la gestione connessione SMTP da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-117">Specify the SMTP connection manager to use.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c1d4d-118">La gestione connessione SMTP supporta solo l'autenticazione anonima e l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-118">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="c1d4d-119">Non supporta l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-119">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="c1d4d-120">Il testo del messaggio può essere una stringa specificata, una connessione a un file che contiene il testo o il nome di una variabile che contiene il testo.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-120">The message text can be a string that you provide, a connection to a file that contains the text, or the name of a variable that contains the text.</span></span> <span data-ttu-id="c1d4d-121">Per connettersi a un file l'attività utilizza una gestione connessione file.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-121">The task uses a File connection manager to connect to a file.</span></span> <span data-ttu-id="c1d4d-122">Per ulteriori informazioni, vedere [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c1d4d-122">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="c1d4d-123">Per connettersi a un server di posta elettronica l'attività utilizza una gestione connessione SMTP.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-123">The task uses an SMTP connection manager to connect to a mail server.</span></span> <span data-ttu-id="c1d4d-124">Per altre informazioni, vedere [Gestione connessione SMTP](../connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c1d4d-124">For more information, see [SMTP Connection Manager](../connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="custom-logging-messages-available-on-the-send-mail-task"></a><span data-ttu-id="c1d4d-125">Messaggi di registrazione personalizzati disponibili nell'attività Invia messaggi</span><span class="sxs-lookup"><span data-stu-id="c1d4d-125">Custom Logging Messages Available on the Send Mail Task</span></span>  
 <span data-ttu-id="c1d4d-126">Nella tabella seguente sono elencate le voci di log personalizzate disponibili per l'attività Invia messaggi.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-126">The following table lists the custom log entries for the Send Mail task.</span></span> <span data-ttu-id="c1d4d-127">Per altre informazioni, vedere [Registrazione di Integration Services &#40;SSIS&#41;](../performance/integration-services-ssis-logging.md) e [Messaggi personalizzati per la registrazione](../custom-messages-for-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c1d4d-127">For more information, see [Integration Services &#40;SSIS&#41; Logging](../performance/integration-services-ssis-logging.md) and [Custom Messages for Logging](../custom-messages-for-logging.md).</span></span>  
  
|<span data-ttu-id="c1d4d-128">Voce di log</span><span class="sxs-lookup"><span data-stu-id="c1d4d-128">Log entry</span></span>|<span data-ttu-id="c1d4d-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c1d4d-129">Description</span></span>|  
|---------------|-----------------|  
|`SendMailTaskBegin`|<span data-ttu-id="c1d4d-130">Indica che l'attività ha iniziato a inviare un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-130">Indicates that the task began to send an e-mail message.</span></span>|  
|`SendMailTaskEnd`|<span data-ttu-id="c1d4d-131">Indica che l'attività ha terminato l'invio di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-131">Indicates that the task finished sending an e-mail message.</span></span>|  
|`SendMailTaskInfo`|<span data-ttu-id="c1d4d-132">Offre informazioni descrittive sull'attività.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-132">Provides descriptive information about the task.</span></span>|  
  
## <a name="configuring-the-send-mail-task"></a><span data-ttu-id="c1d4d-133">Configurazione dell'attività Invia messaggi</span><span class="sxs-lookup"><span data-stu-id="c1d4d-133">Configuring the Send Mail Task</span></span>  
 <span data-ttu-id="c1d4d-134">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="c1d4d-134">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c1d4d-135">Per informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su uno degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1d4d-135">For information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c1d4d-136">Editor attività Invia messaggi &#40;pagina Generale&#41;</span><span class="sxs-lookup"><span data-stu-id="c1d4d-136">Send Mail Task Editor &#40;General Page&#41;</span></span>](../general-page-of-integration-services-designers-options.md)  
  
-   [<span data-ttu-id="c1d4d-137">Editor attività Invia messaggi &#40;pagina Messaggio&#41;</span><span class="sxs-lookup"><span data-stu-id="c1d4d-137">Send Mail Task Editor &#40;Mail Page&#41;</span></span>](../send-mail-task-editor-mail-page.md)  
  
-   [<span data-ttu-id="c1d4d-138">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="c1d4d-138">Expressions Page</span></span>](../expressions/expressions-page.md)  
  
 <span data-ttu-id="c1d4d-139">Per informazioni sull'impostazione di queste proprietà a livello di codice, fare clic sull'argomento seguente:</span><span class="sxs-lookup"><span data-stu-id="c1d4d-139">For information about programmatically setting these properties, click the following topic:</span></span>  
  
-   <xref:Microsoft.SqlServer.Dts.Tasks.SendMailTask.SendMailTask>  
  
## <a name="related-tasks"></a><span data-ttu-id="c1d4d-140">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="c1d4d-140">Related Tasks</span></span>  
 <span data-ttu-id="c1d4d-141">Per informazioni su come impostare queste proprietà nella finestra di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , fare clic su [Impostazione delle proprietà di un'attività o di un contenitore](../set-the-properties-of-a-task-or-container.md).</span><span class="sxs-lookup"><span data-stu-id="c1d4d-141">For information about how to set these properties in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click [Set the Properties of a Task or Container](../set-the-properties-of-a-task-or-container.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="c1d4d-142">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="c1d4d-142">Related Content</span></span>  
  
-   <span data-ttu-id="c1d4d-143">Articolo tecnico relativo all' [invio della posta elettronica con notifica di recapito in C#](https://go.microsoft.com/fwlink/?LinkId=237625)su shareourideas.com</span><span class="sxs-lookup"><span data-stu-id="c1d4d-143">Technical article, [How to send email with delivery notification in C#](https://go.microsoft.com/fwlink/?LinkId=237625), on shareourideas.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d4d-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1d4d-144">See Also</span></span>  
 <span data-ttu-id="c1d4d-145">[Attività di Integration Services](integration-services-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="c1d4d-145">[Integration Services Tasks](integration-services-tasks.md) </span></span>  
 [<span data-ttu-id="c1d4d-146">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="c1d4d-146">Control Flow</span></span>](control-flow.md)  
  
  
