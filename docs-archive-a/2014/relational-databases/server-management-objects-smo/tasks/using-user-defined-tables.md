---
title: Utilizzo di tabelle definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- user-defined tables [SQL Server]
ms.assetid: 620a4e1f-9678-4711-ae09-bcf7c9cae724
author: stevestein
ms.author: sstein
ms.openlocfilehash: 869bff26dc6801a6844e31b11322eb43515f3eac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725360"
---
# <a name="using-user-defined-tables"></a><span data-ttu-id="c3d62-102">Utilizzo di tabelle definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="c3d62-102">Using User-Defined Tables</span></span>
  <span data-ttu-id="c3d62-103">Le tabelle definite dall'utente rappresentano informazioni tabulari.</span><span class="sxs-lookup"><span data-stu-id="c3d62-103">User-defined tables represent tabular information.</span></span> <span data-ttu-id="c3d62-104">Vengono utilizzate come parametri quando si passano dati tabulari in stored procedure o funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d62-104">They are used as parameters when you pass tabular data into stored procedures or user-defined functions.</span></span> <span data-ttu-id="c3d62-105">Non è possibile utilizzare le tabelle definite dall'utente per rappresentare le colonne di una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="c3d62-105">User-defined tables cannot be used to represent columns in a database table.</span></span>  
  
 <span data-ttu-id="c3d62-106">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> dispone di una proprietà <xref:Microsoft.SqlServer.Management.Smo.Database.UserDefinedTableTypes%2A> che fa riferimento a un oggetto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableTypeCollection>.</span><span class="sxs-lookup"><span data-stu-id="c3d62-106">The <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.Database.UserDefinedTableTypes%2A> property that references a <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableTypeCollection> object.</span></span> <span data-ttu-id="c3d62-107">Ogni <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> oggetto nella raccolta dispone di una proprietà **Columns** che fa riferimento a una raccolta di <xref:Microsoft.SqlServer.Management.Smo.Column> oggetti in cui sono elencate le colonne della tabella definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d62-107">Each <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> object in that collection has a **Columns** property that refers to a collection of <xref:Microsoft.SqlServer.Management.Smo.Column> objects that list the columns in the user-defined table.</span></span> <span data-ttu-id="c3d62-108">Utilizzare il metodo Add per aggiungere colonne alla tabella definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d62-108">Use the Add method to add columns to the user-defined table.</span></span>  
  
 <span data-ttu-id="c3d62-109">Quando si definisce una nuova tabella definita dall'utente tramite l'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType>, è necessario fornire colonne e una chiave primaria basata su una delle colonne.</span><span class="sxs-lookup"><span data-stu-id="c3d62-109">When you define a new user-defined table by using the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> object, you will have to supply columns and a primary key based on one of the columns.</span></span>  
  
 <span data-ttu-id="c3d62-110">Dopo averli creati, non è più possibile modificare i tipi di tabella definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d62-110">User-defined table types cannot be altered after they are created.</span></span> <span data-ttu-id="c3d62-111"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> non supporta il metodo Alter.</span><span class="sxs-lookup"><span data-stu-id="c3d62-111">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedTableType> does not support the Alter method.</span></span> <span data-ttu-id="c3d62-112">I tipi di tabella definita dall'utente possono disporre di vincoli CHECK, ma alcune operazioni di controllo genereranno un'eccezione perché il tipo non è modificabile.</span><span class="sxs-lookup"><span data-stu-id="c3d62-112">User-defined table types can have check constraints, but some check operations will throw an exception because the type is not alterable.</span></span>  
  
 <span data-ttu-id="c3d62-113">La classe <xref:Microsoft.SqlServer.Management.Smo.DataType> consente di specificare il tipo di dati associato a colonne e parametri.</span><span class="sxs-lookup"><span data-stu-id="c3d62-113">The <xref:Microsoft.SqlServer.Management.Smo.DataType> class is used to specify the data type that is associated with columns and parameters.</span></span> <span data-ttu-id="c3d62-114">Utilizzare questo tipo per specificare il tipo di tabella definita dall'utente come parametro per stored procedure e funzioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d62-114">Use this type to specify the user-defined table type as a parameter for user-defined functions and stored procedures.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c3d62-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="c3d62-115">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="creating-a-user-defined-table-in-visual-basic"></a><span data-ttu-id="c3d62-116">Creazione di una tabella definita dall'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c3d62-116">Creating a User Defined Table in Visual Basic</span></span>  
 <span data-ttu-id="c3d62-117">Per questo esempio, è necessario includere un'istruzione Imports per la libreria di classi contenente il tipo `StringCollection`.</span><span class="sxs-lookup"><span data-stu-id="c3d62-117">For this example, you will have to include an imports statement for the class library that contains the `StringCollection` type.</span></span>  
  
 `Imports System.Collections.Specialized`  
  
 <span data-ttu-id="c3d62-118">Nell'esempio viene illustrato come creare una tabella definita dall'utente e successivamente come utilizzarla come parametro in una funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d62-118">The example demonstrates how to create a user-defined table, and then how to use it as a parameter in a user-defined function.</span></span>  
  
