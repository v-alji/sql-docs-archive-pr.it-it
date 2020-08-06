---
title: Editor gestione connessione MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.msmqconnectionmanager.f1
helpviewer_keywords:
- MSMQ Connection Manager Editor
ms.assetid: ef842cb4-82da-4550-85fe-9bedbc1e77c7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 41d4231ce121d596c8d818485eccf5ddf6127470
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624814"
---
# <a name="msmq-connection-manager-editor"></a><span data-ttu-id="5b6e5-102">Editor gestione connessione MSMQ</span><span class="sxs-lookup"><span data-stu-id="5b6e5-102">MSMQ Connection Manager Editor</span></span>
  <span data-ttu-id="5b6e5-103">Usare la finestra di dialogo **Gestione connessione MSMQ** per specificare il percorso di una coda di messaggi di Microsoft Message Queuing (noto anche come MSMQ).</span><span class="sxs-lookup"><span data-stu-id="5b6e5-103">Use the **MSMQ Connection Manager** dialog box to specify the path to a Message Queuing (also known as MSMQ) message queue.</span></span>  
  
 <span data-ttu-id="5b6e5-104">Per ulteriori informazioni sulla gestione connessione MSMQ, vedere [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="5b6e5-104">To learn more about the MSMQ connection manager, see [MSMQ Connection Manager](connection-manager/msmq-connection-manager.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5b6e5-105">Gestione connessione MSMQ supporta le code pubbliche e private locali, nonché le code pubbliche remote.</span><span class="sxs-lookup"><span data-stu-id="5b6e5-105">The MSMQ connection manager supports local public and private queues and remote public queues.</span></span> <span data-ttu-id="5b6e5-106">Non supporta le code private remote.</span><span class="sxs-lookup"><span data-stu-id="5b6e5-106">It does not support remote private queues.</span></span> <span data-ttu-id="5b6e5-107">Per una soluzione alternativa che utilizza l'attività Script, vedere [l'invio a una coda di messaggi privata remota tramite l'attività Script](control-flow/script-task.md).</span><span class="sxs-lookup"><span data-stu-id="5b6e5-107">For a workaround that uses the Script Task, see [Sending to a Remote Private Message Queue with the Script Task](control-flow/script-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5b6e5-108">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5b6e5-108">Options</span></span>  
 <span data-ttu-id="5b6e5-109">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5b6e5-109">**Name**</span></span>  
 <span data-ttu-id="5b6e5-110">Consente di specificare un nome univoco per la gestione della connessione MSMQ nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5b6e5-110">Provide a unique name for the MSMQ connection manager in the workflow.</span></span> <span data-ttu-id="5b6e5-111">Il nome specificato verrà visualizzato in Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b6e5-111">The name provided will be displayed within [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
 <span data-ttu-id="5b6e5-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="5b6e5-112">**Description**</span></span>  
 <span data-ttu-id="5b6e5-113">Consente di aggiungere una descrizione per la gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="5b6e5-113">Describe the connection manager.</span></span> <span data-ttu-id="5b6e5-114">È consigliabile includere nella descrizione informazioni sugli scopi della gestione connessione, in modo da ottenere pacchetti autodocumentati e semplificarne quindi la gestione.</span><span class="sxs-lookup"><span data-stu-id="5b6e5-114">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="5b6e5-115">**Percorso**</span><span class="sxs-lookup"><span data-stu-id="5b6e5-115">**Path**</span></span>  
 <span data-ttu-id="5b6e5-116">Digitare il percorso completo della coda di messaggi.</span><span class="sxs-lookup"><span data-stu-id="5b6e5-116">Type the complete path of the message queue.</span></span> <span data-ttu-id="5b6e5-117">Il formato del percorso dipende dal tipo di coda.</span><span class="sxs-lookup"><span data-stu-id="5b6e5-117">The format of the path depends on the type of queue.</span></span>  
  
|<span data-ttu-id="5b6e5-118">Tipo di coda</span><span class="sxs-lookup"><span data-stu-id="5b6e5-118">Queue type</span></span>|<span data-ttu-id="5b6e5-119">Percorso di esempio</span><span class="sxs-lookup"><span data-stu-id="5b6e5-119">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="5b6e5-120">Pubblico</span><span class="sxs-lookup"><span data-stu-id="5b6e5-120">Public</span></span>|<span data-ttu-id="5b6e5-121">\<computer name>\\<nome della coda\></span><span class="sxs-lookup"><span data-stu-id="5b6e5-121">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="5b6e5-122">Privato</span><span class="sxs-lookup"><span data-stu-id="5b6e5-122">Private</span></span>|<span data-ttu-id="5b6e5-123">\<computer name>\Private$\\<nome della coda\></span><span class="sxs-lookup"><span data-stu-id="5b6e5-123">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="5b6e5-124">Per rappresentare il computer locale è possibile utilizzare ".".</span><span class="sxs-lookup"><span data-stu-id="5b6e5-124">You can use "." to represent the local computer.</span></span>  
  
 <span data-ttu-id="5b6e5-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="5b6e5-125">**Test**</span></span>  
 <span data-ttu-id="5b6e5-126">Dopo aver configurato la gestione connessione MSMQ, verificare che la connessione può essere stabilita facendo clic su **Test**.</span><span class="sxs-lookup"><span data-stu-id="5b6e5-126">After configuring the MSMQ connection manager, confirm that the connection is viable by clicking **Test**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6e5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b6e5-127">See Also</span></span>  
 [<span data-ttu-id="5b6e5-128">Guida di riferimento ai messaggi e agli errori di Integration Services</span><span class="sxs-lookup"><span data-stu-id="5b6e5-128">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
