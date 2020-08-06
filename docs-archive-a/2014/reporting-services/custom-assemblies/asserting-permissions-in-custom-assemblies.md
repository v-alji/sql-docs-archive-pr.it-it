---
title: Asserzione di autorizzazioni negli assembly personalizzati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- secure calls [Reporting Services]
- custom assemblies [Reporting Services], permissions
- permission sets [Reporting Services]
- asserting permissions
- permissions [Reporting Services], custom assemblies
- limited permission sets
- security configuration files [Reporting Services]
ms.assetid: 3afb9631-f15e-405e-990b-ee102828f298
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cba3c0b74712b6b4d0f6b5c58925cfd562f0df77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623046"
---
# <a name="asserting-permissions-in-custom-assemblies"></a><span data-ttu-id="6e9e7-102">Asserzione di autorizzazioni negli assembly personalizzati</span><span class="sxs-lookup"><span data-stu-id="6e9e7-102">Asserting Permissions in Custom Assemblies</span></span>
  <span data-ttu-id="6e9e7-103">Per impostazione predefinita, il codice degli assembly personalizzati viene eseguito con il set di autorizzazioni **Execution** limitato.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-103">By default, custom assembly code runs with the limited **Execution** permission set.</span></span> <span data-ttu-id="6e9e7-104">In alcuni casi, potrebbe essere necessario implementare un assembly personalizzato per l'esecuzione di chiamate protette alle risorse protette all'interno del sistema di sicurezza (ad esempio un file o il Registro di sistema).</span><span class="sxs-lookup"><span data-stu-id="6e9e7-104">In some cases, you may wish to implement a custom assembly that makes secured calls to protected resources within your security system (such as a file or the registry).</span></span> <span data-ttu-id="6e9e7-105">A tale scopo, è necessario effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6e9e7-105">In order to accomplish this, you must do the following:</span></span>  
  
1.  <span data-ttu-id="6e9e7-106">Identificare le autorizzazioni esatte necessarie per il codice per effettuare la chiamata protetta.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-106">Identify the exact permissions that your code needs in order to make the secured call.</span></span> <span data-ttu-id="6e9e7-107">Se questo metodo fa parte di una [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] libreria, queste informazioni devono essere incluse nella documentazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-107">If this method is part of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] library, this information should be included in the method documentation.</span></span>  
  
2.  <span data-ttu-id="6e9e7-108">Modificare i file di configurazione dei criteri del server di report per concedere le autorizzazioni necessarie all'assembly personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-108">Modify the report server policy configuration files in order to grant the custom assembly the required permissions.</span></span> <span data-ttu-id="6e9e7-109">Per altre informazioni sui file di configurazione dei criteri di sicurezza, vedere [Uso di file di criteri di sicurezza di Reporting Services](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span><span class="sxs-lookup"><span data-stu-id="6e9e7-109">For more information about the security policy configuration files, see [Using Reporting Services Security Policy Files](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span></span>  
  
3.  <span data-ttu-id="6e9e7-110">Eseguire l'asserzione delle autorizzazioni necessarie come parte del metodo nel quale viene effettuata la chiamata protetta.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-110">Assert the required permissions as part of the method in which the secure call is made.</span></span> <span data-ttu-id="6e9e7-111">Questa operazione è necessaria in quanto il codice dell'assembly personalizzato chiamato dal server di report fa parte dell'assembly host delle espressioni di report che, per impostazione predefinita, viene eseguito con l'autorizzazione di **esecuzione**.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-111">This is required because the custom assembly code that is called by the report server is part of the report expression host assembly, which runs with **Execution** permission by default.</span></span> <span data-ttu-id="6e9e7-112">Il set di autorizzazioni **Execution** consente al codice di essere eseguito, ma non di usare risorse protette.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-112">The **Execution** permission set enables code to run, but not to use protected resources.</span></span>  
  
4.  <span data-ttu-id="6e9e7-113">Contrassegnare l'assembly personalizzato con **AllowPartiallyTrustedCallersAttribute** se è firmato con un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-113">Mark the custom assembly with **AllowPartiallyTrustedCallersAttribute** if it is signed with a strong name.</span></span> <span data-ttu-id="6e9e7-114">Questa operazione è necessaria in quanto gli assembly personalizzati vengono chiamati da un'espressione di report che fa parte dell'assembly host delle espressioni di report a cui, per impostazione predefinita, non viene concesso il set di autorizzazioni **FullTrust**. Si tratta quindi di un chiamante "parzialmente attendibile".</span><span class="sxs-lookup"><span data-stu-id="6e9e7-114">This is required because custom assemblies are called from a report expression that is part of the report expression host assembly, which, by default, is not granted **FullTrust**; thus it is a "partially trusted" caller.</span></span> <span data-ttu-id="6e9e7-115">Per altre informazioni, vedere [Uso di assembly personalizzati con nome sicuro](using-strong-named-custom-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="6e9e7-115">For more information, see [Using Strong-Named Custom Assemblies](using-strong-named-custom-assemblies.md).</span></span>  
  
