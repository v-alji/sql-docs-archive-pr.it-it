---
title: Esempio Hello World Ready | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
ms.assetid: 1cb94266-f702-4a57-a1ae-689a89c98757
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7cc3088af258962a4cec615214147d1f4f09c431
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726191"
---
# <a name="hello-world-ready-sample"></a><span data-ttu-id="24530-102">Esempio Hello World Ready</span><span class="sxs-lookup"><span data-stu-id="24530-102">Hello World Ready Sample</span></span>
  <span data-ttu-id="24530-103">Nell'esempio Hello World Ready vengono illustrate le operazioni di base per la creazione, la distribuzione e il test di una stored procedure basata sull'integrazione con CLR semplice e internazionalizzata.</span><span class="sxs-lookup"><span data-stu-id="24530-103">The Hello World Ready sample demonstrates the basic operations that are involved in creating, deploying, and testing a simple world ready common language runtime (CLR) integration-based stored procedure.</span></span> <span data-ttu-id="24530-104">Un componente internazionalizzato può essere facilmente localizzato in diverse lingue per diversi mercati in tutto il mondo senza dover modificare il codice sorgente del componente.</span><span class="sxs-lookup"><span data-stu-id="24530-104">A world-ready component can be easily localized into different languages for different markets around the world without changing the component's source code.</span></span> <span data-ttu-id="24530-105">Nell'esempio viene illustrato anche come restituire dati tramite un parametro di output e tramite un record costruito dinamicamente dalla stored procedure e restituito al client. L'esempio è quasi identico all'esempio Hello World, ad eccezione del fatto che la localizzazione di questa applicazione è molto più semplice e sicura.</span><span class="sxs-lookup"><span data-stu-id="24530-105">This sample also demonstrates how to return data through an output parameter and through a record, which is dynamically constructed by the stored procedure and returned to the client.This sample is almost identical to the Hello World Sample except that it is much easier and safer to localize this application.</span></span> <span data-ttu-id="24530-106">Per modificare il testo localizzato è necessario effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24530-106">To change localized text requires the following:</span></span>  
  
1.  <span data-ttu-id="24530-107">Modifica di un file XML (il.`resx`</span><span class="sxs-lookup"><span data-stu-id="24530-107">Changing an XML file (the .`resx`</span></span> <span data-ttu-id="24530-108">file) per le impostazioni cultura specifiche nella directory delle risorse</span><span class="sxs-lookup"><span data-stu-id="24530-108">file) for the particular culture in the resources directory</span></span>  
  
2.  <span data-ttu-id="24530-109">Compilazione del file delle risorse nella lingua tramite `resgen`</span><span class="sxs-lookup"><span data-stu-id="24530-109">Building the culture's resources file by using `resgen`</span></span>  
  
3.  <span data-ttu-id="24530-110">Compilazione della DLL satellite aggiornata per le impostazioni cultura</span><span class="sxs-lookup"><span data-stu-id="24530-110">Building the updated satellite DLL for that culture</span></span>  
  
