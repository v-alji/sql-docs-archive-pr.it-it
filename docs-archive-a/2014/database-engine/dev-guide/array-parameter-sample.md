---
title: Esempio di parametro di matrice | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 5d7034ca-ce88-4a7e-8dd9-82f867479e7f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b9afbf13c3797239d142642d9dc6e9ddf9690472
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716712"
---
# <a name="array-parameter-sample"></a><span data-ttu-id="3125a-102">Esempio Array Parameter</span><span class="sxs-lookup"><span data-stu-id="3125a-102">Array Parameter Sample</span></span>
  <span data-ttu-id="3125a-103">Talvolta può risultare utile creare, aggiornare o eliminare un set di righe in un database.</span><span class="sxs-lookup"><span data-stu-id="3125a-103">Sometimes it is useful to create, update, or delete a set of rows in a database.</span></span> <span data-ttu-id="3125a-104">Sono disponibili diversi modi per eseguire queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="3125a-104">There are several approaches you could use to achieve that goal.</span></span> <span data-ttu-id="3125a-105">Uno di questi consiste nel passare una matrice di informazioni da un client a una stored procedure basata sull'integrazione con CLR nel server mediante un tipo di dati per l'integrazione con CLR definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3125a-105">One of them is to pass an array of information from a client to a common language runtime (CLR) integration stored procedure on the server by using a CLR integration user-defined data type.</span></span> <span data-ttu-id="3125a-106">La natura di tale tipo di dati limita a 8.000 byte le dimensioni dei dati forniti al server.</span><span class="sxs-lookup"><span data-stu-id="3125a-106">The nature of such user-defined data types limits the size of the data provided to the server to 8000 bytes.</span></span> <span data-ttu-id="3125a-107">Questa opzione non è pertanto utile in caso di dati complessi o di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="3125a-107">Therefore, this approach is not satisfactory for large or complex data.</span></span> <span data-ttu-id="3125a-108">Se i dati disponibili sono semplici e di piccole dimensioni, questa opzione risulta più efficace rispetto alla chiamata di una stored procedure per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="3125a-108">If the data that is being manipulated is small and simple, this approach can be much more efficient than calling a stored procedure for each row.</span></span> <span data-ttu-id="3125a-109">Passando una matrice, l'ordine dei dati viene mantenuto per le applicazioni in cui tale ordine è importante. Nell'esempio sono inclusi gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="3125a-109">By passing an array, the order of data is preserved for those applications where the order is significant.This sample contains the following:</span></span>  
  
1.  <span data-ttu-id="3125a-110">Il tipo di dati definito dall'utente `ContactTypeNames`,</span><span class="sxs-lookup"><span data-stu-id="3125a-110">The `ContactTypeNames` user-defined data type.</span></span> <span data-ttu-id="3125a-111">che include l'elenco dei nomi dei tipi di contatti desiderati.</span><span class="sxs-lookup"><span data-stu-id="3125a-111">This contains a list of desired contact type names.</span></span>  
  
2.  <span data-ttu-id="3125a-112">La stored procedure `usp_EnsureContactTypeNames` implementata come metodo Microsoft Visual C# o Microsoft Visual Basic,</span><span class="sxs-lookup"><span data-stu-id="3125a-112">The `usp_EnsureContactTypeNames` stored procedure implemented as a Microsoft Visual C# or Microsoft Visual Basic method.</span></span> <span data-ttu-id="3125a-113">che accetta un'istanza del tipo di dati definito dall'utente `ContactTypeNames` e inserisce nuove righe nella tabella `Person.ContactType` per i nomi di contatti inclusi nell'istanza del tipo di dati definito dall'utente e che non sono già presenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="3125a-113">This accepts an instance of the `ContactTypeNames` user-defined data type and inserts new rows in the `Person.ContactType` table for any contact names that are contained in the user-defined data type instance which are not already present in the table.</span></span>  
  