## <a name="implementing-a-secure-call"></a><span data-ttu-id="6e9e7-116">Implementazione di una chiamata protetta</span><span class="sxs-lookup"><span data-stu-id="6e9e7-116">Implementing a Secure Call</span></span>  
 <span data-ttu-id="6e9e7-117">È possibile modificare i file di configurazione dei criteri per concedere autorizzazioni specifiche all'assembly.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-117">You can modify the policy configuration files to grant your assembly specific permissions.</span></span> <span data-ttu-id="6e9e7-118">Se, ad esempio, si scrive un assembly personalizzato per gestire la conversione delle valute, potrebbe essere necessario leggere i tassi di cambio della valuta correnti da un file.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-118">For example, if you were writing a custom assembly to handle currency conversion, you might need to read the current currency exchange rates from a file.</span></span> <span data-ttu-id="6e9e7-119">Per recuperare le informazioni sui tassi, aggiungere un'altra autorizzazione di sicurezza **FileIOPermission** al set di autorizzazioni per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-119">To retrieve the rate information, you would need to add an additional security permission, **FileIOPermission**, to your permission set for the assembly.</span></span> <span data-ttu-id="6e9e7-120">Nel file di configurazione dei criteri è possibile inserire le seguenti voci aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="6e9e7-120">You can make the following additional entry in the policy configuration file:</span></span>  
  
```  
<PermissionSet class="NamedPermissionSet"  
   version="1"  
   Name="CurrencyRatesFilePermissionSet"  
   Description="A special permission set that grants read access to my currency rates file.">  
      <IPermission class="FileIOPermission"  
         version="1"  
         Read="C:\CurrencyRates.xml"/>  
      <IPermission class="SecurityPermission"  
         version="1"  
         Flags="Execution, Assertion"/>  
</PermissionSet>  
```  
  
 <span data-ttu-id="6e9e7-121">Viene quindi aggiunto un gruppo di codice che fa riferimento a tale set di autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="6e9e7-121">You then add a code group that references that permission set:</span></span>  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="CurrencyRatesFilePermissionSet"  
   Name="MyNewCodeGroup"  
   Description="A special code group for my custom assembly.">  
   <IMembershipCondition class="UrlMembershipCondition"  
      version="1"  
      Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\MSSQL\Reporting Services\ReportServer\bin\CurrencyConversion.dll"/>  
</CodeGroup>  
```  
  
 <span data-ttu-id="6e9e7-122">Per consentire al codice di acquisire l'autorizzazione appropriata, è necessaria l'asserzione dell'autorizzazione nel codice dell'assembly personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-122">In order for your code to acquire the appropriate permission, you must assert the permission within your custom assembly code.</span></span> <span data-ttu-id="6e9e7-123">Se, ad esempio, si desidera aggiungere l'accesso in sola lettura a un file XML, C:\CurrencyRates.xml, è necessario aggiungere al metodo il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6e9e7-123">For example, if you want to add read-only access to an XML file, C:\CurrencyRates.xml, you must add the following code to your method:</span></span>  
  
```  
// C#  
FileIOPermission permission = new FileIOPermission(FileIOPermissionAccess.Read, @"C:\CurrencyRates.xml");  
try  
{  
   permission.Assert();  
   // Load the XML currency rates file  
   XmlDocument doc = new XmlDocument();  
   doc.Load(@"C:\CurrencyRates.xml");  
...  
```  
  
 <span data-ttu-id="6e9e7-124">È inoltre possibile aggiungere l'asserzione come attributo del metodo:</span><span class="sxs-lookup"><span data-stu-id="6e9e7-124">You can also add the assertion as a method attribute:</span></span>  
  
```  
[FileIOPermissionAttribute(SecurityAction.Assert, Read=@"C:\CurrencyRates.xml")]  
```  
  
 <span data-ttu-id="6e9e7-125">Per ulteriori informazioni, vedere l'argomento relativo alla sicurezza di .NET Framework nella Guida per gli sviluppatori di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6e9e7-125">For more information, see ".NET Framework Security" in the .NET Framework Developer's Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9e7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e9e7-126">See Also</span></span>  
 [<span data-ttu-id="6e9e7-127">Utilizzo di assembly personalizzati con i report</span><span class="sxs-lookup"><span data-stu-id="6e9e7-127">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
