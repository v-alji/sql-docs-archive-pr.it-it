---
title: Set di righe | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- rowsets [OLE DB], about rowsets
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets
- OLE DB rowsets, about rowsets
- rowsets [OLE DB]
ms.assetid: 5e7b3cbe-3670-4e18-8172-2226e0b6b142
author: rothja
ms.author: jroth
ms.openlocfilehash: 1245d17dc0f3757b3c212146c8c162de6e48a483
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626082"
---
# <a name="rowsets"></a><span data-ttu-id="b94b2-102">Set di righe</span><span class="sxs-lookup"><span data-stu-id="b94b2-102">Rowsets</span></span>
  <span data-ttu-id="b94b2-103">Le righe di un set di righe contengono colonne di dati.</span><span class="sxs-lookup"><span data-stu-id="b94b2-103">A rowset is a set of rows that contain columns of data.</span></span> <span data-ttu-id="b94b2-104">I set di righe sono oggetti centrali che consentono a tutti i provider di dati OLE DB di esporre dati di set di risultati in formato tabulare.</span><span class="sxs-lookup"><span data-stu-id="b94b2-104">Rowsets are central objects that enable all OLE DB data providers to expose result set data in tabular form.</span></span>  
  
 <span data-ttu-id="b94b2-105">Dopo aver creato una sessione mediante il metodo **IDBCreateSession::CreateSession**, il consumer può usare l'interfaccia **IOpenRowset** o **IDBCreateCommand** nella sessione per creare un set di righe.</span><span class="sxs-lookup"><span data-stu-id="b94b2-105">After a consumer creates a session by using the **IDBCreateSession::CreateSession** method, the consumer can use either the **IOpenRowset** or **IDBCreateCommand** interface on the session to create a rowset.</span></span> <span data-ttu-id="b94b2-106">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta entrambe le interfacce.</span><span class="sxs-lookup"><span data-stu-id="b94b2-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports both of these interfaces.</span></span> <span data-ttu-id="b94b2-107">Di seguito sono descritti i due metodi.</span><span class="sxs-lookup"><span data-stu-id="b94b2-107">Both of these methods are described here.</span></span>  
  
-   <span data-ttu-id="b94b2-108">Creare un set di righe chiamando il metodo **IOpenRowset::OpenRowset**.</span><span class="sxs-lookup"><span data-stu-id="b94b2-108">Create a rowset by calling the **IOpenRowset::OpenRowset** method.</span></span>  
  
     <span data-ttu-id="b94b2-109">Questo metodo equivale a chiamare un set di righe in una singola tabella</span><span class="sxs-lookup"><span data-stu-id="b94b2-109">This is equivalent to creating a rowset over a single table.</span></span> <span data-ttu-id="b94b2-110">e consente di aprire e restituire un set di righe che include tutte le righe di una singola tabella di base.</span><span class="sxs-lookup"><span data-stu-id="b94b2-110">This method opens and returns a rowset that includes all of the rows from a single base table.</span></span> <span data-ttu-id="b94b2-111">Uno degli argomenti di **OpenRowset** è un ID di tabella che identifica la tabella dalla quale creare il set di righe.</span><span class="sxs-lookup"><span data-stu-id="b94b2-111">One of the arguments to **OpenRowset** is a table ID that identifies the table from which to create the rowset.</span></span>  
  
