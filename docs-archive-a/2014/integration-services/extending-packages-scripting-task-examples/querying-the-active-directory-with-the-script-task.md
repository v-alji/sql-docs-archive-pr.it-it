---
title: Esecuzione di query su Active Directory tramite l'attività Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], Active Directory access
- SSIS Script task, Active Directory access
- Script task [Integration Services], examples
- Active Directory [Integration Services]
ms.assetid: a88fefbb-9ea2-4a86-b836-e71315bac68e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 624aa56289b9cab9174882b586a37e5d0de7ca9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624871"
---
# <a name="querying-the-active-directory-with-the-script-task"></a><span data-ttu-id="b5252-102">Esecuzione di query su Active Directory tramite l'attività Script</span><span class="sxs-lookup"><span data-stu-id="b5252-102">Querying the Active Directory with the Script Task</span></span>
  <span data-ttu-id="b5252-103">Le applicazioni di elaborazione di dati aziendali, ad esempio i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], devono in genere elaborare i dati in modo diverso a seconda del grado, della posizione o di altre caratteristiche dei dipendenti archiviati in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b5252-103">Enterprise data processing applications, such as [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, often need to process data differently based on the rank, job title, or other characteristics of employees stored in Active Directory.</span></span> <span data-ttu-id="b5252-104">Active Directory è un servizio directory di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows che rende disponibile un archivio centralizzato di metadati sugli utenti e su altre risorse dell'organizzazione, come computer e stampanti.</span><span class="sxs-lookup"><span data-stu-id="b5252-104">Active Directory is a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows directory service that provides a centralized store of metadata, not only about users, but also about other organizational assets such as computers and printers.</span></span> <span data-ttu-id="b5252-105">Lo spazio dei nomi `System.DirectoryServices` in Microsoft .NET Framework fornisce le classi per l'utilizzo di Active Directory, che consente di indirizzare il flusso di lavoro dell'elaborazione dei dati in base alle informazioni archiviate.</span><span class="sxs-lookup"><span data-stu-id="b5252-105">The `System.DirectoryServices` namespace in the Microsoft .NET Framework provides classes for working with Active Directory, to help you direct data processing workflow based on the information that it stores.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5252-106">Se si desidera creare un'attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questo esempio di attività Script come punto iniziale per un'attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b5252-106">If you want to create a task that you can more easily reuse across multiple packages, consider using the code in this Script task sample as the starting point for a custom task.</span></span> <span data-ttu-id="b5252-107">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="b5252-107">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="description"></a><span data-ttu-id="b5252-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5252-108">Description</span></span>  
 <span data-ttu-id="b5252-109">Nell'esempio seguente vengono recuperati il nome, la posizione e il numero di telefono di un dipendente da Active Directory in base al valore della variabile `email`, che contiene l'indirizzo di posta elettronica del dipendente.</span><span class="sxs-lookup"><span data-stu-id="b5252-109">The following example retrieves an employee's name, title, and phone number from Active Directory based on the value of the `email` variable, which contains the e-mail address of the employee.</span></span> <span data-ttu-id="b5252-110">I vincoli di precedenza del pacchetto possono utilizzare le informazioni recuperate per determinare, ad esempio, se inviare un messaggio di posta elettronica con priorità bassa o una pagina con priorità alta, in base alla posizione del dipendente.</span><span class="sxs-lookup"><span data-stu-id="b5252-110">Precedence constraints in the package can use the retrieved information to determine, for example, whether to send a low-priority e-mail message or a high-priority page, based on the job title of the employee.</span></span>  
  
#### <a name="to-configure-this-script-task-example"></a><span data-ttu-id="b5252-111">Per configurare l'esempio di attività Script</span><span class="sxs-lookup"><span data-stu-id="b5252-111">To configure this Script Task example</span></span>  
  
1.  <span data-ttu-id="b5252-112">Creare le tre variabili stringa `email`, `name` e `title`.</span><span class="sxs-lookup"><span data-stu-id="b5252-112">Create the three string variables `email`, `name`, and `title`.</span></span> <span data-ttu-id="b5252-113">Immettere un indirizzo di posta elettronica aziendale valido come valore della variabile `email`.</span><span class="sxs-lookup"><span data-stu-id="b5252-113">Enter a valid corporate email address as the value of the `email` variable.</span></span>  
  
