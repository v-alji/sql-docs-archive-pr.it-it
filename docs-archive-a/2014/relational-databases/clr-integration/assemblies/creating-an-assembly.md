---
title: Creazione di un assembly | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- creating assemblies
- UNSAFE assemblies
- CREATE ASSEMBLY statement
- SAFE assemblies
- EXTERNAL_ACCESS assemblies
- assemblies [CLR integration], creating
ms.assetid: a2bc503d-b6b2-4963-8beb-c11c323f18e0
author: rothja
ms.author: jroth
ms.openlocfilehash: 9dea1f8fe57691f05274cac353a1064420309e06
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720039"
---
# <a name="creating-an-assembly"></a><span data-ttu-id="53773-102">Creazione di un assembly</span><span class="sxs-lookup"><span data-stu-id="53773-102">Creating an Assembly</span></span>
  <span data-ttu-id="53773-103">Gli oggetti di database gestiti, ad esempio le stored procedure o i trigger, vengono compilati e quindi distribuiti in unità denominate assembly.</span><span class="sxs-lookup"><span data-stu-id="53773-103">Managed database objects, such as stored procedures or triggers, are compiled and then deployed in units called an assembly.</span></span> <span data-ttu-id="53773-104">Gli assembly DLL gestiti devono essere registrati in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] prima di poter utilizzare la funzionalità fornita dall'assembly.</span><span class="sxs-lookup"><span data-stu-id="53773-104">Managed DLL assemblies must be registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] before the functionality the assembly provides can be used.</span></span> <span data-ttu-id="53773-105">Per registrare l'assembly in un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], utilizzare l'istruzione CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="53773-105">To register an assembly in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, use the CREATE ASSEMBLY statement.</span></span> <span data-ttu-id="53773-106">In questo argomento viene descritto come registrare un assembly in un database tramite l'istruzione CREATE ASSEMBLY e specificare le impostazioni di sicurezza per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="53773-106">This topic discusses how to register an assembly in a database using the CREATE ASSEMBLY statement, and how to specify the security settings for the assembly.</span></span>  
  
## <a name="the-create-assembly-statement"></a><span data-ttu-id="53773-107">Istruzione CREATE ASSEMBLY</span><span class="sxs-lookup"><span data-stu-id="53773-107">The CREATE ASSEMBLY Statement</span></span>  
 <span data-ttu-id="53773-108">L'istruzione CREATE ASSEMBLY viene utilizzata per creare un assembly in un database.</span><span class="sxs-lookup"><span data-stu-id="53773-108">The CREATE ASSEMBLY statement is used to create an assembly in a database.</span></span> <span data-ttu-id="53773-109">Esempio:</span><span class="sxs-lookup"><span data-stu-id="53773-109">Here is an example:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="53773-110">La clausola FROM specifica il percorso dell'assembly da creare.</span><span class="sxs-lookup"><span data-stu-id="53773-110">The FROM clause specifies the pathname of the assembly to create.</span></span> <span data-ttu-id="53773-111">Questo percorso può essere un percorso UNC (Universal Naming Convention) o un percorso di file fisico locale rispetto al computer.</span><span class="sxs-lookup"><span data-stu-id="53773-111">This path can either be a Universal Naming Convention (UNC) path or a physical file path that is local to the machine.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="53773-112">non consente la registrazione di versioni diverse di un assembly con lo stesso nome, lingua e chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="53773-112">does not allow registering different versions of an assembly with the same name, culture and public key.</span></span>  
  
 <span data-ttu-id="53773-113">È possibile creare assembly che fanno riferimento ad altri assembly.</span><span class="sxs-lookup"><span data-stu-id="53773-113">It is possible to create assemblies that reference other assemblies.</span></span> <span data-ttu-id="53773-114">Quando viene creato un assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , crea anche gli assembly a cui fa riferimento l'assembly a livello di radice, se gli assembly a cui si fa riferimento non sono già stati creati nel database.</span><span class="sxs-lookup"><span data-stu-id="53773-114">When an assembly is created in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] also creates the assemblies referenced by the root-level assembly, if the referenced assemblies are not already created into the database.</span></span>  
  
 <span data-ttu-id="53773-115">Agli utenti del database o ai ruoli utente vengono concesse autorizzazioni per creare, e pertanto possedere, assembly in un database.</span><span class="sxs-lookup"><span data-stu-id="53773-115">Database users or user roles are given permissions to create, and thereby own, assemblies in a database.</span></span> <span data-ttu-id="53773-116">Per creare assembly, l'utente o il ruolo del database deve disporre dell'autorizzazione CREATE ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="53773-116">In order to create assemblies, the database user or role should have the CREATE ASSEMBLY permission.</span></span>  
  
 <span data-ttu-id="53773-117">Un assembly può fare riferimento ad altri assembly solo nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="53773-117">An assembly can only succeed in referencing other assemblies if:</span></span>  
  
