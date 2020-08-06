---
title: Convalida di un componente flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ReinitializeMetaData method
- Validate method
- component validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- data flow components [Integration Services], validating
- validation [Integration Services]
ms.assetid: 1a7d5925-b387-4e31-af7f-c7f3c5151040
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9a78588c1e75697235e62e8955b65da466a37ea5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626826"
---
# <a name="validating-a-data-flow-component"></a><span data-ttu-id="24320-102">Convalida di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="24320-102">Validating a Data Flow Component</span></span>
  <span data-ttu-id="24320-103">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> della classe di base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> viene fornito per impedire l'esecuzione di un componente che non è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="24320-103">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class is provided to prevent execution of a component that is not configured correctly.</span></span> <span data-ttu-id="24320-104">Utilizzare questo metodo per verificare che un componente includa il numero previsto di oggetti di input e output, che i valori delle proprietà personalizzate del componente siano accettabili e che siano state specificate le eventuali connessioni richieste.</span><span class="sxs-lookup"><span data-stu-id="24320-104">Use this method to verify that a component has the expected number of input and output objects, that the custom properties of the component have acceptable values, and that any connections, if required, are specified.</span></span> <span data-ttu-id="24320-105">Utilizzare questo metodo anche per verificare che le colonne nelle raccolte di input e output includano i tipi di dati corretti e che l'oggetto <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSUsageType> di ogni colonna sia impostato correttamente per il componente.</span><span class="sxs-lookup"><span data-stu-id="24320-105">Use this method also to verify that the columns in the input and output collections have the correct data types and that the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSUsageType> of each column is set appropriately for the component.</span></span> <span data-ttu-id="24320-106">L'implementazione della classe di base assiste nel processo di convalida controllando la raccolta di colonne di input del componente e verificando che ogni colonna della raccolta faccia riferimento a una colonna presente in <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100> del componente a monte.</span><span class="sxs-lookup"><span data-stu-id="24320-106">The base class implementation assists in the validation process by checking the input column collection of the component and ensuring that each column in the collection refers to a column in the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100> of the upstream component.</span></span>  
  
