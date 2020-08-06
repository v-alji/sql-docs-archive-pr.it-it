---
title: Rilevamento di un file flat vuoto con l'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- flat files
- Script task [Integration Services], empty flat files
- SSIS Script task, empty flat files
- Script task [Integration Services], examples
ms.assetid: 1b4defb8-886a-483d-8056-d1b91d37bc90
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 379b11bd18752ad648fc5f24d11d9ed5bfb63e14
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629478"
---
# <a name="detecting-an-empty-flat-file-with-the-script-task"></a><span data-ttu-id="d2266-102">Rilevamento di un file flat vuoto con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="d2266-102">Detecting an Empty Flat File with the Script Task</span></span>
  <span data-ttu-id="d2266-103">L'origine file flat non determina se un file flat contiene righe di dati prima di tentare di elaborarlo.</span><span class="sxs-lookup"><span data-stu-id="d2266-103">The Flat File source does not determine whether a flat file contains rows of data before attempting to process it.</span></span> <span data-ttu-id="d2266-104">È possibile migliorare l'efficienza di un pacchetto, specialmente di un pacchetto che scorre numerosi file flat, ignorando i file che non contengono alcuna riga di dati.</span><span class="sxs-lookup"><span data-stu-id="d2266-104">You may want to improve the efficiency of a package, especially of a package that iterates over numerous flat files, by skipping files that do not contain any rows of data.</span></span> <span data-ttu-id="d2266-105">L'attività Script consente di cercare un file flat vuoto prima che il pacchetto inizi a elaborare il flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="d2266-105">The Script task can look for an empty flat file before the package begins to process the data flow.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2266-106">Se si desidera creare un'attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questo esempio di attività Script come punto iniziale per un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="d2266-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="d2266-107">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="d2266-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="d2266-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2266-108">Description</span></span>  
 <span data-ttu-id="d2266-109">Nell'esempio seguente sono utilizzati i metodi dello spazio dei nomi `System.IO` per testare il file flat specificato in una gestione connessione file flat per determinare se il file è vuoto o se contiene solo le righe non di dati previste, ad esempio intestazioni di colonna o una riga vuota.</span><span class="sxs-lookup"><span data-stu-id="d2266-109">The following example uses methods from the `System.IO` namespace to test the flat file specified in a Flat File connection manager to determine whether the file is empty, or whether it contains only expected non-data rows such as column headers or an empty line.</span></span> <span data-ttu-id="d2266-110">Lo script prima controlla la dimensione del file. Se la dimensione è pari a zero byte, significa che il file è vuoto.</span><span class="sxs-lookup"><span data-stu-id="d2266-110">The script checks the size of the file first; if the size is zero bytes, the file is empty.</span></span> <span data-ttu-id="d2266-111">Se la dimensione del file è superiore a zero, lo script legge le righe dal file finché non sussistono più righe o finché il numero di righe supera il numero previsto di righe non di dati.</span><span class="sxs-lookup"><span data-stu-id="d2266-111">If the file size is greater than zero, the script reads lines from the file until there are no more lines, or until the number of lines exceeds the expected number of non-data rows.</span></span> <span data-ttu-id="d2266-112">Se il numero di righe nel file è minore o uguale al numero previsto di righe non di dati, il file è considerato vuoto.</span><span class="sxs-lookup"><span data-stu-id="d2266-112">If the number of lines in the file is less than or equal to the expected number of non-data rows, then the file is considered empty.</span></span> <span data-ttu-id="d2266-113">Il risultato viene restituito come valore booleano in una variabile dell'utente, il cui valore può essere utilizzato per la diramazione nel flusso di controllo del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d2266-113">The result is returned as a Boolean value in a user variable, the value of which can be used for branching in the package's control flow.</span></span> <span data-ttu-id="d2266-114">Il `FireInformation` Metodo Visualizza anche il risultato nella finestra **output** di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="d2266-114">The `FireInformation` method also displays the result in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="d2266-115">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="d2266-115">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="d2266-116">Creare e configurare una gestione connessione file flat denominata `EmptyFlatFileTest` .</span><span class="sxs-lookup"><span data-stu-id="d2266-116">Create and configure a flat file connection manager named `EmptyFlatFileTest`.</span></span>  
  
2.  <span data-ttu-id="d2266-117">Creare una variabile di tipo integer denominata `FFNonDataRows` e impostarne il valore sul numero di righe non di dati previsto nel file flat.</span><span class="sxs-lookup"><span data-stu-id="d2266-117">Create an integer variable named `FFNonDataRows` and set its value to the number of non-data rows expected in the flat file.</span></span>  
  
3.  <span data-ttu-id="d2266-118">Creare una variabile booleana denominata `FFIsEmpty`.</span><span class="sxs-lookup"><span data-stu-id="d2266-118">Create a Boolean variable named `FFIsEmpty`.</span></span>  
  
