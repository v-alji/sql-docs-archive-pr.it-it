---
title: Impostazione delle proprietà | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SMO [SQL Server], properties
- SQL Server Management Objects, properties
- properties [SMO]
ms.assetid: 342569ba-d2f7-44d2-8f3f-ae9c701c7f0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: de381f8e4e9dfe9f6590638742e988f866ccabdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719800"
---
# <a name="setting-properties"></a><span data-ttu-id="cae73-102">Impostazione delle proprietà</span><span class="sxs-lookup"><span data-stu-id="cae73-102">Setting Properties</span></span>
  <span data-ttu-id="cae73-103">Le proprietà sono valori in cui sono archiviate informazioni descrittive sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="cae73-103">Properties are values that store descriptive information about the object.</span></span> <span data-ttu-id="cae73-104">Le opzioni di configurazione, ad esempio, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sono rappresentate dalle <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="cae73-104">For example, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] configuration options are represented by the <xref:Microsoft.SqlServer.Management.Smo.Server.Configuration%2A> object's properties.</span></span> <span data-ttu-id="cae73-105">Alle proprietà è possibile accedere direttamente o indirettamente utilizzando la relativa raccolta.</span><span class="sxs-lookup"><span data-stu-id="cae73-105">Properties can be accessed either directly or indirectly by using the property collection.</span></span> <span data-ttu-id="cae73-106">Per l'accesso diretto alle proprietà viene utilizzata la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="cae73-106">Accessing properties directly uses the following syntax:</span></span>  
  
 `objInstance.PropertyName`  
  
 <span data-ttu-id="cae73-107">Un valore di proprietà può essere modificato o recuperato a seconda che la proprietà disponga di accesso in lettura/scrittura o di accesso in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="cae73-107">A property value can be modified or retrieved depending on whether the property has read/write access or read-only access.</span></span> <span data-ttu-id="cae73-108">È inoltre necessario impostare determinate proprietà prima che sia possibile creare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cae73-108">It is also necessary to set certain properties before an object can be created.</span></span> <span data-ttu-id="cae73-109">Per ulteriori informazioni, vedere la documentazione di riferimento di SMO per l'oggetto specifico.</span><span class="sxs-lookup"><span data-stu-id="cae73-109">For more information, see the SMO reference for the particular object.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="cae73-110">Le raccolte di oggetti figlio vengono visualizzate come proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cae73-110">Collections of child objects appear as the property of an object.</span></span> <span data-ttu-id="cae73-111">La raccolta `Tables` è ad esempio una proprietà di un oggetto `Server`.</span><span class="sxs-lookup"><span data-stu-id="cae73-111">For example, the `Tables` collection is a property of a `Server` object.</span></span> <span data-ttu-id="cae73-112">Per altre informazioni, vedere [Using Collections](using-collections.md).</span><span class="sxs-lookup"><span data-stu-id="cae73-112">For more information, see [Using Collections](using-collections.md).</span></span>  
  
 <span data-ttu-id="cae73-113">Le proprietà di un oggetto sono membri della raccolta Properties.</span><span class="sxs-lookup"><span data-stu-id="cae73-113">The properties of an object are members of the Properties collection.</span></span> <span data-ttu-id="cae73-114">Tale raccolta può essere utilizzata per scorrere tutte le proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="cae73-114">The Properties collection can be used to iterate through every property of an object.</span></span>  
  
 <span data-ttu-id="cae73-115">Talvolta una proprietà non è disponibile per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cae73-115">Sometimes a property is not available for the following reasons:</span></span>  
  
-   <span data-ttu-id="cae73-116">La versione del server non supporta la proprietà, ad esempio se si tenta di accedere a una proprietà che rappresenta una nuova funzionalità di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in una versione precedente di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae73-116">The server version does not support the property, such as if you try to access a property that represents a new [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] feature on an older version of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="cae73-117">Il server non fornisce dati per la proprietà, ad esempio se si tenta di accedere a una proprietà che rappresenta un componente di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] non installato.</span><span class="sxs-lookup"><span data-stu-id="cae73-117">The server does not provide data for the property, such as if you try to access a property that represents a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] component that is not installed.</span></span>  
  
 <span data-ttu-id="cae73-118">Per gestire queste situazioni è possibile individuare le eccezioni SMO <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> e <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException>.</span><span class="sxs-lookup"><span data-stu-id="cae73-118">You can handle these circumstances by catching the <xref:Microsoft.SqlServer.Management.Smo.UnknownPropertyException> and the <xref:Microsoft.SqlServer.Management.Smo.PropertyCannotBeRetrievedException> SMO exceptions.</span></span>  
  
