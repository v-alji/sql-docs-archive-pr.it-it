---
title: Uso delle variabili nell'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], variables
- scripts [Integration Services], variables
- Variables property
- Variable object
- SSIS Script task, variables
- variables [Integration Services], Script task
ms.assetid: 593b5961-4bfa-4ce1-9531-a251c34e89d3
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2cd8fee5741c3d0e28e52c8712c3896428a05e8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727064"
---
# <a name="using-variables-in-the-script-task"></a><span data-ttu-id="c30d5-102">Utilizzo di variabili nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="c30d5-102">Using Variables in the Script Task</span></span>
  <span data-ttu-id="c30d5-103">Le variabili rendono possibile lo scambio di dati tra l'attività Script e altri oggetti del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c30d5-103">Variables make it possible for the Script task to exchange data with other objects in the package.</span></span> <span data-ttu-id="c30d5-104">Per altre informazioni, vedere [Variabili di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md).</span><span class="sxs-lookup"><span data-stu-id="c30d5-104">For more information, see [Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md).</span></span>  
  
 <span data-ttu-id="c30d5-105">L'attività Script utilizza la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> dell'oggetto `Dts` per leggere e scrivere negli oggetti <xref:Microsoft.SqlServer.Dts.Runtime.Variable> del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c30d5-105">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object to read from and write to <xref:Microsoft.SqlServer.Dts.Runtime.Variable> objects in the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c30d5-106">La proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> della classe <xref:Microsoft.SqlServer.Dts.Runtime.Variable> è di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="c30d5-106">The <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property of the <xref:Microsoft.SqlServer.Dts.Runtime.Variable> class is of type `Object`.</span></span> <span data-ttu-id="c30d5-107">Poiché l'oggetto `Option Strict` dell'attività Script è abilitato, è necessario eseguire il cast della proprietà <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> nel tipo appropriato prima che sia possibile utilizzarla.</span><span class="sxs-lookup"><span data-stu-id="c30d5-107">Because the Script task has `Option Strict` enabled, you must cast the <xref:Microsoft.SqlServer.Dts.Runtime.Variable.Value%2A> property to the appropriate type before you can use it.</span></span>  
  
 <span data-ttu-id="c30d5-108">Aggiungere variabili esistenti agli elenchi <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> e <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> in **Editor attività Script** per renderle disponibili per lo script personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c30d5-108">You add existing variables to the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadOnlyVariables%2A> and <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptTask.ReadWriteVariables%2A> lists in the **Script Task Editor** to make them available to the custom script.</span></span> <span data-ttu-id="c30d5-109">Tenere presente che per i nomi delle variabili viene applicata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="c30d5-109">Keep in mind that variable names are case-sensitive.</span></span> <span data-ttu-id="c30d5-110">All'interno dello script le variabili di entrambi i tipi sono accessibili tramite la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> dell'oggetto `Dts`.</span><span class="sxs-lookup"><span data-stu-id="c30d5-110">Within the script, you access variables of both types through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property of the `Dts` object.</span></span> <span data-ttu-id="c30d5-111">Utilizzare la proprietà `Value` per leggere e scrivere in singole variabili.</span><span class="sxs-lookup"><span data-stu-id="c30d5-111">Use the `Value` property to read from and write to individual variables.</span></span> <span data-ttu-id="c30d5-112">L'attività Script gestisce in modo trasparente il blocco mentre lo script legge e modifica i valori delle variabili.</span><span class="sxs-lookup"><span data-stu-id="c30d5-112">The Script task transparently manages locking as the script reads and modifies the values of variables.</span></span>  
  
 <span data-ttu-id="c30d5-113">È possibile utilizzare il metodo <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> della raccolta <xref:Microsoft.SqlServer.Dts.Runtime.Variables> restituita dalla proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> per verificare l'esistenza di una variabile prima di utilizzarla nel codice.</span><span class="sxs-lookup"><span data-stu-id="c30d5-113">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Variables.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Variables> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property to check for the existence of a variable before using it in your code.</span></span>  
  
 <span data-ttu-id="c30d5-114">È anche possibile usare la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> (Dts.VariableDispenser) per usare variabili nell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="c30d5-114">You can also use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property (Dts.VariableDispenser) to work with variables in the Script task.</span></span> <span data-ttu-id="c30d5-115">Quando si utilizza <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, è necessario gestire sia la semantica di blocco che il cast dei tipi di dati per i valori delle variabili nel codice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c30d5-115">When using the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A>, you must handle both the locking semantics and the casting of data types for variable values in your own code.</span></span> <span data-ttu-id="c30d5-116">Può essere necessario utilizzare la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> anziché la proprietà <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> se si desidera utilizzare una variabile non disponibile in fase di progettazione ma che viene creata a livello di programmazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c30d5-116">You may need to use the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.VariableDispenser%2A> property instead of the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Variables%2A> property if you want to work with a variable that is not available at design time but is created programmatically at run time.</span></span>  
  