3.  <span data-ttu-id="3125a-114">L'applicazione console `TestArrayParameter`,</span><span class="sxs-lookup"><span data-stu-id="3125a-114">The `TestArrayParameter` console application.</span></span> <span data-ttu-id="3125a-115">che crea un'istanza del tipo di dati definito dall'utente `ContactTypeNames` sulla base dei parametri della riga di comando passati e quindi richiama la stored procedure `usp_EnsureContactTypeNames` passando l'istanza del tipo di dati definito dall'utente come parametro.</span><span class="sxs-lookup"><span data-stu-id="3125a-115">This creates an instance of the `ContactTypeNames` user-defined data type based on the command line parameters passed in, and then invokes the `usp_EnsureContactTypeNames` stored procedure by passing the user-defined data type instance as a parameter.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3125a-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="3125a-116">Prerequisites</span></span>  
 <span data-ttu-id="3125a-117">Per creare ed eseguire questo progetto, è necessario installare il software seguente:</span><span class="sxs-lookup"><span data-stu-id="3125a-117">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3125a-118">o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="3125a-118">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="3125a-119">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express è disponibile gratuitamente nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sito Web [di documentazione ed esempi di](https://www.microsoft.com/download/details.aspx?id=42299)Express</span><span class="sxs-lookup"><span data-stu-id="3125a-119">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/download/details.aspx?id=42299)</span></span>  
  
