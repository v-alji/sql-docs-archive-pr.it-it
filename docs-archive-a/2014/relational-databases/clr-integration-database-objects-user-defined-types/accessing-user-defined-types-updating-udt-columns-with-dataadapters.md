---
title: Aggiornamento di colonne con tipo definito dall'utente con DataAdapter | Microsoft Docs
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
- ADO.NET [CLR integration]
- updating data [CLR integration]
- populating DataSet
- datasets [CLR integration]
- UDTs [CLR integration], ADO.NET
- updating UDT columns
- user-defined types [CLR integration], ADO.NET
- data adapters [CLR integration]
ms.assetid: 4489c938-ba03-4fdb-b533-cc3f5975ae50
author: rothja
ms.author: jroth
ms.openlocfilehash: 8b908db850b1b77216824a5225d9bd8874387f78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635087"
---
# <a name="updating-udt-columns-with-dataadapters"></a><span data-ttu-id="ce35b-102">Aggiornamento di colonne con tipo definito dall'utente con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="ce35b-102">Updating UDT Columns with DataAdapters</span></span>
  <span data-ttu-id="ce35b-103">Per la modifica e il recupero dei dati i tipi definiti dall'utente utilizzano `System.Data.DataSet` e `System.Data.SqlClient.SqlDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="ce35b-103">User-defined types (UDTs) are supported by using a `System.Data.DataSet` and a `System.Data.SqlClient.SqlDataAdapter` to retrieve and modify data.</span></span>  
  
## <a name="populating-a-dataset"></a><span data-ttu-id="ce35b-104">Popolamento di set di dati</span><span class="sxs-lookup"><span data-stu-id="ce35b-104">Populating a Dataset</span></span>  
 <span data-ttu-id="ce35b-105">È possibile utilizzare un'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT per selezionare i valori delle colonne con tipo definito dall'utente per popolare un set di dati utilizzando un adattatore dati.</span><span class="sxs-lookup"><span data-stu-id="ce35b-105">You can use a [!INCLUDE[tsql](../../includes/tsql-md.md)] SELECT statement to select UDT column values to populate a dataset using a data adapter.</span></span> <span data-ttu-id="ce35b-106">Nell'esempio seguente si presuppone che sia stata definita una tabella **Points** con la struttura seguente e alcuni dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="ce35b-106">The following example assumes that you have a **Points** table defined with the following structure and some sample data.</span></span> <span data-ttu-id="ce35b-107">Le [!INCLUDE[tsql](../../includes/tsql-md.md)] istruzioni seguenti creano la tabella **Points** e inseriscono alcune righe.</span><span class="sxs-lookup"><span data-stu-id="ce35b-107">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements create the **Points** table and insert a few rows.</span></span>  
  
```  
CREATE TABLE dbo.Points (id int PRIMARY Key, p Point);  
  
INSERT INTO dbo.Points VALUES (1, CONVERT(Point, '1,3'));  
INSERT INTO dbo.Points VALUES (2, CONVERT(Point, '2,4'));  
INSERT INTO dbo.Points VALUES (3, CONVERT(Point, '3,5'));  
INSERT INTO dbo.Points VALUES (4, CONVERT(Point, '4,6'));  
GO  
```  
  
 <span data-ttu-id="ce35b-108">Nel frammento di codice ADO.NET seguente viene recuperata una stringa di connessione valida, viene creato un nuovo oggetto `SqlDataAdapter` e viene popolato un oggetto `System.Data.DataTable` con le righe di dati della tabella **Points** .</span><span class="sxs-lookup"><span data-stu-id="ce35b-108">The following ADO.NET code fragment retrieves a valid connection string, creates a new `SqlDataAdapter`, and populates a `System.Data.DataTable` with the rows of data from the **Points** table.</span></span>  
  
```vb  
Dim da As New SqlDataAdapter( _  
    "SELECT id, p FROM dbo.Points", connectionString)  
Dim datTable As New DataTable("Points")  
da.Fill(datTable)  
```  
  
