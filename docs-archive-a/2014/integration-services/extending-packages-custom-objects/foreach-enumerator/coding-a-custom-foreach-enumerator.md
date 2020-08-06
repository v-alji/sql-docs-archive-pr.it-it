---
title: Scrittura del codice di un enumeratore Foreach personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services], coding
ms.assetid: 279cf6de-d06f-40e7-b8ca-569310449f36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b7e6c16124f4682dbdc98f602417bf8f68ce099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626160"
---
# <a name="coding-a-custom-foreach-enumerator"></a><span data-ttu-id="f6724-102">Scrittura del codice di un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="f6724-102">Coding a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="f6724-103">Dopo avere creato una classe che eredita dalla classe di base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> e avere applicato l'attributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> alla classe, è necessario eseguire l'override dell'implementazione delle proprietà e dei metodi della classe di base per fornire la funzionalità personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f6724-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="f6724-104">Per un esempio reale di enumeratore personalizzato, vedere [Sviluppo di un'interfaccia utente per un enumeratore Foreach personalizzato](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span><span class="sxs-lookup"><span data-stu-id="f6724-104">For a working sample of a custom enumerator, see [Developing a User Interface for a Custom ForEach Enumerator](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span></span>  
  
## <a name="initializing-the-enumerator"></a><span data-ttu-id="f6724-105">Inizializzazione dell'enumeratore</span><span class="sxs-lookup"><span data-stu-id="f6724-105">Initializing the Enumerator</span></span>  
 <span data-ttu-id="f6724-106">È possibile eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> per memorizzare nella cache i riferimenti alle gestioni connessioni definite nel pacchetto e i riferimenti all'interfaccia degli eventi che è possibile utilizzare per generare errori, avvisi e messaggi informativi.</span><span class="sxs-lookup"><span data-stu-id="f6724-106">You can override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> method to cache references to the connection managers defined in the package, and to cache references to the events interface that you can use to raise errors, warnings, and informational messages.</span></span>  
  
## <a name="validating-the-enumerator"></a><span data-ttu-id="f6724-107">Convalida dell'enumeratore</span><span class="sxs-lookup"><span data-stu-id="f6724-107">Validating the Enumerator</span></span>  
 <span data-ttu-id="f6724-108">Eseguire l'override del metodo <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> per verificare che l'enumeratore sia configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f6724-108">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> method to verify that the enumerator is correctly configured.</span></span> <span data-ttu-id="f6724-109">Se il metodo restituisce `Failure`, l'enumeratore e il pacchetto che lo contiene non verranno eseguiti.</span><span class="sxs-lookup"><span data-stu-id="f6724-109">If the method returns `Failure`, the enumerator and the package that contains the enumerator will not be executed.</span></span> <span data-ttu-id="f6724-110">L'implementazione di questo metodo è specifica di ogni enumeratore, ma se l'enumeratore si basa su oggetti <xref:Microsoft.SqlServer.Dts.Runtime.Variable> o <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, è necessario aggiungere codice per verificare che questi oggetti esistano nelle raccolte fornite al metodo.</span><span class="sxs-lookup"><span data-stu-id="f6724-110">The implementation of this method is specific to each enumerator, but if the enumerator relies on <xref:Microsoft.SqlServer.Dts.Runtime.Variable> or <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects, you should add code to verify that these objects exist in the collections that are provided to the method.</span></span>  
  
 <span data-ttu-id="f6724-111">Nell'esempio di codice seguente è illustrata un'implementazione di <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> che verifica una variabile specificata in una proprietà dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="f6724-111">The following code example demonstrates an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> that checks for a variable specified in a property of the enumerator.</span></span>  
  
```csharp  
private string variableNameValue;  
  
public string VariableName  
{  
    get{ return this.variableNameValue; }  
    set{ this.variableNameValue = value; }  
}  
  
public override DTSExecResult Validate(Connections connections, VariableDispenser variableDispenser, IDTSInfoEvents infoEvents, IDTSLogging log)  
{  
    if (!variableDispenser.Contains(this.variableNameValue))  
    {  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + this.variableNameValue + " does not exist in the collection.", "", 0);  
            return DTSExecResult.Failure;  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Private variableNameValue As String  
  
Public Property VariableName() As String  
    Get   
         Return Me.variableNameValue  
    End Get  
    Set (ByVal Value As String)   
         Me.variableNameValue = value  
    End Set  
End Property  
  
Public Overrides Function Validate(ByVal connections As Connections, ByVal variableDispenser As VariableDispenser, ByVal infoEvents As IDTSInfoEvents, ByVal log As IDTSLogging) As DTSExecResult  
    If Not variableDispenser.Contains(Me.variableNameValue) Then  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + Me.variableNameValue + " does not exist in the collection.", "", 0)  
            Return DTSExecResult.Failure  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
## <a name="returning-the-collection"></a><span data-ttu-id="f6724-112">Restituzione della raccolta</span><span class="sxs-lookup"><span data-stu-id="f6724-112">Returning the Collection</span></span>  
 <span data-ttu-id="f6724-113">Durante l'esecuzione il contenitore <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> chiama il metodo <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> dell'enumeratore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f6724-113">During execution, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="f6724-114">In questo metodo l'enumeratore crea e popola la raccolta di elementi, quindi la restituisce.</span><span class="sxs-lookup"><span data-stu-id="f6724-114">In this method, the enumerator creates and populates its collection of items, and then returns the collection.</span></span> <span data-ttu-id="f6724-115"><xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> scorre quindi gli elementi della raccolta ed esegue il flusso di controllo per ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="f6724-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates the items in the collection, and executes its control flow for each item in the collection.</span></span>  
  
 <span data-ttu-id="f6724-116">Nell'esempio seguente è illustrata un'implementazione di <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> che restituisce una matrice di numeri interi casuali.</span><span class="sxs-lookup"><span data-stu-id="f6724-116">The following example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> that returns an array of random integers.</span></span>  
  
```csharp  
public override object GetEnumerator()  
{  
    ArrayList numbers = new ArrayList();  
  
    Random randomNumber = new Random(DateTime.Now);  
  
    for( int x=0; x < 100; x++ )  
        numbers.Add( randomNumber.Next());  
  
    return numbers;  
}  
```  
  
```vb  
Public Overrides Function GetEnumerator() As Object  
    Dim numbers As ArrayList =  New ArrayList()   
  
    Dim randomNumber As Random =  New Random(DateTime.Now)   
  
        Dim x As Integer  
        For  x = 0 To  100- 1  Step  x + 1  
        numbers.Add(randomNumber.Next())  
        Next  
  
    Return numbers  
End Function  
```  
  
<span data-ttu-id="f6724-117">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="f6724-117">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="f6724-118">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="f6724-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="f6724-119">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="f6724-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="f6724-120">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f6724-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6724-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6724-121">See Also</span></span>  
 <span data-ttu-id="f6724-122">[Creazione di un enumeratore Foreach personalizzato](creating-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="f6724-122">[Creating a Custom Foreach Enumerator](creating-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="f6724-123">Sviluppo di un'interfaccia utente per un enumeratore Foreach personalizzato</span><span class="sxs-lookup"><span data-stu-id="f6724-123">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
