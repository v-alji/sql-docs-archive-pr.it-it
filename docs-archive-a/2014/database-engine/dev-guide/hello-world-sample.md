---
title: Esempio Hello World | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: fed6c358-f5ee-4d4c-9ad6-089778383ba7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0d5616c1d4ef6428a011c8e36be3757931039c9f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726184"
---
# <a name="hello-world-sample"></a><span data-ttu-id="1e7cf-102">Esempio Hello World</span><span class="sxs-lookup"><span data-stu-id="1e7cf-102">Hello World Sample</span></span>
  <span data-ttu-id="1e7cf-103">Nell'esempio Hello World vengono illustrate le operazioni di base per la creazione, la distribuzione e il test di una stored procedure semplice basata sull'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-103">The Hello World sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="1e7cf-104">Nell'esempio viene inoltre illustrato come restituire dati tramite un record, che viene costruito in modo dinamico dalla stored procedure e restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-104">This sample also demonstrates how to return data through a record, which is dynamically constructed by the stored procedure and returned to the caller.</span></span>  
  
 <span data-ttu-id="1e7cf-105">Il `HelloWorld` stored procedure restituisce la stringa "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="1e7cf-105">The `HelloWorld` stored procedure returns the string "Hello world!"</span></span> <span data-ttu-id="1e7cf-106">in un set di risultati costituito da una riga.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-106">in a result set consisting of one row.</span></span> <span data-ttu-id="1e7cf-107">Questo esempio illustra alcuni usi per le classi [Microsoft. SqlServer. Server. SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft. SqlServer. Server. SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) e [Microsoft. SqlServer. Server. pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span><span class="sxs-lookup"><span data-stu-id="1e7cf-107">This example illustrates some uses for the classes [Microsoft.SqlServer.Server.SqlMetaData](https://go.microsoft.com/fwlink/?LinkID=193572), [Microsoft.SqlServer.Server.SqlDataRecord](https://go.microsoft.com/fwlink/?LinkID=193573) and [Microsoft.SqlServer.Server.Pipe](https://go.microsoft.com/fwlink/?LinkID=193571).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1e7cf-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1e7cf-108">Prerequisites</span></span>  
 <span data-ttu-id="1e7cf-109">Per creare ed eseguire questo progetto, è necessario installare il software seguente:</span><span class="sxs-lookup"><span data-stu-id="1e7cf-109">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1e7cf-110">o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-110">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="1e7cf-111">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express è disponibile gratuitamente nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sito Web [di documentazione ed esempi di](https://www.microsoft.com/sql-server/sql-server-editions-express)Express</span><span class="sxs-lookup"><span data-stu-id="1e7cf-111">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="1e7cf-112">Database AdventureWorks, disponibile nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sito Web [per sviluppatori di](https://go.microsoft.com/fwlink/?linkid=62796)</span><span class="sxs-lookup"><span data-stu-id="1e7cf-112">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="1e7cf-113">.NET Framework SDK 2.0 o versione successiva oppure Microsoft Visual Studio 2005 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-113">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="1e7cf-114">.NET Framework SDK è disponibile gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-114">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="1e7cf-115">È necessario inoltre che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e7cf-115">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="1e7cf-116">Per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usata deve essere abilitata l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="1e7cf-117">Per abilitare l'integrazione con CLR, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e7cf-117">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="1e7cf-118">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="1e7cf-118">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="1e7cf-119">Eseguire i comandi [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e7cf-119">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e7cf-120">Per abilitare CLR, è necessario disporre dell'autorizzazione `ALTER SETTINGS` a livello di server, che viene assegnata implicitamente ai membri dei ruoli predefiniti del server `sysadmin` e `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-120">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="1e7cf-121">Il database AdventureWorks deve essere installato nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in uso.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-121">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="1e7cf-122">Se non si dispone dei diritti di amministratore per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in uso, è necessario ricevere da un amministratore l'autorizzazione **CreateAssembly** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-122">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly** permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="1e7cf-123">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="1e7cf-123">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="1e7cf-124">Creare ed eseguire l'esempio tramite le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1e7cf-124">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="1e7cf-125">Aprire un prompt dei comandi di .NET Framework o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-125">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="1e7cf-126">Se necessario, creare una directory per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-126">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="1e7cf-127">Per questo esempio verrà utilizzata la directory C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-127">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="1e7cf-128">In c:\MySample creare `HelloWorld.vb` (per l'esempio Visual Basic) o `HelloWorld.cs` (per l'esempio C#) e copiare nel file il codice di esempio appropriato, Visual Basic o C#, riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-128">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="1e7cf-129">Compilare il codice di esempio dal prompt della riga di comando eseguendo una delle istruzioni seguenti, a seconda del linguaggio scelto.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-129">Compile the sample code from the command line prompt by executing one of the following, depending on your choice of language.</span></span>  
  
    -   `vbc C:HelloWorld.vb /target:library`  
  
    -   `csc /target:library HelloWorld.cs`  
  
5.  <span data-ttu-id="1e7cf-130">Copiare il codice di installazione [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `Install.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-130">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation code into a file and save it as `Install.sql` in the sample directory.</span></span>  
  
6.  <span data-ttu-id="1e7cf-131">Distribuire l'assembly e la stored procedure eseguendo</span><span class="sxs-lookup"><span data-stu-id="1e7cf-131">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql -v root = "C:\MySample\"`  
  
7.  <span data-ttu-id="1e7cf-132">Copiare lo script di comandi di test [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `test.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-132">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
8.  <span data-ttu-id="1e7cf-133">Eseguire lo script di test con il comando seguente</span><span class="sxs-lookup"><span data-stu-id="1e7cf-133">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
9. <span data-ttu-id="1e7cf-134">Copiare lo script di pulizia [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `cleanup.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-134">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
10. <span data-ttu-id="1e7cf-135">Eseguire lo script con il comando seguente</span><span class="sxs-lookup"><span data-stu-id="1e7cf-135">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="1e7cf-136">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="1e7cf-136">Sample Code</span></span>  
 <span data-ttu-id="1e7cf-137">Di seguito sono illustrati i listati di codice per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-137">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="1e7cf-138">C#</span><span class="sxs-lookup"><span data-stu-id="1e7cf-138">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
public partial class StoredProcedures  
{  
    [Microsoft.SqlServer.Server.SqlProcedure]  
    public static void HelloWorld()  
    {  
        Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 12);  
        SqlDataRecord greetingRecord  
            = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
        greetingRecord.SetString(0, "Hello world!");  
        SqlContext.Pipe.Send(greetingRecord);  
    }  
};  
  
```  
  
 <span data-ttu-id="1e7cf-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e7cf-139">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
  
Partial Public NotInheritable Class StoredProcedures  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorld()  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 12)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, "Hello World!")  
        SqlContext.Pipe.Send(greetingRecord)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="1e7cf-140">Di seguito è illustrato lo script di installazione [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`) che consente la distribuzione dell'assembly e la creazione della stored procedure nel database.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-140">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assembly and creates the stored procedure in the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
DECLARE @SamplesPath nvarchar(1024)  
set @SamplesPath = '$(root)'  
CREATE ASSEMBLY HelloWorld   
FROM @SamplesPath + 'HelloWorld.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorld  
--(  
--    @Greeting nvarchar(12) OUTPUT  
--)  
AS EXTERNAL NAME HelloWorld.[StoredProcedures].HelloWorld;  
GO  
```  
  
 <span data-ttu-id="1e7cf-141">Di seguito è illustrato lo script `test.sql` che consente di testare l'esempio eseguendo la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-141">This is `test.sql`, which tests the sample by executing the stored procedure.</span></span>  
  
```  
use AdventureWorks  
go  
execute usp_HelloWorld  
  
USE AdventureWorks;  
GO  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
```  
  
 <span data-ttu-id="1e7cf-142">Il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di rimuovere l'assembly e la stored procedure dal database.</span><span class="sxs-lookup"><span data-stu-id="1e7cf-142">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assembly and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorld')  
DROP PROCEDURE usp_HelloWorld;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorld')  
DROP ASSEMBLY HelloWorld;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1e7cf-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e7cf-143">See Also</span></span>  
 [<span data-ttu-id="1e7cf-144">Scenari di utilizzo ed esempi per l'integrazione con CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="1e7cf-144">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