```csharp  
SqlDataAdapter da = new SqlDataAdapter(  
   "SELECT id, p FROM dbo.Points", connectionString);  
DataTable datTable = new DataTable("Points");  
da.Fill(datTable);  
```  
  
## <a name="updating-udt-data-in-a-dataset"></a><span data-ttu-id="ce35b-109">Aggiornamento dei dati dei tipi definiti dall'utente di un set di dati</span><span class="sxs-lookup"><span data-stu-id="ce35b-109">Updating UDT Data in a Dataset</span></span>  
 <span data-ttu-id="ce35b-110">È possibile utilizzare due metodi per aggiornare una colonna con tipo definito dall'utente in un `DataSet`:</span><span class="sxs-lookup"><span data-stu-id="ce35b-110">You can use two methods to update a UDT column in a `DataSet`:</span></span>  
  
-   <span data-ttu-id="ce35b-111">Fornire oggetti `InsertCommand`, `UpdateCommand` e `DeleteCommand` personalizzati per un oggetto `SqlDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="ce35b-111">Provide custom `InsertCommand`, `UpdateCommand` and `DeleteCommand` objects for a `SqlDataAdapter` object.</span></span>  
  
-   <span data-ttu-id="ce35b-112">Utilizzare il generatore comandi (`System.Data.SqlClient.SqlCommandBuilder`) per creare automaticamente i comandi INSERT, UPDATE e DELETE.</span><span class="sxs-lookup"><span data-stu-id="ce35b-112">Use the command builder (`System.Data.SqlClient.SqlCommandBuilder`) to create automatically the INSERT, UPDATE, and DELETE commands for you.</span></span> <span data-ttu-id="ce35b-113">Per abilitare il rilevamento dei conflitti, aggiungere una colonna `timestamp` (alias `rowversion`) alla tabella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che contiene il tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ce35b-113">In order to have conflict detection, add a `timestamp` column (alias `rowversion`) to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table that contains the UDT.</span></span> <span data-ttu-id="ce35b-114">Il tipo di dati `timestamp` consente di indicare la versione delle righe di una tabella. È garantita l'univocità all'interno di un database.</span><span class="sxs-lookup"><span data-stu-id="ce35b-114">The `timestamp` data type allows you to version-stamp the rows in a table, and is guaranteed to be unique within a database.</span></span> <span data-ttu-id="ce35b-115">Quando un valore della tabella viene modificato, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene automaticamente aggiornato il numero binario di otto byte per la riga interessata dalla modifica.</span><span class="sxs-lookup"><span data-stu-id="ce35b-115">When a value in the table is changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automatically updates the eight-byte binary number for the row affected by the change.</span></span>  
  
 <span data-ttu-id="ce35b-116">Si noti che `SqlCommandBuilder` non considera il tipo definito dall'utente per il rilevamento dei conflitti, a meno che non sia presente una colonna `timestamp` nella tabella sottostante.</span><span class="sxs-lookup"><span data-stu-id="ce35b-116">Note that the `SqlCommandBuilder` does not consider the UDT for conflict detection unless there is a `timestamp` column in the underlying table.</span></span> <span data-ttu-id="ce35b-117">Dal momento che non è certa la comparabilità dei tipi definiti dall'utente, essi non vengono inclusi nella clausola WHERE quando viene utilizzata l'opzione per il confronto dei valori originali per generare un comando.</span><span class="sxs-lookup"><span data-stu-id="ce35b-117">UDTs may or may not be comparable, so they are not included in the WHERE clause when the "compare original values" option is used to generate a command.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ce35b-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce35b-118">Example</span></span>  
 <span data-ttu-id="ce35b-119">Nell'esempio seguente è richiesta la creazione di una seconda tabella che contiene la colonna con tipo definito dall'utente `Point` e una colonna `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="ce35b-119">The following example requires the creation of a second table containing the `Point` UDT column as well as a `timestamp` column.</span></span> <span data-ttu-id="ce35b-120">Entrambe le tabelle vengono utilizzate per illustrare come creare oggetti comando personalizzati per aggiornare i dati e come eseguire l'aggiornamento utilizzando una colonna `timestamp`.</span><span class="sxs-lookup"><span data-stu-id="ce35b-120">Both tables are used to illustrate how to create custom command objects to update data, and how to update using a `timestamp` column.</span></span> <span data-ttu-id="ce35b-121">Eseguire le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti per creare la seconda tabella e popolarla con i dati di esempio.</span><span class="sxs-lookup"><span data-stu-id="ce35b-121">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements to create the second table and populate it with sample data.</span></span>  
  
