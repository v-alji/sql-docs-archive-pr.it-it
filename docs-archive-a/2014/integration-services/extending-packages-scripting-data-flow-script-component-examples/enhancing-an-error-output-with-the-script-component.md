---
title: Ottimizzazione di un output degli errori con il componente script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- transformations [Integration Services], components
- Script component [Integration Services], examples
- error outputs [Integration Services], enhancing
- Script component [Integration Services], transformation components
ms.assetid: f7c02709-f1fa-4ebd-b255-dc8b81feeaa5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 18637aa1e147ce989645ae859681929f4d0c438a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637436"
---
# <a name="enhancing-an-error-output-with-the-script-component"></a><span data-ttu-id="af751-102">Ottimizzazione di un output degli errori con il componente script</span><span class="sxs-lookup"><span data-stu-id="af751-102">Enhancing an Error Output with the Script Component</span></span>
  <span data-ttu-id="af751-103">Per impostazione predefinita, le due colonne supplementari in un output degli errori di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], ovvero ErrorCode e ErrorColumn, contengono solo codici numerici che rappresentano un numero di errore, nonché l'ID della colonna in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="af751-103">By default, the two extra columns in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error output, ErrorCode and ErrorColumn, contain only numeric codes that represent an error number, and the ID of the column in which the error occurred.</span></span> <span data-ttu-id="af751-104">Questi valori numerici possono avere un'utilità limitata senza la descrizione dell'errore corrispondente.</span><span class="sxs-lookup"><span data-stu-id="af751-104">These numeric values may be of limited use without the corresponding error description.</span></span>  
  
 <span data-ttu-id="af751-105">In questo argomento viene descritto come aggiungere una colonna di descrizioni degli errori ai dati dell'output degli errori esistente nel flusso di dati tramite il componente Script.</span><span class="sxs-lookup"><span data-stu-id="af751-105">This topic describes how to add an error description column to existing error output data in the data flow by using the Script component.</span></span> <span data-ttu-id="af751-106">Nell'esempio viene aggiunta la descrizione dell'errore che corrisponde a un codice di errore specifico predefinito di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utilizzando il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> dell'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponibile tramite la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> del componente script.</span><span class="sxs-lookup"><span data-stu-id="af751-106">The example adds the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property of the Script component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af751-107">Se si desidera creare un componente da riutilizzare più facilmente con più attività Flusso di dati e più pacchetti, è possibile utilizzare il codice di questo esempio di componente script come punto iniziale per un componente del flusso di dati personalizzato.</span><span class="sxs-lookup"><span data-stu-id="af751-107">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="af751-108">Per altre informazioni, vedere [Sviluppo di un componente del flusso di dati personalizzato](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="af751-108">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af751-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="af751-109">Example</span></span>  
 <span data-ttu-id="af751-110">Nell'esempio illustrato viene utilizzato un componente script configurato come trasformazione per aggiungere una colonna di descrizione degli errori ai dati dell'output degli errori esistente nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="af751-110">The example shown here uses a Script component configured as a transformation to add an error description column to existing error output data in the data flow.</span></span>  
  
 <span data-ttu-id="af751-111">Per ulteriori informazioni su come configurare il componente script per l'utilizzo come trasformazione nel flusso di dati, vedere [creazione di una trasformazione sincrona con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)e [creazione di una trasformazione asincrona con il componente script](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="af751-111">For more information about how to configure the Script component for use as a transformation in the data flow, see [Creating a Synchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md)and [Creating an Asynchronous Transformation with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-an-asynchronous-transformation-with-the-script-component.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="af751-112">Per configurare l'esempio di componente script</span><span class="sxs-lookup"><span data-stu-id="af751-112">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="af751-113">Prima di creare il nuovo componente script, configurare un componente a monte nel flusso di dati per reindirizzare righe all'output degli errori quando si verifica un errore o un troncamento.</span><span class="sxs-lookup"><span data-stu-id="af751-113">Before creating the new Script component, configure an upstream component in the data flow to redirect rows to its error output when an error or truncation occurs.</span></span> <span data-ttu-id="af751-114">A scopo di test, è possibile configurare un componente in modo da assicurarsi che si verificheranno errori, ad esempio configurando una trasformazione Ricerca tra due tabelle in cui la ricerca avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="af751-114">For testing purposes, you may want to configure a component in a manner that ensures that errors will occur-for example, by configuring a Lookup transformation between two tables where the lookup will fail.</span></span>  
  
