---
title: Raccolta di un elenco per il ciclo ForEach con l'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Foreach Loop containers
- Script task [Integration Services], Foreach loops
- Script task [Integration Services], examples
- SSIS Script task, Foreach loops
ms.assetid: 694f0462-d0c5-4191-b64e-821b1bdef055
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 039860da121efaa52115bb515b158ea10373e459
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713312"
---
# <a name="gathering-a-list-for-the-foreach-loop-with-the-script-task"></a><span data-ttu-id="4c422-102">Raccolta di un elenco per il ciclo ForEach con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="4c422-102">Gathering a List for the ForEach Loop with the Script Task</span></span>
  <span data-ttu-id="4c422-103">L'enumeratore Foreach da variabile enumera gli elementi in un elenco passato in una variabile ed esegue le stesse attività su ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="4c422-103">The Foreach from Variable Enumerator enumerates over the items in a list that is passed to it in a variable and performs the same tasks on each item.</span></span> <span data-ttu-id="4c422-104">È possibile utilizzare codice personalizzato in un'attività Script per popolare un elenco a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="4c422-104">You can use custom code in a Script task to populate a list for this purpose.</span></span> <span data-ttu-id="4c422-105">Per altre informazioni sull'enumeratore, vedere [Contenitore ciclo Foreach](../control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="4c422-105">For more information about the enumerator, see [Foreach Loop Container](../control-flow/foreach-loop-container.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c422-106">Se si desidera creare un'attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questo esempio di attività Script come punto iniziale per un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4c422-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="4c422-107">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="4c422-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="4c422-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c422-108">Description</span></span>  
 <span data-ttu-id="4c422-109">Nell'esempio seguente vengono utilizzati i metodi dello spazio dei nomi `System.IO` per raccogliere un elenco di cartelle di lavoro di Excel sul computer, più o meno recenti di un numero di giorni specificati dall'utente in una variabile.</span><span class="sxs-lookup"><span data-stu-id="4c422-109">The following example uses methods from the `System.IO` namespace to gather a list of Excel workbooks on the computer that are either newer or older than a number of days specified by the user in a variable.</span></span> <span data-ttu-id="4c422-110">Nelle directory dell'unità C viene eseguita una ricerca ricorsiva dei file con estensione xls e viene esaminata la data dell'ultima modifica di ogni file per determinare se il file fa parte dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4c422-110">It searches directories on Drive C recursively for files that have the .xls extension and examines the date on which each file was last modified to determine whether the file belongs in the list.</span></span> <span data-ttu-id="4c422-111">I file risultanti vengono aggiunti a un oggetto `ArrayList`. L'oggetto `ArrayList` viene quindi salvato in una variabile per uso successivo in un contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="4c422-111">It adds qualifying files to an `ArrayList` and saves the `ArrayList` to a variable for later use in a Foreach Loop container.</span></span> <span data-ttu-id="4c422-112">Il contenitore Ciclo Foreach è configurato per utilizzare l'enumeratore Foreach da variabile.</span><span class="sxs-lookup"><span data-stu-id="4c422-112">The Foreach Loop container is configured to use the Foreach from Variable enumerator.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c422-113">La variabile che si utilizza con l'enumeratore Foreach da variabile deve essere di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="4c422-113">The variable that you use with the Foreach from Variable Enumerator must be of type `Object`.</span></span> <span data-ttu-id="4c422-114">L'oggetto inserito nella variabile deve implementare una delle interfacce seguenti: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource` o `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span><span class="sxs-lookup"><span data-stu-id="4c422-114">The object that you place in the variable must implement one of the following interfaces: `System.Collections.IEnumerable`, `System.Runtime.InteropServices.ComTypes.IEnumVARIANT`, `System.ComponentModel IListSource`, or `Microsoft.SqlServer.Dts.Runtime.Wrapper.ForEachEnumeratorHost`.</span></span> <span data-ttu-id="4c422-115">Viene in genere utilizzato un oggetto `Array` o `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="4c422-115">An `Array` or `ArrayList` is commonly used.</span></span> <span data-ttu-id="4c422-116">Per l'oggetto `ArrayList` sono necessari un riferimento e un'istruzione `Imports` per lo spazio dei nomi `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="4c422-116">The `ArrayList` requires a reference and an `Imports` statement for the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="4c422-117">È possibile provare a utilizzare questa attività utilizzando valori diversi positivi e negativi per la variabile del pacchetto `FileAge`.</span><span class="sxs-lookup"><span data-stu-id="4c422-117">You can experiment with this task by using different positive and negative values for the `FileAge` package variable.</span></span> <span data-ttu-id="4c422-118">È possibile, ad esempio, immettere 5 per cercare i file creati negli ultimi cinque giorni oppure immettere -3 per cercare i file creati più di tre giorni fa.</span><span class="sxs-lookup"><span data-stu-id="4c422-118">For example, you can enter 5 to search for files created in the last five days, or enter -3 to search for files that were created more than three days ago.</span></span> <span data-ttu-id="4c422-119">L'esecuzione di questa attività può richiedere alcuni minuti su un'unità con numerose cartelle in cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4c422-119">This task may take a minute or two on a drive with many folders to search.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="4c422-120">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="4c422-120">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="4c422-121">Creare una variabile del pacchetto denominata `FileAge` di tipo integer e immettere un valore integer positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="4c422-121">Create a package variable named `FileAge` of type integer and enter a positive or negative integer value.</span></span> <span data-ttu-id="4c422-122">Quando il valore è positivo, il codice cerca i file più recenti del numero specificato di giorni. Quando invece è negativo, cerca i file più obsoleti del numero specificato di giorni.</span><span class="sxs-lookup"><span data-stu-id="4c422-122">When the value is positive, the code searches for files newer than the specified number of days; when negative, for files older than the specified number of days.</span></span>  
  
