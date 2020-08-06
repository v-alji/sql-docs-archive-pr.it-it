---
title: Caricamento ed esecuzione di un pacchetto remoto a livello di programmazione | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- remote packages [Integration Services]
ms.assetid: 9f6ef376-3408-46bf-b5fa-fc7b18c689c9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 06565140ae8ea3603461e2944e242aa91213de47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723999"
---
# <a name="loading-and-running-a-remote-package-programmatically"></a><span data-ttu-id="53630-102">Caricamento ed esecuzione di un pacchetto remoto a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="53630-102">Loading and Running a Remote Package Programmatically</span></span>
  <span data-ttu-id="53630-103">Per eseguire pacchetti remoti da un computer locale in cui non è installato [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], avviare i pacchetti in modo che vengano eseguiti nel computer remoto in cui è installato [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53630-103">To run remote packages from a local computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, start the packages so that they run on the remote computer on which [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is installed.</span></span> <span data-ttu-id="53630-104">A tale scopo, configurare il computer locale per l'utilizzo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, un servizio Web o un componente remoto per avviare i pacchetti nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="53630-104">You do this by having the local computer use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, a Web service, or a remote component to start the packages on the remote computer.</span></span> <span data-ttu-id="53630-105">Se si tenta di avviare i pacchetti remoti direttamente dal computer locale, i pacchetti verranno caricati e ne verrà effettuato il tentativo di esecuzione dal computer locale.</span><span class="sxs-lookup"><span data-stu-id="53630-105">If you try to start the remote packages directly from the local computer, the packages will load onto and try to run from the local computer.</span></span> <span data-ttu-id="53630-106">Se nel computer locale non è installato [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], i pacchetti non verranno eseguiti.</span><span class="sxs-lookup"><span data-stu-id="53630-106">If the local computer does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, the packages will not run.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53630-107">Non è possibile eseguire i pacchetti all'esterno di [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] in un computer client in cui [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] non è installato e le condizioni di licenza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] potrebbero non consentire l'installazione di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in computer aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="53630-107">You cannot run packages outside [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing might not let you install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="53630-108">è un componente server e non è ridistribuibile a computer client.</span><span class="sxs-lookup"><span data-stu-id="53630-108">is a server component and is not redistributable to client computers.</span></span>  
  
 <span data-ttu-id="53630-109">In alternativa, è possibile eseguire un pacchetto remoto da un computer locale in cui è installato [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53630-109">Alternately, you can run a remote package from a local computer that has [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed.</span></span> <span data-ttu-id="53630-110">Per altre informazioni, vedere [Caricamento ed esecuzione di un pacchetto locale a livello di programmazione](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span><span class="sxs-lookup"><span data-stu-id="53630-110">For more information, see [Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md).</span></span>  
  
##  <a name="running-a-remote-package-on-the-remote-computer"></a><a name="top"></a> <span data-ttu-id="53630-111">Esecuzione di un pacchetto remoto nel computer remoto</span><span class="sxs-lookup"><span data-stu-id="53630-111">Running a Remote Package on the Remote Computer</span></span>  
 <span data-ttu-id="53630-112">Come accennato in precedenza, è possibile eseguire un pacchetto remoto in un server remoto in vari modi:</span><span class="sxs-lookup"><span data-stu-id="53630-112">As mentioned above, there are multiple ways in which you can run a remote package on a remote server:</span></span>  
  
-   [<span data-ttu-id="53630-113">Usare SQL Server Agent per eseguire il pacchetto remoto a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="53630-113">Use SQL Server Agent to run the remote package programmatically</span></span>](#agent)  
  
-   [<span data-ttu-id="53630-114">Usare un servizio Web o un componente remoto per eseguire il pacchetto remoto a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="53630-114">Use a Web service or remote component to run the remote package programmatically</span></span>](#service)  
  
 <span data-ttu-id="53630-115">Quasi tutti i metodi utilizzati in questo argomento per caricare e salvare pacchetti richiedono un riferimento all'assembly `Microsoft.SqlServer.ManagedDTS`.</span><span class="sxs-lookup"><span data-stu-id="53630-115">Almost all the methods that are used in this topic to load and save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="53630-116">L'eccezione è l'approccio ADO.NET illustrato in questo argomento per l'esecuzione della **sp_start_job** stored procedure, che richiede solo un riferimento a `System.Data` .</span><span class="sxs-lookup"><span data-stu-id="53630-116">The exception is the ADO.NET approach demonstrated in this topic for executing the **sp_start_job** stored procedure, which requires only a reference to `System.Data`.</span></span> <span data-ttu-id="53630-117">Dopo aver aggiunto il riferimento all'assembly `Microsoft.SqlServer.ManagedDTS` in un nuovo progetto, importare lo spazio dei nomi <xref:Microsoft.SqlServer.Dts.Runtime> con un'istruzione `using` o `Imports`.</span><span class="sxs-lookup"><span data-stu-id="53630-117">After you add the reference to the `Microsoft.SqlServer.ManagedDTS` assembly in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
###  <a name="using-sql-server-agent-to-run-a-remote-package-programmatically-on-the-server"></a><a name="agent"></a> <span data-ttu-id="53630-118">Uso di SQL Server Agent per eseguire un pacchetto remoto a livello di programmazione nel server</span><span class="sxs-lookup"><span data-stu-id="53630-118">Using SQL Server Agent to Run a Remote Package Programmatically on the Server</span></span>  
 <span data-ttu-id="53630-119">Nell'esempio di codice seguente è illustrato come utilizzare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent a livello di programmazione per eseguire un pacchetto remoto nel server.</span><span class="sxs-lookup"><span data-stu-id="53630-119">The following code sample demonstrates how to programmatically use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to run a remote package on the server.</span></span> <span data-ttu-id="53630-120">Il codice di esempio chiama la stored procedure di sistema **sp_start_job**, che avvia un processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="53630-120">The code sample calls the system stored procedure, **sp_start_job**, which launches a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job.</span></span> <span data-ttu-id="53630-121">Il processo avviato dalla stored procedure è denominato `RunSSISPackage` e si trova nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="53630-121">The job that the procedure launches is named `RunSSISPackage`, and this job is on the remote computer.</span></span> <span data-ttu-id="53630-122">Il processo `RunSSISPackage` esegue quindi il pacchetto nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="53630-122">The `RunSSISPackage` job then runs the package on the remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53630-123">Il valore restituito della stored procedure **sp_start_job** indica se la stored procedure è stata in grado di avviare correttamente il processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="53630-123">The return value of the **sp_start_job** stored procedure indicates whether the stored procedure was able to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent job successfully.</span></span> <span data-ttu-id="53630-124">ma non indica se il pacchetto è stato o meno eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="53630-124">The return value does not indicate whether the package succeeded or failed.</span></span>  
  
 <span data-ttu-id="53630-125">Per informazioni su come risolvere i problemi legati all'esecuzione di pacchetti dai processi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, vedere l'articolo Microsoft [relativo a un pacchetto SSIS che non viene eseguito quando si chiama il pacchetto SSIS da un passaggio di processo di SQL Server Agent](https://support.microsoft.com/kb/918760).</span><span class="sxs-lookup"><span data-stu-id="53630-125">For information on troubleshooting packages that are run from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs, see the Microsoft article, [An SSIS package does not run when you call the SSIS package from a SQL Server Agent job step](https://support.microsoft.com/kb/918760).</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="53630-126">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="53630-126">Sample Code</span></span>  
  
```vb  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
  
    Dim jobConnection As SqlConnection  
    Dim jobCommand As SqlCommand  
    Dim jobReturnValue As SqlParameter  
    Dim jobParameter As SqlParameter  
    Dim jobResult As Integer  
  
    jobConnection = New SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI")  
    jobCommand = New SqlCommand("sp_start_job", jobConnection)  
    jobCommand.CommandType = CommandType.StoredProcedure  
  
    jobReturnValue = New SqlParameter("@RETURN_VALUE", SqlDbType.Int)  
    jobReturnValue.Direction = ParameterDirection.ReturnValue  
    jobCommand.Parameters.Add(jobReturnValue)  
  
    jobParameter = New SqlParameter("@job_name", SqlDbType.VarChar)  
    jobParameter.Direction = ParameterDirection.Input  
    jobCommand.Parameters.Add(jobParameter)  
    jobParameter.Value = "RunSSISPackage"  
  
    jobConnection.Open()  
    jobCommand.ExecuteNonQuery()  
    jobResult = DirectCast(jobCommand.Parameters("@RETURN_VALUE").Value, Integer)  
    jobConnection.Close()  
  
    Select Case jobResult  
      Case 0  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.")  
      Case Else  
        Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.")  
    End Select  
    Console.Read()  
  
  End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace LaunchSSISPackageAgent_CS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      SqlConnection jobConnection;  
      SqlCommand jobCommand;  
      SqlParameter jobReturnValue;  
      SqlParameter jobParameter;  
      int jobResult;  
  
      jobConnection = new SqlConnection("Data Source=(local);Initial Catalog=msdb;Integrated Security=SSPI");  
      jobCommand = new SqlCommand("sp_start_job", jobConnection);  
      jobCommand.CommandType = CommandType.StoredProcedure;  
  
      jobReturnValue = new SqlParameter("@RETURN_VALUE", SqlDbType.Int);  
      jobReturnValue.Direction = ParameterDirection.ReturnValue;  
      jobCommand.Parameters.Add(jobReturnValue);  
  
      jobParameter = new SqlParameter("@job_name", SqlDbType.VarChar);  
      jobParameter.Direction = ParameterDirection.Input;  
      jobCommand.Parameters.Add(jobParameter);  
      jobParameter.Value = "RunSSISPackage";  
  
      jobConnection.Open();  
      jobCommand.ExecuteNonQuery();  
      jobResult = (Int32)jobCommand.Parameters["@RETURN_VALUE"].Value;  
      jobConnection.Close();  
  
      switch (jobResult)  
      {  
        case 0:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, started successfully.");  
          break;  
        default:  
          Console.WriteLine("SQL Server Agent job, RunSISSPackage, failed to start.");  
          break;  
      }  
      Console.Read();  
    }  
  }  
}  
```  
  
 
  
###  <a name="using-a-web-service-or-remote-component-to-run-a-remote-package-programmatically"></a><a name="service"></a> <span data-ttu-id="53630-127">Uso di un servizio Web o un componente remoto per eseguire un pacchetto remoto a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="53630-127">Using a Web Service or Remote Component to Run a Remote Package Programmatically</span></span>  
 <span data-ttu-id="53630-128">La soluzione precedente per l'esecuzione dei pacchetti a livello di programmazione nel server non richiede codice personalizzato nel server.</span><span class="sxs-lookup"><span data-stu-id="53630-128">The previous solution for running packages programmatically on the server does not require any custom code on the server.</span></span> <span data-ttu-id="53630-129">Tuttavia, può essere preferibile una soluzione che non si basa su SQL Server Agent per l'esecuzione dei pacchetti.</span><span class="sxs-lookup"><span data-stu-id="53630-129">However, you may prefer a solution that does not rely on SQL Server Agent to execute packages.</span></span> <span data-ttu-id="53630-130">Nell'esempio seguente sono illustrati un servizio Web che è possibile creare nel server per avviare i pacchetti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] in locale e un'applicazione di test che è possibile utilizzare per chiamare il servizio Web da un computer client.</span><span class="sxs-lookup"><span data-stu-id="53630-130">The following example demonstrates a Web service that can be created on the server to start [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages locally, and a test application that can be used to call the Web service from a client computer.</span></span> <span data-ttu-id="53630-131">Se si preferisce creare un componente remoto anziché un servizio Web, è possibile usare lo stesso codice con poche modifiche in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="53630-131">If you prefer to create a remote component instead of a Web service, you can use the same code logic with very few changes in a remote component.</span></span> <span data-ttu-id="53630-132">Tuttavia, un componente remoto può richiedere una configurazione più estesa rispetto a un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="53630-132">However a remote component may require more extensive configuration than a Web service.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="53630-133">Con le impostazioni predefinite relative ad autenticazione e autorizzazione, un servizio Web in genere non dispone di autorizzazioni sufficienti per accedere a SQL Server o al file system per caricare ed eseguire pacchetti.</span><span class="sxs-lookup"><span data-stu-id="53630-133">With its default settings for authentication and authorization, a Web service generally does not have sufficient permissions to access SQL Server or the file system to load and execute packages.</span></span> <span data-ttu-id="53630-134">Può essere necessario assegnare le autorizzazioni appropriate al servizio Web configurando le relative impostazioni di autenticazione e autorizzazione nel file **web.config** e assegnando le autorizzazioni appropriate per database e file system.</span><span class="sxs-lookup"><span data-stu-id="53630-134">You may have to assign appropriate permissions to the Web service by configuring its authentication and authorization settings in the **web.config** file and assigning database and file system permissions as appropriate.</span></span> <span data-ttu-id="53630-135">Una descrizione completa delle autorizzazioni per Web, database e file system esula dall'ambito di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="53630-135">A complete discussion of Web, database, and file system permissions is beyond the scope of this topic.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="53630-136">I metodi della classe <xref:Microsoft.SqlServer.Dts.Runtime.Application> per l'utilizzo dell'archivio pacchetti SSIS supportano solo ".", localhost o il nome del server locale.</span><span class="sxs-lookup"><span data-stu-id="53630-136">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store support only ".", localhost, or the server name for the local server.</span></span> <span data-ttu-id="53630-137">Non è possibile utilizzare "(local)".</span><span class="sxs-lookup"><span data-stu-id="53630-137">You cannot use "(local)".</span></span>  
  
### <a name="sample-code"></a><span data-ttu-id="53630-138">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="53630-138">Sample Code</span></span>  
 <span data-ttu-id="53630-139">Negli esempi di codice seguenti è illustrato come creare e testare il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="53630-139">The following code samples show how to create and test the Web service.</span></span>  
  
#### <a name="creating-the-web-service"></a><span data-ttu-id="53630-140">Creazione del servizio Web</span><span class="sxs-lookup"><span data-stu-id="53630-140">Creating the Web Service</span></span>  
 <span data-ttu-id="53630-141">Un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] può essere caricato direttamente da un file, direttamente da SQL Server o dall'archivio pacchetti SSIS, che gestisce l'archiviazione di pacchetti in SQL Server e in cartelle speciali del file system.</span><span class="sxs-lookup"><span data-stu-id="53630-141">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package can be loaded directly from a file, directly from SQL Server, or from the SSIS Package Store, which manages package storage in both SQL Server and special file system folders.</span></span> <span data-ttu-id="53630-142">Questo esempio supporta tutte le opzioni disponibili utilizzando un costrutto `Select Case` o `switch` per selezionare la sintassi appropriata per l'avvio del pacchetto e per concatenare gli argomenti di input in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="53630-142">This sample supports all the available options by using a `Select Case` or `switch` construct to select the appropriate syntax for starting the package and to concatenate the input arguments appropriately.</span></span> <span data-ttu-id="53630-143">Il metodo LaunchPackage del servizio Web restituisce il risultato dell'esecuzione del pacchetto come numero intero anziché come valore <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, per cui i computer client non richiedono un riferimento agli assembly di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53630-143">The LaunchPackage Web service method returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span>  
  
###### <a name="to-create-a-web-service-to-run-packages-on-the-server-programmatically"></a><span data-ttu-id="53630-144">Per creare un servizio Web per eseguire i pacchetti nel server a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="53630-144">To create a Web service to run packages on the server programmatically</span></span>  
  
1.  <span data-ttu-id="53630-145">Aprire Visual Studio e creare un progetto di servizio Web nel linguaggio di programmazione preferito.</span><span class="sxs-lookup"><span data-stu-id="53630-145">Open Visual Studio and create a Web service project in your preferred programming language.</span></span> <span data-ttu-id="53630-146">Nel codice di esempio viene utilizzato il nome LaunchSSISPackageService per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53630-146">The sample code uses the name LaunchSSISPackageService for the project.</span></span>  
  
2.  <span data-ttu-id="53630-147">Aggiungere un riferimento a `Microsoft.SqlServer.ManagedDTS` e aggiungere un' `Imports` `using` istruzione o al file di codice per lo spazio dei nomi **Microsoft. SqlServer. Dts. Runtime** .</span><span class="sxs-lookup"><span data-stu-id="53630-147">Add a reference to `Microsoft.SqlServer.ManagedDTS` and add an `Imports` or `using` statement to the code file for the **Microsoft.SqlServer.Dts.Runtime** namespace.</span></span>  
  
3.  <span data-ttu-id="53630-148">Incollare il codice di esempio per il metodo LaunchPackage del servizio Web nella classe.</span><span class="sxs-lookup"><span data-stu-id="53630-148">Paste the sample code for the LaunchPackage Web service method into the class.</span></span> <span data-ttu-id="53630-149">In questo esempio viene visualizzato l'intero contenuto della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="53630-149">(The sample shows the whole contents of the code window.)</span></span>  
  
4.  <span data-ttu-id="53630-150">Compilare e testare il servizio Web fornendo un set di valori validi per gli argomenti di input del metodo LaunchPackage che puntano a un pacchetto esistente.</span><span class="sxs-lookup"><span data-stu-id="53630-150">Build and test the Web service by providing a set of valid values for the input arguments of the LaunchPackage method that point to an existing package.</span></span> <span data-ttu-id="53630-151">Ad esempio, se package1.dtsx è archiviato nel server in C:\My Packages, passare "file" come valore di sourceType, "C:\My Packages" come valore di sourceLocation e "package1" (senza l'estensione) come valore di packageName.</span><span class="sxs-lookup"><span data-stu-id="53630-151">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of the sourceType, "C:\My Packages" as the value of sourceLocation, and "package1" (without the extension) as the value of packageName.</span></span>  
  
```vb  
Imports System.Web  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports Microsoft.SqlServer.Dts.Runtime  
Imports System.IO  
  
<WebService(Namespace:="http://dtsue/")> _  
<WebServiceBinding(ConformsTo:=WsiProfiles.BasicProfile1_1)> _  
<Global.Microsoft.VisualBasic.CompilerServices.DesignerGenerated()> _  
Public Class LaunchSSISPackageService  
  Inherits System.Web.Services.WebService  
  
  ' LaunchPackage Method Parameters:  
  ' 1. sourceType: file, sql, dts  
  ' 2. sourceLocation: file system folder, (none), logical folder  
  ' 3. packageName: for file system, ".dtsx" extension is appended  
  
  <WebMethod()> _  
  Public Function LaunchPackage( _  
    ByVal sourceType As String, _  
    ByVal sourceLocation As String, _  
    ByVal packageName As String) As Integer 'DTSExecResult  
  
    Dim packagePath As String  
    Dim myPackage As Package  
    Dim integrationServices As New Application  
  
    ' Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName)  
  
    Select Case sourceType  
      Case "file"  
        ' Package is stored as a file.  
        ' Add extension if not present.  
        If String.IsNullOrEmpty(Path.GetExtension(packagePath)) Then  
          packagePath = String.Concat(packagePath, ".dtsx")  
        End If  
        If File.Exists(packagePath) Then  
          myPackage = integrationServices.LoadPackage(packagePath, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid file location: " & packagePath)  
        End If  
      Case "sql"  
        ' Package is stored in MSDB.  
        ' Combine logical path and package name.  
        If integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty) Then  
          myPackage = integrationServices.LoadFromSqlServer( _  
            packageName, "(local)", String.Empty, String.Empty, Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case "dts"  
        ' Package is managed by SSIS Package Store.  
        ' Default logical paths are File System and MSDB.  
        If integrationServices.ExistsOnDtsServer(packagePath, ".") Then  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", Nothing)  
        Else  
          Throw New ApplicationException( _  
            "Invalid package name or location: " & packagePath)  
        End If  
      Case Else  
        Throw New ApplicationException( _  
          "Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.")  
    End Select  
  
    Return myPackage.Execute()  
  
  End Function  
  
End Class  
```  
  
```csharp  
using System;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.IO;  
  
[WebService(Namespace = "http://dtsue/")]  
[WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
public class LaunchSSISPackageServiceCS : System.Web.Services.WebService  
{  
  public LaunchSSISPackageServiceCS()  
  {  
    }  
  
  // LaunchPackage Method Parameters:  
  // 1. sourceType: file, sql, dts  
  // 2. sourceLocation: file system folder, (none), logical folder  
  // 3. packageName: for file system, ".dtsx" extension is appended  
  
  [WebMethod]  
  public int LaunchPackage(string sourceType, string sourceLocation, string packageName)  
  {   
  
    string packagePath;  
    Package myPackage;  
    Application integrationServices = new Application();  
  
    // Combine path and file name.  
    packagePath = Path.Combine(sourceLocation, packageName);  
  
    switch(sourceType)  
    {  
      case "file":  
        // Package is stored as a file.  
        // Add extension if not present.  
        if (String.IsNullOrEmpty(Path.GetExtension(packagePath)))  
        {  
          packagePath = String.Concat(packagePath, ".dtsx");  
        }  
        if (File.Exists(packagePath))  
        {  
          myPackage = integrationServices.LoadPackage(packagePath, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid file location: "+packagePath);  
        }  
        break;  
      case "sql":  
        // Package is stored in MSDB.  
        // Combine logical path and package name.  
        if (integrationServices.ExistsOnSqlServer(packagePath, ".", String.Empty, String.Empty))  
        {  
          myPackage = integrationServices.LoadFromSqlServer(packageName, "(local)", String.Empty, String.Empty, null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      case "dts":  
        // Package is managed by SSIS Package Store.  
        // Default logical paths are File System and MSDB.  
        if (integrationServices.ExistsOnDtsServer(packagePath, "."))  
        {  
          myPackage = integrationServices.LoadFromDtsServer(packagePath, "localhost", null);  
        }  
        else  
        {  
          throw new ApplicationException("Invalid package name or location: "+packagePath);  
        }  
        break;  
      default:  
        throw new ApplicationException("Invalid sourceType argument: valid values are 'file', 'sql', and 'dts'.");  
    }  
  
    return (Int32)myPackage.Execute();  
  
  }  
  
}  
```  
  
#### <a name="testing-the-web-service"></a><span data-ttu-id="53630-152">Test del servizio Web</span><span class="sxs-lookup"><span data-stu-id="53630-152">Testing the Web Service</span></span>  
 <span data-ttu-id="53630-153">Nell'applicazione console di esempio seguente viene utilizzato il servizio Web per eseguire un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="53630-153">The following sample console application uses the Web service to run a package.</span></span> <span data-ttu-id="53630-154">Il metodo LaunchPackage del servizio Web restituisce il risultato dell'esecuzione del pacchetto come numero intero anziché come valore <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult>, per cui i computer client non richiedono un riferimento agli assembly di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53630-154">The LaunchPackage method of the Web service returns the result of package execution as an integer instead of a <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> value so that client computers do not require a reference to any [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] assemblies.</span></span> <span data-ttu-id="53630-155">Nell'esempio viene creata un'enumerazione privata i cui valori rispecchiano i valori <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> per riportare i risultati dell'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="53630-155">The sample creates a private enumeration whose values mirror the <xref:Microsoft.SqlServer.Dts.Runtime.DTSExecResult> values to report the results of execution.</span></span>  
  
###### <a name="to-create-a-console-application-to-test-the-web-service"></a><span data-ttu-id="53630-156">Per creare un'applicazione console per testare il servizio Web</span><span class="sxs-lookup"><span data-stu-id="53630-156">To create a console application to test the Web service</span></span>  
  
1.  <span data-ttu-id="53630-157">In Visual Studio aggiungere una nuova applicazione console, utilizzando il linguaggio di programmazione preferito, nella stessa soluzione che contiene il progetto di servizio Web.</span><span class="sxs-lookup"><span data-stu-id="53630-157">In Visual Studio, add a new console application, using your preferred programming language, to the same solution that contains the Web service project.</span></span> <span data-ttu-id="53630-158">Nell'esempio di codice viene utilizzato il nome LaunchSSISPackageTest per il progetto.</span><span class="sxs-lookup"><span data-stu-id="53630-158">The sample code uses the name LaunchSSISPackageTest for the project.</span></span>  
  
2.  <span data-ttu-id="53630-159">Impostare la nuova applicazione console come progetto di avvio nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="53630-159">Set the new console application as the startup project in the solution.</span></span>  
  
3.  <span data-ttu-id="53630-160">Aggiungere un riferimento Web per il progetto di servizio Web.</span><span class="sxs-lookup"><span data-stu-id="53630-160">Add a Web reference for the Web service project.</span></span> <span data-ttu-id="53630-161">Se necessario, modificare la dichiarazione di variabili nell'esempio di codice per il nome assegnato all'oggetto proxy del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="53630-161">If necessary, adjust the variable declaration in the sample code for the name that you assign to the Web service proxy object.</span></span>  
  
4.  <span data-ttu-id="53630-162">Incollare l'esempio di codice per la routine principale e l'enumerazione privata nel codice.</span><span class="sxs-lookup"><span data-stu-id="53630-162">Paste the sample code for the Main routine and the private enumeration into the code.</span></span> <span data-ttu-id="53630-163">In questo esempio viene visualizzato l'intero contenuto della finestra del codice.</span><span class="sxs-lookup"><span data-stu-id="53630-163">(The sample shows the whole contents of the code window.)</span></span>  
  
5.  <span data-ttu-id="53630-164">Modificare la riga di codice che chiama il metodo LaunchPackage per fornire un set di valori validi per gli argomenti di input che puntano a un pacchetto esistente.</span><span class="sxs-lookup"><span data-stu-id="53630-164">Edit the line of code that calls the LaunchPackage method to provide a set of valid values for the input arguments that point to an existing package.</span></span> <span data-ttu-id="53630-165">Ad esempio, se package1.dtsx è archiviato nel server in C:\My Packages, passare "file" come valore di `sourceType`, "C:\My Packages" come valore di `sourceLocation` e "package1" (senza l'estensione) come valore di `packageName`.</span><span class="sxs-lookup"><span data-stu-id="53630-165">For example, if package1.dtsx is stored on the server in C:\My Packages, pass "file" as the value of `sourceType`, "C:\My Packages" as the value of `sourceLocation`, and "package1" (without the extension) as the value of `packageName`.</span></span>  
  
```vb  
Module LaunchSSISPackageTest  
  
  Sub Main()  
  
    Dim launchPackageService As New LaunchSSISPackageService.LaunchSSISPackageService  
    Dim packageResult As Integer  
  
    Try  
      packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage")  
    Catch ex As Exception  
      ' The type of exception returned by a Web service is:  
      '  System.Web.Services.Protocols.SoapException  
      Console.WriteLine("The following exception occurred: " & ex.Message)  
    End Try  
  
    Console.WriteLine(CType(packageResult, PackageExecutionResult).ToString)  
    Console.ReadKey()  
  
  End Sub  
  
  Private Enum PackageExecutionResult  
    PackageSucceeded  
    PackageFailed  
    PackageCompleted  
    PackageWasCancelled  
  End Enum  
  
End Module  
```  
  
```csharp  
using System;  
  
namespace LaunchSSISPackageSvcTestCS  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS launchPackageService = new LaunchSSISPackageServiceCS.LaunchSSISPackageServiceCS();  
      int packageResult = 0;  
  
      try  
      {  
        packageResult = launchPackageService.LaunchPackage("sql", String.Empty, "SimpleTestPackage");  
      }  
      catch (Exception ex)  
      {  
        // The type of exception returned by a Web service is:  
        //  System.Web.Services.Protocols.SoapException  
        Console.WriteLine("The following exception occurred: " + ex.Message);  
      }  
  
      Console.WriteLine(((PackageExecutionResult)packageResult).ToString());  
      Console.ReadKey();  
  
    }  
  
    private enum PackageExecutionResult  
    {  
      PackageSucceeded,  
      PackageFailed,  
      PackageCompleted,  
      PackageWasCancelled  
    };  
  
  }  
}  
```  
  

  
## <a name="external-resources"></a><span data-ttu-id="53630-166">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="53630-166">External Resources</span></span>  
  
-   <span data-ttu-id="53630-167">Video relativo alla [procedura sull'automazione dell'esecuzione di un pacchetto SSIS usando SQL Server Agent (video di SQL Server)](https://technet.microsoft.com/sqlserver/ff686764.aspx) nel sito technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="53630-167">Video, [How to: Automate SSIS Package Execution by Using the SQL Server Agent (SQL Server Video)](https://technet.microsoft.com/sqlserver/ff686764.aspx), on technet.microsoft.com</span></span>  
  
<span data-ttu-id="53630-168">![Integration Services icona (piccola)](../media/dts-16.gif "Icona di Integration Services (piccola)")  **rimane aggiornata con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="53630-168">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="53630-169">Per i download, gli articoli, gli esempi e i video Microsoft più recenti, oltre alle soluzioni selezionate dalla community, visitare la pagina [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sul sito MSDN:</span><span class="sxs-lookup"><span data-stu-id="53630-169">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="53630-170">Visitare la pagina relativa a Integration Services su MSDN</span><span class="sxs-lookup"><span data-stu-id="53630-170">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="53630-171">Per ricevere una notifica automatica su questi aggiornamenti, sottoscrivere i feed RSS disponibili nella pagina.</span><span class="sxs-lookup"><span data-stu-id="53630-171">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53630-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53630-172">See Also</span></span>  
 <span data-ttu-id="53630-173">[Informazioni sulle differenze tra l'esecuzione locale e remota](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span><span class="sxs-lookup"><span data-stu-id="53630-173">[Understanding the Differences between Local and Remote Execution](../run-manage-packages-programmatically/understanding-the-differences-between-local-and-remote-execution.md) </span></span>  
 <span data-ttu-id="53630-174">[Caricamento ed esecuzione di un pacchetto locale a livello di codice](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="53630-174">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 [<span data-ttu-id="53630-175">Caricamento dell'output di un pacchetto locale</span><span class="sxs-lookup"><span data-stu-id="53630-175">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
