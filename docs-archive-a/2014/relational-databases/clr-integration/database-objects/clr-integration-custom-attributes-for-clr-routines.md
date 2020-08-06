---
title: Attributi personalizzati per routine CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- SqlFacet attribute
- SqlTrigger attribute
- SqlProcedure attribute
- custom attributes [CLR integration]
- SqlUserDefinedAggregate attribute
- attributes [CLR integration]
- SqlMethod attribute
- SqlFunction attribute
- common language runtime [SQL Server], attributes
- SqlUserDefinedTypeAttribute attribute
ms.assetid: 95069d22-b05d-4670-b053-15ee2a664e33
author: rothja
ms.author: jroth
ms.openlocfilehash: 058bbec7f0f1f63fbd96258a0abe7a6c3d543d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623341"
---
# <a name="custom-attributes-for-clr-routines"></a><span data-ttu-id="8d43b-102">Attributi personalizzati per routine CLR</span><span class="sxs-lookup"><span data-stu-id="8d43b-102">Custom Attributes for CLR Routines</span></span>
  <span data-ttu-id="8d43b-103">Gli attributi elencati possono essere applicati alle routine Common Language Runtime (CLR), ai tipi definiti dall'utente e alle aggregazioni definite dall'utente registrate in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8d43b-103">The attributes listed can be applied to common language runtime (CLR) routines, user-defined types, and user-defined aggregates that are registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8d43b-104">Se l'attributo non viene applicato, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assume il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8d43b-104">If the attribute is not applied, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assumes the default value.</span></span> <span data-ttu-id="8d43b-105">Gli attributi elencati vengono definiti nello spazio dei nomi `Microsoft.SqlServer.Server`.</span><span class="sxs-lookup"><span data-stu-id="8d43b-105">The attributes listed are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="the-sqluserdefinedaggregate-attribute"></a><span data-ttu-id="8d43b-106">Attributo SqlUserDefinedAggregate</span><span class="sxs-lookup"><span data-stu-id="8d43b-106">The SqlUserDefinedAggregate Attribute</span></span>  
 <span data-ttu-id="8d43b-107">L'attributo `SqlUserDefinedAggregate` indica che il metodo deve essere registrato come aggregazione definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8d43b-107">The `SqlUserDefinedAggregate` attribute indicates that the method should be registered as a user-defined aggregate.</span></span> <span data-ttu-id="8d43b-108">Ogni aggregazione definita dall'utente deve essere annotata con questo attributo.</span><span class="sxs-lookup"><span data-stu-id="8d43b-108">Every user-defined aggregate must be annotated with this attribute.</span></span>  
  
 <span data-ttu-id="8d43b-109">Per ulteriori informazioni, vedere [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span><span class="sxs-lookup"><span data-stu-id="8d43b-109">For more information, see [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span></span>  
  
## <a name="the-sqlfunction-attribute"></a><span data-ttu-id="8d43b-110">Attributo SqlFunction</span><span class="sxs-lookup"><span data-stu-id="8d43b-110">The SqlFunction Attribute</span></span>  
 <span data-ttu-id="8d43b-111">L'attributo `SqlFunction` indica che il metodo deve essere registrato come funzione, con il set di attributi delle funzioni appropriato.</span><span class="sxs-lookup"><span data-stu-id="8d43b-111">The `SqlFunction` attribute indicates the method should be registered as a function, with the appropriate function attributes set.</span></span>  
  
 <span data-ttu-id="8d43b-112">Per ulteriori informazioni, vedere [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span><span class="sxs-lookup"><span data-stu-id="8d43b-112">For more information, see [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span></span>  
  
## <a name="the-sqlfacet-attribute"></a><span data-ttu-id="8d43b-113">Attributo SqlFacet</span><span class="sxs-lookup"><span data-stu-id="8d43b-113">The SqlFacet Attribute</span></span>  
 <span data-ttu-id="8d43b-114">L'attributo `SqlFacet` viene utilizzato per restituire informazioni sul tipo restituito di un'espressione di tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8d43b-114">The `SqlFacet` attribute is used to return information about the return type of a user-defined type (UDT) expression.</span></span>  
  
 <span data-ttu-id="8d43b-115">Per ulteriori informazioni, vedere [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span><span class="sxs-lookup"><span data-stu-id="8d43b-115">For more information, see [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span></span>  
  
## <a name="the-sqlprocedure-attribute"></a><span data-ttu-id="8d43b-116">Attributo SqlProcedure</span><span class="sxs-lookup"><span data-stu-id="8d43b-116">The SqlProcedure Attribute</span></span>  
 <span data-ttu-id="8d43b-117">L'attributo `SqlProcedure` indica che il metodo deve essere registrato come stored procedure.</span><span class="sxs-lookup"><span data-stu-id="8d43b-117">The `SqlProcedure` attribute indicates the method should be registered as a stored procedure.</span></span> <span data-ttu-id="8d43b-118">Questo attributo viene utilizzato solo da Visual Studio per registrare automaticamente il metodo specificato come stored procedure. Non viene utilizzato da [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8d43b-118">This attribute is used only by Visual Studio to register the specified method as a stored procedure automatically; it is not used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8d43b-119">Per ulteriori informazioni, vedere [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span><span class="sxs-lookup"><span data-stu-id="8d43b-119">For more information, see [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span></span>  
  
## <a name="the-sqltrigger-attribute"></a><span data-ttu-id="8d43b-120">Attributo SqlTrigger</span><span class="sxs-lookup"><span data-stu-id="8d43b-120">The SqlTrigger Attribute</span></span>  
 <span data-ttu-id="8d43b-121">Tramite l'attributo `SqlTrigger` viene indicato che il metodo deve essere registrato come trigger.</span><span class="sxs-lookup"><span data-stu-id="8d43b-121">The `SqlTrigger` attribute indicates the method should be registered as a trigger.</span></span>  
  
 <span data-ttu-id="8d43b-122">Per ulteriori informazioni, vedere [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) e [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span><span class="sxs-lookup"><span data-stu-id="8d43b-122">For more information, see [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) and [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span></span>  
  
## <a name="the-sqluserdefinedtypeattribute"></a><span data-ttu-id="8d43b-123">Attributo SqlUserDefinedTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="8d43b-123">The SqlUserDefinedTypeAttribute</span></span>  
 <span data-ttu-id="8d43b-124">È possibile applicare l'attributo SqlUserDefinedTypeAttribute a una definizione di classe nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8d43b-124">You can apply the SqlUserDefinedTypeAttribute to a class definition in the assembly.</span></span> <span data-ttu-id="8d43b-125">In questo caso, in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] viene creato un tipo definito dall'utente associato alla definizione di classe che include l'attributo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8d43b-125">It causes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to create a user-defined type that is bound to the class definition which has this custom attribute.</span></span>  
  
 <span data-ttu-id="8d43b-126">Per ulteriori informazioni, vedere [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span><span class="sxs-lookup"><span data-stu-id="8d43b-126">For more information, see [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span></span>  
  
## <a name="the-sqlmethod-attribute"></a><span data-ttu-id="8d43b-127">Attributo SqlMethod</span><span class="sxs-lookup"><span data-stu-id="8d43b-127">The SqlMethod Attribute</span></span>  
 <span data-ttu-id="8d43b-128">L'attributo `SqlMethod` viene utilizzato per indicare le proprietà deterministiche e di accesso ai dati di un metodo o di una proprietà in un tipo definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8d43b-128">The `SqlMethod` attribute is used to indicate the determinism and data access properties of a method or a property on a UDT.</span></span>  
  
 <span data-ttu-id="8d43b-129">Per ulteriori informazioni, vedere [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span><span class="sxs-lookup"><span data-stu-id="8d43b-129">For more information, see [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d43b-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d43b-130">See Also</span></span>  
 <span data-ttu-id="8d43b-131">[Funzioni di aggregazione CLR definite dall'utente](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span><span class="sxs-lookup"><span data-stu-id="8d43b-131">[CLR User-Defined Aggregates](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span></span>  
 <span data-ttu-id="8d43b-132">[Funzioni CLR definite dall'utente](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="8d43b-132">[CLR User-Defined Functions](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="8d43b-133">[Tipi CLR definiti dall'utente](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="8d43b-133">[CLR User-Defined Types](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 <span data-ttu-id="8d43b-134">[Stored procedure CLR](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8d43b-134">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="8d43b-135">Trigger CLR</span><span class="sxs-lookup"><span data-stu-id="8d43b-135">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
  
  
