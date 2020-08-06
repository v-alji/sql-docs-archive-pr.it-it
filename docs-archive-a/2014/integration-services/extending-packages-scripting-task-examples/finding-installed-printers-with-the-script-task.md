---
title: Ricerca di stampanti installate con l'attività Script| Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- System.Drawing.Printing namespace
- printers [Integration Services]
- SSIS Script task, printers
- locating printers
- Printing namespace
- Script task [Integration Services], examples
- finding printers [SQL Server]
- Script task [Integration Services], printers
ms.assetid: 50a55014-e2c3-4ecd-84e1-3e877c55a260
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc4bc06879a55d4d07afca1011cc479dd7e7903a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721635"
---
# <a name="finding-installed-printers-with-the-script-task"></a><span data-ttu-id="75f3e-102">Ricerca di stampanti installate con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="75f3e-102">Finding Installed Printers with the Script Task</span></span>
  <span data-ttu-id="75f3e-103">La destinazione finale dei dati trasformati dai pacchetti [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è spesso costituita da un report stampato.</span><span class="sxs-lookup"><span data-stu-id="75f3e-103">The data that is transformed by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages often has a printed report as its final destination.</span></span> <span data-ttu-id="75f3e-104">Lo `System.Drawing.Printing` spazio dei nomi in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] fornisce le classi per l'utilizzo delle stampanti.</span><span class="sxs-lookup"><span data-stu-id="75f3e-104">The `System.Drawing.Printing` namespace in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides classes for working with printers.</span></span>

> [!NOTE]
>  <span data-ttu-id="75f3e-105">Se si desidera creare un'attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questo esempio di attività Script come punto iniziale per un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="75f3e-105">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="75f3e-106">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="75f3e-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>

## <a name="description"></a><span data-ttu-id="75f3e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="75f3e-107">Description</span></span>
 <span data-ttu-id="75f3e-108">Nell'esempio seguente vengono individuate le stampanti installate nel server che supportano carta in formato Legal (utilizzato negli Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="75f3e-108">The following example locates printers installed on the server that support legal size paper (as used in the United States).</span></span> <span data-ttu-id="75f3e-109">Il codice per controllare i formati della carta supportati è incapsulato in una funzione privata.</span><span class="sxs-lookup"><span data-stu-id="75f3e-109">The code to check supported paper sizes is encapsulated in a private function.</span></span> <span data-ttu-id="75f3e-110">Per consentire di tenere traccia del proprio stato mentre controlla le impostazioni per ogni stampante, lo script utilizza il metodo <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> per generare un messaggio informativo per le stampanti con formato della carta Legal e un avviso per le stampanti senza questo formato.</span><span class="sxs-lookup"><span data-stu-id="75f3e-110">To enable you to track the progress of the script as it checks the settings for each printer, the script uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Log%2A> method to raise an informational message for printers with legal size paper, and to raise a warning for printers without legal size paper.</span></span> <span data-ttu-id="75f3e-111">Questi messaggi vengono visualizzati nella finestra **Output** dell'IDE di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) quando si esegue il pacchetto nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="75f3e-111">These messages appear in the **Output** window of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE when you run the package in the designer.</span></span>

#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="75f3e-112">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="75f3e-112">To configure this Script Task example</span></span>

1.  <span data-ttu-id="75f3e-113">Creare la variabile denominata `PrinterList` con tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="75f3e-113">Create the variable named `PrinterList` with type `Object`.</span></span>

2.  <span data-ttu-id="75f3e-114">Nella pagina **Script** dell'**Editor attività Script** questa variabile alla proprietà ReadWriteVariables.</span><span class="sxs-lookup"><span data-stu-id="75f3e-114">On the **Script** page of the **Script Task Editor**, add this variable to the ReadWriteVariables property.</span></span>

3.  <span data-ttu-id="75f3e-115">Nel progetto di script aggiungere un riferimento allo spazio dei nomi **System.Drawing**.</span><span class="sxs-lookup"><span data-stu-id="75f3e-115">In the script project, add a reference to the **System.Drawing** namespace.</span></span>

4.  <span data-ttu-id="75f3e-116">Nel codice usare le `Imports` istruzioni per importare gli spazi dei nomi **System. Collections** e `System.Drawing.Printing` .</span><span class="sxs-lookup"><span data-stu-id="75f3e-116">In your code, use `Imports` statements to import the **System.Collections** and the `System.Drawing.Printing` namespaces.</span></span>

### <a name="code"></a><span data-ttu-id="75f3e-117">Codice</span><span class="sxs-lookup"><span data-stu-id="75f3e-117">Code</span></span>

```vb
Public Sub Main()

    Dim printerName As String
    Dim currentPrinter As New PrinterSettings
    Dim size As PaperSize

    Dim printerList As New ArrayList
    For Each printerName In PrinterSettings.InstalledPrinters
        currentPrinter.PrinterName = printerName
        If PrinterHasLegalPaper(currentPrinter) Then
            printerList.Add(printerName)
            Dts.Events.FireInformation(0, "Example", _
                "Printer " & printerName & " has legal paper.", _
                String.Empty, 0, False)
        Else
            Dts.Events.FireWarning(0, "Example", _
                "Printer " & printerName & " DOES NOT have legal paper.", _
                String.Empty, 0)
        End If
    Next

    Dts.Variables("PrinterList").Value = printerList

    Dts.TaskResult = ScriptResults.Success

End Sub

Private Function PrinterHasLegalPaper( _
    ByVal thisPrinter As PrinterSettings) As Boolean

    Dim size As PaperSize
    Dim hasLegal As Boolean = False

    For Each size In thisPrinter.PaperSizes
        If size.Kind = PaperKind.Legal Then
            hasLegal = True
        End If
    Next

    Return hasLegal

End Function
```

```csharp
public void Main()
        {

            PrinterSettings currentPrinter = new PrinterSettings();
            PaperSize size;
            Boolean Flag = false;

            ArrayList printerList = new ArrayList();
            foreach (string printerName in PrinterSettings.InstalledPrinters)
            {
                currentPrinter.PrinterName = printerName;
                if (PrinterHasLegalPaper(currentPrinter))
                {
                    printerList.Add(printerName);
                    Dts.Events.FireInformation(0, "Example", "Printer " + printerName + " has legal paper.", String.Empty, 0, ref Flag);
                }
                else
                {
                    Dts.Events.FireWarning(0, "Example", "Printer " + printerName + " DOES NOT have legal paper.", String.Empty, 0);
                }
            }

            Dts.Variables["PrinterList"].Value = printerList;

            Dts.TaskResult = (int)ScriptResults.Success;

        }

        private bool PrinterHasLegalPaper(PrinterSettings thisPrinter)
        {

            bool hasLegal = false;

            foreach (PaperSize size in thisPrinter.PaperSizes)
            {
                if (size.Kind == PaperKind.Legal)
                {
                    hasLegal = true;
                }
            }

            return hasLegal;

        }
```

<span data-ttu-id="75f3e-118">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="75f3e-118">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="75f3e-119">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="75f3e-119">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="75f3e-120">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="75f3e-120">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="75f3e-121">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="75f3e-121">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="75f3e-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f3e-122">See Also</span></span>
 [<span data-ttu-id="75f3e-123">Esempi di attività Script</span><span class="sxs-lookup"><span data-stu-id="75f3e-123">Script Task Examples</span></span>](../extending-packages-scripting-task-examples/script-task-examples.md)