## <a name="validate-method"></a><span data-ttu-id="24320-107">Metodo Validate</span><span class="sxs-lookup"><span data-stu-id="24320-107">Validate Method</span></span>  
 <span data-ttu-id="24320-108">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> viene chiamato ripetutamente quando un componente viene modificato in Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24320-108">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method is called repeatedly when a component is edited in [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="24320-109">È possibile fornire feedback alla finestra di progettazione e agli utenti del componente tramite il valore restituito dell'enumerazione <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> e inviando avvisi ed errori.</span><span class="sxs-lookup"><span data-stu-id="24320-109">You can provide feedback to the designer and to users of the component through the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> enumeration return value, and by posting warnings and errors.</span></span> <span data-ttu-id="24320-110">L'enumerazione <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> contiene tre valori che indicano varie fasi di errore e un quarto valore, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISVALID>, che indica se il componente è configurato correttamente e pronto per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="24320-110">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus> enumeration contains three values that indicate various stages of failure, and a fourth, <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISVALID>, that indicates whether the component is correctly configured and ready to execute.</span></span>  
  
 <span data-ttu-id="24320-111">Il valore <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> indica che esiste un errore in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> e che il componente può correggere gli errori.</span><span class="sxs-lookup"><span data-stu-id="24320-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> value indicates that an error exists in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>, and that the component can repair the errors.</span></span> <span data-ttu-id="24320-112">Se un componente rileva un errore di metadati che può correggere, l'errore non deve essere corretto nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> e <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> non deve essere modificato durante la convalida.</span><span class="sxs-lookup"><span data-stu-id="24320-112">If a component encounters a metadata error that it can repair, it should not fix the error in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method, and <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> should not be modified during validation.</span></span> <span data-ttu-id="24320-113">Al contrario, il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> deve restituire solo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> e il componente deve correggere l'errore in una chiamata al metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>, come descritto più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="24320-113">Instead, the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method should return only <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA>, and the component should repair the error in a call to the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method, as described later in this section.</span></span>  
  
 <span data-ttu-id="24320-114">Il valore <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISBROKEN> indica che il componente contiene un errore che può essere corretto modificando il componente nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="24320-114">The <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISBROKEN> value indicates that the component has an error that can be rectified by editing the component in the designer.</span></span> <span data-ttu-id="24320-115">L'errore è in genere causato da una proprietà personalizzata o una connessione richiesta che non è specificata o non è impostata correttamente.</span><span class="sxs-lookup"><span data-stu-id="24320-115">The error is typically caused by a custom property or a required connection that is not specified or is set incorrectly.</span></span>  
  
 <span data-ttu-id="24320-116">Il valore finale dell'errore è <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISCORRUPT>, che indica che il componente ha individuato errori che dovrebbero verificarsi solo se la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> è stata modificata direttamente, modificando il codice XML del pacchetto o utilizzando il modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="24320-116">The final error value is <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_ISCORRUPT>, which indicates that the component has discovered errors that should only occur if the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property has been modified directly, either by editing the package XML or by using the object model.</span></span> <span data-ttu-id="24320-117">Ad esempio, questo tipo di errore si verifica quando un componente ha aggiunto solo un input ma durante la convalida vengono individuati più input in <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="24320-117">For example, this kind of error occurs when a component has added only a single input, but validation discovers that more than one input exists in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A>.</span></span> <span data-ttu-id="24320-118">Gli errori che generano questo valore restituito possono essere corretti solo reimpostando il componente tramite il pulsante **Reimposta** della finestra di dialogo **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="24320-118">Errors that generate this return value can only be repaired by resetting the component by using the **Reset** button in the **Advanced Editor** dialog box.</span></span>  
  
 <span data-ttu-id="24320-119">Oltre a restituire valori di errori, i componenti forniscono feedback inviando avvisi o errori durante la convalida.</span><span class="sxs-lookup"><span data-stu-id="24320-119">Besides returning error values, components provide feedback by posting warnings or errors during validation.</span></span> <span data-ttu-id="24320-120">I metodi <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> forniscono questo meccanismo.</span><span class="sxs-lookup"><span data-stu-id="24320-120">The <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireWarning%2A> and <xref:Microsoft.SqlServer.Dts.Runtime.IDTSComponentEvents.FireError%2A> methods provide this mechanism.</span></span> <span data-ttu-id="24320-121">Quando questi metodi vengono chiamati, tali eventi vengono inviati nella finestra **Elenco errori** di [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24320-121">When these methods are called, these events are posted in the **Error List** window of [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="24320-122">Gli sviluppatori di componenti possono quindi fornire feedback diretto agli utenti sugli errori che si sono verificati e, se necessario, su come correggerli.</span><span class="sxs-lookup"><span data-stu-id="24320-122">Component developers can then provide direct feedback to users on the errors that have occurred, and if appropriate, how to correct them.</span></span>  
  
 <span data-ttu-id="24320-123">Nell'esempio di codice seguente viene illustrata un'implementazione sottoposta a override di <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="24320-123">The following code example shows an overridden implementation of <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    bool pbCancel = false;  
  
    // Validate that there is one input.  
    if (ComponentMetaData.InputCollection.Count != 1)  
    {  
    ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of inputs.", "", 0, out pbCancel);  
    return DTSValidationStatus.VS_ISCORRUPT;  
    }  
  
    // Validate that the UserName custom property is set.  
    if (ComponentMetaData.CustomPropertyCollection["UserName"].Value == null || ((string)ComponentMetaData.CustomPropertyCollection["UserName"].Value).Length == 0)  
    {  
        ComponentMetaData.FireError(0, ComponentMetaData.Name, "The UserName property must be set.", "", 0, out pbCancel);  
        return DTSValidationStatus.VS_ISBROKEN;  
    }  
  
    // Validate that there is one output.  
    if (ComponentMetaData.OutputCollection.Count != 1)  
    {  
        ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of outputs.", "", 0, out pbCancel);  
        return DTSValidationStatus.VS_ISCORRUPT;  
    }  
  
    // Let the base class verify that the input column reflects the output   
    // of the upstream component.  
    return base.Validate();  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
  
 Dim pbCancel As Boolean = False  
  
 ' Validate that there is one input.  
 If Not (ComponentMetaData.InputCollection.Count = 1) Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of inputs.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISCORRUPT   
 End If   
  
 ' Validate that the UserName custom property is set.  
 If ComponentMetaData.CustomPropertyCollection("UserName").Value Is Nothing OrElse CType(ComponentMetaData.CustomPropertyCollection("UserName").Value, String).Length = 0 Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "The UserName property must be set.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISBROKEN   
 End If   
  
 ' Validate that there is one output.  
 If Not (ComponentMetaData.OutputCollection.Count = 1) Then   
   ComponentMetaData.FireError(0, ComponentMetaData.Name, "Incorrect number of outputs.", "", 0, pbCancel)   
   Return DTSValidationStatus.VS_ISCORRUPT   
 End If   
  
 ' Let the base class verify that the input column reflects the output   
 ' of the upstream component.  
  
 Return MyBase.Validate   
  
End Function  
```  
  
## <a name="reinitializemetadata-method"></a><span data-ttu-id="24320-124">Metodo ReinitializeMetaData</span><span class="sxs-lookup"><span data-stu-id="24320-124">ReinitializeMetaData Method</span></span>  
 <span data-ttu-id="24320-125">Il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> viene chiamato da Progettazione [!INCLUDE[ssIS](../../../includes/ssis-md.md)] quando si modifica un componente che restituisce <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> dal metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="24320-125">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method is called by [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer whenever you edit a component that returns <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSValidationStatus.VS_NEEDSNEWMETADATA> from its <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.Validate%2A> method.</span></span> <span data-ttu-id="24320-126">I componenti devono contenere codice che rileva e corregge i problemi identificati dal componente durante la convalida.</span><span class="sxs-lookup"><span data-stu-id="24320-126">Components should contain code that detects and corrects the problems identified by the component during validation.</span></span>  
  
 <span data-ttu-id="24320-127">Nell'esempio seguente viene illustrato un componente che rileva problemi durante la convalida e li corregge nel metodo <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A>.</span><span class="sxs-lookup"><span data-stu-id="24320-127">The following example shows a component that detects problems during validation and fixes these errors in the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ReinitializeMetaData%2A> method.</span></span>  
  
```csharp  
private bool areInputColumnsValid = true;  
public override DTSValidationStatus Validate()  
{  
    IDTSInput100 input = ComponentMetaData.InputCollection[0];  
    IDTSVirtualInput100 vInput = input.GetVirtualInput();  
  
    bool Cancel = false;  
    foreach (IDTSInputColumn100 column in input.InputColumnCollection)  
    {  
        try  
        {  
            IDTSVirtualInputColumn100 vColumn = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID);  
        }  
        catch  
        {  
            ComponentMetaData.FireError(0, ComponentMetaData.Name, "The input column " + column.IdentificationString + " does not match a column in the upstream component.", "", 0, out Cancel);  
            areInputColumnsValid = false;  
            return DTSValidationStatus.VS_NEEDSNEWMETADATA;  
        }  
    }  
  
    return DTSValidationStatus.VS_ISVALID;  
}  
public override void ReinitializeMetaData()  
{  
    if (!areInputColumnsValid)  
    {  
        IDTSInput100 input = ComponentMetaData.InputCollection[0];  
        IDTSVirtualInput100 vInput = input.GetVirtualInput();  
  
        foreach (IDTSInputColumn100 column in input.InputColumnCollection)  
        {  
            IDTSVirtualInputColumn100 vColumn = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID);  
  
            if (vColumn == null)  
                input.InputColumnCollection.RemoveObjectByID(column.ID);  
        }  
        areInputColumnsValid = true;  
    }  
}  
```  
  
```vb  
Private areInputColumnsValid As Boolean = True   
  
