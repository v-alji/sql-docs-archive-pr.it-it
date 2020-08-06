---
title: Implementazione di metadati esterni | Microsoft Docs
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
- disconnected validation [Integration Services]
- connected validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- metadata [Integration Services]
- data flow components [Integration Services], validating
- data flow components [Integration Services], external metadata
- custom data flow components [Integration Services], external metadata
- external metadata [Integration Services]
ms.assetid: 8f5bd3ed-3e79-43a4-b6c1-435e4c2cc8cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a6b77229c528bc08057e662a4b3761d1daf732f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713343"
---
# <a name="implementing-external-metadata"></a><span data-ttu-id="ed8f6-102">Implementazione di metadati esterni</span><span class="sxs-lookup"><span data-stu-id="ed8f6-102">Implementing External Metadata</span></span>
  <span data-ttu-id="ed8f6-103">Quando un componente è disconnesso dalla relativa origine dati, è possibile convalidare le colonne nelle raccolte di colonne di input e output in base alle colonne presenti nell'origine dati esterna utilizzando l'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100>.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-103">When a component is disconnected from its data source, you can validate the columns in the input and output column collections against the columns at its external data source by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100> interface.</span></span> <span data-ttu-id="ed8f6-104">Questa interfaccia consente di mantenere uno snapshot delle colonne presenti nell'origine dati esterna e di eseguire il mapping di queste colonne alle raccolte di colonne di input e output del componente.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-104">This interface lets you maintain a snapshot of the columns at the external data source and map these columns to the columns in the input and output column collection of the component.</span></span>  
  
 <span data-ttu-id="ed8f6-105">L'implementazione di colonne di metadati esterni aggiunge un livello di overhead e complessità allo sviluppo di componenti, perché è necessario mantenere una raccolta aggiuntiva di colonne ed eseguire la convalida in base ad essa, ma la possibilità di evitare onerosi round trip al server per la convalida giustifica questa attività di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-105">Implementing external metadata columns adds a layer of overhead and complexity to component development, because you must maintain and validate against an additional column collection, but the ability to avoid expensive round trips to the server for validation may make this development work worthwhile.</span></span>  
  
## <a name="populating-external-metadata-columns"></a><span data-ttu-id="ed8f6-106">Popolamento di colonne di metadati esterni</span><span class="sxs-lookup"><span data-stu-id="ed8f6-106">Populating External Metadata Columns</span></span>  
 <span data-ttu-id="ed8f6-107">Le colonne di metadati esterni vengono in genere aggiunte alla raccolta quando viene creata la corrispondente colonna di input o di output.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-107">External metadata columns are typically added to the collection when the corresponding input or output column is created.</span></span> <span data-ttu-id="ed8f6-108">Le nuove colonne vengono create chiamando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-108">New columns are created by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A> method.</span></span> <span data-ttu-id="ed8f6-109">Le proprietà della colonna vengono quindi impostate in base all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-109">The properties of the column are then set to match the external data source.</span></span>  
  
 <span data-ttu-id="ed8f6-110">Il mapping della colonna di metadati esterni alla corrispondente colonna di input o di output viene eseguito assegnando l'ID della prima alla proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> della seconda.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-110">The external metadata column is mapped to the corresponding input or output column by assigning the ID of the external metadata column to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property of the input or output column.</span></span> <span data-ttu-id="ed8f6-111">In questo modo è possibile individuare facilmente la colonna di metadati esterni per una specifica colonna di input o di output utilizzando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> della raccolta.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-111">This lets you locate the external metadata column easily for a specific input or output column by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> method of the collection.</span></span>  
  
 <span data-ttu-id="ed8f6-112">Nell'esempio seguente viene illustrato come creare una colonna di metadati esterni e quindi eseguirne il mapping a una colonna di output impostando la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A>.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-112">The following example shows how to create an external metadata column and then map the column to an output column by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property.</span></span>  
  
```csharp  
public void CreateExternalMetaDataColumn(IDTSOutput100 output, int outputColumnID )  
{  
    IDTSOutputColumn100 oColumn = output.OutputColumnCollection.GetObjectByID(outputColumnID);  
    IDTSExternalMetadataColumn100 eColumn = output.ExternalMetadataColumnCollection.New();  
  
    eColumn.DataType = oColumn.DataType;  
    eColumn.Precision = oColumn.Precision;  
    eColumn.Scale = oColumn.Scale;  
    eColumn.Length = oColumn.Length;  
    eColumn.CodePage = oColumn.CodePage;  
  
    oColumn.ExternalMetadataColumnID = eColumn.ID;  
}  
```  
  
```vb  
Public Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumnID As Integer)   
 Dim oColumn As IDTSOutputColumn100 = output.OutputColumnCollection.GetObjectByID(outputColumnID)   
 Dim eColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New   
 eColumn.DataType = oColumn.DataType   
 eColumn.Precision = oColumn.Precision   
 eColumn.Scale = oColumn.Scale   
 eColumn.Length = oColumn.Length   
 eColumn.CodePage = oColumn.CodePage   
 oColumn.ExternalMetadataColumnID = eColumn.ID   
End Sub  
```  
  