2.  <span data-ttu-id="b5252-114">Nella pagina **script** dell' **Editor attività script**aggiungere la `email` variabile alla `ReadOnlyVariables` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="b5252-114">On the **Script** page of the **Script Task Editor**, add the `email` variable to the `ReadOnlyVariables` property.</span></span>  
  
3.  <span data-ttu-id="b5252-115">Aggiungere le variabili `name` e `title` alla proprietà `ReadWriteVariables`.</span><span class="sxs-lookup"><span data-stu-id="b5252-115">Add the `name` and `title` variables to the `ReadWriteVariables` property.</span></span>  
  
4.  <span data-ttu-id="b5252-116">Nel progetto di script aggiungere un riferimento allo spazio dei nomi `System.DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="b5252-116">In the script project, add a reference to the `System.DirectoryServices` namespace.</span></span>  
  
5.  <span data-ttu-id="b5252-117">.</span><span class="sxs-lookup"><span data-stu-id="b5252-117">.</span></span> <span data-ttu-id="b5252-118">Nel codice utilizzare un'istruzione `Imports` per importare lo spazio dei nomi `DirectoryServices`.</span><span class="sxs-lookup"><span data-stu-id="b5252-118">In your code, use an `Imports` statement to import the `DirectoryServices` namespace.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5252-119">Per eseguire correttamente lo script, è necessario che l'azienda utilizzi Active Directory nella propria rete e archivi le informazioni sui dipendenti utilizzati nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="b5252-119">To run this script successfully, your company must be using Active Directory on its network and storing the employee information that this example uses.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b5252-120">Codice</span><span class="sxs-lookup"><span data-stu-id="b5252-120">Code</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim directory As DirectoryServices.DirectorySearcher  
    Dim result As DirectoryServices.SearchResult  
    Dim email As String  
  
    email = Dts.Variables("email").Value.ToString  
  
    Try  
        directory = New _  
            DirectoryServices.DirectorySearcher("(mail=" & email & ")")  
        result = directory.FindOne  
        Dts.Variables("name").Value = _  
            result.Properties("displayname").ToString  
        Dts.Variables("title").Value = _  
            result.Properties("title").ToString  
        Dts.TaskResult = ScriptResults.Success  
    Catch ex As Exception  
        Dts.Events.FireError(0, _  
            "Script Task Example", _  
            ex.Message & ControlChars.CrLf & ex.StackTrace, _  
            String.Empty, 0)  
        Dts.TaskResult = ScriptResults.Failure  
    End Try  
  
End Sub  
```  
  
```csharp  
public void Main()  
{  
    //  
    DirectorySearcher directory;  
    SearchResult result;  
    string email;  
  
    email = (string)Dts.Variables["email"].Value;  
  
    try  
    {  
        directory = new DirectorySearcher("(mail=" + email + ")");  
        result = directory.FindOne();  
        Dts.Variables["name"].Value = result.Properties["displayname"].ToString();  
        Dts.Variables["title"].Value = result.Properties["title"].ToString();  
        Dts.TaskResult = (int)ScriptResults.Success;  
    }  
    catch (Exception ex)  
    {  
        Dts.Events.FireError(0, "Script Task Example", ex.Message + "\n" + ex.StackTrace, String.Empty, 0);  
        Dts.TaskResult = (int)ScriptResults.Failure;  
    }  
  
}  
```  
  
## <a name="external-resources"></a><span data-ttu-id="b5252-121">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="b5252-121">External Resources</span></span>  
  
-   <span data-ttu-id="b5252-122">Articolo tecnico [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588) (Elaborazione di informazioni di Active Directory in SSIS) nel sito Web social.technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b5252-122">Technical article, [Processing Active Directory Information in SSIS](https://go.microsoft.com/fwlink/?LinkId=199588), on social.technet.microsoft.com</span></span>  
  
<span data-ttu-id="b5252-123">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="b5252-123">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="b5252-124">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="b5252-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="b5252-125">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="b5252-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="b5252-126">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="b5252-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
