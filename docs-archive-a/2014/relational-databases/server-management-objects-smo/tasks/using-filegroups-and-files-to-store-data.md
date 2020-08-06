---
title: Utilizzo di filegroup e file per archiviare i dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- filegroups [SMO]
- storing data [SMO]
- files [SMO]
- files [SMO], about files
- storage [SMO]
ms.assetid: 7e2327ce-e1a6-4904-83d1-0944b24a7b43
author: stevestein
ms.author: sstein
ms.openlocfilehash: 15ac5fd0c43c9b58432a774ae11aeb6500f0403b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636649"
---
# <a name="using-filegroups-and-files-to-store-data"></a><span data-ttu-id="2a00e-102">Utilizzo di filegroup e file per archiviare dati</span><span class="sxs-lookup"><span data-stu-id="2a00e-102">Using Filegroups and Files to Store Data</span></span>
  <span data-ttu-id="2a00e-103">I file di dati vengono utilizzati per archiviare file di database.</span><span class="sxs-lookup"><span data-stu-id="2a00e-103">Data files are used to store database files.</span></span> <span data-ttu-id="2a00e-104">I file di dati vengono suddivisi in filegroup.</span><span class="sxs-lookup"><span data-stu-id="2a00e-104">The data files are subdivided into file groups.</span></span> <span data-ttu-id="2a00e-105">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> dispone di una proprietà <xref:Microsoft.SqlServer.Management.Smo.Database.FileGroups%2A> che fa riferimento a un oggetto <xref:Microsoft.SqlServer.Management.Smo.FileGroupCollection>.</span><span class="sxs-lookup"><span data-stu-id="2a00e-105">The <xref:Microsoft.SqlServer.Management.Smo.Database> object has a <xref:Microsoft.SqlServer.Management.Smo.Database.FileGroups%2A> property that references a <xref:Microsoft.SqlServer.Management.Smo.FileGroupCollection> object.</span></span> <span data-ttu-id="2a00e-106">Ogni oggetto <xref:Microsoft.SqlServer.Management.Smo.FileGroup> di quella raccolta dispone di una proprietà <xref:Microsoft.SqlServer.Management.Smo.FileGroup.Files%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a00e-106">Each <xref:Microsoft.SqlServer.Management.Smo.FileGroup> object in that collection has a <xref:Microsoft.SqlServer.Management.Smo.FileGroup.Files%2A> property.</span></span> <span data-ttu-id="2a00e-107">Questa proprietà fa riferimento a una raccolta <xref:Microsoft.SqlServer.Management.Smo.DataFileCollection> che contiene tutti i file di dati che appartengono al database.</span><span class="sxs-lookup"><span data-stu-id="2a00e-107">This property refers to a <xref:Microsoft.SqlServer.Management.Smo.DataFileCollection> collection that contains all the data files that belong to the database.</span></span> <span data-ttu-id="2a00e-108">Un filegroup viene utilizzato principalmente per raggruppare file utilizzati per archiviare un oggetto di database.</span><span class="sxs-lookup"><span data-stu-id="2a00e-108">A file group is principally used to group files together that are used to store a database object.</span></span> <span data-ttu-id="2a00e-109">È opportuno distribuire un oggetto di database su diversi file poiché questa operazione può migliorare le prestazioni, specialmente se i file sono archiviati su unità disco diverse.</span><span class="sxs-lookup"><span data-stu-id="2a00e-109">One reason for spreading a database object over several files is that it can improve performance, especially if the files are stored on different disk drives.</span></span>  
  
 <span data-ttu-id="2a00e-110">Ogni database creato automaticamente dispone di un filegroup denominato "Primary" e di un file di dati con lo stesso nome del database.</span><span class="sxs-lookup"><span data-stu-id="2a00e-110">Every database that is created automatically has a file group named "Primary" and a data file with the same name as the database.</span></span> <span data-ttu-id="2a00e-111">È possibile aggiungere file e gruppi supplementari alle raccolte.</span><span class="sxs-lookup"><span data-stu-id="2a00e-111">Additional files and groups can be added to the collections.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2a00e-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="2a00e-112">Examples</span></span>  
 <span data-ttu-id="2a00e-113">Per gli esempi di codice seguenti, è necessario selezionare l'ambiente, il modello e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2a00e-113">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="2a00e-114">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e alla [creazione di un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="2a00e-114">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-visual-basic"></a><span data-ttu-id="2a00e-115">Aggiunta di filegroup e file di dati a un database in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a00e-115">Adding FileGroups and DataFiles to a Database in Visual Basic</span></span>  
 <span data-ttu-id="2a00e-116">Il file di dati e il filegroup primari vengono creati automaticamente con i valori delle proprietà predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2a00e-116">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="2a00e-117">Nell'esempio di codice vengono specificati alcuni valori delle proprietà che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2a00e-117">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="2a00e-118">In caso contrario, vengono utilizzati i valori delle proprietà predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2a00e-118">Otherwise, the default property values are used.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBFileGroups1](SMO How to#SMO_VBFileGroups1)]  -->  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-visual-c"></a><span data-ttu-id="2a00e-119">Aggiunta di filegroup e file di dati a un database in Visual C#</span><span class="sxs-lookup"><span data-stu-id="2a00e-119">Adding FileGroups and DataFiles to a Database in Visual C#</span></span>  
 <span data-ttu-id="2a00e-120">Il file di dati e il filegroup primari vengono creati automaticamente con i valori delle proprietà predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2a00e-120">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="2a00e-121">Nell'esempio di codice vengono specificati alcuni valori delle proprietà che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2a00e-121">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="2a00e-122">In caso contrario, vengono utilizzati i valori delle proprietà predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2a00e-122">Otherwise, the default property values are used.</span></span>  
  
