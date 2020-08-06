---
title: Gestione delle eccezioni SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SMO [SQL Server], exceptions
- exceptions [SMO]
- SQL Server Management Objects, exceptions
- inner exceptions [SMO]
ms.assetid: 4c725ff2-6588-44ca-b86a-87979e164153
author: stevestein
ms.author: sstein
ms.openlocfilehash: f4ae9e475a019c9bf874ee3f8365f3f3ac8e19d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637194"
---
# <a name="handling-smo-exceptions"></a><span data-ttu-id="75770-102">Gestione delle eccezioni SMO</span><span class="sxs-lookup"><span data-stu-id="75770-102">Handling SMO Exceptions</span></span>
  <span data-ttu-id="75770-103">Nel codice gestito vengono generate eccezioni quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="75770-103">In managed code, exceptions are thrown when an error occurs.</span></span> <span data-ttu-id="75770-104">Proprietà e metodi SMO non indicano l'esito positivo o negativo nel valore restituito.</span><span class="sxs-lookup"><span data-stu-id="75770-104">SMO methods and properties do not report success or failure in the return value.</span></span> <span data-ttu-id="75770-105">Le eccezioni possono invece essere rilevate e gestite da un gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="75770-105">Instead, exceptions can be caught and handled by an exception handler.</span></span>  
  
 <span data-ttu-id="75770-106">In SMO esistono classi di eccezioni diverse.</span><span class="sxs-lookup"><span data-stu-id="75770-106">Different exception classes exist in the SMO.</span></span> <span data-ttu-id="75770-107">È possibile estrarre informazioni sull'eccezione dalle proprietà dell'eccezione, ad esempio la proprietà `Message` fornisce un messaggio di testo sull'eccezione.</span><span class="sxs-lookup"><span data-stu-id="75770-107">Information about the exception can be extracted from the exception properties such as the `Message` property that gives a text message about the exception.</span></span>  
  
 <span data-ttu-id="75770-108">Le istruzioni relative alla gestione delle eccezioni sono specifiche del linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="75770-108">The exception handling statements are specific to the programming language.</span></span> <span data-ttu-id="75770-109">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic, ad esempio, è l'istruzione `Catch`.</span><span class="sxs-lookup"><span data-stu-id="75770-109">For example, in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic it is the `Catch` statement.</span></span>  
  
