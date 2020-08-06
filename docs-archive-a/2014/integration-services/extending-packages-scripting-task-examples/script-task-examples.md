---
title: Esempi di attività Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], examples
- examples [Integration Services]
- SSIS Script task, examples
ms.assetid: b0dd77ee-ee11-4cd9-87aa-61dd67f2fe1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 920d2ee5cc2e64db1048d10522d9be644794e55b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716415"
---
# <a name="script-task-examples"></a><span data-ttu-id="18bbe-102">Esempi di attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-102">Script Task Examples</span></span>
  <span data-ttu-id="18bbe-103">L'attività Script è uno strumento multifunzione che è possibile utilizzare in un pacchetto per rispondere ai requisiti non soddisfatti dalle attività incluse in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18bbe-103">The Script task is a multi-purpose tool that you can use in a package to fill almost any requirement that is not met by the tasks included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="18bbe-104">In questo argomento sono riportati esempi di codice dell'attività Script che dimostrano alcune delle funzionalità disponibili.</span><span class="sxs-lookup"><span data-stu-id="18bbe-104">This topic lists Script task code samples that demonstrate some of the available functionality.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="18bbe-105">Se si desidera creare attività da riutilizzare più facilmente con più pacchetti, è possibile utilizzare il codice di questi esempi di attività Script come punto iniziale per attività personalizzate.</span><span class="sxs-lookup"><span data-stu-id="18bbe-105">If you want to create tasks that you can more easily reuse across multiple packages, consider using the code in these Script task samples as the starting point for custom tasks.</span></span> <span data-ttu-id="18bbe-106">Per altre informazioni, vedere [Sviluppo di un'attività personalizzata](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="18bbe-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18bbe-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="18bbe-107">In This Section</span></span>  
  
### <a name="example-topics"></a><span data-ttu-id="18bbe-108">Argomenti di esempio</span><span class="sxs-lookup"><span data-stu-id="18bbe-108">Example Topics</span></span>  
 <span data-ttu-id="18bbe-109">Questa sezione contiene esempi di codice che dimostrano i vari utilizzi delle classi di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] che è possibile incorporare in un'attività Script di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="18bbe-109">This section contains code examples that demonstrate various uses of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that you can incorporate into an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task:</span></span>  
  
 [<span data-ttu-id="18bbe-110">Rilevamento di un file flat vuoto con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-110">Detecting an Empty Flat File with the Script Task</span></span>](../extending-packages-scripting-task-examples/detecting-an-empty-flat-file-with-the-script-task.md)  
 <span data-ttu-id="18bbe-111">Viene controllato un file flat per determinare se contiene righe di dati, quindi il risultato viene salvato in una variabile da utilizzare nella diramazione del flusso di controllo.</span><span class="sxs-lookup"><span data-stu-id="18bbe-111">Checks a flat file to determine whether it contains rows of data, and saves the result to a variable for use in control flow branching.</span></span>  
  
 [<span data-ttu-id="18bbe-112">Raccolta di un elenco per il ciclo ForEach con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-112">Gathering a List for the ForEach Loop with the Script Task</span></span>](../extending-packages-scripting-task-examples/gathering-a-list-for-the-foreach-loop-with-the-script-task.md)  
 <span data-ttu-id="18bbe-113">Viene raccolto un elenco di file che soddisfano criteri specificati dall'utente e viene popolata una variabile per un utilizzo successivo da parte dell'enumeratore Foreach da variabile.</span><span class="sxs-lookup"><span data-stu-id="18bbe-113">Gathers a list of files that meet user-specified criteria, and populates a variable for later use by the Foreach from Variable Enumerator.</span></span>  
  
 [<span data-ttu-id="18bbe-114">Esecuzione di query su Active Directory tramite l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-114">Querying the Active Directory with the Script Task</span></span>](../extending-packages-scripting-task-examples/querying-the-active-directory-with-the-script-task.md)  
 <span data-ttu-id="18bbe-115">Vengono recuperate informazioni utente da Active Directory in base al valore di una variabile [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], tramite le classi dello spazio dei nomi System.DirectoryServices.</span><span class="sxs-lookup"><span data-stu-id="18bbe-115">Retrieves user information from Active Directory based on the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, by using classes in the System.DirectoryServices namespace.</span></span>  
  
 [<span data-ttu-id="18bbe-116">Monitoraggio dei contatori delle prestazioni con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-116">Monitoring Performance Counters with the Script Task</span></span>](../extending-packages-scripting-task-examples/monitoring-performance-counters-with-the-script-task.md)  
 <span data-ttu-id="18bbe-117">Viene creato un contatore delle prestazioni personalizzato che può essere usato per registrare lo stato dell'esecuzione di un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], tramite le classi dello spazio dei nomi System.Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="18bbe-117">Creates a custom performance counter that can be used to track the execution progress of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package, by using classes in the System.Diagnostics namespace.</span></span>  
  
 [<span data-ttu-id="18bbe-118">Utilizzo di immagini con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-118">Working with Images with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md)  
 <span data-ttu-id="18bbe-119">Vengono compresse immagini in formato JPEG e da esse vengono create immagini anteprima, tramite le classi dello spazio dei nomi System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="18bbe-119">Compresses images into the JPEG format and creates thumbnail images from them, by using classes in the System.Drawing namespace.</span></span>  
  
 [<span data-ttu-id="18bbe-120">Ricerca di stampanti installate con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-120">Finding Installed Printers with the Script Task</span></span>](../extending-packages-scripting-task-examples/finding-installed-printers-with-the-script-task.md)  
 <span data-ttu-id="18bbe-121">Vengono individuate le stampanti installate che supportano un formato della carta specifico, tramite le classi dello spazio dei nomi System.Drawing.Printing.</span><span class="sxs-lookup"><span data-stu-id="18bbe-121">Locates installed printers that support a specific paper size, by using classes in the System.Drawing.Printing namespace.</span></span>  
  
 [<span data-ttu-id="18bbe-122">Invio di un messaggio di posta HTML con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-122">Sending an HTML Mail Message with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-an-html-mail-message-with-the-script-task.md)  
 <span data-ttu-id="18bbe-123">Viene inviato un messaggio di posta in formato HTML anziché di testo normale.</span><span class="sxs-lookup"><span data-stu-id="18bbe-123">Sends a mail message in HTML format instead of plain text format.</span></span>  
  
 [<span data-ttu-id="18bbe-124">Utilizzo di file di Excel con l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-124">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
 <span data-ttu-id="18bbe-125">Vengono elencati i fogli di lavoro di un file di Excel e viene verificata l'esistenza di un foglio di lavoro specifico.</span><span class="sxs-lookup"><span data-stu-id="18bbe-125">Lists the worksheets in an Excel file and checks for the existence of a specific worksheet.</span></span>  
  
 [<span data-ttu-id="18bbe-126">Invio di messaggi a una coda privata remota tramite l'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-126">Sending to a Remote Private Message Queue with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-to-a-remote-private-message-queue-with-the-script-task.md)  
 <span data-ttu-id="18bbe-127">Viene inviato un messaggio a una coda privata remota.</span><span class="sxs-lookup"><span data-stu-id="18bbe-127">Sends a message to a remote private message queue.</span></span>  
  
### <a name="other-examples"></a><span data-ttu-id="18bbe-128">Altri esempi</span><span class="sxs-lookup"><span data-stu-id="18bbe-128">Other Examples</span></span>  
 <span data-ttu-id="18bbe-129">Anche gli argomenti riportati di seguito contengono esempi di codice da utilizzare con l'attività Script:</span><span class="sxs-lookup"><span data-stu-id="18bbe-129">The following topics also contain code examples for use with the Script task:</span></span>  
  
 [<span data-ttu-id="18bbe-130">Uso delle variabili nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-130">Using Variables in the Script Task</span></span>](../extending-packages-scripting/task/using-variables-in-the-script-task.md)  
 <span data-ttu-id="18bbe-131">Viene chiesta la conferma dell'utente per continuare o meno l'esecuzione del pacchetto, in base al valore di una variabile del pacchetto che potrebbe superare il limite specificato in un'altra variabile.</span><span class="sxs-lookup"><span data-stu-id="18bbe-131">Asks the user for confirmation of whether the package should continue to run, based on the value of a package variable that may exceed the limit specified in another variable.</span></span>  
  
 [<span data-ttu-id="18bbe-132">Connessione a origini dati nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-132">Connecting to Data Sources in the Script Task</span></span>](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md)  
 <span data-ttu-id="18bbe-133">Vengono recuperate una connessione o le relative informazioni dalle gestioni connessioni definite nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="18bbe-133">Retrieves a connection or connection information from connection managers defined in the package.</span></span>  
  
 [<span data-ttu-id="18bbe-134">Generazione di eventi nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-134">Raising Events in the Script Task</span></span>](../extending-packages-scripting/task/raising-events-in-the-script-task.md)  
 <span data-ttu-id="18bbe-135">Viene generato un errore, un avviso o un messaggio informativo a seconda dello stato della connessione Internet nel server.</span><span class="sxs-lookup"><span data-stu-id="18bbe-135">Raises an error, a warning, or an informational message based on the status of the Internet connection on the server.</span></span>  
  
 [<span data-ttu-id="18bbe-136">Registrazione nell'attività Script</span><span class="sxs-lookup"><span data-stu-id="18bbe-136">Logging in the Script Task</span></span>](../extending-packages-scripting/task/logging-in-the-script-task.md)  
 <span data-ttu-id="18bbe-137">Viene registrato il numero di elementi elaborati dall'attività nei provider di log abilitati.</span><span class="sxs-lookup"><span data-stu-id="18bbe-137">Logs the number of items processed by the task to enabled log providers.</span></span>  
  
<span data-ttu-id="18bbe-138">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="18bbe-138">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="18bbe-139">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="18bbe-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="18bbe-140">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="18bbe-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="18bbe-141">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="18bbe-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
