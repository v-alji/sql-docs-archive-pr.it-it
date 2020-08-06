---
title: Uso di file di Excel con l'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Excel files
- Script task [Integration Services], examples
- Excel [Integration Services]
ms.assetid: b8fa110a-2c9c-4f5a-8fe1-305555640e44
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68a764452de548cd46e74d2a7f2f588a050a21c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628912"
---
# <a name="working-with-excel-files-with-the-script-task"></a><span data-ttu-id="b9f01-102">Uso di file di Excel con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="b9f01-102">Working with Excel Files with the Script Task</span></span>
  <span data-ttu-id="b9f01-103">In [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sono disponibili la gestione connessione, l'origine e la destinazione Excel per l'utilizzo di dati archiviati in fogli di calcolo nel formato di file di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="b9f01-103">[!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides the Excel connection manager, Excel source, and Excel destination for working with data stored in spreadsheets in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel file format.</span></span> <span data-ttu-id="b9f01-104">Per le tecniche descritte in questo argomento si utilizza l'attività Script per ottenere informazioni sui database (file di cartelle di lavoro) e sulle tabelle (fogli di lavoro e intervalli denominati) di Excel disponibili.</span><span class="sxs-lookup"><span data-stu-id="b9f01-104">The techniques described in this topic use the Script task to obtain information about available Excel databases (workbook files) and tables (worksheets and named ranges).</span></span> <span data-ttu-id="b9f01-105">Questi esempi possono essere facilmente modificati per utilizzare una delle altre origini dati basate su file supportate dal provider OLE DB di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet.</span><span class="sxs-lookup"><span data-stu-id="b9f01-105">These samples can easily be modified to work with any of the other file-based data sources supported by the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Jet OLE DB Provider.</span></span>  
  
 [<span data-ttu-id="b9f01-106">Configurazione di un pacchetto per testare gli esempi</span><span class="sxs-lookup"><span data-stu-id="b9f01-106">Configuring a Package to Test the Samples</span></span>](#configuring)  
  
 [<span data-ttu-id="b9f01-107">Esempio 1: verificare l'esistenza di un file di Excel</span><span class="sxs-lookup"><span data-stu-id="b9f01-107">Example1: Check Whether an Excel File Exists</span></span>](#example1)  
  
 [<span data-ttu-id="b9f01-108">Esempio 2: verificare l'esistenza di una tabella di Excel</span><span class="sxs-lookup"><span data-stu-id="b9f01-108">Example 2: Check Whether an Excel Table Exists</span></span>](#example2)  
  
 [<span data-ttu-id="b9f01-109">Esempio 3: ottenere un elenco dei file di Excel in una cartella</span><span class="sxs-lookup"><span data-stu-id="b9f01-109">Example 3: Get a List of Excel Files in a Folder</span></span>](#example3)  
  
 [<span data-ttu-id="b9f01-110">Esempio 4: ottenere un elenco di tabelle in un file di Excel</span><span class="sxs-lookup"><span data-stu-id="b9f01-110">Example 4: Get a List of Tables in an Excel File</span></span>](#example4)  
  
 [<span data-ttu-id="b9f01-111">Visualizzazione dei risultati degli esempi</span><span class="sxs-lookup"><span data-stu-id="b9f01-111">Displaying the Results of the Samples</span></span>](#testing)  
  
> [!NOTE]  
>  <span data-ttu-id="b9f01-112">Se si desidera creare un'attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questo esempio di attività Script come punto iniziale per un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b9f01-112">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="b9f01-113">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="b9f01-113">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
##  <a name="configuring-a-package-to-test-the-samples"></a><a name="configuring"></a> <span data-ttu-id="b9f01-114">Configurazione di un pacchetto per testare gli esempi</span><span class="sxs-lookup"><span data-stu-id="b9f01-114">Configuring a Package to Test the Samples</span></span>  
 <span data-ttu-id="b9f01-115">È possibile configurare un singolo pacchetto per testare tutti gli esempi riportati in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b9f01-115">You can configure a single package to test all the samples in this topic.</span></span> <span data-ttu-id="b9f01-116">Negli esempi vengono utilizzate molte variabili del pacchetto e classi di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9f01-116">The samples use many of the same package variables and the same [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes.</span></span>  
  
#### <a name="to-configure-a-package-for-use-with-the-examples-in-this-topic"></a><span data-ttu-id="b9f01-117">Per configurare un pacchetto per l'utilizzo con gli esempi di questo argomento</span><span class="sxs-lookup"><span data-stu-id="b9f01-117">To configure a package for use with the examples in this topic</span></span>  
  
1.  <span data-ttu-id="b9f01-118">Creare un nuovo progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e aprire il pacchetto predefinito per la modifica.</span><span class="sxs-lookup"><span data-stu-id="b9f01-118">Create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and open the default package for editing.</span></span>  
  
2.  <span data-ttu-id="b9f01-119">**Variabili**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-119">**Variables**.</span></span> <span data-ttu-id="b9f01-120">Aprire la finestra **Variabili** e definire le variabili seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-120">Open the **Variables** window and define the following variables:</span></span>  
  
    -   <span data-ttu-id="b9f01-121">`ExcelFile`, di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-121">`ExcelFile`, of type `String`.</span></span> <span data-ttu-id="b9f01-122">Immettere il percorso completo e il nome del file di una cartella di lavoro di Excel esistente.</span><span class="sxs-lookup"><span data-stu-id="b9f01-122">Enter the complete path and filename to an existing Excel workbook.</span></span>  
  
    -   <span data-ttu-id="b9f01-123">`ExcelTable`, di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-123">`ExcelTable`, of type `String`.</span></span> <span data-ttu-id="b9f01-124">Immettere il nome di un foglio di lavoro o di un intervallo denominato esistente nella cartella di lavoro specificata nel valore della variabile `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-124">Enter the name of an existing worksheet or named range in the workbook named in the value of the `ExcelFile` variable.</span></span> <span data-ttu-id="b9f01-125">Per questo valore viene applicata la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b9f01-125">This value is case-sensitive.</span></span>  
  
    -   <span data-ttu-id="b9f01-126">`ExcelFileExists`, di tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-126">`ExcelFileExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="b9f01-127">`ExcelTableExists`, di tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-127">`ExcelTableExists`, of type `Boolean`.</span></span>  
  
    -   <span data-ttu-id="b9f01-128">`ExcelFolder`, di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-128">`ExcelFolder`, of type `String`.</span></span> <span data-ttu-id="b9f01-129">Immettere il percorso completo di una cartella che contiene almeno una cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="b9f01-129">Enter the complete path of a folder that contains at least one Excel workbook.</span></span>  
  
    -   <span data-ttu-id="b9f01-130">`ExcelFiles`, di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-130">`ExcelFiles`, of type `Object`.</span></span>  
  
    -   <span data-ttu-id="b9f01-131">`ExcelTables`, di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-131">`ExcelTables`, of type `Object`.</span></span>  
  
3.  <span data-ttu-id="b9f01-132">**Istruzioni Imports**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-132">**Imports statements**.</span></span> <span data-ttu-id="b9f01-133">Per la maggior parte degli esempi di codice, è necessario importare uno o entrambi i seguenti spazi dei nomi di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] all'inizio del file script:</span><span class="sxs-lookup"><span data-stu-id="b9f01-133">Most of the code samples require you to import one or both of the following [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] namespaces at the top of your script file:</span></span>  
  
    -   <span data-ttu-id="b9f01-134">`System.IO`, per le operazioni del file system.</span><span class="sxs-lookup"><span data-stu-id="b9f01-134">`System.IO`, for file system operations.</span></span>  
  
    -   <span data-ttu-id="b9f01-135">`System.Data.OleDb`, per aprire i file di Excel come origini dati.</span><span class="sxs-lookup"><span data-stu-id="b9f01-135">`System.Data.OleDb`, to open Excel files as data sources.</span></span>  
  
4.  <span data-ttu-id="b9f01-136">**Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-136">**References**.</span></span> <span data-ttu-id="b9f01-137">Gli esempi di codice che leggono informazioni sullo schema da file di Excel richiedono un riferimento aggiuntivo allo spazio dei nomi `System.Xml` nel progetto di script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-137">The code samples that read schema information from Excel files require an additional reference in the script project to the `System.Xml` namespace.</span></span>  
  
5.  <span data-ttu-id="b9f01-138">Impostare il linguaggio di scripting predefinito per il componente Script usando l'opzione **Linguaggio di scripting** nella pagina **Generale** della finestra di dialogo **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-138">Set the default scripting language for the Script component by using the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="b9f01-139">Per ulteriori informazioni, vedere [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="b9f01-139">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>  
  
##  <a name="example-1-description-check-whether-an-excel-file-exists"></a><a name="example1"></a> <span data-ttu-id="b9f01-140">Descrizione dell'esempio 1: verificare l'esistenza di un file di Excel</span><span class="sxs-lookup"><span data-stu-id="b9f01-140">Example 1 Description: Check Whether an Excel File Exists</span></span>  
 <span data-ttu-id="b9f01-141">In questo esempio viene determinato se il file della cartella di lavoro di Excel specificato nella variabile `ExcelFile` esiste, quindi il valore booleano della variabile `ExcelFileExists` viene impostato sul risultato.</span><span class="sxs-lookup"><span data-stu-id="b9f01-141">This example determines whether the Excel workbook file specified in the `ExcelFile` variable exists, and then sets the Boolean value of the `ExcelFileExists` variable to the result.</span></span> <span data-ttu-id="b9f01-142">È possibile utilizzare questo valore booleano per la diramazione nel flusso di lavoro del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b9f01-142">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="b9f01-143">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="b9f01-143">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="b9f01-144">Aggiungere una nuova attività script al pacchetto e modificarne il nome in `ExcelFileExists` .</span><span class="sxs-lookup"><span data-stu-id="b9f01-144">Add a new Script task to the package and change its name to `ExcelFileExists`.</span></span>  
  
2.  <span data-ttu-id="b9f01-145">Nella scheda **Script** di **Editor attività Script** fare clic su **ReadOnlyVariables** e immettere il valore della proprietà usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-145">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b9f01-146">Digitare `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-146">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="b9f01-147">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-147">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-148">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e selezionare la variabile nella finestra di dialogo **Seleziona variabili** `ExcelFile` .</span><span class="sxs-lookup"><span data-stu-id="b9f01-148">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFile` variable.</span></span>  
  
3.  <span data-ttu-id="b9f01-149">Fare clic su **ReadWriteVariables** e immettere il valore della proprietà usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-149">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b9f01-150">Digitare `ExcelFileExists`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-150">Type `ExcelFileExists`.</span></span>  
  
         <span data-ttu-id="b9f01-151">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-151">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-152">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e selezionare la variabile nella finestra di dialogo **Seleziona variabili** `ExcelFileExists` .</span><span class="sxs-lookup"><span data-stu-id="b9f01-152">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelFileExists` variable.</span></span>  
  
4.  <span data-ttu-id="b9f01-153">Fare clic su **Modifica script** per aprire l'editor di script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-153">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="b9f01-154">Aggiungere un'istruzione `Imports` per lo spazio dei nomi `System.IO` all'inizio del file script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-154">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="b9f01-155">Aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b9f01-155">Add the following code.</span></span>  
  
### <a name="example-1-code"></a><span data-ttu-id="b9f01-156">Codice dell'esempio 1</span><span class="sxs-lookup"><span data-stu-id="b9f01-156">Example 1 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    If File.Exists(fileToTest) Then  
      Dts.Variables("ExcelFileExists").Value = True  
    Else  
      Dts.Variables("ExcelFileExists").Value = False  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    string fileToTest;  
  
    fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
    if (File.Exists(fileToTest))  
    {  
      Dts.Variables["ExcelFileExists"].Value = true;  
    }  
    else  
    {  
      Dts.Variables["ExcelFileExists"].Value = false;  
    }  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
##  <a name="example-2-description-check-whether-an-excel-table-exists"></a><a name="example2"></a> <span data-ttu-id="b9f01-157">Descrizione dell'esempio 2: verificare l'esistenza di una tabella di Excel</span><span class="sxs-lookup"><span data-stu-id="b9f01-157">Example 2 Description: Check Whether an Excel Table Exists</span></span>  
 <span data-ttu-id="b9f01-158">In questo esempio viene determinato se il foglio di lavoro o l'intervallo denominato di Excel specificato nella variabile `ExcelTable` esiste nel file della cartella di lavoro di Excel specificato nella variabile `ExcelFile`, quindi il valore booleano della variabile `ExcelTableExists` viene impostato sul risultato.</span><span class="sxs-lookup"><span data-stu-id="b9f01-158">This example determines whether the Excel worksheet or named range specified in the `ExcelTable` variable exists in the Excel workbook file specified in the `ExcelFile` variable, and then sets the Boolean value of the `ExcelTableExists` variable to the result.</span></span> <span data-ttu-id="b9f01-159">È possibile utilizzare questo valore booleano per la diramazione nel flusso di lavoro del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b9f01-159">You can use this Boolean value for branching in the workflow of the package.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="b9f01-160">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="b9f01-160">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="b9f01-161">Aggiungere una nuova attività script al pacchetto e modificarne il nome in `ExcelTableExists` .</span><span class="sxs-lookup"><span data-stu-id="b9f01-161">Add a new Script task to the package and change its name to `ExcelTableExists`.</span></span>  
  
2.  <span data-ttu-id="b9f01-162">Nella scheda **Script** di **Editor attività Script** fare clic su **ReadOnlyVariables** e immettere il valore della proprietà usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-162">In the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b9f01-163">Digitare `ExcelTable` e delimitato `ExcelFile` da virgole`.`</span><span class="sxs-lookup"><span data-stu-id="b9f01-163">Type `ExcelTable` and `ExcelFile` separated by commas`.`</span></span>  
  
         <span data-ttu-id="b9f01-164">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-164">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-165">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e nella finestra di dialogo **Seleziona variabili** Selezionare le `ExcelTable` `ExcelFile` variabili e.</span><span class="sxs-lookup"><span data-stu-id="b9f01-165">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTable` and `ExcelFile` variables.</span></span>  
  
3.  <span data-ttu-id="b9f01-166">Fare clic su **ReadWriteVariables** e immettere il valore della proprietà usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-166">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b9f01-167">Digitare `ExcelTableExists`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-167">Type `ExcelTableExists`.</span></span>  
  
         <span data-ttu-id="b9f01-168">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-168">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-169">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e selezionare la variabile nella finestra di dialogo **Seleziona variabili** `ExcelTableExists` .</span><span class="sxs-lookup"><span data-stu-id="b9f01-169">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the `ExcelTableExists` variable.</span></span>  
  
4.  <span data-ttu-id="b9f01-170">Fare clic su **Modifica script** per aprire l'editor di script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-170">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="b9f01-171">Aggiungere un riferimento all'assembly `System.Xml` nel progetto di script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-171">Add a reference to the `System.Xml` assembly in the script project.</span></span>  
  
6.  <span data-ttu-id="b9f01-172">Aggiungere le istruzioni `Imports` per gli spazi dei nomi `System.IO` e `System.Data.OleDb` all'inizio del file script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-172">Add `Imports` statements for the `System.IO` and `System.Data.OleDb` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="b9f01-173">Aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b9f01-173">Add the following code.</span></span>  
  
### <a name="example-2-code"></a><span data-ttu-id="b9f01-174">Codice dell'esempio 2</span><span class="sxs-lookup"><span data-stu-id="b9f01-174">Example 2 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim fileToTest As String  
    Dim tableToTest As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim excelTables As DataTable  
    Dim excelTable As DataRow  
    Dim currentTable As String  
  
    fileToTest = Dts.Variables("ExcelFile").Value.ToString  
    tableToTest = Dts.Variables("ExcelTable").Value.ToString  
  
    Dts.Variables("ExcelTableExists").Value = False  
    If File.Exists(fileToTest) Then  
      connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & fileToTest & _  
        ";Extended Properties=Excel 8.0"  
      excelConnection = New OleDbConnection(connectionString)  
      excelConnection.Open()  
      excelTables = excelConnection.GetSchema("Tables")  
      For Each excelTable In excelTables.Rows  
        currentTable = excelTable.Item("TABLE_NAME").ToString  
        If currentTable = tableToTest Then  
          Dts.Variables("ExcelTableExists").Value = True  
        End If  
      Next  
    End If  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
    public void Main()  
        {  
            string fileToTest;  
            string tableToTest;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable excelTables;  
            string currentTable;  
  
            fileToTest = Dts.Variables["ExcelFile"].Value.ToString();  
            tableToTest = Dts.Variables["ExcelTable"].Value.ToString();  
  
            Dts.Variables["ExcelTableExists"].Value = false;  
            if (File.Exists(fileToTest))  
            {  
                connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + fileToTest + ";Extended Properties=Excel 8.0";  
                excelConnection = new OleDbConnection(connectionString);  
                excelConnection.Open();  
                excelTables = excelConnection.GetSchema("Tables");  
                foreach (DataRow excelTable in excelTables.Rows)  
                {  
                    currentTable = excelTable["TABLE_NAME"].ToString();  
                    if (currentTable == tableToTest)  
                    {  
                        Dts.Variables["ExcelTableExists"].Value = true;  
                    }  
                }  
            }  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
}  
```  
  
##  <a name="example-3-description-get-a-list-of-excel-files-in-a-folder"></a><a name="example3"></a> <span data-ttu-id="b9f01-175">Descrizione dell'esempio 3: ottenere un elenco dei file di Excel in una cartella</span><span class="sxs-lookup"><span data-stu-id="b9f01-175">Example 3 Description: Get a List of Excel Files in a Folder</span></span>  
 <span data-ttu-id="b9f01-176">In questo esempio l'elenco dei file di Excel trovati nella cartella specificata nel valore della variabile `ExcelFolder` viene inserito in una matrice, che viene quindi copiata nella variabile `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-176">This example fills an array with the list of Excel files found in the folder specified in the value of the `ExcelFolder` variable, and then copies the array into the `ExcelFiles` variable.</span></span> <span data-ttu-id="b9f01-177">È possibile utilizzare l'enumeratore Foreach From Variable per scorrere i file nella matrice.</span><span class="sxs-lookup"><span data-stu-id="b9f01-177">You can use the Foreach from Variable enumerator to iterate over the files in the array.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="b9f01-178">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="b9f01-178">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="b9f01-179">Aggiungere una nuova attività Script al pacchetto e impostarne il nome su **GetExcelFiles**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-179">Add a new Script task to the package and change its name to **GetExcelFiles**.</span></span>  
  
2.  <span data-ttu-id="b9f01-180">Nella scheda **Script** di **Editor attività Script** fare clic su **ReadOnlyVariables** e immettere il valore della proprietà usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-180">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b9f01-181">Digitare `ExcelFolder`</span><span class="sxs-lookup"><span data-stu-id="b9f01-181">Type `ExcelFolder`</span></span>  
  
         <span data-ttu-id="b9f01-182">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-182">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-183">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e selezionare la variabile ExcelFolder nella finestra di dialogo **Seleziona variabili** .</span><span class="sxs-lookup"><span data-stu-id="b9f01-183">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFolder variable.</span></span>  
  
3.  <span data-ttu-id="b9f01-184">Fare clic su **ReadWriteVariables** e immettere il valore della proprietà usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-184">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b9f01-185">Digitare `ExcelFiles`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-185">Type `ExcelFiles`.</span></span>  
  
         <span data-ttu-id="b9f01-186">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-186">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-187">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e selezionare la variabile ExcelFiles nella finestra di dialogo **Seleziona variabili** .</span><span class="sxs-lookup"><span data-stu-id="b9f01-187">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFiles variable.</span></span>  
  
4.  <span data-ttu-id="b9f01-188">Fare clic su **Modifica script** per aprire l'editor di script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-188">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="b9f01-189">Aggiungere un'istruzione `Imports` per lo spazio dei nomi `System.IO` all'inizio del file script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-189">Add an `Imports` statement for the `System.IO` namespace at the top of the script file.</span></span>  
  
6.  <span data-ttu-id="b9f01-190">Aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b9f01-190">Add the following code.</span></span>  
  
### <a name="example-3-code"></a><span data-ttu-id="b9f01-191">Codice dell'esempio 3</span><span class="sxs-lookup"><span data-stu-id="b9f01-191">Example 3 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const FILE_PATTERN As String = "*.xls"  
  
    Dim excelFolder As String  
    Dim excelFiles As String()  
  
    excelFolder = Dts.Variables("ExcelFolder").Value.ToString  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN)  
  
    Dts.Variables("ExcelFiles").Value = excelFiles  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
  {  
    const string FILE_PATTERN = "*.xls";  
  
    string excelFolder;  
    string[] excelFiles;  
  
    excelFolder = Dts.Variables["ExcelFolder"].Value.ToString();  
    excelFiles = Directory.GetFiles(excelFolder, FILE_PATTERN);  
  
    Dts.Variables["ExcelFiles"].Value = excelFiles;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="b9f01-192">Soluzione alternativa</span><span class="sxs-lookup"><span data-stu-id="b9f01-192">Alternate Solution</span></span>  
 <span data-ttu-id="b9f01-193">Anziché utilizzare un'attività Script per raccogliere un elenco di file di Excel in una matrice, è anche possibile utilizzare l'enumeratore ForEach File per scorrere tutti i file di Excel presenti in una cartella.</span><span class="sxs-lookup"><span data-stu-id="b9f01-193">Instead of using a Script task to gather a list of Excel files into an array, you can also use the ForEach File enumerator to iterate over all the Excel files in a folder.</span></span> <span data-ttu-id="b9f01-194">Per altre informazioni, vedere [Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="b9f01-194">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="example-4-description-get-a-list-of-tables-in-an-excel-file"></a><a name="example4"></a> <span data-ttu-id="b9f01-195">Descrizione dell'esempio 4: ottenere un elenco di tabelle in un file di Excel</span><span class="sxs-lookup"><span data-stu-id="b9f01-195">Example 4 Description: Get a List of Tables in an Excel File</span></span>  
 <span data-ttu-id="b9f01-196">In questo esempio l'elenco dei fogli di lavoro e degli intervalli denominati trovati nel file della cartella di lavoro di Excel specificata dal valore della variabile `ExcelFile` viene inserito in una matrice, che viene quindi copiata nella variabile `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-196">This example fills an array with the list of worksheets and named ranges found in the Excel workbook file specified by the value of the `ExcelFile` variable, and then copies the array into the `ExcelTables` variable.</span></span> <span data-ttu-id="b9f01-197">È possibile utilizzare l'enumeratore Foreach From Variable per scorrere le tabelle nella matrice.</span><span class="sxs-lookup"><span data-stu-id="b9f01-197">You can use the Foreach from Variable Enumerator to iterate over the tables in the array.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b9f01-198">Nell'elenco di tabelle di una cartella di Excel sono inclusi sia i fogli di lavoro (con suffisso $) sia gli intervalli denominati.</span><span class="sxs-lookup"><span data-stu-id="b9f01-198">The list of tables in an Excel workbook includes both worksheets (which have the $ suffix) and named ranges.</span></span> <span data-ttu-id="b9f01-199">Se è necessario applicare un filtro all'elenco per individuare solo fogli di lavoro o solo intervalli denominati, può essere necessario scrivere codice aggiuntivo a tale scopo.</span><span class="sxs-lookup"><span data-stu-id="b9f01-199">If you have to filter the list for only worksheets or only named ranges, you may have to add additional code for this purpose.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="b9f01-200">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="b9f01-200">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="b9f01-201">Aggiungere una nuova attività Script al pacchetto e impostarne il nome su **GetExcelTables**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-201">Add a new Script task to the package and change its name to **GetExcelTables**.</span></span>  
  
2.  <span data-ttu-id="b9f01-202">Nella scheda **Script** di **Editor attività Script** fare clic su **ReadOnlyVariables** e immettere il valore della proprietà usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-202">Open the **Script Task Editor**, on the **Script** tab, click **ReadOnlyVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b9f01-203">Digitare `ExcelFile`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-203">Type `ExcelFile`.</span></span>  
  
         <span data-ttu-id="b9f01-204">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-204">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-205">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e selezionare la variabile ExcelFile nella finestra di dialogo **Seleziona variabili** .</span><span class="sxs-lookup"><span data-stu-id="b9f01-205">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelFile variable.</span></span>  
  
3.  <span data-ttu-id="b9f01-206">Fare clic su **ReadWriteVariables** e immettere il valore della proprietà usando uno dei metodi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b9f01-206">Click **ReadWriteVariables** and enter the property value using one of the following methods:</span></span>  
  
    -   <span data-ttu-id="b9f01-207">Digitare `ExcelTables`.</span><span class="sxs-lookup"><span data-stu-id="b9f01-207">Type `ExcelTables`.</span></span>  
  
         <span data-ttu-id="b9f01-208">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-208">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-209">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e selezionare ExcelTablesvariable nella finestra di dialogo **Seleziona variabili** .</span><span class="sxs-lookup"><span data-stu-id="b9f01-209">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, select the ExcelTablesvariable.</span></span>  
  
4.  <span data-ttu-id="b9f01-210">Fare clic su **Modifica script** per aprire l'editor di script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-210">Click **Edit Script** to open the script editor.</span></span>  
  
5.  <span data-ttu-id="b9f01-211">Aggiungere un riferimento allo spazio dei nomi `System.Xml` nel progetto di script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-211">Add a reference to the `System.Xml` namespace in the script project.</span></span>  
  
6.  <span data-ttu-id="b9f01-212">Aggiungere un'istruzione `Imports` per lo spazio dei nomi `System.Data.OleDb` all'inizio del file script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-212">Add an `Imports` statement for the `System.Data.OleDb` namespace at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="b9f01-213">Aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b9f01-213">Add the following code.</span></span>  
  
### <a name="example-4-code"></a><span data-ttu-id="b9f01-214">Codice dell'esempio 4</span><span class="sxs-lookup"><span data-stu-id="b9f01-214">Example 4 Code</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Dim excelFile As String  
    Dim connectionString As String  
    Dim excelConnection As OleDbConnection  
    Dim tablesInFile As DataTable  
    Dim tableCount As Integer = 0  
    Dim tableInFile As DataRow  
    Dim currentTable As String  
    Dim tableIndex As Integer = 0  
  
    Dim excelTables As String()  
  
    excelFile = Dts.Variables("ExcelFile").Value.ToString  
    connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" & _  
        "Data Source=" & excelFile & _  
        ";Extended Properties=Excel 8.0"  
    excelConnection = New OleDbConnection(connectionString)  
    excelConnection.Open()  
    tablesInFile = excelConnection.GetSchema("Tables")  
    tableCount = tablesInFile.Rows.Count  
    ReDim excelTables(tableCount - 1)  
    For Each tableInFile In tablesInFile.Rows  
      currentTable = tableInFile.Item("TABLE_NAME").ToString  
      excelTables(tableIndex) = currentTable  
      tableIndex += 1  
    Next  
  
    Dts.Variables("ExcelTables").Value = excelTables  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            string excelFile;  
            string connectionString;  
            OleDbConnection excelConnection;  
            DataTable tablesInFile;  
            int tableCount = 0;  
            string currentTable;  
            int tableIndex = 0;  
  
            string[] excelTables = new string[5];  
  
            excelFile = Dts.Variables["ExcelFile"].Value.ToString();  
            connectionString = "Provider=Microsoft.Jet.OLEDB.4.0;" +  
                "Data Source=" + excelFile + ";Extended Properties=Excel 8.0";  
            excelConnection = new OleDbConnection(connectionString);  
            excelConnection.Open();  
            tablesInFile = excelConnection.GetSchema("Tables");  
            tableCount = tablesInFile.Rows.Count;  
  
            foreach (DataRow tableInFile in tablesInFile.Rows)  
            {  
                currentTable = tableInFile["TABLE_NAME"].ToString();  
                excelTables[tableIndex] = currentTable;  
                tableIndex += 1;  
            }  
  
            Dts.Variables["ExcelTables"].Value = excelTables;  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
### <a name="alternate-solution"></a><span data-ttu-id="b9f01-215">Soluzione alternativa</span><span class="sxs-lookup"><span data-stu-id="b9f01-215">Alternate Solution</span></span>  
 <span data-ttu-id="b9f01-216">Anziché utilizzare un'attività Script per raccogliere un elenco delle tabelle di Excel in una matrice, è anche possibile utilizzare ForEach ADO.NET Schema Rowset Enumerator per scorrere tutte le tabelle, ovvero fogli di lavoro e intervalli denominati, nel file di una cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="b9f01-216">Instead of using a Script task to gather a list of Excel tables into an array, you can also use the ForEach ADO.NET Schema Rowset Enumerator to iterate over all the tables (that is, worksheets and named ranges) in an Excel workbook file.</span></span> <span data-ttu-id="b9f01-217">Per altre informazioni, vedere [Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="b9f01-217">For more information, see [Loop through Excel Files and Tables by Using a Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
##  <a name="displaying-the-results-of-the-samples"></a><a name="testing"></a><span data-ttu-id="b9f01-218">Visualizzazione dei risultati degli esempi</span><span class="sxs-lookup"><span data-stu-id="b9f01-218">Displaying the Results of the Samples</span></span>  
 <span data-ttu-id="b9f01-219">Se tutti gli esempi di questo argomento sono stati configurati nello stesso pacchetto, è possibile connettere tutte le attività Script a un'attività Script aggiuntiva che visualizza l'output di tutti gli esempi.</span><span class="sxs-lookup"><span data-stu-id="b9f01-219">If you have configured each of the examples in this topic in the same package, you can connect all the Script tasks to an additional Script task that displays the output of all the examples.</span></span>  
  
#### <a name="to-configure-a-script-task-to-display-the-output-of-the-examples-in-this-topic"></a><span data-ttu-id="b9f01-220">Per configurare un'attività Script per visualizzare l'output degli esempi di questo argomento</span><span class="sxs-lookup"><span data-stu-id="b9f01-220">To configure a Script task to display the output of the examples in this topic</span></span>  
  
1.  <span data-ttu-id="b9f01-221">Aggiungere una nuova attività Script al pacchetto e impostarne il nome su **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-221">Add a new Script task to the package and change its name to **DisplayResults**.</span></span>  
  
2.  <span data-ttu-id="b9f01-222">Connettere i quattro esempi di attività Script l'uno all'altro, in modo che ogni attività venga eseguita al completamento di quella precedente, quindi connettere il quarto esempio di attività all'attività **DisplayResults**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-222">Connect each of the four example Script tasks to one another, so that each task runs after the preceding task completes successfully, and connect the fourth example task to the **DisplayResults** task.</span></span>  
  
3.  <span data-ttu-id="b9f01-223">Aprire l'attività **DisplayResults** in **Editor attività Script**.</span><span class="sxs-lookup"><span data-stu-id="b9f01-223">Open the **DisplayResults** task in the **Script Task Editor**.</span></span>  
  
4.  <span data-ttu-id="b9f01-224">Nella scheda **Script** fare clic su **ReadOnlyVariables** e usare uno dei metodi seguenti per aggiungere tutte le sette variabili elencate in [Configurazione di un pacchetto per testare gli esempi](#configuring):</span><span class="sxs-lookup"><span data-stu-id="b9f01-224">On the **Script** tab, click **ReadOnlyVariables** and use one of the following methods to add all seven variables listed in [Configuring a Package to Test the Samples](#configuring):</span></span>  
  
    -   <span data-ttu-id="b9f01-225">Digitare i nomi di ogni variabile separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="b9f01-225">Type the name of each variable separated by commas.</span></span>  
  
         <span data-ttu-id="b9f01-226">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b9f01-226">-or-</span></span>  
  
    -   <span data-ttu-id="b9f01-227">Fare clic sul pulsante con i puntini di sospensione (**...**) accanto al campo della proprietà e nella finestra di dialogo **Seleziona variabili** Selezionare le variabili.</span><span class="sxs-lookup"><span data-stu-id="b9f01-227">Click the ellipsis (**...**) button next to the property field, and in the **Select variables** dialog box, selecting the variables.</span></span>  
  
5.  <span data-ttu-id="b9f01-228">Fare clic su **Modifica script** per aprire l'editor di script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-228">Click **Edit Script** to open the script editor.</span></span>  
  
6.  <span data-ttu-id="b9f01-229">Aggiungere le istruzioni `Imports` per gli spazi dei nomi `Microsoft.VisualBasic` e `System.Windows.Forms` all'inizio del file script.</span><span class="sxs-lookup"><span data-stu-id="b9f01-229">Add `Imports` statements for the `Microsoft.VisualBasic` and `System.Windows.Forms` namespaces at the top of the script file.</span></span>  
  
7.  <span data-ttu-id="b9f01-230">Aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b9f01-230">Add the following code.</span></span>  
  
8.  <span data-ttu-id="b9f01-231">Eseguire il pacchetto ed esaminare i risultati visualizzati in una finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="b9f01-231">Run the package and examine the results displayed in a message box.</span></span>  
  
### <a name="code-to-display-the-results"></a><span data-ttu-id="b9f01-232">Codice per visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="b9f01-232">Code to Display the Results</span></span>  
  
```vb  
Public Class ScriptMain  
  Public Sub Main()  
    Const EOL As String = ControlChars.CrLf  
  
    Dim results As String  
    Dim filesInFolder As String()  
    Dim fileInFolder As String  
    Dim tablesInFile As String()  
    Dim tableInFile As String  
  
    results = _  
      "Final values of variables:" & EOL & _  
      "ExcelFile: " & Dts.Variables("ExcelFile").Value.ToString & EOL & _  
      "ExcelFileExists: " & Dts.Variables("ExcelFileExists").Value.ToString & EOL & _  
      "ExcelTable: " & Dts.Variables("ExcelTable").Value.ToString & EOL & _  
      "ExcelTableExists: " & Dts.Variables("ExcelTableExists").Value.ToString & EOL & _  
      "ExcelFolder: " & Dts.Variables("ExcelFolder").Value.ToString & EOL & _  
      EOL  
  
    results &= "Excel files in folder: " & EOL  
    filesInFolder = DirectCast(Dts.Variables("ExcelFiles").Value, String())  
    For Each fileInFolder In filesInFolder  
      results &= " " & fileInFolder & EOL  
    Next  
    results &= EOL  
  
    results &= "Excel tables in file: " & EOL  
    tablesInFile = DirectCast(Dts.Variables("ExcelTables").Value, String())  
    For Each tableInFile In tablesInFile  
      results &= " " & tableInFile & EOL  
    Next  
  
    MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information)  
  
    Dts.TaskResult = ScriptResults.Success  
  End Sub  
End Class  
```  
  
```csharp  
public class ScriptMain  
{  
  public void Main()  
        {  
            const string EOL = "\r";  
  
            string results;  
            string[] filesInFolder;  
            //string fileInFolder;  
            string[] tablesInFile;  
            //string tableInFile;  
  
            results = "Final values of variables:" + EOL + "ExcelFile: " + Dts.Variables["ExcelFile"].Value.ToString() + EOL + "ExcelFileExists: " + Dts.Variables["ExcelFileExists"].Value.ToString() + EOL + "ExcelTable: " + Dts.Variables["ExcelTable"].Value.ToString() + EOL + "ExcelTableExists: " + Dts.Variables["ExcelTableExists"].Value.ToString() + EOL + "ExcelFolder: " + Dts.Variables["ExcelFolder"].Value.ToString() + EOL + EOL;  
  
            results += "Excel files in folder: " + EOL;  
            filesInFolder = (string[])(Dts.Variables["ExcelFiles"].Value);  
            foreach (string fileInFolder in filesInFolder)  
            {  
                results += " " + fileInFolder + EOL;  
            }  
            results += EOL;  
  
            results += "Excel tables in file: " + EOL;  
            tablesInFile = (string[])(Dts.Variables["ExcelTables"].Value);  
            foreach (string tableInFile in tablesInFile)  
            {  
                results += " " + tableInFile + EOL;  
            }  
  
            MessageBox.Show(results, "Results", MessageBoxButtons.OK, MessageBoxIcon.Information);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
        }  
}  
```  
  
<span data-ttu-id="b9f01-233">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b9f01-233">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b9f01-234">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="b9f01-234">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b9f01-235">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="b9f01-235">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b9f01-236">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="b9f01-236">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f01-237">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9f01-237">See Also</span></span>  
 <span data-ttu-id="b9f01-238">[Gestione connessione Excel](../connection-manager/excel-connection-manager.md) </span><span class="sxs-lookup"><span data-stu-id="b9f01-238">[Excel Connection Manager](../connection-manager/excel-connection-manager.md) </span></span>  
 [<span data-ttu-id="b9f01-239">Esecuzione di un ciclo su file e tabelle di Excel usando un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="b9f01-239">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
  