-   <span data-ttu-id="53773-118">L'assembly chiamato o cui si fa riferimento è di proprietà dello stesso utente o ruolo.</span><span class="sxs-lookup"><span data-stu-id="53773-118">The assembly that is called or referenced is owned by the same user or role.</span></span>  
  
-   <span data-ttu-id="53773-119">L'assembly chiamato o cui si fa riferimento è stato creato nello stesso database.</span><span class="sxs-lookup"><span data-stu-id="53773-119">The assembly that is called or referenced was created in the same database.</span></span>  
  
## <a name="specifying-security-when-creating-assemblies"></a><span data-ttu-id="53773-120">Configurazione della sicurezza durante la creazione di assembly</span><span class="sxs-lookup"><span data-stu-id="53773-120">Specifying Security When Creating Assemblies</span></span>  
 <span data-ttu-id="53773-121">Quando si crea un assembly in un database di [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], è possibile specificare uno tra tre diversi livelli di sicurezza in cui eseguire il codice: `SAFE`, `EXTERNAL_ACCESS` o `UNSAFE`.</span><span class="sxs-lookup"><span data-stu-id="53773-121">When creating an assembly into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, you can specify one of three different levels of security in which your code can run: `SAFE`, `EXTERNAL_ACCESS`, or `UNSAFE`.</span></span> <span data-ttu-id="53773-122">Quando si esegue l'istruzione `CREATE ASSEMBLY`, nell'assembly di codice vengono effettuati alcuni controlli che possono impedire la registrazione dell'assembly nel server.</span><span class="sxs-lookup"><span data-stu-id="53773-122">When the `CREATE ASSEMBLY` statement is run, certain checks are performed on the code assembly which may cause the assembly to fail to register on the server.</span></span> <span data-ttu-id="53773-123">Per ulteriori informazioni, vedere l'esempio di rappresentazione in [codeplex](https://msftengprodsamples.codeplex.com/).</span><span class="sxs-lookup"><span data-stu-id="53773-123">For more information, see the Impersonation sample on [CodePlex](https://msftengprodsamples.codeplex.com/).</span></span>  
  
 <span data-ttu-id="53773-124">`SAFE` è il set di autorizzazioni predefinito e può essere utilizzato nella maggior parte degli scenari.</span><span class="sxs-lookup"><span data-stu-id="53773-124">`SAFE` is the default permission set and works for the majority of scenarios.</span></span> <span data-ttu-id="53773-125">Per specificare un determinato livello di sicurezza, è necessario modificare la sintassi dell'istruzione CREATE ASSEMBLY come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="53773-125">To specify a given security level, you modify the syntax of the CREATE ASSEMBLY statement as follows:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = SAFE;  
```  
  
 <span data-ttu-id="53773-126">È inoltre possibile creare un assembly con il set di autorizzazioni `SAFE` omettendo semplicemente la terza riga del codice precedente:</span><span class="sxs-lookup"><span data-stu-id="53773-126">It is also possible to create an assembly with the `SAFE` permission set by simply omitting the third line of code above:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll';  
```  
  
 <span data-ttu-id="53773-127">Quando il codice in un assembly viene eseguito utilizzando il set di autorizzazioni `SAFE`, può eseguire solo calcoli e accesso ai dati nel server tramite il provider gestito in-process.</span><span class="sxs-lookup"><span data-stu-id="53773-127">When code in an assembly runs under the `SAFE` permission set, it can only do computation and data access within the server through the in-process managed provider.</span></span>  
  
### <a name="creating-external_access-and-unsafe-assemblies"></a><span data-ttu-id="53773-128">Creazione di assembly EXTERNAL_ACCESS e UNSAFE</span><span class="sxs-lookup"><span data-stu-id="53773-128">Creating EXTERNAL_ACCESS and UNSAFE Assemblies</span></span>  
 <span data-ttu-id="53773-129">`EXTERNAL_ACCESS` consente di gestire scenari in cui il codice deve accedere a risorse esterne al server, ad esempio file, rete, Registro di sistema e variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="53773-129">`EXTERNAL_ACCESS` addresses scenarios in which the code needs to access resources outside the server, such as files, network, registry, and environment variables.</span></span> <span data-ttu-id="53773-130">Ogni volta che il server accede a una risorsa esterna, rappresenta il contesto di sicurezza dell'utente che chiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="53773-130">Whenever the server accesses an external resource, it impersonates the security context of the user calling the managed code.</span></span>  
  
 <span data-ttu-id="53773-131">L'autorizzazione `UNSAFE` per il codice è adatta in situazioni in cui un assembly non è effettivamente protetto o richiede accesso aggiuntivo a risorse limitate, ad esempio le API [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32.</span><span class="sxs-lookup"><span data-stu-id="53773-131">`UNSAFE` code permission is for those situations in which an assembly is not verifiably safe or requires additional access to restricted resources, such as the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Win32 API.</span></span>  
  
 <span data-ttu-id="53773-132">Per creare un assembly `EXTERNAL_ACCESS` o `UNSAFE` in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], deve verificarsi una delle due condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="53773-132">To create an `EXTERNAL_ACCESS` or `UNSAFE` assembly in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], one of the following two conditions must be met:</span></span>  
  
