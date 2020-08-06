---
title: Codifica di tipi definiti dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- validation [CLR integration]
- UDTs [CLR integration], coding
- UserDefined serialization format [CLR integration]
- Point UDT
- Parse method
- null values [CLR integration]
- ToString method
- ValidatePoint method
- attributes [CLR integration]
- coding user-defined types [CLR integration]
- Read method
- Write method
- nullability [CLR integration]
- user-defined types [CLR integration], coding
- Currency UDT
- validating UDT values
- exposing UDT properties [CLR integration]
ms.assetid: 1e5b43b3-4971-45ee-a591-3f535e2ac722
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e88c4d8162e5c7c921f5c5062f5b3c23df40a2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625423"
---
# <a name="coding-user-defined-types"></a><span data-ttu-id="a9eda-102">Codifica dei tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="a9eda-102">Coding User-Defined Types</span></span>
  <span data-ttu-id="a9eda-103">Quando si codifica la definizione del tipo definito dall'utente (UDT), è necessario implementare varie caratteristiche a seconda che il tipo UDT venga implementato come classe o come struttura, nonché a seconda delle opzioni di formato e di serializzazione scelte.</span><span class="sxs-lookup"><span data-stu-id="a9eda-103">When coding your user-defined type (UDT) definition, you must implement various features, depending on whether you are implementing the UDT as a class or a structure, as well as on the format and serialization options you have chosen.</span></span>  
  
 <span data-ttu-id="a9eda-104">Nell'esempio contenuto in questa sezione viene illustrata l'implementazione di un tipo definito dall'utente `Point` come `struct` (o `Structure` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a9eda-104">The example in this section illustrates implementing a `Point` UDT as a `struct` (or `Structure` in Visual Basic).</span></span> <span data-ttu-id="a9eda-105">Il `Point` tipo definito dall'utente è costituito dalle coordinate X e Y implementate come routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="a9eda-105">The `Point` UDT consists of X and Y coordinates implemented as property procedures.</span></span>  
  
 <span data-ttu-id="a9eda-106">Quando si definisce un tipo definito dall'utente sono richiesti gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9eda-106">The following namespaces are required when defining a UDT:</span></span>  
  
```vb  
Imports System  
Imports System.Data.SqlTypes  
Imports Microsoft.SqlServer.Server  
```  
  
```csharp  
using System;  
using System.Data.SqlTypes;  
using Microsoft.SqlServer.Server;  
```  
  
 <span data-ttu-id="a9eda-107">Lo spazio dei nomi `Microsoft.SqlServer.Server` contiene gli oggetti richiesti per vari attributi del tipo definito dall'utente, mentre lo spazio dei nomi `System.Data.SqlTypes` contiene le classi che rappresentano i tipi di dati nativi di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] disponibili per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a9eda-107">The `Microsoft.SqlServer.Server` namespace contains the objects required for various attributes of your UDT, and the `System.Data.SqlTypes` namespace contains the classes that represent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types available to the assembly.</span></span> <span data-ttu-id="a9eda-108">Naturalmente, per il corretto funzionamento dell'assembly potrebbero essere necessari altri spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a9eda-108">There may of course be additional namespaces that your assembly requires in order to function correctly.</span></span> <span data-ttu-id="a9eda-109">Nel tipo definito dall'utente `Point` viene utilizzato anche lo spazio dei nomi `System.Text` per il supporto delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="a9eda-109">The `Point` UDT also uses the `System.Text` namespace for working with strings.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9eda-110">L'esecuzione degli oggetti di database Visual C++, ad esempio i tipi definiti dall'utente, compilati con `/clr:pure` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="a9eda-110">Visual C++ database objects, such as UDTs, compiled with `/clr:pure` are not supported for execution.</span></span>  
  
## <a name="specifying-attributes"></a><span data-ttu-id="a9eda-111">Specifica degli attributi</span><span class="sxs-lookup"><span data-stu-id="a9eda-111">Specifying Attributes</span></span>  
 <span data-ttu-id="a9eda-112">Gli attributi consentono di determinare la modalità di utilizzo della serializzazione per costruire la rappresentazione di archiviazione dei tipi definiti dall'utente e per trasmettere tali tipi al client in base al valore.</span><span class="sxs-lookup"><span data-stu-id="a9eda-112">Attributes determine how serialization is used to construct the storage representation of UDTs and to transmit UDTs by value to the client.</span></span>  
  
 <span data-ttu-id="a9eda-113">`Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a9eda-113">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` is required.</span></span> <span data-ttu-id="a9eda-114">L'attributo `Serializable` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a9eda-114">The `Serializable` attribute is optional.</span></span> <span data-ttu-id="a9eda-115">È anche possibile specificare `Microsoft.SqlServer.Server.SqlFacetAttribute` per fornire informazioni sul tipo restituito di un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-115">You can also specify the `Microsoft.SqlServer.Server.SqlFacetAttribute` to provide information about the return type of a UDT.</span></span> <span data-ttu-id="a9eda-116">Per altre informazioni, vedere [Attributi personalizzati per routine CLR](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span><span class="sxs-lookup"><span data-stu-id="a9eda-116">For more information, see [Custom Attributes for CLR Routines](../clr-integration/database-objects/clr-integration-custom-attributes-for-clr-routines.md).</span></span>  
  
### <a name="point-udt-attributes"></a><span data-ttu-id="a9eda-117">Attributi per il tipo definito dall'utente Point</span><span class="sxs-lookup"><span data-stu-id="a9eda-117">Point UDT Attributes</span></span>  
 <span data-ttu-id="a9eda-118">`Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` imposta il formato di archiviazione per il tipo definito dall'utente `Point` su `Native`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-118">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` sets the storage format for the `Point` UDT to `Native`.</span></span> <span data-ttu-id="a9eda-119">`IsByteOrdered` è impostato su `true` e ciò garantisce che i risultati dei confronti siano uguali in SQL Server, come se nel codice gestito fosse stato effettuato lo stesso confronto.</span><span class="sxs-lookup"><span data-stu-id="a9eda-119">`IsByteOrdered` is set to `true`, which guarantees that the results of comparisons are the same in SQL Server as if the same comparison had taken place in managed code.</span></span> <span data-ttu-id="a9eda-120">Il tipo definito dall'utente implementa l'interfaccia `System.Data.SqlTypes.INullable` che fornisce il supporto dei valori Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-120">The UDT implements the `System.Data.SqlTypes.INullable` interface to make the UDT null aware.</span></span>  
  
 <span data-ttu-id="a9eda-121">Nel frammento di codice seguente sono mostrati gli attributi per il tipo definito dall'utente `Point`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-121">The following code fragment shows the attributes for the `Point` UDT.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True)> _  
  Public Structure Point  
    Implements INullable  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true)]  
