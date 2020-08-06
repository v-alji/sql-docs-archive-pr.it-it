---
title: Simulazione di un output degli errori per il componente script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], error output
- error outputs [Integration Services], Script component
ms.assetid: f8b6ecff-ac99-4231-a0e7-7ce4ad76bad0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bed458ce378eb26cd863811b4974b5f39429e1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713315"
---
# <a name="simulating-an-error-output-for-the-script-component"></a><span data-ttu-id="cfdea-102">Simulazione di un output degli errori per il componente script</span><span class="sxs-lookup"><span data-stu-id="cfdea-102">Simulating an Error Output for the Script Component</span></span>
  <span data-ttu-id="cfdea-103">Anche se non è possibile configurare direttamente un output come output degli errori nel componente script per la gestione automatica delle righe di errori, è possibile riprodurre la funzionalità di un output degli errori incorporato creando un output aggiuntivo e utilizzando la logica condizionale nello script per indirizzare le righe a questo output quando è appropriato.</span><span class="sxs-lookup"><span data-stu-id="cfdea-103">Although you cannot directly configure an output as an error output in the Script component for automatic handling of error rows, you can reproduce the functionality of a built-in error output by creating an additional output and using conditional logic in your script to direct rows to this output when appropriate.</span></span> <span data-ttu-id="cfdea-104">È necessario imitare il comportamento di un output degli errori incorporato aggiungendo due colonne di output aggiuntive per ricevere il numero di errore e l'ID della colonna nella quale si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="cfdea-104">You may want to imitate the behavior of a built-in error output by adding two additional output columns to receive the error number and the ID of the column in which an error occurred.</span></span>  
  
 <span data-ttu-id="cfdea-105">Se si desidera aggiungere la descrizione dell'errore che corrisponde a un codice di errore [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] predefinito specifico, è possibile utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> dell'interfaccia <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponibile tramite la proprietà <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> del componente script.</span><span class="sxs-lookup"><span data-stu-id="cfdea-105">If you want to add the error description that corresponds to a specific predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the Script component's <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ComponentMetaData%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfdea-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="cfdea-106">Example</span></span>  
 <span data-ttu-id="cfdea-107">Nell'esempio illustrato di seguito viene utilizzato un componente script configurato come trasformazione che dispone di due output sincroni.</span><span class="sxs-lookup"><span data-stu-id="cfdea-107">The example shown here uses a Script component configured as a transformation that has two synchronous outputs.</span></span> <span data-ttu-id="cfdea-108">Lo scopo del componente script è di filtrare le righe di errore dai dati relativi agli indirizzi nel database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cfdea-108">The purpose of the Script component is to filter error rows from address data in the AdventureWorks sample database.</span></span> <span data-ttu-id="cfdea-109">Questo esempio fittizio presuppone che si stia preparando una promozione per i clienti dell'America del nord e che sia necessario filtrare gli indirizzi non relativi all'America del nord.</span><span class="sxs-lookup"><span data-stu-id="cfdea-109">This fictitious example assumes that we are preparing a promotion for North American customers and need to filter out addresses that are not located in North America.</span></span>  
  
#### <a name="to-configure-the-example"></a><span data-ttu-id="cfdea-110">Per configurare l'esempio</span><span class="sxs-lookup"><span data-stu-id="cfdea-110">To configure the example</span></span>  
  
1.  <span data-ttu-id="cfdea-111">Prima di creare il nuovo componente script, creare una gestione connessione e configurare un'origine del flusso di dati che seleziona i dati relativi agli indirizzi dal database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="cfdea-111">Before creating the new Script component, create a connection manager and configure a data flow source that selects address data from the AdventureWorks sample database.</span></span> <span data-ttu-id="cfdea-112">Per questo esempio, in cui viene analizzata solo la colonna CountryRegionName, è possibile utilizzare semplicemente la vista Person.vStateCountryProvinceRegion oppure selezionare i dati unendo in join le tabelle Person.Address, Person.StateProvince e Person.CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="cfdea-112">For this example, which only looks at the CountryRegionName column, you can simply use the Person.vStateCountryProvinceRegion view, or you can select data by joining the Person.Address, Person.StateProvince, and Person.CountryRegion tables.</span></span>  
  