4.  <span data-ttu-id="24530-111">Eliminazione e aggiunta dell'assembly in SQL Server</span><span class="sxs-lookup"><span data-stu-id="24530-111">Dropping and adding that assembly in SQL Server</span></span>  
  
 <span data-ttu-id="24530-112">Il codice sorgente e l'assembly per la stored procedure CLR non vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="24530-112">The source code and assembly for the CLR stored procedure itself does not change.</span></span> <span data-ttu-id="24530-113">Viene fornito uno script `build.cmd`, che illustra come compilare e collegare gli assembly delle risorse. Sebbene tramite il codice sorgente per l'applicazione venga creato uno strumento di gestione delle risorse basato sull'assembly attualmente eseguito, non è necessario incorporare le risorse indipendenti dalle impostazioni cultura nella DLL contenente la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="24530-113">A `build.cmd` script is provided which demonstrates how to compile and link the resource assemblies.Although the source code for the application creates a resource manager based the currently executing assembly, you do not have to embed the culture neutral resources in the DLL that contains the stored procedure.</span></span> <span data-ttu-id="24530-114">`System.Resources.NeutralResourcesLanguage attribute` consente l'inserimento delle risorse indipendenti dalle impostazioni cultura in una DLL satellite.</span><span class="sxs-lookup"><span data-stu-id="24530-114">The `System.Resources.NeutralResourcesLanguage attribute` permits the culture-neutral resources to exist in a satellite DLL.</span></span> <span data-ttu-id="24530-115">A tale scopo, è consigliabile utilizzare una DLL separata in modo che, quando è necessario aggiungere o modificare testo localizzato, la DLL primaria che include la stored procedure CLR non debba essere modificata.</span><span class="sxs-lookup"><span data-stu-id="24530-115">It is much better to use a separate DLL for this purpose so that when localized text needs to be added or changed, the primary DLL that contains the CLR stored procedure does not have to be changed.</span></span> <span data-ttu-id="24530-116">Questo aspetto è particolarmente utile per tipi CLR definiti dall'utente che potrebbero prevedere colonne e altre dipendenze che possono rendere complesse le operazioni di eliminazione e aggiunta del tipo. In genere, le versioni DLL satellite devono essere identiche alla versione dell'assembly principale.</span><span class="sxs-lookup"><span data-stu-id="24530-116">This is especially useful for CLR user-defined types that might have columns and other dependencies which would make it difficult to drop and re-add the type.Ordinarily, the satellite DLL versions must be identical to the main assembly version.</span></span> <span data-ttu-id="24530-117">È tuttavia possibile utilizzare l'attributo `SatelliteContractVersion` per consentire l'aggiornamento dell'assembly principale senza dover aggiornare anche gli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="24530-117">However, you can use the `SatelliteContractVersion` attribute to allow the main assembly to be updated without updating the satellite assemblies too.</span></span> <span data-ttu-id="24530-118">Per ulteriori informazioni, vedere la classe `ResourceManager` nella documentazione relativa a Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="24530-118">For more information, see the `ResourceManager` class in the Microsoft .NET documentation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="24530-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="24530-119">Prerequisites</span></span>  
 <span data-ttu-id="24530-120">Questo esempio può essere utilizzato solo con SQL Server 2005 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="24530-120">This sample works only with SQL Server 2005 and later versions.</span></span>  
  
 <span data-ttu-id="24530-121">Per creare ed eseguire questo progetto, è necessario installare il software seguente:</span><span class="sxs-lookup"><span data-stu-id="24530-121">To create and run this project the following the following software must be installed:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="24530-122">o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span><span class="sxs-lookup"><span data-stu-id="24530-122">or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express.</span></span> <span data-ttu-id="24530-123">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express è disponibile gratuitamente nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sito Web [di documentazione ed esempi di](https://www.microsoft.com/sql-server/sql-server-editions-express)Express</span><span class="sxs-lookup"><span data-stu-id="24530-123">You can obtain [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express free of charge from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express Documentation and Samples [Web site](https://www.microsoft.com/sql-server/sql-server-editions-express)</span></span>  
  
-   <span data-ttu-id="24530-124">Database AdventureWorks, disponibile nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sito Web [per sviluppatori di](https://go.microsoft.com/fwlink/?linkid=62796)</span><span class="sxs-lookup"><span data-stu-id="24530-124">The AdventureWorks database that is available at the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Developer [Web site](https://go.microsoft.com/fwlink/?linkid=62796)</span></span>  
  
-   <span data-ttu-id="24530-125">.NET Framework SDK 2.0 o versione successiva oppure Microsoft Visual Studio 2005 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="24530-125">.NET Framework SDK 2.0 or later or Microsoft Visual Studio 2005 or later.</span></span> <span data-ttu-id="24530-126">.NET Framework SDK è disponibile gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="24530-126">You can obtain .NET Framework SDK free of charge.</span></span>  
  
-   <span data-ttu-id="24530-127">È necessario inoltre che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24530-127">In addition, the following conditions must be met:</span></span>  
  
-   <span data-ttu-id="24530-128">Per l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usata deve essere abilitata l'integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="24530-128">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using must have CLR integration enabled.</span></span>  
  
-   <span data-ttu-id="24530-129">Per abilitare l'integrazione con CLR, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24530-129">In order to enable CLR integration, perform the following steps:</span></span>  
  
    #### <a name="enabling-clr-integration"></a><span data-ttu-id="24530-130">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="24530-130">Enabling CLR Integration</span></span>  
  
    -   <span data-ttu-id="24530-131">Eseguire i comandi [!INCLUDE[tsql](../../includes/tsql-md.md)] seguenti:</span><span class="sxs-lookup"><span data-stu-id="24530-131">Execute the following [!INCLUDE[tsql](../../includes/tsql-md.md)] commands:</span></span>  
  
     `sp_configure 'clr enabled', 1`  
  
     `GO`  
  
     `RECONFIGURE`  
  
     `GO`  
  
    > [!NOTE]  
    >  <span data-ttu-id="24530-132">Per abilitare CLR, è necessario disporre dell'autorizzazione `ALTER SETTINGS` a livello di server, che viene assegnata implicitamente ai membri dei ruoli predefiniti del server `sysadmin` e `serveradmin`.</span><span class="sxs-lookup"><span data-stu-id="24530-132">To enable CLR, you must have `ALTER SETTINGS` server level permission, which is implicitly held by members of the `sysadmin` and `serveradmin` fixed server roles.</span></span>  
  
-   <span data-ttu-id="24530-133">Il database AdventureWorks deve essere installato nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in uso.</span><span class="sxs-lookup"><span data-stu-id="24530-133">The AdventureWorks database must be installed on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using.</span></span>  
  
-   <span data-ttu-id="24530-134">Se non si è un amministratore per l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] istanza di in uso, è necessario disporre di un amministratore per concedere l'autorizzazione **CreateAssembly** per completare l'installazione.</span><span class="sxs-lookup"><span data-stu-id="24530-134">If you are not an administrator for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance you are using, you must have an administrator grant you **CreateAssembly**  permission to complete the installation.</span></span>  
  
## <a name="building-the-sample"></a><span data-ttu-id="24530-135">Compilazione dell'esempio</span><span class="sxs-lookup"><span data-stu-id="24530-135">Building the Sample</span></span>  
  
#### <a name="create-and-run-the-sample-by-using-the-following-instructions"></a><span data-ttu-id="24530-136">Creare ed eseguire l'esempio tramite le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24530-136">Create and run the sample by using the following instructions:</span></span>  
  
1.  <span data-ttu-id="24530-137">Aprire un prompt dei comandi di .NET Framework o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="24530-137">Open a Visual Studio or .NET Framework command prompt.</span></span>  
  
2.  <span data-ttu-id="24530-138">Se necessario, creare una directory per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="24530-138">If necessary, create a directory for your sample.</span></span> <span data-ttu-id="24530-139">Per questo esempio verrà utilizzata la directory C:\MySample.</span><span class="sxs-lookup"><span data-stu-id="24530-139">For this example, we will use C:\MySample.</span></span>  
  
3.  <span data-ttu-id="24530-140">In c:\MySample creare `HelloWorld.vb` (per l'esempio Visual Basic) o `HelloWorld.cs` (per l'esempio C#) e copiare nel file il codice di esempio appropriato, Visual Basic o C#, riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="24530-140">In c:\MySample, create `HelloWorld.vb` (for the Visual Basic sample) or `HelloWorld.cs` (for the C# sample) and copy the appropriate Visual Basic or C# sample code (below) into the file.</span></span>  
  
4.  <span data-ttu-id="24530-141">In c:\MySample creare il file `messages.resx` e copiare il codice di esempio nel file.</span><span class="sxs-lookup"><span data-stu-id="24530-141">In c:\MySample, create the file `messages.resx` and copy the sample code into the file.</span></span>  
  
5.  <span data-ttu-id="24530-142">In c:\MySample creare il file `messages.de.resx` salvando il file `messages.resx` come `messages.de.resx` dopo la modifica della riga</span><span class="sxs-lookup"><span data-stu-id="24530-142">In c:\MySample, create the file `messages.de.resx` by saving the file `messages.resx` as `messages.de.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="24530-143">per leggere</span><span class="sxs-lookup"><span data-stu-id="24530-143">To read</span></span>  
  
    -   `<value xml:space="preserve">Hallo Welt!</value>`  
  
6.  <span data-ttu-id="24530-144">In c:\MySample creare il file `messages.es.resx` salvando il file `messages.resx` come `messages.es.resx` dopo la modifica della riga</span><span class="sxs-lookup"><span data-stu-id="24530-144">In c:\MySample, create the file `messages.es.resx` by saving the file `messages.resx` as `messages.es.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="24530-145">per leggere</span><span class="sxs-lookup"><span data-stu-id="24530-145">To read</span></span>  
  
    -   `<value xml:space="preserve">Hola a todos</value>`  
  
7.  <span data-ttu-id="24530-146">In c:\MySample creare il file `messages.fr.resx` salvando il file `messages.resx` come `messages.fr.resx` dopo la modifica della riga</span><span class="sxs-lookup"><span data-stu-id="24530-146">In c:\MySample, create the file `messages.fr.resx` by saving the file `messages.resx` as `messages.fr.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="24530-147">per leggere</span><span class="sxs-lookup"><span data-stu-id="24530-147">To read</span></span>  
  
    -   `<value xml:space="preserve">BonjourÂ !</value>`  
  
8.  <span data-ttu-id="24530-148">In c:\MySample creare il file `messages.fr-FR.resx` salvando il file `messages.resx` come `messages.fr-FR.resx` dopo la modifica della riga</span><span class="sxs-lookup"><span data-stu-id="24530-148">In c:\MySample, create the file `messages.fr-FR.resx` by saving the file `messages.resx` as `messages.fr-FR.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="24530-149">per leggere</span><span class="sxs-lookup"><span data-stu-id="24530-149">To read</span></span>  
  
    -   `<value xml:space="preserve">Bonjour de France!</value>`  
  
9. <span data-ttu-id="24530-150">In c:\MySample creare il file `messages.it.resx` salvando il file `messages.resx` come `messages.it.resx` dopo la modifica della riga</span><span class="sxs-lookup"><span data-stu-id="24530-150">In c:\MySample, create the file `messages.it.resx` by saving the file `messages.resx` as `messages.it.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="24530-151">per leggere</span><span class="sxs-lookup"><span data-stu-id="24530-151">To read</span></span>  
  
    -   `<value xml:space="preserve">Buongiorno</value>`  
  
10. <span data-ttu-id="24530-152">In c:\MySample creare il file `messages.ja.resx` salvando il file `messages.resx` come `messages.ja.resx` dopo la modifica della riga</span><span class="sxs-lookup"><span data-stu-id="24530-152">In c:\MySample, create the file `messages.ja.resx` by saving the file `messages.resx` as `messages.ja.resx` after changing the line</span></span>  
  
    -   `<value xml:space="preserve">Hello, World!</value>`  
  
    -   <span data-ttu-id="24530-153">per leggere</span><span class="sxs-lookup"><span data-stu-id="24530-153">To read</span></span>  
  
    -   <span data-ttu-id="24530-154">`<value xml:space="preserve">` `ã"ã‚"ã«ã¡ã¯</value>`</span><span class="sxs-lookup"><span data-stu-id="24530-154">`<value xml:space="preserve">` `ã"ã‚"ã«ã¡ã¯</value>`</span></span>  
  
11. <span data-ttu-id="24530-155">In c:\MySample creare il file `build.com` e copiare il codice di esempio nel file</span><span class="sxs-lookup"><span data-stu-id="24530-155">In c:\MySample, create the file `build.com` and copy the sample code into the file</span></span>  
  
12. <span data-ttu-id="24530-156">Compilare l'assembly satellite eseguendo la compilazione del file al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="24530-156">Build the satellite assembles by executing the file build at the command prompt.</span></span>  
  
13. <span data-ttu-id="24530-157">Compilare il codice di esempio dal prompt della riga di comando eseguendo una delle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="24530-157">Compile the sample code from the command line prompt by executing the one of the following:</span></span>  
  
    -   `Vbc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll,C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Xml.dll /out:HelloWorldReady.dll /target:library HelloWorld.vb`  
  
    -   `Csc /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.Data.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.dll /reference:C:\Windows\Microsoft.NET\Framework\v2.0.50727\System.XML.dll /out:HelloWorldReady.dll /target:library Hello.csCopy the tsql installation code into a file and save it as Install.sql in the sample directory.`  
  
14. <span data-ttu-id="24530-158">Se l'esempio è installato in una directory diversa da `C:\MySample\`, modificare il file `Install.sql` come indicato, in modo che punti al percorso appropriato.</span><span class="sxs-lookup"><span data-stu-id="24530-158">If the sample is installed in a directory other then `C:\MySample\`, edit the file `Install.sql` as indicated to point to that location.</span></span>  
  
15. <span data-ttu-id="24530-159">Distribuire l'assembly e la stored procedure eseguendo</span><span class="sxs-lookup"><span data-stu-id="24530-159">Deploy the assembly and stored procedure by executing</span></span>  
  
    -   `sqlcmd -E -I -i install.sql`  
  
16. <span data-ttu-id="24530-160">Copiare lo script di comandi di test [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `test.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="24530-160">Copy [!INCLUDE[tsql](../../includes/tsql-md.md)] test command script into a file and save it as `test.sql` in the sample directory.</span></span>  
  
17. <span data-ttu-id="24530-161">Eseguire lo script di test con il comando seguente</span><span class="sxs-lookup"><span data-stu-id="24530-161">Execute the test script with the following command</span></span>  
  
    -   `sqlcmd -E -I -i test.sql`  
  
18. <span data-ttu-id="24530-162">Copiare lo script di pulizia [!INCLUDE[tsql](../../includes/tsql-md.md)] in un file e salvarlo come `cleanup.sql` nella directory dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="24530-162">Copy the [!INCLUDE[tsql](../../includes/tsql-md.md)] cleanup script into a file and save it as `cleanup.sql` in the sample directory.</span></span>  
  
19. <span data-ttu-id="24530-163">Eseguire lo script con il comando seguente</span><span class="sxs-lookup"><span data-stu-id="24530-163">Execute the script with the  following command</span></span>  
  
    -   `sqlcmd -E -I -i cleanup.sql`  
  
## <a name="sample-code"></a><span data-ttu-id="24530-164">Codice di esempio</span><span class="sxs-lookup"><span data-stu-id="24530-164">Sample Code</span></span>  
 <span data-ttu-id="24530-165">Di seguito sono illustrati i listati di codice per l'esempio.</span><span class="sxs-lookup"><span data-stu-id="24530-165">The following are the code listings for this sample.</span></span>  
  
 <span data-ttu-id="24530-166">C#</span><span class="sxs-lookup"><span data-stu-id="24530-166">C#</span></span>  
  
```  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
using System.Globalization;  
using System.Threading;  
using System.Resources;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
  
[assembly: System.Resources.NeutralResourcesLanguage("", System.Resources.UltimateResourceFallbackLocation.Satellite)]  
[assembly: System.Security.Permissions.SecurityPermissionAttribute(System.Security.Permissions.SecurityAction.RequestMinimum)]  
[assembly: System.Runtime.ConstrainedExecution.ReliabilityContract(System.Runtime.ConstrainedExecution.Consistency.MayCorruptInstance, System.Runtime.ConstrainedExecution.Cer.None)]  
  
    public sealed partial class StoredProcedures  
    {  
        private StoredProcedures()  
        {  
        }  
  
        [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1021:AvoidOutParameters"), Microsoft.SqlServer.Server.SqlProcedure]  
        public static void HelloWorldReady(string culture, out string greeting)  
        {  
ResourceManager rm   
= new ResourceManager("Messages",   
Assembly.GetExecutingAssembly());  
  
string message = rm.GetString("HelloWorld", CultureInfo.GetCultureInfo(culture));  
  
            Microsoft.SqlServer.Server.SqlMetaData columnInfo  
                = new Microsoft.SqlServer.Server.SqlMetaData("Column1", SqlDbType.NVarChar, 24);  
            SqlDataRecord greetingRecord  
                = new SqlDataRecord(new Microsoft.SqlServer.Server.SqlMetaData[] { columnInfo });  
            greetingRecord.SetString(0, message);  
            SqlContext.Pipe.Send(greetingRecord);  
            greeting = message;  
        }  
    }  
  
```  
  
 <span data-ttu-id="24530-167">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24530-167">Visual Basic</span></span>  
  
```  
Imports System  
Imports System.Data  
Imports System.Data.Sql  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
Imports System.Globalization  
Imports System.Resources  
Imports System.Reflection  
Imports System.Runtime.InteropServices  
<Assembly: AssemblyVersion("1.0.*")>   
<Assembly: System.Runtime.InteropServices.ComVisible(False)>   
<Assembly: System.CLSCompliant(True)>   
<Assembly: System.Resources.NeutralResourcesLanguage("", System.Resources.UltimateResourceFallbackLocation.Satellite)>   
<Assembly: System.Security.Permissions.SecurityPermissionAttribute(System.Security.Permissions.SecurityAction.RequestMinimum)>   
<Assembly: System.Runtime.ConstrainedExecution.ReliabilityContract(System.Runtime.ConstrainedExecution.Consistency.WillNotCorruptState, Runtime.ConstrainedExecution.Cer.None)>   
  
Partial Public NotInheritable Class StoredProcedures  
    Private Sub New()  
    End Sub  
    <Microsoft.SqlServer.Server.SqlProcedure()> _  
    Public Shared Sub HelloWorldReady(ByVal culture As String, ByRef greeting As String)  
        Dim rm As New ResourceManager("Messages", Assembly.GetExecutingAssembly())  
        Dim message As String = rm.GetString("HelloWorld", CultureInfo.GetCultureInfo(culture))  
        Dim columnInfo As New Microsoft.SqlServer.Server.SqlMetaData("Column1", _  
            SqlDbType.NVarChar, 24)  
        Dim greetingRecord As New SqlDataRecord(New  _  
            Microsoft.SqlServer.Server.SqlMetaData() {columnInfo})  
        greetingRecord.SetString(0, message)  
        SqlContext.Pipe.Send(greetingRecord)  
        greeting = message  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="24530-168">Di seguito è illustrato `build.com`, che consente di compilare gli assembly satellite.</span><span class="sxs-lookup"><span data-stu-id="24530-168">This is `build.com`, which builds the satellite assemblies.</span></span>  
  
```  
resgen Messages.resx  
resgen Messages.de.resx  
resgen Messages.es.resx  
resgen Messages.fr.resx  
resgen Messages.fr-Fr.resx  
resgen Messages.it.resx  
resgen Messages.ja.resx  
if not exist de/ mkdir de  
if not exist es/ mkdir es  
if not exist fr/ mkdir fr  
if not exist fr-FR/ mkdir fr-FR  
if not exist it/ mkdir it  
if not exist ja/ mkdir ja  
al /t:lib /culture:de /embed:Messages.de.resources /out:de\HelloWorldReady.resources.dll  
al /t:lib /culture:es /embed:Messages.es.resources /out:es\HelloWorldReady.resources.dll  
al /t:lib /culture:fr /embed:Messages.fr.resources /out:fr\HelloWorldReady.resources.dll  
al /t:lib /culture:fr-FR /embed:Messages.fr-FR.resources /out:fr-FR\HelloWorldReady.resources.dll  
al /t:lib /culture:it /embed:Messages.it.resources /out:it\HelloWorldReady.resources.dll  
al /t:lib /culture:ja /embed:Messages.ja.resources /out:ja\HelloWorldReady.resources.dll  
al /t:lib /culture:"" /embed:Messages.resources /out:HelloWorldReady.resources.dll  
```  
  
 <span data-ttu-id="24530-169">Di seguito è illustrato lo script di installazione [!INCLUDE[tsql](../../includes/tsql-md.md)] (`Install.sql`) che consente la distribuzione degli assembly e la creazione della stored procedure nel database.</span><span class="sxs-lookup"><span data-stu-id="24530-169">This is the [!INCLUDE[tsql](../../includes/tsql-md.md)] installation script (`Install.sql`), which deploys the assemblies and creates the stored procedure within the database.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
-- Drop existing sproc and assembly if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorldReady')  
DROP PROCEDURE usp_HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady')  
DROP ASSEMBLY HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.neutral')  
DROP ASSEMBLY [HelloWorldReady.resources.neutral]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.de')  
DROP ASSEMBLY [HelloWorldReady.resources.de]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.es')  
DROP ASSEMBLY [HelloWorldReady.resources.es]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr')  
DROP ASSEMBLY [HelloWorldReady.resources.fr]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr-FR')  
DROP ASSEMBLY [HelloWorldReady.resources.fr-FR]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.it')  
DROP ASSEMBLY [HelloWorldReady.resources.it]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.ja')  
DROP ASSEMBLY [HelloWorldReady.resources.ja]  
GO  
  
DECLARE @SamplesPath nvarchar(1024)  
-- You may need to modify the value of this variable if you have installed the sample someplace other than the default location.  
Set @SamplesPath = N'C:\MySample\'  
  
-- Add the assembly and CLR integration based stored procedure  
  
CREATE ASSEMBLY HelloWorldReady  
FROM @SamplesPath + 'HelloWorldReady.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.neutral]  
FROM @SamplesPath + 'HelloWorldReady.resources.dll'  
WITH permission_set = Safe;   
  
CREATE ASSEMBLY [HelloWorldReady.resources.de]  
FROM @SamplesPath + '\de\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.es]  
FROM @SamplesPath + '\es\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.fr]  
FROM @SamplesPath + '\fr\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.fr-FR]  
FROM @SamplesPath + '\fr-FR\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.it]  
FROM @SamplesPath + '\it\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
  
CREATE ASSEMBLY [HelloWorldReady.resources.ja]  
FROM @SamplesPath + '\ja\HelloWorldReady.resources.dll'  
WITH permission_set = Safe;  
GO  
  
CREATE PROCEDURE usp_HelloWorldReady  
(  
@Culture NVarchar(12),  
@Greeting NVarchar(24) OUTPUT  
)  
AS EXTERNAL NAME HelloWorldReady.StoredProcedures.HelloWorldReady;  
GO  
  
USE master;  
GO  
```  
  
 <span data-ttu-id="24530-170">Di seguito è illustrato lo script `test.sql` che consente di testare l'esempio eseguendo le funzioni per ciascuna delle impostazioni locali.</span><span class="sxs-lookup"><span data-stu-id="24530-170">This is `test.sql`, which tests the sample by executing the functions on each locale.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
DECLARE @GreetingDe nvarchar(24);  
DECLARE @GreetingDe_CH nvarchar(24);  
DECLARE @GreetingEn nvarchar(24);  
DECLARE @GreetingEs nvarchar(24);  
DECLARE @GreetingFr nvarchar(24);  
DECLARE @GreetingFr_FR nvarchar(24);  
DECLARE @GreetingIt nvarchar(24);  
DECLARE @GreetingJa nvarchar(24);  
  
--German as spoken anywhere in the world (the neutral German culture)  
EXEC usp_HelloWorldReady 'de', @GreetingDe OUTPUT;  
--German as spoken in Switzerland.  Because we don't have a specific assembly  
--for this case, the .NET Framework will automatically fall back to the neutral German culture DLL.  
EXEC usp_HelloWorldReady 'de-CH', @GreetingDe_CH OUTPUT;  
EXEC usp_HelloWorldReady 'en', @GreetingEn OUTPUT;  
EXEC usp_HelloWorldReady 'es', @GreetingEs OUTPUT;  
--French as spoken anywhere in the world (the neutral French culture)  
EXEC usp_HelloWorldReady 'fr', @GreetingFr OUTPUT  
--French as spoken in France.  Since we do have a specific assembly for this case, a specific   
--greeting is provided from that DLL.  The neutral French culture DLL is not used in this case.  
EXEC usp_HelloWorldReady 'fr-FR', @GreetingFr_FR OUTPUT  
EXEC usp_HelloWorldReady 'it', @GreetingIt OUTPUT;  
EXEC usp_HelloWorldReady 'ja', @GreetingJa OUTPUT;  
  
SELECT @GreetingDe AS OUTPUT_PARAMETER_DE;  
SELECT @GreetingDe_CH AS OUTPUT_PARAMETER_De_CH;  
SELECT @GreetingEn AS OUTPUT_PARAMETER_EN;  
SELECT @GreetingEs AS OUTPUT_PARAMETER_ES;  
SELECT @GreetingFr AS OUTPUT_PARAMETER_FR;  
SELECT @GreetingFr_FR AS OUTPUT_PARAMETER_Fr_FR;  
SELECT @GreetingIt AS OUTPUT_PARAMETER_IT;  
SELECT @GreetingJa AS OUTPUT_PARAMETER_JA;  
  
GO  
```  
  
 <span data-ttu-id="24530-171">Il codice [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente consente di rimuovere gli assembly e la stored procedure dal database.</span><span class="sxs-lookup"><span data-stu-id="24530-171">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] removes the assemblies and stored procedure from the database.</span></span>  
  
```  
USE AdventureWorks;  
GO  
  
-- Drop existing sproc and assembly if any.  
  
IF EXISTS (SELECT * FROM sys.procedures WHERE [name] = 'usp_HelloWorldReady')  
DROP PROCEDURE usp_HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady')  
DROP ASSEMBLY HelloWorldReady;  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.neutral')  
DROP ASSEMBLY [HelloWorldReady.resources.neutral]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.de')  
DROP ASSEMBLY [HelloWorldReady.resources.de]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.es')  
DROP ASSEMBLY [HelloWorldReady.resources.es]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr')  
DROP ASSEMBLY [HelloWorldReady.resources.fr]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.fr-FR')  
DROP ASSEMBLY [HelloWorldReady.resources.fr-FR]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.it')  
DROP ASSEMBLY [HelloWorldReady.resources.it]  
GO  
  
IF EXISTS (SELECT * FROM sys.assemblies WHERE [name] = 'HelloWorldReady.resources.ja')  
DROP ASSEMBLY [HelloWorldReady.resources.ja]  
GO  
  
USE master;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="24530-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24530-172">See Also</span></span>  
 [<span data-ttu-id="24530-173">Scenari di utilizzo ed esempi per l'integrazione con CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="24530-173">Usage Scenarios and Examples for Common Language Runtime &#40;CLR&#41; Integration</span></span>](../../../2014/database-engine/dev-guide/usage-scenarios-and-examples-for-common-language-runtime-clr-integration.md)  
  
  