-   <span data-ttu-id="3125a-120">Database AdventureWorks, disponibile nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sito Web [per sviluppatori di](https://archive.codeplex.com/?p=SqlServerSamples)</span><span class="sxs-lookup"><span data-stu-id="3125a-120">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://archive.codeplex.com/?p=SqlServerSamples)</span></span>  
  
-   <span data-ttu-id="3125a-121">.NET Framework SDK 2.0 o versione successiva oppure Microsoft Visual Studio 2005 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="3125a-121">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="3125a-122">.NET Framework SDK è disponibile gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="3125a-122">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="3125a-123">È necessario inoltre che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3125a-123">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="3125a-124">Per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usata deve essere abilitata l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="3125a-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="3125a-125">Per abilitare l'integrazione con CLR, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3125a-125">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="3125a-126">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="3125a-126">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="3125a-127">Eseguire i comandi [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="3125a-127">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="3125a-128">Per abilitare CLR, è necessario disporre dell'autorizzazione `ALTER SETTINGS` a livello di server, che viene assegnata implicitamente ai membri dei ruoli predefiniti del server `sysadmin` e `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="3125a-128">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="3125a-129">Il database AdventureWorks deve essere installato nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in uso.</span><span class="sxs-lookup"><span data-stu-id="3125a-129">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="3125a-130">Se non si è un amministratore per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanza di in uso, è necessario disporre di un amministratore per concedere l'autorizzazione **CreateAssembly** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3125a-130">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly**  permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="3125a-131">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="3125a-131">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="3125a-132">Creare ed eseguire l'esempio tramite le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3125a-132">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="3125a-133">Aprire un prompt dei comandi di .NET Framework o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3125a-133">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="3125a-134">Se necessario, creare una directory per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="3125a-134">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="3125a-135">Per questo esempio verrà utilizzata la directory C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="3125a-135">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="3125a-136">In c:\MySample creare `ContactTypeNames.vb` (per l'esempio Visual Basic) o `ContactTypeNames.cs` (per l'esempio C#) e copiare nel file il codice di esempio appropriato, Visual Basic o C#, riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3125a-136">In c:\MySample, create `ContactTypeNames.vb` (for the Visual Basic sample) or `ContactTypeNames.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="3125a-137">Compilare il codice di esempio nell'assembly necessario dal prompt della riga di comando eseguendo una delle istruzioni seguenti, a seconda del linguaggio scelto.</span><span class="sxs-lookup"><span data-stu-id="3125a-137">Compile the sample code into the required assembly from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll  /target:library ContactTypeNames.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /target:library ContactTypeNames.cs`  
  
5.  <span data-ttu-id="3125a-138">In c:\MySample creare `Program.vb` (per l'esempio Visual Basic) o `Program.cs` (per l'esempio C#) e copiare nel file il codice di esempio appropriato, Visual Basic o C#, riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3125a-138">In c:\MySample, create `Program.vb` (for the Visual Basic sample) or `Program.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
6.  <span data-ttu-id="3125a-139">Individuare la riga appropriata nel file Program (intorno alla riga 24) e sostituire `XXX` con il nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3125a-139">Locate the appropriate line in the file Program (around line 24) and replace `XXX` with the name of your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
    -   `Dim connection As New SqlConnection("data source=XXX;initial catalog=AdventureWorks;Integrated Security=SSPI")`  
  
    -   `using (SqlConnection connection = new SqlConnection("data source=XXX;initial catalog=AdventureWorks;Integrated Security=SSPI"))`  
  
7.  <span data-ttu-id="3125a-140">Compilare il codice di esempio nell'eseguibile necessario dal prompt della riga di comando eseguendo una delle istruzioni seguenti, a seconda del linguaggio scelto.</span><span class="sxs-lookup"><span data-stu-id="3125a-140">Compile the sample code into the required executable from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Deployment.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Drawing.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Windows.Forms.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll,C:\MySample\ContactTypeNames.dll /out:TestArrayParameter Program.vb`  
  
    -   `Csc /reference:ContactTypeNames.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /out:TestArrayParameter.exe Program.cs`  
  
8.  <span data-ttu-id="3125a-141">Copiare il codice di installazione [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `Install.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="3125a-141">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
9. <span data-ttu-id="3125a-142">Se l'esempio è installato in una directory diversa da `C:\MySample\`, modificare il file `Install.sql` come indicato, in modo che punti al percorso appropriato.</span><span class="sxs-lookup"><span data-stu-id="3125a-142">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
10. <span data-ttu-id="3125a-143">Distribuire l'assembly, la stored procedure e le funzioni eseguendo</span><span class="sxs-lookup"><span data-stu-id="3125a-143">Deploy the assembly, stored procedure and functions by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
11. <span data-ttu-id="3125a-144">Testare l'applicazione eseguendo la riga seguente al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="3125a-144">Test the application by executing the following line at the command prompt:</span></span>  
  
    -   `TestArrayParameter "Executive Sales Representative" "Executive Sales Manager"`  
  
12. <span data-ttu-id="3125a-145">Copiare lo script di pulizia [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `cleanup.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="3125a-145">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
13. <span data-ttu-id="3125a-146">Eseguire lo script con il comando seguente</span><span class="sxs-lookup"><span data-stu-id="3125a-146">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="3125a-147">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="3125a-147">Sample Code</span></span>  
 <span data-ttu-id="3125a-148">Di seguito sono illustrati i listati di codice per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="3125a-148">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="3125a-149">Di seguito è riportato il codice per la libreria `ContactTypeNames.`</span><span class="sxs-lookup"><span data-stu-id="3125a-149">This is the code for the Library `ContactTypeNames.`</span></span>  
  
 <span data-ttu-id="3125a-150">C#</span><span class="sxs-lookup"><span data-stu-id="3125a-150">C#</span></span>  
  
```  
#region Using directives  
  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Globalization;  
using Microsoft.SqlServer.Server;  
  
#endregion  
  
    // This class is used to demonstrate passing an array of a fairly small number of reasonably small strings  
    // to a CLR integration based stored procedure on the server.  Because a UDT is limited to 8000 bytes  
    // this approach will not work well for large numbers of strings or long strings.  See the contact  
    // creation stored procedure in the AdventureWorks CLR integration sample for an alternative approach  
    // using XML which does not have these limitations.  
    [Serializable]  
    [Microsoft.SqlServer.Server.SqlUserDefinedType(Microsoft.SqlServer.Server.Format.UserDefined, IsByteOrdered = true, MaxByteSize = 8000)]  
    public class ContactTypeNames : INullable, Microsoft.SqlServer.Server.IBinarySerialize  
    {  
  
        #region Constructors  
        private const int maxByteSize = 8000;  
  
        public ContactTypeNames()  
        {  
        }  
  
        public ContactTypeNames(string[] names)  
        {  
            int numberOfCharacters = 0;  
            foreach (string name in names)  
            {  
                if (name.Length == 0)   
                    throw new ArgumentException("Zero length names are not allowed");  
                numberOfCharacters += name.Length;  
            }  
            int dataByteSize = numberOfCharacters*2 //UTF-16 characters take 2 bytes  
                + names.Length*4  //Four byte header for each string  
                + 4                 //Four byte header for null string at end  
                + 1;                //One byte boolean for null flag  
            if (dataByteSize >= maxByteSize)  
                throw new ArgumentException(string.Format(CultureInfo.InvariantCulture, "Data provided occupies {0} bytes but only {1} bytes "  
                    + "are available", dataByteSize, maxByteSize));  
  
            this._names = names;  
        }  
        #endregion  
  
        #region Accessors  
        public string[] GetTypeNameArray()  
        {  
            //Don't let caller modify our copy of the array  
            return (string[])_names.Clone();  
        }  
  
        //This has an odd API because we can only define Transact-SQL functions on static methods.  
        [SqlFunctionAttribute(FillRowMethodName = "FillNameRow")]  
        public static IEnumerable GetContactTypeNames(ContactTypeNames names)  
        {  
            if (names == null)  
                throw new ArgumentNullException("names");  
  
            return names.GetTypeNameArray();  
        }  
  
        public static void FillNameRow(object nameArrayElement, out string contactName)  
        {  
            contactName = (string)nameArrayElement;  
        }  
  
        #endregion  
  
        #region String Conversions  
  
        /// <summary>  
        /// The string format for contact type names is a sequence of names separated by commas  
        /// </summary>  
        /// <param name="s">a string containing contact type names separated by commas</param>  
        /// <returns>An instance of contact type name containing the specified names</returns>  
        [Microsoft.SqlServer.Server.SqlMethod(DataAccess = Microsoft.SqlServer.Server.DataAccessKind.None, IsDeterministic = false, IsMutator = false, IsPrecise = false,  
        SystemDataAccess = Microsoft.SqlServer.Server.SystemDataAccessKind.None)]  
        public static ContactTypeNames Parse(SqlString s)  
        {  
            if (s.IsNull)  
                return Null;  
            return new ContactTypeNames(s.Value.Split(new char[] {','}));  
        }  
  
        /// <summary>  
        /// Convert the contact type names to a string  
        /// </summary>  
        /// <returns>The contact type names separated by commas</returns>  
        public override string ToString()  
        {  
            if (this.IsNull)  
                return null;  
  
            StringBuilder sb = new StringBuilder();  
            foreach (string name in _names)  
            {  
                if (sb.Length > 0) sb.Append(", ");  
                sb.Append(name);  
            }  
  
            return sb.ToString();  
        }  
        #endregion  
  
        #region INullable Members  
  
        public static ContactTypeNames Null  
        {  
            get  
            {  
                return new ContactTypeNames();  
            }  
        }  
        public bool IsNull  
        {  
            get   
            {   
                return _names == null;   
            }  
        }  
  
        #endregion  
  
        #region IBinarySerialize Members  
  
        //Format:   
        //Byte 1: Null flag (boolean) (true = null)  
        //Byte 2 - 7994: Strings with 4 byte length headers,  
        //               last string is a zero length string.  
        //This format is in part dictated by how the BinaryWriter serializes strings.  See  
        //the Microsoft .NET Framework documentation on System.IO.BinaryWriter for more details.  
  
        public void Read(System.IO.BinaryReader r)  
        {  
            if (r.ReadBoolean())  
            {  
                _names = null;  
                return;  
            }  
            List<String> nameList = new List<String>();  
            string name;  
            while ((name = r.ReadString()).Length != 0)  
            {  
                nameList.Add(name);  
            }  
            _names = new string[nameList.Count];  
            nameList.CopyTo(_names);  
        }  
  
        public void Write(System.IO.BinaryWriter w)  
        {  
            if (w == null)  
                throw new ArgumentNullException("w");  
  
            w.Write(this.IsNull);  
            foreach (string name in _names)  
            {  
                w.Write(name);  
            }  
            w.Write(string.Empty);              
        }  
  
        #endregion  
  
        #region Private Implementation  
  
        private string[] _names;  
        #endregion  
    }  
```  
  
 <span data-ttu-id="3125a-151">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3125a-151">Visual Basic</span></span>  
  
```  
#Region "Using directives"  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports System.Collections  
Imports System.Collections.Generic  
Imports System.Text  
Imports System.Globalization  
Imports Microsoft.SqlServer.Server  
Imports System.Runtime.InteropServices  
#End Region  
  
' This class is used to demonstrate passing an array of a fairly small number of reasonably small strings  
' to a CLR integration based stored procedure on the server.  Because a UDT is limited to 8000 bytes  
' this approach will not work well for large numbers of strings or long strings.  See the contact  
' creation stored procedure in the AdventureWorks CLR integration sample for an alternative approach  
' using XML which does not have these limitations.  
<Serializable()> _  
<SqlUserDefinedType(Format.UserDefined, IsByteOrdered:=True, maxByteSize:=8000), CLSCompliant(False)> _  
Public Class ContactTypeNames  
    Implements INullable, IBinarySerialize  
  
#Region "Constructors"  
    Private Const maxByteSize As Integer = 8000  
  
    Public Sub New()  
    End Sub  
  
    Public Sub New(ByVal names() As String)  
        Dim numberOfCharacters As Integer = 0  
  
        For Each name As String In names  
            If name.Length = 0 Then  
                Throw New ArgumentException("Zero length names are not allowed")  
            End If  
  
            numberOfCharacters += name.Length  
        Next  
  
        'UTF-16 characters take 2 bytes  
        'Four byte header for each string  
        'Four byte header for null string at end  
        'One byte boolean for null flag  
        Dim dataByteSize As Integer = numberOfCharacters * 2 _  
            + names.Length * 4 _  
            + 4 _  
            + 1  
  
        If dataByteSize >= maxByteSize Then  
            Throw New ArgumentException(String.Format(CultureInfo.InvariantCulture, _  
                "Data provided occupies {0} bytes but only {1} bytes are available", _  
                dataByteSize, maxByteSize))  
        End If  
  
        Me._names = names  
    End Sub  
#End Region  
  
#Region "Accessors"  
  
    Public Function GetTypeNameArray() As String()  
        'Don't let caller modify our copy of the array  
        Return CType(Me._names.Clone(), String())  
    End Function  
  
    'This has an odd API because we can only define Transact-SQL functions on static methods.  
    <SqlFunction(FillRowMethodName:="FillNameRow", TableDefinition:="[Name] [Name]")> _  
    Public Shared Function GetContactTypeNames(ByVal names As ContactTypeNames) As IEnumerable  
        If names Is Nothing Then  
            Throw New ArgumentNullException("names")  
        End If  
  
        Return names.GetTypeNameArray()  
    End Function  
  
    Public Shared Sub FillNameRow(ByVal nameArrayElement As Object, <Out()> ByRef contactName As String)  
        contactName = CStr(nameArrayElement)  
    End Sub  
  
#End Region  
  
#Region "String Conversions"  
  
    ''' <summary>  
    ''' The string format for contact type names is a sequence of names separated by commas  
    ''' </summary>  
    ''' <param name="s">a string containing contact type names separated by commas</param>  
    ''' <returns>An instance of contact type name containing the specified names</returns>  
    <Microsoft.SqlServer.Server.SqlMethod(DataAccess:=Microsoft.SqlServer.Server.DataAccessKind.None, IsDeterministic:=False, IsMutator:=False, IsPrecise:=False, SystemDataAccess:=Microsoft.SqlServer.Server.SystemDataAccessKind.None)> _  
    Public Shared Function Parse(ByVal s As SqlString) As ContactTypeNames  
        If s.IsNull Then  
            Return Nothing  
        End If  
  
        Return New ContactTypeNames(s.Value.Split(New Char() {","c}))  
    End Function  
  
    ''' <summary>  
    ''' Convert the contact type names to a string  
    ''' </summary>  
    ''' <returns>The contact type names separated by commas</returns>  
    Public Overrides Function ToString() As String  
        If Me.IsNull Then  
            Return Nothing  
        End If  
  
        Dim sb As New StringBuilder()  
  
        For Each name As String In Me._names  
            If sb.Length > 0 Then  
                sb.Append(", ")  
            End If  
  
            sb.Append(name)  
        Next name  
  
        Return sb.ToString()  
    End Function  
#End Region  
  
#Region "INullable Members"  
  
    Shared ReadOnly Property Null() As ContactTypeNames  
        Get  
            Return New ContactTypeNames()  
        End Get  
    End Property  
  
    Public ReadOnly Property IsNull() As Boolean Implements INullable.IsNull  
        Get  
            Return Me._names Is Nothing  
        End Get  
    End Property  
  
#End Region  
  
#Region "IBinarySerialize Members"  
  
    'Format:   
    'Byte 1: Null flag (boolean) (true = null)  
    'Byte 2 - 7994: Strings with 4 byte length headers,  
    '               last string is a zero length string.  
    'This format is in part dictated by how the BinaryWriter serializes strings.  See  
    'the Microsoft .NET Framework documentation on System.IO.BinaryWriter for more details.  
    Public Sub Read(ByVal r As System.IO.BinaryReader) Implements IBinarySerialize.Read  
        If r.ReadBoolean() Then  
            Me._names = Nothing  
            Return  
        End If  
  
        Dim nameList As New List(Of String)  
        Dim name As String = r.ReadString()  
        While name.Length <> 0  
            nameList.Add(name)  
            name = r.ReadString()  
        End While  
  
        Me._names = New String(nameList.Count - 1) {}  
        nameList.CopyTo(Me._names)  
    End Sub  
  
    Public Sub Write(ByVal w As System.IO.BinaryWriter) Implements IBinarySerialize.Write  
        If w Is Nothing Then  
            Throw New ArgumentNullException("w")  
        End If  
  
        w.Write(Me.IsNull)  
  
        For Each name As String In Me._names  
            w.Write(name)  
        Next  
  
        w.Write(String.Empty)  
    End Sub  
  
#End Region  
  
#Region "Private Implementation"  
    Private _names() As String  
#End Region  
  
End Class  
```  
  
 <span data-ttu-id="3125a-152">Di seguito è riportato il codice per l'eseguibile di test.</span><span class="sxs-lookup"><span data-stu-id="3125a-152">This is the code for the test executable.</span></span>  
  
 <span data-ttu-id="3125a-153">C#</span><span class="sxs-lookup"><span data-stu-id="3125a-153">C#</span></span>  
  
```  
#region Using directives  
  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.IO;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using System.Data.SqlClient;  
#endregion  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            if (args.Length == 0)  
            {  
                Console.WriteLine("Usage: TestArrayParameter contactTypeName1 "  
                    + "contactTypeName2 ... contactTypeNamen");  
                return;  
            }  
            using (SqlConnection connection = new SqlConnection("data source=XXX;initial catalog=AdventureWorks;Integrated Security=SSPI"))  
            {  
                connection.Open();  
                ShowTypeNames(connection, "before any inserts");  
  
                SqlCommand command = connection.CreateCommand();  
                command.CommandText = "usp_EnsureContactTypeNames";  
                command.CommandType = CommandType.StoredProcedure;  
                SqlParameter namesParameter = new SqlParameter("@names", SqlDbType.Udt);  
                namesParameter.UdtTypeName = "ContactTypeNames";  
                namesParameter.Value = new ContactTypeNames(args);  
                command.Parameters.Add(namesParameter);  
                command.ExecuteNonQuery();  
  
                ShowTypeNames(connection, "after any inserts");  
  
            }  
  
        }  
  
        private static void ShowTypeNames(SqlConnection connection, string whenRan)  
        {  
            SqlCommand command = connection.CreateCommand();  
            command.CommandText = "SELECT Name FROM Person.ContactType ORDER BY Name";  
            using (SqlDataReader reader = command.ExecuteReader())  
            {  
                Console.BackgroundColor = ConsoleColor.Blue;  
                Console.Write("Contact type names {0}: ", whenRan);  
                Console.ResetColor();  
                bool first = true;  
                while (reader.Read())  
                {  
                    if (!first) Console.Write(", ");  
                    Console.Write(reader[0].ToString());  
                    first = false;  
                }  
                Console.WriteLine("");  
                Console.WriteLine("");  
            }  
  
        }  
    }  
```  
  
 <span data-ttu-id="3125a-154">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3125a-154">Visual Basic</span></span>  
  
```  
#Region "Using directives"  
Imports System  
Imports System.Collections.Generic  
Imports System.Text  
Imports System.IO  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports System.Data.SqlClient  
#End Region  
  
Class Program  
  
    Shared Sub Main(ByVal args() As String)  
        If args.Length = 0 Then  
            Console.WriteLine("Usage: TestArrayParameter contactTypeName1 " _  
                + "contactTypeName2 ... contactTypeNamen")  
            Return  
        End If  
  
        Dim connection As New SqlConnection("data source=XXX;initial catalog=AdventureWorks;Integrated Security=SSPI")  
        Try  
            connection.Open()  
            ShowTypeNames(connection, "Before any inserts")  
  
            Dim command As SqlCommand = connection.CreateCommand()  
            command.CommandText = "usp_EnsureContactTypeNames"  
            command.CommandType = CommandType.StoredProcedure  
            Dim namesParameter As New SqlParameter("@names", SqlDbType.Udt)  
            namesParameter.UdtTypeName = "ContactTypeNames"  
            namesParameter.Value = New ContactTypeNames(args)  
            command.Parameters.Add(namesParameter)  
            command.ExecuteNonQuery()  
  
            ShowTypeNames(connection, "After any inserts")  
        Finally  
            connection.Dispose()  
        End Try  
    End Sub  
  
    Private Shared Sub ShowTypeNames(ByVal connection As SqlConnection, ByVal whenRan As String)  
        Dim command As SqlCommand = connection.CreateCommand()  
        command.CommandText = "SELECT [Name] FROM [Person].[ContactType] ORDER BY Name"  
        Dim reader As SqlDataReader = command.ExecuteReader()  
        Try  
            Console.BackgroundColor = ConsoleColor.Blue  
            Console.Write("Contact type names {0}: ", whenRan)  
            Console.ResetColor()  
            Dim first As Boolean = True  
            While reader.Read()  
                If Not first Then  
                    Console.Write(", ")  
                End If  
  
                Console.Write(reader(0).ToString())  
                first = False  
            End While  
  
            Console.WriteLine("")  
            Console.WriteLine("")  
        Finally  
            reader.Dispose()  
        End Try  
  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="3125a-155">Di seguito è illustrato lo script di installazione [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`) che consente la distribuzione dell'assembly e la creazione della stored procedure e delle funzioni nel database.</span><span class="sxs-lookup"><span data-stu-id="3125a-155">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure and functions in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
-- Drop existing sprocs, type, and assemblies if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_EnsureContactTypeNames')  
DROP PROCEDURE usp_EnsureContactTypeNames;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE [name] = N'GetContactTypeNames' and (type = 'FS' or type = 'FT'))    
DROP FUNCTION [GetContactTypeNames];  
GO  
  
IF EXISTS (SELECT * FROM sys.types WHERE [name] = 'ContactTypeNames')  
DROP TYPE ContactTypeNames;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'ContactTypeNames')  
DROP ASSEMBLY ContactTypeNames;  
GO  
  