## <a name="setting-default-initialization-fields"></a><span data-ttu-id="cae73-119">Impostazione dei campi di inizializzazione predefiniti</span><span class="sxs-lookup"><span data-stu-id="cae73-119">Setting Default Initialization Fields</span></span>  
 <span data-ttu-id="cae73-120">SMO consente di eseguire un'ottimizzazione durante il recupero di oggetti.</span><span class="sxs-lookup"><span data-stu-id="cae73-120">SMO performs an optimization when retrieving objects.</span></span> <span data-ttu-id="cae73-121">L'ottimizzazione riduce il numero di proprietà caricate mediante il passaggio automatico tra gli stati seguenti:</span><span class="sxs-lookup"><span data-stu-id="cae73-121">The optimization minimizes the number of properties loaded by automatically scaling between the following states:</span></span>  
  
1.  <span data-ttu-id="cae73-122">Parzialmente caricato.</span><span class="sxs-lookup"><span data-stu-id="cae73-122">Partially loaded.</span></span> <span data-ttu-id="cae73-123">Quando viene fatto riferimento a un oggetto per la prima volta, esso dispone di un minimo di proprietà disponibili (ad esempio Name e Schema).</span><span class="sxs-lookup"><span data-stu-id="cae73-123">When an object is first referenced it has a minimum of properties available (such as Name and Schema).</span></span>  
  
2.  <span data-ttu-id="cae73-124">Completamente caricato.</span><span class="sxs-lookup"><span data-stu-id="cae73-124">Fully loaded.</span></span> <span data-ttu-id="cae73-125">Quando viene fatto riferimento a una proprietà, le proprietà restanti, che sono rapide da caricare, vengono inizializzate e rese disponibili.</span><span class="sxs-lookup"><span data-stu-id="cae73-125">When any property is referenced, the remaining properties that are quick to load, are initialized and are made available.</span></span>  
  