2.  <span data-ttu-id="cfdea-113">Aggiungere un nuovo componente script all'area di progettazione del flusso di dati e configurarlo come trasformazione.</span><span class="sxs-lookup"><span data-stu-id="cfdea-113">Add a new Script component to the Data Flow designer surface and configure it as a transformation.</span></span> <span data-ttu-id="cfdea-114">Aprire l'**Editor trasformazione Script**.</span><span class="sxs-lookup"><span data-stu-id="cfdea-114">Open the **Script Transformation Editor**.</span></span>  
  
3.  <span data-ttu-id="cfdea-115">Nella pagina **Script** impostare la proprietà **ScriptLanguage** sul linguaggio di scripting che si vuole usare per codificare lo script.</span><span class="sxs-lookup"><span data-stu-id="cfdea-115">On the **Script** page, set the **ScriptLanguage** property to the script language that you want to use to code the script.</span></span>  
  
4.  <span data-ttu-id="cfdea-116">Fare clic su **Modifica script** per aprire [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="cfdea-116">Click **Edit Script** to open [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
5.  <span data-ttu-id="cfdea-117">Nel metodo `Input0_ProcessInputRow` digitare o incollare il codice di esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cfdea-117">In the `Input0_ProcessInputRow` method, type or paste the sample code shown below.</span></span>  
  
6.  <span data-ttu-id="cfdea-118">Chiudere VSTA.</span><span class="sxs-lookup"><span data-stu-id="cfdea-118">Close VSTA.</span></span>  
  
7.  <span data-ttu-id="cfdea-119">Nella pagina **Colonne di input** selezionare le colonne che si vogliono elaborare nella trasformazione Script.</span><span class="sxs-lookup"><span data-stu-id="cfdea-119">On the **Input Columns** page, select the columns that you want to process in the Script transformation.</span></span> <span data-ttu-id="cfdea-120">In questo esempio viene utilizzata solo la colonna CountryRegionName.</span><span class="sxs-lookup"><span data-stu-id="cfdea-120">This example uses only the CountryRegionName column.</span></span> <span data-ttu-id="cfdea-121">Le colonne di input disponibili lasciate deselezionate verranno semplicemente passate nel flusso di dati senza alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="cfdea-121">Available input columns that you leave unselected will simply be passed through unchanged in the data flow.</span></span>  
  
8.  <span data-ttu-id="cfdea-122">Nella pagina **input e output** aggiungere un nuovo, un secondo output e impostarne il `SynchronousInputID` valore sull'ID dell'input, che corrisponde anche al valore della `SynchronousInputID` proprietà dell'output predefinito.</span><span class="sxs-lookup"><span data-stu-id="cfdea-122">On the **Inputs and Outputs** page, add a new, second output, and set its `SynchronousInputID` value to the ID of the input, which is also the value of the `SynchronousInputID` property of the default output.</span></span> <span data-ttu-id="cfdea-123">Impostare la proprietà `ExclusionGroup` di entrambi gli output sullo stesso valore diverso da zero (ad esempio, 1) per indicare che ogni riga verrà diretta a uno solo dei due output.</span><span class="sxs-lookup"><span data-stu-id="cfdea-123">Set the `ExclusionGroup` property of both outputs to the same non-zero value (for example, 1) to indicate that each row will be directed to only one of the two outputs.</span></span> <span data-ttu-id="cfdea-124">Assegnare al nuovo output degli errori un nome distintivo, ad esempio "MyErrorOutput".</span><span class="sxs-lookup"><span data-stu-id="cfdea-124">Give the new error output a distinctive name, such as "MyErrorOutput."</span></span>  
  
9. <span data-ttu-id="cfdea-125">Aggiungere altre colonne di output al nuovo output degli errori per acquisire le informazioni desiderate sull'errore, tra cui il codice di errore, l'ID della colonna nella quale si è verificato l'errore ed eventualmente la descrizione dell'errore.</span><span class="sxs-lookup"><span data-stu-id="cfdea-125">Add additional output columns to the new error output to capture the desired error information, which may include the error code, the ID of the column in which the error occurred, and possibly the error description.</span></span> <span data-ttu-id="cfdea-126">In questo esempio vengono create le nuove colonne, ErrorColumn ed ErrorMessage.</span><span class="sxs-lookup"><span data-stu-id="cfdea-126">This example creates the new columns, ErrorColumn and ErrorMessage.</span></span> <span data-ttu-id="cfdea-127">Se si acquisiscono errori di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] predefiniti nell'implementazione, assicurarsi di aggiungere una colonna ErrorCode per il numero di errore.</span><span class="sxs-lookup"><span data-stu-id="cfdea-127">If you are catching predefined [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] errors in your own implementation, make sure to add an ErrorCode column for the error number.</span></span>  
  
10. <span data-ttu-id="cfdea-128">Prendere nota del valore di ID di una o più colonne di input in cui il componente script verificherà le condizioni di errore.</span><span class="sxs-lookup"><span data-stu-id="cfdea-128">Note the ID value of the input column or columns that the Script component will check for error conditions.</span></span> <span data-ttu-id="cfdea-129">In questo esempio viene utilizzato questo identificatore di colonna per popolare il valore ErrorColumn.</span><span class="sxs-lookup"><span data-stu-id="cfdea-129">This example uses this column identifier to populate the ErrorColumn value.</span></span>  
  
11. <span data-ttu-id="cfdea-130">Chiudere l'**Editor trasformazione Script.**</span><span class="sxs-lookup"><span data-stu-id="cfdea-130">Close the **Script Transformation Editor.**</span></span>  
  
12. <span data-ttu-id="cfdea-131">Allegare gli output del componente script alle destinazioni adatte.</span><span class="sxs-lookup"><span data-stu-id="cfdea-131">Attach the outputs of the Script component to suitable destinations.</span></span> <span data-ttu-id="cfdea-132">Le destinazioni file flat sono le più semplici da configurare per test ad hoc.</span><span class="sxs-lookup"><span data-stu-id="cfdea-132">Flat file destinations are the easiest to configure for ad hoc testing.</span></span>  
  
13. <span data-ttu-id="cfdea-133">Eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cfdea-133">Run the package.</span></span>  
  
```vb  
Public Overrides Sub Input0_ProcessInputRow(ByVal Row As Input0Buffer)  
  
  If Row.CountryRegionName <> "Canada" _  
      And Row.CountryRegionName <> "United States" Then  
  
    Row.ErrorColumn = 68 ' ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America."  
    Row.DirectRowToMyErrorOutput()  
  
  Else  
  
    Row.DirectRowToOutput0()  
  
  End If  
  
End Sub  
```  
  
```csharp  
public override void Input0_ProcessInputRow(Input0Buffer Row)  
{  
  
  if (Row.CountryRegionName!="Canada"&&Row.CountryRegionName!="United States")  
  
  {  
    Row.ErrorColumn = 68; // ID of CountryRegionName column  
    Row.ErrorMessage = "Address is not in North America.";  
    Row.DirectRowToMyErrorOutput();  
  
  }  
  else  
  {  
  
    Row.DirectRowToOutput0();  
  
  }  
  
}  
```  
  
<span data-ttu-id="cfdea-134">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cfdea-134">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cfdea-135">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="cfdea-135">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cfdea-136">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="cfdea-136">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cfdea-137">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="cfdea-137">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfdea-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfdea-138">See Also</span></span>  
 <span data-ttu-id="cfdea-139">[Gestione degli errori nei dati](../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="cfdea-139">[Error Handling in Data](../data-flow/error-handling-in-data.md) </span></span>  
 <span data-ttu-id="cfdea-140">[Uso degli output degli errori in un componente flusso di dati](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="cfdea-140">[Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="cfdea-141">Creazione di una trasformazione sincrona con il componente script</span><span class="sxs-lookup"><span data-stu-id="cfdea-141">Creating a Synchronous Transformation with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-synchronous-transformation-with-the-script-component.md) 
  
  
