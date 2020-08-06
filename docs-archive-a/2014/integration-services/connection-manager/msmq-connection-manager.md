---
title: Gestione connessione MSMQ | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], message queues
- connection managers [Integration Services], MSMQ
- MSMQ connection manager
- message queue connections [Integration Services]
ms.assetid: a86900e2-450e-479f-b207-e1b02361d395
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0c51866eeef281f6587bf281461e4faa2278308d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636348"
---
# <a name="msmq-connection-manager"></a><span data-ttu-id="46391-102">gestione connessione MSMQ</span><span class="sxs-lookup"><span data-stu-id="46391-102">MSMQ Connection Manager</span></span>
  <span data-ttu-id="46391-103">Una gestione connessione MSMQ consente la connessione di un pacchetto a una coda di messaggi che utilizza MSMQ (Message Queuing, Accodamento messaggi).</span><span class="sxs-lookup"><span data-stu-id="46391-103">An MSMQ connection manager enables a package to connect to a message queue that uses Message Queuing (also known as MSMQ).</span></span> <span data-ttu-id="46391-104">La gestione connessione MSMQ viene usata dall'attività Message Queue inclusa in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46391-104">The Message Queue task that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses an MSMQ connection manager.</span></span>  
  
 <span data-ttu-id="46391-105">Quando si aggiunge una gestione connessione MSMQ a un pacchetto, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] crea una gestione connessione che in fase di esecuzione verrà risolta in una connessione MSMQ, imposta le proprietà di tale gestione connessione, quindi la aggiunge alla raccolta `Connections` del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="46391-105">When you add an MSMQ connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an MSMQ connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span> <span data-ttu-id="46391-106">La proprietà `ConnectionManagerType` della gestione connessione viene impostata su `MSMQ`.</span><span class="sxs-lookup"><span data-stu-id="46391-106">The `ConnectionManagerType` property of the connection manager is set to `MSMQ`.</span></span>  
  
 <span data-ttu-id="46391-107">Per configurare la gestione connessione MSMQ, procedere nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="46391-107">You can configure an MSMQ connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="46391-108">Specificare una stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="46391-108">Provide a connection string.</span></span>  
  
-   <span data-ttu-id="46391-109">Specificare il percorso della coda di messaggi a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="46391-109">Provide the path of the message queue to connect to.</span></span>  
  
 <span data-ttu-id="46391-110">Il formato del percorso dipende dal tipo di coda, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="46391-110">The format of the path depends on the type of queue, as shown in the following table.</span></span>  
  
|<span data-ttu-id="46391-111">Tipo di coda</span><span class="sxs-lookup"><span data-stu-id="46391-111">Queue type</span></span>|<span data-ttu-id="46391-112">Percorso di esempio</span><span class="sxs-lookup"><span data-stu-id="46391-112">Sample path</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="46391-113">Pubblico</span><span class="sxs-lookup"><span data-stu-id="46391-113">Public</span></span>|<span data-ttu-id="46391-114">\<computer name>\\<nome della coda\></span><span class="sxs-lookup"><span data-stu-id="46391-114">\<computer name>\\<queue name\></span></span>|  
|<span data-ttu-id="46391-115">Privato</span><span class="sxs-lookup"><span data-stu-id="46391-115">Private</span></span>|<span data-ttu-id="46391-116">\<computer name>\Private$\\<nome della coda\></span><span class="sxs-lookup"><span data-stu-id="46391-116">\<computer name>\Private$\\<queue name\></span></span>|  
  
 <span data-ttu-id="46391-117">Per rappresentare il computer locale è possibile utilizzare un punto (.).</span><span class="sxs-lookup"><span data-stu-id="46391-117">You can use a period (.) to represent the local computer.</span></span>  
  
## <a name="configuration-of-the-msmq-connection-manager"></a><span data-ttu-id="46391-118">Configurazione della gestione connessione MSMQ</span><span class="sxs-lookup"><span data-stu-id="46391-118">Configuration of the MSMQ Connection Manager</span></span>  
 <span data-ttu-id="46391-119">È possibile impostare le proprietà tramite Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] o a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="46391-119">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="46391-120">Per altre informazioni sulle proprietà che è possibile impostare in Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] , vedere [Editor gestione connessione MSMQ](../msmq-connection-manager-editor.md).</span><span class="sxs-lookup"><span data-stu-id="46391-120">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [MSMQ Connection Manager Editor](../msmq-connection-manager-editor.md).</span></span>  
  
 <span data-ttu-id="46391-121">Per informazioni sulla configurazione di una gestione connessione a livello di programmazione, vedere l'articolo relativo a <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> e [Aggiunta di connessioni a livello di programmazione](../building-packages-programmatically/adding-connections-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="46391-121">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46391-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46391-122">See Also</span></span>  
 <span data-ttu-id="46391-123">[Attività Message Queue](../control-flow/message-queue-task.md) </span><span class="sxs-lookup"><span data-stu-id="46391-123">[Message Queue Task](../control-flow/message-queue-task.md) </span></span>  
 [<span data-ttu-id="46391-124">Connessioni in Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="46391-124">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
