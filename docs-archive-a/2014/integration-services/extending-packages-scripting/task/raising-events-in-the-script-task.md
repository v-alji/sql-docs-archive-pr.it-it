---
title: Generazione di eventi nell'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- events [Integration Services], scripts
- warnings [Integration Services]
- SSIS events, scripts
- errors [Integration Services], events
- SSIS Script task, events
- Events property
- Script task [Integration Services], events
ms.assetid: 21ea07d1-e267-4fb1-a6cc-82c95a39beae
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e20a276b91e434b6915cfb218eba17c07acd6544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715575"
---
# <a name="raising-events-in-the-script-task"></a><span data-ttu-id="47ae4-102">Generazione di eventi nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="47ae4-102">Raising Events in the Script Task</span></span>
  <span data-ttu-id="47ae4-103">Gli eventi consentono di segnalare errori, avvisi e altre informazioni, ad esempio l'avanzamento o lo stato delle attività, al pacchetto contenitore.</span><span class="sxs-lookup"><span data-stu-id="47ae4-103">Events provide a way to report errors, warnings, and other information, such as task progress or status, to the containing package.</span></span> <span data-ttu-id="47ae4-104">Il pacchetto fornisce gestori eventi per la gestione di notifiche degli eventi.</span><span class="sxs-lookup"><span data-stu-id="47ae4-104">The package provides event handlers for managing event notifications.</span></span> <span data-ttu-id="47ae4-105">L'attività Script può generare eventi chiamando metodi sulla proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> dell'oggetto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="47ae4-105">The Script task can raise events by calling methods on the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property of the `Dts` object.</span></span> <span data-ttu-id="47ae4-106">Per altre informazioni sulla gestione degli eventi da parte dei pacchetti di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], vedere [Gestori eventi di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="47ae4-106">For more information about how [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages handle events, see [Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md).</span></span>  
  
 <span data-ttu-id="47ae4-107">Gli eventi possono essere registrati in qualsiasi provider di log abilitato nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="47ae4-107">Events can be logged to any log provider that is enabled in the package.</span></span> <span data-ttu-id="47ae4-108">I provider di log archiviano informazioni sugli eventi in un archivio dati.</span><span class="sxs-lookup"><span data-stu-id="47ae4-108">Log providers store information about events in a data store.</span></span> <span data-ttu-id="47ae4-109">L'attività Script può anche utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> per registrare informazioni in un provider di log senza generare un evento.</span><span class="sxs-lookup"><span data-stu-id="47ae4-109">The Script task can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to log information to a log provider without raising an event.</span></span> <span data-ttu-id="47ae4-110">Per altre informazioni sull'uso del metodo <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A>, vedere [Registrazione nell'attività Script](logging-in-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="47ae4-110">For more information about how to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method, see [Logging in the Script Task](logging-in-the-script-task.md).</span></span>  
  
 <span data-ttu-id="47ae4-111">Per generare un evento, l'attività Script chiama uno dei metodi esposti dalla proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="47ae4-111">To raise an event, the Script task calls one of the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span> <span data-ttu-id="47ae4-112">Nella tabella seguente sono elencati i metodi esposti dalla proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A>.</span><span class="sxs-lookup"><span data-stu-id="47ae4-112">The following table lists the methods exposed by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Events%2A> property.</span></span>  
  
|<span data-ttu-id="47ae4-113">Event</span><span class="sxs-lookup"><span data-stu-id="47ae4-113">Event</span></span>|<span data-ttu-id="47ae4-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="47ae4-114">Description</span></span>|  
|-----------|-----------------|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireCustomEvent%2A>|<span data-ttu-id="47ae4-115">Genera un evento personalizzato definito dall'utente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="47ae4-115">Raises a user-defined custom event in the package.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A>|<span data-ttu-id="47ae4-116">Informa il pacchetto di una condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="47ae4-116">Informs the package of an error condition.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireInformation%2A>|<span data-ttu-id="47ae4-117">Fornisce informazioni all'utente.</span><span class="sxs-lookup"><span data-stu-id="47ae4-117">Provides information to the user.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireProgress%2A>|<span data-ttu-id="47ae4-118">Informa il pacchetto dello stato dell'attività.</span><span class="sxs-lookup"><span data-stu-id="47ae4-118">Informs the package of the progress of the task.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireQueryCancel%2A>|<span data-ttu-id="47ae4-119">Restituisce un valore che indica se il pacchetto richiede che l'attività venga chiusa in modo anomalo.</span><span class="sxs-lookup"><span data-stu-id="47ae4-119">Returns a value that indicates whether the package needs the task to shut down prematurely.</span></span>|  
|<xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A>|<span data-ttu-id="47ae4-120">Informa il pacchetto che l'attività è in uno stato che garantisce la notifica all'utente, ma non è una condizione di errore.</span><span class="sxs-lookup"><span data-stu-id="47ae4-120">Informs the package that the task is in a state that warrants user notification, but is not an error condition.</span></span>|  
  
## <a name="events-example"></a><span data-ttu-id="47ae4-121">Esempio di eventi</span><span class="sxs-lookup"><span data-stu-id="47ae4-121">Events Example</span></span>  
 <span data-ttu-id="47ae4-122">Nell'esempio seguente viene illustrato come generare eventi dall'attività Script.</span><span class="sxs-lookup"><span data-stu-id="47ae4-122">The following example demonstrates how to raise events from within the Script task.</span></span> <span data-ttu-id="47ae4-123">Viene utilizzata una funzione dell'API di Windows nativa per determinare se è disponibile una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="47ae4-123">The example uses a native Windows API function to determine whether an Internet connection is available.</span></span> <span data-ttu-id="47ae4-124">Se non sono disponibili connessioni, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="47ae4-124">If no connection is available, it raises an error.</span></span> <span data-ttu-id="47ae4-125">Se è in uso una connessione modem potenzialmente volatile, viene generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="47ae4-125">If a potentially volatile modem connection is in use, the example raises a warning.</span></span> <span data-ttu-id="47ae4-126">In caso contrario, viene restituito un messaggio informativo indicante che è stata rilevata una connessione Internet.</span><span class="sxs-lookup"><span data-stu-id="47ae4-126">Otherwise, it returns an informational message that an Internet connection has been detected.</span></span>  
  
```vb  
Private Declare Function InternetGetConnectedState Lib "wininet" _  
    (ByRef dwFlags As Long, ByVal dwReserved As Long) As Long  
  
Private Enum ConnectedStates  
    LAN = &H2  
    Modem = &H1  
    Proxy = &H4  
    Offline = &H20  
    Configured = &H40  
    RasInstalled = &H10  
End Enum  
  
Public Sub Main()  
  
    Dim dwFlags As Long  
    Dim connectedState As Long  
    Dim fireAgain as Boolean  
  
    connectedState = InternetGetConnectedState(dwFlags, 0)  
  
    If connectedState <> 0 Then  
        If (dwFlags And ConnectedStates.Modem) = ConnectedStates.Modem Then  
            Dts.Events.FireWarning(0, "Script Task Example", _  
                "Volatile Internet connection detected.", String.Empty, 0)  
        Else  
            Dts.Events.FireInformation(0, "Script Task Example", _  
                "Internet connection detected.", String.Empty, 0, fireAgain)  
        End If  
    Else  
        ' If not connected to the Internet, raise an error.  
        Dts.Events.FireError(0, "Script Task Example", _  
            "Internet connection not available.", String.Empty, 0)  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
using System.Runtime.InteropServices;  
  
public class ScriptMain  
{  
  
[DllImport("wininet")]  
        private extern static long InternetGetConnectedState(ref long dwFlags, long dwReserved);  
  
        private enum ConnectedStates  
        {  
            LAN = 0x2,  
            Modem = 0x1,  
            Proxy = 0x4,  
            Offline = 0x20,  
            Configured = 0x40,  
            RasInstalled = 0x10  
        };  
  
        public void Main()  
        {  
            //  
            long dwFlags = 0;  
            long connectedState;  
            bool fireAgain = true;  
            int state;  
  
            connectedState = InternetGetConnectedState(ref dwFlags, 0);  
            state = (int)ConnectedStates.Modem;  
            if (connectedState != 0)  
            {  
                if ((dwFlags & state) == state)  
                {  
                    Dts.Events.FireWarning(0, "Script Task Example", "Volatile Internet connection detected.", String.Empty, 0);  
                }  
                else  
                {  
                    Dts.Events.FireInformation(0, "Script Task Example", "Internet connection detected.", String.Empty, 0, ref fireAgain);  
                }  
            }  
            else  
            {  
                // If not connected to the Internet, raise an error.  
                Dts.Events.FireError(0, "Script Task Example", "Internet connection not available.", String.Empty, 0);  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
```  
  
<span data-ttu-id="47ae4-127">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="47ae4-127">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="47ae4-128">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="47ae4-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="47ae4-129">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="47ae4-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="47ae4-130">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="47ae4-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ae4-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47ae4-131">See Also</span></span>  
 <span data-ttu-id="47ae4-132">[Gestori eventi di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-event-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="47ae4-132">[Integration Services &#40;SSIS&#41; Event Handlers](../../integration-services-ssis-event-handlers.md) </span></span>  
 [<span data-ttu-id="47ae4-133">Aggiunta di un gestore eventi a un pacchetto</span><span class="sxs-lookup"><span data-stu-id="47ae4-133">Add an Event Handler to a Package</span></span>](../../add-an-event-handler-to-a-package.md)  
  
  
