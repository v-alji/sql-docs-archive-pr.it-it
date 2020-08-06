---
title: Registrazione e definizione di voci di log in un componente flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- logs [Integration Services], custom
- custom log entries [Integration Services]
- custom data flow components [Integration Services], logging
- data flow components [Integration Services], logging
ms.assetid: 2190dba9-59b5-480b-b8e9-21d5a54c5917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 14dfec71679bbe455ae8be5face98b776a80b9e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713320"
---
# <a name="logging-and-defining-log-entries-in-a-data-flow-component"></a><span data-ttu-id="1749e-102">Registrazione e definizione di voci di log in un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="1749e-102">Logging and Defining Log Entries in a Data Flow Component</span></span>
  <span data-ttu-id="1749e-103">I componenti personalizzati del flusso di dati possono inserire messaggi in una voce di log esistente tramite il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> dell'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="1749e-103">Custom data flow components can post messages to an existing log entry by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="1749e-104">Possono inoltre presentare informazioni all'utente tramite il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> o metodi simili dell'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>.</span><span class="sxs-lookup"><span data-stu-id="1749e-104">They can also present information to the user by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> method or similar methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="1749e-105">Tuttavia, questo approccio genera l'overhead della generazione e gestione di eventi aggiuntivi e forza l'utente a esaminare numerosi messaggi informativi dettagliati alla ricerca di quelli che potrebbero interessarlo.</span><span class="sxs-lookup"><span data-stu-id="1749e-105">However, this approach incurs the overhead of raising and handling additional events, and forces the user to sift through verbose informational messages for the messages that may be of interest to them.</span></span> <span data-ttu-id="1749e-106">È possibile utilizzare una voce di log personalizzata, come descritto di seguito, per fornire informazioni di log personalizzate con etichette distinte agli utenti del componente.</span><span class="sxs-lookup"><span data-stu-id="1749e-106">You can use a custom log entry as described below to provide distinctly labeled custom log information to users of your component.</span></span>  
  
## <a name="registering-and-using-a-custom-log-entry"></a><span data-ttu-id="1749e-107">Registrazione e utilizzo di una voce di log personalizzata</span><span class="sxs-lookup"><span data-stu-id="1749e-107">Registering and Using a Custom Log Entry</span></span>  
  
### <a name="registering-a-custom-log-entry"></a><span data-ttu-id="1749e-108">Registrazione di una voce di log personalizzata</span><span class="sxs-lookup"><span data-stu-id="1749e-108">Registering a Custom Log Entry</span></span>  
 <span data-ttu-id="1749e-109">Per registrare una voce di log personalizzata per il componente, eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> della classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>.</span><span class="sxs-lookup"><span data-stu-id="1749e-109">To register a custom log entry for use by your component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="1749e-110">Nell'esempio seguente viene registrata una voce di log personalizzata e vengono forniti un nome e una descrizione.</span><span class="sxs-lookup"><span data-stu-id="1749e-110">The following example registers a custom log entry and provides a name and description.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Runtime;  
...  
private const string MyLogEntryName = "My Custom Component Log Entry";  
private const string MyLogEntryDescription = "Log entry from My Custom Component ";  
...  
    public override void RegisterLogEntries()  
    {  
      this.LogEntryInfos.Add(MyLogEntryName,  
        MyLogEntryDescription,  
        Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT);  
    }  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
...  
Private Const MyLogEntryName As String = "My Custom Component Log Entry"   
Private Const MyLogEntryDescription As String = "Log entry from My Custom Component "  
...  
Public  Overrides Sub RegisterLogEntries()   
  Me.LogEntryInfos.Add(MyLogEntryName, _  
    MyLogEntryDescription, _  
    Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT)   
