---
title: Progettazione di assembly | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- designing assemblies [SQL Server]
- assemblies [CLR integration], designing
ms.assetid: 9c07f706-6508-41aa-a4d7-56ce354f9061
author: rothja
ms.author: jroth
ms.openlocfilehash: 785ab80a529140a52ec18ef96ccaaeafd03698cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720075"
---
# <a name="designing-assemblies"></a><span data-ttu-id="333a2-102">Progettazione di assembly</span><span class="sxs-lookup"><span data-stu-id="333a2-102">Designing Assemblies</span></span>
  <span data-ttu-id="333a2-103">In questo argomento vengono illustrati alcuni fattori da prendere in considerazione durante la progettazione degli assembly:</span><span class="sxs-lookup"><span data-stu-id="333a2-103">This topic describes the following factors you should consider when you design assemblies:</span></span>  
  
-   <span data-ttu-id="333a2-104">Assemblaggio di assembly</span><span class="sxs-lookup"><span data-stu-id="333a2-104">Packaging assemblies</span></span>  
  
-   <span data-ttu-id="333a2-105">Gestione della sicurezza degli assembly</span><span class="sxs-lookup"><span data-stu-id="333a2-105">Managing assembly security</span></span>  
  
-   <span data-ttu-id="333a2-106">Limitazioni relative agli assembly</span><span class="sxs-lookup"><span data-stu-id="333a2-106">Restrictions on assemblies</span></span>  
  
## <a name="packaging-assemblies"></a><span data-ttu-id="333a2-107">Assemblaggio di assembly</span><span class="sxs-lookup"><span data-stu-id="333a2-107">Packaging Assemblies</span></span>  
 <span data-ttu-id="333a2-108">Le classi e i metodi di un assembly possono contenere funzionalità per più di una routine o un tipo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="333a2-108">An assembly can contain functionality for more than one [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] routine or type in its classes and methods.</span></span> <span data-ttu-id="333a2-109">Nella maggior parte dei casi è opportuno assemblare le funzionalità delle routine che eseguono funzioni correlate all'interno dello stesso assembly, in particolare se le routine condividono classi i cui metodi si chiamano a vicenda.</span><span class="sxs-lookup"><span data-stu-id="333a2-109">Most of the time, it makes sense to package the functionality of routines that perform related functions within the same assembly, especially if these routines share classes whose methods call one another.</span></span> <span data-ttu-id="333a2-110">Ad esempio, le classi che eseguono attività di gestione dell'immissione di dati per trigger CLR (Common Language Runtime) e stored procedure CLR possono essere assemblate nello stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="333a2-110">For example, classes that perform data entry management tasks for common language runtime (CLR) triggers and CLR stored procedures can be packaged in the same assembly.</span></span> <span data-ttu-id="333a2-111">Il motivo di questa scelta è che è più probabile che i metodi di queste classi si chiamino l'un l'altro rispetto ai metodi di attività meno correlate.</span><span class="sxs-lookup"><span data-stu-id="333a2-111">This is because the methods for these classes are more likely to call each other than those of less related tasks.</span></span>  
  
 <span data-ttu-id="333a2-112">Quando si assembla codice in assembly, è opportuno prendere in considerazione i fattori seguenti:</span><span class="sxs-lookup"><span data-stu-id="333a2-112">When you are packaging code into assembly, you should consider the following:</span></span>  
  