2.  <span data-ttu-id="4c422-123">Creare una variabile del pacchetto denominata `FileList` di tipo `Object` per ricevere l'elenco di file raccolti dall'attività Script per utilizzarli in seguito tramite l'enumeratore Foreach da variabile.</span><span class="sxs-lookup"><span data-stu-id="4c422-123">Create a package variable named `FileList` of type `Object` to receive the list of files gathered by the Script task for later use by the Foreach from Variable Enumerator.</span></span>  
  
3.  <span data-ttu-id="4c422-124">Aggiungere la variabile `FileAge` alla proprietà `ReadOnlyVariables` dell'attività Script e aggiungere la variabile `FileList` alla proprietà `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="4c422-124">Add the `FileAge` variable to the Script task's `ReadOnlyVariables` property, and add the `FileList` variable to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="4c422-125">Nel codice importare gli spazi dei nomi `System.Collections` e `System.IO`.</span><span class="sxs-lookup"><span data-stu-id="4c422-125">In your code, import the `System.Collections` and the `System.IO` namespaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4c422-126">Codice</span><span class="sxs-lookup"><span data-stu-id="4c422-126">Code</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Math  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.Collections  
Imports System.IO  
  
Public Class ScriptMain  
  
  Private Const FILE_AGE As Integer = -50  
  
  Private Const FILE_ROOT As String = "C:\"  
  Private Const FILE_FILTER As String = "*.xls"  
  
  Private isCheckForNewer As Boolean = True  
  Dim fileAgeLimit As Integer  
  Private listForEnumerator As ArrayList  
  
  Public Sub Main()  
  
    fileAgeLimit = DirectCast(Dts.Variables("FileAge").Value, Integer)  
  
    ' If value provided is positive, we want files NEWER THAN n days.  
    '  If negative, we want files OLDER THAN n days.  
    If fileAgeLimit < 0 Then  
      isCheckForNewer = False  
    End If  
    ' Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit)  
  
    listForEnumerator = New ArrayList  
  
    GetFilesInFolder(FILE_ROOT)  
  
    ' Return the list of files to the variable  
    '  for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: " & listForEnumerator.Count.ToString, "Results", Windows.Forms.MessageBoxButtons.OK, Windows.Forms.MessageBoxIcon.Information)  
    Dts.Variables("FileList").Value = listForEnumerator  
  
    Dts.TaskResult = ScriptResults.Success  
  
  End Sub  
  
  Private Sub GetFilesInFolder(ByVal folderPath As String)  
  
    Dim localFiles() As String  
    Dim localFile As String  
    Dim fileChangeDate As Date  
    Dim fileAge As TimeSpan  
    Dim fileAgeInDays As Integer  
    Dim childFolder As String  
  
    Try  
      localFiles = Directory.GetFiles(folderPath, FILE_FILTER)  
      For Each localFile In localFiles  
        fileChangeDate = File.GetLastWriteTime(localFile)  
        fileAge = DateTime.Now.Subtract(fileChangeDate)  
        fileAgeInDays = fileAge.Days  
        CheckAgeOfFile(localFile, fileAgeInDays)  
      Next  
  
      If Directory.GetDirectories(folderPath).Length > 0 Then  
        For Each childFolder In Directory.GetDirectories(folderPath)  
          GetFilesInFolder(childFolder)  
        Next  
      End If  
  
    Catch  
      ' Ignore exceptions on special folders such as System Volume Information.  
    End Try  
  
  End Sub  
  
  Private Sub CheckAgeOfFile(ByVal localFile As String, ByVal fileAgeInDays As Integer)  
  
    If isCheckForNewer Then  
      If fileAgeInDays <= fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    Else  
      If fileAgeInDays > fileAgeLimit Then  
        listForEnumerator.Add(localFile)  
      End If  
    End If  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Math;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Collections;  
