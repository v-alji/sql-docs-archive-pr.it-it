---
title: Metodi di chiamata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- methods [SMO]
- calling methods
- SQL Server Management Objects, method calling
- SMO [SQL Server], method calling
ms.assetid: c88d5c5f-9ff0-4f84-b2b6-24c6b90fa15e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 13216b4c533527d4249471073580d7c86f6b07e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719805"
---
# <a name="calling-methods"></a><span data-ttu-id="b39c1-102">Chiamata di metodi</span><span class="sxs-lookup"><span data-stu-id="b39c1-102">Calling Methods</span></span>
  <span data-ttu-id="b39c1-103">I metodi eseguono attività specifiche correlate all'oggetto, ad esempio l'emissione di un oggetto `Checkpoint` in un database o la richiesta di un elenco enumerato di accessi per l'istanza di [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b39c1-103">Methods perform specific tasks related to the object, such as issuing a `Checkpoint` on a database or requesting an enumerated list of logons for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b39c1-104">I metodi eseguono un'operazione su un oggetto.</span><span class="sxs-lookup"><span data-stu-id="b39c1-104">Methods perform an operation on an object.</span></span> <span data-ttu-id="b39c1-105">I metodi possono accettare parametri e spesso restituiscono un valore.</span><span class="sxs-lookup"><span data-stu-id="b39c1-105">Methods can take parameters and often have a return value.</span></span> <span data-ttu-id="b39c1-106">Il valore restituito può essere un tipo di dati semplice, un oggetto complesso o una struttura che contiene molti membri.</span><span class="sxs-lookup"><span data-stu-id="b39c1-106">The return value can be a simple data type, a complex object, or a structure that contains many members.</span></span>  
  
 <span data-ttu-id="b39c1-107">Utilizzare la gestione delle eccezioni per determinare se il metodo è stato eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b39c1-107">Use exception handling to detect whether the method has been successful.</span></span> <span data-ttu-id="b39c1-108">Per altre informazioni, vedere [Handling SMO Exceptions](handling-smo-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="b39c1-108">For more information, see [Handling SMO Exceptions](handling-smo-exceptions.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b39c1-109">Esempi</span><span class="sxs-lookup"><span data-stu-id="b39c1-109">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="using-a-simple-smo-method-in-visual-basic"></a><span data-ttu-id="b39c1-110">Utilizzo di un metodo SMO semplice in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b39c1-110">Using a Simple SMO Method in Visual Basic</span></span>  
 <span data-ttu-id="b39c1-111">In questo esempio il metodo <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> non accetta parametri e non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="b39c1-111">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods1](SMO How to#SMO_VBMethods1)]  -->  
  
## <a name="using-a-simple-smo-method-in-visual-c"></a><span data-ttu-id="b39c1-112">Utilizzo di un metodo SMO semplice in Visual C#</span><span class="sxs-lookup"><span data-stu-id="b39c1-112">Using a Simple SMO Method in Visual C#</span></span>  
 <span data-ttu-id="b39c1-113">In questo esempio il metodo <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> non accetta parametri e non restituisce alcun valore.</span><span class="sxs-lookup"><span data-stu-id="b39c1-113">In this example, the <xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> method takes no parameters and has no return value.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define a Database object variable by supplying the parent server and the database name arguments in the constructor.   
Database db;   
db = new Database(srv, "Test_SMO_Database");   
//Call the Create method to create the database on the instance of SQL Server.   
db.Create();   
```  
  
 <span data-ttu-id="b39c1-114">}</span><span class="sxs-lookup"><span data-stu-id="b39c1-114">}</span></span>  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-basic"></a><span data-ttu-id="b39c1-115">Utilizzo di un metodo SMO con un parametro in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b39c1-115">Using an SMO Method with a Parameter in Visual Basic</span></span>  
 <span data-ttu-id="b39c1-116">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Table> include un metodo denominato <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="b39c1-116">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="b39c1-117">Questo metodo richiede un parametro numerico che specifica `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="b39c1-117">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
Dim srv As Server  
srv = New Server  
Dim tb As Table  
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources")  
tb.RebuildIndexes(70)  
```  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-c"></a><span data-ttu-id="b39c1-118">Utilizzo di un metodo SMO con un parametro in Visual C#</span><span class="sxs-lookup"><span data-stu-id="b39c1-118">Using an SMO Method with a Parameter in Visual C#</span></span>  
 <span data-ttu-id="b39c1-119">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Table> include un metodo denominato <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span><span class="sxs-lookup"><span data-stu-id="b39c1-119">The <xref:Microsoft.SqlServer.Management.Smo.Table> object has a method called <xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>.</span></span> <span data-ttu-id="b39c1-120">Questo metodo richiede un parametro numerico che specifica `FillFactor`.</span><span class="sxs-lookup"><span data-stu-id="b39c1-120">This method requires a numeric parameter that specifies the `FillFactor`.</span></span>  
  
```  
{   
Server srv = default(Server);   
srv = new Server();   
Table tb = default(Table);   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
}   
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-basic"></a><span data-ttu-id="b39c1-121">Utilizzo di un metodo di enumerazione che restituisce un oggetto DataTable in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b39c1-121">Using an Enumeration Method that Returns a DataTable Object in Visual Basic</span></span>  
 <span data-ttu-id="b39c1-122">In questa sezione viene descritto come chiamare un metodo di enumerazione e come gestire i dati nell'oggetto <xref:System.Data.DataTable> restituito.</span><span class="sxs-lookup"><span data-stu-id="b39c1-122">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="b39c1-123">Il metodo <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> restituisce un oggetto <xref:System.Data.DataTable>, che richiede ulteriore navigazione per accedere a tutte le informazioni sulle regole di confronto disponibili relative all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b39c1-123">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a <xref:System.Data.DataTable> object, which requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
'Connect to the local, default instance of SQL Server.  
Dim srv As Server  
srv = New Server  
'Call the EnumCollations method and return collation information to DataTable variable.  
Dim d As DataTable  
'Select the returned data into an array of DataRow.  
d = srv.EnumCollations  
'Iterate through the rows and display collation details for the instance of SQL Server.  
Dim r As DataRow  
Dim c As DataColumn  
For Each r In d.Rows  
    Console.WriteLine("==")  
    For Each c In r.Table.Columns  
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)  
    Next  