public struct Point : INullable  
{  
```  
  
## <a name="implementing-nullability"></a><span data-ttu-id="a9eda-122">Implementazione del supporto dei valori Null</span><span class="sxs-lookup"><span data-stu-id="a9eda-122">Implementing Nullability</span></span>  
 <span data-ttu-id="a9eda-123">Oltre a specificare gli attributi per gli assembly in modo corretto, il tipo definito dall'utente deve supportare anche i valori Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-123">In addition to specifying the attributes for your assemblies correctly, your UDT must also support nullability.</span></span> <span data-ttu-id="a9eda-124">I tipi definiti dall'utente caricati in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] includono il supporto dei valori Null, ma perché un tipo definito dall'utente possa riconoscere un valore Null, è necessario che implementi l'interfaccia `System.Data.SqlTypes.INullable`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-124">UDTs loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are null-aware, but in order for the UDT to recognize a null value, the UDT must implement the `System.Data.SqlTypes.INullable` interface.</span></span>  
  
 <span data-ttu-id="a9eda-125">Per determinare se un valore è Null dal codice CLR, è necessario creare una proprietà denominata `IsNull`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-125">You must create a property named `IsNull`, which is needed to determine whether a value is null from within CLR code.</span></span> <span data-ttu-id="a9eda-126">Quando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trova un'istanza Null di un tipo definito dall'utente, tale tipo viene reso persistente utilizzando i normali metodi di gestione dei valori Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finds a null instance of a UDT, the UDT is persisted using normal null-handling methods.</span></span> <span data-ttu-id="a9eda-127">Se non è necessario, nel server non viene eseguita la serializzazione o la deserializzazione del tipo definito dall'utente. Non viene inoltre occupato spazio per l'archiviazione di un tipo definito dall'utente Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-127">The server does not waste time serializing or deserializing the UDT if it does not have to, and it does not waste space to store a null UDT.</span></span> <span data-ttu-id="a9eda-128">La verifica della presenza di valori Null viene eseguita ogni volta che un tipo definito dall'utente viene importato da CLR. Questo significa che l'utilizzo del costrutto [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL per la verifica dei tipi definiti dall'utente Null dovrebbe funzionare sempre.</span><span class="sxs-lookup"><span data-stu-id="a9eda-128">This check for nulls is performed every time a UDT is brought over from the CLR, which means that using the [!INCLUDE[tsql](../../includes/tsql-md.md)] IS NULL construct to check for null UDTs should always work.</span></span> <span data-ttu-id="a9eda-129">La proprietà `IsNull` viene utilizzata anche dal server per verificare se un'istanza è Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-129">The `IsNull` property is also used by the server to test whether an instance is null.</span></span> <span data-ttu-id="a9eda-130">Una volta stabilito che il tipo definito dall'utente è Null, il server è in grado di utilizzare la relativa funzionalità di gestione nativa dei valori Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-130">Once the server determines that the UDT is null, it can use its native null handling.</span></span>  
  
 <span data-ttu-id="a9eda-131">Per il metodo `get()` di `IsNull` non viene utilizzata una combinazione di maiuscole/minuscole speciale.</span><span class="sxs-lookup"><span data-stu-id="a9eda-131">The `get()` method of `IsNull` is not special-cased in any way.</span></span> <span data-ttu-id="a9eda-132">Se una variabile `Point``@p` è `Null`, `@p.IsNull` restituirà, per impostazione predefinita, il valore "NULL" e non il valore "1"</span><span class="sxs-lookup"><span data-stu-id="a9eda-132">If a `Point` variable `@p` is `Null`, then `@p.IsNull` will, by default, evaluate to "NULL", not "1".</span></span> <span data-ttu-id="a9eda-133">perché l'attributo `SqlMethod(OnNullCall)` del metodo `IsNull get()` ha il valore predefinito false.</span><span class="sxs-lookup"><span data-stu-id="a9eda-133">This is because the `SqlMethod(OnNullCall)` attribute of the `IsNull get()` method defaults to false.</span></span> <span data-ttu-id="a9eda-134">Poiché l'oggetto è `Null`, quando la proprietà è richiesta l'oggetto non viene deserializzato, il metodo non viene chiamato e viene restituito il valore predefinito "NULL".</span><span class="sxs-lookup"><span data-stu-id="a9eda-134">Because the object is `Null`, when the property is requested the object is not deserialized, the method is not called, and a default value of "NULL" is returned.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a9eda-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9eda-135">Example</span></span>  
 <span data-ttu-id="a9eda-136">Nell'esempio seguente la variabile `is_Null` è privata e mantiene lo stato Null per l'istanza del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-136">In the following example, the `is_Null` variable is private and holds the state of null for the instance of the UDT.</span></span> <span data-ttu-id="a9eda-137">Il codice deve gestire un valore appropriato per `is_Null`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-137">Your code must maintain an appropriate value for `is_Null`.</span></span> <span data-ttu-id="a9eda-138">Il tipo definito dall'utente deve anche disporre di una proprietà statica denominata `Null` che restituisce un'istanza con valore Null del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-138">The UDT must also have a static property named `Null` that returns a null value instance of the UDT.</span></span> <span data-ttu-id="a9eda-139">In questo modo il tipo definito dall'utente può restituire un valore Null se l'istanza è Null nel database.</span><span class="sxs-lookup"><span data-stu-id="a9eda-139">This allows the UDT to return a null value if the instance is indeed null in the database.</span></span>  
  
```vb  
Private is_Null As Boolean  
  
Public ReadOnly Property IsNull() As Boolean _  
   Implements INullable.IsNull  
    Get  
        Return (is_Null)  
    End Get  
End Property  
  
Public Shared ReadOnly Property Null() As Point  
    Get  
        Dim pt As New Point  
        pt.is_Null = True  
        Return (pt)  
    End Get  
End Property  
```  
  
```csharp  
private bool is_Null;  
  
public bool IsNull  
{  
    get  
    {  
        return (is_Null);  
    }  
}  
  
public static Point Null  
{  
    get  
    {  
        Point pt = new Point();  
        pt.is_Null = true;  
        return pt;  
    }  
}  
```  
  
### <a name="is-null-vs-isnull"></a><span data-ttu-id="a9eda-140">Confronto tra IS NULL e IsNull</span><span class="sxs-lookup"><span data-stu-id="a9eda-140">IS NULL vs. IsNull</span></span>  
 <span data-ttu-id="a9eda-141">Si consideri una tabella contenente lo schema Points(id int, location Point), dove `Point` è un tipo CLR definito dall'utente, e le query seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9eda-141">Consider a table that contains the schema Points(id int, location Point), where `Point` is a CLR UDT, and the following queries:</span></span>  
  
```  
--Query 1  
SELECT ID  
FROM Points  
WHERE NOT (location IS NULL) -- Or, WHERE location IS NOT NULL;  
```  
  
```  
--Query 2:  
SELECT ID  
FROM Points  
WHERE location.IsNull = 0;  
```  
  
 <span data-ttu-id="a9eda-142">Entrambe le query restituiscono gli ID dei punti con posizioni non `Null`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-142">Both queries return the IDs of points with non-`Null` locations.</span></span> <span data-ttu-id="a9eda-143">Nella Query 1 viene utilizzata la normale gestione dei valori Null e non è necessaria la deserializzazione dei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-143">In Query 1, normal null-handling is used, and there no deserialization of UDTs is required.</span></span> <span data-ttu-id="a9eda-144">Nella Query 2, d'altra parte, è necessario deserializzare tutti gli oggetti non `Null` ed effettuare una chiamata in CLR per ottenere il valore della proprietà `IsNull`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-144">Query 2, on the other hand, has to deserialize each non-`Null` object and call into the CLR to obtain the value of the `IsNull` property.</span></span> <span data-ttu-id="a9eda-145">Chiaramente, `IS NULL` offrirà prestazioni migliori e pertanto non dovrebbe esistere alcun motivo per leggere la proprietà `IsNull` di un tipo definito dall'utente dal codice [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9eda-145">Clearly, using `IS NULL` will exhibit better performance and there should never be a reason to read the `IsNull` property of a UDT from [!INCLUDE[tsql](../../includes/tsql-md.md)] code.</span></span>  
  
 <span data-ttu-id="a9eda-146">L'utilizzo della proprietà `IsNull`</span><span class="sxs-lookup"><span data-stu-id="a9eda-146">So, what is the use of the `IsNull` property?</span></span> <span data-ttu-id="a9eda-147">è innanzitutto necessario per determinare se un valore è `Null` dal codice CLR.</span><span class="sxs-lookup"><span data-stu-id="a9eda-147">First, it is needed to determine whether a value is `Null` from within CLR code.</span></span> <span data-ttu-id="a9eda-148">In secondo luogo, questa proprietà viene utilizzata dal server per verificare se un'istanza è `Null`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-148">Second, the server needs a way to test whether an instance is `Null`, so this property is used by the server.</span></span> <span data-ttu-id="a9eda-149">Una volta stabilito che è `Null`, il server sarà in grado di utilizzare la relativa funzionalità di gestione nativa dei valori Null per gestirla.</span><span class="sxs-lookup"><span data-stu-id="a9eda-149">After it determines it is `Null`, then it can use its native null handling to handle it.</span></span>  
  
## <a name="implementing-the-parse-method"></a><span data-ttu-id="a9eda-150">Implementazione del metodo Parse</span><span class="sxs-lookup"><span data-stu-id="a9eda-150">Implementing the Parse Method</span></span>  
 <span data-ttu-id="a9eda-151">I metodi `Parse` e `ToString` consentono le conversioni da e verso le rappresentazioni di stringa del tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-151">The `Parse` and `ToString` methods allow for conversions to and from string representations of the UDT.</span></span> <span data-ttu-id="a9eda-152">Il metodo `Parse` consente la conversione di una stringa in un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-152">The `Parse` method allows a string to be converted into a UDT.</span></span> <span data-ttu-id="a9eda-153">Tale metodo deve essere dichiarato come `static` (o `Shared` in Visual Basic) e accetta un parametro di tipo `System.Data.SqlTypes.SqlString`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-153">It must be declared as `static` (or `Shared` in Visual Basic), and take a parameter of type `System.Data.SqlTypes.SqlString`.</span></span>  
  
 <span data-ttu-id="a9eda-154">Nel codice seguente viene implementato il metodo `Parse` per il tipo definito dall'utente `Point` che separa le coordinate X e Y.</span><span class="sxs-lookup"><span data-stu-id="a9eda-154">The following code implements the `Parse` method for the `Point` UDT, which separates out the X and Y coordinates.</span></span> <span data-ttu-id="a9eda-155">Il metodo `Parse` dispone di un solo argomento di tipo `System.Data.SqlTypes.SqlString` e presuppone che i valori X e Y vengano forniti come stringa delimitata da virgole.</span><span class="sxs-lookup"><span data-stu-id="a9eda-155">The `Parse` method has a single argument of type `System.Data.SqlTypes.SqlString`, and assumes that X and Y values are supplied as a comma-delimited string.</span></span> <span data-ttu-id="a9eda-156">L'impostazione dell'attributo `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` su `false` impedisce che il metodo `Parse` venga chiamato da un'istanza Null di Point.</span><span class="sxs-lookup"><span data-stu-id="a9eda-156">Setting the `Microsoft.SqlServer.Server.SqlMethodAttribute.OnNullCall` attribute to `false` prevents the `Parse` method from being called from a null instance of Point.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
    return pt;  
}  
```  
  
## <a name="implementing-the-tostring-method"></a><span data-ttu-id="a9eda-157">Implementazione del metodo ToString</span><span class="sxs-lookup"><span data-stu-id="a9eda-157">Implementing the ToString Method</span></span>  
 <span data-ttu-id="a9eda-158">Il metodo `ToString` converte il tipo definito dall'utente `Point` in un valore stringa.</span><span class="sxs-lookup"><span data-stu-id="a9eda-158">The `ToString` method converts the `Point` UDT to a string value.</span></span> <span data-ttu-id="a9eda-159">In questo caso, viene restituita la stringa "NULL" per un'istanza Null del tipo `Point`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-159">In this case, the string "NULL" is returned for a Null instance of the `Point` type.</span></span> <span data-ttu-id="a9eda-160">Il metodo `ToString` inverte il metodo `Parse` utilizzando un `System.Text.StringBuilder` per restituire un oggetto `System.String` delimitato da virgole costituito dai valori delle coordinate X e Y.</span><span class="sxs-lookup"><span data-stu-id="a9eda-160">The `ToString` method reverses the `Parse` method by using a `System.Text.StringBuilder` to return a comma-delimited `System.String` consisting of the X and Y coordinate values.</span></span> <span data-ttu-id="a9eda-161">Poiché il valore predefinito di **InvokeIfReceiverIsNull** è false, il controllo della presenza di un'istanza null di non `Point` è necessario.</span><span class="sxs-lookup"><span data-stu-id="a9eda-161">Because **InvokeIfReceiverIsNull** defaults to false, the check for a null instance of `Point` is unnecessary.</span></span>  
  
```vb  
Private _x As Int32  
Private _y As Int32  
  
Public Overrides Function ToString() As String  
    If Me.IsNull Then  
        Return "NULL"  
    Else  
        Dim builder As StringBuilder = New StringBuilder  
        builder.Append(_x)  
        builder.Append(",")  
        builder.Append(_y)  
        Return builder.ToString  
    End If  
End Function  
```  
  
```csharp  
private Int32 _x;  
private Int32 _y;  
  
public override string ToString()  
{  
    if (this.IsNull)  
        return "NULL";  
    else  
    {  
        StringBuilder builder = new StringBuilder();  
        builder.Append(_x);  
        builder.Append(",");  
        builder.Append(_y);  
        return builder.ToString();  
    }  
}  
```  
  
## <a name="exposing-udt-properties"></a><span data-ttu-id="a9eda-162">Esposizione delle proprietà dei tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="a9eda-162">Exposing UDT Properties</span></span>  
 <span data-ttu-id="a9eda-163">Il tipo definito dall'utente `Point` espone le coordinate X e Y implementate come proprietà pubbliche di lettura e scrittura di tipo `System.Int32`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-163">The `Point` UDT exposes X and Y coordinates that are implemented as public read-write properties of type `System.Int32`.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _x = Value  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        _y = Value  
    End Set  
End Property  
```  
  
```csharp  
public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    set   
    {  
        _x = value;  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        _y = value;  
    }  
}  
```  
  
## <a name="validating-udt-values"></a><span data-ttu-id="a9eda-164">Convalida dei valori dei tipi definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="a9eda-164">Validating UDT Values</span></span>  
 <span data-ttu-id="a9eda-165">Quando si utilizzano i dati dei tipi definiti dall'utente, il [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] converte automaticamente i valori binari in valori dei tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-165">When working with UDT data, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] automatically converts binary values to UDT values.</span></span> <span data-ttu-id="a9eda-166">Ai fini di tale processo di conversione, viene verificato che i valori siano appropriati al formato di serializzazione del tipo e che il valore possa essere deserializzato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-166">This conversion process involves checking that values are appropriate for the serialization format of the type and ensuring that the value can be deserialized correctly.</span></span> <span data-ttu-id="a9eda-167">In questo modo si garantisce che il valore possa essere convertito di nuovo in formato binario.</span><span class="sxs-lookup"><span data-stu-id="a9eda-167">This ensures that the value can be converted back to binary form.</span></span> <span data-ttu-id="a9eda-168">Nel caso dei tipi definiti dall'utente ordinati per byte, questo processo assicura anche che il valore binario risultante corrisponda al valore binario originale.</span><span class="sxs-lookup"><span data-stu-id="a9eda-168">In the case of byte-ordered UDTs, this also ensures that the resulting binary value matches the original binary value.</span></span> <span data-ttu-id="a9eda-169">In questo modo si impedisce che valori non validi vengano resi persistenti nel database.</span><span class="sxs-lookup"><span data-stu-id="a9eda-169">This prevents invalid values from being persisted in the database.</span></span> <span data-ttu-id="a9eda-170">In alcuni casi, questo livello di controllo può risultare inadeguato.</span><span class="sxs-lookup"><span data-stu-id="a9eda-170">In some cases, this level of checking may be inadequate.</span></span> <span data-ttu-id="a9eda-171">Una convalida aggiuntiva può essere necessaria quando è necessario che i valori dei tipi definiti dall'utente si trovino in un dominio o in un intervallo previsto.</span><span class="sxs-lookup"><span data-stu-id="a9eda-171">Additional validation may be required when UDT values are required to be in an expected domain or range.</span></span> <span data-ttu-id="a9eda-172">Un tipo definito dall'utente che implementa, ad esempio, una data potrebbe richiedere che il valore del giorno sia un numero positivo compreso in un determinato intervallo di valori validi.</span><span class="sxs-lookup"><span data-stu-id="a9eda-172">For example, a UDT that implements a date might require the day value to be a positive number that falls within a certain range of valid values.</span></span>  
  
 <span data-ttu-id="a9eda-173">La proprietà `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` di `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` consente all'utente di fornire il nome di un metodo di convalida che il server esegue quando i dati sono assegnati a un tipo definito dall'utente o convertiti in un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-173">The `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute.ValidationMethodName` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute` allows you to supply the name of a validation method that the server runs when data is assigned to a UDT or converted to a UDT.</span></span> <span data-ttu-id="a9eda-174">`ValidationMethodName` viene chiamato anche durante l'esecuzione dell'utilità bcp, BULK INSERT, DBCC CHECKDB, CHECKFILEGROUP DBCC, CHECKTABLE DBCC, query distribuita e operazioni della chiamata RPC (Remote Procedure Call) (RPC) di flusso TDS (tabular data stream).</span><span class="sxs-lookup"><span data-stu-id="a9eda-174">`ValidationMethodName` is also called during the running of the bcp utility, BULK INSERT, DBCC CHECKDB, DBCC CHECKFILEGROUP, DBCC CHECKTABLE, distributed query, and tabular data stream (TDS) remote procedure call (RPC) operations.</span></span> <span data-ttu-id="a9eda-175">Il valore predefinito per `ValidationMethodName` è Null e indica che non è stato specificato alcun metodo di convalida.</span><span class="sxs-lookup"><span data-stu-id="a9eda-175">The default value for `ValidationMethodName` is null, indicating that there is no validation method.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a9eda-176">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9eda-176">Example</span></span>  
 <span data-ttu-id="a9eda-177">Nel frammento di codice seguente è riportata la dichiarazione per la classe `Point` che specifica `ValidationMethodName` di `ValidatePoint`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-177">The following code fragment shows the declaration for the `Point` class, which specifies a `ValidationMethodName` of `ValidatePoint`.</span></span>  
  