```csharp
{  
            Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define a FileGroup object called SECONDARY on the database.   
            FileGroup fg1 = default(FileGroup);  
            fg1 = new FileGroup(db, "SECONDARY");  
            //Call the Create method to create the file group on the instance of SQL Server.   
            fg1.Create();  
            //Define a DataFile object on the file group and set the FileName property.   
            DataFile df1 = default(DataFile);  
            df1 = new DataFile(fg1, "datafile1");  
            df1.FileName = "c:\\Program Files\\Microsoft SQL Server\\MSSQL.1\\MSSQL\\Data\\datafile2.ndf";  
            //Call the Create method to create the data file on the instance of SQL Server.   
            df1.Create();  
        }  
```  
  
## <a name="adding-filegroups-and-datafiles-to-a-database-in-powershell"></a><span data-ttu-id="2a00e-123">Aggiunta di filegroup e file di dati a un database in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a00e-123">Adding FileGroups and DataFiles to a Database in PowerShell</span></span>  
 <span data-ttu-id="2a00e-124">Il file di dati e il filegroup primari vengono creati automaticamente con i valori delle proprietà predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2a00e-124">The primary file group and data file are created automatically with default property values.</span></span> <span data-ttu-id="2a00e-125">Nell'esempio di codice vengono specificati alcuni valori delle proprietà che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2a00e-125">The code example specifies some property values that you can use.</span></span> <span data-ttu-id="2a00e-126">In caso contrario, vengono utilizzati i valori delle proprietà predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2a00e-126">Otherwise, the default property values are used.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default\Databases\  
  
#And the database object corresponding to AdventureWorks2012.  
$db = get-item AdventureWorks2012  
  
#Create a new filegroup  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "SECONDARY"  
$fg1.Create()  
  
#Define a DataFile object on the file group and set the FileName property.   
$df1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.DataFile -argumentlist $fg1, "datafile1"  
  
#Make sure to have a directory created to hold the designated data file  
$df1.FileName = "c:\\TestData\\datafile2.ndf"  
  