```vb
'Connect to the local, default instance of SQL Server  
        Dim srv As Server  
        srv = New Server  
        'Reference the AdventureWorks2012 database.  
        Dim db As Database  
        db = srv.Databases("AdventureWorks2012")  
        'Define a UserDefinedTableType object variable by supplying the 'database and name in the constructor.  
        Dim udtt As UserDefinedTableType  
        udtt = New UserDefinedTableType(db, "My_User_Defined_Table")  
        'Add three columns of different types to the  
        'UserDefinedTableType object.  
        udtt.Columns.Add(New Column(udtt, "Col1", DataType.Int))  
        udtt.Columns.Add(New Column(udtt, "Col2", DataType.VarCharMax))  
        udtt.Columns.Add(New Column(udtt, "Col3", DataType.Money))  
        'Define an Index object variable by supplying the user-defined  
        'table variable and name in the constructor.  
        Dim idx As Index  
        idx = New Index(udtt, "PK_UddtTable")  
        'Add the first column in the user-defined table as  
        'the indexed column.  
        idx.IndexedColumns.Add(New IndexedColumn(idx, "Col1"))  
        'Specify that the index is a clustered, unique, primary key.  
        idx.IsClustered = True  
        idx.IsUnique = True  
        idx.IndexKeyType = IndexKeyType.DriPrimaryKey  
        udtt.Indexes.Add(idx)  
        'Add the index and create the user-defined table.  
        udtt.Create()  
        'Display the Transact-SQL creation script for the  
        'user-defined table.  
        Dim sc As StringCollection  
        sc = udtt.Script()  
        For Each c As String In sc  
            Console.WriteLine(c)  
        Next  
  
        'Define a new user-defined function with a single parameter.  
        Dim udf As UserDefinedFunction  
        udf = New UserDefinedFunction(db, "My_User_Defined_Function")  
        udf.TextMode = False  
        udf.FunctionType = UserDefinedFunctionType.Scalar  
        udf.ImplementationType = ImplementationType.TransactSql  
        udf.DataType = DataType.DateTime  
        'Specify the parameter as a UserDefinedTableTable object.  
        Dim udfp As UserDefinedFunctionParameter  
        udfp = New UserDefinedFunctionParameter(udf, "@param")  
        udfp.DataType = New DataType(udtt)  
        udfp.IsReadOnly = True  
        udf.Parameters.Add(udfp)  
        'Specify the TextBody property to the Transact-SQL definition of the  
        'user-defined function.  
        udf.TextBody = "BEGIN RETURN (GETDATE());end"  
        'Create the user-defined function.  
        udf.Create()  
```  
  
## <a name="creating-a-user-defined-table-in-visual-c"></a><span data-ttu-id="c3d62-119">Creazione di una tabella definita dall'utente in Visual C#</span><span class="sxs-lookup"><span data-stu-id="c3d62-119">Creating a User Defined Table in Visual C#</span></span>  
 <span data-ttu-id="c3d62-120">Per questo esempio, è necessario includere un'istruzione Imports per la libreria di classi contenente il tipo `StringCollection`.</span><span class="sxs-lookup"><span data-stu-id="c3d62-120">For this example, you will have to include an imports statement for the class library that contains the `StringCollection` type.</span></span>  
  
 `using System.Collections.Specialized;`  
  
 <span data-ttu-id="c3d62-121">Nell'esempio viene illustrato come creare una tabella definita dall'utente e come utilizzarla quindi come parametro in una funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d62-121">The example shows how to create a user-defined table, and then how to use it as a parameter in a user-defined function.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server   
               Server srv = new Server();  
  
            //Reference the AdventureWorks2012 database.   
            Database db = srv.Databases["AdventureWorks2012"];  
            //Define a UserDefinedTableType object variable by supplying the  
            //database and name in the constructor.   
         UserDefinedTableType udtt = new UserDefinedTableType(db, "My_User_Defined_Table");  
  
            //Add three columns of different types to the   
            //UserDefinedTableType object.   
         udtt.Columns.Add(new Column(udtt, "Col1", DataType.Int));  
         udtt.Columns.Add(new Column(udtt, "Col2", DataType.VarCharMax));  
         udtt.Columns.Add(new Column(udtt, "Col3", DataType.Money));  
  
            //Define an Index object variable by supplying the user-defined   
            //table variable and name in the constructor.   
  
            Index idx = new Index(udtt, "PK_UddtTable");  
  
            //Add the first column in the user-defined table as   
            //the indexed column.   
            idx.IndexedColumns.Add(new IndexedColumn(idx, "Col1"));  
            //Specify that the index is a clustered, unique, primary key.   
            idx.IsClustered = true;  
            idx.IsUnique = true;  
            idx.IndexKeyType = IndexKeyType.DriPrimaryKey;  
            udtt.Indexes.Add(idx);  
            //Add the index and create the user-defined table.   
            udtt.Create();  
  
            //Display the Transact-SQL creation script for the   
            //user-defined table.   
            System.Collections.Specialized.StringCollection sc;  
            sc = udtt.Script();  
            foreach (string s in sc)  
            {  
                Console.WriteLine(s);  
            }  
  
            //Define a new user-defined function with a single parameter.  
            UserDefinedFunction udf = new UserDefinedFunction(db, "My_User_Defined_Function");  
            udf.TextMode = false;  
            udf.FunctionType = UserDefinedFunctionType.Scalar;  
            udf.ImplementationType = ImplementationType.TransactSql;  
            udf.DataType = DataType.DateTime;  
  
            //Specify the parameter as a UserDefinedTableTable object.  
             UserDefinedFunctionParameter udfp = new UserDefinedFunctionParameter(udf, "@param");  
            udfp.DataType = new DataType(udtt);  
            udfp.IsReadOnly = true;  
            udf.Parameters.Add(udfp);  
  
            //Specify the TextBody property to the Transact-SQL definition of the   
            //user-defined function.   
            udf.TextBody = "BEGIN RETURN (GETDATE());end";  
            //Create the user-defined function.   
            udf.Create();  
        }  
