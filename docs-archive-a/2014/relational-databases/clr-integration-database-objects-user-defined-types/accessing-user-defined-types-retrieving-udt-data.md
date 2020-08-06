---
title: Recupero di dati UDT | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SqlDataReader object
- ADO.NET [CLR integration]
- binding UDTs [CLR integration]
- UDTs [CLR integration], ADO.NET
- assemblies [CLR integration], user-defined types
- query parameters [CLR integration]
- user-defined types [CLR integration], ADO.NET
- bytes [CLR integration]
ms.assetid: 6a98ac8c-0e69-4c03-83a4-2062cb782049
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9133ea45069f76e7590f6b74d3c1e1cb98c7bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635090"
---
# <a name="retrieving-udt-data"></a><span data-ttu-id="c8c26-102">Recupero di dati UDT</span><span class="sxs-lookup"><span data-stu-id="c8c26-102">Retrieving UDT Data</span></span>
  <span data-ttu-id="c8c26-103">Per creare un tipo definito dall'utente (UDT) nel client, l'assembly registrato come tipo definito dall'utente in un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve essere disponibile per l'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="c8c26-103">In order to create a user-defined type (UDT) on the client, the assembly that was registered as a UDT in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database must be available to the client application.</span></span> <span data-ttu-id="c8c26-104">L'assembly UDT può essere posizionato nella stessa directory dell'applicazione oppure nella Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="c8c26-104">The UDT assembly can be placed in the same directory with the application, or in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="c8c26-105">È inoltre possibile impostare un riferimento all'assembly nel progetto.</span><span class="sxs-lookup"><span data-stu-id="c8c26-105">You can also set a reference to the assembly in your project.</span></span>  
  
## <a name="requirements-for-using-udts-in-adonet"></a><span data-ttu-id="c8c26-106">Requisiti per l'utilizzo di tipi definiti dall'utente in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c8c26-106">Requirements for Using UDTs in ADO.NET</span></span>  
 <span data-ttu-id="c8c26-107">Per consentire la creazione del tipo definito dall'utente sul client, è necessario che l'assembly caricato in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e l'assembly sul client siano compatibili.</span><span class="sxs-lookup"><span data-stu-id="c8c26-107">The assembly loaded in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the assembly on the client must be compatible in order for the UDT to be created on the client.</span></span> <span data-ttu-id="c8c26-108">Per i tipi definiti dall'utente con il formato di serializzazione `Native`, gli assembly devono essere strutturalmente compatibili.</span><span class="sxs-lookup"><span data-stu-id="c8c26-108">For UDTs defined with the `Native` serialization format, the assemblies must be structurally compatible.</span></span> <span data-ttu-id="c8c26-109">Gli assembly definiti con il formato `UserDefined` devono essere disponibili sul client.</span><span class="sxs-lookup"><span data-stu-id="c8c26-109">For assemblies defined with the `UserDefined` format, the assembly must be available on the client.</span></span>  
  
 <span data-ttu-id="c8c26-110">Per recuperare i dati non elaborati da una colonna con tipo definito dall'utente in una tabella, non è necessario che sul client sia disponibile una copia dell'assembly UDT.</span><span class="sxs-lookup"><span data-stu-id="c8c26-110">You do not need a copy of the UDT assembly on the client in order to retrieve the raw data from a UDT column in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8c26-111">**SqlClient** potrebbe non riuscire a caricare un tipo definito dall'utente in caso di versioni non corrispondenti del tipo definito dall'utente o di altri problemi.</span><span class="sxs-lookup"><span data-stu-id="c8c26-111">**SqlClient** may fail to load a UDT in the event of mismatched UDT versions or other problems.</span></span> <span data-ttu-id="c8c26-112">In questo caso, utilizzare i normali meccanismi per la risoluzione di problemi per determinare il motivo per cui l'assembly in cui è contenuto il tipo definito dall'utente non viene individuato dall'applicazione chiamante.</span><span class="sxs-lookup"><span data-stu-id="c8c26-112">In this case, use regular troubleshooting mechanisms to determine why the assembly containing the UDT cannot be found by the calling application.</span></span> <span data-ttu-id="c8c26-113">Per ulteriori informazioni, consultare l'argomento intitolato "Diagnostica degli errori tramite gli assistenti al debug gestito" nella documentazione di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8c26-113">For more information, read the topic titled "Diagnosing Errors with Managed Debugging Assistants" in the .NET Framework documentation.</span></span>  
  
