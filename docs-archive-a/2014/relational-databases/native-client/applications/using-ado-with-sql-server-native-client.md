---
title: Utilizzo di ADO con SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, ADO
- data access [SQL Server Native Client], ADO
- ADO [SQL Server Native Client]
- SQLNCLI, ADO
ms.assetid: 118a7cac-4c0d-44fd-b63e-3d542932d239
author: rothja
ms.author: jroth
ms.openlocfilehash: ccd14432aa3541572467a4c651c1f48b1ac957f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722704"
---
# <a name="using-ado-with-sql-server-native-client"></a><span data-ttu-id="c1db1-102">Utilizzo di ADO con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c1db1-102">Using ADO with SQL Server Native Client</span></span>
  <span data-ttu-id="c1db1-103">Per sfruttare i vantaggi delle nuove funzionalità introdotte in, [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] ad esempio Mars (Multiple Active Result Set), notifiche delle query, tipi definiti dall'utente (UDT) o il nuovo tipo di dati **XML** , le applicazioni esistenti che utilizzano ActiveX Data Objects (ADO) utilizzano il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider OLE DB di Native client come provider di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="c1db1-103">In order to take advantage of new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] such as multiple active result sets (MARS), query notifications, user-defined types (UDTs), or the new **xml** data type, existing applications that use ActiveX Data Objects (ADO) should use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider as their data access provider.</span></span>  
  
 <span data-ttu-id="c1db1-104">L'uso del provider OLE DB di [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client è necessario solo per utilizzare una delle caratteristiche introdotte in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Se non si intende utilizzare tali caratteristiche, è possibile continuare a usare il provider di accesso ai dati corrente, generalmente SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="c1db1-104">If you do not need to use any of the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], there is no need to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider; you can continue using your current data access provider, which is typically SQLOLEDB.</span></span> <span data-ttu-id="c1db1-105">L'uso del provider OLE DB di [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client è consigliabile se si intende potenziare un'applicazione esistente e si ha l'esigenza di utilizzare le nuove caratteristiche introdotte in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1db1-105">If you are enhancing an existing application and you need to use the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], you should use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1db1-106">Se si sviluppa una nuova applicazione, è consigliabile valutare l'opportunità di utilizzare ADO.NET e il provider di dati .NET Framework per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] anziché [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client per accedere a tutte le nuove caratteristiche delle ultime versioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1db1-106">If you are developing a new application, it is recommended that you consider using ADO.NET and the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instead of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access all the new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c1db1-107">Per ulteriori informazioni sul provider di dati .NET Framework per [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], fare riferimento alla documentazione di .NET Framework SDK per ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="c1db1-107">For more information about the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see the .NET Framework SDK documentation for ADO.NET.</span></span>  
  
 <span data-ttu-id="c1db1-108">Per consentire l'utilizzo in ADO delle nuove caratteristiche delle ultime versioni di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], al provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client sono stati apportati alcuni miglioramenti che estendono le caratteristiche principali di OLE DB.</span><span class="sxs-lookup"><span data-stu-id="c1db1-108">To enable ADO to use new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], some enhancements have been made to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider which extends the core features of OLE DB.</span></span> <span data-ttu-id="c1db1-109">Questi miglioramenti consentono l'uso nelle applicazioni ADO delle più recenti funzionalità di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e di due tipi di dati introdotti in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml** e **udt**.</span><span class="sxs-lookup"><span data-stu-id="c1db1-109">These enhancements allow ADO applications to use newer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features and to consume two data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml** and **udt**.</span></span> <span data-ttu-id="c1db1-110">Consentono inoltre di sfruttare i miglioramenti ai tipi di dati **varchar**, **nvarchar** e **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="c1db1-110">These enhancements also exploit enhancements to the **varchar**, **nvarchar**, and **varbinary** data types.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="c1db1-111">Native client aggiunge la proprietà di inizializzazione SSPROP_INIT_DATATYPECOMPATIBILITY al set di proprietà DBPROPSET_SQLSERVERDBINIT per l'utilizzo da parte delle applicazioni ADO, in modo che i nuovi tipi di dati vengano esposti in modo compatibile con ADO.</span><span class="sxs-lookup"><span data-stu-id="c1db1-111">Native Client adds the SSPROP_INIT_DATATYPECOMPATIBILITY initialization property to the DBPROPSET_SQLSERVERDBINIT property set for use by ADO applications so that the new data types are exposed in a way compatible with ADO.</span></span> <span data-ttu-id="c1db1-112">Inoltre, il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client definisce anche una nuova parola chiave della stringa di connessione denominata `DataTypeCompatibility` impostata nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="c1db1-112">In addition, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider also defines a new connection string keyword named `DataTypeCompatibility` that is set in the connection string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1db1-113">Le applicazioni ADO esistenti possono accedere a valori XML, UDT, nonché di campi binari e di testo valore di grandi dimensioni ed eseguirne l'aggiornamento utilizzando il provider SQLOLEDB.</span><span class="sxs-lookup"><span data-stu-id="c1db1-113">Existing ADO applications can access and update XML, UDT, and large value text and binary field values using the SQLOLEDB provider.</span></span> <span data-ttu-id="c1db1-114">I nuovi tipi di dati **varchar(max)** , **nvarchar(max)** e **varbinary(max)** di grandi dimensioni vengono restituiti rispettivamente come i tipi ADO **adLongVarChar**, **adLongVarWChar** e **adLongVarBinary**.</span><span class="sxs-lookup"><span data-stu-id="c1db1-114">The new larger **varchar(max)**, **nvarchar(max)**, and **varbinary(max)** data types are returned as the ADO types **adLongVarChar**, **adLongVarWChar** and **adLongVarBinary** respectively.</span></span> <span data-ttu-id="c1db1-115">Le colonne XML vengono restituite come **adLongVarChar**, mentre le colonne con tipo definito dall'utente vengono restituite come **adVarBinary**.</span><span class="sxs-lookup"><span data-stu-id="c1db1-115">XML columns are returned as **adLongVarChar**, and UDT columns are returned as **adVarBinary**.</span></span> <span data-ttu-id="c1db1-116">Se tuttavia, si utilizza il provider OLE DB di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) anziché SQLOLEDB, è necessario assicurarsi di impostare la parola chiave `DataTypeCompatibility` su "80" in modo da consentire la corretta esecuzione del mapping dei nuovi tipi di dati ai tipi di dati ADO.</span><span class="sxs-lookup"><span data-stu-id="c1db1-116">However, if you use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider (SQLNCLI11) instead of SQLOLEDB, you need to make sure to set the `DataTypeCompatibility` keyword to "80" so that the new data types will map correctly to the ADO data types.</span></span>  
  
## <a name="enabling-sql-server-native-client-from-ado"></a><span data-ttu-id="c1db1-117">Abilitazione di SQL Server Native Client da ADO</span><span class="sxs-lookup"><span data-stu-id="c1db1-117">Enabling SQL Server Native Client from ADO</span></span>  
 <span data-ttu-id="c1db1-118">Per abilitare l'utilizzo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] native client, le applicazioni ADO dovranno implementare le parole chiave seguenti nelle stringhe di connessione:</span><span class="sxs-lookup"><span data-stu-id="c1db1-118">To enable the usage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, ADO applications will need to implement the following keywords in their connection strings:</span></span>  
  
-   `Provider=SQLNCLI11`  
  
-   `DataTypeCompatibility=80`  
  
 <span data-ttu-id="c1db1-119">Per ulteriori informazioni sulle parole chiave delle stringhe di connessione ADO supportate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] native client, vedere [utilizzo delle parole chiave delle stringhe di connessione con SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c1db1-119">For more information about the ADO connections string keywords supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="c1db1-120">Di seguito è riportato un esempio di creazione di una stringa di connessione ADO completamente abilitata per l'utilizzo con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] native client, inclusa l'abilitazione della funzionalità Mars:</span><span class="sxs-lookup"><span data-stu-id="c1db1-120">The following is an example of establishing an ADO connection string that is fully enabled to work with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, including the enabling of the MARS feature:</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
```  
  
## <a name="examples"></a><span data-ttu-id="c1db1-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="c1db1-121">Examples</span></span>  
 <span data-ttu-id="c1db1-122">Nelle sezioni seguenti vengono forniti esempi di come è possibile utilizzare ADO con il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="c1db1-122">The following sections provide examples of how you can use ADO with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
### <a name="retrieving-xml-column-data"></a><span data-ttu-id="c1db1-123">Recupero dei dati delle colonne XML</span><span class="sxs-lookup"><span data-stu-id="c1db1-123">Retrieving XML Column Data</span></span>  
 <span data-ttu-id="c1db1-124">In questo esempio viene usato un recordset per recuperare e visualizzare i dati da una colonna XML nel database di esempio **AdventureWorks** di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1db1-124">In this example, a recordset is used to retrieve and display the data from an XML column in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **AdventureWorks** sample database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim rst As New ADODB.Recordset  
Dim sXMLResult As String  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _   
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the xml data as a recordset.  
Set rst.ActiveConnection = con  
rst.Source = "SELECT AdditionalContactInfo FROM Person.Contact " _  
   & "WHERE AdditionalContactInfo IS NOT NULL"  
rst.Open  
  
' Display the data in the recordset.  
While (Not rst.EOF)  
   sXMLResult = rst.Fields("AdditionalContactInfo").Value  
   Debug.Print (sXMLResult)  
   rst.MoveNext  
End While  
  
con.Close  
Set con = Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c1db1-125">L'applicazione di filtri al recordset non è supportata con le colonne XML.</span><span class="sxs-lookup"><span data-stu-id="c1db1-125">Recordset filtering is not supported with XML columns.</span></span> <span data-ttu-id="c1db1-126">Se si prova ad applicare i filtri, viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="c1db1-126">If used, an error will be returned.</span></span>  
  
### <a name="retrieving-udt-column-data"></a><span data-ttu-id="c1db1-127">Recupero dei dati delle colonne con tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="c1db1-127">Retrieving UDT Column Data</span></span>  
 <span data-ttu-id="c1db1-128">In questo esempio viene utilizzato un oggetto **Command** per eseguire una query SQL che restituisce un tipo definito dall'utente, vengono aggiornati i dati UDT, quindi i nuovi dati vengono nuovamente inseriti nel database.</span><span class="sxs-lookup"><span data-stu-id="c1db1-128">In this example, a **Command** object is used to execute a SQL query that returns a UDT, the UDT data is updated, and then the new data is inserted back into the database.</span></span> <span data-ttu-id="c1db1-129">In questo esempio si presuppone che il tipo definito dall'utente (UDT) **Point** sia già stato registrato nel database.</span><span class="sxs-lookup"><span data-stu-id="c1db1-129">This example assumes that the **Point** UDT has already been registered in the database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim cmd As New ADODB.Command  
Dim rst As New ADODB.Recordset  
Dim strOldUDT As String  
Dim strNewUDT As String  
Dim aryTempUDT() As String  
Dim strTempID As String  
Dim i As Integer  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the UDT value.  
Set cmd.ActiveConnection = con  
cmd.CommandText = "SELECT ID, Pnt FROM dbo.Points.ToString()"  
Set rst = cmd.Execute  
strTempID = rst.Fields(0).Value  
strOldUDT = rst.Fields(1).Value  
  
' Do something with the UDT by adding i to each point.  
arytempUDT = Split(strOldUDT, ",")  
i = 3  
strNewUDT = LTrim(Str(Int(aryTempUDT(0)) + i)) + "," + _  
   LTrim(Str(Int(aryTempUDT(1)) + i))  
  
' Insert the new value back into the database.  
cmd.CommandText = "UPDATE dbo.Points SET Pnt = '" + strNewUDT + _  
   "' WHERE ID = '" + strTempID + "'"  
cmd.Execute  
  
con.Close  
Set con = Nothing  
```  
  
### <a name="enabling-and-using-mars"></a><span data-ttu-id="c1db1-130">Abilitazione e utilizzo di MARS</span><span class="sxs-lookup"><span data-stu-id="c1db1-130">Enabling and Using MARS</span></span>  
 <span data-ttu-id="c1db1-131">In questo esempio, la stringa di connessione viene costruita per abilitare MARS tramite il [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native client e quindi vengono creati due oggetti recordset da eseguire utilizzando la stessa connessione.</span><span class="sxs-lookup"><span data-stu-id="c1db1-131">In this example, the connection string is constructed to enable MARS through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, and then two recordset objects are created to execute using the same connection.</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
  
Dim recordset1 As New ADODB.Recordset  
Dim recordset2 As New ADODB.Recordset  
  
Dim recordsaffected As Integer  
Set recordset1 =  con.Execute("SELECT * FROM Table1", recordsaffected, adCmdText)  
Set recordset2 =  con.Execute("SELECT * FROM Table2", recordsaffected, adCmdText)  
  
con.Close  
Set con = Nothing  
```  
  
 <span data-ttu-id="c1db1-132">Nelle versioni precedenti del provider OLE DB questo codice determinerebbe la creazione di una connessione implicita alla seconda esecuzione, in quanto per una sola connessione sarebbe possibile aprire un solo set attivo di risultati.</span><span class="sxs-lookup"><span data-stu-id="c1db1-132">In prior versions of the OLE DB provider, this code would cause an implicit connection to be created on the second execution because only one active set of results could be opened per a single connection.</span></span> <span data-ttu-id="c1db1-133">Poiché la connessione implicita non sarebbe inserita nel pool di connessioni OLE DB, questa situazione provocherebbe overhead aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="c1db1-133">Because the implicit connection was not pooled in the OLE DB connection pool this would cause additional overhead.</span></span> <span data-ttu-id="c1db1-134">Con la funzionalità MARS esposta dal [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provider di OLE DB di Native client, si ottengono più risultati attivi in una connessione.</span><span class="sxs-lookup"><span data-stu-id="c1db1-134">With the MARS feature exposed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, you get multiple active results on the one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1db1-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1db1-135">See Also</span></span>  
 [<span data-ttu-id="c1db1-136">Compilazione di applicazioni con SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="c1db1-136">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
