---
title: Rappresentazione del database (tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 16a233fb-f83b-4ca1-acb5-6186eca0a62c
author: minewiskan
ms.author: owend
ms.openlocfilehash: c327e07685e98e6fa9f992025510e869d909e5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626935"
---
# <a name="database-representationtabular"></a><span data-ttu-id="2c359-102">Rappresentazione del database(tabulare)</span><span class="sxs-lookup"><span data-stu-id="2c359-102">Database Representation(Tabular)</span></span>
  <span data-ttu-id="2c359-103">In modalità tabulare, il database è il contenitore per tutti gli oggetti del modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="2c359-103">In Tabular Mode, the database is the container for all objects in the tabular model.</span></span>  
  
## <a name="database-representation"></a><span data-ttu-id="2c359-104">Rappresentazione di un database</span><span class="sxs-lookup"><span data-stu-id="2c359-104">Database Representation</span></span>  
 <span data-ttu-id="2c359-105">Il database è il posto dove si trovano tutti gli oggetti che formano un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="2c359-105">The database is the place where all objects that form a tabular model reside.</span></span> <span data-ttu-id="2c359-106">All'interno del database lo sviluppatore trova oggetti come connessioni, tabelle, ruoli e molti altri ancora.</span><span class="sxs-lookup"><span data-stu-id="2c359-106">Contained by the database, the developer finds objects like connections, tables, roles and many more.</span></span>  
  
### <a name="database-in-amo"></a><span data-ttu-id="2c359-107">Database in AMO</span><span class="sxs-lookup"><span data-stu-id="2c359-107">Database in AMO</span></span>  
 <span data-ttu-id="2c359-108">Quando si utilizza AMO (Analysis Management Objects) per gestire un database modello tabulare, l'oggetto <xref:Microsoft.AnalysisServices.Database> ha una corrispondenza uno-a-uno in AMO (Analysis Management Objects) con l'oggetto logico del database in un modello tabulare.</span><span class="sxs-lookup"><span data-stu-id="2c359-108">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.Database> object in AMO matches one-to-one the database logical object in a tabular model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2c359-109">Per accedere a un oggetto di database, in AMO (Analysis Management Objects) l'utente deve avere accesso a un oggetto server e connettersi.</span><span class="sxs-lookup"><span data-stu-id="2c359-109">In order to gain access to a database object, in AMO, the user needs to have access to a server object and connect to it.</span></span>  
  
### <a name="database-in-adomdnet"></a><span data-ttu-id="2c359-110">Database in ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="2c359-110">Database in ADOMD.Net</span></span>  
 <span data-ttu-id="2c359-111">Quando si utilizza ADOMD per consultare ed eseguire una query su un database modello tabulare, la connessione a un database specifico si ottiene mediante l'oggetto <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>.</span><span class="sxs-lookup"><span data-stu-id="2c359-111">When using ADOMD to consult and query a tabular model database, connection to a specific database is obtained through the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> object.</span></span>  
  
 <span data-ttu-id="2c359-112">È possibile connettersi direttamente a un determinato database utilizzando il seguente frammento di codice:</span><span class="sxs-lookup"><span data-stu-id="2c359-112">You can connect directly to a certain database using the following code snippet:</span></span>  
  
```csharp  
using ADOMD = Microsoft.AnalysisServices.AdomdClient;  
...  
   ADOMD.AdomdConnection currrentCnx = new ADOMD.AdomdConnection("Data Source=<<server\instance>>;Catalog=<<database>>");  
   currrentCnx.Open();  
...  
  
```  
  
 <span data-ttu-id="2c359-113">Inoltre, tramite un oggetto connessione esistente (che non è stato chiuso) è possibile passare dal database corrente a un altro come mostrato nel seguente frammento di codice:</span><span class="sxs-lookup"><span data-stu-id="2c359-113">Also, over an existing connection object (that hasn't been closed), you can change the current database to another as shown in the following code snippet:</span></span>  
  
```csharp  
currentCnx.ChangeDatabase("myOtherDatabase");  
  
```  
  
## <a name="database-in-amo"></a><span data-ttu-id="2c359-114">Database in AMO</span><span class="sxs-lookup"><span data-stu-id="2c359-114">Database in AMO</span></span>  
 <span data-ttu-id="2c359-115">Quando si utilizza AMO per gestire un oggetto di database, iniziare con un oggetto <xref:Microsoft.AnalysisServices.Server>.</span><span class="sxs-lookup"><span data-stu-id="2c359-115">When using AMO to manage a database object, start with a <xref:Microsoft.AnalysisServices.Server> object.</span></span> <span data-ttu-id="2c359-116">Quindi cercare il database nella raccolta di database oppure creare un nuovo database aggiungendone uno alla raccolta.</span><span class="sxs-lookup"><span data-stu-id="2c359-116">Then search for your database in the databases collection or create a new database by adding one to the collection.</span></span>  
  
 <span data-ttu-id="2c359-117">Nel frammento di codice seguente vengono illustrati i passaggi per connettersi a un server e creare un database vuoto, dopo aver verificato che il database non esista:</span><span class="sxs-lookup"><span data-stu-id="2c359-117">The following code snippet shows the steps to connect to a server and create an empty database, after checking the database doesn't exist:</span></span>  
  
```  
  
AMO.Server CurrentServer = new AMO.Server();  
try  
{  
    CurrentServer.Connect(currentServerName);  
}  
catch (Exception cnxException)  
{  
    MessageBox.Show(string.Format("Error while trying to connect to server: [{0}]\nError message: {1}", currentServerName, cnxException.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    return;  
}  
newDatabaseName = DatabaseName.Text;  
if (CurrentServer.Databases.Contains(newDatabaseName))  
{  
    return;  
}  
try  
{  
    AMO.Database newDatabase = CurrentServer.Databases.Add(newDatabaseName);  
  
    CurrentServer.Update();  
}  
catch (Exception createDBxc)  
{  
    MessageBox.Show(String.Format("Database [{0}] couldn't be created.\n{1}", newDatabaseName, createDBxc.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    newDatabaseAvailable = false;  
}  
  
```  
  
 <span data-ttu-id="2c359-118">Per comprendere praticamente le modalità di utilizzo di AMO (Analysis Management Objects) per creare e modificare le rappresentazioni di database vedere il codice sorgente dell'esempio Tabular AMO 2012; in particolare controllare nel seguente file di origine: Database.cs.</span><span class="sxs-lookup"><span data-stu-id="2c359-118">For a practical understanding on how to use AMO to create and manipulate database representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="2c359-119">Il codice di esempio viene fornito solo come supporto ai concetti logici illustrati in questo argomento e non deve essere utilizzato in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="2c359-119">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  