```  
  
## <a name="creating-a-user-defined-table-in-powershell"></a><span data-ttu-id="c3d62-122">Creazione di una tabella definita dall'utente in PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3d62-122">Creating a User Defined Table in PowerShell</span></span>  
 <span data-ttu-id="c3d62-123">Per questo esempio, è necessario includere un'istruzione Imports per la libreria di classi contenente il tipo `StringCollection`.</span><span class="sxs-lookup"><span data-stu-id="c3d62-123">For this example, you will have to include an imports statement for the class library that contains the `StringCollection` type.</span></span>  
  
 `using System.Collections.Specialized;`  
  
 <span data-ttu-id="c3d62-124">Nell'esempio viene illustrato come creare una tabella definita dall'utente e come utilizzarla quindi come parametro in una funzione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c3d62-124">The example shows how to create a user-defined table, and then how to use it as a parameter in a user-defined function.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server and get a reference to AdventureWorks2012  
CD \sql\localhost\default\databases  
$db = Get-Item Adventureworks2012  
  
#Define a UserDefinedTableType object variable by supplying the  
#database and name in the constructor.
$udtt = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedTableType -ArgumentList $db, "My_User_Defined_Table"  
  
#Add three columns of different types to the UserDefinedTableType object.  
  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::Int  
$col = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -ArgumentList $udtt, "col1", $type  
$udtt.Columns.Add($col)  
  
$type = [Microsoft.SqlServer.Management.SMO.DataType]::VarCharMax  
$col = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -ArgumentList $udtt, "col2", $type  
$udtt.Columns.Add($col)  
  
 $type = [Microsoft.SqlServer.Management.SMO.DataType]::Money  
$col = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Column -ArgumentList $udtt, "col3", $type  
$udtt.Columns.Add($col)
  
#Define an Index object variable by supplying the user-defined table variable and name in the constructor.
$idx = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Index `  
-argumentlist $udtt, "PK_UddtTable"  
  
#Add the first column in the user-defined table as the indexed column.
$idxcol = New-Object -TypeName Microsoft.SqlServer.Management.SMO.IndexedColumn `  
-argumentlist $idx, "Col1"  
$idx.IndexedColumns.Add($idxcol)  
  
#Specify that the index is a clustered, unique, primary key.
$idx.IsClustered = $true  
$idx.IsUnique = $true  
$idx.IndexKeyType = [Microsoft.SqlServer.Management.SMO.IndexKeyType]::DriPrimaryKey;  
  
#Add the index and create the user-defined table.
$udtt.Indexes.Add($idx)  
$udtt.Create();  
  
# Display the Transact-SQL creation script for the user-defined table.
$sc = $udtt.Script()  
$sc  
  
# Define a new user-defined function with a single parameter.
$udf = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunction -ArgumentList $db, "My_User_Defined_Function"  
$udf.TextMode = $false  
$udf.FunctionType = [Microsoft.SqlServer.Management.SMO.UserDefinedFunctionType]::Scalar  
$udf.ImplementationType = [Microsoft.SqlServer.Management.SMO.ImplementationType]::TransactSql  
$udf.DataType = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
  
# Specify the parameter as a UserDefinedTableTable object.  
$udfp = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedFunctionParameter -ArgumentList $udf, "@param"  
$type = New-Object -TypeName Microsoft.SqlServer.Management.SMO.DataType -ArgumentList $udtt  
$udfp.DataType = $type  
$udfp.IsReadOnly = $true  
$udf.Parameters.Add($udfp)  
  
# Specify the TextBody property to the Transact-SQL definition of the user-defined function.   
$udf.TextBody = "BEGIN RETURN (GETDATE());end"  
  
# Create the user-defined function.
$udf.Create()
```  
  
## <a name="see-also"></a><span data-ttu-id="c3d62-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3d62-125">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.FileGroup>   
 [<span data-ttu-id="c3d62-126">Filegroup e file di database</span><span class="sxs-lookup"><span data-stu-id="c3d62-126">Database Files and Filegroups</span></span>](../../databases/database-files-and-filegroups.md)  
