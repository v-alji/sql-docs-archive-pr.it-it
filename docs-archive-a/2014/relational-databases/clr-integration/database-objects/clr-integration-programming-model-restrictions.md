---
title: Restrizioni del modello di programmazione dell'integrazione con CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], programming model restrictions
- assemblies [CLR integration], CREATE ASSEMBLY checks
- programming model restrictions [CLR integration]
- assemblies [CLR integration], runtime checks
ms.assetid: 2446afc2-9d21-42d3-9847-7733d3074de9
author: rothja
ms.author: jroth
ms.openlocfilehash: 01a32e1460ad9c49061b39b1bdc419c7cd2f1342
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623339"
---
# <a name="clr-integration-programming-model-restrictions"></a><span data-ttu-id="5933d-102">Restrizioni relative al modello di programmazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="5933d-102">CLR Integration Programming Model Restrictions</span></span>
  <span data-ttu-id="5933d-103">Quando si compila un stored procedure gestito o un altro oggetto di database gestito, vengono eseguiti alcuni controlli del codice eseguendo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] controlli sull'assembly del codice gestito quando viene registrato per la prima volta nel database, usando l' `CREATE ASSEMBLY` istruzione e anche in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5933d-103">When you are building a managed stored procedure or other managed database object, there are certain code checks performed by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs checks on the managed code assembly when it is first registered in the database, using the `CREATE ASSEMBLY` statement, and also at runtime.</span></span> <span data-ttu-id="5933d-104">Il controllo del codice gestito viene effettuato anche in fase di esecuzione in quanto è possibile che in un assembly siano presenti percorsi di codice mai raggiunti in questa fase.</span><span class="sxs-lookup"><span data-stu-id="5933d-104">The managed code is also checked at runtime because in an assembly there may be code paths that may never actually be reached at runtime.</span></span>  <span data-ttu-id="5933d-105">Tale controllo offre quindi la flessibilità necessaria per registrare soprattutto assembly di terze parti, in modo da evitare che un assembly venga bloccato in presenza di codice considerato poco sicuro, progettato per essere eseguito in un ambiente client, ma mai nel CLR hosted.</span><span class="sxs-lookup"><span data-stu-id="5933d-105">This provides flexibility for registering third party assemblies, especially, so that an assembly wouldn't be blocked where there is 'unsafe' code designed to run in a client environment but would never be executed in the hosted CLR.</span></span> <span data-ttu-id="5933d-106">I requisiti che il codice gestito deve soddisfare variano a seconda che l'assembly sia registrato come `SAFE` , `EXTERNAL_ACCESS` o `UNSAFE` , `SAFE` sia il più restrittivo e sia elencato di seguito.</span><span class="sxs-lookup"><span data-stu-id="5933d-106">The requirements that the managed code must meet depend on whether the assembly is registered as `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`, `SAFE` being the strictest, and are listed below.</span></span>  
  
 <span data-ttu-id="5933d-107">Oltre alle restrizioni inserite negli assembly del codice gestito, vengono concesse anche delle autorizzazioni di sicurezza da accesso di codice.</span><span class="sxs-lookup"><span data-stu-id="5933d-107">In addition to restrictions being placed on the managed code assemblies, there are also code security permissions that are granted.</span></span> <span data-ttu-id="5933d-108">Common Language Runtime (CLR) supporta un modello di sicurezza definito sicurezza dall'accesso di codice per il codice gestito</span><span class="sxs-lookup"><span data-stu-id="5933d-108">The common language runtime (CLR) supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="5933d-109">che prevede che le autorizzazioni vengano concesse agli assembly in base all'identità del codice.</span><span class="sxs-lookup"><span data-stu-id="5933d-109">In this model, permissions are granted to assemblies based on the identity of the code.</span></span> <span data-ttu-id="5933d-110">Gli assembly `SAFE`, `EXTERNAL_ACCESS` e `UNSAFE` presentano autorizzazioni di protezione dall'accesso di codice diverse.</span><span class="sxs-lookup"><span data-stu-id="5933d-110">`SAFE`, `EXTERNAL_ACCESS`, and `UNSAFE` assemblies have different CAS permissions.</span></span> <span data-ttu-id="5933d-111">Per altre informazioni, vedere [sicurezza dall'accesso di codice per l'integrazione con CLR](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="5933d-111">For more information, see [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="create-assembly-checks"></a><span data-ttu-id="5933d-112">Controlli CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="5933d-112">CREATE ASSEMBLY Checks</span></span>  
 <span data-ttu-id="5933d-113">Durante l'esecuzione dell'istruzione `CREATE ASSEMBLY`, per ogni livello di sicurezza vengono eseguiti i controlli seguenti.</span><span class="sxs-lookup"><span data-stu-id="5933d-113">When the `CREATE ASSEMBLY` statement is run, the following checks are performed for each security level.</span></span>  <span data-ttu-id="5933d-114">Se un controllo non riesce, non è possibile completare l'esecuzione di `CREATE ASSEMBLY` e viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="5933d-114">If any check fails, `CREATE ASSEMBLY` will fail with an error message.</span></span>  
  
