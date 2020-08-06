---
title: Registrazione nell'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SQL Server Integration Services packages, logs
- SSIS packages, logs
- logs [Integration Services], scripts
- Integration Services packages, logs
- Log method
- SSIS Script task, logs
- Script task [Integration Services], logs
- packages [Integration Services], logs
ms.assetid: 2e11fc15-df18-4309-bd2d-fc58aa4b9b7a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 61f7a46088de5df2765d860bd4a43e4872a1be6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715579"
---
# <a name="logging-in-the-script-task"></a><span data-ttu-id="a3a90-102">Registrazione nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="a3a90-102">Logging in the Script Task</span></span>
  <span data-ttu-id="a3a90-103">L'utilizzo della registrazione nei pacchetti di [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] consente di registrare informazioni dettagliate su stato di esecuzione, risultati e problemi, tramite la registrazione di eventi predefiniti o di messaggi definiti dall'utente da analizzare in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="a3a90-103">The use of logging in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages lets you record detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="a3a90-104">L'attività Script può utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> dell'oggetto `Dts` per registrare dati definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a3a90-104">The Script task can use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method of the `Dts` object to log user-defined data.</span></span> <span data-ttu-id="a3a90-105">Se la registrazione è abilitata e l'evento **ScriptTaskLogEntry** è selezionato per la registrazione nella scheda **Dettagli** della finestra di dialogo **Configura log SSIS**, una singola chiamata al metodo <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> archivia le informazioni dell'evento in tutti i provider di log configurati per l'attività.</span><span class="sxs-lookup"><span data-stu-id="a3a90-105">If logging is enabled, and the **ScriptTaskLogEntry** event is selected for logging on the **Details** tab of the **Configure SSIS Logs** dialog box, a single call to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method stores the event information in all the log providers configured for the task.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a3a90-106">Anche se è possibile eseguire direttamente la registrazione dall'attività Script, è consigliabile implementare eventi anziché registrare.</span><span class="sxs-lookup"><span data-stu-id="a3a90-106">Although you can perform logging directly from your Script task, you may want to consider implementing events rather than logging.</span></span> <span data-ttu-id="a3a90-107">Quando si utilizzano gli eventi, oltre ad abilitare la registrazione dei messaggi di eventi, è anche possibile rispondere all'evento con gestori eventi predefiniti o definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a3a90-107">When using events, not only can you enable the logging of event messages, but you can also respond to the event with default or user-defined event handlers.</span></span>  
  
 <span data-ttu-id="a3a90-108">Per altre informazioni sulla registrazione, vedere [Registrazione di Integration Services &#40;SSIS&#41;](../../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="a3a90-108">For more information about logging, see [Integration Services &#40;SSIS&#41; Logging](../../performance/integration-services-ssis-logging.md).</span></span>  
  
## <a name="logging-example"></a><span data-ttu-id="a3a90-109">Esempio di registrazione</span><span class="sxs-lookup"><span data-stu-id="a3a90-109">Logging Example</span></span>  
 <span data-ttu-id="a3a90-110">Nell'esempio seguente è illustrata la registrazione dall'attività Script registrando un valore che rappresenta il numero di righe elaborate.</span><span class="sxs-lookup"><span data-stu-id="a3a90-110">The following example demonstrates logging from the Script task by logging a value that represents the number of rows processed.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim rowsProcessed As Integer = 100  
    Dim emptyBytes(0) As Byte  
  
    Try  
        Dts.Log("Rows processed: " & rowsProcessed.ToString, _  
            0, _  
            emptyBytes)  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        'An error occurred.  
        Dts.Events.FireError(0, "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Dts.Runtime;  
  
public class ScriptMain  
{  
  
    public void Main()  
        {  
            //  
            int rowsProcessed = 100;  
            byte[] emptyBytes = new byte[0];  
  
            try  
            {  
                Dts.Log("Rows processed: " + rowsProcessed.ToString(), 0, emptyBytes);  
                Dts.TaskResult = (int)ScriptResults.Success;  
            }  
            catch (Exception ex)  
            {  
                //An error occurred.  
                Dts.Events.FireError(0, "Script Task Example", ex.Message + "\r" + ex.StackTrace, String.Empty, 0);  
                Dts.TaskResult = (int)ScriptResults.Failure;  
            }  
  
        }  
```  
  
 <span data-ttu-id="a3a90-111">}</span><span class="sxs-lookup"><span data-stu-id="a3a90-111">}</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="a3a90-112">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="a3a90-112">External Resources</span></span>  
  
<span data-ttu-id="a3a90-113">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a3a90-113">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a3a90-114">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="a3a90-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a3a90-115">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="a3a90-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a3a90-116">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="a3a90-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a90-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3a90-117">See Also</span></span>  
 [<span data-ttu-id="a3a90-118">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="a3a90-118">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
