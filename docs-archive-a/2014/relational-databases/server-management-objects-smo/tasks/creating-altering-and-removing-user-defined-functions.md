---
title: Creazione, modifica e rimozione di funzioni definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- user-defined functions [SMO]
ms.assetid: 0ebebd3b-0775-41c2-989d-aa4cf81af12a
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9ff6d1b6e675d41e96f26fc24e6e0dd4ba69454
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637190"
---
# <a name="creating-altering-and-removing-user-defined-functions"></a><span data-ttu-id="64af7-102">Creazione, modifica e rimozione delle funzioni definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="64af7-102">Creating, Altering, and Removing User-Defined Functions</span></span>
  <span data-ttu-id="64af7-103">L' <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> oggetto fornisce funzionalità che consentono agli utenti di gestire a livello di codice le funzioni definite dall'utente in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64af7-103">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object provides functionality that lets users programmatically manage user-defined functions in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="64af7-104">Le funzioni definite dall'utente supportano parametri di input e di output e riferimenti diretti alle colonne delle tabelle.</span><span class="sxs-lookup"><span data-stu-id="64af7-104">User-defined functions support input and output parameters, and also support direct references to table columns.</span></span>  
  
 <span data-ttu-id="64af7-105">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è necessario registrare gli assembly all'interno di un database prima di poterli utilizzare in stored procedure, funzioni definite dall'utente, trigger e tipi di dati definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="64af7-105">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requires assemblies to be registered within a database before these can be used inside stored procedures, user defined functions, triggers, and user defined data types.</span></span> <span data-ttu-id="64af7-106">In SMO questa funzionalità è supportata con l'oggetto <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly>.</span><span class="sxs-lookup"><span data-stu-id="64af7-106">SMO supports this feature with the <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object.</span></span>  
  
 <span data-ttu-id="64af7-107">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> fa riferimento all'assembly .NET con le proprietà <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A> e <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A>.</span><span class="sxs-lookup"><span data-stu-id="64af7-107">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references the .NET assembly with the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.AssemblyName%2A>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.ClassName%2A>, and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction.MethodName%2A> properties.</span></span>  
  
 <span data-ttu-id="64af7-108">Quando l'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> fa riferimento a un assembly .NET, è necessario registrare l'assembly creando un oggetto <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> e aggiungendolo all'oggetto <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection> che appartiene all'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database>.</span><span class="sxs-lookup"><span data-stu-id="64af7-108">When the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction> object references a .NET assembly, you must register the assembly by creating a <xref:Microsoft.SqlServer.Management.Smo.SqlAssembly> object and adding it to the <xref:Microsoft.SqlServer.Management.Smo.SqlAssemblyCollection> object, which belongs to the <xref:Microsoft.SqlServer.Management.Smo.Database> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64af7-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="64af7-109">Example</span></span>  
 <span data-ttu-id="64af7-110">Per usare qualsiasi esempio di codice fornito, è necessario scegliere l'ambiente di programmazione, il modello di programmazione e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="64af7-110">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="64af7-111">Per ulteriori informazioni, vedere [creare un Visual Basic progetto SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) o [creare un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="64af7-111">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) or [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-basic"></a><span data-ttu-id="64af7-112">Creazione di una funzione scalare definita dall'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="64af7-112">Creating a Scalar User-Defined Function in Visual Basic</span></span>  
 <span data-ttu-id="64af7-113">In questo esempio di codice viene illustrato come creare e rimuovere una funzione scalare definita dall'utente con un parametro dell'oggetto <xref:System.DateTime> di input e un tipo restituito integer in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64af7-113">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span></span> <span data-ttu-id="64af7-114">La funzione definita dall'utente viene creata nel database [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64af7-114">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="64af7-115">Nell'esempio viene creata una funzione definita dall'utente, ISOweek, che accetta un argomento data per calcolare il numero di settimana ISO.</span><span class="sxs-lookup"><span data-stu-id="64af7-115">The example creates a user-defined function, ISOweek, which takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="64af7-116">Affinché il calcolo venga eseguito correttamente, è necessario impostare l'opzione DATEFIRST del database su 1 prima di chiamare la funzione.</span><span class="sxs-lookup"><span data-stu-id="64af7-116">For this function to calculate correctly, the database DATEFIRST option must be set to 1 before the function is called.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBUserDefFuncs1](SMO How to#SMO_VBUserDefFuncs1)]  -->  
  