#Call the Create method to create the data file on the instance of SQL Server.   
$df1.Create()  
```  
  
## <a name="creating-altering-and-removing-a-log-file-in-visual-basic"></a><span data-ttu-id="2a00e-127">Creazione, modifica e rimozione di un file di log in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a00e-127">Creating, Altering, and Removing a Log File in Visual Basic</span></span>  
 <span data-ttu-id="2a00e-128">Nell'esempio di codice viene creato un oggetto <xref:Microsoft.SqlServer.Management.Smo.LogFile>, viene modificata una delle proprietà, quindi l'oggetto viene rimosso dal database.</span><span class="sxs-lookup"><span data-stu-id="2a00e-128">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBFileGroups3](SMO How to#SMO_VBFileGroups3)]  -->  
  
## <a name="creating-altering-and-removing-a-log-file-in-visual-c"></a><span data-ttu-id="2a00e-129">Creazione, modifica e rimozione di un file di log in Visual C#</span><span class="sxs-lookup"><span data-stu-id="2a00e-129">Creating, Altering, and Removing a Log File in Visual C#</span></span>  
 <span data-ttu-id="2a00e-130">Nell'esempio di codice viene creato un oggetto <xref:Microsoft.SqlServer.Management.Smo.LogFile>, viene modificata una delle proprietà, quindi l'oggetto viene rimosso dal database.</span><span class="sxs-lookup"><span data-stu-id="2a00e-130">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference the AdventureWorks2012 database.   
            Database db = default(Database);  
            db = srv.Databases["AdventureWorks2012"];  
            //Define a LogFile object and set the database, name, and file name properties in the constructor.   
            LogFile lf1 = default(LogFile);  
            lf1 = new LogFile(db, "logfile1", "c:\\Program Files\\Microsoft SQL Server\\MSSQL.10_50.MSSQLSERVER\\MSSQL\\Data\\logfile1.ldf");  
            //Set the file growth to 6%.   
            lf1.GrowthType = FileGrowthType.Percent;  
            lf1.Growth = 6;  
            //Run the Create method to create the log file on the instance of SQL Server.   
            lf1.Create();  
            //Alter the growth percentage.
            lf1.Growth = 7;  
            lf1.Alter();  
            //Remove the log file.
            lf1.Drop();
```  
  
## <a name="creating-altering-and-removing-a-log-file-in-powershell"></a><span data-ttu-id="2a00e-131">Creazione, modifica e rimozione di un file di log in PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a00e-131">Creating, Altering, and Removing a Log File in PowerShell</span></span>  
 <span data-ttu-id="2a00e-132">Nell'esempio di codice viene creato un oggetto <xref:Microsoft.SqlServer.Management.Smo.LogFile>, viene modificata una delle proprietà, quindi l'oggetto viene rimosso dal database.</span><span class="sxs-lookup"><span data-stu-id="2a00e-132">The code example creates a <xref:Microsoft.SqlServer.Management.Smo.LogFile> object, changes one of the properties, and then removes it from the database.</span></span>  
  
```powershell
#Load the assembly containing the enums used in this example  
[reflection.assembly]::LoadWithPartialName("Microsoft.SqlServer.SqlEnum")  
  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default\Databases\  
  
#And the database object corresponding to AdventureWorks2012  
$db = get-item AdventureWorks2012  
  
#Create a filegroup  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Secondary"  
  
#Call the Create method to create the file group on the instance of SQL Server.   
$fg1.Create()  
  
#Define a LogFile object on the file group and set the FileName property.   
$lf1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.LogFile -argumentlist $db, "LogFile2"  
  
#Set a location for it - make sure the directory exists  
$lf1.FileName = "logfile1", "c:\\Program Files\\Microsoft SQL Server\\MSSQL.10_50.MSSQLSERVER\\MSSQL\\Data\\logfile1.ldf"  
  
#Set file growth to 6%  
$lf1.GrowthType = [Microsoft.SqlServer.Management.Smo.FileGrowthType]::Percent  
$lf1.Growth = 6.0  
  
#Call the Create method to create the data file on the instance of SQL Server.   
$lf1.Create()  
  
#Alter a value and drop the log file  
$lf1.Growth = 7.0  
$lf1.Alter()  
$lf1.Drop()
```  
  
## <a name="see-also"></a><span data-ttu-id="2a00e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a00e-133">See Also</span></span>  
 <xref:Microsoft.SqlServer.Management.Smo.FileGroup>   
 [<span data-ttu-id="2a00e-134">Filegroup e file di database</span><span class="sxs-lookup"><span data-stu-id="2a00e-134">Database Files and Filegroups</span></span>](../../databases/database-files-and-filegroups.md)  
