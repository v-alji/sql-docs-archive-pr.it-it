---
title: Assembly (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- assemblies [CLR integration]
- assemblies [CLR integration], about assemblies
- managed code [SQL Server], assemblies
ms.assetid: 4b146437-3061-47f6-9e8c-26eeea10b54e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7edb18ccfa9954fe52093f87948f956c2eacc1b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720081"
---
# <a name="assemblies-database-engine"></a><span data-ttu-id="1fbd8-102">Assembly (Motore di database)</span><span class="sxs-lookup"><span data-stu-id="1fbd8-102">Assemblies (Database Engine)</span></span>
  <span data-ttu-id="1fbd8-103">Gli argomenti di questa sezione includono informazioni utili per comprendere, progettare e implementare assembly.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-103">The topics in this section provide information to help you understand, design, and implement assemblies.</span></span>  
  
 <span data-ttu-id="1fbd8-104">Gli assembly sono file DLL utilizzati in un'istanza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] per distribuire funzioni, stored procedure, trigger, funzioni di aggregazione definite dall'utente e tipi definiti dall'utente scritti in uno dei linguaggi di codice gestito ospitati dal [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR), anziché in [!INCLUDE[tsql](../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1fbd8-104">Assemblies are DLL files used in an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to deploy functions, stored procedures, triggers, user-defined aggregates, and user-defined types that are written in one of the managed code languages hosted by the [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime (CLR), instead of in [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="1fbd8-105">Un assembly di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] è un oggetto che fa riferimento a un modulo di applicazione gestito (file con estensione dll) creato nel linguaggio CLR di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1fbd8-105">An assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is an object that references a managed application module (.dll file) that was created in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] common language runtime.</span></span> <span data-ttu-id="1fbd8-106">Un assembly contiene i metadati della classe e codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-106">An assembly contains class metadata and managed code.</span></span> <span data-ttu-id="1fbd8-107">Il caricamento di un assembly in un'istanza di SQL Server è il primo passaggio da eseguire per creare uno degli oggetti di database seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fbd8-107">Uploading an assembly to an instance of SQL Server is the first step toward creating any of the following database objects:</span></span>  
  
-   <span data-ttu-id="1fbd8-108">Funzioni CLR.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-108">CLR functions.</span></span> <span data-ttu-id="1fbd8-109">Per altre informazioni, vedere [create CLR Functions](../user-defined-functions/create-clr-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-109">For more information, see [Create CLR Functions](../user-defined-functions/create-clr-functions.md).</span></span>  
  
-   <span data-ttu-id="1fbd8-110">Stored procedure CLR.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-110">CLR stored procedures.</span></span> <span data-ttu-id="1fbd8-111">Per ulteriori informazioni, vedere [stored procedure CLR](../../database-engine/dev-guide/clr-stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-111">For more information, see [CLR Stored Procedures](../../database-engine/dev-guide/clr-stored-procedures.md).</span></span>  
  
-   <span data-ttu-id="1fbd8-112">Trigger CLR.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-112">CLR triggers.</span></span> <span data-ttu-id="1fbd8-113">Per altre informazioni, vedere [create CLR Triggers](../triggers/create-clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-113">For more information, see [Create CLR Triggers](../triggers/create-clr-triggers.md).</span></span>  
  
-   <span data-ttu-id="1fbd8-114">Funzioni di aggregazione definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-114">User-defined aggregate functions.</span></span> <span data-ttu-id="1fbd8-115">Per altre informazioni, vedere [creare funzioni di aggregazione definite dall'utente](../user-defined-functions/create-user-defined-aggregates.md).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-115">For more information, see [Create User-defined Aggregates](../user-defined-functions/create-user-defined-aggregates.md).</span></span>  
  
-   <span data-ttu-id="1fbd8-116">Tipi definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-116">User-defined types.</span></span> <span data-ttu-id="1fbd8-117">Per altre informazioni, vedere [Uso dei tipi definiti dall'utente](../native-client/features/using-user-defined-types.md).</span><span class="sxs-lookup"><span data-stu-id="1fbd8-117">For more information, see [Using User-Defined Types](../native-client/features/using-user-defined-types.md).</span></span>  
  
 <span data-ttu-id="1fbd8-118">Gli assembly svolgono le funzioni seguenti in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="1fbd8-118">Assemblies perform the following functions in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="1fbd8-119">Includono il codice gestito che esegue le funzionalità di uno o più degli oggetti di database CLR elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-119">Contain the managed code that runs the functionality of one or more of the CLR database objects previously listed.</span></span>  
  
-   <span data-ttu-id="1fbd8-120">Contengono i metadati che includono il numero di versione e la lingua dell'assembly, una chiave pubblica facoltativa che identifica l'elenco delle classi dell'assembly, i metodi definiti nell'assembly e l'architettura del processore dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-120">Contain metadata that includes the version number and culture of the assembly, an optional public key that uniquely identifies the list of classes of the assembly, the methods that are defined in the assembly, and the processor architecture of the assembly.</span></span>  
  
-   <span data-ttu-id="1fbd8-121">Gestiscono il livello di accesso del codice gestito alle risorse esterne tramite l'impostazione delle autorizzazioni di accesso per il codice.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-121">Manage the degree to which managed code can access outside resources by regulating code access permissions.</span></span>  
  
-   <span data-ttu-id="1fbd8-122">Includono i metadati relativi alle dipendenze da altri assembly a cui viene fatto riferimento nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-122">Contain metadata about dependencies on other assemblies that are referenced by the assembly.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1fbd8-123">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1fbd8-123">In This Section</span></span>  
  
|<span data-ttu-id="1fbd8-124">Argomento</span><span class="sxs-lookup"><span data-stu-id="1fbd8-124">Topic</span></span>|<span data-ttu-id="1fbd8-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1fbd8-125">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1fbd8-126">Progettazione di assembly</span><span class="sxs-lookup"><span data-stu-id="1fbd8-126">Designing Assemblies</span></span>](assemblies-designing.md)|<span data-ttu-id="1fbd8-127">Descrive gli elementi da tenere in considerazione prima di creare un assembly,</span><span class="sxs-lookup"><span data-stu-id="1fbd8-127">Explains what you have to consider before creating an assembly.</span></span> <span data-ttu-id="1fbd8-128">che includono l'assemblaggio degli assembly, le autorizzazioni di accesso per il codice e altre restrizioni.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-128">This includes packaging assemblies, code access permissions, and other restrictions.</span></span>|  
|[<span data-ttu-id="1fbd8-129">Implementazione di assembly</span><span class="sxs-lookup"><span data-stu-id="1fbd8-129">Implementing Assemblies</span></span>](assemblies-implementing.md)|<span data-ttu-id="1fbd8-130">Illustra come creare ed eliminare gli assembly, come e quando modificare gli assembly e come recuperare i metadati relativi agli assembly.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-130">Explains how to create and drop assemblies, how and when to modify assemblies, and how to retrieve metadata about assemblies.</span></span>|  
|[<span data-ttu-id="1fbd8-131">Recupero di informazioni sugli assembly</span><span class="sxs-lookup"><span data-stu-id="1fbd8-131">Getting Information About Assemblies</span></span>](assemblies-getting-information.md)|<span data-ttu-id="1fbd8-132">Elenca le viste del catalogo e le funzioni sulle quali è possibile eseguire query relative agli assembly.</span><span class="sxs-lookup"><span data-stu-id="1fbd8-132">Lists the catalog views and functions that can be queried for metadata about assemblies.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1fbd8-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fbd8-133">See Also</span></span>  
 [<span data-ttu-id="1fbd8-134">Concetti relativi alla programmazione dell'integrazione con CLR &#40;Common Language Runtime&#41;</span><span class="sxs-lookup"><span data-stu-id="1fbd8-134">Common Language Runtime &#40;CLR&#41; Integration Programming Concepts</span></span>](common-language-runtime-clr-integration-programming-concepts.md)  
  
  
