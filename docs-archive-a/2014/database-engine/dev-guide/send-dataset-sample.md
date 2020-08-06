---
title: Esempio Send DataSet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: d10dacbc-1b0f-4a4b-b53b-83eae2a6d809
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: de50007641dd39dc7aa2bcb16ea8da9fde4cabb2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638072"
---
# <a name="send-dataset-sample"></a><span data-ttu-id="85ff7-102">Esempio Send DataSet</span><span class="sxs-lookup"><span data-stu-id="85ff7-102">Send DataSet Sample</span></span>
  <span data-ttu-id="85ff7-103">Nell'esempio Send `DataSet` viene illustrato come restituire un oggetto `DataSet` basato su ADO.NET all'interno di una stored procedure sul lato server basata su Common Language Runtime (CLR) come set di risultati al client.</span><span class="sxs-lookup"><span data-stu-id="85ff7-103">The Send `DataSet` sample demonstrates how to return an ADO.NET based `DataSet` within a server side common language runtime (CLR)-based stored procedure as a result set to the client.</span></span> <span data-ttu-id="85ff7-104">Questa operazione è utile, ad esempio, quando tramite una stored procedure di questo tipo vengono inseriti dati in un oggetto `DataSet` utilizzando i risultati di una query e vengono modificati i dati contenuti in tale oggetto `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="85ff7-104">This is useful, for example, when such a stored procedure fills a `DataSet` using the results of a query, and then manipulates the data that is contained in that `DataSet`.</span></span> <span data-ttu-id="85ff7-105">In alternativa, è utile se tramite la stored procedure viene creato e popolato un oggetto `DataSet` da zero. L'esempio è composto da due classi, `DataSetUtilities` e `TestSendDataSet`.</span><span class="sxs-lookup"><span data-stu-id="85ff7-105">Alternatively this is useful if the stored procedure creates and populates a `DataSet` from scratch.The sample is composed of two classes, `DataSetUtilities` and `TestSendDataSet`.</span></span> <span data-ttu-id="85ff7-106">Il metodo `SendDataSet` sulla classe `DataSetUtilities` implementa un modo generico per trasmettere il contenuto di un'istanza di un oggetto `DataSet` al client.</span><span class="sxs-lookup"><span data-stu-id="85ff7-106">The method `SendDataSet` on the `DataSetUtilities` class implements a general-purpose way to transmit the contents of a `DataSet` instance to the client.</span></span> <span data-ttu-id="85ff7-107">Il metodo `DoTest` definito sulla classe `TestSendDataSet` consente di verificare che il metodo `SendDataSet` funzioni, creando un oggetto `DataSet` e inserendovi dati dalla stored procedure Transact-SQL `uspGetTwoBOMTestData`.</span><span class="sxs-lookup"><span data-stu-id="85ff7-107">The `DoTest` method that is defined on the `TestSendDataSet` class verifies that the `SendDataSet` method works by creating a `DataSet` and filling it with data from the `uspGetTwoBOMTestData` Transact-SQL stored procedure.</span></span> <span data-ttu-id="85ff7-108">La stored procedure `uspGetTwoBOMTestData` consente di eseguire la stored procedure `uspGetBillOfMaterials` Transact-SQL due volte per eseguire in modo ricorsivo la query per la distinta base di due prodotti specificati come parametri della stored procedure `usp_GetTwoBOMTestData`.</span><span class="sxs-lookup"><span data-stu-id="85ff7-108">The `uspGetTwoBOMTestData` runs the Transact-SQL stored procedure `uspGetBillOfMaterials` twice to recursively query for the bill of materials for two products specified as parameters to the `usp_GetTwoBOMTestData` stored procedure.</span></span> <span data-ttu-id="85ff7-109">Generalmente, dopo essere stati inseriti nel set di dati, i dati vengono modificati prima di richiamare `SendDataSet` per recapitare i dati del set di dati come set di risultati al client.</span><span class="sxs-lookup"><span data-stu-id="85ff7-109">Ordinarily, after filling the data set, the data would be modified before invoking `SendDataSet` to deliver the data within the data set as a result set to the client.</span></span> <span data-ttu-id="85ff7-110">Per motivi di semplicità, nell'esempio vengono restituiti i dati senza apportare modifiche.</span><span class="sxs-lookup"><span data-stu-id="85ff7-110">For simplicity, this sample returns the data without modification.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="85ff7-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="85ff7-111">Prerequisites</span></span>  
 <span data-ttu-id="85ff7-112">Per creare ed eseguire questo progetto, è necessario installare il software seguente:</span><span class="sxs-lookup"><span data-stu-id="85ff7-112">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="85ff7-113">o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="85ff7-113">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="85ff7-114">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express è disponibile gratuitamente nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sito Web [di documentazione ed esempi di](https://www.microsoft.com/sql-server/sql-server-editions-express)Express</span><span class="sxs-lookup"><span data-stu-id="85ff7-114">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="85ff7-115">Database AdventureWorks, disponibile nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sito Web [per sviluppatori di](https://go.microsoft.com/fwlink/?linkid=62796)</span><span class="sxs-lookup"><span data-stu-id="85ff7-115">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="85ff7-116">.NET Framework SDK 2.0 o versione successiva oppure Microsoft Visual Studio 2005 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="85ff7-116">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="85ff7-117">.NET Framework SDK è disponibile gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="85ff7-117">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="85ff7-118">È necessario inoltre che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85ff7-118">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="85ff7-119">Per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usata deve essere abilitata l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="85ff7-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="85ff7-120">Per abilitare l'integrazione con CLR, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85ff7-120">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="85ff7-121">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="85ff7-121">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="85ff7-122">Eseguire i comandi [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="85ff7-122">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="85ff7-123">Per abilitare CLR, è necessario disporre dell'autorizzazione `ALTER SETTINGS` a livello di server, che viene assegnata implicitamente ai membri dei ruoli predefiniti del server `sysadmin` e `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="85ff7-123">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="85ff7-124">Il database AdventureWorks deve essere installato nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in uso.</span><span class="sxs-lookup"><span data-stu-id="85ff7-124">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="85ff7-125">Se non si è un amministratore per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanza di in uso, è necessario disporre di un amministratore per concedere l'autorizzazione **CreateAssembly** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="85ff7-125">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly**  permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="85ff7-126">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="85ff7-126">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="85ff7-127">Creare ed eseguire l'esempio tramite le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="85ff7-127">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="85ff7-128">Aprire un prompt dei comandi di .NET Framework o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="85ff7-128">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="85ff7-129">Se necessario, creare una directory per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="85ff7-129">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="85ff7-130">Per questo esempio verrà utilizzata la directory C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="85ff7-130">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="85ff7-131">In c:\MySample creare `SendDataSet.vb` (per l'esempio Visual Basic) o `SendDataSet.cs` (per l'esempio C#) e copiare nel file il codice di esempio appropriato, Visual Basic o C#, riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="85ff7-131">In c:\MySample, create `SendDataSet.vb` (for the Visual Basic sample) or `SendDataSet.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="85ff7-132">Compilare il codice di esempio nell'assembly necessario dal prompt della riga di comando eseguendo una delle istruzioni seguenti, a seconda del linguaggio scelto.</span><span class="sxs-lookup"><span data-stu-id="85ff7-132">Compile the sample code into the required assembly from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll  /target:library SendDataSet.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /target:library SendDataSet.cs`  
  
5.  <span data-ttu-id="85ff7-133">Copiare il codice di installazione [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `Install.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="85ff7-133">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="85ff7-134">Se l'esempio è installato in una directory diversa da `C:\MySample\`, modificare il file `Install.sql` come indicato, in modo che punti al percorso appropriato.</span><span class="sxs-lookup"><span data-stu-id="85ff7-134">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
7.  <span data-ttu-id="85ff7-135">Distribuire l'assembly, la stored procedure e le funzioni eseguendo</span><span class="sxs-lookup"><span data-stu-id="85ff7-135">Deploy the assembly, stored procedure and functions by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
8.  <span data-ttu-id="85ff7-136">Copiare lo script di test [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `test.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="85ff7-136">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] test script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
9. <span data-ttu-id="85ff7-137">Copiare lo script di pulizia [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `cleanup.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="85ff7-137">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
10. <span data-ttu-id="85ff7-138">Eseguire lo script con il comando seguente</span><span class="sxs-lookup"><span data-stu-id="85ff7-138">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="85ff7-139">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="85ff7-139">Sample Code</span></span>  
 <span data-ttu-id="85ff7-140">Di seguito sono illustrati i listati di codice per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="85ff7-140">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="85ff7-141">C#</span><span class="sxs-lookup"><span data-stu-id="85ff7-141">C#</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
  
    public static class DataSetUtilities  
    {  
  
        public static void SendDataSet(DataSet ds)  
        {  
            if (ds == null)  
            {  
                throw new ArgumentException("SendDataSet requires a non-null data set.");  
            }  
            else  
            {  
                foreach (DataTable dt in ds.Tables)  
                {  
                    SendDataTable(dt);  
                }  
            }  
        }  
  
        public static void SendDataTable(DataTable dt)  
        {  
            bool[] coerceToString;  // Do we need to coerce this column to string?  
            SqlMetaData[] metaData = ExtractDataTableColumnMetaData(dt, out coerceToString);  
  
            SqlDataRecord record = new SqlDataRecord(metaData);  
            SqlPipe pipe = SqlContext.Pipe;  
            pipe.SendResultsStart(record);  
            try  
            {  
                foreach (DataRow row in dt.Rows)  
                {  
                    for (int index = 0; index < record.FieldCount; index++)  
                    {  
                        object value = row[index];  
                        if (null != value && coerceToString[index])  
                            value = value.ToString();  
                        record.SetValue(index, value);  
                    }  
  
                    pipe.SendResultsRow(record);  
                }  
            }  
            finally  
            {  
                pipe.SendResultsEnd();  
            }  
        }  
  
        private static SqlMetaData[] ExtractDataTableColumnMetaData(DataTable dt, out bool[] coerceToString)  
        {  
            SqlMetaData[] metaDataResult = new SqlMetaData[dt.Columns.Count];  
            coerceToString = new bool[dt.Columns.Count];  
            for (int index = 0; index < dt.Columns.Count; index++)  
            {  
                DataColumn column = dt.Columns[index];  
                metaDataResult[index] = SqlMetaDataFromColumn(column, out coerceToString[index]);  
            }  
  
            return metaDataResult;  
        }  
  
        private static Exception InvalidDataTypeCode(TypeCode code)  
        {  
            return new ArgumentException("Invalid type: " + code);  
        }  
  
        private static Exception UnknownDataType(Type clrType)  
        {  
            return new ArgumentException("Unknown type: " + clrType);  
        }  
  
        private static SqlMetaData SqlMetaDataFromColumn(DataColumn column, out bool coerceToString)  
        {  
            coerceToString = false;  
            SqlMetaData sql_md = null;  
            Type clrType = column.DataType;  
            string name = column.ColumnName;  
            switch (Type.GetTypeCode(clrType))  
            {  
                case TypeCode.Boolean: sql_md = new SqlMetaData(name, SqlDbType.Bit); break;  
                case TypeCode.Byte: sql_md = new SqlMetaData(name, SqlDbType.TinyInt); break;  
                case TypeCode.Char: sql_md = new SqlMetaData(name, SqlDbType.NVarChar, 1); break;  
                case TypeCode.DateTime: sql_md = new SqlMetaData(name, SqlDbType.DateTime); break;  
                case TypeCode.DBNull: throw InvalidDataTypeCode(TypeCode.DBNull);  
                case TypeCode.Decimal: sql_md = new SqlMetaData(name, SqlDbType.Decimal, 18, 0); break;  
                case TypeCode.Double: sql_md = new SqlMetaData(name, SqlDbType.Float); break;  
                case TypeCode.Empty: throw InvalidDataTypeCode(TypeCode.Empty);  
                case TypeCode.Int16: sql_md = new SqlMetaData(name, SqlDbType.SmallInt); break;  
                case TypeCode.Int32: sql_md = new SqlMetaData(name, SqlDbType.Int); break;  
                case TypeCode.Int64: sql_md = new SqlMetaData(name, SqlDbType.BigInt); break;  
                case TypeCode.SByte: throw InvalidDataTypeCode(TypeCode.SByte);  
                case TypeCode.Single: sql_md = new SqlMetaData(name, SqlDbType.Real); break;  
                case TypeCode.String: sql_md = new SqlMetaData(name, SqlDbType.NVarChar, column.MaxLength);  
                    break;  
                case TypeCode.UInt16: throw InvalidDataTypeCode(TypeCode.UInt16);  
                case TypeCode.UInt32: throw InvalidDataTypeCode(TypeCode.UInt32);  
                case TypeCode.UInt64: throw InvalidDataTypeCode(TypeCode.UInt64);  
                case TypeCode.Object:  
                    sql_md = SqlMetaDataFromObjectColumn(name, column, clrType);  
                    if (sql_md == null)  
                    {  
                        // Unknown type, try to treat it as string;  
                        sql_md = new SqlMetaData(name, SqlDbType.NVarChar, column.MaxLength);  
                        coerceToString = true;  
                    }  
                    break;  
  
                default: throw UnknownDataType(clrType);  
            }  
  
            return sql_md;  
        }  
  
        private static SqlMetaData SqlMetaDataFromObjectColumn(string name, DataColumn column, Type clrType)  
        {  
            SqlMetaData sql_md = null;  
            if (clrType == typeof(System.Byte[]) || clrType == typeof(SqlBinary) || clrType == typeof(SqlBytes) ||  
        clrType == typeof(System.Char[]) || clrType == typeof(SqlString) || clrType == typeof(SqlChars))  
                sql_md = new SqlMetaData(name, SqlDbType.VarBinary, column.MaxLength);  
            else if (clrType == typeof(System.Guid))  
                sql_md = new SqlMetaData(name, SqlDbType.UniqueIdentifier);  
            else if (clrType == typeof(System.Object))  
                sql_md = new SqlMetaData(name, SqlDbType.Variant);  
            else if (clrType == typeof(SqlBoolean))  
                sql_md = new SqlMetaData(name, SqlDbType.Bit);  
            else if (clrType == typeof(SqlByte))  
                sql_md = new SqlMetaData(name, SqlDbType.TinyInt);  
            else if (clrType == typeof(SqlDateTime))  
                sql_md = new SqlMetaData(name, SqlDbType.DateTime);  
            else if (clrType == typeof(SqlDouble))  
                sql_md = new SqlMetaData(name, SqlDbType.Float);  
            else if (clrType == typeof(SqlGuid))  
                sql_md = new SqlMetaData(name, SqlDbType.UniqueIdentifier);  
            else if (clrType == typeof(SqlInt16))  
                sql_md = new SqlMetaData(name, SqlDbType.SmallInt);  
            else if (clrType == typeof(SqlInt32))  
                sql_md = new SqlMetaData(name, SqlDbType.Int);  
            else if (clrType == typeof(SqlInt64))  
                sql_md = new SqlMetaData(name, SqlDbType.BigInt);  
            else if (clrType == typeof(SqlMoney))  
                sql_md = new SqlMetaData(name, SqlDbType.Money);  
            else if (clrType == typeof(SqlDecimal))  
                sql_md = new SqlMetaData(name, SqlDbType.Decimal, SqlDecimal.MaxPrecision, 0);  
            else if (clrType == typeof(SqlSingle))  
                sql_md = new SqlMetaData(name, SqlDbType.Real);  
            else if (clrType == typeof(SqlXml))  
                sql_md = new SqlMetaData(name, SqlDbType.Xml);  
            else  
                sql_md = null;  
  
            return sql_md;  
        }  
  
    }  
 public static class TestSendDataSet  
    {  
        private const string TestConnectionString = "context connection=true";  
        const int prod1ID = 750; //Product ID of Road-150 Red, 44 bicycle  
        const int prod2ID = 751; //Product ID of Road-150 Red, 48 bicycle  
  
        /// <summary>  
        /// Invoke a stored procedure to get some bill of material information and   
        /// fill a data set with the two result sets.  Return the data set to the client.  
        /// </summary>  
        public static void DoTest()  
        {  
            using (SqlConnection conn = new SqlConnection(TestConnectionString))  
            {  
                SqlCommand cmd = conn.CreateCommand();  
                cmd.CommandText = "usp_GetTwoBOMTestData";  
                cmd.CommandType = CommandType.StoredProcedure;  
  
                SqlParameter prod1Param = new SqlParameter("@ProductID1", SqlDbType.Int);  
                prod1Param.Value = prod1ID;  
                cmd.Parameters.Add(prod1Param);  
  
                SqlParameter prod2Param = new SqlParameter("@ProductID2", SqlDbType.Int);  
                prod2Param.Value = prod2ID;  
                cmd.Parameters.Add(prod2Param);  
  
                SqlParameter asOfDateParam = new SqlParameter("@AsOfDate", SqlDbType.DateTime);  
                asOfDateParam.Value = DateTime.Now;  
                cmd.Parameters.Add(asOfDateParam);  
  
                DataSet ds = new DataSet("TestData");  
                SqlDataAdapter sda = new SqlDataAdapter(cmd);  
                conn.Open();  
                sda.Fill(ds);  
  
// Normally, after filling the data set, rather than immediately returning it,   
// the data would be modified before invoking SendDataSet to deliver   
// the data within the data set as a result set to the client.  For simplicity   
// this sample simply returns the data.  
  
                DataSetUtilities.SendDataSet(ds);  
  
            }  
        }  
  
    }  
```  
  
 <span data-ttu-id="85ff7-142">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85ff7-142">Visual Basic</span></span>  
  
```  
Imports Microsoft.VisualBasic  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Diagnostics  
Imports System.Collections.Generic  
Imports System.Text  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Runtime.InteropServices  
  
Public Class DataSetUtilities  
  
    Public Shared Sub SendDataSet(ByVal ds As DataSet)  
        If ds Is Nothing Then  
            Throw New ArgumentException("SendDataSet requires a non-null data set.")  
        Else  
            For Each dt As DataTable In ds.Tables  
                SendDataTable(dt)  
            Next  
        End If  
    End Sub  
  
    Public Shared Sub SendDataTable(ByVal dt As DataTable)  
        Dim coerceToString() As Boolean = Nothing ' Do we need to coerce this column to string?  
        Dim metaData As SqlMetaData() = ExtractDataTableColumnMetaData(dt, coerceToString)  
  
        Dim record As New SqlDataRecord(metaData)  
        Dim pipe As SqlPipe = SqlContext.Pipe  
        pipe.SendResultsStart(record)  
  
        Try  
            For Each row As DataRow In dt.Rows  
                For index As Integer = 0 To record.FieldCount - 1  
                    Dim value As Object = row(index)  
                    If Nothing Is value AndAlso coerceToString(index) Then  
                        value = value.ToString()  
                    End If  
  
                    record.SetValue(index, value)  
                Next  
  
                pipe.SendResultsRow(record)  
            Next  
        Finally  
            pipe.SendResultsEnd()  
        End Try  
    End Sub  
  
    Private Shared Function ExtractDataTableColumnMetaData(ByVal dt As DataTable, <Out()> ByRef coerceToString() As Boolean) As SqlMetaData()  
        Dim metaDataResult(dt.Columns.Count - 1) As SqlMetaData  
        coerceToString = New Boolean(dt.Columns.Count - 1) {}  
        For index As Integer = 0 To dt.Columns.Count - 1  
            Dim column As DataColumn = dt.Columns(index)  
            metaDataResult(index) = SqlMetaDataFromColumn(column, coerceToString(index))  
        Next  
  
        Return metaDataResult  
    End Function  
    Private Shared Function InvalidDataTypeCode(ByVal code As TypeCode) As Exception  
        Return New ArgumentException("Invalid type: " & code.ToString())  
    End Function  
  
    Private Shared Function UnknownDataType(ByVal clrType As Type) As Exception  
        Return New ArgumentException("Unknown type: " & clrType.ToString())  
    End Function  
  
    Private Shared Function SqlMetaDataFromColumn(ByVal column As DataColumn, ByRef coerceToString As Boolean) As SqlMetaData  
        coerceToString = False  
        Dim sql_md As SqlMetaData = Nothing  
        Dim clrType As Type = column.DataType  
        Dim name As String = column.ColumnName  
        Select Case Type.GetTypeCode(clrType)  
            Case TypeCode.Boolean  
                sql_md = New SqlMetaData(name, SqlDbType.Bit)  
            Case TypeCode.Byte  
                sql_md = New SqlMetaData(name, SqlDbType.TinyInt)  
            Case TypeCode.Char  
                sql_md = New SqlMetaData(name, SqlDbType.NVarChar, 1)  
            Case TypeCode.DateTime  
                sql_md = New SqlMetaData(name, SqlDbType.DateTime)  
            Case TypeCode.DBNull  
                Throw InvalidDataTypeCode(TypeCode.DBNull)  
            Case TypeCode.Decimal  
                sql_md = New SqlMetaData(name, SqlDbType.Decimal)  
            Case TypeCode.Double  
                sql_md = New SqlMetaData(name, SqlDbType.Float)  
            Case TypeCode.Empty  
                Throw InvalidDataTypeCode(TypeCode.Empty)  
            Case TypeCode.Int16  
                sql_md = New SqlMetaData(name, SqlDbType.SmallInt)  
            Case TypeCode.Int32  
                sql_md = New SqlMetaData(name, SqlDbType.Int)  
            Case TypeCode.Int64  
                sql_md = New SqlMetaData(name, SqlDbType.BigInt)  
            Case TypeCode.SByte  
                Throw InvalidDataTypeCode(TypeCode.SByte)  
            Case TypeCode.Single  
                sql_md = New SqlMetaData(name, SqlDbType.Real)  
            Case TypeCode.String  
                sql_md = New SqlMetaData(name, SqlDbType.NVarChar, column.MaxLength)  
            Case TypeCode.UInt16  
                Throw InvalidDataTypeCode(TypeCode.UInt16)  
            Case TypeCode.UInt32  
                Throw InvalidDataTypeCode(TypeCode.UInt32)  
            Case TypeCode.UInt64  
                Throw InvalidDataTypeCode(TypeCode.UInt64)  
            Case TypeCode.Object  
                sql_md = SqlMetaDataFromObjectColumn(name, column, clrType)  
                If sql_md Is Nothing Then  
                    ' Unknown type, try to treat it as string  
                    sql_md = New SqlMetaData(name, SqlDbType.NVarChar, column.MaxLength)  
                    coerceToString = True  
                End If  
            Case Else  
                Throw UnknownDataType(clrType)  
        End Select  
  
        Return sql_md  
    End Function  
  
    Private Shared Function SqlMetaDataFromObjectColumn(ByVal name As String, ByVal column As DataColumn, ByVal clrType As Type) As SqlMetaData  
        Dim sql_md As SqlMetaData = Nothing  
  
        If (clrType Is GetType(System.Byte()) OrElse clrType Is GetType(SqlBinary) OrElse clrType Is GetType(SqlBytes) _  
            OrElse clrType Is GetType(System.Char()) OrElse clrType Is GetType(SqlString) OrElse clrType Is GetType(SqlChars)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.VarBinary, column.MaxLength)  
        ElseIf (clrType Is GetType(System.Guid)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.UniqueIdentifier)  
        ElseIf (clrType Is GetType(System.Object)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Variant)  
        ElseIf (clrType Is GetType(SqlBoolean)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Bit)  
        ElseIf (clrType Is GetType(SqlByte)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.TinyInt)  
        ElseIf (clrType Is GetType(SqlDateTime)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.DateTime)  
        ElseIf (clrType Is GetType(SqlDouble)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Float)  
        ElseIf (clrType Is GetType(SqlGuid)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.UniqueIdentifier)  
        ElseIf (clrType Is GetType(SqlInt16)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.SmallInt)  
        ElseIf (clrType Is GetType(SqlInt32)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Int)  
        ElseIf (clrType Is GetType(SqlInt64)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.BigInt)  
        ElseIf (clrType Is GetType(SqlMoney)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Money)  
        ElseIf (clrType Is GetType(SqlDecimal)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Decimal, SqlDecimal.MaxPrecision, 0)  
        ElseIf (clrType Is GetType(SqlSingle)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Real)  
        ElseIf (clrType Is GetType(SqlXml)) Then  
            sql_md = New SqlMetaData(name, SqlDbType.Xml)  
        Else  
            sql_md = Nothing  
        End If  
  
        Return sql_md  
    End Function  
End Class  
  
Public Class TestSendDataSet  
    Private Const TestConnectionString As String = "context connection=true"  
    Private Const prod1ID As Integer = 750  'Product ID of Road-150 Red, 44 bicycle  
    Private Const prod2ID As Integer = 751  'Product ID of Road-150 Red, 48 bicycle  
  
    ''' <summary>  
    ''' Invoke a stored procedure to get some bill of material information and   
    ''' fill a data set with the two result sets.  Return the data set to the client.  
  
    <SqlProcedure(Name:="usp_TestSendDataSet")> _  
    Public Shared Sub DoTest()  
        Dim conn As New SqlConnection(TestConnectionString)  
        Try  
            Dim cmd As SqlCommand = conn.CreateCommand()  
            cmd.CommandText = "usp_GetTwoBOMTestData"  
            cmd.CommandType = CommandType.StoredProcedure  
  
            Dim prod1Param As New SqlParameter("@ProductID1", SqlDbType.Int)  
            prod1Param.Value = prod1ID  
            cmd.Parameters.Add(prod1Param)  
  
            Dim prod2Param As New SqlParameter("@ProductID2", SqlDbType.Int)  
            prod2Param.Value = prod2ID  
            cmd.Parameters.Add(prod2Param)  
  
            Dim asOfDateParam As New SqlParameter("@AsOfDate", SqlDbType.DateTime)  
            asOfDateParam.Value = DateTime.Now  
            cmd.Parameters.Add(asOfDateParam)  
  
            Dim ds As New DataSet("TestData")  
            Dim sda As New SqlDataAdapter(cmd)  
            conn.Open()  
            sda.Fill(ds)  
  
            ' Normally, after filling the data set, rather than immediately returning it,   
            ' the data would be modified before invoking SendDataSet to deliver   
            ' the data within the data set as a result set to the client.  For simplicity   
            ' this sample simply returns the data.  
            DataSetUtilities.SendDataSet(ds)  
        Finally  
            conn.Dispose()  
        End Try  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="85ff7-143">Di seguito è illustrato lo script di installazione [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`) che consente la distribuzione dell'assembly e la creazione delle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="85ff7-143">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedures.</span></span>  
  
```  
USE AdventureWorks;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'usp_GetTwoBOMTestData')  
DROP PROCEDURE usp_GetTwoBOMTestData;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'usp_TestSendDataSet')  
DROP PROCEDURE usp_TestSendDataSet;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = N'SendDataSet')   
DROP ASSEMBLY SendDataSet;  
GO  
  
-- Procedure used to generate test data to fill the data set being returned to the client  
CREATE PROCEDURE usp_GetTwoBOMTestData  
(  
@ProductID1 int,  
@ProductID2 int,  
@AsOfDate DateTime  
)  
AS  
BEGIN  
EXEC uspGetBillOfMaterials @ProductID1, @AsOfDate;  
EXEC uspGetBillOfMaterials @ProductID2, @AsOfDate;  
END;  
GO  
  
DECLARE @SamplesPath nvarchar(1024)  
-- You may need to modify the value of the this variable if you have installed the sample someplace other than the default location.  
Set @SamplesPath = N'C:\MySample\'  
  
CREATE ASSEMBLY SendDataSet from @SamplesPath +'SendDataSet.dll'  
WITH PERMISSION_SET = Safe;  
GO  
  
CREATE PROCEDURE usp_TestSendDataSet  
AS  
EXTERNAL NAME [SendDataSet].[TestSendDataSet].[DoTest];  
GO  
```  
  
 <span data-ttu-id="85ff7-144">Di seguito è riportato lo script di test [!INCLUDE[tsql](../../includes/tsql-md.md)] (`test.sql`) che consente di testare l'esempio.</span><span class="sxs-lookup"><span data-stu-id="85ff7-144">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] test script (`test.sql`), which tests the sample.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
EXEC usp_TestSendDataSet  
GO  
```  
  
 <span data-ttu-id="85ff7-145">Il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di rimuovere l'assembly e la stored procedure dal database.</span><span class="sxs-lookup"><span data-stu-id="85ff7-145">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'usp_GetTwoBOMTestData')  
DROP PROCEDURE usp_GetTwoBOMTestData;  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE name = N'usp_TestSendDataSet')  
DROP PROCEDURE usp_TestSendDataSet;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE name = N'SendDataSet')   
DROP ASSEMBLY SendDataSet;  
GO  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="85ff7-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85ff7-146">See Also</span></span>  
 [<span data-ttu-id="85ff7-147">Scenari di utilizzo ed esempi per l'integrazione con CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="85ff7-147">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
