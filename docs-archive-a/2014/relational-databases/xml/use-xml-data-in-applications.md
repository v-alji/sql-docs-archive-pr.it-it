---
title: Usare dati XML nelle applicazioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- parameters [XML in SQL Server]
- XML [SQL Server], ADO
- columns [XML in SQL Server], ADO.NET
- ADO [XML in SQL Server]
- columns [XML in SQL Server], SQL Server Native Client
- xml data type [SQL Server], ADO
- SQLNCLI, XML
- xml data type [SQL Server], SQL Server Native Client
- SQL Server Native Client, XML
- ADO.NET [XML in SQL Server]
- XML [SQL Server], ADO.NET
- columns [XML in SQL Server], ADO
- xml data type [SQL Server], ADO.NET
- XML [SQL Server], SQL Server Native Client
ms.assetid: 5dabf7e0-c6df-451d-a070-4661f84607fd
author: rothja
ms.author: jroth
ms.openlocfilehash: 79dd4f4d2ff3cd61bc33c632f499bfb8e8817f0f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711768"
---
# <a name="use-xml-data-in-applications"></a><span data-ttu-id="2c04a-102">Utilizzo di dati XML nelle applicazioni</span><span class="sxs-lookup"><span data-stu-id="2c04a-102">Use XML Data in Applications</span></span>
  <span data-ttu-id="2c04a-103">In questo argomento vengono descritte le opzioni disponibili per l'utilizzo del tipo di dati `xml` nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="2c04a-103">This topic describes the options that are available to you for working with the `xml` data type in your application.</span></span> <span data-ttu-id="2c04a-104">Vengono fornite informazioni sugli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c04a-104">The topic includes information about the following:</span></span>  
  
-   <span data-ttu-id="2c04a-105">Gestione di dati XML da una colonna di tipo `xml` utilizzando ADO e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="2c04a-105">Handling XML from an `xml` type column by using ADO and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="2c04a-106">Gestione di dati XML da una colonna di tipo `xml` utilizzando ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c04a-106">Handling XML from an `xml` type column by using ADO.NET</span></span>  
  
-   <span data-ttu-id="2c04a-107">Gestione del tipo `xml` nei parametri utilizzando ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c04a-107">Handling `xml` type in parameters by using ADO.NET</span></span>  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-ado-and-sql-server-native-client"></a><span data-ttu-id="2c04a-108">Gestione di XML da una colonna di tipo xml utilizzando ADO e SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="2c04a-108">Handling XML from an xml Type Column by Using ADO and SQL Server Native Client</span></span>  
 <span data-ttu-id="2c04a-109">Per usare i componenti MDAC e accedere alle funzionalità e ai tipi introdotti in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], è necessario impostare la proprietà di inizializzazione DataTypeCompatibility nella stringa di connessione di ADO.</span><span class="sxs-lookup"><span data-stu-id="2c04a-109">To use MDAC components to access the types and features that were introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you must set the DataTypeCompatibility initialization property in the ADO connection string.</span></span>  
  
 <span data-ttu-id="2c04a-110">Nel seguente esempio di codice Visual Basic Scripting Edition (VBScript) vengono illustrati i risultati di una query su una colonna di dati di tipo `xml`, `Demographics`, contenuta nella tabella `Sales.Store` del database di esempio `AdventureWorks2012`.</span><span class="sxs-lookup"><span data-stu-id="2c04a-110">For example, the following Visual Basic Scripting Edition (VBScript) sample shows the results of querying an `xml` data type column, `Demographics`, in the `Sales.Store` table of the `AdventureWorks2012` sample database.</span></span> <span data-ttu-id="2c04a-111">Questa particolare query cerca il valore di istanza della colonna per la riga dove `CustomerID` è uguale a `3`.</span><span class="sxs-lookup"><span data-stu-id="2c04a-111">Specifically, the query looks for the instance value of this column for the row where the `CustomerID` is equal to `3`.</span></span>  
  
