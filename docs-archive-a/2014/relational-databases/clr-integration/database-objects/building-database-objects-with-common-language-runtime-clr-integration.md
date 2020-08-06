---
title: Compilazione di oggetti di database con l'integrazione con CLR (Common Language Runtime) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- database objects [CLR integration], building
- common language runtime [SQL Server], building database objects
- managed code [SQL Server], database objects
- building database objects [CLR integration]
- .NET Framework routines [SQL Server]
ms.assetid: ce34132c-bfa3-447b-9131-b6e17c672efe
author: rothja
ms.author: jroth
ms.openlocfilehash: 3c849c095a3be1c590e6fcb3ce87a0725eb795c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629866"
---
# <a name="building-database-objects-with-common-language-runtime-clr-integration"></a><span data-ttu-id="e747c-102">Compilazione di oggetti di database con l'integrazione con CLR (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="e747c-102">Building Database Objects with Common Language Runtime (CLR) Integration</span></span>
  <span data-ttu-id="e747c-103">È possibile creare oggetti di database utilizzando l'oggetto [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] definito "routine CLR".</span><span class="sxs-lookup"><span data-stu-id="e747c-103">You can build database objects using the [!INCLUDE[ssNoVersion](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is referred to as a "CLR routine."</span></span> <span data-ttu-id="e747c-104">Queste routine includono gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e747c-104">These routines include:</span></span>  
  
-   <span data-ttu-id="e747c-105">Funzioni definite dall'utente con valori scalari</span><span class="sxs-lookup"><span data-stu-id="e747c-105">Scalar-valued user-defined functions (scalar UDFs)</span></span>  
  
-   <span data-ttu-id="e747c-106">Funzioni definite dall'utente con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="e747c-106">Table-valued user-defined functions (TVFs)</span></span>  
  
-   <span data-ttu-id="e747c-107">Procedure definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="e747c-107">User-defined procedures (UDPs)</span></span>  
  
