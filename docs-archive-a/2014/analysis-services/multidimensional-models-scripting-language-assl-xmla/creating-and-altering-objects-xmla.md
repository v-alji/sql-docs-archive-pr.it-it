---
title: Creazione e modifica di oggetti (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [XML for Analysis]
- subordinate objects [XML for Analysis]
- XML for Analysis, objects
- modifying objects
- removing objects
- deleting objects
- XMLA, objects
ms.assetid: a2080867-e130-440c-92eb-f768869f34a8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2390c0b921368e7e06f0e5563a7eb59769d99c17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636447"
---
# <a name="creating-and-altering-objects-xmla"></a><span data-ttu-id="2b928-102">Creazione e modifica di oggetti (XMLA)</span><span class="sxs-lookup"><span data-stu-id="2b928-102">Creating and Altering Objects (XMLA)</span></span>
  <span data-ttu-id="2b928-103">Gli oggetti principali possono essere creati, modificati ed eliminati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="2b928-103">Major objects can be independently created, altered, and deleted.</span></span> <span data-ttu-id="2b928-104">Di seguito vengono elencati gli oggetti principali:</span><span class="sxs-lookup"><span data-stu-id="2b928-104">Major objects include the following objects:</span></span>  
  
-   <span data-ttu-id="2b928-105">Server</span><span class="sxs-lookup"><span data-stu-id="2b928-105">Servers</span></span>  
  
-   <span data-ttu-id="2b928-106">Database</span><span class="sxs-lookup"><span data-stu-id="2b928-106">Databases</span></span>  
  
-   <span data-ttu-id="2b928-107">Dimensioni</span><span class="sxs-lookup"><span data-stu-id="2b928-107">Dimensions</span></span>  
  
-   <span data-ttu-id="2b928-108">Cubi</span><span class="sxs-lookup"><span data-stu-id="2b928-108">Cubes</span></span>  
  
-   <span data-ttu-id="2b928-109">Gruppi di misure</span><span class="sxs-lookup"><span data-stu-id="2b928-109">Measure groups</span></span>  
  
-   <span data-ttu-id="2b928-110">Partizioni</span><span class="sxs-lookup"><span data-stu-id="2b928-110">Partitions</span></span>  
  
-   <span data-ttu-id="2b928-111">Prospettive</span><span class="sxs-lookup"><span data-stu-id="2b928-111">Perspectives</span></span>  
  
-   <span data-ttu-id="2b928-112">Modelli di data mining</span><span class="sxs-lookup"><span data-stu-id="2b928-112">Mining models</span></span>  
  
-   <span data-ttu-id="2b928-113">Ruoli</span><span class="sxs-lookup"><span data-stu-id="2b928-113">Roles</span></span>  
  
-   <span data-ttu-id="2b928-114">Comandi associati a un server o a un database</span><span class="sxs-lookup"><span data-stu-id="2b928-114">Commands associated with a server or database</span></span>  
  
-   <span data-ttu-id="2b928-115">Origini dati</span><span class="sxs-lookup"><span data-stu-id="2b928-115">Data sources</span></span>  
  
 <span data-ttu-id="2b928-116">Usare il comando [create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) per creare un oggetto principale in un'istanza di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e il comando [ALTER](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) per modificare un oggetto principale esistente in un'istanza di.</span><span class="sxs-lookup"><span data-stu-id="2b928-116">You use the [Create](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla) command to create a major object on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], and the [Alter](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) command to alter an existing major object on an instance.</span></span> <span data-ttu-id="2b928-117">Entrambi i comandi vengono eseguiti usando il metodo [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) .</span><span class="sxs-lookup"><span data-stu-id="2b928-117">Both commands are run using the [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="2b928-118">Creazione di oggetti</span><span class="sxs-lookup"><span data-stu-id="2b928-118">Creating Objects</span></span>  
 <span data-ttu-id="2b928-119">Quando si creano oggetti tramite il metodo `Create`, è necessario innanzitutto identificare l'oggetto padre che contiene l'oggetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] da creare.</span><span class="sxs-lookup"><span data-stu-id="2b928-119">When you create objects by using the `Create` method, you must first identify the parent object that contains the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] object to be created.</span></span> <span data-ttu-id="2b928-120">Per identificare l'oggetto padre, fornire un riferimento all'oggetto nella proprietà [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `Create` comando.</span><span class="sxs-lookup"><span data-stu-id="2b928-120">You identify the parent object by providing an object reference in the [ParentObject](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Create` command.</span></span> <span data-ttu-id="2b928-121">Ogni riferimento all'oggetto contiene gli identificatori dell'oggetto necessari per identificare in modo univoco l'oggetto padre per il comando `Create`.</span><span class="sxs-lookup"><span data-stu-id="2b928-121">Each object reference contains the object identifiers needed to uniquely identify the parent object for the `Create` command.</span></span> <span data-ttu-id="2b928-122">Per ulteriori informazioni sui riferimenti a oggetti, vedere [definizione e identificazione di oggetti &#40;&#41;XMLA ](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="2b928-122">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="2b928-123">Si supponga ad esempio che sia necessario fornire un riferimento a un oggetto per un cubo per creare un nuovo gruppo di misure per il cubo stesso.</span><span class="sxs-lookup"><span data-stu-id="2b928-123">For example, you must provide an object reference to a cube to create a new measure group for the cube.</span></span> <span data-ttu-id="2b928-124">Il riferimento all'oggetto per il cubo nella proprietà `ParentObject` contiene sia un identificatore di database che un identificatore del cubo poiché lo stesso identificatore del cubo potrebbe essere utilizzato in un database diverso.</span><span class="sxs-lookup"><span data-stu-id="2b928-124">The object reference for the cube in the `ParentObject` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="2b928-125">L'elemento [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) contiene Analysis Services elementi ASSL (Scripting Language) che definiscono l'oggetto principale da creare.</span><span class="sxs-lookup"><span data-stu-id="2b928-125">The [ObjectDefinition](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/objectdefinition-element-xmla) element contains Analysis Services Scripting Language (ASSL) elements that define the major object to be created.</span></span> <span data-ttu-id="2b928-126">Per ulteriori informazioni su ASSL, vedere [sviluppo con Analysis Services linguaggio di scripting &#40;assl&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="2b928-126">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="2b928-127">Se si imposta l'attributo `AllowOverwrite` del comando `Create` su true, è possibile sovrascrivere un oggetto principale esistente con l'identificatore specificato.</span><span class="sxs-lookup"><span data-stu-id="2b928-127">If you set the `AllowOverwrite` attribute of the `Create` command to true, you can overwrite an existing major object that has the specified identifier.</span></span> <span data-ttu-id="2b928-128">In caso contrario, se un oggetto principale con l'identificatore specificato esiste già nell'oggetto padre si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="2b928-128">Otherwise, an error occurs if a major object that has the specified identifier already exists in the parent object.</span></span>  
  
 <span data-ttu-id="2b928-129">Per ulteriori informazioni sul `Create` comando, vedere [Create element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="2b928-129">For more information about the `Create` command, see [Create Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla).</span></span>  
  
### <a name="creating-session-objects"></a><span data-ttu-id="2b928-130">Creazione di oggetti di sessione</span><span class="sxs-lookup"><span data-stu-id="2b928-130">Creating Session Objects</span></span>  
 <span data-ttu-id="2b928-131">Gli oggetti di sessione sono oggetti temporanei disponibili solo nella sessione esplicita o implicita utilizzata da un'applicazione client che vengono eliminati quando la sessione è terminata.</span><span class="sxs-lookup"><span data-stu-id="2b928-131">Session objects are temporary objects that are available only to the explicit or implicit session used by a client application and are deleted when the session is ended.</span></span> <span data-ttu-id="2b928-132">È possibile creare oggetti sessione impostando l' `Scope` attributo del `Create` comando su *sessione*.</span><span class="sxs-lookup"><span data-stu-id="2b928-132">You can create session objects by setting the `Scope` attribute of the `Create` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b928-133">Quando si utilizza l'impostazione della *sessione* , l' `ObjectDefinition` elemento può contenere solo elementi ASSL di [dimensione](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [cubo](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)o [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) .</span><span class="sxs-lookup"><span data-stu-id="2b928-133">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="altering-objects"></a><span data-ttu-id="2b928-134">Modifica di oggetti</span><span class="sxs-lookup"><span data-stu-id="2b928-134">Altering Objects</span></span>  
 <span data-ttu-id="2b928-135">Quando si modificano gli oggetti usando il `Alter` metodo, è necessario innanzitutto identificare l'oggetto da modificare fornendo un riferimento a un oggetto nella proprietà [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) del `Alter` comando.</span><span class="sxs-lookup"><span data-stu-id="2b928-135">When modifying objects by using the `Alter` method, you must first identify the object to be modified by providing an object reference in the [Object](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/object-element-xmla) property of the `Alter` command.</span></span> <span data-ttu-id="2b928-136">Ogni riferimento all'oggetto contiene gli identificatori dell'oggetto necessari per identificare in modo univoco l'oggetto per il comando `Alter`.</span><span class="sxs-lookup"><span data-stu-id="2b928-136">Each object reference contains the object identifiers needed to uniquely identify the object for the `Alter` command.</span></span> <span data-ttu-id="2b928-137">Per ulteriori informazioni sui riferimenti a oggetti, vedere [definizione e identificazione di oggetti &#40;&#41;XMLA ](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span><span class="sxs-lookup"><span data-stu-id="2b928-137">For more information about object references, see [Defining and Identifying Objects &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-objects).</span></span>  
  
 <span data-ttu-id="2b928-138">Si supponga ad esempio che sia necessario fornire un riferimento a un oggetto per un cubo per modificarne la struttura.</span><span class="sxs-lookup"><span data-stu-id="2b928-138">For example, you must provide an object reference to a cube in order to modify the structure of a cube.</span></span> <span data-ttu-id="2b928-139">Il riferimento all'oggetto per il cubo nella proprietà `Object` contiene sia un identificatore di database che un identificatore del cubo poiché lo stesso identificatore del cubo potrebbe essere utilizzato in un database diverso.</span><span class="sxs-lookup"><span data-stu-id="2b928-139">The object reference for the cube in the `Object` property contains both a database identifier and a cube identifier, as the same cube identifier could potentially be used on a different database.</span></span>  
  
 <span data-ttu-id="2b928-140">L'elemento `ObjectDefinition` contiene elementi ASSL che definiscono l'oggetto principale da modificare.</span><span class="sxs-lookup"><span data-stu-id="2b928-140">The `ObjectDefinition` element contains ASSL elements that define the major object to be modified.</span></span> <span data-ttu-id="2b928-141">Per ulteriori informazioni su ASSL, vedere [sviluppo con Analysis Services linguaggio di scripting &#40;assl&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span><span class="sxs-lookup"><span data-stu-id="2b928-141">For more information about ASSL, see [Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md).</span></span>  
  
 <span data-ttu-id="2b928-142">Se si imposta l'attributo `AllowCreate` del comando `Alter` su true, è possibile creare l'oggetto principale specificato qualora non esista.</span><span class="sxs-lookup"><span data-stu-id="2b928-142">If you set the `AllowCreate` attribute of the `Alter` command to true, you can create the specified major object if the object does not exist.</span></span> <span data-ttu-id="2b928-143">In caso contrario, se un oggetto principale specificato non esiste si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="2b928-143">Otherwise, an error occurs if a specified major object does not already exist.</span></span>  
  
### <a name="using-the-objectexpansion-attribute"></a><span data-ttu-id="2b928-144">Utilizzo dell'attributo ObjectExpansion</span><span class="sxs-lookup"><span data-stu-id="2b928-144">Using the ObjectExpansion Attribute</span></span>  
 <span data-ttu-id="2b928-145">Se si modificano solo le proprietà dell'oggetto principale e non si ridefiniscono gli oggetti secondari contenuti nell'oggetto principale, è possibile impostare l' `ObjectExpansion` attributo del `Alter` comando su *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="2b928-145">If you are changing only the properties of the major object and are not redefining minor objects that are contained by the major object, you can set the `ObjectExpansion` attribute of the `Alter` command to *ObjectProperties*.</span></span> <span data-ttu-id="2b928-146">La proprietà `ObjectDefinition` deve contenere pertanto solo gli elementi per le proprietà dell'oggetto principale e il comando `Alter` non modifica gli oggetti secondari associati all'oggetto principale.</span><span class="sxs-lookup"><span data-stu-id="2b928-146">The `ObjectDefinition` property then only has to contain the elements for the properties of the major object, and the `Alter` command leaves minor objects associated with the major object untouched.</span></span>  
  
 <span data-ttu-id="2b928-147">Per ridefinire gli oggetti secondari per un oggetto principale, è necessario impostare l' `ObjectExpansion` attributo su *ExpandFull* e la definizione dell'oggetto deve includere tutti gli oggetti secondari contenuti nell'oggetto principale.</span><span class="sxs-lookup"><span data-stu-id="2b928-147">To redefine minor objects for a major object, you must set the `ObjectExpansion` attribute to *ExpandFull* and the object definition must include all minor objects that are contained by the major object.</span></span> <span data-ttu-id="2b928-148">Se la proprietà `ObjectDefinition` del comando `Alter` non include in modo esplicito un oggetto secondario contenuto in quello principale, l'oggetto secondario non incluso viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="2b928-148">If the `ObjectDefinition` property of the `Alter` command does not explicitly include a minor object that is contained by the major object, the minor object that was not included is deleted.</span></span>  
  
### <a name="altering-session-objects"></a><span data-ttu-id="2b928-149">Modifica di oggetti di sessione</span><span class="sxs-lookup"><span data-stu-id="2b928-149">Altering Session Objects</span></span>  
 <span data-ttu-id="2b928-150">Per modificare gli oggetti sessione creati dal `Create` comando, impostare l' `Scope` attributo del `Alter` comando su *sessione*.</span><span class="sxs-lookup"><span data-stu-id="2b928-150">To modify session objects created by the `Create` command, set the `Scope` attribute of the `Alter` command to *Session*.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2b928-151">Quando si utilizza l'impostazione della *sessione* , l' `ObjectDefinition` elemento può contenere solo elementi ASSL di [dimensione](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [cubo](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl)o [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) .</span><span class="sxs-lookup"><span data-stu-id="2b928-151">When using the *Session* setting, the `ObjectDefinition` element can only contain [Dimension](https://docs.microsoft.com/bi-reference/assl/objects/dimension-element-assl), [Cube](https://docs.microsoft.com/bi-reference/assl/objects/cube-element-assl), or [MiningModel](https://docs.microsoft.com/bi-reference/assl/objects/miningmodel-element-assl) ASSL elements.</span></span>  
  
## <a name="creating-or-altering-subordinate-objects"></a><span data-ttu-id="2b928-152">Creazione o modifica di oggetti subordinati</span><span class="sxs-lookup"><span data-stu-id="2b928-152">Creating or Altering Subordinate Objects</span></span>  
 <span data-ttu-id="2b928-153">Sebbene un comando `Create` o `Alter` crei o modifichi solo un oggetto principale di livello superiore, l'oggetto principale creato o modificato può includere nella proprietà `ObjectDefinition` che lo contiene definizioni per altri oggetti principali e secondari subordinati.</span><span class="sxs-lookup"><span data-stu-id="2b928-153">Although a `Create` or `Alter` command creates or alters only one topmost major object, the major object being created or modified can contain definitions within the enclosing `ObjectDefinition` property for other major and minor objects that are subordinate to it.</span></span> <span data-ttu-id="2b928-154">Se si definisce un cubo, ad esempio, si specifica innanzitutto il database padre in `ParentObject`, quindi nella definizione del cubo in `ObjectDefinition` è possibile definire gruppi di misure per il cubo e nei gruppi di misure è possibile definire partizioni per ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="2b928-154">For example, if you define a cube, you specify the parent database in `ParentObject`, and within the cube definition in `ObjectDefinition` you can define measure groups for the cube, and within the measure groups you can define partitions for each measure group.</span></span> <span data-ttu-id="2b928-155">Un oggetto secondario può essere definito solo sotto l'oggetto principale che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="2b928-155">A minor object can be defined only under the major object that contains it.</span></span> <span data-ttu-id="2b928-156">Per ulteriori informazioni sugli oggetti principali e secondari, vedere [oggetti di Database &#40;Analysis Services-&#41;di dati multidimensionali ](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="2b928-156">For more information about major and minor objects, see [Database Objects &#40;Analysis Services - Multidimensional Data&#41;](../multidimensional-models/olap-logical/database-objects-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2b928-157">Esempi</span><span class="sxs-lookup"><span data-stu-id="2b928-157">Examples</span></span>  
  
### <a name="description"></a><span data-ttu-id="2b928-158">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b928-158">Description</span></span>  
 <span data-ttu-id="2b928-159">Nell'esempio seguente viene creata un'origine dati relazionale che fa riferimento al [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] database di esempio [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b928-159">The following example creates a relational data source that references the [!INCLUDE[ssAWDWsp](../../includes/ssawdwsp-md.md)] sample [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2b928-160">Codice</span><span class="sxs-lookup"><span data-stu-id="2b928-160">Code</span></span>  
  
```  
<Create xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <ParentObject>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
    </ParentObject>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=localhost;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ImpersonationInfo>  
                <ImpersonationMode>ImpersonateServiceAccount</ImpersonationMode>  
            </ImpersonationInfo>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT0S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Create>  
```  
  
### <a name="description"></a><span data-ttu-id="2b928-161">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b928-161">Description</span></span>  
 <span data-ttu-id="2b928-162">Nell'esempio seguente viene modificata l'origine dati relazionale creata nell'esempio precedente per impostare il timeout per la query per l'origine dati su 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="2b928-162">The following example alters the relational data source created in the previous example to set the query time-out for the data source to 30 seconds.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2b928-163">Codice</span><span class="sxs-lookup"><span data-stu-id="2b928-163">Code</span></span>  
  
```  
<Alter ObjectExpansion="ObjectProperties" xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
    <Object>  
        <DatabaseID>Adventure Works DW Multidimensional 2012</DatabaseID>  
        <DataSourceID>AdventureWorksDW2012</DataSourceID>  
    </Object>  
    <ObjectDefinition>  
        <DataSource xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="RelationalDataSource">  
            <ID>AdventureWorksDW2012</ID>  
            <Name>AdventureWorksDW2012</Name>  
            <ConnectionString>Data Source=fr-dwk-02;Initial Catalog=AdventureWorksDW2008R2;Integrated Security=True</ConnectionString>  
            <ManagedProvider>System.Data.SqlClient</ManagedProvider>  
            <Timeout>PT30S</Timeout>  
        </DataSource>  
    </ObjectDefinition>  
</Alter>  
```  
  
### <a name="comments"></a><span data-ttu-id="2b928-164">Commenti</span><span class="sxs-lookup"><span data-stu-id="2b928-164">Comments</span></span>  
 <span data-ttu-id="2b928-165">L' `ObjectExpansion` attributo del `Alter` comando è stato impostato su *ObjectProperties*.</span><span class="sxs-lookup"><span data-stu-id="2b928-165">The `ObjectExpansion` attribute of the `Alter` command was set to *ObjectProperties*.</span></span> <span data-ttu-id="2b928-166">Questa impostazione consente di escludere l'elemento [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) , un oggetto secondario, dall'origine dati definita in `ObjectDefinition` .</span><span class="sxs-lookup"><span data-stu-id="2b928-166">This setting allows the [ImpersonationInfo](https://docs.microsoft.com/bi-reference/assl/properties/impersonationinfo-element-assl) element, a minor object, to be excluded from the data source defined in `ObjectDefinition`.</span></span> <span data-ttu-id="2b928-167">Le impostazioni di rappresentazione per tale origine dati rimangono pertanto configurate sull'account del servizio, come specificato nel primo esempio.</span><span class="sxs-lookup"><span data-stu-id="2b928-167">Therefore, the impersonation information for that data source remains set to the service account, as specified in the first example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b928-168">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b928-168">See Also</span></span>  
 <span data-ttu-id="2b928-169">[Metodo Execute &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span><span class="sxs-lookup"><span data-stu-id="2b928-169">[Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) </span></span>  
 <span data-ttu-id="2b928-170">[Sviluppo con Analysis Services linguaggio di scripting &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span><span class="sxs-lookup"><span data-stu-id="2b928-170">[Developing with Analysis Services Scripting Language &#40;ASSL&#41;](../multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md) </span></span>  
 [<span data-ttu-id="2b928-171">Sviluppo con XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2b928-171">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