-   <span data-ttu-id="333a2-113">I tipi CLR definiti dall'utente e gli indici che dipendono da funzioni CLR definite dall'utente possono provocare la presenza di dati persistenti nel database che dipende dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="333a2-113">CLR user-defined types and indexes that depend on CLR user-defined functions can cause persisted data to be in the database that depends on the assembly.</span></span> <span data-ttu-id="333a2-114">Modificare il codice di un assembly risulta spesso più complesso quando nel database sono presenti dati persistenti che dipendono dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="333a2-114">Modifying the code of an assembly is frequently more complex when there is persisted data that depends on the assembly in the database.</span></span> <span data-ttu-id="333a2-115">È pertanto preferibile separare il codice sul quale si basano le dipendenze dei dati persistenti, ad esempio i tipi definiti dall'utente e gli indici che utilizzano funzioni definite dall'utente, dal codice che non contiene questo tipo di dipendenze.</span><span class="sxs-lookup"><span data-stu-id="333a2-115">Therefore, it is generally better to separate code on which persisted data dependencies rely (such as user-defined types and indexes using user-defined functions) from code that does not have such persisted data dependencies.</span></span> <span data-ttu-id="333a2-116">Per ulteriori informazioni, vedere [implementazione di assembly](assemblies-implementing.md) e [ALTER assembly &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="333a2-116">For more information, see [Implementing Assemblies](assemblies-implementing.md) and [ALTER ASSEMBLY &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-assembly-transact-sql).</span></span>  
  
-   <span data-ttu-id="333a2-117">Se una parte di codice gestito richiede un'autorizzazione di livello superiore, è opportuno inserirla in un assembly separato.</span><span class="sxs-lookup"><span data-stu-id="333a2-117">If a piece of managed code requires higher permission, it is better to separate that code into a separate assembly from code that does not require higher permission.</span></span>  
  
## <a name="managing-assembly-security"></a><span data-ttu-id="333a2-118">Gestione della sicurezza degli assembly</span><span class="sxs-lookup"><span data-stu-id="333a2-118">Managing Assembly Security</span></span>  
 <span data-ttu-id="333a2-119">È possibile controllare l'accesso di un assembly alle risorse protette dalla sicurezza dall'accesso di codice .NET quando esegue codice gestito.</span><span class="sxs-lookup"><span data-stu-id="333a2-119">You can control how much an assembly can access resources protected by .NET Code Access Security when it runs managed code.</span></span> <span data-ttu-id="333a2-120">A questo scopo, quando si crea o modifica l'assembly è necessario specificare uno dei tre set di autorizzazioni disponibili: SAFE, EXTERNAL_ACCESS oppure UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="333a2-120">You do this by specifying one of three permission sets when you create or modify an assembly: SAFE, EXTERNAL_ACCESS, or UNSAFE.</span></span>  
  
### <a name="safe"></a><span data-ttu-id="333a2-121">SAFE</span><span class="sxs-lookup"><span data-stu-id="333a2-121">SAFE</span></span>  
 <span data-ttu-id="333a2-122">SAFE è il set di autorizzazioni predefinito ed è il più restrittivo.</span><span class="sxs-lookup"><span data-stu-id="333a2-122">SAFE is the default permission set and it is the most restrictive.</span></span> <span data-ttu-id="333a2-123">Il codice eseguito da un assembly con autorizzazioni SAFE non può accedere a risorse di sistema esterne, ad esempio file, la rete, variabili di ambiente o il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="333a2-123">Code run by an assembly with SAFE permissions cannot access external system resources such as files, the network, environment variables, or the registry.</span></span> <span data-ttu-id="333a2-124">Il codice SAFE può accedere ai dati dei database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] locali o eseguire calcoli e logiche di business che non comportino l'accesso a risorse esterne ai database locali.</span><span class="sxs-lookup"><span data-stu-id="333a2-124">SAFE code can access data from the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases or perform computations and business logic that do not involve accessing resources outside the local databases.</span></span>  
  
 <span data-ttu-id="333a2-125">Nella maggior parte dei casi gli assembly eseguono attività di calcolo e gestione dei dati senza accedere a risorse esterne a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="333a2-125">Most assemblies perform computation and data management tasks without having to access resources outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="333a2-126">È pertanto consigliabile applicare agli assembly il set di autorizzazioni SAFE.</span><span class="sxs-lookup"><span data-stu-id="333a2-126">Therefore, we recommend SAFE as the assembly permission set.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="333a2-127">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="333a2-127">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="333a2-128">EXTERNAL_ACCESS consente agli assembly di accedere a specifiche risorse di sistema esterne, ad esempio file, reti, servizi Web, variabili di ambiente e il Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="333a2-128">EXTERNAL_ACCESS allows for assemblies to access certain external system resources such as files, networks, Web services, environmental variables, and the registry.</span></span> <span data-ttu-id="333a2-129">Solo gli account di accesso di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] con autorizzazioni EXTERNAL ACCESS possono creare assembly EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="333a2-129">Only [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins with EXTERNAL ACCESS permissions can create EXTERNAL_ACCESS assemblies.</span></span>  
  
 <span data-ttu-id="333a2-130">Gli assembly SAFE ed EXTERNAL_ACCESS possono contenere solo codice effettivamente indipendente dai tipi.</span><span class="sxs-lookup"><span data-stu-id="333a2-130">SAFE and EXTERNAL_ACCESS assemblies can contain only code that is verifiably type-safe.</span></span> <span data-ttu-id="333a2-131">Ciò significa che questi assembly possono accedere alle classi solo tramite punti di accesso ben definiti, validi per la definizione del tipo.</span><span class="sxs-lookup"><span data-stu-id="333a2-131">This means that these assemblies can only access classes through well-defined entry points that are valid for the type definition.</span></span> <span data-ttu-id="333a2-132">Non possono pertanto accedere arbitrariamente a buffer di memoria non di proprietà del codice.</span><span class="sxs-lookup"><span data-stu-id="333a2-132">Therefore, they cannot arbitrarily access memory buffers not owned by the code.</span></span> <span data-ttu-id="333a2-133">Non possono inoltre eseguire operazioni che possono influire in modo negativo sull'affidabilità del processo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="333a2-133">Additionally, they cannot perform operations that might have an adverse effect on the robustness of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="333a2-134">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="333a2-134">UNSAFE</span></span>  
 <span data-ttu-id="333a2-135">Il set di autorizzazioni UNSAFE concede agli assembly libero accesso alle risorse interne ed esterne a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="333a2-135">UNSAFE gives assemblies unrestricted access to resources, both within and outside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="333a2-136">Il codice eseguito da un assembly UNSAFE può chiamare codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="333a2-136">Code that is running from within an UNSAFE assembly can call unmanaged code.</span></span>  
  
 <span data-ttu-id="333a2-137">Specificando UNSAFE si consente inoltre al codice dell'assembly di eseguire operazioni considerate non indipendenti dai tipi da CLR Verifier.</span><span class="sxs-lookup"><span data-stu-id="333a2-137">Also, specifying UNSAFE allows for the code in the assembly to perform operations that are considered type-unsafe by the CLR verifier.</span></span> <span data-ttu-id="333a2-138">Tali operazioni potrebbero accedere ai buffer di memoria nello spazio di processo di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in modo incontrollato.</span><span class="sxs-lookup"><span data-stu-id="333a2-138">These operations can potentially access memory buffers in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process space in an uncontrolled manner.</span></span> <span data-ttu-id="333a2-139">Gli assembly UNSAFE possono anche compromettere il sistema di sicurezza di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o del CLR.</span><span class="sxs-lookup"><span data-stu-id="333a2-139">UNSAFE assemblies can also potentially subvert the security system of either [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] or the common language runtime.</span></span> <span data-ttu-id="333a2-140">Si consiglia di concedere le autorizzazioni UNSAFE solo ad assembly assolutamente attendibili, creati da sviluppatori o amministratori esperti.</span><span class="sxs-lookup"><span data-stu-id="333a2-140">UNSAFE permissions should be granted only to highly trusted assemblies by experienced developers or administrators.</span></span> <span data-ttu-id="333a2-141">Solo i membri del ruolo predefinito del server **sysadmin** possono creare assembly UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="333a2-141">Only members of the **sysadmin** fixed server role can create UNSAFE assemblies.</span></span>  
  
## <a name="restrictions-on-assemblies"></a><span data-ttu-id="333a2-142">Limitazioni relative agli assembly</span><span class="sxs-lookup"><span data-stu-id="333a2-142">Restrictions on Assemblies</span></span>  
 <span data-ttu-id="333a2-143">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] vengono imposte restrizioni sul codice gestito negli assembly per garantirne l'affidabilità e la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="333a2-143">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] puts certain restrictions on managed code in assemblies to make sure that they can run in a reliable and scalable manner.</span></span> <span data-ttu-id="333a2-144">Alcune operazioni potenzialmente in grado di compromettere l'affidabilità del server non sono consentite negli assembly SAFE ed EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="333a2-144">This means that certain operations that can compromise the robustness of the server are not permitted in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
