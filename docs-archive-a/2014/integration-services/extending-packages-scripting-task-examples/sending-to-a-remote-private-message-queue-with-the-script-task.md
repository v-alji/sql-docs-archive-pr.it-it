---
title: Invio di messaggi a una coda privata remota tramite l'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], remote private message queues
- Message Queue task [Integration Services]
- Script task [Integration Services], examples
ms.assetid: 636314fd-d099-45cd-8bb4-f730d0a06739
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 308815293dfc41f0a0ac60c21ce7f561a5e7f660
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716416"
---
# <a name="sending-to-a-remote-private-message-queue-with-the-script-task"></a><span data-ttu-id="f7103-102">Invio di messaggi a una coda privata remota tramite l'attività Script</span><span class="sxs-lookup"><span data-stu-id="f7103-102">Sending to a Remote Private Message Queue with the Script Task</span></span>
  <span data-ttu-id="f7103-103">Accodamento messaggi (noto anche come MSMQ) consente agli sviluppatori di applicazioni di comunicare in modo rapido, semplice e affidabile con i programmi applicativi mediante l'invio e la ricezione di messaggi.</span><span class="sxs-lookup"><span data-stu-id="f7103-103">Message Queuing (also known as MSMQ) makes it easy for developers to communicate with application programs quickly and reliably by sending and receiving messages.</span></span> <span data-ttu-id="f7103-104">Una coda di messaggi può trovarsi nel computer locale o in un computer remoto e può essere pubblica o privata.</span><span class="sxs-lookup"><span data-stu-id="f7103-104">A message queue may be located on the local computer or a remote computer, and may be public or private.</span></span> <span data-ttu-id="f7103-105">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], la gestione connessione MSMQ e l'attività Message Queue non supportano l'invio a una coda privata su un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="f7103-105">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], the MSMQ connection manager and Message Queue task do not support sending to a private queue on a remote computer.</span></span> <span data-ttu-id="f7103-106">Tuttavia, utilizzando l'attività Script, è possibile inviare facilmente un messaggio a una coda privata remota.</span><span class="sxs-lookup"><span data-stu-id="f7103-106">However, by using the Script task, it is easy to send a message to a remote private queue.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f7103-107">Se si desidera creare un'attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questo esempio di attività Script come punto iniziale per un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f7103-107">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="f7103-108">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="f7103-108">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="f7103-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7103-109">Description</span></span>  
 <span data-ttu-id="f7103-110">Nell'esempio seguente viene usata una gestione connessione MSMQ esistente, insieme agli oggetti e ai metodi dello spazio dei nomi System.Messaging, per inviare il testo contenuto in una variabile di pacchetto a una coda di messaggi privata remota.</span><span class="sxs-lookup"><span data-stu-id="f7103-110">The following example uses an existing MSMQ connection manager, together with objects and methods from the System.Messaging namespace, to send the text contained in a package variable to a remote private message queue.</span></span> <span data-ttu-id="f7103-111">La chiamata al metodo M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection (System. Object) della gestione connessione MSMQ restituisce un oggetto **MessageQueue** il cui `Send` metodo consente di eseguire questa attività.</span><span class="sxs-lookup"><span data-stu-id="f7103-111">The call to the M:Microsoft.SqlServer.Dts.ManagedConnections.MSMQConn.AcquireConnection(System.Object) method of the MSMQ connection manager returns a **MessageQueue** object whose `Send` method accomplishes this task.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="f7103-112">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="f7103-112">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="f7103-113">Creare una gestione connessione MSMQ con il nome predefinito.</span><span class="sxs-lookup"><span data-stu-id="f7103-113">Create an MSMQ connection manager with the default name.</span></span> <span data-ttu-id="f7103-114">Impostare il percorso di una coda privata remota valida, nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="f7103-114">Set the path of a valid remote private queue, in the following format:</span></span>  
  
    ```  
    FORMATNAME:DIRECT=OS:<computername>\private$\<queuename>  
    ```  
  
2.  <span data-ttu-id="f7103-115">Creare una [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variabile denominata **MessageText** di tipo `String` per passare il testo del messaggio nello script.</span><span class="sxs-lookup"><span data-stu-id="f7103-115">Create an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable named **MessageText** of type `String` to pass the message text into the script.</span></span> <span data-ttu-id="f7103-116">Immettere un messaggio predefinito come valore della variabile.</span><span class="sxs-lookup"><span data-stu-id="f7103-116">Enter a default message as the value of the variable.</span></span>  
  
3.  <span data-ttu-id="f7103-117">Aggiungere un'attività Script all'area di progettazione e modificarla.</span><span class="sxs-lookup"><span data-stu-id="f7103-117">Add a Script Task to the design surface and edit it.</span></span> <span data-ttu-id="f7103-118">Nella scheda **Script** dell'**Editor attività Script** aggiungere la variabile `MessageText` alla proprietà **ReadOnlyVariables** per rendere disponibile la variabile all'interno dello script.</span><span class="sxs-lookup"><span data-stu-id="f7103-118">On the **Script** tab of the **Script Task Editor**, add the `MessageText` variable to the **ReadOnlyVariables** property to make the variable available inside the script.</span></span>  
  
4.  <span data-ttu-id="f7103-119">Fare clic su **Modifica script** per aprire l'editor di script di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="f7103-119">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) script editor.</span></span>  
  
5.  <span data-ttu-id="f7103-120">Aggiungere un riferimento nel progetto di script allo spazio dei nomi `System.Messaging`.</span><span class="sxs-lookup"><span data-stu-id="f7103-120">Add a reference in the script project to the `System.Messaging` namespace.</span></span>  
  
6.  <span data-ttu-id="f7103-121">Sostituire il contenuto della finestra dello script con il codice nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="f7103-121">Replace the contents of the script window with the code in the following section.</span></span>  
  
## <a name="code"></a><span data-ttu-id="f7103-122">Codice</span><span class="sxs-lookup"><span data-stu-id="f7103-122">Code</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Messaging  
  
Public Class ScriptMain  
  
    Public Sub Main()  
  
        Dim remotePrivateQueue As MessageQueue  
        Dim messageText As String  
  
        remotePrivateQueue = _  
            DirectCast(Dts.Connections("Message Queue Connection Manager").AcquireConnection(Dts.Transaction), _  
            MessageQueue)  
        messageText = DirectCast(Dts.Variables("MessageText").Value, String)  
        remotePrivateQueue.Send(messageText)  
  
        Dts.TaskResult = ScriptResults.Success  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Messaging;  
  
public class ScriptMain  
{  
  
    public void Main()  
        {  
  
            MessageQueue remotePrivateQueue = new MessageQueue();  
            string messageText;  
  
            remotePrivateQueue = (MessageQueue)(Dts.Connections["Message Queue Connection Manager"].AcquireConnection(Dts.Transaction) as MessageQueue);  
            messageText = (string)(Dts.Variables["MessageText"].Value);  
            remotePrivateQueue.Send(messageText);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
```  
  
<span data-ttu-id="f7103-123">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f7103-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f7103-124">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="f7103-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f7103-125">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="f7103-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f7103-126">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f7103-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7103-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7103-127">See Also</span></span>  
 [<span data-ttu-id="f7103-128">Attività Message Queue</span><span class="sxs-lookup"><span data-stu-id="f7103-128">Message Queue Task</span></span>](../control-flow/message-queue-task.md)  
  
  