## <a name="using-the-script-task-within-a-foreach-loop-container"></a><span data-ttu-id="c30d5-117">Utilizzo dell'attività Script in un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="c30d5-117">Using the Script Task within a Foreach Loop Container</span></span>  
 <span data-ttu-id="c30d5-118">Quando un'attività Script viene eseguita ripetutamente in un contenitore Ciclo Foreach, lo script deve in genere gestire il contenuto dell'elemento corrente nell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="c30d5-118">When a Script task runs repeatedly within a Foreach Loop container, the script usually needs to work with the contents of the current item in the enumerator.</span></span> <span data-ttu-id="c30d5-119">Ad esempio, se si utilizza l'enumeratore Foreach File, lo script deve riconoscere il nome di file corrente. Se si utilizza l'enumeratore Foreach ADO, lo script deve conoscere il contenuto delle colonne nella riga di dati corrente.</span><span class="sxs-lookup"><span data-stu-id="c30d5-119">For example, when using a Foreach File enumerator, the script needs to know the current file name; when using a Foreach ADO enumerator, the script needs to know the contents of the columns in the current row of data.</span></span>  
  
 <span data-ttu-id="c30d5-120">Le variabili rendono possibile questa comunicazione tra il contenitore Ciclo Foreach e l'attività Script.</span><span class="sxs-lookup"><span data-stu-id="c30d5-120">Variables make this communication between the Foreach Loop container and the Script task possible.</span></span> <span data-ttu-id="c30d5-121">Nella pagina **Mapping variabili** di **Editor ciclo Foreach** assegnare variabili a ogni elemento di dati restituito da un singolo elemento enumerato.</span><span class="sxs-lookup"><span data-stu-id="c30d5-121">On the **Variable Mappings** page of the **Foreach Loop Editor**, assign variables to each item of data that is returned by a single enumerated item.</span></span> <span data-ttu-id="c30d5-122">Ad esempio, un enumeratore Foreach File restituisce solo un nome di file in corrispondenza dell'indice 0 e pertanto richiede solo un mapping di variabili, mentre un enumeratore che restituisce diverse colonne di dati in ogni riga richiede che venga eseguito il mapping di una variabile diversa a ogni colonna che si desidera utilizzare nell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="c30d5-122">For example, a Foreach File enumerator returns only a file name at Index 0 and therefore requires only one variable mapping, whereas an enumerator that returns several columns of data in each row requires you to map a different variable to each column that you want to use in the Script task.</span></span>  
  
 <span data-ttu-id="c30d5-123">Dopo aver eseguito il mapping degli elementi enumerati alle variabili, è necessario aggiungere le variabili mappate alla `ReadOnlyVariables` proprietà nella pagina **script** dell' **Editor attività script** per renderle disponibili per lo script.</span><span class="sxs-lookup"><span data-stu-id="c30d5-123">After you have mapped enumerated items to variables, then you must add the mapped variables to the `ReadOnlyVariables` property on the **Script** page of the **Script Task Editor** to make them available to your script.</span></span> <span data-ttu-id="c30d5-124">Per un esempio di un'attività Script all'interno di un contenitore Ciclo Foreach che elabora i file di immagine in una cartella, vedere [Uso di immagini con l'attività Script](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span><span class="sxs-lookup"><span data-stu-id="c30d5-124">For an example of a Script task within a Foreach Loop container that processes the image files in a folder, see [Working with Images with the Script Task](../../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md).</span></span>  
  
## <a name="variables-example"></a><span data-ttu-id="c30d5-125">Esempio di variabili</span><span class="sxs-lookup"><span data-stu-id="c30d5-125">Variables Example</span></span>  
 <span data-ttu-id="c30d5-126">Nell'esempio seguente viene illustrato come accedere e utilizzare le variabili in un'attività Script per determinare il percorso del flusso di lavoro del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c30d5-126">The following example demonstrates how to access and use variables in a Script task to determine the path of package workflow.</span></span> <span data-ttu-id="c30d5-127">Nell'esempio si presuppone che siano state create variabili integer denominate e che siano state `CustomerCount` `MaxRecordCount` aggiunte alla `ReadOnlyVariables` raccolta in **Editor attività script**.</span><span class="sxs-lookup"><span data-stu-id="c30d5-127">The sample assumes that you have created integer variables named `CustomerCount` and `MaxRecordCount` and added them to the `ReadOnlyVariables` collection in the **Script Task Editor**.</span></span> <span data-ttu-id="c30d5-128">La variabile `CustomerCount` contiene il numero di record di clienti da importare.</span><span class="sxs-lookup"><span data-stu-id="c30d5-128">The `CustomerCount` variable contains the number of customer records to be imported.</span></span> <span data-ttu-id="c30d5-129">Se il valore è maggiore del valore `MaxRecordCount`, l'attività Script riporta un errore.</span><span class="sxs-lookup"><span data-stu-id="c30d5-129">If its value is greater than the value of `MaxRecordCount`, the Script task reports failure.</span></span> <span data-ttu-id="c30d5-130">Quando si verifica un errore perché la soglia `MaxRecordCount` è stata superata, il percorso di errore del flusso di lavoro può implementare l'eventuale pulizia richiesta.</span><span class="sxs-lookup"><span data-stu-id="c30d5-130">When a failure occurs because the `MaxRecordCount` threshold has been exceeded, the error path of the workflow can implement any required clean-up.</span></span>  
  
 <span data-ttu-id="c30d5-131">Per compilare correttamente l'esempio, è necessario aggiungere un riferimento all'assembly Microsoft.SqlServer.ScriptTask.</span><span class="sxs-lookup"><span data-stu-id="c30d5-131">To successfully compile the sample, you need to add a reference to the Microsoft.SqlServer.ScriptTask assembly.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim customerCount As Integer  
    Dim maxRecordCount As Integer  
  
    If Dts.Variables.Contains("CustomerCount") = True AndAlso _  
        Dts.Variables.Contains("MaxRecordCount") = True Then  
  
        customerCount = _  
            CType(Dts.Variables("CustomerCount").Value, Integer)  
        maxRecordCount = _  
            CType(Dts.Variables("MaxRecordCount").Value, Integer)  
  
    End If  
  
    If customerCount > maxRecordCount Then  
            Dts.TaskResult = ScriptResults.Failure  
    Else  
            Dts.TaskResult = ScriptResults.Success  
    End If  
  
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
        int customerCount;  
        int maxRecordCount;  
  
        if (Dts.Variables.Contains("CustomerCount")==true&&Dts.Variables.Contains("MaxRecordCount")==true)  
  
        {  
            customerCount = (int) Dts.Variables["CustomerCount"].Value;  
            maxRecordCount = (int) Dts.Variables["MaxRecordCount"].Value;  
  
        }  
  
        if (customerCount>maxRecordCount)  
        {  
            Dts.TaskResult = (int)ScriptResults.Failure;  
        }  
        else  
        {  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
  
    }  
  
}  
  
```  
  
<span data-ttu-id="c30d5-132">![Integration Services icona (piccola)](../../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="c30d5-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="c30d5-133">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="c30d5-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="c30d5-134">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="c30d5-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="c30d5-135">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="c30d5-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30d5-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c30d5-136">See Also</span></span>  
 <span data-ttu-id="c30d5-137">[Variabili di Integration Services &#40;SSIS&#41;](../../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="c30d5-137">[Integration Services &#40;SSIS&#41; Variables](../../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="c30d5-138">Usare variabili nei pacchetti</span><span class="sxs-lookup"><span data-stu-id="c30d5-138">Use Variables in Packages</span></span>](../../use-variables-in-packages.md)  
  
  
