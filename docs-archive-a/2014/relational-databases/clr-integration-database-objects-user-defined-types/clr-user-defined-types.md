---
title: Tipi CLR definiti dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- validation [CLR integration]
- types [CLR integration]
- UserDefined serialization format [CLR integration]
- null values [CLR integration]
- serialization
- Native serialization format [CLR integration]
- databases [CLR integration]
- building database objects [CLR integration], user-defined types
- user-defined types [CLR integration]
- common language runtime [SQL Server], user-defined types
- UDTs [CLR integration]
- database objects [CLR integration], user-defined types
- turning on CLR functionality
- customizing UDT expression return types [CLR integration]
- UDTs [CLR integration], about UDTs
- comparing UDT values
- annotations [CLR integration]
- user-defined types [CLR integration], about UDTs
- variables [CLR integration]
- invoking UDT methods
- indexes [CLR integration]
ms.assetid: 27c4889b-c543-47a8-a630-ad06804f92df
author: rothja
ms.author: jroth
ms.openlocfilehash: e4e19323eeac9e0a1148924543f71aa7de5619b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637917"
---
# <a name="clr-user-defined-types"></a><span data-ttu-id="4ab7f-102">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="4ab7f-102">CLR User-Defined Types</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="4ab7f-103">consente di creare oggetti di database programmati in un assembly creato in Common Language Runtime (CLR) di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-103">gives you the ability to create database objects that are programmed against an assembly created in the.NET Framework common language runtime (CLR).</span></span> <span data-ttu-id="4ab7f-104">Tra gli oggetti di database che consentono l'utilizzo del ricco modello di programmazione offerto da CLR vi sono trigger, stored procedure, funzioni, funzioni di aggregazione e tipi.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-104">Database objects that can take advantage of the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4ab7f-105">Per impostazione predefinita, l'esecuzione di codice CLR in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è disattivata.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-105">The ability to execute CLR code is set to OFF by default in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4ab7f-106">CLR può essere abilitato tramite l'stored procedure di sistema **sp_configure** .</span><span class="sxs-lookup"><span data-stu-id="4ab7f-106">The CLR can be enabled by using the **sp_configure** system stored procedure.</span></span>  
  
 <span data-ttu-id="4ab7f-107">A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , è possibile usare i tipi definiti dall'utente (UDT) per estendere il sistema di tipi scalari del server, abilitando l'archiviazione di oggetti CLR in un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-107">Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], you can use user-defined types (UDTs) to extend the scalar type system of the server, enabling storage of CLR objects in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="4ab7f-108">I tipi definiti dall'utente possono contenere più elementi e assumere vari comportamenti. Questo li differenzia dai tipi di dati alias tradizionali costituiti da un singolo tipo di dati di sistema di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ab7f-108">UDTs can contain multiple elements and can have behaviors, differentiating them from the traditional alias data types which consist of a single [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system data type.</span></span>  
  
 <span data-ttu-id="4ab7f-109">Poiché il sistema accede ai tipi definiti dall'utente nella loro interezza, l'utilizzo che ne viene fatto per i tipi di dati complessi può influire negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-109">Because UDTs are accessed by the system as a whole, their use for complex data types may negatively impact performance.</span></span> <span data-ttu-id="4ab7f-110">Il modo migliore per modellare i dati complessi in genere consiste nell'utilizzare righe e tabelle tradizionali.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-110">Complex data is generally best modeled using traditional rows and tables.</span></span> <span data-ttu-id="4ab7f-111">I tipi definiti dall'utente in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] risultano particolarmente adatti per:</span><span class="sxs-lookup"><span data-stu-id="4ab7f-111">UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are well suited to the following:</span></span>  
  
-   <span data-ttu-id="4ab7f-112">Data, ora, valuta e tipi numerici estesi</span><span class="sxs-lookup"><span data-stu-id="4ab7f-112">Date, time, currency, and extended numeric types</span></span>  
  
-   <span data-ttu-id="4ab7f-113">Applicazioni Geospatial</span><span class="sxs-lookup"><span data-stu-id="4ab7f-113">Geospatial applications</span></span>  
  
-   <span data-ttu-id="4ab7f-114">Dati codificati o crittografati</span><span class="sxs-lookup"><span data-stu-id="4ab7f-114">Encoded or encrypted data</span></span>  
  
 <span data-ttu-id="4ab7f-115">Il processo di sviluppo dei tipi definiti dall'utente in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è costituito dai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4ab7f-115">The process of developing UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="4ab7f-116">**Codifica e compilazione dell'assembly che definisce il tipo definito dall'utente.**</span><span class="sxs-lookup"><span data-stu-id="4ab7f-116">**Code and build the assembly that defines the UDT.**</span></span> <span data-ttu-id="4ab7f-117">I tipi definiti dall'utente vengono definiti utilizzando uno dei linguaggi supportati da CLR (Common Language Runtime) di .NET Framework che generano codice verificabile, tra cui, ad esempio,</span><span class="sxs-lookup"><span data-stu-id="4ab7f-117">UDTs are defined using any of the languages supported by the.NET Framework common language runtime (CLR) that produce verifiable code.</span></span> <span data-ttu-id="4ab7f-118">Microsoft Visual C# e Visual Basic .NET.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-118">This includes Visual C# and Visual Basic .NET.</span></span> <span data-ttu-id="4ab7f-119">I dati vengono esposti come campi e proprietà di una classe o una struttura .NET Framework mentre i comportamenti vengono definiti dai metodi della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-119">The data is exposed as fields and properties of a .NET Framework class or structure, and behaviors are defined by methods of the class or structure.</span></span>  
  
2.  <span data-ttu-id="4ab7f-120">**Registrazione dell'assembly.**</span><span class="sxs-lookup"><span data-stu-id="4ab7f-120">**Register the assembly.**</span></span> <span data-ttu-id="4ab7f-121">I tipi definiti dall'utente possono essere distribuiti attraverso l'interfaccia utente di Visual Studio in un progetto di database o mediante l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY, che copia l'assembly contenente la classe o la struttura in un database.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-121">UDTs can be deployed through the Visual Studio user interface in a database project, or by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE ASSEMBLY statement, which copies the assembly containing the class or structure into a database.</span></span>  
  
3.  <span data-ttu-id="4ab7f-122">**Creazione del tipo definito dall'utente in SQL Server.**</span><span class="sxs-lookup"><span data-stu-id="4ab7f-122">**Create the UDT in SQL Server.**</span></span> <span data-ttu-id="4ab7f-123">Dopo aver caricato un assembly in un database host, viene utilizzata l'istruzione [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE per creare un tipo definito dall'utente e vengono esposti i membri della classe o della struttura come membri del tipo in questione.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-123">Once an assembly is loaded into a host database, you use the [!INCLUDE[tsql](../../includes/tsql-md.md)] CREATE TYPE statement to create a UDT and expose the members of the class or structure as members of the UDT.</span></span> <span data-ttu-id="4ab7f-124">I tipi definiti dall'utente esistono solo nel contesto di un singolo database e dopo la registrazione non hanno dipendenze sui file esterni da cui sono stati creati.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-124">UDTs exist only in the context of a single database, and, once registered, have no dependencies on the external files from which they were created.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4ab7f-125">Prima di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], i tipi definiti dall'utente creati dagli assembly di .NET Framework non erano supportati.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-125">Before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], UDTs created from .NET Framework assemblies were not supported.</span></span> <span data-ttu-id="4ab7f-126">Tuttavia, è comunque possibile usare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] i tipi di dati alias usando **sp_addtype**.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-126">However, you can still use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alias data types by using **sp_addtype**.</span></span> <span data-ttu-id="4ab7f-127">La sintassi CREATE TYPE può essere utilizzata per creare tipi di dati definiti dall'utente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nativi e tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-127">The CREATE TYPE syntax can be used for creating both native [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user-defined data types and UDTs.</span></span>  
  
4.  <span data-ttu-id="4ab7f-128">**Creare tabelle, variabili o parametri usando il tipo definito dall'utente** A partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , un tipo definito dall'utente può essere utilizzato come definizione di colonna di una tabella, come variabile in un [!INCLUDE[tsql](../../includes/tsql-md.md)] batch o come argomento di una [!INCLUDE[tsql](../../includes/tsql-md.md)] funzione o stored procedure.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-128">**Create tables, variables, or parameters using the UDT** Beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], a user-defined type can be used as the column definition of a table, as a variable in a [!INCLUDE[tsql](../../includes/tsql-md.md)] batch, or as an argument of a [!INCLUDE[tsql](../../includes/tsql-md.md)] function or stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ab7f-129">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4ab7f-129">In This Section</span></span>  
 [<span data-ttu-id="4ab7f-130">Creazione di un tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="4ab7f-130">Creating a User-Defined Type</span></span>](creating-user-defined-types.md)  
 <span data-ttu-id="4ab7f-131">Viene illustrato come creare tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-131">Describes how to create UDTs.</span></span>  
  
 [<span data-ttu-id="4ab7f-132">Registrazione dei tipi definiti dall'utente in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ab7f-132">Registering User-Defined Types in SQL Server</span></span>](registering-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="4ab7f-133">Viene illustrato come registrare e gestire i tipi definiti dall'utente (UDT) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ab7f-133">Describes how to register and manage UDTs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="4ab7f-134">Uso di tipi definiti dall'utente in SQL Server</span><span class="sxs-lookup"><span data-stu-id="4ab7f-134">Working with User-Defined Types in SQL Server</span></span>](working-with-user-defined-types-in-sql-server.md)  
 <span data-ttu-id="4ab7f-135">Viene descritto come creare query mediante i tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-135">Describes how to create queries using UDTs.</span></span>  
  
 [<span data-ttu-id="4ab7f-136">Accesso ai tipi definiti dall'utente in ADO .NET</span><span class="sxs-lookup"><span data-stu-id="4ab7f-136">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
 <span data-ttu-id="4ab7f-137">Viene illustrato come utilizzare i tipi definiti dall'utente mediante il provider di dati .NET Framework per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="4ab7f-137">Describes how to work with UDTs using the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in ADO.NET.</span></span>  
  
  