Next  
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-c"></a><span data-ttu-id="b39c1-124">Utilizzo di un metodo di enumerazione che restituisce un oggetto DataTable in Visual C#</span><span class="sxs-lookup"><span data-stu-id="b39c1-124">Using an Enumeration Method that Returns a DataTable Object in Visual C#</span></span>  
 <span data-ttu-id="b39c1-125">In questa sezione viene descritto come chiamare un metodo di enumerazione e come gestire i dati nell'oggetto <xref:System.Data.DataTable> restituito.</span><span class="sxs-lookup"><span data-stu-id="b39c1-125">This section describes how to call an enumeration method and how to handle the data in the returned <xref:System.Data.DataTable> object.</span></span>  
  
 <span data-ttu-id="b39c1-126">Il metodo <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> restituisce un oggetto <xref:System.Data.DataTable> di sistema.</span><span class="sxs-lookup"><span data-stu-id="b39c1-126">The <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> method returns a system <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="b39c1-127">L'oggetto <xref:System.Data.DataTable> richiede ulteriore navigazione per accedere a tutte le informazioni sulle regole di confronto disponibili relative all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b39c1-127">The <xref:System.Data.DataTable> object requires further navigation to access all available collation information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumCollations;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=========");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="constructing-an-object-in-visual-basic"></a><span data-ttu-id="b39c1-128">Costruzione di un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b39c1-128">Constructing an Object in Visual Basic</span></span>  
 <span data-ttu-id="b39c1-129">È possibile chiamare il costruttore di qualsiasi oggetto utilizzando l'operatore `New`.</span><span class="sxs-lookup"><span data-stu-id="b39c1-129">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="b39c1-130">Viene eseguito l'overload del costruttore dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> e la versione del costruttore dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> usata nell'esempio accetta due parametri: l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> padre cui appartiene il database e una stringa che rappresenta il nome del nuovo database.</span><span class="sxs-lookup"><span data-stu-id="b39c1-130">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods4](SMO How to#SMO_VBMethods4)]  -->  
  
## <a name="constructing-an-object-in-visual-c"></a><span data-ttu-id="b39c1-131">Costruzione di un oggetto in Visual C#</span><span class="sxs-lookup"><span data-stu-id="b39c1-131">Constructing an Object in Visual C#</span></span>  
 <span data-ttu-id="b39c1-132">È possibile chiamare il costruttore di qualsiasi oggetto utilizzando l'operatore `New`.</span><span class="sxs-lookup"><span data-stu-id="b39c1-132">The constructor of any object can be called by using the `New` operator.</span></span> <span data-ttu-id="b39c1-133">Viene eseguito l'overload del costruttore dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> e la versione del costruttore dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> usata nell'esempio accetta due parametri: l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> padre cui appartiene il database e una stringa che rappresenta il nome del nuovo database.</span><span class="sxs-lookup"><span data-stu-id="b39c1-133">The <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor is overloaded and the version of the <xref:Microsoft.SqlServer.Management.Smo.Database> object constructor that is used in the sample takes two parameters: the parent <xref:Microsoft.SqlServer.Management.Smo.Server> object to which the database belongs, and a string that represents the name of the new database.</span></span>  
  
