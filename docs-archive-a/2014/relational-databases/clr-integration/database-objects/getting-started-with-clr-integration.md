---
title: Introduzione con l'integrazione con CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
- VB
- CSharp
helpviewer_keywords:
- database objects [CLR integration]
- namespaces [CLR integration]
- database objects [CLR integration], about CLR integration
- stored procedures [CLR integration]
- common language runtime [SQL Server], about CLR integration
- building database objects [CLR integration], about CLR integration
- common language runtime [SQL Server], stored procedures
- common language runtime [SQL Server], namespaces
- Hello World example [CLR integration]
- library [CLR integration]
ms.assetid: c73e628a-f54a-411a-bfe3-6dae519316cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 43c97e411a4d74aa48b88f2edbbe420ae17f3534
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623334"
---
# <a name="getting-started-with-clr-integration"></a><span data-ttu-id="fae29-102">Introduzione all'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="fae29-102">Getting Started with CLR Integration</span></span>
  <span data-ttu-id="fae29-103">In questo argomento viene fornita una panoramica delle librerie e degli spazi dei nomi necessari per compilare gli oggetti di database utilizzando l' [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integrazione con il .NET Framework Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fae29-103">This topic provides an overview of the namespaces and libraries required to compile database objects using the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="fae29-104">In questo argomento viene inoltre illustrato come scrivere, compilare ed eseguire una stored procedure CLR semplice scritta in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span><span class="sxs-lookup"><span data-stu-id="fae29-104">The topic also shows you how to write, compile, and run a simple CLR stored procedure written in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual C#.</span></span>  
  