-   <span data-ttu-id="e747c-108">Trigger definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="e747c-108">User-defined triggers</span></span>  
  
 <span data-ttu-id="e747c-109">Le routine CLR hanno la stessa struttura in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="e747c-109">CLR routines have the same structure in managed code.</span></span> <span data-ttu-id="e747c-110">Viene eseguito il mapping di tali routine a metodi pubblici e statici (condivisi in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) di una classe.</span><span class="sxs-lookup"><span data-stu-id="e747c-110">They are mapped to public, static (shared in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic .NET) methods of a class.</span></span> <span data-ttu-id="e747c-111">Oltre alle routine, è possibile definire tipi definiti dall'utente e funzioni di aggregazione definite dall'utente utilizzando .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e747c-111">In addition to routines, user-defined types (UDTs) and user-defined aggregate functions can also be defined using the .NET Framework.</span></span> <span data-ttu-id="e747c-112">Viene eseguito il mapping dei tipi definiti dall'utente (UDT) e delle aggregazioni definite dall'utente a intere classi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e747c-112">UDTs and user-defined aggregates are mapped to entire .NET Framework classes.</span></span>  
  
 <span data-ttu-id="e747c-113">Ogni tipo di .NET Framework routine dispone di un oggetto [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] che [!INCLUDE[tsql](../../../includes/tsql-md.md)] può essere utilizzato dall'oggetto equivalente.</span><span class="sxs-lookup"><span data-stu-id="e747c-113">Each type of .NET Framework routine has a [!INCLUDE[tsql](../../../includes/ssnoversion-md.md)] that the [!INCLUDE[tsql](../../../includes/tsql-md.md)] equivalent can be used.</span></span> <span data-ttu-id="e747c-114">Le funzioni scalari definite dall'utente, ad esempio, possono essere utilizzate in qualsiasi espressione scalare.</span><span class="sxs-lookup"><span data-stu-id="e747c-114">For instance, scalar UDFs can be used in any scalar expression.</span></span> <span data-ttu-id="e747c-115">Una funzione con valori di tabella può essere utilizzata in qualsiasi clausola FROM.</span><span class="sxs-lookup"><span data-stu-id="e747c-115">A TVF can be used in any FROM clause.</span></span> <span data-ttu-id="e747c-116">Una procedura può essere richiamata in un'istruzione EXEC o da un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="e747c-116">A procedure can be invoked in an EXEC statement or invoked from a client application.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e747c-117">L'esecuzione di un oggetto CLR (funzione definita dall'utente, tipo definito dall'utente o trigger) sul Common Language Runtime può avvenire su più thread (piano parallelo), se il Query Optimizer decide che è vantaggioso.</span><span class="sxs-lookup"><span data-stu-id="e747c-117">Execution of a CLR object (user-defined function, user-defined type, or trigger) on the common language runtime can take place on multiple threads (parallel plan), if the query optimizer decides it is beneficial.</span></span> <span data-ttu-id="e747c-118">Tuttavia, se una funzione definita dall'utente accede ai dati, l'esecuzione sarà su un piano seriale.</span><span class="sxs-lookup"><span data-stu-id="e747c-118">However, if a user-defined function accesses data, execution will be  on a serial plan.</span></span> <span data-ttu-id="e747c-119">Anche in caso di esecuzione in una versione server precedente a [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] e se in una funzione definita dall'utente sono contenuti parametri LOB o valori restituiti, l'esecuzione deve essere su un piano seriale.</span><span class="sxs-lookup"><span data-stu-id="e747c-119">When executed on a server version prior to [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)], if a user-defined function contains LOB parameters or return values, execution also must be on a serial plan.</span></span>  
  
 <span data-ttu-id="e747c-120">Nella tabella seguente sono elencati gli argomenti inclusi in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="e747c-120">The following table lists the topics covered in this section.</span></span>  
  
 [<span data-ttu-id="e747c-121">Introduzione all'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="e747c-121">Getting Started with CLR Integration</span></span>](getting-started-with-clr-integration.md)  
 <span data-ttu-id="e747c-122">Include una breve panoramica delle librerie e degli spazi dei nomi necessari per compilare l'oggetto utilizzando l'integrazione con CLR con [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e747c-122">Provides a brief overview of the libraries and namespaces required to compile object using CLR integration with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="e747c-123">È inclusa una stored procedure CLR "Hello World" di esempio.</span><span class="sxs-lookup"><span data-stu-id="e747c-123">Includes an example "Hello World" CLR stored procedure.</span></span>  
  
 [<span data-ttu-id="e747c-124">Librerie .NET Framework supportate</span><span class="sxs-lookup"><span data-stu-id="e747c-124">Supported .NET Framework Libraries</span></span>](supported-net-framework-libraries.md)  
 <span data-ttu-id="e747c-125">Include informazioni sulle librerie .NET Framework supportate dall'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="e747c-125">Provides information on the .NET Framework libraries supported by CLR integration.</span></span>  
  
 [<span data-ttu-id="e747c-126">Restrizioni relative al modello di programmazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="e747c-126">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
 <span data-ttu-id="e747c-127">Include informazioni sulle restrizioni del modello di programmazione dell'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="e747c-127">Provides information about CLR integration programming model restrictions.</span></span>  
  
 [<span data-ttu-id="e747c-128">Tipi di dati di SQL Server in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e747c-128">SQL Server Data Types in the .NET Framework</span></span>](../../clr-integration-database-objects-types-net-framework/sql-server-data-types-in-the-net-framework.md)  
 <span data-ttu-id="e747c-129">Panoramica dei tipi di dati di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e degli equivalenti di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e747c-129">An overview of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data types and their .NET Framework equivalents.</span></span>  
  
 [<span data-ttu-id="e747c-130">Panoramica degli attributi personalizzati dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="e747c-130">Overview of CLR Integration Custom Attributes</span></span>](../../../database-engine/dev-guide/overview-of-clr-integration-custom-attributes.md)  
 <span data-ttu-id="e747c-131">Include informazioni sugli attributi personalizzati dell'integrazione CLR.</span><span class="sxs-lookup"><span data-stu-id="e747c-131">Provides information about CLR integration custom attributes.</span></span>  
  
 [<span data-ttu-id="e747c-132">Funzioni CLR definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="e747c-132">CLR User-Defined Functions</span></span>](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md)  
 <span data-ttu-id="e747c-133">Viene descritto come implementare e utilizzare i diversi tipi di funzioni CLR, ovvero le funzioni con valori di tabella, le funzioni scalari e le funzioni di aggregazione definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e747c-133">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="e747c-134">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="e747c-134">CLR User-Defined Types</span></span>](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md)  
 <span data-ttu-id="e747c-135">Viene descritto come implementare e utilizzare i tipi CLR definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e747c-135">Describes how to implement and use CLR user-defined types.</span></span>  
  
 [<span data-ttu-id="e747c-136">Stored procedure CLR</span><span class="sxs-lookup"><span data-stu-id="e747c-136">CLR Stored Procedures</span></span>](../../../database-engine/dev-guide/clr-stored-procedures.md)  
 <span data-ttu-id="e747c-137">Viene descritto come implementare e utilizzare le stored procedure CLR.</span><span class="sxs-lookup"><span data-stu-id="e747c-137">Describes how to implement and use CLR stored procedures.</span></span>  
  
 [<span data-ttu-id="e747c-138">Trigger CLR</span><span class="sxs-lookup"><span data-stu-id="e747c-138">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
 <span data-ttu-id="e747c-139">Viene descritto come implementare e utilizzare i trigger CLR.</span><span class="sxs-lookup"><span data-stu-id="e747c-139">Describes how to implement and use CLR triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e747c-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e747c-140">See Also</span></span>  
 [<span data-ttu-id="e747c-141">Panoramica dell'integrazione di Common Language Runtime &#40;CLR&#41;</span><span class="sxs-lookup"><span data-stu-id="e747c-141">Common Language Runtime &#40;CLR&#41; Integration Overview</span></span>](../common-language-runtime-integration-overview.md)  
  
  