End Sub  
```  
  
 <span data-ttu-id="1749e-111">L'enumerazione <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> fornisce un hint al runtime sulla frequenza con cui verrà registrato l'evento:</span><span class="sxs-lookup"><span data-stu-id="1749e-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> enumeration provides a hint to the runtime about how frequently the event will be logged:</span></span>  
  
-   <span data-ttu-id="1749e-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: l'evento viene registrato occasionalmente, non durante ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1749e-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: Event is logged only sometimes, not during every execution.</span></span>  
  
-   <span data-ttu-id="1749e-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: l'evento viene registrato un numero costante di volte durante ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1749e-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: Event is logged a constant number of times during every execution.</span></span>  
  
-   <span data-ttu-id="1749e-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: l'evento viene registrato un numero di volte proporzionale alla quantità di lavoro completata.</span><span class="sxs-lookup"><span data-stu-id="1749e-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: Event is logged a number of times proportional to the amount of work completed.</span></span>  
  
 <span data-ttu-id="1749e-115">Negli esempi precedenti viene utilizzato <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> perché il componente si aspetta di registrare una voce una volta ogni esecuzione.</span><span class="sxs-lookup"><span data-stu-id="1749e-115">The example above uses <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> because the component expects to log an entry once per execution.</span></span>  
  
 <span data-ttu-id="1749e-116">Dopo la registrazione della voce di log personalizzata e l'aggiunta di un'istanza del componente personalizzato nell'area di progettazione del flusso di dati, nella finestra di dialogo **Registrazione** della finestra di progettazione viene visualizzata una nuova voce di log denominata "My Custom Component Log Entry" nell'elenco di voci di log disponibili.</span><span class="sxs-lookup"><span data-stu-id="1749e-116">After registering the custom log entry and adding an instance of your custom component to the data flow designer surface, the **Logging** dialog box in the designer displays a new log entry with the name "My Custom Component Log Entry" in the list of available log entries.</span></span>  
  
### <a name="logging-to-a-custom-log-entry"></a><span data-ttu-id="1749e-117">Registrazione in una voce di log personalizzata</span><span class="sxs-lookup"><span data-stu-id="1749e-117">Logging to a Custom Log Entry</span></span>  
 <span data-ttu-id="1749e-118">Dopo la registrazione della voce di log personalizzata, il componente può registrare messaggi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1749e-118">After registering the custom log entry, the component can now log custom messages.</span></span> <span data-ttu-id="1749e-119">Nell'esempio seguente viene scritta una voce di log personalizzata durante il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> che contiene il testo di un'istruzione SQL utilizzata dal componente.</span><span class="sxs-lookup"><span data-stu-id="1749e-119">The example below writes a custom log entry during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method that contains the text of a SQL statement used by the component.</span></span>  
  
```csharp  
public override void PreExecute()  
{  
  DateTime now = DateTime.Now;  
  byte[] additionalData = null;  
  this.ComponentMetaData.PostLogMessage(MyLogEntryName,  
    this.ComponentMetaData.Name,  
    "Command Sent was: " + myCommand.CommandText,  
    now, now, 0, ref additionalData);  
}  
```  
  
```vb  
Public  Overrides Sub PreExecute()   
  Dim now As DateTime = DateTime.Now   
  Dim additionalData As Byte() = Nothing   
  Me.ComponentMetaData.PostLogMessage(MyLogEntryName, _  
    Me.ComponentMetaData.Name, _  
    "Command Sent was: " + myCommand.CommandText, _  
    now, now, 0, additionalData)   
End Sub  
```  
  
 <span data-ttu-id="1749e-120">A questo punto, quando l'utente esegue il pacchetto, dopo la selezione di "My Custom Component Log Entry" nella finestra di dialogo **Registrazione**, il log conterrà una voce chiaramente identificata come "User::My Custom Component Log Entry".</span><span class="sxs-lookup"><span data-stu-id="1749e-120">Now when the user executes the package, after selecting the "My Custom Component Log Entry" in the **Logging** dialog box, the log will contain an entry clearly labeled as "User::My Custom Component Log Entry."</span></span> <span data-ttu-id="1749e-121">Questa nuova voce di log contiene il testo dell'istruzione SQL, il timestamp ed eventuali altri dati registrati dallo sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="1749e-121">This new log entry contains the text of the SQL statement, the timestamp, and any additional data logged by the developer.</span></span>  
  
<span data-ttu-id="1749e-122">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="1749e-122">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="1749e-123">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="1749e-123">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="1749e-124">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="1749e-124">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="1749e-125">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="1749e-125">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1749e-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1749e-126">See Also</span></span>  
 [<span data-ttu-id="1749e-127">Registrazione di Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="1749e-127">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