## <a name="creating-a-scalar-user-defined-function-in-visual-c"></a><span data-ttu-id="64af7-117">Creazione di una funzione scalare definita dall'utente in Visual C#</span><span class="sxs-lookup"><span data-stu-id="64af7-117">Creating a Scalar User-Defined Function in Visual C#</span></span>  
 <span data-ttu-id="64af7-118">In questo esempio di codice viene illustrato come creare e rimuovere una funzione scalare definita dall'utente con un parametro dell'oggetto <xref:System.DateTime> di input e un tipo restituito integer in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64af7-118">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="64af7-119">La funzione definita dall'utente viene creata nel database [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64af7-119">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="64af7-120">Nell'esempio viene creata la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="64af7-120">The example creates the user-defined function.</span></span> <span data-ttu-id="64af7-121">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="64af7-121">`ISOweek`.</span></span> <span data-ttu-id="64af7-122">Questa funzione calcola il numero di settimana ISO in base a un argomento di data specificato.</span><span class="sxs-lookup"><span data-stu-id="64af7-122">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="64af7-123">Affinché il calcolo venga eseguito correttamente, è necessario impostare l'opzione `DATEFIRST` del database su `1` prima di chiamare la funzione.</span><span class="sxs-lookup"><span data-stu-id="64af7-123">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
           Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
           Database db = srv.Databases["AdventureWorks2012"];  
  
            //Define a UserDefinedFunction object variable by supplying the parent database and the name arguments in the constructor.   
            UserDefinedFunction udf = new UserDefinedFunction(db, "IsOWeek");  
  
            //Set the TextMode property to false and then set the other properties.   
            udf.TextMode = false;  
            udf.DataType = DataType.Int;  
            udf.ExecutionContext = ExecutionContext.Caller;  
            udf.FunctionType = UserDefinedFunctionType.Scalar;  
            udf.ImplementationType = ImplementationType.TransactSql;  
  
            //Add a parameter.   
  
     UserDefinedFunctionParameter par = new UserDefinedFunctionParameter(udf, "@DATE", DataType.DateTime);  
            udf.Parameters.Add(par);  
  
            //Set the TextBody property to define the user-defined function.   
            udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;";  
  
            //Create the user-defined function on the instance of SQL Server.   
            udf.Create();  
  
            //Remove the user-defined function.   
            udf.Drop();  
        }  
```  
  
## <a name="creating-a-scalar-user-defined-function-in-powershell"></a><span data-ttu-id="64af7-124">Creazione di una funzione scalare definita dall'utente in PowerShell</span><span class="sxs-lookup"><span data-stu-id="64af7-124">Creating a Scalar User-Defined Function in PowerShell</span></span>  
 <span data-ttu-id="64af7-125">In questo esempio di codice viene illustrato come creare e rimuovere una funzione scalare definita dall'utente con un parametro dell'oggetto <xref:System.DateTime> di input e un tipo restituito integer in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64af7-125">This code example shows how to create and remove a scalar user-defined function that has an input <xref:System.DateTime> object parameter and an integer return type in [!INCLUDE[csprcs](../../../includes/csprcs-md.md)].</span></span> <span data-ttu-id="64af7-126">La funzione definita dall'utente viene creata nel database [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64af7-126">The user-defined function is created on the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] database.</span></span> <span data-ttu-id="64af7-127">Nell'esempio viene creata la funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="64af7-127">The example creates the user-defined function.</span></span> <span data-ttu-id="64af7-128">`ISOweek`.</span><span class="sxs-lookup"><span data-stu-id="64af7-128">`ISOweek`.</span></span> <span data-ttu-id="64af7-129">Questa funzione calcola il numero di settimana ISO in base a un argomento di data specificato.</span><span class="sxs-lookup"><span data-stu-id="64af7-129">This function takes a date argument and calculates the ISO week number.</span></span> <span data-ttu-id="64af7-130">Affinché il calcolo venga eseguito correttamente, è necessario impostare l'opzione `DATEFIRST` del database su `1` prima di chiamare la funzione.</span><span class="sxs-lookup"><span data-stu-id="64af7-130">For this function to calculate correctly, the database `DATEFIRST` option must be set to `1` before the function is called.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
# Define a user defined function object variable by supplying the parent database and name arguments in the constructor.
$udf  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunction -argumentlist $db, "IsOWeek"  
  
# Set the TextMode property to false and then set the other properties.
$udf.TextMode = $false  
$udf.DataType = [Microsoft.SqlServer.Management.SMO.DataType]::Int
$udf.ExecutionContext = [Microsoft.SqlServer.Management.SMO.ExecutionContext]::Caller  
$udf.FunctionType = [Microsoft.SqlServer.Management.SMO.UserDefinedFunctionType]::Scalar  
$udf.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
  
# Define a Parameter object variable by supplying the parent function, name and type arguments in the constructor.  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$par  = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunctionParameter -argumentlist $udf, "@DATE",$type  
  
# Add the parameter to the function  
$udf.Parameters.Add($par)  
  
#Set the TextBody property to define the user-defined function.
$udf.TextBody = "BEGIN DECLARE @ISOweek int SET @ISOweek= DATEPART(wk,@DATE)+1 -DATEPART(wk,CAST(DATEPART(yy,@DATE) as CHAR(4))+'0104') IF (@ISOweek=0) SET @ISOweek=dbo.ISOweek(CAST(DATEPART(yy,@DATE)-1 AS CHAR(4))+'12'+ CAST(24+DATEPART(DAY,@DATE) AS CHAR(2)))+1 IF ((DATEPART(mm,@DATE)=12) AND ((DATEPART(dd,@DATE)-DATEPART(dw,@DATE))>= 28)) SET @ISOweek=1 RETURN(@ISOweek) END;"  
  
# Create the user-defined function on the instance of SQL Server.
$udf.Create()  
  
# Remove the user-defined function.
$udf.Drop()  
```  
  
## <a name="see-also"></a><span data-ttu-id="64af7-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64af7-131">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunction>  