2.  <span data-ttu-id="af751-115">Aggiungere un nuovo componente script all'area di progettazione del flusso di dati e configurarlo come trasformazione.</span><span class="sxs-lookup"><span data-stu-id="af751-115">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span>  
  
3.  <span data-ttu-id="af751-116">Connettere l'output degli errori del componente a monte a questo nuovo componente script.</span><span class="sxs-lookup"><span data-stu-id="af751-116">Connect the error output from the upstream component to the new Script component.</span></span>  
  
4.  <span data-ttu-id="af751-117">Aprire **Editor trasformazione Script** e nella pagina **Script** selezionare il linguaggio di scripting per la proprietà **ScriptLanguage**.</span><span class="sxs-lookup"><span data-stu-id="af751-117">Open the **Script Transformation Editor**, and on the **Script** page, for the **ScriptLanguage** property, select the script language.</span></span>  
  
5.  <span data-ttu-id="af751-118">Fare clic su \*\*Modifica script[!INCLUDE[msCoName](../../includes/msconame-md.md)]  per aprire l'IDE di \*\*[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) e aggiungere il codice di esempio illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="af751-118">Click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE and add the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="af751-119">Chiudere VSTA.</span><span class="sxs-lookup"><span data-stu-id="af751-119">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="af751-120">Nella pagina **colonne di input** dell'Editor trasformazione script selezionare la colonna ErrorCode.</span><span class="sxs-lookup"><span data-stu-id="af751-120">In the Script Transformation Editor, on the **Input Columns** page, select the ErrorCode column.</span></span>  
  
8.  <span data-ttu-id="af751-121">Nella pagina **input e output** aggiungere una nuova colonna di output di tipo `String` denominata **ErrorDescription**.</span><span class="sxs-lookup"><span data-stu-id="af751-121">On the **Inputs and Outputs** page, add a new output column of type `String` named **ErrorDescription**.</span></span> <span data-ttu-id="af751-122">Aumentare la lunghezza predefinita della nuova colonna fino a 255 per supportare messaggi lunghi.</span><span class="sxs-lookup"><span data-stu-id="af751-122">Increase the default length of the new column to 255 to support long messages.</span></span>  
  
9. <span data-ttu-id="af751-123">Chiudere l'**Editor trasformazione Script.**</span><span class="sxs-lookup"><span data-stu-id="af751-123">Close the **Script Transformation Editor.**</span></span>  
  
10. <span data-ttu-id="af751-124">Connettere l'output del componente script a una destinazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="af751-124">Attach the output of the Script component to a suitable destination.</span></span> <span data-ttu-id="af751-125">Le destinazioni file flat sono le più facili da configurare per test ad hoc.</span><span class="sxs-lookup"><span data-stu-id="af751-125">A Flat File destination is the easiest to configure for ad hoc testing.</span></span>  
  
11. <span data-ttu-id="af751-126">Eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="af751-126">Run the package.</span></span>  
  
```vb  
Public Class ScriptMain  
    Inherits UserComponent  
    Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  Row.ErrorDescription = _  
    Me.ComponentMetaData.GetErrorDescription(Row.ErrorCode)  
  
    End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain:  
    UserComponent  
{  
    public override void Input0_ProcessInputRow(Input0Buffer Row)  
    {  
  
  Row.ErrorDescription = this.ComponentMetaData.GetErrorDescription(Row.ErrorCode);  
  
    }  
}  
  
```  
  
<span data-ttu-id="af751-127">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="af751-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="af751-128">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="af751-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="af751-129">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="af751-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="af751-130">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="af751-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af751-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af751-131">See Also</span></span>  
 <span data-ttu-id="af751-132">[Gestione degli errori nei dati](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="af751-132">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="af751-133">[Uso degli output degli errori in un componente flusso di dati](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="af751-133">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="af751-134">Creazione di una trasformazione sincrona con il componente script</span><span class="sxs-lookup"><span data-stu-id="af751-134">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