-   <span data-ttu-id="b94b2-112">Creare un oggetto comando chiamando il metodo **IDBCreateCommand::CreateCommand**.</span><span class="sxs-lookup"><span data-stu-id="b94b2-112">Create a command object by calling the **IDBCreateCommand::CreateCommand** method.</span></span>  
  
     <span data-ttu-id="b94b2-113">L'oggetto comando esegue comandi supportati dal provider.</span><span class="sxs-lookup"><span data-stu-id="b94b2-113">The command object executes commands that the provider supports.</span></span> <span data-ttu-id="b94b2-114">Con il provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, il consumer può specificare qualsiasi istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)], ad esempio un'istruzione SELECT o una chiamata a una stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b94b2-114">With the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the consumer can specify any [!INCLUDE[tsql](../../includes/tsql-md.md)] statement, such as a SELECT statement or a call to a stored procedure.</span></span> <span data-ttu-id="b94b2-115">Di seguito sono elencati i passaggi per la creazione di un set di righe tramite un oggetto comando:</span><span class="sxs-lookup"><span data-stu-id="b94b2-115">The steps for creating a rowset by using a command object are:</span></span>  
  
    1.  <span data-ttu-id="b94b2-116">Il consumer chiama il metodo **IDBCreateCommand::CreateCommand** nella sessione per ottenere un oggetto comando che richieda l'interfaccia **ICommandText** sull'oggetto stesso.</span><span class="sxs-lookup"><span data-stu-id="b94b2-116">The consumer calls the **IDBCreateCommand::CreateCommand** method on the session to get a command object requesting the **ICommandText** interface on the command object.</span></span> <span data-ttu-id="b94b2-117">Questa interfaccia **ICommandText** imposta e recupera il testo del comando effettivo.</span><span class="sxs-lookup"><span data-stu-id="b94b2-117">This **ICommandText** interface sets and retrieves the actual command text.</span></span> <span data-ttu-id="b94b2-118">Il consumer inserisce il comando di testo chiamando il metodo **ICommandText::SetCommandText**.</span><span class="sxs-lookup"><span data-stu-id="b94b2-118">The consumer fills in the text command by calling the **ICommandText::SetCommandText** method.</span></span>  
  
    2.  <span data-ttu-id="b94b2-119">L'utente chiama il metodo **ICommand::Execute** sul comando.</span><span class="sxs-lookup"><span data-stu-id="b94b2-119">The user calls the **ICommand::Execute** method on the command.</span></span> <span data-ttu-id="b94b2-120">L'oggetto set di righe compilato durante l'esecuzione del comando contiene il set di risultati restituito dal comando.</span><span class="sxs-lookup"><span data-stu-id="b94b2-120">The rowset object built when the command executes contains the result set from the command.</span></span>  
  
 <span data-ttu-id="b94b2-121">Nel consumer è possibile usare l'interfaccia **ICommandProperties** per ottenere o impostare le proprietà per il set di righe restituito dal comando eseguito dalle interfacce **ICommand::Execute**.</span><span class="sxs-lookup"><span data-stu-id="b94b2-121">The consumer can use the **ICommandProperties** interface to get or set the properties for the rowset returned by the command executed by the **ICommand::Execute** interfaces.</span></span> <span data-ttu-id="b94b2-122">Le proprietà generalmente più richieste sono le interfacce che il set di righe deve supportare.</span><span class="sxs-lookup"><span data-stu-id="b94b2-122">The most commonly requested properties are the interfaces the rowset must support.</span></span> <span data-ttu-id="b94b2-123">Oltre alle interfacce, il consumer può richiedere proprietà che modificano il comportamento del set di righe o dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b94b2-123">In addition to interfaces, the consumer can request properties that modify the behavior of the rowset or interface.</span></span>  
  
 <span data-ttu-id="b94b2-124">I consumer rilasciano set di righe con il metodo **IRowset::Release**.</span><span class="sxs-lookup"><span data-stu-id="b94b2-124">Consumers release rowsets with the **IRowset::Release** method.</span></span> <span data-ttu-id="b94b2-125">Il rilascio di un set di righe comporta anche il rilascio di tutti gli handle di riga gestiti dal consumer per tale set di righe,</span><span class="sxs-lookup"><span data-stu-id="b94b2-125">Releasing a rowset releases any row handles held by the consumer on that rowset.</span></span> <span data-ttu-id="b94b2-126">ma non comporta il rilascio delle funzioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="b94b2-126">Releasing a rowset does not release the accessors.</span></span> <span data-ttu-id="b94b2-127">Se si ha un'interfaccia **IAccessor**, questa deve essere comunque rilasciata.</span><span class="sxs-lookup"><span data-stu-id="b94b2-127">If you have an **IAccessor** interface, it still has to be released.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b94b2-128">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b94b2-128">In This Section</span></span>  
  
-   [<span data-ttu-id="b94b2-129">Creazione di un set di righe con IOpenRowset</span><span class="sxs-lookup"><span data-stu-id="b94b2-129">Creating a Rowset with IOpenRowset</span></span>](creating-a-rowset-with-iopenrowset.md)  
  
-   [<span data-ttu-id="b94b2-130">Creazione di set di righe con ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="b94b2-130">Creating Rowsets with ICommand::Execute</span></span>](creating-rowsets-with-icommand-execute.md)  
  
-   [<span data-ttu-id="b94b2-131">Proprietà e comportamenti dei set di righe</span><span class="sxs-lookup"><span data-stu-id="b94b2-131">Rowset Properties and Behaviors</span></span>](rowset-properties-and-behaviors.md)  
  
-   [<span data-ttu-id="b94b2-132">Set di righe e cursori di Server SQL</span><span class="sxs-lookup"><span data-stu-id="b94b2-132">Rowsets and SQL Server Cursors</span></span>](rowsets-and-sql-server-cursors.md)  
  
-   [<span data-ttu-id="b94b2-133">Recupero di righe</span><span class="sxs-lookup"><span data-stu-id="b94b2-133">Fetching Rows</span></span>](fetching-rows.md)  
  
-   [<span data-ttu-id="b94b2-134">Recupero di una sola riga utilizzando IRow</span><span class="sxs-lookup"><span data-stu-id="b94b2-134">Fetching a Single Row with IRow</span></span>](fetching-a-single-row-with-irow.md)  
  
-   [<span data-ttu-id="b94b2-135">Bookmarks</span><span class="sxs-lookup"><span data-stu-id="b94b2-135">Bookmarks</span></span>](bookmarks.md)  
  
-   [<span data-ttu-id="b94b2-136">Aggiornamento dei dati dei set di righe</span><span class="sxs-lookup"><span data-stu-id="b94b2-136">Updating Data in Rowsets</span></span>](updating-data-in-rowsets.md)  
  
## <a name="see-also"></a><span data-ttu-id="b94b2-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b94b2-137">See Also</span></span>  
 [<span data-ttu-id="b94b2-138">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b94b2-138">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