```vb  
<Serializable(), SqlUserDefinedTypeAttribute(Format.Native, _  
  IsByteOrdered:=True, _  
  ValidationMethodName:="ValidatePoint")> _  
  Public Structure Point  
```  
  
```csharp  
[Serializable]  
[Microsoft.SqlServer.Server.SqlUserDefinedType(Format.Native,  
  IsByteOrdered=true,   
  ValidationMethodName = "ValidatePoint")]  
public struct Point : INullable  
{  
```  
  
 <span data-ttu-id="a9eda-178">Se si specifica un metodo di convalida, è necessario che includa una firma simile al frammento di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a9eda-178">If a validation method is specified, it must have a signature that looks like the following code fragment.</span></span>  
  
```vb  
Private Function ValidationFunction() As Boolean  
    If (validation logic here) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidationFunction()  
{  
    if (validation logic here)  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
 <span data-ttu-id="a9eda-179">Il metodo di convalida può disporre di qualsiasi ambito e deve restituire `true` se il valore è valido e `false` in caso contrario.</span><span class="sxs-lookup"><span data-stu-id="a9eda-179">The validation method can have any scope and should return `true` if the value is valid, and `false` otherwise.</span></span> <span data-ttu-id="a9eda-180">Se il metodo restituisce `false` o genera un'eccezione, il valore viene considerato non valido e viene generato un errore.</span><span class="sxs-lookup"><span data-stu-id="a9eda-180">If the method returns `false` or throws an exception, the value is treated as not valid and an error is raised.</span></span>  
  
 <span data-ttu-id="a9eda-181">Nell'esempio riportato di seguito il codice accetta solo valori pari a zero o superiori per le coordinate X e Y.</span><span class="sxs-lookup"><span data-stu-id="a9eda-181">In the example below, the code allows only values of zero or greater the X and Y coordinates.</span></span>  
  
```vb  
Private Function ValidatePoint() As Boolean  
    If (_x >= 0) And (_y >= 0) Then  
        Return True  
    Else  
        Return False  
    End If  