```  
CREATE TABLE dbo.Points_ts (id int PRIMARY KEY, p Point, ts timestamp);  
  
INSERT INTO dbo.Points_ts (id, p) VALUES (1, CONVERT(Point, '1,3'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (2, CONVERT(Point, '2,4'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (3, CONVERT(Point, '3,5'));  
INSERT INTO dbo.Points_ts (id, p) VALUES (4, CONVERT(Point, '4,6'));  
```  
  
 <span data-ttu-id="ce35b-122">Nell'esempio ADO.NET seguente sono presenti due metodi:</span><span class="sxs-lookup"><span data-stu-id="ce35b-122">The following ADO.NET example has two methods:</span></span>  
  
-   <span data-ttu-id="ce35b-123">`UserProvidedCommands`, che dimostra come fornire `InsertCommand` `UpdateCommand` gli oggetti, e `DeleteCommand` per l'aggiornamento del `Point` tipo definito dall'utente nella tabella **Points** , che non contiene una `timestamp` colonna.</span><span class="sxs-lookup"><span data-stu-id="ce35b-123">`UserProvidedCommands`, which demonstrates how to supply `InsertCommand`, `UpdateCommand`, and `DeleteCommand` objects for updating the `Point` UDT in the **Points** table (which does not contain a `timestamp` column).</span></span>  
  
-   <span data-ttu-id="ce35b-124">`CommandBuilder`, in cui viene illustrato come utilizzare un oggetto `SqlCommandBuilder` nella tabella **Points_ts** che contiene la `timestamp` colonna.</span><span class="sxs-lookup"><span data-stu-id="ce35b-124">`CommandBuilder`, which demonstrates how to use a `SqlCommandBuilder` in the **Points_ts** table that contains the `timestamp` column.</span></span>  
  
