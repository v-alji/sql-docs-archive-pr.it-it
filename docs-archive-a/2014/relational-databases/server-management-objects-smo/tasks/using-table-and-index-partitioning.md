---
title: Uso del partizionamento di tabelle e indici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- partitions [SMO]
- storing data [SMO]
- partitioned tables [SQL Server], SMO
- partitioned indexes [SQL Server], SMO
ms.assetid: 0e682d7e-86c3-4d73-950d-aa692d46cb62
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e05087f63da163b8fa339befae039eb5e7e8245
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626037"
---
# <a name="using-table-and-index-partitioning"></a><span data-ttu-id="96fed-102">Utilizzo del partizionamento di tabelle e indici</span><span class="sxs-lookup"><span data-stu-id="96fed-102">Using Table and Index Partitioning</span></span>
  <span data-ttu-id="96fed-103">I dati possono essere archiviati tramite gli algoritmi di archiviazione forniti da [Partitioned Tables and Indexes](../../partitions/partitioned-tables-and-indexes.md).</span><span class="sxs-lookup"><span data-stu-id="96fed-103">Data can be stored by using the storage algorithms provided by [Partitioned Tables and Indexes](../../partitions/partitioned-tables-and-indexes.md).</span></span> <span data-ttu-id="96fed-104">Il partizionamento semplifica la gestione delle tabelle e degli indici di grandi dimensioni e li rende più scalabili.</span><span class="sxs-lookup"><span data-stu-id="96fed-104">Partitioning can make large tables and indexes more manageable and scalable.</span></span>  
  