### <a name="global-any-security-level"></a><span data-ttu-id="5933d-115">Globale (qualsiasi livello di sicurezza)</span><span class="sxs-lookup"><span data-stu-id="5933d-115">Global (any security level)</span></span>  
 <span data-ttu-id="5933d-116">Tutti gli assembly a cui si fa riferimento devono soddisfare uno o più dei criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5933d-116">All referenced assemblies must meet one or more of the following criteria:</span></span>  
  
-   <span data-ttu-id="5933d-117">L'assembly è già registrato nel database.</span><span class="sxs-lookup"><span data-stu-id="5933d-117">The assembly is already registered in the database.</span></span>  
  
-   <span data-ttu-id="5933d-118">L'assembly è uno degli assembly supportati.</span><span class="sxs-lookup"><span data-stu-id="5933d-118">The assembly is one of the supported assemblies.</span></span> <span data-ttu-id="5933d-119">Per ulteriori informazioni, vedere [supported .NET Framework libraries](supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="5933d-119">For more information, see [Supported .NET Framework Libraries](supported-net-framework-libraries.md).</span></span>  
  
-   <span data-ttu-id="5933d-120">Si sta utilizzando `CREATE ASSEMBLY FROM` \* \<location> \* e tutti gli assembly a cui viene fatto riferimento e le relative dipendenze sono disponibili in *\<location>* .</span><span class="sxs-lookup"><span data-stu-id="5933d-120">You are using `CREATE ASSEMBLY FROM`*\<location>,* and all the referenced assemblies and their dependencies are available in *\<location>*.</span></span>  
  
-   <span data-ttu-id="5933d-121">Si sta utilizzando `CREATE ASSEMBLY FROM` \* \<bytes ...> \* e tutti i riferimenti vengono specificati tramite byte separati da spazi.</span><span class="sxs-lookup"><span data-stu-id="5933d-121">You are using `CREATE ASSEMBLY FROM`*\<bytes ...>,* and all the references are specified via space separated bytes.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="5933d-122">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="5933d-122">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="5933d-123">Tutti gli assembly `EXTERNAL_ACCESS` devono soddisfare i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5933d-123">All `EXTERNAL_ACCESS` assemblies must meet the following criteria:</span></span>  
  
-   <span data-ttu-id="5933d-124">I campi statici non vengono utilizzati per archiviare informazioni.</span><span class="sxs-lookup"><span data-stu-id="5933d-124">Static fields are not used to store information.</span></span> <span data-ttu-id="5933d-125">Sono consentiti campi statici di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5933d-125">Read-only static fields are allowed.</span></span>  
  
-   <span data-ttu-id="5933d-126">Il test di PEVerify viene superato.</span><span class="sxs-lookup"><span data-stu-id="5933d-126">PEVerify test is passed.</span></span> <span data-ttu-id="5933d-127">Lo strumento PEVerify (peverify.exe) che verifica che il codice MSIL e i metadati associati soddisfino i requisiti di indipendenza dai tipi, viene fornito insieme a .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="5933d-127">The PEVerify tool (peverify.exe), which checks that the MSIL code and associated metadata meet type safety requirements, is provided with the .NET Framework SDK.</span></span>  
  