using System.IO;  
  
public partial class ScriptMain : Microsoft.SqlServer.Dts.Tasks.ScriptTask.VSTARTScriptObjectModelBase  
    {  
  
        private const int FILE_AGE = -50;  
  
        private const string FILE_ROOT = "C:\\";  
        private const string FILE_FILTER = "*.xls";  
  
        private bool isCheckForNewer = true;  
        int fileAgeLimit;  
        private ArrayList listForEnumerator;  
  
        public void Main()  
  {  
  
    fileAgeLimit = (int)(Dts.Variables["FileAge"].Value);  
  
    // If value provided is positive, we want files NEWER THAN n days.  
    // If negative, we want files OLDER THAN n days.  
    if (fileAgeLimit<0)  
    {  
      isCheckForNewer = false;  
    }  
    // Extract number of days as positive integer.  
    fileAgeLimit = Math.Abs(fileAgeLimit);  
  
    ArrayList listForEnumerator = new ArrayList();  
  
    GetFilesInFolder(FILE_ROOT);  
  
    // Return the list of files to the variable  
    // for later use by the Foreach from Variable enumerator.  
    System.Windows.Forms.MessageBox.Show("Matching files: "+ listForEnumerator.Count, "Results",   
MessageBoxButtons.OK, MessageBoxIcon.Information);  
    Dts.Variables["FileList"].Value = listForEnumerator;  
  
    Dts.TaskResult = (int)ScriptResults.Success;  
  
  }  
  
        private void GetFilesInFolder(string folderPath)  
        {  
  
            string[] localFiles;  
            DateTime fileChangeDate;  
            TimeSpan fileAge;  
            int fileAgeInDays;  
  
            try  
            {  
                localFiles = Directory.GetFiles(folderPath, FILE_FILTER);  
                foreach (string localFile in localFiles)  
                {  
                    fileChangeDate = File.GetLastWriteTime(localFile);  
                    fileAge = DateTime.Now.Subtract(fileChangeDate);  
                    fileAgeInDays = fileAge.Days;  
                    CheckAgeOfFile(localFile, fileAgeInDays);  
                }  
  
                if (Directory.GetDirectories(folderPath).Length > 0)  
                {  
                    foreach (string childFolder in Directory.GetDirectories(folderPath))  
                    {  
                        GetFilesInFolder(childFolder);  
                    }  
                }  
  
            }  
            catch  
            {  
                // Ignore exceptions on special folders, such as System Volume Information.  
            }  
  
        }  
  
        private void CheckAgeOfFile(string localFile, int fileAgeInDays)  
        {  
  
            if (isCheckForNewer)  
            {  
                if (fileAgeInDays <= fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
            else  
            {  
                if (fileAgeInDays > fileAgeLimit)  
                {  
                    listForEnumerator.Add(localFile);  
                }  
            }  
  
        }  
  
    }  
```  
  
<span data-ttu-id="4c422-127">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="4c422-127">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="4c422-128">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="4c422-128">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="4c422-129">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="4c422-129">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="4c422-130">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="4c422-130">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c422-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c422-131">See Also</span></span>  
 <span data-ttu-id="4c422-132">[Contenitore ciclo foreach](../control-flow/foreach-loop-container.md) </span><span class="sxs-lookup"><span data-stu-id="4c422-132">[Foreach Loop Container](../control-flow/foreach-loop-container.md) </span></span>  
 [<span data-ttu-id="4c422-133">Configurare un contenitore ciclo foreach</span><span class="sxs-lookup"><span data-stu-id="4c422-133">Configure a Foreach Loop Container</span></span>](../configure-a-foreach-loop-container.md)  
  
  