## <a name="accessing-udts-with-a-sqldatareader"></a><span data-ttu-id="c8c26-114">Accesso ai tipi definiti dall'utente con un oggetto SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="c8c26-114">Accessing UDTs with a SqlDataReader</span></span>  
 <span data-ttu-id="c8c26-115">È possibile utilizzare un oggetto `System.Data.SqlClient.SqlDataReader` dal codice client per recuperare un set di risultati in cui è contenuta una colonna con tipo definito dall'utente, esposta come un'istanza dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c8c26-115">A `System.Data.SqlClient.SqlDataReader` can be used from client code to retrieve a result set that contains a UDT column, which is exposed as an instance of the object.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c8c26-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8c26-116">Example</span></span>  
 <span data-ttu-id="c8c26-117">In questo esempio viene mostrato come utilizzare il metodo `Main` per creare un nuovo oggetto `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="c8c26-117">This example shows how to use the `Main` method to create a new `SqlDataReader` object.</span></span> <span data-ttu-id="c8c26-118">All'interno del codice di esempio si verificano le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8c26-118">The following actions occur within the code example:</span></span>  
  
1.  <span data-ttu-id="c8c26-119">Il metodo Main crea un nuovo oggetto `SqlDataReader` e recupera i valori della tabella Points contenente una colonna con tipo definito dall'utente denominata Point.</span><span class="sxs-lookup"><span data-stu-id="c8c26-119">The Main method creates a new `SqlDataReader` object and retrieves the values from the Points table, which has a UDT column named Point.</span></span>  
  
2.  <span data-ttu-id="c8c26-120">Il tipo definito dall'utente di Point espone le coordinate X e Y definite come numeri interi.</span><span class="sxs-lookup"><span data-stu-id="c8c26-120">The Point UDT exposes X and Y coordinates defined as integers.</span></span>  
  
3.  <span data-ttu-id="c8c26-121">Il tipo definito dall'utente definisce un metodo `Distance` e un metodo `GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="c8c26-121">The UDT defines a `Distance` method and a `GetDistanceFromXY` method.</span></span>  
  
4.  <span data-ttu-id="c8c26-122">Il codice di esempio recupera i valori delle colonne con tipo definito dall'utente di chiave primaria per dimostrare le funzionalità del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c8c26-122">The sample code retrieves the values of the primary key and UDT columns in order to demonstrate the capabilities of the UDT.</span></span>  
  
5.  <span data-ttu-id="c8c26-123">Il codice di esempio chiama i metodi `Point.Distance` e `Point.GetDistanceFromXY`.</span><span class="sxs-lookup"><span data-stu-id="c8c26-123">The sample code calls the `Point.Distance` and `Point.GetDistanceFromXY` methods.</span></span>  
  
6.  <span data-ttu-id="c8c26-124">I risultati vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="c8c26-124">The results are displayed in the console window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8c26-125">Nell'applicazione deve essere già presente un riferimento all'assembly UDT.</span><span class="sxs-lookup"><span data-stu-id="c8c26-125">The application must already have a reference to the UDT assembly.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module ReadPoints  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the value of the UDT  
                Dim pnt As Point = CType(rdr(1), Point)  
  
             ' You can also use GetSqlValue and GetValue  
             ' Dim pnt As Point = CType(rdr.GetSqlValue(1), Point)  
             ' Dim pnt As Point = CType(rdr.GetValue(1), Point)  
  
                ' Print values  
                Console.WriteLine( _  
                 "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}", _  
                  id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance())  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
         & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