-   <span data-ttu-id="5933d-128">La sincronizzazione, ad esempio con la classe `SynchronizationAttribute`, non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="5933d-128">Synchronization, for example with the `SynchronizationAttribute` class, is not used.</span></span>  
  
-   <span data-ttu-id="5933d-129">I metodi del finalizzatore non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="5933d-129">Finalizer methods are not used.</span></span>  
  
 <span data-ttu-id="5933d-130">Gli attributi personalizzati seguenti non sono consentiti negli assembly `EXTERNAL_ACCESS`:</span><span class="sxs-lookup"><span data-stu-id="5933d-130">The following custom attributes are disallowed in `EXTERNAL_ACCESS` assemblies:</span></span>  
  
-   <span data-ttu-id="5933d-131">System.ContextStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-131">System.ContextStaticAttribute</span></span>  
  
-   <span data-ttu-id="5933d-132">System.MTAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-132">System.MTAThreadAttribute</span></span>  
  
-   <span data-ttu-id="5933d-133">System.Runtime.CompilerServices.MethodImplAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-133">System.Runtime.CompilerServices.MethodImplAttribute</span></span>  
  
-   <span data-ttu-id="5933d-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-134">System.Runtime.CompilerServices.CompilationRelaxationsAttribute</span></span>  
  
-   <span data-ttu-id="5933d-135">System.Runtime.Remoting.Contexts.ContextAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-135">System.Runtime.Remoting.Contexts.ContextAttribute</span></span>  
  
-   <span data-ttu-id="5933d-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-136">System.Runtime.Remoting.Contexts.SynchronizationAttribute</span></span>  
  
-   <span data-ttu-id="5933d-137">System.Runtime.InteropServices.DllImportAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-137">System.Runtime.InteropServices.DllImportAttribute</span></span>  
  
-   <span data-ttu-id="5933d-138">System.Security.Permissions.CodeAccessSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-138">System.Security.Permissions.CodeAccessSecurityAttribute</span></span>  
  
-   <span data-ttu-id="5933d-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-139">System.Security.SuppressUnmanagedCodeSecurityAttribute</span></span>  
  
-   <span data-ttu-id="5933d-140">System.Security.UnverifiableCodeAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-140">System.Security.UnverifiableCodeAttribute</span></span>  
  
-   <span data-ttu-id="5933d-141">System.STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-141">System.STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="5933d-142">System.ThreadStaticAttribute</span><span class="sxs-lookup"><span data-stu-id="5933d-142">System.ThreadStaticAttribute</span></span>  
  
### <a name="safe"></a><span data-ttu-id="5933d-143">SAFE</span><span class="sxs-lookup"><span data-stu-id="5933d-143">SAFE</span></span>  
  
-   <span data-ttu-id="5933d-144">Tutte le condizioni dell'assembly `EXTERNAL_ACCESS` vengono controllate.</span><span class="sxs-lookup"><span data-stu-id="5933d-144">All `EXTERNAL_ACCESS` assembly conditions are checked.</span></span>  
  
## <a name="runtime-checks"></a><span data-ttu-id="5933d-145">Controlli runtime</span><span class="sxs-lookup"><span data-stu-id="5933d-145">Runtime Checks</span></span>  
 <span data-ttu-id="5933d-146">In fase di esecuzione l'assembly del codice viene esaminato per verificare la presenza delle condizioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="5933d-146">At runtime, the code assembly is checked for the following conditions.</span></span> <span data-ttu-id="5933d-147">Se ne viene riscontrata una, non verrà consentita l'esecuzione del codice gestito e sarà generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5933d-147">If any of these conditions are found, the managed code will not be allowed to run and an exception will be thrown.</span></span>  
  
### <a name="unsafe"></a><span data-ttu-id="5933d-148">UNSAFE</span><span class="sxs-lookup"><span data-stu-id="5933d-148">UNSAFE</span></span>  
 <span data-ttu-id="5933d-149">Il caricamento di un assembly, in modo esplicito chiamando il `System.Reflection.Assembly.Load()` metodo da una matrice di byte o in modo implicito tramite l'utilizzo dello `Reflection.Emit` spazio dei nomi, non è consentito.</span><span class="sxs-lookup"><span data-stu-id="5933d-149">Loading an assembly-either explicitly by calling the `System.Reflection.Assembly.Load()` method from a byte array, or implicitly through the use of `Reflection.Emit` namespace-is not permitted.</span></span>  
  
