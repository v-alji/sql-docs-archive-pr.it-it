---
title: Creare funzioni di aggregazione definite dall'utente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- aggregate functions [SQL Server], user-defined
- user-defined functions [CLR integration]
ms.assetid: c278b746-6323-4b32-b460-239915acc067
author: rothja
ms.author: jroth
ms.openlocfilehash: c91179cb194bbfb79e8e7a8476e9725877b88afa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724463"
---
# <a name="create-user-defined-aggregates"></a><span data-ttu-id="f530f-102">Creazione di funzioni di aggregazione definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="f530f-102">Create User-defined Aggregates</span></span>
  <span data-ttu-id="f530f-103">È possibile creare un oggetto di database all'interno di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] programmato in un assembly CLR.</span><span class="sxs-lookup"><span data-stu-id="f530f-103">You can create a database object inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is programmed in a CLR assembly.</span></span> <span data-ttu-id="f530f-104">Gli oggetti di database che possono sfruttare il complesso modello di programmazione fornito da CLR includono trigger, stored procedure, funzioni, funzioni di aggregazione e tipi.</span><span class="sxs-lookup"><span data-stu-id="f530f-104">Database objects that can leverage the rich programming model provided by the CLR include triggers, stored procedures, functions, aggregate functions, and types.</span></span>  
  
 <span data-ttu-id="f530f-105">Analogamente alle funzioni di aggregazione predefinite incluse in [!INCLUDE[tsql](../../includes/tsql-md.md)], le funzioni di aggregazione definite dall'utente eseguono un calcolo su un set di valori e restituiscono un unico valore.</span><span class="sxs-lookup"><span data-stu-id="f530f-105">Like the built-in aggregate functions provided in [!INCLUDE[tsql](../../includes/tsql-md.md)], user-defined aggregate functions perform a calculation on a set of values and return a single value.</span></span>  
  
 <span data-ttu-id="f530f-106">Per creare una funzione di aggregazione definita dall'utente in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , eseguire le operazioni descritte di seguito:</span><span class="sxs-lookup"><span data-stu-id="f530f-106">Creating a user-defined aggregate function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] involves the following steps:</span></span>  
  
-   <span data-ttu-id="f530f-107">Impostare la funzione di aggregazione definita dall'utente come una classe utilizzando un linguaggio supportato in [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f530f-107">Define the user-defined aggregate function as a class in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework-supported language.</span></span> <span data-ttu-id="f530f-108">Per altre informazioni sulla programmazione di funzioni di aggregazione definite dall'utente in CLR, vedere [Aggregazioni CLR definite dall'utente](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="f530f-108">For more information about how to program user-defined aggregates in the CLR, see [CLR User-Defined Aggregates](../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md).</span></span> <span data-ttu-id="f530f-109">Compilare questa classe per compilare un assembly CLR utilizzando il compilatore di linguaggio appropriato.</span><span class="sxs-lookup"><span data-stu-id="f530f-109">Compile this class to build a CLR assembly using the appropriate language compiler.</span></span>  
  
-   <span data-ttu-id="f530f-110">Per registrare l'assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilizzare l'istruzione CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="f530f-110">Register the assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="f530f-111">Per altre informazioni sugli assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Assembly &#40;Motore di database&#41;](../clr-integration/assemblies-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="f530f-111">For more information about assemblies in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Assemblies &#40;Database Engine&#41;](../clr-integration/assemblies-database-engine.md).</span></span>  
  
-   <span data-ttu-id="f530f-112">Per creare la funzione di aggregazione definita dall'utente che fa riferimento all'assembly registrato, utilizzare l'istruzione CREATE AGGREGATE.</span><span class="sxs-lookup"><span data-stu-id="f530f-112">Create the user-defined aggregate that references the registered assembly using the CREATE AGGREGATE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f530f-113">Con la distribuzione di un progetto SQL Server in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] viene registrato un assembly nel database specificato per il progetto.</span><span class="sxs-lookup"><span data-stu-id="f530f-113">Deploying a SQL Server Project in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] registers an assembly in the database that was specified for the project.</span></span> <span data-ttu-id="f530f-114">La distribuzione del progetto consente inoltre di creare una funzione di aggregazione definita dall'utente nel database per tutte le definizioni di classe annotate con l'attributo `SqlUserDefinedAggregate`.</span><span class="sxs-lookup"><span data-stu-id="f530f-114">Deploying the project also creates a user-defined aggregate in the database for all class definitions annotated with the `SqlUserDefinedAggregate` attribute.</span></span> <span data-ttu-id="f530f-115">Per altre informazioni, vedere [Distribuzione di oggetti di database CLR](../clr-integration/deploying-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f530f-115">For more information, see [Deploying CLR Database Objects](../clr-integration/deploying-clr-database-objects.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f530f-116">Per impostazione predefinita, l'esecuzione di codice CLR in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è disattivata.</span><span class="sxs-lookup"><span data-stu-id="f530f-116">The ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to execute CLR code is off by default.</span></span> <span data-ttu-id="f530f-117">È possibile creare, modificare ed eliminare oggetti di database che fanno riferimento a moduli di codice gestito. Tali riferimenti non verranno tuttavia eseguiti in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a meno che non si attivi l' [opzione clr enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) tramite [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f530f-117">You can create, alter and drop database objects that reference managed code modules, but these references will not execute in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unless the [clr enabled Option](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) is enabled using [sp_configure (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql).</span></span>  
  
 <span data-ttu-id="f530f-118">**Per creare, modificare o eliminare un assembly**</span><span class="sxs-lookup"><span data-stu-id="f530f-118">**To create, modify, or drop an assembly**</span></span>  
  
-   [<span data-ttu-id="f530f-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f530f-119">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
-   [<span data-ttu-id="f530f-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f530f-120">ALTER ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-assembly-transact-sql)  
  
-   [<span data-ttu-id="f530f-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f530f-121">DROP ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-assembly-transact-sql)  
  
 <span data-ttu-id="f530f-122">**Per creare una funzione di aggregazione definita dall'utente**</span><span class="sxs-lookup"><span data-stu-id="f530f-122">**To create a user-defined aggregate**</span></span>  
  
-   [<span data-ttu-id="f530f-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f530f-123">CREATE AGGREGATE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-aggregate-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="f530f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f530f-124">See Also</span></span>  
 [<span data-ttu-id="f530f-125">Concetti relativi alla programmazione dell'integrazione con CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="f530f-125">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](../clr-integration/common-language-runtime-clr-integration-programming-concepts.md)  
  
  