### <a name="disallowed-custom-attributes"></a><span data-ttu-id="333a2-145">Attributi personalizzati non consentiti</span><span class="sxs-lookup"><span data-stu-id="333a2-145">Disallowed Custom Attributes</span></span>  
 <span data-ttu-id="333a2-146">Non è possibile annotare gli assembly con gli attributi personalizzati seguenti:</span><span class="sxs-lookup"><span data-stu-id="333a2-146">Assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.ContextStaticAttribute  
System.MTAThreadAttribute  
System.Runtime.CompilerServices.MethodImplAttribute  
System.Runtime.CompilerServices.CompilationRelaxationsAttribute  
System.Runtime.Remoting.Contexts.ContextAttribute  
System.Runtime.Remoting.Contexts.SynchronizationAttribute  
System.Runtime.InteropServices.DllImportAttribute   
System.Security.Permissions.CodeAccessSecurityAttribute  
System.STAThreadAttribute  
System.ThreadStaticAttribute  
```  
  
 <span data-ttu-id="333a2-147">Non è inoltre possibile annotare gli assembly SAFE ed EXTERNAL_ACCESS con gli attributi personalizzati seguenti:</span><span class="sxs-lookup"><span data-stu-id="333a2-147">Additionally, SAFE and EXTERNAL_ACCESS assemblies cannot be annotated with the following custom attributes:</span></span>  
  
```  
System.Security.SuppressUnmanagedCodeSecurityAttribute  
System.Security.UnverifiableCodeAttribute  
```  
  
### <a name="disallowed-net-framework-apis"></a><span data-ttu-id="333a2-148">API .NET Framework non consentite</span><span class="sxs-lookup"><span data-stu-id="333a2-148">Disallowed .NET Framework APIs</span></span>  
 <span data-ttu-id="333a2-149">Le [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API annotate con uno dei **HostProtectionAttributes** non consentiti non possono essere chiamate da assembly SAFE e EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="333a2-149">Any [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] API that is annotated with one of the disallowed **HostProtectionAttributes** cannot be called from SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
```  
eSelfAffectingProcessMgmt  
eSelfAffectingThreading  
eSynchronization  
eSharedState   
eExternalProcessMgmt  
eExternalThreading  
eSecurityInfrastructure  
eMayLeakOnAbort  
eUI  
```  
  
### <a name="supported-net-framework-assemblies"></a><span data-ttu-id="333a2-150">Assembly .NET Framework supportati</span><span class="sxs-lookup"><span data-stu-id="333a2-150">Supported .NET Framework Assemblies</span></span>  
 <span data-ttu-id="333a2-151">Gli assembly cui fa riferimento l'assembly personalizzato devono essere caricati in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilizzando CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="333a2-151">Any assembly that is referenced by your custom assembly must be loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using CREATE ASSEMBLY.</span></span> <span data-ttu-id="333a2-152">Gli assembly [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] seguenti sono già caricati in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e, pertanto, possono essere utilizzati come riferimento dagli assembly personalizzati senza richiedere l'utilizzo di CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="333a2-152">The following [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] assemblies are already loaded into [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and, therefore, can be referenced by custom assemblies without having to use CREATE ASSEMBLY.</span></span>  
  
```  
custommarshallers.dll  
Microsoft.visualbasic.dll  
Microsoft.visualc.dll  
mscorlib.dll  
system.data.dll  
System.Data.SqlXml.dll  
system.dll  
system.security.dll  
system.web.services.dll  
system.xml.dll  
System.Transactions  
System.Data.OracleClient  
System.Configuration  
```  
  
## <a name="see-also"></a><span data-ttu-id="333a2-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="333a2-153">See Also</span></span>  
 <span data-ttu-id="333a2-154">[Assembly &#40;motore di database&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span><span class="sxs-lookup"><span data-stu-id="333a2-154">[Assemblies &#40;Database Engine&#41;](../../relational-databases/clr-integration/assemblies-database-engine.md) </span></span>  
 [<span data-ttu-id="333a2-155">Sicurezza per l'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="333a2-155">CLR Integration Security</span></span>](security/clr-integration-security.md)  
  
  