### <a name="external_access"></a><span data-ttu-id="5933d-150">EXTERNAL_ACCESS</span><span class="sxs-lookup"><span data-stu-id="5933d-150">EXTERNAL_ACCESS</span></span>  
 <span data-ttu-id="5933d-151">Tutte le condizioni di `UNSAFE` vengono controllate.</span><span class="sxs-lookup"><span data-stu-id="5933d-151">All `UNSAFE` conditions are checked.</span></span>  
  
 <span data-ttu-id="5933d-152">Tutti i tipi e i metodi annotati con i valori dell'attributo di protezione host riportati di seguito dell'elenco supportato di assembly non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="5933d-152">All types and methods annotated with the following host protection attribute (HPA) values in the supported list of assemblies are disallowed.</span></span>  
  
-   <span data-ttu-id="5933d-153">SelfAffectingProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="5933d-153">SelfAffectingProcessMgmt</span></span>  
  
-   <span data-ttu-id="5933d-154">SelfAffectingThreading</span><span class="sxs-lookup"><span data-stu-id="5933d-154">SelfAffectingThreading</span></span>  
  
-   <span data-ttu-id="5933d-155">Sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="5933d-155">Synchronization</span></span>  
  
-   <span data-ttu-id="5933d-156">SharedState</span><span class="sxs-lookup"><span data-stu-id="5933d-156">SharedState</span></span>  
  
-   <span data-ttu-id="5933d-157">ExternalProcessMgmt</span><span class="sxs-lookup"><span data-stu-id="5933d-157">ExternalProcessMgmt</span></span>  
  
-   <span data-ttu-id="5933d-158">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="5933d-158">ExternalThreading</span></span>  
  
-   <span data-ttu-id="5933d-159">SecurityInfrastructure</span><span class="sxs-lookup"><span data-stu-id="5933d-159">SecurityInfrastructure</span></span>  
  
-   <span data-ttu-id="5933d-160">MayLeakOnAbort</span><span class="sxs-lookup"><span data-stu-id="5933d-160">MayLeakOnAbort</span></span>  
  
-   <span data-ttu-id="5933d-161">Interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="5933d-161">UI</span></span>  
  
 <span data-ttu-id="5933d-162">Per ulteriori informazioni su attributi e un elenco di tipi e membri non consentiti negli assembly supportati, vedere [attributi di protezione host e programmazione dell'integrazione con CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span><span class="sxs-lookup"><span data-stu-id="5933d-162">For more information about HPAs and a list of disallowed types and members in the supported assemblies, see [Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md).</span></span>  
  
### <a name="safe"></a><span data-ttu-id="5933d-163">SAFE</span><span class="sxs-lookup"><span data-stu-id="5933d-163">SAFE</span></span>  
 <span data-ttu-id="5933d-164">Tutte le condizioni di `EXTERNAL_ACCESS` vengono controllate.</span><span class="sxs-lookup"><span data-stu-id="5933d-164">All `EXTERNAL_ACCESS` conditions are checked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5933d-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5933d-165">See Also</span></span>  
 <span data-ttu-id="5933d-166">[Librerie di .NET Framework supportate](supported-net-framework-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="5933d-166">[Supported .NET Framework Libraries](supported-net-framework-libraries.md) </span></span>  
 <span data-ttu-id="5933d-167">[Sicurezza dall'accesso di codice per l'integrazione con CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="5933d-167">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="5933d-168">[Attributi di protezione host e programmazione dell'integrazione con CLR](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="5933d-168">[Host Protection Attributes and CLR Integration Programming](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 [<span data-ttu-id="5933d-169">Creazione di un assembly</span><span class="sxs-lookup"><span data-stu-id="5933d-169">Creating an Assembly</span></span>](../assemblies/creating-an-assembly.md)  
  
  