## <a name="validating-with-external-metadata-columns"></a><span data-ttu-id="ed8f6-113">Convalida delle colonne di metadati esterni</span><span class="sxs-lookup"><span data-stu-id="ed8f6-113">Validating with External Metadata Columns</span></span>  
 <span data-ttu-id="ed8f6-114">La convalida richiede passaggi aggiuntivi per i componenti che mantengono una raccolta di colonne di metadati esterni, perché è necessario eseguirla in base a una raccolta aggiuntiva di colonne.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-114">Validation requires additional steps for components that maintain an external metadata column collection, because you must validate against an additional collection of columns.</span></span> <span data-ttu-id="ed8f6-115">La convalida può essere eseguita in modalità connessa o disconnessa.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-115">Validation can be divided into connected validation or disconnected validation.</span></span>  
  
### <a name="connected-validation"></a><span data-ttu-id="ed8f6-116">Convalida in modalità connessa</span><span class="sxs-lookup"><span data-stu-id="ed8f6-116">Connected Validation</span></span>  
 <span data-ttu-id="ed8f6-117">Quando un componente è connesso a un'origine dati esterna, le colonne delle raccolte di input o output vengono verificate direttamente in base all'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-117">When a component is connected to an external data source, the columns in the input or output collections are verified directly against the external data source.</span></span> <span data-ttu-id="ed8f6-118">È inoltre necessario convalidare le colonne della raccolta di metadati esterni.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-118">Additionally, the columns in the external metadata collection must be validated.</span></span> <span data-ttu-id="ed8f6-119">Questa operazione è necessaria perché la raccolta di metadati esterni può essere modificata tramite l'**Editor avanzato** in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] e le modifiche non sono individuabili.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-119">This is required because the external metadata collection can be modified by using the **Advanced Editor** in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and changes made to the collection are not detectable.</span></span> <span data-ttu-id="ed8f6-120">Pertanto, se connessi, i componenti devono assicurarsi che le colonne della raccolta di colonne di metadati esterni continuino a riflettere le colonne presenti nell'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-120">Therefore, when connected, components must make sure that the columns in the external metadata column collection continue to reflect the columns at the external data source.</span></span>  
  
 <span data-ttu-id="ed8f6-121">È possibile scegliere di nascondere la raccolta di metadati esterni nel **Editor avanzato** impostando la <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> proprietà della raccolta su `false` .</span><span class="sxs-lookup"><span data-stu-id="ed8f6-121">You may choose to hide the external metadata collection in the **Advanced Editor** by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> property of the collection to `false`.</span></span> <span data-ttu-id="ed8f6-122">Tuttavia, in questo modo si nasconde anche la scheda **Mapping colonne** dell'editor, che consente agli utenti di eseguire il mapping delle colonne della raccolta di input o output alle colonne della raccolta di colonne di metadati esterni.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-122">However this also hides the **Column Mapping** tab of the editor, which lets users map columns from the input or output collection to the columns in the external metadata column collection.</span></span> <span data-ttu-id="ed8f6-123">L'impostazione di questa proprietà su `false` non impedisce agli sviluppatori di modificare la raccolta a livello di programmazione, ma fornisce un livello di protezione per la raccolta di colonne di metadati esterni di un componente utilizzato esclusivamente in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed8f6-123">Setting this property to `false` does not prevent developers from programmatically modifying the collection, but it does provide a level of protection for the external metadata column collection of a component that is used exclusively in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="disconnected-validation"></a><span data-ttu-id="ed8f6-124">Convalida in modalità disconnessa</span><span class="sxs-lookup"><span data-stu-id="ed8f6-124">Disconnected Validation</span></span>  
 <span data-ttu-id="ed8f6-125">Quando un componente è disconnesso da un'origine dati esterna, la convalida risulta semplificata, perché le colonne della raccolta di input o output vengono verificate direttamente in base alle colonne della raccolta di metadati esterni e non rispetto all'origine esterna.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-125">When a component is disconnected from an external data source, validation is simplified because the columns in the input or output collection are verified directly against the columns in the external metadata collection and not against the external source.</span></span> <span data-ttu-id="ed8f6-126">Un componente deve eseguire la convalida in modalità disconnessa quando la connessione all'origine dati esterna non è stata stabilita o quando la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> è `false`.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-126">A component should perform disconnected validation when the connection to its external data source has not been established, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="ed8f6-127">Nell'esempio di codice seguente è illustrata un'implementazione di un componente che esegue la convalida in base alla raccolta di colonne di metadati esterni.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-127">The following code example demonstrates an implementation of a component that performs validation against its external metadata column collection.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    if( this.isConnected && ComponentMetaData.ValidateExternalMetaData )  
    {  
        // TODO: Perform connected validation.  
    }  
    else  
    {  
        // TODO: Perform disconnected validation.  
    }  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
 If Me.isConnected AndAlso ComponentMetaData.ValidateExternalMetaData Then   
  ' TODO: Perform connected validation.  
 Else   
  ' TODO: Perform disconnected validation.  
 End If   
End Function  
```  
  
<span data-ttu-id="ed8f6-128">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ed8f6-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ed8f6-129">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="ed8f6-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ed8f6-130">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="ed8f6-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ed8f6-131">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="ed8f6-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8f6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed8f6-132">See Also</span></span>  
 [<span data-ttu-id="ed8f6-133">Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="ed8f6-133">Data Flow</span></span>](../../data-flow/data-flow.md)  
  
  