namespace Microsoft.Samples.SqlServer  
{  
class ReadPoints  
{  
static void Main()  
{  
  string connectionString = GetConnectionString();  
  using (SqlConnection cnn = new SqlConnection(connectionString))  
  {  
    cnn.Open();  
    SqlCommand cmd = new SqlCommand(  
       "SELECT ID, Pnt FROM dbo.Points", cnn);  
    SqlDataReader rdr = cmd.ExecuteReader();  
  
    while (rdr.Read())  
    {  
      // Retrieve the value of the Primary Key column  
      int id = rdr.GetInt32(0);  
  
        // Retrieve the value of the UDT  
        Point pnt = (Point)rdr[1];  
  
        // You can also use GetSqlValue and GetValue  
        // Point pnt = (Point)rdr.GetSqlValue(1);  
        // Point pnt = (Point)rdr.GetValue(1);  
  
        Console.WriteLine(  
        "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}",   
        id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance());  
    }  
  rdr.Close();  
  Console.WriteLine("done");  
  }  
  static private string GetConnectionString()  
  {  
    // To avoid storing the connection string in your code,   
    // you can retrieve it from a configuration file.  
    return "Data Source=(local);Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="binding-udts-as-bytes"></a><span data-ttu-id="c8c26-126">Associazione di tipi definiti dall'utente come byte</span><span class="sxs-lookup"><span data-stu-id="c8c26-126">Binding UDTs as Bytes</span></span>  
 <span data-ttu-id="c8c26-127">In alcune situazioni può risultare utile recuperare i dati non elaborati dalla colonna con tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c8c26-127">In some situations, you may want to retrieve the raw data from the UDT column.</span></span> <span data-ttu-id="c8c26-128">Può accadere che il tipo non sia disponibile localmente o non si desideri creare un'istanza del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="c8c26-128">Perhaps the type is not available locally, or you do not wish to instantiate an instance of the UDT.</span></span> <span data-ttu-id="c8c26-129">È possibile leggere i byte non elaborati in una matrice di byte usando il metodo **GetBytes** di un oggetto `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="c8c26-129">You can read the raw bytes into a byte array using the **GetBytes** method of a `SqlDataReader`.</span></span> <span data-ttu-id="c8c26-130">Tale metodo legge un flusso di byte dall'offset di colonna specificato nel buffer di una matrice, a partire dall'offset del buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="c8c26-130">This method reads a stream of bytes from the specified column offset into the buffer of an array starting at a specified buffer offset.</span></span> <span data-ttu-id="c8c26-131">Un'altra opzione consiste nell'usare uno dei metodi **GetSqlBytes** o **GetSqlBinary** e leggere tutto il contenuto in una singola operazione.</span><span class="sxs-lookup"><span data-stu-id="c8c26-131">Another option is to use one of the **GetSqlBytes** or **GetSqlBinary** methods and read all of the contents in a single operation.</span></span> <span data-ttu-id="c8c26-132">In entrambi i casi non viene mai creata un'istanza dell'oggetto UDT, pertanto non è necessario impostare un riferimento al tipo definito dall'utente nell'assembly client.</span><span class="sxs-lookup"><span data-stu-id="c8c26-132">In either case, the UDT object is never instantiated, so you do not need to set a reference to the UDT in the client assembly.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c8c26-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8c26-133">Example</span></span>  
 <span data-ttu-id="c8c26-134">In questo esempio viene illustrato come recuperare i dati **punto** come byte non elaborati in una matrice di byte utilizzando un oggetto `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="c8c26-134">This example shows how to retrieve the **Point** data as raw bytes into a byte array using a `SqlDataReader`.</span></span> <span data-ttu-id="c8c26-135">Il codice utilizza un oggetto `System.Text.StringBuilder` per convertire i byte non elaborati in una rappresentazione di stringa da visualizzare nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="c8c26-135">The code uses a `System.Text.StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the raw bytes into a byte array  
                Dim buffer(31) As Byte  
                Dim byteCount As Integer = _  
                 CInt(rdr.GetBytes(1, 0, buffer, 0, 31))  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", buffer(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
        string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand("SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Retrieve the raw bytes into a byte array  
                byte[] buffer = new byte[32];  
                long byteCount = rdr.GetBytes(1, 0, buffer, 0, 32);  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", buffer[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
### <a name="example-using-getsqlbytes"></a><span data-ttu-id="c8c26-136">Esempio di utilizzo di GetSqlBytes</span><span class="sxs-lookup"><span data-stu-id="c8c26-136">Example Using GetSqlBytes</span></span>  
 <span data-ttu-id="c8c26-137">Questo esempio illustra come recuperare i dati **punto** come byte non elaborati in una singola operazione usando il metodo **GetSqlBytes** .</span><span class="sxs-lookup"><span data-stu-id="c8c26-137">This example shows how to retrieve the **Point** data as raw bytes in a single operation using the **GetSqlBytes** method.</span></span> <span data-ttu-id="c8c26-138">Il codice utilizza un oggetto `StringBuilder` per convertire i byte non elaborati in una rappresentazione di stringa da visualizzare nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="c8c26-138">The code uses a `StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Use SqlBytes to retrieve raw bytes  
                Dim sb As SqlBytes = rdr.GetSqlBytes(1)  
                Dim byteCount As Long = sb.Length  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", sb(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
         string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Use SqlBytes to retrieve raw bytes  
                SqlBytes sb = rdr.GetSqlBytes(1);  
                long byteCount = sb.Length;  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", sb[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="working-with-udt-parameters"></a><span data-ttu-id="c8c26-139">Utilizzo dei parametri UDT</span><span class="sxs-lookup"><span data-stu-id="c8c26-139">Working with UDT Parameters</span></span>  
 <span data-ttu-id="c8c26-140">I tipi definiti dall'utente possono essere utilizzati come parametri sia di input che di output nel codice ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="c8c26-140">UDTs can be used as both input and output parameters in your ADO.NET code.</span></span>  
  
## <a name="using-udts-in-query-parameters"></a><span data-ttu-id="c8c26-141">Utilizzo dei tipi definiti dall'utente nei parametri di query</span><span class="sxs-lookup"><span data-stu-id="c8c26-141">Using UDTs in Query Parameters</span></span>  
 <span data-ttu-id="c8c26-142">I tipi definiti dall'utente possono essere utilizzati come valori di parametro in caso di configurazione di un oggetto `SqlParameter` per un oggetto `System.Data.SqlClient.SqlCommand`.</span><span class="sxs-lookup"><span data-stu-id="c8c26-142">UDTs can be used as parameter values when setting up a `SqlParameter` for a `System.Data.SqlClient.SqlCommand` object.</span></span> <span data-ttu-id="c8c26-143">L'enumerazione `SqlDbType.Udt` di un oggetto `SqlParameter` viene utilizzata per indicare che il parametro è un tipo definito dall'utente durante la chiamata al metodo `Add` nella raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="c8c26-143">The `SqlDbType.Udt` enumeration of a `SqlParameter` object is used to indicate that the parameter is a UDT when calling the `Add` method to the `Parameters` collection.</span></span> <span data-ttu-id="c8c26-144">La `UdtTypeName` proprietà di un `SqlCommand` oggetto viene utilizzata per specificare il nome completo del tipo definito dall'utente nel database utilizzando la sintassi del *database. schema_name. object_name* .</span><span class="sxs-lookup"><span data-stu-id="c8c26-144">The `UdtTypeName` property of a `SqlCommand` object is used to specify the fully qualified name of the UDT in the database using the *database.schema_name.object_name* syntax.</span></span> <span data-ttu-id="c8c26-145">Anche se non è richiesto, l'utilizzo che il nome completo, elimina l'ambiguità dal codice.</span><span class="sxs-lookup"><span data-stu-id="c8c26-145">Although it is not required, using the fully qualified name removes ambiguity from your code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c8c26-146">Una copia locale dell'assembly UDT deve essere disponibile per il progetto client.</span><span class="sxs-lookup"><span data-stu-id="c8c26-146">A local copy of the UDT assembly must be available to the client project.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c8c26-147">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8c26-147">Example</span></span>  
 <span data-ttu-id="c8c26-148">Il codice riportato in questo esempio crea oggetti `SqlCommand` e `SqlParameter` per l'inserimento di dati in una colonna con tipo definito dall'utente di una tabella.</span><span class="sxs-lookup"><span data-stu-id="c8c26-148">The code in this example creates `SqlCommand` and `SqlParameter` objects to insert data into a UDT column in a table.</span></span> <span data-ttu-id="c8c26-149">Il codice utilizza l'enumerazione `SqlDbType.Udt` per specificare il tipo di dati e la proprietà `UdtTypeName` dell'oggetto `SqlParameter` per specificare il nome completo del tipo definito dall'utente nel database.</span><span class="sxs-lookup"><span data-stu-id="c8c26-149">The code uses the `SqlDbType.Udt` enumeration to specify the data type, and the `UdtTypeName` property of the `SqlParameter` object to specify the fully qualified name of the UDT in the database.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports system.Data  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim ConnectionString As String = GetConnectionString()  
    Dim cnn As New SqlConnection(ConnectionString)  
    Using cnn  
      Dim cmd As SqlCommand = cnn.CreateCommand()  
      cmd.CommandText = "INSERT INTO dbo.Points (Pnt) VALUES (@Point)"  
      cmd.CommandType = CommandType.Text  
  
      Dim param As New SqlParameter("@Point", SqlDbType.Udt)      param.UdtTypeName = "TestPoint.dbo.Point"      param.Direction = ParameterDirection.Input      param.Value = New Point(5, 6)      cmd.Parameters.Add(param)  
  
      cnn.Open()  
      cmd.ExecuteNonQuery()  
      Console.WriteLine("done")  
    End Using  
  End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
class Class1  
{  
static void Main()  
{  
  string ConnectionString = GetConnectionString();  
     using (SqlConnection cnn = new SqlConnection(ConnectionString))  
     {  
       SqlCommand cmd = cnn.CreateCommand();  
       cmd.CommandText =   
         "INSERT INTO dbo.Points (Pnt) VALUES (@Point)";  
       cmd.CommandType = CommandType.Text;  
  
       SqlParameter param = new SqlParameter("@Point", SqlDbType.Udt);       param.UdtTypeName = "TestPoint.dbo.Point";       param.Direction = ParameterDirection.Input;       param.Value = new Point(5, 6);       cmd.Parameters.Add(param);  
  
       cnn.Open();  
       cmd.ExecuteNonQuery();  
       Console.WriteLine("done");  
     }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8c26-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8c26-150">See Also</span></span>  
 [<span data-ttu-id="c8c26-151">Accesso ai tipi definiti dall'utente in ADO .NET</span><span class="sxs-lookup"><span data-stu-id="c8c26-151">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