4.  <span data-ttu-id="d2266-119">Aggiungere la variabile `FFNonDataRows` alla proprietà **ReadOnlyVariables** dell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="d2266-119">Add the `FFNonDataRows` variable to the Script task's **ReadOnlyVariables** property.</span></span>  
  
5.  <span data-ttu-id="d2266-120">Aggiungere la variabile `FFIsEmpty` alla proprietà **ReadWriteVariables** dell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="d2266-120">Add the `FFIsEmpty` variable to the Script task's **ReadWriteVariables** property.</span></span>  
  
6.  <span data-ttu-id="d2266-121">Nel codice importare lo spazio dei nomi `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="d2266-121">In your code, import the `System.IO` namespace.</span></span>  
  
 <span data-ttu-id="d2266-122">Se si scorrono i file con un enumeratore Foreach File, anziché utilizzare una sola gestione connessione file flat, sarà necessario modificare il codice di esempio seguente per ottenere il nome e il percorso del file dalla variabile nella quale il valore enumerato è archiviato anziché dalla gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="d2266-122">If you are iterating over files with a Foreach File enumerator, instead of using a single Flat File connection manager, you will need to modify the sample code below to obtain the file name and path from the variable in which the enumerated value is stored instead of from the connection manager.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d2266-123">Codice</span><span class="sxs-lookup"><span data-stu-id="d2266-123">Code</span></span>  
  
```vb  
Public Sub Main()  
  
  Dim nonDataRows As Integer = _  
      DirectCast(Dts.Variables("FFNonDataRows").Value, Integer)  
  Dim ffConnection As String = _  
      DirectCast(Dts.Connections("EmptyFlatFileTest").AcquireConnection(Nothing), _  
      String)  
  Dim flatFileInfo As New FileInfo(ffConnection)  
  ' If file size is 0 bytes, flat file does not contain data.  
  Dim fileSize As Long = flatFileInfo.Length  
  If fileSize > 0 Then  
    Dim lineCount As Integer = 0  
    Dim line As String  
    Dim fsFlatFile As New StreamReader(ffConnection)  
    Do Until fsFlatFile.EndOfStream  
      line = fsFlatFile.ReadLine  
      lineCount += 1  
      ' If line count > expected number of non-data rows,  
      '  flat file contains data (default value).  
      If lineCount > nonDataRows Then  
        Exit Do  
      End If  
      ' If line count <= expected number of non-data rows,  
      '  flat file does not contain data.  
      If lineCount <= nonDataRows Then  
        Dts.Variables("FFIsEmpty").Value = True  
      End If  
    Loop  
  Else  
    Dts.Variables("FFIsEmpty").Value = True  
  End If  
  
  Dim fireAgain As Boolean = False  
  Dts.Events.FireInformation(0, "Script Task", _  
      String.Format("{0}: {1}", ffConnection, _  
      Dts.Variables("FFIsEmpty").Value.ToString), _  
      String.Empty, 0, fireAgain)  
  
  Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
public void Main()  
        {  
  
            int nonDataRows = (int)(Dts.Variables["FFNonDataRows"].Value);  
            string ffConnection = (string)(Dts.Connections["EmptyFlatFileTest"].AcquireConnection(null) as String);  
            FileInfo flatFileInfo = new FileInfo(ffConnection);  
            // If file size is 0 bytes, flat file does not contain data.  
            long fileSize = flatFileInfo.Length;  
            if (fileSize > 0)  
            {  
  
                int lineCount = 0;  
                string line;  
                StreamReader fsFlatFile = new StreamReader(ffConnection);  
                while (!(fsFlatFile.EndOfStream))  
                {  
                    Console.WriteLine (fsFlatFile.ReadLine());  
                    lineCount += 1;  
                    // If line count > expected number of non-data rows,  
                    //  flat file contains data (default value).  
                    if (lineCount > nonDataRows)  
                    {  
                        break;  
                    }  
                    // If line count <= expected number of non-data rows,  
                    //  flat file does not contain data.  
                    if (lineCount <= nonDataRows)  
                    {  
                        Dts.Variables["FFIsEmpty"].Value = true;  
                    }  
                }  
            }  
            else  
            {  
                Dts.Variables["FFIsEmpty"].Value = true;  
            }  
  
            bool fireAgain = false;  
            Dts.Events.FireInformation(0, "Script Task", String.Format("{0}: {1}", ffConnection, Dts.Variables["FFIsEmpty"].Value), String.Empty, 0, ref fireAgain);  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
```  
  
<span data-ttu-id="d2266-124">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="d2266-124">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="d2266-125">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="d2266-125">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="d2266-126">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="d2266-126">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="d2266-127">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="d2266-127">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2266-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2266-128">See Also</span></span>  
 [<span data-ttu-id="d2266-129">Esempi di attività Script</span><span class="sxs-lookup"><span data-stu-id="d2266-129">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)  
  
  