3.  <span data-ttu-id="cae73-126">Proprietà che utilizzano grandi quantità di memoria.</span><span class="sxs-lookup"><span data-stu-id="cae73-126">Properties that use lots of memory.</span></span> <span data-ttu-id="cae73-127">Le restanti proprietà non disponibili utilizzano grandi quantità di memoria e presentano un valore True per la proprietà <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> (ad esempio <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span><span class="sxs-lookup"><span data-stu-id="cae73-127">The remaining unavailable properties use lots of memory and have an <xref:Microsoft.SqlServer.Management.Smo.Property.Expensive%2A> property value of true (such as <xref:Microsoft.SqlServer.Management.Smo.Database.DataSpaceUsage%2A>).</span></span> <span data-ttu-id="cae73-128">Tali proprietà vengono caricate solo quando viene fatto loro riferimento in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="cae73-128">These properties are loaded only when specifically referenced.</span></span>  
  
 <span data-ttu-id="cae73-129">Se l'applicazione recupera proprietà aggiuntive, oltre a quelle fornite nello stato di caricamento parziale, invia una query per recuperarle e passa allo stato di caricamento completo.</span><span class="sxs-lookup"><span data-stu-id="cae73-129">If your application does fetch extra properties, besides the ones provided in the partially loaded state, it submits a query to retrieve these extra properties and scales up to the fully loaded state.</span></span> <span data-ttu-id="cae73-130">Ciò può provocare traffico non necessario tra il client e server.</span><span class="sxs-lookup"><span data-stu-id="cae73-130">This can cause unnecessary traffic between the client and server.</span></span> <span data-ttu-id="cae73-131">Per una maggiore ottimizzazione, è possibile chiamare il metodo <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A>.</span><span class="sxs-lookup"><span data-stu-id="cae73-131">More optimization can be achieved by calling the <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method.</span></span> <span data-ttu-id="cae73-132">Il metodo <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> consente la specifica delle proprietà caricate quando viene inizializzato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="cae73-132">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method allows specification of the properties that are loaded when the object is initialized.</span></span>  
  
 <span data-ttu-id="cae73-133">Il metodo <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> imposta il comportamento di caricamento della proprietà per la parte restante dell'applicazione o fino a quando non viene reimpostato.</span><span class="sxs-lookup"><span data-stu-id="cae73-133">The <xref:Microsoft.SqlServer.Management.Smo.Server.SetDefaultInitFields%2A> method sets the property loading behavior for the rest of application or until it is reset.</span></span> <span data-ttu-id="cae73-134">È possibile salvare il comportamento originale utilizzando il metodo <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> e ripristinarlo come necessario.</span><span class="sxs-lookup"><span data-stu-id="cae73-134">You can save the original behavior by using the <xref:Microsoft.SqlServer.Management.Smo.Server.GetDefaultInitFields%2A> method and restore it as required.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="cae73-135">Esempi</span><span class="sxs-lookup"><span data-stu-id="cae73-135">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="getting-and-setting-a-property-in-visual-basic"></a><span data-ttu-id="cae73-136">Ottenere e impostare una proprietà in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cae73-136">Getting and Setting a Property in Visual Basic</span></span>  
 <span data-ttu-id="cae73-137">In questo esempio di codice viene illustrato come ottenere la proprietà <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Information> e come impostare la proprietà <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> della proprietà <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> sul membro `ExecuteSql` del tipo enumerato <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="cae73-137">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties1](SMO How to#SMO_VBProperties1)]  -->  
  
## <a name="getting-and-setting-a-property-in-visual-c"></a><span data-ttu-id="cae73-138">Ottenere e impostare una proprietà in Visual C#</span><span class="sxs-lookup"><span data-stu-id="cae73-138">Getting and Setting a Property in Visual C#</span></span>  
 <span data-ttu-id="cae73-139">In questo esempio di codice viene illustrato come ottenere la proprietà <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Information> e come impostare la proprietà <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> della proprietà <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> sul membro `ExecuteSql` del tipo enumerato <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes>.</span><span class="sxs-lookup"><span data-stu-id="cae73-139">This code example shows how to get the <xref:Microsoft.SqlServer.Management.Smo.Information.Edition%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Information> object and how to set the <xref:Microsoft.SqlServer.Management.Common.ServerConnection.SqlExecutionModes%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Server.ConnectionContext%2A> property to the `ExecuteSql` member of the <xref:Microsoft.SqlServer.Management.Common.SqlExecutionModes> enumerated type.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Get a property.   
Console.WriteLine(srv.Information.Version);   
//Set a property.   
srv.ConnectionContext.SqlExecutionModes = SqlExecutionModes.ExecuteSql;   
}  
```  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-basic"></a><span data-ttu-id="cae73-140">Impostazione di diverse proprietà prima della creazione di un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cae73-140">Setting Various Properties Before an Object is Created in Visual Basic</span></span>  
 <span data-ttu-id="cae73-141">In questo esempio di codice viene illustrato come impostare direttamente la proprietà <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Table> e come creare e aggiungere colonne prima di creare l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="cae73-141">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties2](SMO How to#SMO_VBProperties2)]  -->  
  
## <a name="setting-various-properties-before-an-object-is-created-in-visual-c"></a><span data-ttu-id="cae73-142">Impostazione di diverse proprietà prima della creazione di un oggetto in Visual C#</span><span class="sxs-lookup"><span data-stu-id="cae73-142">Setting Various Properties Before an Object is Created in Visual C#</span></span>  
 <span data-ttu-id="cae73-143">In questo esempio di codice viene illustrato come impostare direttamente la proprietà <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.Table> e come creare e aggiungere colonne prima di creare l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Table>.</span><span class="sxs-lookup"><span data-stu-id="cae73-143">This code example shows how to directly set the <xref:Microsoft.SqlServer.Management.Smo.Table.AnsiNullsStatus%2A> property of the <xref:Microsoft.SqlServer.Management.Smo.Table> object, and how to create and add columns before you create the <xref:Microsoft.SqlServer.Management.Smo.Table> object.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Create a new table in the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
Table tb;   
//Specify the parent database, table schema, and the table name in the constructor.   
tb = new Table(db, "Test_Table", "HumanResources");   
//Add columns because the table requires columns before it can be created.   
Column c1;   
//Specify the parent table, the column name, and data type in the constructor.   
c1 = new Column(tb, "ID", DataType.Int);   
tb.Columns.Add(c1);   
c1.Nullable = false;   
c1.Identity = true;   
c1.IdentityIncrement = 1;   
c1.IdentitySeed = 0;   
Column c2;   
c2 = new Column(tb, "Name", DataType.NVarChar(100));   
c2.Nullable = false;   
tb.Columns.Add(c2);   
tb.AnsiNullsStatus = true;   
//Create the table on the instance of SQL Server.   
tb.Create();   
}  
```  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-basic"></a><span data-ttu-id="cae73-144">Scorrimento di tutte le proprietà di un oggetto in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cae73-144">Iterating Through All Properties of an Object in Visual Basic</span></span>  
 <span data-ttu-id="cae73-145">In questo esempio di codice viene eseguito lo scorrimento della raccolta `Properties` dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> e vengono visualizzati gli oggetti nella schermata di output di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae73-145">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
 <span data-ttu-id="cae73-146">Nell'esempio l'oggetto <xref:Microsoft.SqlServer.Management.Smo.Property> è stato inserito tra parentesi quadre in quanto è anche una parola chiave di [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae73-146">In the example, the <xref:Microsoft.SqlServer.Management.Smo.Property> object has been put in square parentheses because it is also a [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] keyword.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBProperties3](SMO How to#SMO_VBProperties3)]  -->  
  
## <a name="iterating-through-all-properties-of-an-object-in-visual-c"></a><span data-ttu-id="cae73-147">Scorrimento di tutte le proprietà di un oggetto in Visual C#</span><span class="sxs-lookup"><span data-stu-id="cae73-147">Iterating Through All Properties of an Object in Visual C#</span></span>  
 <span data-ttu-id="cae73-148">In questo esempio di codice viene eseguito lo scorrimento della raccolta `Properties` dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> e vengono visualizzati gli oggetti nella schermata di output di [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae73-148">This code example iterates through the `Properties` collection of the <xref:Microsoft.SqlServer.Management.Smo.StoredProcedure> object and displays them on the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] Output screen.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Set properties on the uspGetEmployeedManagers stored procedure on the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
StoredProcedure sp;   
sp = db.StoredProcedures("uspGetEmployeeManagers");   
sp.AnsiNullsStatus = false;   
sp.QuotedIdentifierStatus = false;   
//Iterate through the properties of the stored procedure and display.   
  Property p;   
  foreach ( p in sp.Properties) {   
    Console.WriteLine(p.Name + p.Value);   
  }   
}  
```  
  
## <a name="setting-default-initialization-fields-in-visual-basic"></a><span data-ttu-id="cae73-149">Impostazione dei campi di inizializzazione predefiniti in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cae73-149">Setting Default Initialization Fields in Visual Basic</span></span>  
 <span data-ttu-id="cae73-150">In questo esempio di codice viene illustrato come ridurre il numero di proprietà dell'oggetto inizializzate in un programma SMO.</span><span class="sxs-lookup"><span data-stu-id="cae73-150">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="cae73-151">È necessario includere l'istruzione `using System.Collections.Specialized` per utilizzare l'oggetto <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="cae73-151">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="cae73-152">consente di confrontare il numero di istruzioni inviate all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con questa ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="cae73-152">can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDefaultInitFields1](SMO How to#SMO_VBDefaultInitFields1)]  -->  
  
## <a name="setting-default-initialization-fields-in-visual-c"></a><span data-ttu-id="cae73-153">Impostazione dei campi di inizializzazione predefiniti in Visual C#</span><span class="sxs-lookup"><span data-stu-id="cae73-153">Setting Default Initialization Fields in Visual C#</span></span>  
 <span data-ttu-id="cae73-154">In questo esempio di codice viene illustrato come ridurre il numero di proprietà dell'oggetto inizializzate in un programma SMO.</span><span class="sxs-lookup"><span data-stu-id="cae73-154">This code example shows how to minimize the number of object properties initialized in an SMO program.</span></span> <span data-ttu-id="cae73-155">È necessario includere l'istruzione `using System.Collections.Specialized` per utilizzare l'oggetto <xref:System.Collections.Specialized.StringCollection>.</span><span class="sxs-lookup"><span data-stu-id="cae73-155">You have to include the `using System.Collections.Specialized`; statement to use the <xref:System.Collections.Specialized.StringCollection> object.</span></span>  
  
 [!INCLUDE[ssSqlProfiler](../../../includes/sssqlprofiler-md.md)] <span data-ttu-id="cae73-156">consente di confrontare il numero di istruzioni inviate all'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con questa ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="cae73-156">can be used to compare the number statements sent to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with this optimization.</span></span>  
  
```  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Reference the AdventureWorks2012 database.   
Database db;   
db = srv.Databases("AdventureWorks2012");   
//Assign the Table object type to a System.Type object variable.   
Table tb;   
Type typ;   
tb = new Table();   
typ = tb.GetType;   
//Assign the current default initialization fields for the Table object type to a   
//StringCollection object variable.   
StringCollection sc;   
sc = srv.GetDefaultInitFields(typ);   
//Set the default initialization fields for the Table object type to the CreateDate property.   
srv.SetDefaultInitFields(typ, "CreateDate");   
//Retrieve the Schema, Name, and CreateDate properties for every table in AdventureWorks2012.   
   //Note that the improvement in performance can be viewed in SQL Server Profiler.   
foreach ( tb in db.Tables) {   
   Console.WriteLine(tb.Schema + "." + tb.Name + " " + tb.CreateDate);   
}   
//Set the default initialization fields for the Table object type back to the original settings.   
srv.SetDefaultInitFields(typ, sc);   
}  
```  
  
  
