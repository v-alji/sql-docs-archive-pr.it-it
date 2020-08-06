---
title: Gestione degli eventi SMO | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- events [SMO]
- SQL Server Management Objects, events
- SMO [SQL Server], events
- events [SMO], about events
ms.assetid: b4f120dd-ba78-46ff-99c5-e47effac8544
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7ea438142ac283c5ad19670fa827b5e248e80f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637202"
---
# <a name="handling-smo-events"></a><span data-ttu-id="3d1e4-102">Gestione degli eventi SMO</span><span class="sxs-lookup"><span data-stu-id="3d1e4-102">Handling SMO Events</span></span>
  <span data-ttu-id="3d1e4-103">Vi sono tipi di eventi del server che possono essere sottoscritti tramite un gestore di eventi e l'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-103">There are server event types that can be subscribed to by using an event handler and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object.</span></span>  
  
 <span data-ttu-id="3d1e4-104">Molte delle classi di istanze in SMO ([!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects) possono attivare eventi quando si verificano determinate azioni nel server.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-104">Many of the instance classes in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) can trigger events when certain actions on the server occur.</span></span>  
  
 <span data-ttu-id="3d1e4-105">Questi eventi possono essere gestiti a livello di codice configurando un gestore evento e sottoscrivendo gli eventi associati.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-105">These events can be handled programmatically by setting up an event handler and subscribing to the associated events.</span></span> <span data-ttu-id="3d1e4-106">Questo tipo di gestione degli eventi è temporanea perché quando viene chiuso il programma client SMO vengono rimosse tutte le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-106">This type of event handling is transient because all the subscriptions are removed when the SMO client program exits.</span></span>  
  
## <a name="connectioncontext-event-handling"></a><span data-ttu-id="3d1e4-107">Gestione degli eventi ConnectionContext</span><span class="sxs-lookup"><span data-stu-id="3d1e4-107">ConnectionContext Event Handling</span></span>  
 <span data-ttu-id="3d1e4-108">L'oggetto <xref:Microsoft.SqlServer.Management.Common.ServerConnection> supporta diversi tipi di evento.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-108">The <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object supports several event types.</span></span> <span data-ttu-id="3d1e4-109">La proprietà dell'evento deve essere impostata su un'istanza di un gestore evento appropriato e l'oggetto gestore evento deve essere definito come una funzione protetta che gestisce l'evento.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-109">The event property must be set to an instance of an appropriate event handler, and the event handler object must be defined as a protected function that handles the event.</span></span>  
  
## <a name="event-subscription"></a><span data-ttu-id="3d1e4-110">Sottoscrizione di eventi</span><span class="sxs-lookup"><span data-stu-id="3d1e4-110">Event Subscription</span></span>  
 <span data-ttu-id="3d1e4-111">Per gestire gli eventi è necessario scrivere una classe del gestore evento, crearne un'istanza, assegnare il gestore evento all'oggetto padre e infine effettuare la sottoscrizione all'evento.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-111">You handle events by writing an event handler class, creating an instance of it, assigning the event handler to the parent object, and then subscribing to the event.</span></span>  
  
 <span data-ttu-id="3d1e4-112">Per gestire gli eventi, è necessario scrivere una classe del gestore evento.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-112">An event handler class must be written to handle events.</span></span> <span data-ttu-id="3d1e4-113">La classe del gestore evento può contenere più di una funzione del gestore evento e deve essere installata per poter gestire gli eventi.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-113">The event handler class can contain more than one event handler function, and must be installed for the events to be handled.</span></span> <span data-ttu-id="3d1e4-114">Le funzioni del gestore eventi ricevono informazioni sull'evento dal parametro *ServerEventNotificatificationArgs* che può essere usato per segnalare le informazioni relative all'evento.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-114">The event handler functions receive information about the event from the *ServerEventNotificatificationArgs* parameter that can be used to report information about the event.</span></span>  
  
 <span data-ttu-id="3d1e4-115">I tipi di eventi del database e del server che possono essere gestiti sono elencati nella <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> classe e nella <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet> classe.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-115">The types of database and server events that can be handled are listed in the <xref:Microsoft.SqlServer.Management.Smo.DatabaseEventSet> class and the <xref:Microsoft.SqlServer.Management.Smo.ServerEventSet>class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d1e4-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d1e4-116">Example</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-basic"></a><span data-ttu-id="3d1e4-117">Registrazione di gestori di eventi e sottoscrizione della gestione degli eventi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d1e4-117">Registering Event Handlers and Subscribing to Event Handling in Visual Basic</span></span>  
 <span data-ttu-id="3d1e4-118">In questo esempio di codice viene illustrato come configurare il gestore dell'evento e come effettuare la sottoscrizione degli eventi del database.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-118">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBEvents1](SMO How to#SMO_VBEvents1)]  -->  
  
## <a name="registering-event-handlers-and-subscribing-to-event-handling-in-visual-c"></a><span data-ttu-id="3d1e4-119">Registrazione di gestori di eventi e sottoscrizione della gestione degli eventi in Visual C#</span><span class="sxs-lookup"><span data-stu-id="3d1e4-119">Registering Event Handlers and Subscribing to Event Handling in Visual C#</span></span>  
 <span data-ttu-id="3d1e4-120">In questo esempio di codice viene illustrato come configurare il gestore dell'evento e come effettuare la sottoscrizione degli eventi del database.</span><span class="sxs-lookup"><span data-stu-id="3d1e4-120">This code example shows how to set up the event handler, and how to subscribe to the database events.</span></span>  
  
```  
//Create an event handler subroutine that runs when a table is created.   
private void MyCreateEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been added to the AdventureWorks2012 database.");   
}   
//Create an event handler subroutine that runs when a table is deleted.   
private void MyDropEventHandler(object sender, ServerEventArgs e)   
{   
Console.WriteLine("A table has just been dropped from the AdventureWorks2012 database.");   
}   
public void Main()   
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Create a database event set that contains the CreateTable event only.   
DatabaseEventSet databaseCreateEventSet = new DatabaseEventSet();   
databaseCreateEventSet.CreateTable = true;   
//Create a server event handler and set it to the first event handler subroutine.   
ServerEventHandler serverCreateEventHandler;   
serverCreateEventHandler = new ServerEventHandler(MyCreateEventHandler);   
//Subscribe to the first server event handler when a CreateTable event occurs.   
db.Events.SubscribeToEvents(databaseCreateEventSet, serverCreateEventHandler);   
    //Create a database event set that contains the DropTable event only.   
DatabaseEventSet databaseDropEventSet = new DatabaseEventSet();   
databaseDropEventSet.DropTable = true;   
//Create a server event handler and set it to the second event handler subroutine.   
ServerEventHandler serverDropEventHandler;   
serverDropEventHandler = new ServerEventHandler(MyDropEventHandler);   
//Subscribe to the second server event handler when a DropTable event occurs.   
db.Events.SubscribeToEvents(databaseDropEventSet, serverDropEventHandler);   
//Start event handling.   
db.Events.StartEvents();   
//Create a table on the database.   
Table tb;   
tb = new Table(db, "Test_Table");   
Column mycol1;   
mycol1 = new Column(tb, "Name", DataType.NChar(50));   
mycol1.Collation = "Latin1_General_CI_AS";   
mycol1.Nullable = true;   
tb.Columns.Add(mycol1);   
tb.Create();   
//Remove the table.   
tb.Drop();   
//Wait until the events have occured.   
int x;   
int y;   
for (x = 1; x <= 1000000000; x++) {   
    y = x * 2;   
}   
//Stop event handling.   
db.Events.StopEvents();   
}  
```  
  
  