Public  Overrides Function Validate() As DTSValidationStatus   
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
 Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput   
 Dim Cancel As Boolean = False   
 For Each column As IDTSInputColumn100 In input.InputColumnCollection   
   Try   
     Dim vColumn As IDTSVirtualInputColumn100 = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID)   
   Catch   
     ComponentMetaData.FireError(0, ComponentMetaData.Name, "The input column " + column.IdentificationString + " does not match a column in the upstream component.", "", 0, Cancel)   
     areInputColumnsValid = False   
     Return DTSValidationStatus.VS_NEEDSNEWMETADATA   
   End Try   
 Next   
 Return DTSValidationStatus.VS_ISVALID   
End Function   
  
Public  Overrides Sub ReinitializeMetaData()   
 If Not areInputColumnsValid Then   
   Dim input As IDTSInput100 = ComponentMetaData.InputCollection(0)   
   Dim vInput As IDTSVirtualInput100 = input.GetVirtualInput   
   For Each column As IDTSInputColumn100 In input.InputColumnCollection   
     Dim vColumn As IDTSVirtualInputColumn100 = vInput.VirtualInputColumnCollection.GetVirtualInputColumnByLineageID(column.LineageID)   
     If vColumn Is Nothing Then   
       input.InputColumnCollection.RemoveObjectByID(column.ID)   
     End If   
   Next   
   areInputColumnsValid = True   
 End If   
End Sub  
```  
  
<span data-ttu-id="24320-128">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="24320-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="24320-129">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="24320-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="24320-130">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="24320-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="24320-131">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="24320-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