End Function  
```  
  
```csharp  
private bool ValidatePoint()  
{  
    if ((_x >= 0) && (_y >= 0))  
    {  
        return true;  
    }  
    else  
    {  
        return false;  
    }  
}  
```  
  
### <a name="validation-method-limitations"></a><span data-ttu-id="a9eda-182">Limitazioni del metodo di convalida</span><span class="sxs-lookup"><span data-stu-id="a9eda-182">Validation Method Limitations</span></span>  
 <span data-ttu-id="a9eda-183">Il server chiama il metodo di convalida durante l'esecuzione delle conversioni e non quando i dati vengono inseriti impostando singole proprietà o utilizzando un'istruzione INSERT [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9eda-183">The server calls the validation method when the server is performing conversions, not when data is inserted by setting individual properties or when data is inserted using a [!INCLUDE[tsql](../../includes/tsql-md.md)] INSERT statement.</span></span>  
  
 <span data-ttu-id="a9eda-184">È necessario chiamare in modo esplicito il metodo di convalida dai setter di proprietà e il `Parse` metodo se si desidera che il metodo di convalida venga eseguito in tutte le situazioni.</span><span class="sxs-lookup"><span data-stu-id="a9eda-184">You must explicitly call the validation method from property setters and the `Parse` method if you want the validation method to execute in all situations.</span></span> <span data-ttu-id="a9eda-185">Questa operazione non è obbligatoria e in alcuni casi può essere anche sconsigliata.</span><span class="sxs-lookup"><span data-stu-id="a9eda-185">This is not a requirement, and in some cases may not even be desirable.</span></span>  
  
### <a name="parse-validation-example"></a><span data-ttu-id="a9eda-186">Esempio di convalida del metodo Parse</span><span class="sxs-lookup"><span data-stu-id="a9eda-186">Parse Validation Example</span></span>  
 <span data-ttu-id="a9eda-187">Per assicurarsi che il `ValidatePoint` metodo venga richiamato nella `Point` classe, è necessario chiamarlo dal `Parse` metodo e dalle routine di proprietà che impostano i valori delle coordinate X e Y.</span><span class="sxs-lookup"><span data-stu-id="a9eda-187">To ensure that the `ValidatePoint` method is invoked in the `Point` class, you must call it from the `Parse` method and from the property procedures that set the X and Y coordinate values.</span></span> <span data-ttu-id="a9eda-188">Nel frammento di codice seguente viene illustrato come chiamare il `ValidatePoint` metodo di convalida dalla `Parse` funzione.</span><span class="sxs-lookup"><span data-stu-id="a9eda-188">The following code fragment shows how to call the `ValidatePoint` validation method from the `Parse` function.</span></span>  
  
```vb  
<SqlMethod(OnNullCall:=False)> _  
Public Shared Function Parse(ByVal s As SqlString) As Point  
    If s.IsNull Then  
        Return Null  
    End If  
  
    ' Parse input string here to separate out points.  
    Dim pt As New Point()  
    Dim xy() As String = s.Value.Split(",".ToCharArray())  
    pt.X = Int32.Parse(xy(0))  
    pt.Y = Int32.Parse(xy(1))  
  
    ' Call ValidatePoint to enforce validation  
    ' for string conversions.  
    If Not pt.ValidatePoint() Then  
        Throw New ArgumentException("Invalid XY coordinate values.")  
    End If  
    Return pt  
