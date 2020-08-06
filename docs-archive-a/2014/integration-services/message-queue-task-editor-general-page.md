---
title: Editor attività Message Queue (pagina generale) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msgqueuetask.general.f1
helpviewer_keywords:
- Message Queue Task Editor
ms.assetid: 09368b18-37a5-4321-a173-7cfe5d42d2a2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dcec75f3a4dd85efb7c97226c592d6b1e1bb26ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637988"
---
# <a name="message-queue-task-editor-general-page"></a><span data-ttu-id="b270a-102">Editor attività Message Queue (pagina Generale)</span><span class="sxs-lookup"><span data-stu-id="b270a-102">Message Queue Task Editor (General Page)</span></span>
  <span data-ttu-id="b270a-103">Utilizzare la pagina **Generale** della finestra di dialogo **Editor attività Message Queue** per assegnare un nome e una descrizione all'attività Message Queue, specificare il formato dei messaggi e impostare l'attività per l'invio o la ricezione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="b270a-103">Use the **General page** of the **Message Queue Task Editor** dialog box to name and describe the Message Queue task, to specify the message format, and to indicate whether the task sends or receives messages.</span></span>  
  
 <span data-ttu-id="b270a-104">Per ulteriori informazioni su questa attività, vedere [Message Queue Task](control-flow/message-queue-task.md).</span><span class="sxs-lookup"><span data-stu-id="b270a-104">To learn about this task, see [Message Queue Task](control-flow/message-queue-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b270a-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b270a-105">Options</span></span>  
 <span data-ttu-id="b270a-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b270a-106">**Name**</span></span>  
 <span data-ttu-id="b270a-107">Consente di specificare un nome univoco per l'attività Message Queue.</span><span class="sxs-lookup"><span data-stu-id="b270a-107">Provide a unique name for the Message Queue task.</span></span> <span data-ttu-id="b270a-108">Tale nome viene utilizzato come etichetta nell'icona dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b270a-108">This name is used as the label in the task icon.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b270a-109">I nomi delle attività devono essere univoci all'interno di un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b270a-109">Task names must be unique within a package.</span></span>  
  
 <span data-ttu-id="b270a-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b270a-110">**Description**</span></span>  
 <span data-ttu-id="b270a-111">Consente di digitare una descrizione dell'attività Message Queue.</span><span class="sxs-lookup"><span data-stu-id="b270a-111">Type a description of the Message Queue task.</span></span>  
  
 <span data-ttu-id="b270a-112">**Use2000Format**</span><span class="sxs-lookup"><span data-stu-id="b270a-112">**Use2000Format**</span></span>  
 <span data-ttu-id="b270a-113">Consente di indicare se utilizzare il formato 2000 di Microsoft Message Queuing (noto anche come MSMQ).</span><span class="sxs-lookup"><span data-stu-id="b270a-113">Indicate whether to use the 2000 format of Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="b270a-114">Il valore predefinito è `False`.</span><span class="sxs-lookup"><span data-stu-id="b270a-114">The default is `False`.</span></span>  
  
 <span data-ttu-id="b270a-115">**MSMQConnection**</span><span class="sxs-lookup"><span data-stu-id="b270a-115">**MSMQConnection**</span></span>  
 <span data-ttu-id="b270a-116">Selezionare una gestione connessione MSMQ nell'elenco oppure fare clic su \<**New connection...**> per creare una nuova gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="b270a-116">Select an existing MSMQ connection manager or click \<**New connection...**> to create a new connection manager.</span></span>  
  
 <span data-ttu-id="b270a-117">**Argomenti correlati**: [Gestione connessione MSMQ](connection-manager/msmq-connection-manager.md), [Editor gestione connessione MSMQ](../../2014/integration-services/msmq-connection-manager-editor.md)</span><span class="sxs-lookup"><span data-stu-id="b270a-117">**Related Topics**: [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md), [MSMQ Connection Manager Editor](../../2014/integration-services/msmq-connection-manager-editor.md)</span></span>  
  
 <span data-ttu-id="b270a-118">**Messaggio**</span><span class="sxs-lookup"><span data-stu-id="b270a-118">**Message**</span></span>  
 <span data-ttu-id="b270a-119">Consente di specificare se l'attività Message Queue invia o riceve messaggi.</span><span class="sxs-lookup"><span data-stu-id="b270a-119">Specify whether the Message Queue task sends or receive messages.</span></span> <span data-ttu-id="b270a-120">Se si seleziona **Invia messaggio**, nel riquadro sinistro della finestra di dialogo viene inserita la pagina Invia. Se invece si seleziona **Ricevi messaggio**, viene inserita la pagina Ricevi.</span><span class="sxs-lookup"><span data-stu-id="b270a-120">If you select **Send message**, the Send page is listed in the left pane of the dialog box; if you select **Receive message**, the Receive page is listed.</span></span> <span data-ttu-id="b270a-121">Per impostazione predefinita, questo valore è impostato su **Invia messaggio**.</span><span class="sxs-lookup"><span data-stu-id="b270a-121">By default, this value is set to **Send message**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b270a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b270a-122">See Also</span></span>  
 <span data-ttu-id="b270a-123">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="b270a-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="b270a-124">[Editor attività Message Queue &#40;pagina ricezione&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span><span class="sxs-lookup"><span data-stu-id="b270a-124">[Message Queue Task Editor &#40;Receive Page&#41;](../../2014/integration-services/message-queue-task-editor-receive-page.md) </span></span>  
 <span data-ttu-id="b270a-125">[Editor attività Message Queue &#40;Invia pagina&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span><span class="sxs-lookup"><span data-stu-id="b270a-125">[Message Queue Task Editor &#40;Send Page&#41;](../../2014/integration-services/message-queue-task-editor-send-page.md) </span></span>  
 [<span data-ttu-id="b270a-126">Pagina Espressioni</span><span class="sxs-lookup"><span data-stu-id="b270a-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