1.  <span data-ttu-id="53773-133">L'assembly è firmato con nome sicuro o dispone di firma Authenticode con un certificato.</span><span class="sxs-lookup"><span data-stu-id="53773-133">The assembly is strong name signed or Authenticode signed with a certificate.</span></span> <span data-ttu-id="53773-134">Questo nome sicuro (o certificato) viene creato in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] come chiave asimmetrica (o certificato) e dispone di un account di accesso corrispondente con autorizzazione `EXTERNAL ACCESS ASSEMBLY` (per assembly di accesso esterni) o `UNSAFE ASSEMBLY` (per assembly non protetti).</span><span class="sxs-lookup"><span data-stu-id="53773-134">This strong name (or certificate) is created inside [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as an asymmetric key (or certificate), and has a corresponding login with `EXTERNAL ACCESS ASSEMBLY` permission (for external access assemblies) or `UNSAFE ASSEMBLY` permission (for unsafe assemblies).</span></span>  
  
2.  <span data-ttu-id="53773-135">Il proprietario del database (DBO) dispone dell' `EXTERNAL ACCESS ASSEMBLY` autorizzazione (per `EXTERNAL ACCESS` gli assembly) o `UNSAFE ASSEMBLY` (per `UNSAFE` gli assembly) e il database dispone della [proprietà di database TRUSTWORTHY](../../security/trustworthy-database-property.md) impostata su `ON` .</span><span class="sxs-lookup"><span data-stu-id="53773-135">The database owner (DBO) has `EXTERNAL ACCESS ASSEMBLY` (for `EXTERNAL ACCESS` assemblies) or `UNSAFE ASSEMBLY` (for `UNSAFE` assemblies) permission, and the database has the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) set to `ON`.</span></span>  
  
 <span data-ttu-id="53773-136">Le due condizioni elencate in precedenza vengono verificate in fase di caricamento dell'assembly (fase che include l'esecuzione).</span><span class="sxs-lookup"><span data-stu-id="53773-136">The two conditions listed above are also checked at assembly load time (which includes execution).</span></span> <span data-ttu-id="53773-137">Per caricare l'assembly, è necessario che si verifichi almeno una delle due condizioni.</span><span class="sxs-lookup"><span data-stu-id="53773-137">At least one of the conditions must be met in order to load the assembly.</span></span>  
  
 <span data-ttu-id="53773-138">Si consiglia di non impostare la [Proprietà Trustworthy del database](../../security/trustworthy-database-property.md) in un database solo per l' `ON` esecuzione del codice Common Language Runtime (CLR) nel processo server.</span><span class="sxs-lookup"><span data-stu-id="53773-138">We recommend that the [TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) on a database not be set to `ON` only to run common language runtime (CLR) code in the server process.</span></span> <span data-ttu-id="53773-139">È invece consigliabile creare una chiave asimmetrica dal file di assembly nel database master.</span><span class="sxs-lookup"><span data-stu-id="53773-139">Instead, we recommend that an asymmetric key be created from the assembly file in the master database.</span></span> <span data-ttu-id="53773-140">È quindi necessario creare un account di accesso con mapping alla chiave asimmetrica e concedere a tale account di accesso l'autorizzazione `EXTERNAL ACCESS ASSEMBLY` o `UNSAFE ASSEMBLY`.</span><span class="sxs-lookup"><span data-stu-id="53773-140">A login mapped to this asymmetric key must then be created, and the login must be granted `EXTERNAL ACCESS ASSEMBLY` or `UNSAFE ASSEMBLY` permission.</span></span>  
  
 <span data-ttu-id="53773-141">Le [!INCLUDE[tsql](../../../includes/tsql-md.md)] istruzioni seguenti prima di eseguire l'istruzione CREATE assembly.</span><span class="sxs-lookup"><span data-stu-id="53773-141">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll'     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey     