-- Add assemblies, type, and sproc  
  
DECLARE @SamplesPath nvarchar(1024)  
-- You may need to modify the value of the this variable if you have installed the sample someplace other than the default location.  
set @SamplesPath= 'C:\MySample\'  
CREATE ASSEMBLY ContactTypeNames   
FROM @SamplesPath + 'ContactTypeNames.dll'  
WITH permission_set = Safe;  
  
CREATE TYPE ContactTypeNames  
EXTERNAL NAME ContactTypeNames.ContactTypeNames;  
GO  
  
CREATE FUNCTION GetContactTypeNames  
(  
@names dbo.ContactTypeNames  
)  
RETURNS TABLE  
(  
[Name] [Name]  
)  
AS EXTERNAL NAME [ContactTypeNames].[ContactTypeNames].[GetContactTypeNames];  
GO  
  
CREATE PROCEDURE usp_EnsureContactTypeNames  
(  
@names dbo.ContactTypeNames  
)  
AS  
SET NOCOUNT ON;  
  
INSERT Person.ContactType ([Name])  
SELECT [Name] FROM GetContactTypeNames(@names) AS PotentialNames  
WHERE [Name] NOT IN (SELECT [Name] FROM Person.ContactType);   
GO  
```  
  
 <span data-ttu-id="3125a-156">Il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di rimuovere l'assembly e la stored procedure dal database.</span><span class="sxs-lookup"><span data-stu-id="3125a-156">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
DELETE Person.ContactType WHERE ContactTypeID > 20;  
GO  
  
-- Drop existing sprocs, type, and assemblies if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_EnsureContactTypeNames')  
DROP PROCEDURE usp_EnsureContactTypeNames;  
GO  
  
IF EXISTS (SELECT * FROM sys.objects WHERE [name] = N'GetContactTypeNames' and (type = 'FS' or type = 'FT'))    
DROP FUNCTION [GetContactTypeNames];  
GO  
  
IF EXISTS (SELECT * FROM sys.types WHERE [name] = 'ContactTypeNames')  
DROP TYPE ContactTypeNames;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'ContactTypeNames')  
DROP ASSEMBLY ContactTypeNames;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="3125a-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3125a-157">See Also</span></span>  
 [<span data-ttu-id="3125a-158">Scenari di utilizzo ed esempi per l'integrazione con CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="3125a-158">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