## <a name="inner-exceptions"></a><span data-ttu-id="75770-110">Eccezioni interne</span><span class="sxs-lookup"><span data-stu-id="75770-110">Inner Exceptions</span></span>  
 <span data-ttu-id="75770-111">Le eccezioni possono essere generali o specifiche.</span><span class="sxs-lookup"><span data-stu-id="75770-111">Exceptions can either be general or specific.</span></span> <span data-ttu-id="75770-112">Le eccezioni generali contengono un set di eccezioni specifiche.</span><span class="sxs-lookup"><span data-stu-id="75770-112">General exceptions contain a set of specific exceptions.</span></span> <span data-ttu-id="75770-113">È possibile utilizzare diverse istruzioni `Catch` per gestire gli errori anticipati e fare in modo che gli errori rimanenti vengano passati al codice di gestione delle eccezioni generali.</span><span class="sxs-lookup"><span data-stu-id="75770-113">Several `Catch` statements can be used to handle anticipated errors and let remaining errors fall through to general exception handling code.</span></span> <span data-ttu-id="75770-114">Le eccezioni si verificano spesso in una sequenza a cascata.</span><span class="sxs-lookup"><span data-stu-id="75770-114">Exceptions often occur in a cascading sequence.</span></span> <span data-ttu-id="75770-115">Accade di frequente che un'eccezione SMO sia stata causata da un'eccezione SQL.</span><span class="sxs-lookup"><span data-stu-id="75770-115">Frequently, an SMO exception might have been caused by an SQL exception.</span></span> <span data-ttu-id="75770-116">È possibile stabilirlo utilizzando in successione la proprietà `InnerException` per determinare l'eccezione originale che ha provocato l'eccezione finale di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="75770-116">The way to detect this is to use the `InnerException` property successively to determine the original exception that caused the final, top-level exception.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="75770-117">L' `SQLException` eccezione viene dichiarata nello spazio dei nomi **System. Data. SqlClient** .</span><span class="sxs-lookup"><span data-stu-id="75770-117">The `SQLException` exception is declared in the **System.Data.SqlClient** namespace.</span></span>  
  
 <span data-ttu-id="75770-118">![Diagramma in cui sono illustrati i livelli da cui viene generata un'eccezione](../../../database-engine/dev-guide/media/exception-flow.gif "Diagramma in cui sono illustrati i livelli da cui viene generata un'eccezione")</span><span class="sxs-lookup"><span data-stu-id="75770-118">![A diagram that shows the levels from which an excp](../../../database-engine/dev-guide/media/exception-flow.gif "A diagram that shows the levels from which an excp")</span></span>  
  
 <span data-ttu-id="75770-119">Nel diagramma seguente viene illustrato il flusso di eccezioni attraverso i livelli dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75770-119">The diagram shows the flow of exceptions through the layers of the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75770-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="75770-120">Example</span></span>  
 <span data-ttu-id="75770-121">Per usare qualsiasi esempio di codice fornito, è necessario scegliere l'ambiente di programmazione, il modello di programmazione e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="75770-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="75770-122">Per altre informazioni, vedere [creare un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) o [creare un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="75770-122">For more information, see [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) or [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="catching-an-exception-in-visual-basic"></a><span data-ttu-id="75770-123">Rilevamento di un'eccezione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75770-123">Catching an Exception in Visual Basic</span></span>  
 <span data-ttu-id="75770-124">Questo esempio di codice illustra come usare l'istruzione `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] per rilevare un'eccezione SMO.</span><span class="sxs-lookup"><span data-stu-id="75770-124">This code example shows how to use the `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] statement to catch a SMO exception.</span></span> <span data-ttu-id="75770-125">Tutte le eccezioni SMO sono di tipo SmoException e sono elencate nella documentazione di riferimento di SMO.</span><span class="sxs-lookup"><span data-stu-id="75770-125">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="75770-126">La sequenza di eccezioni interne viene visualizzata per mostrare la radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="75770-126">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="75770-127">Per ulteriori informazioni, vedere la documentazione di [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="75770-127">For more information, see the [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET documentation.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBExceptions1](SMO How to#SMO_VBExceptions1)]  -->  
  
## <a name="catching-an-exception-in-visual-c"></a><span data-ttu-id="75770-128">Rilevamento di un'eccezione in Visual C#</span><span class="sxs-lookup"><span data-stu-id="75770-128">Catching an Exception in Visual C#</span></span>  
 <span data-ttu-id="75770-129">In questo esempio di codice viene illustrato come utilizzare l'istruzione `Try...Catch...Finally` Visual C# per rilevare un'eccezione SMO.</span><span class="sxs-lookup"><span data-stu-id="75770-129">This code example shows how to use the `Try...Catch...Finally` Visual C# statement to catch a SMO exception.</span></span> <span data-ttu-id="75770-130">Tutte le eccezioni SMO sono di tipo SmoException e sono elencate nella documentazione di riferimento di SMO.</span><span class="sxs-lookup"><span data-stu-id="75770-130">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="75770-131">La sequenza di eccezioni interne viene visualizzata per mostrare la radice dell'errore.</span><span class="sxs-lookup"><span data-stu-id="75770-131">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="75770-132">Per ulteriori informazioni, vedere la documentazione di Visual C#.</span><span class="sxs-lookup"><span data-stu-id="75770-132">For more information, see the Visual C# documentation.</span></span>  
  
```  
{   
//This sample requires the Microsoft.SqlServer.Management.Smo.Agent namespace to be included.   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define an Operator object variable by supplying the parent SQL Agent and the name arguments in the constructor.   
//Note that the Operator type requires [] parenthesis to differentiate it from a Visual Basic key word.   
op = new Operator(srv.JobServer, "Test_Operator");   
op.Create();   
//Start exception handling.   
try {   
    //Create the operator again to cause an SMO exception.   
    OperatorCategory opx;   
    opx = new OperatorCategory(srv.JobServer, "Test_Operator");   
    opx.Create();   
}   
//Catch the SMO exception   
catch (SmoException smoex) {   
    Console.WriteLine("This is an SMO Exception");   
   //Display the SMO exception message.   
   Console.WriteLine(smoex.Message);   
   //Display the sequence of non-SMO exceptions that caused the SMO exception.   
   Exception ex;   
   ex = smoex.InnerException;   
   while (!object.ReferenceEquals(ex.InnerException, (null))) {   
      Console.WriteLine(ex.InnerException.Message);   
      ex = ex.InnerException;   
    }   
    }   
   //Catch other non-SMO exceptions.   
   catch (Exception ex) {   
      Console.WriteLine("This is not an SMO exception.");   
}   
}  
```  
  
  
