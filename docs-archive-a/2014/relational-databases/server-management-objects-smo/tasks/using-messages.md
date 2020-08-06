---
title: Uso dei messaggi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- messages [SMO]
ms.assetid: 4037a866-4826-4c1f-890c-e7e3658adf13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53b2e0fa4be2dfd53cdd8f4f0cacb7ae0bd79edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636648"
---
# <a name="using-messages"></a><span data-ttu-id="09710-102">Utilizzo di messaggi</span><span class="sxs-lookup"><span data-stu-id="09710-102">Using Messages</span></span>
  <span data-ttu-id="09710-103">In SMO i messaggi di sistema sono rappresentati dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> che appartiene all'oggetto `Server`.</span><span class="sxs-lookup"><span data-stu-id="09710-103">In SMO, system messages are represented by the <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> object that belongs to the `Server` object.</span></span> <span data-ttu-id="09710-104">Poiché i messaggi di sistema non possono essere modificati, le proprietà dell'oggetto `SystemMessage` sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="09710-104">Because the system messages cannot be modified, `SystemMessage` object properties are read-only.</span></span>  
  
 <span data-ttu-id="09710-105">In SMO i messaggi definiti dall'utente sono rappresentati a livello di codice dall'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection>.</span><span class="sxs-lookup"><span data-stu-id="09710-105">User-defined messages are represented programmatically in SMO by the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection> object.</span></span> <span data-ttu-id="09710-106">È possibile individuare i messaggi definiti dall'utente esistenti scorrendo la raccolta.</span><span class="sxs-lookup"><span data-stu-id="09710-106">Existing user-defined messages can be discovered by iterating through the collection.</span></span> <span data-ttu-id="09710-107">È possibile creare nuovi messaggi definiti dall'utente creando un'istanza di un nuovo oggetto `UserDefinedMessage` e impostando le proprietà appropriate.</span><span class="sxs-lookup"><span data-stu-id="09710-107">New user-defined messages can be created by instantiating a new `UserDefinedMessage` object and setting the appropriate properties.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="09710-108">Esempi</span><span class="sxs-lookup"><span data-stu-id="09710-108">Examples</span></span>  
 <span data-ttu-id="09710-109">Per gli esempi di codice seguenti, è necessario selezionare l'ambiente, il modello e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="09710-109">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="09710-110">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e alla [creazione di un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="09710-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="finding-a-particular-system-message-in-visual-basic"></a><span data-ttu-id="09710-111">Individuazione di un messaggio di sistema particolare in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09710-111">Finding a Particular System Message in Visual Basic</span></span>  
 <span data-ttu-id="09710-112">Nell'esempio di codice viene illustrato come identificare un messaggio di sistema in base al numero ID e come visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="09710-112">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMessages1](SMO How to#SMO_VBMessages1)]  -->  
  
## <a name="finding-a-particular-system-message-in-visual-c"></a><span data-ttu-id="09710-113">Individuazione di un messaggio di sistema particolare in Visual C#</span><span class="sxs-lookup"><span data-stu-id="09710-113">Finding a Particular System Message in Visual C#</span></span>  
 <span data-ttu-id="09710-114">Nell'esempio di codice viene illustrato come identificare un messaggio di sistema in base al numero ID e come visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="09710-114">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference an existing system message using the   
            //ItemByIdAndLanguage method.   
            SystemMessage msg = default(SystemMessage);  
            msg = srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
        }  
```  
  
## <a name="finding-a-particular-system-message-in-powershell"></a><span data-ttu-id="09710-115">Individuazione di un messaggio di sistema particolare in PowerShell</span><span class="sxs-lookup"><span data-stu-id="09710-115">Finding a Particular System Message in PowerShell</span></span>  
 <span data-ttu-id="09710-116">Nell'esempio di codice viene illustrato come identificare un messaggio di sistema in base al numero ID e come visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="09710-116">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get the message 14126 in US English and display it  
$msg = $srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english")  
$msg.ID.ToString() + " "+ $msg.Text  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-basic"></a><span data-ttu-id="09710-117">Aggiunta di un nuovo messaggio definito dall'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09710-117">Adding a New User-Defined Message in Visual Basic</span></span>  
 <span data-ttu-id="09710-118">Nell'esempio di codice viene illustrato come creare un messaggio definito dall'utente con un ID maggiore di 50000.</span><span class="sxs-lookup"><span data-stu-id="09710-118">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```vb
Dim mysrv As Server  
mysrv = New Server  
Dim udm As UserDefinedMessage  
udm = New UserDefinedMessage(mysrv, 50003, "us_english", 16, "Test message")  
udm.Create()  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-c"></a><span data-ttu-id="09710-119">Aggiunta di un nuovo messaggio definito dall'utente in Visual C#</span><span class="sxs-lookup"><span data-stu-id="09710-119">Adding a New User-Defined Message in Visual C#</span></span>  
 <span data-ttu-id="09710-120">Nell'esempio di codice viene illustrato come creare un messaggio definito dall'utente con un ID maggiore di 50000.</span><span class="sxs-lookup"><span data-stu-id="09710-120">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```csharp
{
            Server mysrv = new Server();  
  
            UserDefinedMessage udm = new UserDefinedMessage(mysrv, 50030, "us_english",16, "Test message");  
            udm.Create();  
             UserDefinedMessage  msg = mysrv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
  
        }  
```  
  
## <a name="adding-a-new-user-defined-message-in-powershell"></a><span data-ttu-id="09710-121">Aggiunta di un nuovo messaggio definito dall'utente in PowerShell</span><span class="sxs-lookup"><span data-stu-id="09710-121">Adding a New User-Defined Message in PowerShell</span></span>
 <span data-ttu-id="09710-122">Nell'esempio di codice viene illustrato come creare un messaggio definito dall'utente con un ID maggiore di 50000.</span><span class="sxs-lookup"><span data-stu-id="09710-122">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a new message
$udm = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedMessage -ArgumentList `  
$srv, 50030, "us_english", 16, "Test message"  
$udm.Create()  
$msg = $srv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
$msg  
```  