End Function  
```  
  
```csharp  
[SqlMethod(OnNullCall = false)]  
public static Point Parse(SqlString s)  
{  
    if (s.IsNull)  
        return Null;  
  
    // Parse input string to separate out points.  
    Point pt = new Point();  
    string[] xy = s.Value.Split(",".ToCharArray());  
    pt.X = Int32.Parse(xy[0]);  
    pt.Y = Int32.Parse(xy[1]);  
  
    // Call ValidatePoint to enforce validation  
    // for string conversions.  
    if (!pt.ValidatePoint())   
        throw new ArgumentException("Invalid XY coordinate values.");  
    return pt;  
}  
```  
  
### <a name="property-validation-example"></a><span data-ttu-id="a9eda-189">Esempio di convalida delle proprietà</span><span class="sxs-lookup"><span data-stu-id="a9eda-189">Property Validation Example</span></span>  
 <span data-ttu-id="a9eda-190">Nel frammento di codice seguente viene illustrato come chiamare il `ValidatePoint` metodo di convalida dalle routine di proprietà che impostano le coordinate X e Y.</span><span class="sxs-lookup"><span data-stu-id="a9eda-190">The following code fragment shows how to call the `ValidatePoint` validation method from the property procedures that set the X and Y coordinates.</span></span>  
  
```vb  
Public Property X() As Int32  
    Get  
        Return (Me._x)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _x  
        _x = Value  
        If Not ValidatePoint() Then  
            _x = temp  
            Throw New ArgumentException("Invalid X coordinate value.")  
        End If  
    End Set  
End Property  
  
Public Property Y() As Int32  
    Get  
        Return (Me._y)  
    End Get  
  
    Set(ByVal Value As Int32)  
        Dim temp As Int32 = _y  
        _y = Value  
        If Not ValidatePoint() Then  
            _y = temp  
            Throw New ArgumentException("Invalid Y coordinate value.")  
        End If  
    End Set  
End Property  
```  
  
```csharp  
    public Int32 X  
{  
    get  
    {  
        return this._x;  
    }  
    // Call ValidatePoint to ensure valid range of Point values.  
    set   
    {  
        Int32 temp = _x;  
        _x = value;  
        if (!ValidatePoint())  
        {  
            _x = temp;  
            throw new ArgumentException("Invalid X coordinate value.");  
        }  
    }  
}  
  
public Int32 Y  
{  
    get  
    {  
        return this._y;  
    }  
    set  
    {  
        Int32 temp = _y;  
        _y = value;  
        if (!ValidatePoint())  
        {  
            _y = temp;  
            throw new ArgumentException("Invalid Y coordinate value.");  
        }  
    }  
}  
```  
  
## <a name="coding-udt-methods"></a><span data-ttu-id="a9eda-191">Codifica dei metodi UDT</span><span class="sxs-lookup"><span data-stu-id="a9eda-191">Coding UDT Methods</span></span>  
 <span data-ttu-id="a9eda-192">Quando si codificano i metodi UDT, è consigliabile valutare la possibilità che l'algoritmo utilizzato possa cambiare nel tempo.</span><span class="sxs-lookup"><span data-stu-id="a9eda-192">When coding UDT methods, consider whether the algorithm used could possibly change over time.</span></span> <span data-ttu-id="a9eda-193">In questo caso è possibile creare una classe separata per i metodi utilizzati dal tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-193">If so, you may want to consider creating a separate class for the methods your UDT uses.</span></span> <span data-ttu-id="a9eda-194">Se l'algoritmo cambia, è possibile ricompilare la classe con il nuovo codice e caricare l'assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] senza influire sul tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-194">If the algorithm changes, you can recompile the class with the new code and load the assembly into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without affecting the UDT.</span></span> <span data-ttu-id="a9eda-195">In molti casi i tipi definiti dall'utente possono essere ricaricati utilizzando l'istruzione ALTER ASSEMBLY [!INCLUDE[tsql](../../includes/tsql-md.md)], anche se tale operazione potrebbe provocare problemi con i dati esistenti.</span><span class="sxs-lookup"><span data-stu-id="a9eda-195">In many cases UDTs can be reloaded using the [!INCLUDE[tsql](../../includes/tsql-md.md)] ALTER ASSEMBLY statement, but that could potentially cause problems with existing data.</span></span> <span data-ttu-id="a9eda-196">Il `Currency` tipo definito dall'utente incluso nel database di esempio **AdventureWorks** , ad esempio, utilizza una funzione **ConvertCurrency** per convertire i valori di valuta, implementati in una classe separata.</span><span class="sxs-lookup"><span data-stu-id="a9eda-196">For example, the `Currency` UDT included with the **AdventureWorks** sample database uses a **ConvertCurrency** function to convert currency values, which is implemented in a separate class.</span></span> <span data-ttu-id="a9eda-197">È possibile che gli algoritmi di conversione cambino nel tempo in modo imprevedibile o che venga richiesta una nuova funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a9eda-197">It is possible that conversion algorithms may change in unpredictable ways in the future, or that new functionality may be required.</span></span> <span data-ttu-id="a9eda-198">La separazione della funzione **ConvertCurrency** dall' `Currency` implementazione del tipo definito dall'utente garantisce una maggiore flessibilità durante la pianificazione di modifiche future.</span><span class="sxs-lookup"><span data-stu-id="a9eda-198">Separating the **ConvertCurrency** function from the `Currency` UDT implementation provides greater flexibility when planning for future changes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a9eda-199">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9eda-199">Example</span></span>  
 <span data-ttu-id="a9eda-200">La `Point` classe contiene tre semplici metodi per il calcolo della distanza, ovvero **distance**, **DistanceFrom** e **DistanceFromXY**.</span><span class="sxs-lookup"><span data-stu-id="a9eda-200">The `Point` class contains three simple methods for calculating distance: **Distance**, **DistanceFrom** and **DistanceFromXY**.</span></span> <span data-ttu-id="a9eda-201">Ognuno di essi restituisce un valore `double` che calcola la distanza da `Point` a zero, la distanza da un punto specificato a `Point` e la distanza dalle coordinate X e Y specificate a `Point`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-201">Each returns a `double` calculating the distance from `Point` to zero, the distance from a specified point to `Point`, and the distance from specified X and Y coordinates to `Point`.</span></span> <span data-ttu-id="a9eda-202">**Distance** e **DistanceFrom** ogni chiamata **DistanceFromXY**e illustrano come usare argomenti diversi per ogni metodo.</span><span class="sxs-lookup"><span data-stu-id="a9eda-202">**Distance** and **DistanceFrom** each call **DistanceFromXY**, and demonstrate how to use different arguments for each method.</span></span>  
  
```vb  
' Distance from 0 to Point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function Distance() As Double  
    Return DistanceFromXY(0, 0)  
End Function  
  
' Distance from Point to the specified point.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFrom(ByVal pFrom As Point) As Double  
    Return DistanceFromXY(pFrom.X, pFrom.Y)  
End Function  
  
' Distance from Point to the specified x and y values.  
<SqlMethod(OnNullCall:=False)> _  
Public Function DistanceFromXY(ByVal ix As Int32, ByVal iy As Int32) _  
    As Double  
    Return Math.Sqrt(Math.Pow(ix - _x, 2.0) + Math.Pow(iy - _y, 2.0))  