```  
Const DS = "MyServer"  
Const DB = "AdventureWorks2012"  
  
Set objConn = CreateObject("ADODB.Connection")  
Set objRs = CreateObject("ADODB.Recordset")  
  
CommandText = "SELECT Demographics" & _  
              " FROM Sales.Store" & _  
              " INNER JOIN Sales.Customer" & _  
              " ON Sales.Store.BusinessEntityID = sales.customer.StoreID" & _  
              " WHERE Sales.Customer.CustomerID = 3" & _  
              " OR Sales.Customer.CustomerID = 4"  
  
ConnectionString = "Provider=SQLNCLI11" & _  
                   ";Data Source=" & DS & _  
                   ";Initial Catalog=" & DB & _  
                   ";Integrated Security=SSPI;" & _  
                   "DataTypeCompatibility=80"  
  
'Connect to the data source.  
objConn.Open ConnectionString  
  
'Execute command through the connection and display  
Set objRs = objConn.Execute(CommandText)  
  
Dim rowcount  
rowcount = 0  
Do While Not objRs.EOF  
   rowcount = rowcount + 1  
   MsgBox "Row " & rowcount & _  
           vbCrLf & vbCrLf & objRs(0)  
   objRs.MoveNext  
Loop  
  
'Clean up.  
objRs.Close  
objConn.Close  
Set objRs = Nothing  
Set objConn = Nothing  
```  
  
 <span data-ttu-id="2c04a-112">Questo esempio illustra come impostare la proprietà di compatibilità del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="2c04a-112">This example shows how to set the data type compatibility property.</span></span> <span data-ttu-id="2c04a-113">Per impostazione predefinita, questa proprietà è impostata su 0 quando si utilizza [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="2c04a-113">By default, this is set to 0 when you are using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="2c04a-114">Se sir imposta il valore su 80, il provider [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client fa in modo che le colonne di tipo `xml` e di tipo definito dall'utente appaiano come tipi di dati [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2c04a-114">If you set the value to 80, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client provider will make `xml` and user-defined type columns appear as [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] data types.</span></span> <span data-ttu-id="2c04a-115">Vale a dire: rispettivamente DBTYPE_WSTR e DBTYPE_BYTES.</span><span class="sxs-lookup"><span data-stu-id="2c04a-115">This would be DBTYPE_WSTR and DBTYPE_BYTES, respectively.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2c04a-116">Native Client deve essere installato anche nel computer client e la stringa di connessione deve specificare che venga usato come provider di dati tramite "`Provider=SQLNCLI11;...`".</span><span class="sxs-lookup"><span data-stu-id="2c04a-116">Native Client must also be installed on the client computer and the connection string must specify it for use as the data provider with "`Provider=SQLNCLI11;...`".</span></span>  
  
#### <a name="to-test-this-example"></a><span data-ttu-id="2c04a-117">Per testare l'esempio</span><span class="sxs-lookup"><span data-stu-id="2c04a-117">To test this example</span></span>  
  
1.  <span data-ttu-id="2c04a-118">Verificare che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sia installato e che MDAC 2 versione 6.0, o una versione successiva, sia installato sul computer client.</span><span class="sxs-lookup"><span data-stu-id="2c04a-118">Verify that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client is installed and that MDAC 2.6.0or later is available on the client computer.</span></span>  
  
     <span data-ttu-id="2c04a-119">Per altre informazioni, vedere [Programmazione in SQL Server Native Client](../native-client/sql-server-native-client-programming.md).</span><span class="sxs-lookup"><span data-stu-id="2c04a-119">For more information, see [SQL Server Native Client Programming](../native-client/sql-server-native-client-programming.md).</span></span>  
  
2.  <span data-ttu-id="2c04a-120">Verificare che il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sia installato.</span><span class="sxs-lookup"><span data-stu-id="2c04a-120">Verify that the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
     <span data-ttu-id="2c04a-121">Questo esempio richiede il database di esempio [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c04a-121">This example requires the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sample database.</span></span>  
  
3.  <span data-ttu-id="2c04a-122">Copiare il codice riportato precedentemente in questo argomento nel proprio editor di testo o di codice.</span><span class="sxs-lookup"><span data-stu-id="2c04a-122">Copy the code shown previously in this topic and paste the code into your text or code editor.</span></span> <span data-ttu-id="2c04a-123">Salvare il file col nome HandlingXmlDataType.vbs.</span><span class="sxs-lookup"><span data-stu-id="2c04a-123">Save the file as HandlingXmlDataType.vbs.</span></span>  
  
4.  <span data-ttu-id="2c04a-124">Modificare lo script come necessario per l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2c04a-124">Modify the script as required for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation and save your changes.</span></span>  
  
     <span data-ttu-id="2c04a-125">Ad esempio, la stringa `MyServer` va sostituita con `(local)` o con il nome effettivo del server sul quale è installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c04a-125">For example, where `MyServer` is specified, you should replace it with either `(local)` or the actual name of the server on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed.</span></span>  
  
5.  <span data-ttu-id="2c04a-126">Eseguire HandlingXmlDataType.vbs e lo script.</span><span class="sxs-lookup"><span data-stu-id="2c04a-126">Run HandlingXmlDataType.vbs and execute the script.</span></span>  
  
 <span data-ttu-id="2c04a-127">Si dovrebbe ottenere un risultato simile a quello riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2c04a-127">The results should be similar to the following sample output:</span></span>  
  
```  
Row 1  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>1500000</AnnualSales>  
  <AnnualRevenue>150000</AnnualRevenue>  
  <BankName>Primary International</BankName>  
  <BusinessType>OS</BusinessType>  
  <YearOpened>1974</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>38000</SquareFeet>  
  <Brands>3</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>40</NumberEmployees>  
</StoreSurvey>  
  
Row 2  
  
<StoreSurvey xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/StoreSurvey">  
  <AnnualSales>300000</AnnualSales>  
  <AnnualRevenue>30000</AnnualRevenue>  
  <BankName>United Security</BankName>  
  <BusinessType>BM</BusinessType>  
  <YearOpened>1976</YearOpened>  
  <Specialty>Road</Specialty>  
  <SquareFeet>6000</SquareFeet>  
  <Brands>2</Brands>  
  <Internet>DSL</Internet>  
  <NumberEmployees>5</NumberEmployees>  
</StoreSurvey>  
```  
  
## <a name="handling-xml-from-an-xml-type-column-by-using-adonet"></a><span data-ttu-id="2c04a-128">Gestione di dati XML da una colonna di tipo xml utilizzando ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c04a-128">Handling XML from an xml Type Column by Using ADO.NET</span></span>  
 <span data-ttu-id="2c04a-129">Per gestire il codice XML da una `xml` colonna con tipo di dati utilizzando ADO.NET e l'oggetto, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] è possibile utilizzare il comportamento standard della `SqlCommand` classe.</span><span class="sxs-lookup"><span data-stu-id="2c04a-129">To handle XML from an `xml` data type column by using ADO.NET and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] you can use the standard behavior of the `SqlCommand` class.</span></span> <span data-ttu-id="2c04a-130">Ad esempio, una colonna con tipo di dati `xml` e i suoi valori possono essere recuperati in modo analogo a qualsiasi colonna SQL utilizzando un `SqlDataReader`. Tuttavia, se si desidera utilizzare il contenuto di una colonna con tipo di dati `xml` come XML, sarà anzitutto necessario assegnarne il contenuto a un tipo `XmlReader`.</span><span class="sxs-lookup"><span data-stu-id="2c04a-130">For example, an `xml` data type column and its values can be retrieved in the same way any SQL column is retrieved by using a `SqlDataReader`.However, if you want to work with the contents of an `xml` data type column as XML, you will first have to assign the contents to an `XmlReader` type.</span></span>  
  
 <span data-ttu-id="2c04a-131">Per altre informazioni e codice di esempio, vedere "Valori delle colonne XML in un lettore di dati" nella documentazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="2c04a-131">For more information and example code, see "XML Column Values in a Data Reader" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="handling-an-xml-type-column-in-parameters-by-using-adonet"></a><span data-ttu-id="2c04a-132">Gestione di una colonna di tipo xml in parametri utilizzando ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2c04a-132">Handling an xml Type Column in Parameters by Using ADO.NET</span></span>  
 <span data-ttu-id="2c04a-133">Per gestire un tipo di dati xml passato come parametro in ADO.NET e [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], è possibile specificare il valore come un'istanza del tipo di dati `SqlXml`.</span><span class="sxs-lookup"><span data-stu-id="2c04a-133">To handle an xml data type passed as a parameter in ADO.NET and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can supply the value as an instance of the `SqlXml` data type.</span></span> <span data-ttu-id="2c04a-134">Non è necessaria una gestione particolare in quanto le colonne di tipo di dati `xml` in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possono accettare valori di parametro in modo analogo ad altre colonne e tipi di dati, ad esempio `string` o `integer`.</span><span class="sxs-lookup"><span data-stu-id="2c04a-134">No special handling is involved, because `xml` data type columns in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can accept parameter values in the same way as other columns and data types, such as `string` or `integer`.</span></span>  
  
 <span data-ttu-id="2c04a-135">Per altre informazioni e codice di esempio, vedere "Valori XML come parametri di comando" nella documentazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="2c04a-135">For more information and example code, see "XML Values as Command Parameters" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c04a-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c04a-136">See Also</span></span>  
 [<span data-ttu-id="2c04a-137">Dati XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2c04a-137">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