```vb  
Imports System  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
    ' Retrieves the connection string  
    Private connString As String = GetConnectionString()  
  
    Sub Main()  
        UserProvidedCommands()  
        CommandBuilder()  
    End Sub  
  
    Private Sub UserProvidedCommands()  
        ' Create a new SqlDataAdapter  
        Dim da As New SqlDataAdapter( _  
          "SELECT id, p FROM dbo.Points", connString)  
  
        ' Setup the INSERT/UPDATE/DELETE commands  
        Dim idParam As SqlParameter  
        Dim pointParam As SqlParameter  
  
        da.InsertCommand = New SqlCommand( _  
          "INSERT INTO dbo.Points (id, p) VALUES (@id, @p)", _  
          da.SelectCommand.Connection)  
        idParam = da.InsertCommand.Parameters.Add( _  
          "@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
        pointParam = da.InsertCommand.Parameters.Add( _  
          "@p", SqlDbType.Udt)  
        pointParam.SourceColumn = "p"  
        pointParam.UdtTypeName = "dbo.Point"  
  
        da.UpdateCommand = New SqlCommand( _  
          "UPDATE dbo.Points SET p = @p WHERE id = @id", _  
          da.SelectCommand.Connection)  
        idParam = _  
           da.UpdateCommand.Parameters.Add("@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
        pointParam = da.UpdateCommand.Parameters.Add( _  
          "@p", SqlDbType.Udt)  
        pointParam.SourceColumn = "p"  
        pointParam.UdtTypeName = "dbo.Point"  
  
        da.DeleteCommand = New SqlCommand( _  
          "DELETE dbo.Points WHERE id = @id", _  
          da.SelectCommand.Connection)  
        idParam = da.DeleteCommand.Parameters.Add( _  
          "@id", SqlDbType.Int)  
        idParam.SourceColumn = "id"  
  
        ' Fill the DataTable with UDT rows  
        Dim datTable As New DataTable("Points")  
        da.Fill(datTable)  
  
        ' Display the contents of the p (Point) column  
        Dim r As DataRow  
        For Each r In datTable.Rows  
            Dim p As Point = CType(r(1), Point)  
            Console.WriteLine( _  
              "ID: {0}, x={1}, y={1}", r(0), p.X, p.Y)  
        Next r  
  
        ' Update a row if the DataTable has at least 1 row  
        If datTable.Rows.Count > 0 Then  
            Dim oldPoint As Point = _  
              CType(datTable.Rows(0)(1), Point)  
            datTable.Rows(0)(1) = _  
              New Point(oldPoint.X + 1, oldPoint.Y + 1)  
        End If  
  
        ' Delete the last row  
        If datTable.Rows.Count > 0 Then  
            ' If we have at least 1 row  
            datTable.Rows(1).Delete()  
        End If  
  
        ' Insert a row. This will fail if run twice  
        ' because 100 is a primary key value.  
        datTable.Rows.Add(100, New Point(100, 200))  
  
        ' Send the changes back to the database  
        da.Update(datTable)  
    End Sub  
  
    Private Sub CommandBuilder()  
        ' Create a new SqlDataAdapter  
        Dim da As New SqlDataAdapter( _  
          "SELECT id, ts, p FROM dbo.Points_ts", connString)  
  
        ' Select a few rows with UDTs from the database  
        Dim datTable As New DataTable("Points")  
        da.Fill(datTable)  
  
        ' Display the contents of the p (Point) column  
        Dim r As DataRow  
        For Each r In datTable.Rows  
            Dim p As Point = CType(r(2), Point)  
            Console.WriteLine( _  
              "ID: {0}, x={1}, y={1}", r(0), p.X, p.Y)  
        Next r  
  
        ' Update a row if DataTable has at least 1 row  
        If datTable.Rows.Count > 0 Then  
            Dim oldPoint As Point = _  
              CType(datTable.Rows(0)(2), Point)  
            datTable.Rows(0)(2) = _  
              New Point(oldPoint.X + 1, oldPoint.Y + 1)  
        End If  
  
        ' Delete the last row  
        If datTable.Rows.Count > 0 Then  
            ' if we have at least 1 row  
            datTable.Rows(1).Delete()  
        End If  
  
        ' Insert a row. This will fail if run twice  
        ' because 100 is a primary key value  
        datTable.Rows.Add(100, Nothing, New Point(100, 200))  
  
        ' Use the CommandBuilder to generate DML statements  
        Dim bld As New SqlCommandBuilder(da)  
        bld.ConflictDetection = ConflictOptions.CompareRowVersion  
  
        ' Send the changes back to the database  
        da.Update(datTable)  
    End Sub  
  
  Private Function GetConnectionString() As String  
      ' To avoid storing the connection string in your code,   
      ' you can retrieve it from a configuration file.  
     Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
       & "Integrated Security=SSPI"  
   End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Class1  
  {  
// Retrieves the connection string  
private string connString = GetConnectionString();  
  
static void Main()  
{  
        UserProvidedCommands();  
        CommandBuilder();  
 }  
    static void UserProvidedCommands()  
    {  
        // Create a new SqlDataAdapter  
        SqlDataAdapter da = new SqlDataAdapter(  
          "SELECT id, p FROM dbo.Points", connString);  
  
        // Setup the INSERT/UPDATE/DELETE commands  
        SqlParameter idParam;  
        SqlParameter pointParam;  
  
        da.InsertCommand = new SqlCommand(  
            "INSERT INTO dbo.Points (id, p) VALUES (@id, @p)",   
             da.SelectCommand.Connection);  
        idParam =   
            da.InsertCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
        pointParam =   
            da.InsertCommand.Parameters.Add("@p", SqlDbType.Udt);  
        pointParam.SourceColumn = "p";  
        pointParam.UdtTypeName = "dbo.Point";  
  
        da.UpdateCommand = new SqlCommand(  
            "UPDATE dbo.Points SET p = @p WHERE id = @id",   
            da.SelectCommand.Connection);  
        idParam =   
            da.UpdateCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
        pointParam =   
            da.UpdateCommand.Parameters.Add("@p", SqlDbType.Udt);  
        pointParam.SourceColumn = "p";  
        pointParam.UdtTypeName = "dbo.Point";   
  
        da.DeleteCommand = new SqlCommand(  
            "DELETE dbo.Points WHERE id = @id",   
            da.SelectCommand.Connection);  
        idParam =   
            da.DeleteCommand.Parameters.Add("@id", SqlDbType.Int);  
        idParam.SourceColumn = "id";  
  
        // Fill the DataTable with UDT rows  
        DataTable datTable = new DataTable("Points");  
        da.Fill(datTable);  
  
        // Display the contents of the p (Point) column  
        foreach(DataRow r in datTable.Rows)   
        {  
            Point p = (Point)r[1];  
            Console.WriteLine(  
                "ID: {0}, x={1}, y={1}", r[0], p.X, p.Y);  
        }  
  
        // Update a row if the DataTable has at least 1 row  
        if(datTable.Rows.Count > 0 )   
        {   
            Point oldPoint = (Point)datTable.Rows[0][1];  
            datTable.Rows[0][1] =   
                new Point(oldPoint.X+1, oldPoint.Y+1);  
        }  
  
        // Delete the last row  
        if(datTable.Rows.Count > 0 )   
        { // If we have at least 1 row  
            datTable.Rows[1].Delete();  
        }  
  
        // Insert a row. This will fail if run twice  
        // because 100 is a primary key value.  
        datTable.Rows.Add(100, new Point(100, 200));   
  
        // Send the changes back to the database  
        da.Update(datTable);  
    }  
  
    static void CommandBuilder()  
    {  
        // Create a new SqlDataAdapter  
        SqlDataAdapter da = new SqlDataAdapter(  
            "SELECT id, ts, p FROM dbo.Points_ts", connString);  
  
        // Select a few rows with UDTs from the database  
        DataTable datTable = new DataTable("Points");  
        da.Fill(datTable);  
  
        // Display the contents of the p (Point) column  
        foreach (DataRow r in datTable.Rows)  
        {  
            Point p = (Point)r[2];  
            Console.WriteLine(  
                "ID: {0}, x={1}, y={1}", r[0], p.X, p.Y);  
        }  
  
        // Update a row if DataTable has at least 1 row  
        if (datTable.Rows.Count > 0)  
        {   
            Point oldPoint = (Point)datTable.Rows[0][2];  
            datTable.Rows[0][2] =   
                new Point(oldPoint.X + 1, oldPoint.Y + 1);  
        }  
  
        // Delete the last row  
        if (datTable.Rows.Count > 0)  
        { // if we have at least 1 row  
            datTable.Rows[1].Delete();  
        }  
  
        // Insert a row. This will fail if run twice  
        // because 100 is a primary key value  
        datTable.Rows.Add(100, null, new Point(100, 200));   
  
        // Use the CommandBuilder to generate DML statements  
        SqlCommandBuilder bld = new SqlCommandBuilder(da);  
        bld.ConflictDetection = ConflictOptions.CompareRowVersion;  
  
        // Send the changes back to the database  
        da.Update(datTable);  
    }  
  
 static private string GetConnectionString()  
 {  
 // To avoid storing the connection string in your code,   
 // you can retrieve it from a configuration file.  
    return "Data Source=localhost;Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce35b-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce35b-125">See Also</span></span>  
 [<span data-ttu-id="ce35b-126">Accesso ai tipi definiti dall'utente in ADO .NET</span><span class="sxs-lookup"><span data-stu-id="ce35b-126">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