End Function  
```  
  
```csharp  
// Distance from 0 to Point.  
[SqlMethod(OnNullCall = false)]  
public Double Distance()  
{  
    return DistanceFromXY(0, 0);  
}  
  
// Distance from Point to the specified point.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFrom(Point pFrom)  
{  
    return DistanceFromXY(pFrom.X, pFrom.Y);  
}  
  
// Distance from Point to the specified x and y values.  
[SqlMethod(OnNullCall = false)]  
public Double DistanceFromXY(Int32 iX, Int32 iY)  
{  
    return Math.Sqrt(Math.Pow(iX - _x, 2.0) + Math.Pow(iY - _y, 2.0));  
}  
```  
  
### <a name="using-sqlmethod-attributes"></a><span data-ttu-id="a9eda-203">Utilizzo degli attributi SqlMethod</span><span class="sxs-lookup"><span data-stu-id="a9eda-203">Using SqlMethod Attributes</span></span>  
 <span data-ttu-id="a9eda-204">La classe `Microsoft.SqlServer.Server.SqlMethodAttribute` fornisce attributi personalizzati che possono essere utilizzati per contrassegnare le definizioni di metodo allo scopo di specificare il determinismo, il comportamento in caso di chiamate Null e per indicare se un metodo è di tipo mutatore.</span><span class="sxs-lookup"><span data-stu-id="a9eda-204">The `Microsoft.SqlServer.Server.SqlMethodAttribute` class provides custom attributes that can be used to mark method definitions in order to specify determinism, on null call behavior, and to specify whether a method is a mutator.</span></span> <span data-ttu-id="a9eda-205">Per queste proprietà si presuppone l'uso dei valori predefiniti e l'attributo personalizzato viene utilizzato solo quando è necessario un valore non predefinito.</span><span class="sxs-lookup"><span data-stu-id="a9eda-205">Default values for these properties are assumed, and the custom attribute is only used when a non-default value is needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9eda-206">La classe `SqlMethodAttribute` eredita dalla classe `SqlFunctionAttribute` e pertanto `SqlMethodAttribute` eredita i campi `FillRowMethodName` e `TableDefinition` da `SqlFunctionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-206">The `SqlMethodAttribute` class inherits from the `SqlFunctionAttribute` class, so `SqlMethodAttribute` inherits the `FillRowMethodName` and `TableDefinition` fields from `SqlFunctionAttribute`.</span></span> <span data-ttu-id="a9eda-207">Questo implica, contrariamente al vero, la possibilità di scrivere un metodo con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="a9eda-207">This implies that it is possible to write a table-valued method, which is not the case.</span></span> <span data-ttu-id="a9eda-208">Il metodo viene compilato e l'assembly viene distribuito, ma un errore relativo al `IEnumerable` tipo restituito viene generato in fase di esecuzione con il messaggio seguente: "il metodo, la proprietà o il campo ' \<name> ' nella classe ' \<class> ' nell'assembly ' \<assembly> ' ha un tipo restituito non valido."</span><span class="sxs-lookup"><span data-stu-id="a9eda-208">The method compiles and the assembly deploys, but an error about the `IEnumerable` return type is raised at runtime with the following message: "Method, property, or field '\<name>' in class '\<class>' in assembly '\<assembly>' has invalid return type."</span></span>  
  
 <span data-ttu-id="a9eda-209">Nella tabella seguente sono descritte alcune delle proprietà `Microsoft.SqlServer.Server.SqlMethodAttribute` rilevanti che possono essere utilizzate nei metodi UDT con i relativi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a9eda-209">The following table describes some of the relevant `Microsoft.SqlServer.Server.SqlMethodAttribute` properties that can be used in UDT methods, and lists their default values.</span></span>  
  
 <span data-ttu-id="a9eda-210">DataAccess</span><span class="sxs-lookup"><span data-stu-id="a9eda-210">DataAccess</span></span>  
 <span data-ttu-id="a9eda-211">Indica se la funzione comporta l'accesso ai dati dell'utente archiviati nell'istanza locale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9eda-211">Indicates whether the function involves access to user data stored in the local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a9eda-212">Il valore predefinito è `DataAccessKind``None`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-212">Default is `DataAccessKind`.`None`.</span></span>  
  
 <span data-ttu-id="a9eda-213">IsDeterministic</span><span class="sxs-lookup"><span data-stu-id="a9eda-213">IsDeterministic</span></span>  
 <span data-ttu-id="a9eda-214">Indica se la funzione produce gli stessi valori di output quando vengono specificati gli stessi valori di input e lo stesso stato del database.</span><span class="sxs-lookup"><span data-stu-id="a9eda-214">Indicates whether the function produces the same output values given the same input values and the same database state.</span></span> <span data-ttu-id="a9eda-215">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-215">Default is `false`.</span></span>  
  
 <span data-ttu-id="a9eda-216">IsMutator</span><span class="sxs-lookup"><span data-stu-id="a9eda-216">IsMutator</span></span>  
 <span data-ttu-id="a9eda-217">Indica se il metodo causa una modifica dello stato dell'istanza UDT.</span><span class="sxs-lookup"><span data-stu-id="a9eda-217">Indicates whether the method causes a state change in the UDT instance.</span></span> <span data-ttu-id="a9eda-218">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-218">Default is `false`.</span></span>  
  
 <span data-ttu-id="a9eda-219">IsPrecise</span><span class="sxs-lookup"><span data-stu-id="a9eda-219">IsPrecise</span></span>  
 <span data-ttu-id="a9eda-220">Indica se la funzione comporta calcoli imprecisi, quali operazioni a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="a9eda-220">Indicates whether the function involves imprecise computations, such as floating point operations.</span></span> <span data-ttu-id="a9eda-221">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-221">Default is `false`.</span></span>  
  
 <span data-ttu-id="a9eda-222">OnNullCall</span><span class="sxs-lookup"><span data-stu-id="a9eda-222">OnNullCall</span></span>  
 <span data-ttu-id="a9eda-223">Indica se il metodo viene chiamato quando vengono specificati argomenti di input con riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-223">Indicates whether the method is called when null reference input arguments are specified.</span></span> <span data-ttu-id="a9eda-224">Il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-224">Default is `true`.</span></span>  
  
### <a name="example"></a><span data-ttu-id="a9eda-225">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9eda-225">Example</span></span>  
 <span data-ttu-id="a9eda-226">La proprietà `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` consente all'utente di contrassegnare un metodo che consente una modifica nello stato di un'istanza di un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-226">The `Microsoft.SqlServer.Server.SqlMethodAttribute.IsMutator` property allows you to mark a method that allows a change in the state of an instance of a UDT.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="a9eda-227">non consente all'utente di impostare due proprietà del tipo definito dall'utente nella clausola SET di un'istruzione UPDATE.</span><span class="sxs-lookup"><span data-stu-id="a9eda-227">does not allow you to set two UDT properties in the SET clause of one UPDATE statement.</span></span> <span data-ttu-id="a9eda-228">È tuttavia possibile contrassegnare un metodo come mutatore che modifica i due membri.</span><span class="sxs-lookup"><span data-stu-id="a9eda-228">However, you can have a method marked as a mutator that changes the two members.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a9eda-229">Nelle query non è consentito l'uso di metodi di tipo mutatore.</span><span class="sxs-lookup"><span data-stu-id="a9eda-229">Mutator methods are not allowed in queries.</span></span> <span data-ttu-id="a9eda-230">Tali metodi possono essere chiamati solo nelle istruzioni di assegnazione o nelle istruzioni di modifica dei dati.</span><span class="sxs-lookup"><span data-stu-id="a9eda-230">They can be called only in assignment statements or data modification statements.</span></span> <span data-ttu-id="a9eda-231">Se un metodo contrassegnato come mutatore non restituisce `void` (o non è un `Sub` in Visual Basic), l'istruzione CREATE TYPE ha esito negativo e restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="a9eda-231">If a method marked as mutator does not return `void` (or is not a `Sub` in Visual Basic), CREATE TYPE fails with an error.</span></span>  
  
 <span data-ttu-id="a9eda-232">Nell'istruzione seguente si presuppone l'esistenza di un tipo definito dall'utente `Triangles` con un metodo `Rotate`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-232">The following statement assumes the existence of a `Triangles` UDT that has a `Rotate` method.</span></span> <span data-ttu-id="a9eda-233">Nell'istruzione di aggiornamento [!INCLUDE[tsql](../../includes/tsql-md.md)] seguente viene richiamato il metodo `Rotate`:</span><span class="sxs-lookup"><span data-stu-id="a9eda-233">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] update statement invokes the `Rotate` method:</span></span>  
  
