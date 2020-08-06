---
title: Editor attività Invia messaggi (pagina posta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.mail.f1
helpviewer_keywords:
- Send Mail Task Editor
ms.assetid: adb385d5-ef24-4d18-b9ea-b39e00a7075e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 52cab62f3c88ea248b76061664547fd8f1314099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726087"
---
# <a name="send-mail-task-editor-mail-page"></a><span data-ttu-id="e6244-102">Editor attività Invia messaggi (pagina Messaggio)</span><span class="sxs-lookup"><span data-stu-id="e6244-102">Send Mail Task Editor (Mail Page)</span></span>
  <span data-ttu-id="e6244-103">Usare la pagina **Messaggio** della finestra di dialogo **Editor attività Invia messaggi** per specificare i destinatari, il tipo di messaggio e la priorità relativi a un messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-103">Use the **Mail** page of the **Send Mail Task Editor** dialog box to specify recipients, message type, and priority for a message.</span></span> <span data-ttu-id="e6244-104">È inoltre possibile allegare file al messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-104">You can also attach files to the message.</span></span> <span data-ttu-id="e6244-105">Il testo del messaggio può essere una stringa specificata, una connessione a un file che contiene il testo o il nome di una variabile che contiene il testo.</span><span class="sxs-lookup"><span data-stu-id="e6244-105">The message text can be a string you provide, a file connection to a file that contains the text, or the name of a variable that contains the text.</span></span>  
  
 <span data-ttu-id="e6244-106">Per ulteriori informazioni su questa attività, vedere [Send Mail Task](control-flow/send-mail-task.md).</span><span class="sxs-lookup"><span data-stu-id="e6244-106">To learn about this task, see [Send Mail Task](control-flow/send-mail-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e6244-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e6244-107">Options</span></span>  
 <span data-ttu-id="e6244-108">**SMTPConnection**</span><span class="sxs-lookup"><span data-stu-id="e6244-108">**SMTPConnection**</span></span>  
 <span data-ttu-id="e6244-109">Selezionare una gestione connessione SMTP nell'elenco oppure fare clic su **\<New connection...>** per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="e6244-109">Select an SMTP connection manager in the list, or click **\<New connection...>** to create a new connection manager.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e6244-110">La gestione connessione SMTP supporta solo l'autenticazione anonima e l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e6244-110">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="e6244-111">Non supporta l'autenticazione di base.</span><span class="sxs-lookup"><span data-stu-id="e6244-111">It does not support basic authentication.</span></span>  
  
 <span data-ttu-id="e6244-112">**Argomenti correlati:** [Gestione connessione SMTP](connection-manager/smtp-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="e6244-112">**Related Topics:** [SMTP Connection Manager](connection-manager/smtp-connection-manager.md)</span></span>  
  
 <span data-ttu-id="e6244-113">**From**</span><span class="sxs-lookup"><span data-stu-id="e6244-113">**From**</span></span>  
 <span data-ttu-id="e6244-114">Consente di specificare l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="e6244-114">Specify the e-mail address of the sender.</span></span>  
  
 <span data-ttu-id="e6244-115">**To**</span><span class="sxs-lookup"><span data-stu-id="e6244-115">**To**</span></span>  
 <span data-ttu-id="e6244-116">Consente di specificare gli indirizzi di posta elettronica dei destinatari, separati da punti e virgola.</span><span class="sxs-lookup"><span data-stu-id="e6244-116">Provide the e-mail addresses of the recipients, delimited by semicolons.</span></span>  
  
 <span data-ttu-id="e6244-117">**Cc**</span><span class="sxs-lookup"><span data-stu-id="e6244-117">**Cc**</span></span>  
 <span data-ttu-id="e6244-118">Consente di specificare gli indirizzi di posta elettronica, separati da punti e virgola, di altri destinatari che riceveranno copie del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-118">Specify the e-mail addresses, delimited by semicolons, of individuals who also receive copies of the message.</span></span>  
  
 <span data-ttu-id="e6244-119">**Bcc**</span><span class="sxs-lookup"><span data-stu-id="e6244-119">**Bcc**</span></span>  
 <span data-ttu-id="e6244-120">Consente di specificare gli indirizzi di posta elettronica, separati da punti e virgola, di destinatari in copia nascosta che riceveranno copie del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-120">Specify the e-mail addresses, delimited by semicolons, of individuals who receive blind carbon copies (Bcc) copies of the message.</span></span>  
  
 <span data-ttu-id="e6244-121">**Oggetto**</span><span class="sxs-lookup"><span data-stu-id="e6244-121">**Subject**</span></span>  
 <span data-ttu-id="e6244-122">Consente di specificare l'oggetto del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e6244-122">Provide a subject for the e-mail message.</span></span>  
  
 <span data-ttu-id="e6244-123">**MessageSourceType**</span><span class="sxs-lookup"><span data-stu-id="e6244-123">**MessageSourceType**</span></span>  
 <span data-ttu-id="e6244-124">Consente di selezionare il tipo di origine del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-124">Select the source type of the message.</span></span> <span data-ttu-id="e6244-125">Per questa proprietà sono disponibili le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="e6244-125">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="e6244-126">valore</span><span class="sxs-lookup"><span data-stu-id="e6244-126">Value</span></span>|<span data-ttu-id="e6244-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6244-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e6244-128">**Input diretto**</span><span class="sxs-lookup"><span data-stu-id="e6244-128">**Direct input**</span></span>|<span data-ttu-id="e6244-129">Consente di impostare l'origine sul testo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-129">Set the source to the message text.</span></span> <span data-ttu-id="e6244-130">Selezionando questo valore, verrà visualizzata l'opzione dinamica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="e6244-130">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="e6244-131">**Connessione file**</span><span class="sxs-lookup"><span data-stu-id="e6244-131">**File connection**</span></span>|<span data-ttu-id="e6244-132">Consente di impostare l'origine sul file contenente il testo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-132">Set the source to the file that contains the message text.</span></span> <span data-ttu-id="e6244-133">Selezionando questo valore, verrà visualizzata l'opzione dinamica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="e6244-133">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
|<span data-ttu-id="e6244-134">**Variabile**</span><span class="sxs-lookup"><span data-stu-id="e6244-134">**Variable**</span></span>|<span data-ttu-id="e6244-135">Consente di impostare l'origine su una variabile contenente il testo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-135">Set the source to a variable that contains the message text.</span></span> <span data-ttu-id="e6244-136">Selezionando questo valore, verrà visualizzata l'opzione dinamica **MessageSource**.</span><span class="sxs-lookup"><span data-stu-id="e6244-136">Selecting this value displays the dynamic option, **MessageSource**.</span></span>|  
  
 <span data-ttu-id="e6244-137">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="e6244-137">**Priority**</span></span>  
 <span data-ttu-id="e6244-138">Consente di impostare il livello di priorità del messaggio.</span><span class="sxs-lookup"><span data-stu-id="e6244-138">Set the priority of the message.</span></span>  
  
 <span data-ttu-id="e6244-139">**Allegati**</span><span class="sxs-lookup"><span data-stu-id="e6244-139">**Attachments**</span></span>  
 <span data-ttu-id="e6244-140">Consente di specificare i nomi file degli allegati del messaggio di posta elettronica, separati dal carattere di barra verticale (|).</span><span class="sxs-lookup"><span data-stu-id="e6244-140">Provide the file names of attachments to the e-mail message, delimited by the pipe (|) character.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e6244-141">Le righe A, Cc e Ccn sono limitate a 256 caratteri, in conformità con gli standard Internet.</span><span class="sxs-lookup"><span data-stu-id="e6244-141">The To, Cc, and Bcc lines are limited to 256 characters in accordance with Internet standards.</span></span>  
  
## <a name="messagesourcetype-dynamic-options"></a><span data-ttu-id="e6244-142">Opzioni dinamiche MessageSourceType</span><span class="sxs-lookup"><span data-stu-id="e6244-142">MessageSourceType Dynamic Options</span></span>  
  
### <a name="messagesourcetype--direct-input"></a><span data-ttu-id="e6244-143">MessageSourceType = Input diretto</span><span class="sxs-lookup"><span data-stu-id="e6244-143">MessageSourceType = Direct Input</span></span>  
 <span data-ttu-id="e6244-144">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="e6244-144">**MessageSource**</span></span>  
 <span data-ttu-id="e6244-145">Digitare il testo del messaggio oppure fare clic sul pulsante Sfoglia (...), quindi digitare il messaggio nella finestra di dialogo **Origine messaggio**.</span><span class="sxs-lookup"><span data-stu-id="e6244-145">Type the message text or click the browse button (...) and then type the message in the **Message source** dialog box.</span></span>  
  
### <a name="messagesourcetype--file-connection"></a><span data-ttu-id="e6244-146">MessageSourceType = Connessione file</span><span class="sxs-lookup"><span data-stu-id="e6244-146">MessageSourceType = File connection</span></span>  
 <span data-ttu-id="e6244-147">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="e6244-147">**MessageSource**</span></span>  
 <span data-ttu-id="e6244-148">Selezionare una gestione connessione file nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="e6244-148">Select a File connection manager in the list or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="e6244-149">**Argomenti correlati:** [Gestione connessione file](connection-manager/file-connection-manager.md), [Editor gestione connessione file](../../2014/integration-services/file-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="e6244-149">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)</span></span>  
  
### <a name="messagesourcetype--variable"></a><span data-ttu-id="e6244-150">MessageSourceType = Variabile</span><span class="sxs-lookup"><span data-stu-id="e6244-150">MessageSourceType = Variable</span></span>  
 <span data-ttu-id="e6244-151">**MessageSource**</span><span class="sxs-lookup"><span data-stu-id="e6244-151">**MessageSource**</span></span>  
 <span data-ttu-id="e6244-152">Selezionare una variabile nell'elenco oppure fare clic su \<**New variable...**> per crearne una nuova.</span><span class="sxs-lookup"><span data-stu-id="e6244-152">Select a variable in the list or click \<**New variable...**> to create a new variable.</span></span>  
  
 <span data-ttu-id="e6244-153">**Argomenti correlati:** [Variabili di Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Aggiungere una variabile](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="e6244-153">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6244-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6244-154">See Also</span></span>  
 <span data-ttu-id="e6244-155">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e6244-155">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e6244-156">[Editor attività Invia messaggi &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e6244-156">[Send Mail Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 [<span data-ttu-id="e6244-157">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="e6244-157">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