## <a name="required-namespaces"></a><span data-ttu-id="fae29-105">Spazi dei nomi necessari</span><span class="sxs-lookup"><span data-stu-id="fae29-105">Required Namespaces</span></span>  
 <span data-ttu-id="fae29-106">A partire da [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fae29-106">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fae29-107">La funzionalità di integrazione CLR viene esposta in un assembly denominato system.data.dll, che fa parte di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fae29-107">CLR integration functionality is exposed in an assembly called system.data.dll, which is part of the .NET Framework.</span></span> <span data-ttu-id="fae29-108">Questo assembly è disponibile in Global Assembly Cache (GAC) e nella directory di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fae29-108">This assembly can be found in the Global Assembly Cache (GAC) as well as in the .NET Framework directory.</span></span> <span data-ttu-id="fae29-109">Poiché un riferimento a questo assembly viene in genere aggiunto tramite gli strumenti della riga di comando e [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, non è necessario aggiungerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="fae29-109">A reference to this assembly is typically added automatically by both command line tools and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Studio, so there is no need to add it manually.</span></span>  
  
 <span data-ttu-id="fae29-110">L'assembly system.data.dll contiene gli spazi dei nomi seguenti, necessari per la compilazione di oggetti di database CLR:</span><span class="sxs-lookup"><span data-stu-id="fae29-110">The system.data.dll assembly contains the following namespaces, which are required for compiling CLR database objects:</span></span>  
  
 `System.Data`  
  
 `System.Data.Sql`  
  
 `Microsoft.SqlServer.Server`  
  
 `System.Data.SqlTypes`  
  
## <a name="writing-a-simple-hello-world-stored-procedure"></a><span data-ttu-id="fae29-111">Scrittura di una stored procedure "Hello World" semplice</span><span class="sxs-lookup"><span data-stu-id="fae29-111">Writing A Simple "Hello World" Stored Procedure</span></span>  
 <span data-ttu-id="fae29-112">Copiare e incollare il codice Visual C# o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic seguente in un editor di testo e salvarlo in un file denominato "helloworld.cs" o "helloworld.vb".</span><span class="sxs-lookup"><span data-stu-id="fae29-112">Copy and paste the following Visual C# or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic code into a text editor, and save it in a file named "helloworld.cs" or "helloworld.vb".</span></span>  
  
```csharp  
using System;  
using System.Data;  
using Microsoft.SqlServer.Server;  
using System.Data.SqlTypes;  
  
public class HelloWorldProc  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld(out string text)  
    {  
        SqlContext.Pipe.Send("Hello world!" + Environment.NewLine);  
        text = "Hello world!";  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.Data  
Imports Microsoft.SqlServer.Server  
Imports System.Data.SqlTypes  
Imports System.Runtime.InteropServices  
  
Public Class HelloWorldProc  
    <Microsoft.SqlServer.Server.SqlProcedure> _   
    Public Shared  Sub HelloWorld(<Out()> ByRef text as String)  
        SqlContext.Pipe.Send("Hello world!" & Environment.NewLine)  
        text = "Hello world!"  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="fae29-113">Questo semplice programma contiene un singolo metodo statico su una classe pubblica.</span><span class="sxs-lookup"><span data-stu-id="fae29-113">This simple program contains a single static method on a public class.</span></span> <span data-ttu-id="fae29-114">Questo metodo utilizza due nuove classi, `SqlContext` e `SqlPipe`, per creare oggetti di database gestiti e restituire un messaggio di testo semplice.</span><span class="sxs-lookup"><span data-stu-id="fae29-114">This method uses two new classes, `SqlContext` and `SqlPipe`, for creating managed database objects to output a simple text message.</span></span> <span data-ttu-id="fae29-115">Il metodo assegna anche la stringa "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="fae29-115">The method also assigns the string "Hello world!"</span></span> <span data-ttu-id="fae29-116">come valore di un parametro out.</span><span class="sxs-lookup"><span data-stu-id="fae29-116">as the value of an out parameter.</span></span> <span data-ttu-id="fae29-117">Questo metodo può essere dichiarato come stored procedure in [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] stored procedure.</span><span class="sxs-lookup"><span data-stu-id="fae29-117">This method can be declared as a stored procedure in [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] stored procedure.</span></span>  
  
 <span data-ttu-id="fae29-118">Il programma verrà quindi compilato come libreria, caricato in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ed eseguito come stored procedure.</span><span class="sxs-lookup"><span data-stu-id="fae29-118">We will now compile this program as a library, load it into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], and run it as a stored procedure.</span></span>  
  
## <a name="compiling-the-hello-world-stored-procedure"></a><span data-ttu-id="fae29-119">Compilazione della stored procedure "Hello World"</span><span class="sxs-lookup"><span data-stu-id="fae29-119">Compiling the "Hello World" Stored Procedure</span></span>  
 [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)]<span data-ttu-id="fae29-120">.NET Framework i file di ridistribuzione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fae29-120">.NET Framework redistribution files by default.</span></span> <span data-ttu-id="fae29-121">Tali file includono csc.exe e vbc.exe, i compilatori della riga di comando per programmi Visual C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fae29-121">These files include csc.exe and vbc.exe, the command-line compilers for Visual C# and Visual Basic programs.</span></span> <span data-ttu-id="fae29-122">Per compilare l'esempio, è necessario modificare la variabile del percorso in modo che punti alla directory contenente csc.exe o vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="fae29-122">In order to compile our sample, you must modify your path variable to point to the directory containing csc.exe or vbc.exe.</span></span> <span data-ttu-id="fae29-123">Di seguito viene indicato il percorso di installazione predefinito di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fae29-123">The following is the default installation path of the .NET Framework.</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\(version)  
```  
  
 <span data-ttu-id="fae29-124">version contiene il numero di versione del file di ridistribuzione di .NET Framework installato.</span><span class="sxs-lookup"><span data-stu-id="fae29-124">Version contains the version number of the installed .NET Framework redistributable.</span></span> <span data-ttu-id="fae29-125">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fae29-125">For example:</span></span>  
  
```  
C:\Windows\Microsoft.NET\Framework\v2.0.31113  
```  
  
 <span data-ttu-id="fae29-126">Dopo avere aggiunto la directory di .NET Framework al percorso, è possibile compilare la stored procedure di esempio in un assembly con il comando indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fae29-126">Once you have added the .NET Framework directory to your path, you can compile the sample stored procedure into an assembly with the following command.</span></span> <span data-ttu-id="fae29-127">L'opzione `/target` consente di compilare la stored procedure in un assembly.</span><span class="sxs-lookup"><span data-stu-id="fae29-127">The `/target` option allows you to compile it into an assembly.</span></span>  
  
 <span data-ttu-id="fae29-128">Per i file di origine di Visual C#:</span><span class="sxs-lookup"><span data-stu-id="fae29-128">For Visual C# source files:</span></span>  
  
```  
csc /target:library helloworld.cs   
```  
  
 <span data-ttu-id="fae29-129">Per i file di origine di Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="fae29-129">For Visual Basic source files:</span></span>  
  
```  
vbc /target:library helloworld.vb  
```  
  
 <span data-ttu-id="fae29-130">Questi comandi consentono di avviare il compilatore Visual C# o Visual Basic utilizzando l'opzione /target per specificare la compilazione di una DLL della libreria.</span><span class="sxs-lookup"><span data-stu-id="fae29-130">These commands launch the Visual C# or Visual Basic compiler using the /target option to specify building a library DLL.</span></span>  
  
## <a name="loading-and-running-the-hello-world-stored-procedure-in-sql-server"></a><span data-ttu-id="fae29-131">Caricamento ed esecuzione della stored procedure "Hello World" in SQL Server</span><span class="sxs-lookup"><span data-stu-id="fae29-131">Loading and Running the "Hello World" Stored Procedure in SQL Server</span></span>  
 <span data-ttu-id="fae29-132">Una volta completata la compilazione della procedura di esempio, è possibile eseguirne il test in [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] e creare una nuova query, connettendosi a un database di prova appropriato, ad esempio il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="fae29-132">Once the sample procedure has successfully compiled, you can test it in [!INCLUDE[ssNoVersion](../../../includes/ssmanstudiofull-md.md)] and create a new query, connecting to a suitable test database (for example, the AdventureWorks sample database).</span></span>  
  
 <span data-ttu-id="fae29-133">L'esecuzione di codice CLR (Common Language Runtime) in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è disattivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fae29-133">The ability to execute common language runtime (CLR) code is set to OFF by default in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fae29-134">Il codice CLR può essere abilitato usando il **sp_configure** stored procedure di sistema.</span><span class="sxs-lookup"><span data-stu-id="fae29-134">The CLR code can be enabled by using the **sp_configure** system stored procedure.</span></span> <span data-ttu-id="fae29-135">Per altre informazioni, vedere [Enabling CLR Integration](../clr-integration-enabling.md).</span><span class="sxs-lookup"><span data-stu-id="fae29-135">For more information, see [Enabling CLR Integration](../clr-integration-enabling.md).</span></span>  
  
 <span data-ttu-id="fae29-136">A questo punto è necessario creare l'assembly per poter accedere alla stored procedure.</span><span class="sxs-lookup"><span data-stu-id="fae29-136">We will need to create the assembly so we can access the stored procedure.</span></span> <span data-ttu-id="fae29-137">Ai fini dell'esempio, si presuppone che sia stato creato l'assembly helloworld.dll nella directory C:\.</span><span class="sxs-lookup"><span data-stu-id="fae29-137">For this example, we will assume that you have created the helloworld.dll assembly in the C:\ directory.</span></span> <span data-ttu-id="fae29-138">Aggiungere l'istruzione [!INCLUDE[tsql](../../../includes/tsql-md.md)] seguente alla query:</span><span class="sxs-lookup"><span data-stu-id="fae29-138">Add the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement to your query.</span></span>  
  
```  
CREATE ASSEMBLY helloworld from 'c:\helloworld.dll' WITH PERMISSION_SET = SAFE  
```  
  
 <span data-ttu-id="fae29-139">Dopo avere creato l'assembly, è possibile accedere al metodo HelloWorld utilizzando l'istruzione CREATE PROCEDURE.</span><span class="sxs-lookup"><span data-stu-id="fae29-139">Once the assembly has been created, we can now access our HelloWorld method by using the create procedure statement.</span></span> <span data-ttu-id="fae29-140">La stored procedure verrà denominata "hello":</span><span class="sxs-lookup"><span data-stu-id="fae29-140">We will call our stored procedure "hello":</span></span>  
  
```  
  
CREATE PROCEDURE hello  
@i nchar(25) OUTPUT  
AS  
EXTERNAL NAME helloworld.HelloWorldProc.HelloWorld  
-- if the HelloWorldProc class is inside a namespace (called MyNS),  
-- the last line in the create procedure statement would be  
-- EXTERNAL NAME helloworld.[MyNS.HelloWorldProc].HelloWorld  
```  
  
 <span data-ttu-id="fae29-141">Una volta creata, la stored procedure può essere eseguita come una normale stored procedure scritta in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fae29-141">Once the procedure has been created, it can be run just like a normal stored procedure written in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span> <span data-ttu-id="fae29-142">Eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="fae29-142">Execute the following command:</span></span>  
  
```  
DECLARE @J nchar(25)  
EXEC hello @J out  
PRINT @J  
```  
  
 <span data-ttu-id="fae29-143">Verrà restituito l'output seguente nella finestra dei messaggi di [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fae29-143">This should result in the following output in the [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] messages window.</span></span>  
  
```  
Hello world!  
Hello world!  
```  
  
## <a name="removing-the-hello-world-stored-procedure-sample"></a><span data-ttu-id="fae29-144">Rimozione della stored procedure "Hello World" di esempio</span><span class="sxs-lookup"><span data-stu-id="fae29-144">Removing the "Hello World" Stored Procedure Sample</span></span>  
 <span data-ttu-id="fae29-145">Al termine dell'esecuzione della stored procedure di esempio, è possibile rimuovere la procedura e l'assembly dal database di test.</span><span class="sxs-lookup"><span data-stu-id="fae29-145">When you are finished running the sample stored procedure, you can remove the procedure and the assembly from your test database.</span></span>  
  
 <span data-ttu-id="fae29-146">Rimuovere innanzitutto la procedura utilizzando il comando drop procedure.</span><span class="sxs-lookup"><span data-stu-id="fae29-146">First, remove the procedure using the drop procedure command.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'hello')  
   drop procedure hello  
```  
  
 <span data-ttu-id="fae29-147">Dopo avere eliminato la procedura, è possibile rimuovere l'assembly contenente il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="fae29-147">Once the procedure has been dropped, you can remove the assembly containing your sample code.</span></span>  
  
```  
IF EXISTS (SELECT name FROM sys.assemblies WHERE name = 'helloworld')  
   drop assembly helloworld  
```  
  
## <a name="see-also"></a><span data-ttu-id="fae29-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fae29-148">See Also</span></span>  
 <span data-ttu-id="fae29-149">[Stored procedure CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fae29-149">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 <span data-ttu-id="fae29-150">[SQL Server estensioni specifiche in-process per ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span><span class="sxs-lookup"><span data-stu-id="fae29-150">[SQL Server In-Process Specific Extensions to ADO.NET](../../clr-integration-data-access-in-process-ado-net/sql-server-in-process-specific-extensions-to-ado-net.md) </span></span>  
 <span data-ttu-id="fae29-151">[Debug di oggetti di database CLR](../debugging-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="fae29-151">[Debugging CLR Database Objects](../debugging-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="fae29-152">Sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="fae29-152">CLR Integration Security</span></span>](../security/clr-integration-security.md)  
  
  