```  
UPDATE Triangles SET t.RotateY(0.6) WHERE id=5  
```  
  
 <span data-ttu-id="a9eda-234">Il metodo `Rotate` è decorato con l'impostazione dell'attributo `SqlMethod``IsMutator` su `true` in modo che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possa contrassegnare il metodo come metodo mutatore.</span><span class="sxs-lookup"><span data-stu-id="a9eda-234">The `Rotate` method is decorated with the `SqlMethod` attribute setting `IsMutator` to `true` so that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can mark the method as a mutator method.</span></span> <span data-ttu-id="a9eda-235">Il codice imposta anche `OnNullCall` su `false` che indica al server che il metodo restituisce un riferimento Null (`Nothing` in Visual Basic) se uno dei parametri di input è un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-235">The code also sets `OnNullCall` to `false`, which indicates to the server that the method returns a null reference (`Nothing` in Visual Basic) if any of the input parameters are null references.</span></span>  
  
```vb  
<SqlMethod(IsMutator:=True, OnNullCall:=False)> _  
Public Sub Rotate(ByVal anglex as Double, _  
  ByVal angley as Double, ByVal anglez As Double)   
   RotateX(anglex)  
   RotateY(angley)  
   RotateZ(anglez)  
End Sub  
```  
  
```csharp  
[SqlMethod(IsMutator = true, OnNullCall = false)]  
public void Rotate(double anglex, double angley, double anglez)   
{  
   RotateX(anglex);  
   RotateY(angley);  
   RotateZ(anglez);  
}  
```  
  
## <a name="implementing-a-udt-with-a-user-defined-format"></a><span data-ttu-id="a9eda-236">Implementazione di un tipo definito dall'utente con un formato definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="a9eda-236">Implementing a UDT with a User-Defined Format</span></span>  
 <span data-ttu-id="a9eda-237">Quando si implementa un tipo definito dall'utente con un formato definito dall'utente, è necessario implementare i metodi `Read` e `Write` che implementano l'interfaccia Microsoft.SqlServer.Server.IBinarySerialize per gestire la serializzazione e la deserializzazione dei dati UDT.</span><span class="sxs-lookup"><span data-stu-id="a9eda-237">When implementing a UDT with a user-defined format, you must implement `Read` and `Write` methods that implement the Microsoft.SqlServer.Server.IBinarySerialize interface to handle serializing and deserializing UDT data.</span></span> <span data-ttu-id="a9eda-238">È inoltre necessario specificare la proprietà `MaxByteSize` di `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-238">You must also specify the `MaxByteSize` property of the `Microsoft.SqlServer.Server.SqlUserDefinedTypeAttribute`.</span></span>  
  
### <a name="the-currency-udt"></a><span data-ttu-id="a9eda-239">Tipo definito dall'utente Currency</span><span class="sxs-lookup"><span data-stu-id="a9eda-239">The Currency UDT</span></span>  
 <span data-ttu-id="a9eda-240">Il tipo definito dall'utente (UDT) `Currency` è incluso negli esempi CLR che possono essere installati con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9eda-240">The `Currency` UDT is included with the CLR samples that can be installed with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="a9eda-241">Il tipo definito dall'utente (UDT) `Currency` supporta la gestione degli importi nel sistema monetario di specifiche impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a9eda-241">The `Currency` UDT supports handling amounts of money in the monetary system of a particular culture.</span></span> <span data-ttu-id="a9eda-242">È necessario definire due campi, ovvero un campo `string` per l'oggetto `CultureInfo` che specifica il paese che ha emesso la valuta, ad esempio it-it, e un campo `decimal` per l'oggetto `CurrencyValue` che indica l'importo.</span><span class="sxs-lookup"><span data-stu-id="a9eda-242">You must define two fields: a `string` for `CultureInfo`, which specifies who issued the currency (en-us, for example) and a `decimal` for `CurrencyValue`, the amount of money.</span></span>  
  
 <span data-ttu-id="a9eda-243">Anche se non utilizzato dal server per i confronti, il tipo definito dall'utente `Currency` implementa l'interfaccia `System.IComparable` che espone un singolo metodo, `System.IComparable.CompareTo`.</span><span class="sxs-lookup"><span data-stu-id="a9eda-243">Although it is not used by the server for performing comparisons, the `Currency` UDT implements the `System.IComparable` interface, which exposes a single method, `System.IComparable.CompareTo`.</span></span> <span data-ttu-id="a9eda-244">Tale metodo viene utilizzato sul lato client nelle situazioni in cui è consigliabile confrontare o ordinare i valori relativi alla valuta in modo accurato all'interno delle diverse impostazioni cultura.</span><span class="sxs-lookup"><span data-stu-id="a9eda-244">This is used on the client side in situations where it is desirable to accurately compare or order currency values within cultures.</span></span>  
  
 <span data-ttu-id="a9eda-245">Il codice eseguito in CLR confronta le impostazioni cultura separatamente dal valore della valuta.</span><span class="sxs-lookup"><span data-stu-id="a9eda-245">Code running in the CLR compares the culture separately from the currency value.</span></span> <span data-ttu-id="a9eda-246">Per il codice [!INCLUDE[tsql](../../includes/tsql-md.md)], il confronto viene determinato dalle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9eda-246">For [!INCLUDE[tsql](../../includes/tsql-md.md)] code, the following actions determine the comparison:</span></span>  
  
1.  <span data-ttu-id="a9eda-247">Impostare l'attributo `IsByteOrdered` su True per indicare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di utilizzare la rappresentazione binaria persistente su disco per i confronti.</span><span class="sxs-lookup"><span data-stu-id="a9eda-247">Set the `IsByteOrdered` attribute to true, which tells [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use the persisted binary representation on disk for comparisons.</span></span>  
  
2.  <span data-ttu-id="a9eda-248">Utilizzare il metodo `Write` per il tipo definito dall'utente `Currency` per stabilire in che modo rendere tale tipo persistente su disco e confrontarne e ordinarne i valori per le operazioni [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9eda-248">Use the `Write` method for the `Currency` UDT to determine how the UDT is persisted on disk and therefore how UDT values are compared and ordered for [!INCLUDE[tsql](../../includes/tsql-md.md)] operations.</span></span>  
  