```  
{   
Server srv;   
srv = new Server();   
Table tb;   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.   
Database d;   
d = new Database(srv, "Test_SMO_Database");   
//Create the database on the instance of SQL Server.   
d.Create();   
Console.WriteLine(d.Name);   
}  
```  
  
## <a name="copying-an-smo-object-in-visual-basic"></a><span data-ttu-id="b39c1-134">Copia di un oggetto SMO in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b39c1-134">Copying an SMO Object in Visual Basic</span></span>  
 <span data-ttu-id="b39c1-135">In questo esempio di codice viene utilizzato il metodo <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> per creare una copia dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="b39c1-135">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="b39c1-136">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> rappresenta una connessione a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b39c1-136">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VCMethods6](SMO How to#SMO_VCMethods6)]  -->  
  
## <a name="copying-an-smo-object-in-visual-c"></a><span data-ttu-id="b39c1-137">Copia di un oggetto SMO in Visual C#</span><span class="sxs-lookup"><span data-stu-id="b39c1-137">Copying an SMO Object in Visual C#</span></span>  
 <span data-ttu-id="b39c1-138">In questo esempio di codice viene utilizzato il metodo <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> per creare una copia dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="b39c1-138">This code example uses the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A> method to create a copy of the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span> <span data-ttu-id="b39c1-139">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Server> rappresenta una connessione a un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b39c1-139">The <xref:Microsoft.SqlServer.Management.Smo.Server> object represents a connection to an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv1;   
srv1 = new Server();   
//Modify the default database and the timeout period for the connection.   
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012";   
srv1.ConnectionContext.ConnectTimeout = 30;   
//Make a second connection using a copy of the ConnectionContext property and verify settings.   
Server srv2;   
srv2 = new Server(srv1.ConnectionContext.Copy);   
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString);   
}  
```  
  
## <a name="monitoring-server-processes-in-visual-basic"></a><span data-ttu-id="b39c1-140">Monitoraggio di processi server in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b39c1-140">Monitoring Server Processes in Visual Basic</span></span>  
 <span data-ttu-id="b39c1-141">È possibile ottenere le informazioni sul tipo di stato corrente relative all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando metodi di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b39c1-141">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="b39c1-142">Nell'esempio di codice viene utilizzato il metodo <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> per individuare informazioni sui processi correnti.</span><span class="sxs-lookup"><span data-stu-id="b39c1-142">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="b39c1-143">Viene inoltre illustrato come utilizzare le colonne e le righe nell'oggetto <xref:System.Data.DataTable> restituito.</span><span class="sxs-lookup"><span data-stu-id="b39c1-143">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMethods5](SMO How to#SMO_VBMethods5)]  -->  
  
## <a name="monitoring-server-processes-in-visual-c"></a><span data-ttu-id="b39c1-144">Monitoraggio di processi server in Visual C#</span><span class="sxs-lookup"><span data-stu-id="b39c1-144">Monitoring Server Processes in Visual C#</span></span>  
 <span data-ttu-id="b39c1-145">È possibile ottenere le informazioni sul tipo di stato corrente relative all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando metodi di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="b39c1-145">You can obtain the current status type information about the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] through enumeration methods.</span></span> <span data-ttu-id="b39c1-146">Nell'esempio di codice viene utilizzato il metodo <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> per individuare informazioni sui processi correnti.</span><span class="sxs-lookup"><span data-stu-id="b39c1-146">The code example uses the <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> method to discover information about the current processes.</span></span> <span data-ttu-id="b39c1-147">Viene inoltre illustrato come utilizzare le colonne e le righe nell'oggetto <xref:System.Data.DataTable> restituito.</span><span class="sxs-lookup"><span data-stu-id="b39c1-147">It also demonstrates how to work with the columns and rows in the returned <xref:System.Data.DataTable> object.</span></span>  
  
```  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumProcesses;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=====");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="see-also"></a><span data-ttu-id="b39c1-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b39c1-148">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  