GRANT EXTERNAL ACCESS ASSEMBLY TO SQLCLRTestLogin;   
GO   
```  
  
> [!NOTE]  
>  <span data-ttu-id="53773-142">È necessario creare un nuovo account di accesso da associare alla chiave asimmetrica.</span><span class="sxs-lookup"><span data-stu-id="53773-142">You must create a new login to associate with the asymmetric key.</span></span> <span data-ttu-id="53773-143">Questo account di accesso viene utilizzato solo per concedere le autorizzazioni e non è necessario che sia associato a un utente o utilizzato nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="53773-143">This login is only used to grant permissions; it does not have to be associated with a user, or used within the application.</span></span>  
  
 <span data-ttu-id="53773-144">Per creare un assembly `EXTERNAL ACCESS`, è necessario disporre dell'autorizzazione `EXTERNAL ACCESS`.</span><span class="sxs-lookup"><span data-stu-id="53773-144">To create an `EXTERNAL ACCESS` assembly, the creator needs to have `EXTERNAL ACCESS` permission.</span></span> <span data-ttu-id="53773-145">Questa autorizzazione viene specificata durante la creazione dell'assembly:</span><span class="sxs-lookup"><span data-stu-id="53773-145">This is specified when creating the assembly:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = EXTERNAL_ACCESS;  
```  
  
 <span data-ttu-id="53773-146">Le [!INCLUDE[tsql](../../../includes/tsql-md.md)] istruzioni seguenti prima di eseguire l'istruzione CREATE assembly.</span><span class="sxs-lookup"><span data-stu-id="53773-146">The following [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements before running the CREATE ASSEMBLY statement.</span></span>  
  
```  
USE master;   
GO    
  
CREATE ASYMMETRIC KEY SQLCLRTestKey FROM EXECUTABLE FILE = 'C:\MyDBApp\SQLCLRTest.dll';     
CREATE LOGIN SQLCLRTestLogin FROM ASYMMETRIC KEY SQLCLRTestKey ;    
GRANT UNSAFE ASSEMBLY TO SQLCLRTestLogin ;  
GO  
```  
  
 <span data-ttu-id="53773-147">Per indicare che un assembly viene caricato con l'autorizzazione `UNSAFE`, è necessario specificare il set di autorizzazioni `UNSAFE` durante il caricamento dell'assembly nel server:</span><span class="sxs-lookup"><span data-stu-id="53773-147">To specify that an assembly loads with `UNSAFE` permission, you specify the `UNSAFE` permission set when loading the assembly into the server:</span></span>  
  
```  
CREATE ASSEMBLY SQLCLRTest  
FROM 'C:\MyDBApp\SQLCLRTest.dll'  
WITH PERMISSION_SET = UNSAFE;  
```  
  
 <span data-ttu-id="53773-148">Per ulteriori informazioni sulle autorizzazioni per ognuna delle impostazioni, vedere sicurezza dell' [integrazione con CLR](../security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="53773-148">For more details about the permissions for each of the settings, see [CLR Integration Security](../security/clr-integration-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53773-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53773-149">See Also</span></span>  
 <span data-ttu-id="53773-150">[Gestione degli assembly di integrazione CLR](managing-clr-integration-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="53773-150">[Managing CLR Integration Assemblies](managing-clr-integration-assemblies.md) </span></span>  
 <span data-ttu-id="53773-151">[Modifica di un assembly](altering-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="53773-151">[Altering an Assembly](altering-an-assembly.md) </span></span>  
 <span data-ttu-id="53773-152">[Eliminazione di un assembly](dropping-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="53773-152">[Dropping an Assembly](dropping-an-assembly.md) </span></span>  
 <span data-ttu-id="53773-153">[Sicurezza dall'accesso di codice per l'integrazione con CLR](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="53773-153">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 <span data-ttu-id="53773-154">[Proprietà di database TRUSTWORTHY](../../security/trustworthy-database-property.md) </span><span class="sxs-lookup"><span data-stu-id="53773-154">[TRUSTWORTHY Database Property](../../security/trustworthy-database-property.md) </span></span>  
 [<span data-ttu-id="53773-155">Accettazione di chiamanti parzialmente attendibili</span><span class="sxs-lookup"><span data-stu-id="53773-155">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
  