3.  <span data-ttu-id="a9eda-249">Salvare il tipo definito dall'utente `Currency` utilizzando il formato binario seguente:</span><span class="sxs-lookup"><span data-stu-id="a9eda-249">Save the `Currency` UDT using the following binary format:</span></span>  
  
    1.  <span data-ttu-id="a9eda-250">Salvare le impostazioni cultura come stringa codificata UTF-16 per i byte 0-19 con riempimento a destra con caratteri Null.</span><span class="sxs-lookup"><span data-stu-id="a9eda-250">Save the culture as a UTF-16 encoded string for bytes 0-19 with padding to the right with null characters.</span></span>  
  
    2.  <span data-ttu-id="a9eda-251">Utilizzare i byte 20 e successivi per contenere il valore decimale della valuta.</span><span class="sxs-lookup"><span data-stu-id="a9eda-251">Use bytes 20 and above to contain the decimal value of the currency.</span></span>  
  
 <span data-ttu-id="a9eda-252">Lo scopo del riempimento è assicurare che le impostazioni cultura vengano separate completamente dal valore di valuta, in modo che quando un tipo definito dall'utente viene confrontato con un altro tipo nel codice [!INCLUDE[tsql](../../includes/tsql-md.md)], i byte delle impostazioni cultura vengono confrontati con i byte delle impostazioni cultura e i valori dei byte della valuta vengono confrontati con i valori dei byte della valuta.</span><span class="sxs-lookup"><span data-stu-id="a9eda-252">The purpose of the padding is to ensure that the culture is completely separated from the currency value, so that when one UDT is compared against another in [!INCLUDE[tsql](../../includes/tsql-md.md)] code, culture bytes are compared against culture bytes, and currency byte values are compared against currency byte values.</span></span>  
  
 <span data-ttu-id="a9eda-253">Per il listato di codice completo per il `Currency` tipo definito dall'utente, seguire le istruzioni per l'installazione degli esempi CLR in [SQL Server motore di database esempi](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="a9eda-253">For the complete code listing for the `Currency` UDT, follow the directions for installing the CLR samples in [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
### <a name="currency-attributes"></a><span data-ttu-id="a9eda-254">Attributi di Currency</span><span class="sxs-lookup"><span data-stu-id="a9eda-254">Currency Attributes</span></span>  
 <span data-ttu-id="a9eda-255">Il tipo definito dall'utente (UDT) `Currency` viene definito con gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9eda-255">The `Currency` UDT is defined with the following attributes.</span></span>  
  
```vb  
<Serializable(), Microsoft.SqlServer.Server.SqlUserDefinedType( _  
    Microsoft.SqlServer.Server.Format.UserDefined, _  
    IsByteOrdered:=True, MaxByteSize:=32), _  
    CLSCompliant(False)> _  
Public Structure Currency  
Implements INullable, IComparable, _  
Microsoft.SqlServer.Server.IBinarySerialize  
```  
  
```csharp  
[Serializable]  
[SqlUserDefinedType(Format.UserDefined,   
    IsByteOrdered = true, MaxByteSize = 32)]  
    [CLSCompliant(false)]  
    public struct Currency : INullable, IComparable, IBinarySerialize  
    {  
```  
  
## <a name="creating-read-and-write-methods-with-ibinaryserialize"></a><span data-ttu-id="a9eda-256">Creazione di metodi di lettura e scrittura con IBinarySerialize</span><span class="sxs-lookup"><span data-stu-id="a9eda-256">Creating Read and Write Methods with IBinarySerialize</span></span>  
 <span data-ttu-id="a9eda-257">Quando si sceglie il formato di serializzazione `UserDefined`, è anche necessario implementare l'interfaccia `IBinarySerialize` e creare metodi `Read` e `Write` personalizzati.</span><span class="sxs-lookup"><span data-stu-id="a9eda-257">When you choose `UserDefined` serialization format, you also must implement the `IBinarySerialize` interface and create your own `Read` and `Write` methods.</span></span> <span data-ttu-id="a9eda-258">Le procedure riportate di seguito dell'UDT `Currency` utilizzano `System.IO.BinaryReader` e `System.IO.BinaryWriter` per la lettura e la scrittura nel tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="a9eda-258">The following procedures from the `Currency` UDT use the `System.IO.BinaryReader` and `System.IO.BinaryWriter` to read from and write to the UDT.</span></span>  
  
```vb  
' IBinarySerialize methods  
' The binary layout is as follow:  
'    Bytes 0 - 19: Culture name, padded to the right with null  
'    characters, UTF-16 encoded  
'    Bytes 20+: Decimal value of money  
' If the culture name is empty, the currency is null.  
Public Sub Write(ByVal w As System.IO.BinaryWriter) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Write  
    If Me.IsNull Then  
        w.Write(nullMarker)  
        w.Write(System.Convert.ToDecimal(0))  
        Return  
    End If  
  
    If cultureName.Length > cultureNameMaxSize Then  
        Throw New ApplicationException(String.Format(CultureInfo.CurrentUICulture, _  
           "{0} is an invalid culture name for currency as it is too long.", cultureNameMaxSize))  
    End If  
  
    Dim paddedName As String = cultureName.PadRight(cultureNameMaxSize, CChar(vbNullChar))  
  
    For i As Integer = 0 To cultureNameMaxSize - 1  
        w.Write(paddedName(i))  
    Next i  
  
    ' Normalize decimal value to two places  
    currencyVal = Decimal.Floor(currencyVal * 100) / 100  
    w.Write(currencyVal)  
End Sub  
  
Public Sub Read(ByVal r As System.IO.BinaryReader) _  
  Implements Microsoft.SqlServer.Server.IBinarySerialize.Read  
    Dim name As Char() = r.ReadChars(cultureNameMaxSize)  
    Dim stringEnd As Integer = Array.IndexOf(name, CChar(vbNullChar))  
  
    If stringEnd = 0 Then  
        cultureName = Nothing  
        Return  
    End If  
  
    cultureName = New String(name, 0, stringEnd)  
    currencyVal = r.ReadDecimal()  
End Sub  
  
```  
  
```csharp  
// IBinarySerialize methods  
// The binary layout is as follow:  
//    Bytes 0 - 19:Culture name, padded to the right   
//    with null characters, UTF-16 encoded  
//    Bytes 20+:Decimal value of money  
// If the culture name is empty, the currency is null.  
public void Write(System.IO.BinaryWriter w)  
{  
    if (this.IsNull)  
    {  
        w.Write(nullMarker);  
        w.Write((decimal)0);  
        return;  
    }  
  
    if (cultureName.Length > cultureNameMaxSize)  
    {  
        throw new ApplicationException(string.Format(  
            CultureInfo.InvariantCulture,   
            "{0} is an invalid culture name for currency as it is too long.",   
            cultureNameMaxSize));  
    }  
  
    String paddedName = cultureName.PadRight(cultureNameMaxSize, '\0');  
    for (int i = 0; i < cultureNameMaxSize; i++)  
    {  
        w.Write(paddedName[i]);  
    }  
  
    // Normalize decimal value to two places  
    currencyValue = Decimal.Floor(currencyValue * 100) / 100;  
    w.Write(currencyValue);  
}  
public void Read(System.IO.BinaryReader r)  
{  
    char[] name = r.ReadChars(cultureNameMaxSize);  
    int stringEnd = Array.IndexOf(name, '\0');  
  
    if (stringEnd == 0)  
    {  
        cultureName = null;  
        return;  
    }  
  
    cultureName = new String(name, 0, stringEnd);  
    currencyValue = r.ReadDecimal();  
}  
```  
  
 <span data-ttu-id="a9eda-259">Per il listato di codice completo per il `Currency` tipo definito dall'utente, vedere [SQL Server motore di database Samples](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="a9eda-259">For the complete code listing for the `Currency` UDT, see [SQL Server Database Engine Samples](https://msftengprodsamples.codeplex.com/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9eda-260">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9eda-260">See Also</span></span>  
 [<span data-ttu-id="a9eda-261">Creazione di un tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="a9eda-261">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
  
