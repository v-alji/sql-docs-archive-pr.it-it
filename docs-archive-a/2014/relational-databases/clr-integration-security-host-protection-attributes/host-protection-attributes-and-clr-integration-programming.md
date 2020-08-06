---
title: Attributi di protezione host e programmazione dell'integrazione con CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- HostProtectionAttribute [CLR integration]
- common language runtime [SQL Server], host protection attributes
- disallowed types and members [CLR integration]
- common language runtime [SQL Server], disallowed types and members
- HPAs [CLR integration]
ms.assetid: 268078df-63ca-4c03-a8e7-7108bcea9697
author: rothja
ms.author: jroth
ms.openlocfilehash: 16ca1e4734e66b0eca85523764739e8f8b32634a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720082"
---
# <a name="host-protection-attributes-and-clr-integration-programming"></a><span data-ttu-id="e1c53-102">Attributi di protezione host e programmazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="e1c53-102">Host Protection Attributes and CLR Integration Programming</span></span>
  <span data-ttu-id="e1c53-103">Common Language Runtime (CLR) fornisce un meccanismo di annotazione delle API gestite che fanno parte di .NET Framework con determinati attributi che possono interessare un host di CLR, ad esempio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], a partire da [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1c53-103">The common language runtime (CLR) provides a mechanism to annotate managed application programming interfaces (APIs) that are part of the .NET Framework with certain attributes that may be of interest to a host of the CLR, such as [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], beginning with [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="e1c53-104">Di seguito sono riportati alcuni esempi di attributi di protezione host:</span><span class="sxs-lookup"><span data-stu-id="e1c53-104">Examples of such host protection attributes (HPAs) include:</span></span>  
  
-   <span data-ttu-id="e1c53-105">`SharedState`, che indica se l'API espone la possibilità di creare o gestire uno stato condiviso, ad esempio campi classe statici.</span><span class="sxs-lookup"><span data-stu-id="e1c53-105">`SharedState`, which indicates whether the API exposes the ability to create or manage shared state (for example, static class fields).</span></span>  
  
-   <span data-ttu-id="e1c53-106">`Synchronization`, che indica se l'API espone la possibilità di eseguire la sincronizzazione tra thread.</span><span class="sxs-lookup"><span data-stu-id="e1c53-106">`Synchronization`, which indicates whether the API exposes the ability to perform synchronization between threads.</span></span>  
  
-   <span data-ttu-id="e1c53-107">`ExternalProcessMgmt`, che indica se l'API espone una modalità per controllare il processo host.</span><span class="sxs-lookup"><span data-stu-id="e1c53-107">`ExternalProcessMgmt`, which indicates whether the API exposes a way to control the host process.</span></span>  
  
 <span data-ttu-id="e1c53-108">Sulla base di tali attributi, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specifica un elenco di attributi di protezione host non consentiti nell'ambiente host attraverso la sicurezza da accesso di codice.</span><span class="sxs-lookup"><span data-stu-id="e1c53-108">Given these attributes, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] specifies a list of HPAs that are disallowed in the hosted environment through code access security (CAS).</span></span> <span data-ttu-id="e1c53-109">I requisiti della protezione dall'accesso di codice sono specificati da uno dei tre set di autorizzazioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: `SAFE`, `EXTERNAL_ACCESS` o `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="e1c53-109">The CAS requirements are specified by one of three [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permission sets: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="e1c53-110">Uno dei tre livelli di sicurezza viene specificato quando l'assembly viene registrato nel server, mediante l'istruzione `CREATE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="e1c53-110">One of these three security levels is specified when the assembly is registered on the server, using the `CREATE ASSEMBLY` statement.</span></span> <span data-ttu-id="e1c53-111">Durante l'esecuzione di codice nell'ambito dei set di autorizzazioni `SAFE` o `EXTERNAL_ACCESS`, è necessario evitare alcuni tipi o membri a cui è applicato l'attributo `System.Security.Permissions.HostProtectionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="e1c53-111">Code executing within the `SAFE` or `EXTERNAL_ACCESS` permission sets must avoid certain types or members that have the `System.Security.Permissions.HostProtectionAttribute` attribute applied.</span></span> <span data-ttu-id="e1c53-112">Per ulteriori informazioni, vedere [creazione di un assembly](../clr-integration/assemblies/creating-an-assembly.md) e [restrizioni del modello di programmazione dell'integrazione CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="e1c53-112">For more information, see [Creating an Assembly](../clr-integration/assemblies/creating-an-assembly.md) and [CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md).</span></span>  
  
 <span data-ttu-id="e1c53-113">`HostProtectionAttribute` rappresenta più una modalità per migliorare l'affidabilità che un'autorizzazione di sicurezza, in quanto identifica i costrutti di codice specifici, tipi o metodi, che possono essere disattivati dall'host.</span><span class="sxs-lookup"><span data-stu-id="e1c53-113">The `HostProtectionAttribute` is not a security permission as much as a way to improve reliability, in that it identifies specific code constructs, either types or methods, that the host may disallow.</span></span> <span data-ttu-id="e1c53-114">L'utilizzo di `HostProtectionAttribute` impone un modello di programmazione che consente di migliorare la stabilità dell'host.</span><span class="sxs-lookup"><span data-stu-id="e1c53-114">The use of the `HostProtectionAttribute` enforces a programming model that helps protect the stability of the host.</span></span>  
  
## <a name="host-protection-attributes"></a><span data-ttu-id="e1c53-115">Attributi di protezione host</span><span class="sxs-lookup"><span data-stu-id="e1c53-115">Host Protection Attributes</span></span>  
 <span data-ttu-id="e1c53-116">Gli attributi di protezione host identificano i tipi o i membri non inclusi nel modello di programmazione host e rappresentano i livelli di pericolo per l'affidabilità, riportati di seguito in ordine crescente di gravità:</span><span class="sxs-lookup"><span data-stu-id="e1c53-116">HPAs identify types or members that do not fit the host programming model and represent the following increasing levels of reliability threat:</span></span>  
  
-   <span data-ttu-id="e1c53-117">Sono altrimenti innocui.</span><span class="sxs-lookup"><span data-stu-id="e1c53-117">Are otherwise benign.</span></span>  
  
-   <span data-ttu-id="e1c53-118">Possono determinare la destabilizzazione del codice utente gestito dal server.</span><span class="sxs-lookup"><span data-stu-id="e1c53-118">Could lead to destabilization of server-managed user code.</span></span>  
  
-   <span data-ttu-id="e1c53-119">Possono determinare la destabilizzazione del processo del server stesso.</span><span class="sxs-lookup"><span data-stu-id="e1c53-119">Could lead to destabilization of the server process itself.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="e1c53-120">non consente l'utilizzo di un tipo o di un membro che dispone di un oggetto `HostProtectionAttribute` che specifica un' `System.Security.Permissions.HostProtectionResource` enumerazione con un valore di `ExternalProcessMgmt` , `ExternalThreading` , `MayLeakOnAbort` , `SecurityInfrastructure` , `SelfAffectingProcessMgmnt` , `SelfAffectingThreading` , `SharedState` , `Synchronization` o `UI` .</span><span class="sxs-lookup"><span data-stu-id="e1c53-120">disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, `SharedState`, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="e1c53-121">In questo modo si impedisce agli assembly di chiamare membri che attivano la condivisione dello stato, eseguono la sincronizzazione, possono determinare una perdita di risorse al termine del processo o compromettere l'integrità del processo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1c53-121">This prevents the assemblies from calling members that enable sharing state, perform synchronization, might cause a resource leak on termination, or affect the integrity of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="disallowed-types-and-members"></a><span data-ttu-id="e1c53-122">Tipi e membri non consentiti</span><span class="sxs-lookup"><span data-stu-id="e1c53-122">Disallowed Types and Members</span></span>  
 <span data-ttu-id="e1c53-123">Negli argomenti riportati di seguito vengono identificati tipi e membri i cui valori di `HostProtectionResource` non sono consentiti da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1c53-123">The following topics identify types and members whose `HostProtectionResource` values are disallowed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e1c53-124">Gli elenchi presenti in questi argomenti sono stati generati dagli assembly supportati.</span><span class="sxs-lookup"><span data-stu-id="e1c53-124">The lists in these topics were generated from the supported assemblies.</span></span>  <span data-ttu-id="e1c53-125">Per ulteriori informazioni, vedere [supported .NET Framework libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="e1c53-125">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1c53-126">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e1c53-126">In This Section</span></span>  
 [<span data-ttu-id="e1c53-127">Tipi e membri non consentiti in Microsoft.VisualBasic.dll</span><span class="sxs-lookup"><span data-stu-id="e1c53-127">Disallowed Types and Members in Microsoft.VisualBasic.dll</span></span>](disallowed-types-and-members-in-microsoft-visualbasic-dll.md)  
 <span data-ttu-id="e1c53-128">Vengono elencati i tipi e i membri di Microsoft.VisualBasic.dll, i cui valori degli attributi di protezione host non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1c53-128">Lists the types and members in Microsoft.VisualBasic.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="e1c53-129">Tipi e membri non consentiti in mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="e1c53-129">Disallowed Types and Members in mscorlib.dll</span></span>](disallowed-types-and-members-in-mscorlib-dll.md)  
 <span data-ttu-id="e1c53-130">Elenca i tipi e i membri in mscorlib.dll, i cui valori degli attributi di protezione host non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1c53-130">Lists the types and members in mscorlib.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="e1c53-131">Tipi e membri non consentiti in System.dll</span><span class="sxs-lookup"><span data-stu-id="e1c53-131">Disallowed Types and Members in System.dll</span></span>](disallowed-types-and-members-in-system-dll.md)  
 <span data-ttu-id="e1c53-132">Elenca i tipi e i membri in System.dll, i cui valori degli attributi di protezione host non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1c53-132">Lists the types and members in System.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="e1c53-133">Tipi e membri non consentiti in System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="e1c53-133">Disallowed Types and Members in System.Data.dll</span></span>](disallowed-types-and-members-in-system-data-dll.md)  
 <span data-ttu-id="e1c53-134">Elenca i tipi e i membri in System.Data.dll, i cui valori degli attributi di protezione host non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1c53-134">Lists the types and members in System.Data.dll whose HPA values are disallowed.</span></span>  
  
 [<span data-ttu-id="e1c53-135">Tipi e membri non consentiti in System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e1c53-135">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
 <span data-ttu-id="e1c53-136">Elenca i tipi e i membri in System.Core.dll, i cui valori degli attributi di protezione host non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1c53-136">Lists the types and members in System.Core.dll whose HPA values are disallowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c53-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1c53-137">See Also</span></span>  
 <span data-ttu-id="e1c53-138">[Sicurezza dall'accesso di codice per l'integrazione con CLR](../clr-integration/security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="e1c53-138">[CLR Integration Code Access Security](../clr-integration/security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="e1c53-139">[Restrizioni del modello di programmazione dell'integrazione con CLR](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span><span class="sxs-lookup"><span data-stu-id="e1c53-139">[CLR Integration Programming Model Restrictions](../clr-integration/database-objects/clr-integration-programming-model-restrictions.md) </span></span>  
 [<span data-ttu-id="e1c53-140">Creazione di un assembly</span><span class="sxs-lookup"><span data-stu-id="e1c53-140">Creating an Assembly</span></span>](../clr-integration/assemblies/creating-an-assembly.md)  
  
  