## <a name="index-and-table-partitioning"></a><span data-ttu-id="96fed-105">Partizionamento di indici e tabelle</span><span class="sxs-lookup"><span data-stu-id="96fed-105">Index and Table Partitioning</span></span>  
 <span data-ttu-id="96fed-106">La funzionalità consente la distribuzione di dati relativi a indici e tabelle in più filegroup all'interno delle partizioni.</span><span class="sxs-lookup"><span data-stu-id="96fed-106">The feature enables index and table data to be spread across multiple file groups in partitions.</span></span> <span data-ttu-id="96fed-107">Una funzione di partizione definisce la modalità di mapping delle righe di una tabella o di un indice a un set di partizioni in base ai valori di alcune colonne definite colonne di partizionamento.</span><span class="sxs-lookup"><span data-stu-id="96fed-107">A partition function defines how the rows of a table or index are mapped to a set of partitions based on the values of certain columns, referred to as partitioning columns.</span></span> <span data-ttu-id="96fed-108">Uno schema di partizione consente di eseguire il mapping di ogni partizione specificata dalla funzione di partizione a un filegroup.</span><span class="sxs-lookup"><span data-stu-id="96fed-108">A partition scheme maps each partition specified by the partition function to a file group.</span></span> <span data-ttu-id="96fed-109">In questo modo, è possibile sviluppare strategie di archiviazione che prevedano la scalabilità delle tabelle tra filegroup e di conseguenza tra dispositivi fisici.</span><span class="sxs-lookup"><span data-stu-id="96fed-109">This lets you develop archiving strategies that enable tables to be scaled across file groups, and therefore physical devices.</span></span>  
  
 <span data-ttu-id="96fed-110">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.Database> contiene una raccolta di oggetti <xref:Microsoft.SqlServer.Management.Smo.PartitionFunction> che rappresentano le funzioni di partizione implementate e una raccolta di oggetti <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> che descrivono le modalità di mapping dei dati ai filegroup.</span><span class="sxs-lookup"><span data-stu-id="96fed-110">The <xref:Microsoft.SqlServer.Management.Smo.Database> object contains a collection of <xref:Microsoft.SqlServer.Management.Smo.PartitionFunction> objects that represent the implemented partition functions and a collection of <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> objects that describe how data is mapped to file groups.</span></span>  
  
 <span data-ttu-id="96fed-111">Ogni oggetto <xref:Microsoft.SqlServer.Management.Smo.Table> e <xref:Microsoft.SqlServer.Management.Smo.Index> specifica lo schema di partizione utilizzato nella proprietà <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> e specifica le colonne in <xref:Microsoft.SqlServer.Management.Smo.PartitionSchemeParameterCollection>.</span><span class="sxs-lookup"><span data-stu-id="96fed-111">Each <xref:Microsoft.SqlServer.Management.Smo.Table> and <xref:Microsoft.SqlServer.Management.Smo.Index> object specifies which partition scheme it uses in the <xref:Microsoft.SqlServer.Management.Smo.PartitionScheme> property and specifies the columns in the <xref:Microsoft.SqlServer.Management.Smo.PartitionSchemeParameterCollection>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96fed-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="96fed-112">Example</span></span>  
 <span data-ttu-id="96fed-113">Per l'esempio di codice seguente, è necessario selezionare l'ambiente, il modello e il linguaggio di programmazione per la creazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="96fed-113">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="96fed-114">Per ulteriori informazioni, vedere la pagina relativa alla [creazione di un progetto Visual Basic SMO in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) e alla [creazione di un progetto Visual C&#35; SMO in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="96fed-114">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-visual-basic"></a><span data-ttu-id="96fed-115">Configurazione di uno schema di partizione per una tabella in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96fed-115">Setting Up a Partition Scheme for a Table in Visual Basic</span></span>  
 <span data-ttu-id="96fed-116">Nell'esempio di codice viene illustrato come creare una funzione e uno schema di partizione per la tabella `TransactionHistory` nel database di esempio di [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96fed-116">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="96fed-117">Le partizioni sono divise in base alla data con l'intenzione di separare i record obsoleti nella tabella `TransactionHistoryArchive` .</span><span class="sxs-lookup"><span data-stu-id="96fed-117">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBPartition1](SMO How to#SMO_VBPartition1)]  -->  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-visual-c"></a><span data-ttu-id="96fed-118">Configurazione di uno schema di partizione per una tabella in Visual C#</span><span class="sxs-lookup"><span data-stu-id="96fed-118">Setting Up a Partition Scheme for a Table in Visual C#</span></span>  
 <span data-ttu-id="96fed-119">Nell'esempio di codice viene illustrato come creare una funzione e uno schema di partizione per la tabella `TransactionHistory` nel database di esempio di [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96fed-119">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="96fed-120">Le partizioni sono divise in base alla data con l'intenzione di separare i record obsoleti nella tabella `TransactionHistoryArchive` .</span><span class="sxs-lookup"><span data-stu-id="96fed-120">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
```csharp
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Define and create three new file groups on the database.   
FileGroup fg2;   
fg2 = new FileGroup(db, "Second");   
fg2.Create();   
FileGroup fg3;   
fg3 = new FileGroup(db, "Third");   
fg3.Create();   
FileGroup fg4;   
fg4 = new FileGroup(db, "Fourth");   
fg4.Create();   
//Define a partition function by supplying the parent database and name arguments in the constructor.   
PartitionFunction pf;   
pf = new PartitionFunction(db, "TransHistPF");   
//Add a partition function parameter that specifies the function uses a DateTime range type.   
PartitionFunctionParameter pfp;   
pfp = new PartitionFunctionParameter(pf, DataType.DateTime);   
pf.PartitionFunctionParameters.Add(pfp);   
//Specify the three dates that divide the data into four partitions.   
object[] val;   
val = new object[] {"1/1/2003", "1/1/2004", "1/1/2005"};   
pf.RangeValues = val;   
//Create the partition function.   
pf.Create();   
//Define a partition scheme by supplying the parent database and name arguments in the constructor.   
PartitionScheme ps;   
ps = new PartitionScheme(db, "TransHistPS");   
//Specify the partition function and the filegroups required by the partition scheme.   
ps.PartitionFunction = "TransHistPF";   
ps.FileGroups.Add("PRIMARY");   
ps.FileGroups.Add("second");   
ps.FileGroups.Add("Third");   
ps.FileGroups.Add("Fourth");   
//Create the partition scheme.   
ps.Create();   
}   
```  
  
## <a name="setting-up-a-partition-scheme-for-a-table-in-powershell"></a><span data-ttu-id="96fed-121">Configurazione di uno schema di partizione per una tabella in PowerShell</span><span class="sxs-lookup"><span data-stu-id="96fed-121">Setting Up a Partition Scheme for a Table in PowerShell</span></span>  
 <span data-ttu-id="96fed-122">Nell'esempio di codice viene illustrato come creare una funzione e uno schema di partizione per la tabella `TransactionHistory` nel database di esempio di [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96fed-122">The code example shows how to create a partition function and a partition scheme for the `TransactionHistory` table in the [!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal-md.md)] sample database.</span></span> <span data-ttu-id="96fed-123">Le partizioni sono divise in base alla data con l'intenzione di separare i record obsoleti nella tabella `TransactionHistoryArchive` .</span><span class="sxs-lookup"><span data-stu-id="96fed-123">The partitions are divided by date with the intention of separating out old records into the `TransactionHistoryArchive` table.</span></span>  
  
```powershell  
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\default  
  
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
$db = $srv.Databases["AdventureWorks"]  
#Create four filegroups  
$fg1 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "First"  
$fg2 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Second"  
$fg3 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Third"  
$fg4 = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Filegroup -argumentlist $db, "Fourth"  
  
#Define a partition function by supplying the parent database and name arguments in the constructor.  
$pf =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionFunction -argumentlist $db, "TransHistPF"  
$T = [Microsoft.SqlServer.Management.SMO.DataType]::DateTime  
$T  
$T.GetType()  
#Add a partition function parameter that specifies the function uses a DateTime range type.  
$pfp =  New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionFunctionParameter -argumentlist $pf, $T  
  
#Specify the three dates that divide the data into four partitions.
#Create an array of type object to hold the partition data  
$val = "1/1/2003"."1/1/2004","1/1/2005"  
$pf.RangeValues = $val  
$pf  
#Create the partition function  
$pf.Create()  
  
#Create partition scheme  
$ps = New-Object -TypeName Microsoft.SqlServer.Management.SMO.PartitionScheme -argumentlist $db, "TransHistPS"  
$ps.PartitionFunction = "TransHistPF"  
  
#add the filegroups to the scheme
$ps.FileGroups.Add("PRIMARY")  
$ps.FileGroups.Add("Second")  
$ps.FileGroups.Add("Third")  
$ps.FileGroups.Add("Fourth")  
  
#Create it at the server  
$ps.Create()  
```  
  
## <a name="see-also"></a><span data-ttu-id="96fed-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96fed-124">See Also</span></span>  
 [<span data-ttu-id="96fed-125">Tabelle e indici partizionati</span><span class="sxs-lookup"><span data-stu-id="96fed-125">Partitioned Tables and Indexes</span></span>](../../partitions/partitioned-tables-and-indexes.md)  
