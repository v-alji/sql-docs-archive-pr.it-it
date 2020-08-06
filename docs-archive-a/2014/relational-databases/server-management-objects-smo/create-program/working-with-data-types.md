---
title: Utilizzo dei tipi di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DataType object
- SQL Server Management Objects, data types
- data types [SMO]
- SMO [SQL Server], data types
ms.assetid: 1e0e736a-c709-4d89-aeb2-b32dcfd641fa
author: stevestein
ms.author: sstein
ms.openlocfilehash: cbffc1c59eb12fa0f448a7fcb26157d5e18dba3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625262"
---
# <a name="working-with-data-types"></a><span data-ttu-id="7306d-102">Utilizzo dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7306d-102">Working with Data Types</span></span>
  <span data-ttu-id="7306d-103">I dati sono disponibili in diversi tipi e dimensioni, ad esempio una stringa con una lunghezza definita, un numero con una accuratezza specifica o un tipo di dati definito dall'utente che rappresenta un altro oggetto con un set di regole specifico.</span><span class="sxs-lookup"><span data-stu-id="7306d-103">Data comes in many types and sizes, such as a string that has a defined length, a number that has specific accuracy, or a user-defined data type that is another object that has its own set of rules.</span></span> <span data-ttu-id="7306d-104">L' <xref:Microsoft.SqlServer.Management.Smo.DataType> oggetto classifica il tipo di dati in modo che possa essere gestito correttamente da [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7306d-104">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object classifies the type of data so that it can be handled correctly by [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7306d-105">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType> è associato a oggetti che accettano dati.</span><span class="sxs-lookup"><span data-stu-id="7306d-105">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object is associated with objects that accept data.</span></span> <span data-ttu-id="7306d-106">Gli oggetti [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) seguenti accettano dati che devono essere definiti da una proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType>:</span><span class="sxs-lookup"><span data-stu-id="7306d-106">The following [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Management Objects (SMO) objects accept data that must be defined by a <xref:Microsoft.SqlServer.Management.Smo.DataType> object property:</span></span>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.Column>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.StoredProcedureParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedFunctionParameter>  
  
-   <xref:Microsoft.SqlServer.Management.Smo.UserDefinedAggregateParameter>  
  
 <span data-ttu-id="7306d-107">La proprietà `DataType` per oggetti che accettano dati può essere impostata in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="7306d-107">The `DataType` property for objects that accept data can be set in several ways.</span></span>  
  
-   <span data-ttu-id="7306d-108">Utilizzare il costruttore predefinito e specificare in modo esplicito le proprietà dell'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType></span><span class="sxs-lookup"><span data-stu-id="7306d-108">Use the default constructor and specify <xref:Microsoft.SqlServer.Management.Smo.DataType> object properties explicitly</span></span>  
  
-   <span data-ttu-id="7306d-109">Utilizzare un costruttore di overload e specificare le proprietà <xref:Microsoft.SqlServer.Management.Smo.DataType> come parametri.</span><span class="sxs-lookup"><span data-stu-id="7306d-109">Use an overloaded constructor and specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> properties as parameters.</span></span>  
  
-   <span data-ttu-id="7306d-110">Specificare l'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType> inline nel costruttore di oggetti.</span><span class="sxs-lookup"><span data-stu-id="7306d-110">Specify the <xref:Microsoft.SqlServer.Management.Smo.DataType> inline in the object constructor.</span></span>  
  
-   <span data-ttu-id="7306d-111">Utilizzare uno dei membri statici della classe <xref:Microsoft.SqlServer.Management.Smo.DataType>, ad esempio `Int`.</span><span class="sxs-lookup"><span data-stu-id="7306d-111">Use one of the static members of the <xref:Microsoft.SqlServer.Management.Smo.DataType> class, for example `Int`.</span></span> <span data-ttu-id="7306d-112">In questo modo verrà restituita un'istanza di un oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType>.</span><span class="sxs-lookup"><span data-stu-id="7306d-112">This will in fact return an instance of a <xref:Microsoft.SqlServer.Management.Smo.DataType> object.</span></span>  
  
 <span data-ttu-id="7306d-113">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.DataType> include diverse proprietà che definiscono il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7306d-113">The <xref:Microsoft.SqlServer.Management.Smo.DataType> object has several properties that define the type of data.</span></span> <span data-ttu-id="7306d-114">La proprietà <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> specifica, ad esempio, il tipo di dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7306d-114">For example, the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> property specifies the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.</span></span> <span data-ttu-id="7306d-115">I valori costanti che rappresentano i tipi di dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sono elencati nell'enumerazione <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="7306d-115">The constant values that represent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types are listed in the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="7306d-116">Tale enumerazione si riferisce a tipi di dati quali `varchar`, `nchar`, `currency`, `integer`, `float` e `datetime`.</span><span class="sxs-lookup"><span data-stu-id="7306d-116">This refers to data types such as `varchar`, `nchar`, `currency`, `integer`, `float`, and `datetime`.</span></span>  
  
 <span data-ttu-id="7306d-117">Quando viene stabilito il tipo di dati, è necessario impostare proprietà specifiche per i dati.</span><span class="sxs-lookup"><span data-stu-id="7306d-117">When the data type is established, specific properties must be set for the data.</span></span> <span data-ttu-id="7306d-118">Se, ad esempio, i dati sono di tipo `nchar`, è necessario impostare la lunghezza dei dati di stringa nella proprietà `Length`.</span><span class="sxs-lookup"><span data-stu-id="7306d-118">For example, if it is an `nchar` type, the length of the string data must be set in the `Length` property.</span></span> <span data-ttu-id="7306d-119">La stessa operazione è richiesta anche nel caso dei valori numerici, per i quali è necessario specificare la precisione e la scala.</span><span class="sxs-lookup"><span data-stu-id="7306d-119">The same applies for numeric values, where you would have to specify precision and scale.</span></span>  
  
 <span data-ttu-id="7306d-120">I tipi di dati <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> fanno riferimento agli oggetti contenenti la definizione de tipo di dati fornita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7306d-120"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> and <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> data types refer to objects that contain the definition of the type of data defined by the user.</span></span> <span data-ttu-id="7306d-121"><xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> si basa sui tipi di dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dell'enumerazione <xref:Microsoft.SqlServer.Management.Smo.SqlDataType>.</span><span class="sxs-lookup"><span data-stu-id="7306d-121">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> is based on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types from the <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration.</span></span> <span data-ttu-id="7306d-122">L'oggetto <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> è basato sui [!INCLUDE[msCoName](../../../includes/msconame-md.md)] tipi di dati .NET.</span><span class="sxs-lookup"><span data-stu-id="7306d-122">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> is based on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET data types.</span></span> <span data-ttu-id="7306d-123">In genere, rappresentano dati di un tipo specifico riutilizzati di frequente dal database in base a regole business definite dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7306d-123">Typically, these would represent data of a specific type that is frequently reused by the database because of business rules defined by the organization.</span></span> <span data-ttu-id="7306d-124">Un tipo di dati che consente, ad esempio, di archiviare un importo e un denominatore di valuta risulterebbe utile in una società che gestisce più valute.</span><span class="sxs-lookup"><span data-stu-id="7306d-124">For example, a data type that stores an amount of money and a currency denominator would be helpful in a company that deals in multiple currencies.</span></span>  
  
 <span data-ttu-id="7306d-125">L'enumerazione <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> contiene un elenco di tutti i tipi di dati supportati in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7306d-125">The <xref:Microsoft.SqlServer.Management.Smo.SqlDataType> enumeration contains a list of all the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-supported data types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7306d-126">Esempi</span><span class="sxs-lookup"><span data-stu-id="7306d-126">Examples</span></span>  
 [!INCLUDE[ssChooseProgEnv](../../../includes/sschooseprogenv-md.md)]  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-basic"></a><span data-ttu-id="7306d-127">Costruzione di un oggetto DataType con la specifica nel costruttore di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7306d-127">Constructing a DataType Object with the Specification in the Constructor in Visual Basic</span></span>  
 <span data-ttu-id="7306d-128">In questo esempio di codice viene illustrato come utilizzare il costruttore per creare istanze dei tipi di dati basate su tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differenti.</span><span class="sxs-lookup"><span data-stu-id="7306d-128">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7306d-129">I tipi <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e XML richiedono tutti un nome per identificare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7306d-129">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes1](SMO How to#SMO_VBDataTypes1)]  -->  
  
## <a name="constructing-a-datatype-object-with-the-specification-in-the-constructor-in-visual-c"></a><span data-ttu-id="7306d-130">Costruzione di un oggetto DataType con la specifica nel costruttore di Visual C#</span><span class="sxs-lookup"><span data-stu-id="7306d-130">Constructing a DataType Object with the Specification in the Constructor in Visual C#</span></span>  
 <span data-ttu-id="7306d-131">In questo esempio di codice viene illustrato come utilizzare il costruttore per creare istanze dei tipi di dati basate su tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differenti.</span><span class="sxs-lookup"><span data-stu-id="7306d-131">This code example shows how to use the constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7306d-132">I tipi <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> e XML richiedono tutti un nome per identificare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7306d-132">The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare a DataType object variable and define the data type in the constructor.   
DataType dt;   
//For the decimal data type the following two arguments specify precision, and scale.   
dt = new DataType(SqlDataType.Decimal, 10, 2);   
}  
```  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-basic"></a><span data-ttu-id="7306d-133">Costruzione di un oggetto DataType mediante il costruttore predefinito di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7306d-133">Constructing a DataType Object by Using the Default Constructor in Visual Basic</span></span>  
 <span data-ttu-id="7306d-134">In questo esempio di codice viene illustrato come utilizzare il costruttore predefinito per creare istanze dei tipi di dati basate su tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differenti.</span><span class="sxs-lookup"><span data-stu-id="7306d-134">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="7306d-135">Successivamente vengono utilizzate le proprietà per specificare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7306d-135">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="7306d-136">**Nota** I <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> tipi XML, e richiedono tutti un valore Name per identificare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7306d-136">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBDataTypes2](SMO How to#SMO_VBDataTypes2)]  -->  
  
## <a name="constructing-a-datatype-object-by-using-the-default-constructor-in-visual-c"></a><span data-ttu-id="7306d-137">Costruzione di un oggetto DataType mediante il costruttore predefinito di Visual C#</span><span class="sxs-lookup"><span data-stu-id="7306d-137">Constructing a DataType Object by Using the Default Constructor in Visual C#</span></span>  
 <span data-ttu-id="7306d-138">In questo esempio di codice viene illustrato come utilizzare il costruttore predefinito per creare istanze dei tipi di dati basate su tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] differenti.</span><span class="sxs-lookup"><span data-stu-id="7306d-138">This code example shows how to use the default constructor to create instances of data types that are based on different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types.</span></span> <span data-ttu-id="7306d-139">Successivamente vengono utilizzate le proprietà per specificare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="7306d-139">The properties are then used to specify the data type.</span></span>  
  
 <span data-ttu-id="7306d-140">**Nota** I <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType> <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType> tipi XML, e richiedono tutti un valore Name per identificare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7306d-140">**Note** The <xref:Microsoft.SqlServer.Management.Smo.UserDefinedType>, <xref:Microsoft.SqlServer.Management.Smo.UserDefinedDataType>, and XML types all require a name value to identify the object.</span></span>  
  
```  
{   
//Declare and create a DataType object variable.   
DataType dt;   
dt = new DataType();   
//Define the data type by setting the SqlDataType property.   
dt.SqlDataType = SqlDataType.VarChar;   
//The VarChar data type requires a value for the MaximumLength property.   
dt.MaximumLength = 100;   
}  
```  
  
  
