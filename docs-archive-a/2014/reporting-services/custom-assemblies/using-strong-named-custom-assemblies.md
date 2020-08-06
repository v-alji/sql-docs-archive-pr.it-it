---
title: Uso di assembly personalizzati con nome sicuro | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- AllowPartiallyTrustedCallersAttribute attribute
- strong-named custom assemblies [Reporting Services]
- strong names [Reporting Services]
- assemblies [Reporting Services], strong names
- custom assemblies [Reporting Services], strong-named
ms.assetid: ca9f19d7-6e86-46f2-b9ad-9bf807eaa52e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e685ecda39e0487eb4b469920820fa6e4a10daa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623916"
---
# <a name="using-strong-named-custom-assemblies"></a><span data-ttu-id="e277e-102">Utilizzo di assembly personalizzati con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="e277e-102">Using Strong-Named Custom Assemblies</span></span>
  <span data-ttu-id="e277e-103">Un nome sicuro identifica un assembly e include il nome di testo dell'assembly, il numero di versione in quattro parti, informazioni sulle impostazioni cultura (se disponibili), una chiave pubblica e una firma digitale archiviata nel manifesto dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e277e-103">A strong name identifies an assembly and includes the assembly's text name, four-part version number, culture information (if provided), a public key, and a digital signature stored in the assembly's manifest.</span></span> <span data-ttu-id="e277e-104">Un nome sicuro identifica in modo univoco un assembly in CLR (Common Language Runtime) e assicura l'integrità binaria.</span><span class="sxs-lookup"><span data-stu-id="e277e-104">A strong name uniquely identifies an assembly to the common language runtime (CLR) and ensures binary integrity.</span></span>  
  
## <a name="using-allowpartiallytrustedcallersattribute"></a><span data-ttu-id="e277e-105">Utilizzo di AllowPartiallyTrustedCallersAttribute</span><span class="sxs-lookup"><span data-stu-id="e277e-105">Using AllowPartiallyTrustedCallersAttribute</span></span>  
 <span data-ttu-id="e277e-106">Per usare assembly con nome sicuro con i report, è necessario consentire la chiamata a tali assembly da un codice parzialmente attendibile usando l'attributo **AllowPartiallyTrustedCallers** dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e277e-106">To use strong-named assemblies with reports, you must allow your strong-named assembly to be called by partially trusted code using the assembly's **AllowPartiallyTrustedCallers** attribute.</span></span> <span data-ttu-id="e277e-107">È possibile usare **AllowPartiallyTrustedCallersAttribute** per consentire la chiamata agli assembly con nome sicuro da Progettazione report o dal server di report nelle espressioni di report.</span><span class="sxs-lookup"><span data-stu-id="e277e-107">You can use **AllowPartiallyTrustedCallersAttribute** to allow strong-named assemblies to be called by Report Designer or the report server in report expressions.</span></span> <span data-ttu-id="e277e-108">Per consentire al codice parzialmente attendibile di chiamare gli assembly con nome sicuro, aggiungere l'attributo a livello di assembly seguente al file di attributo dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e277e-108">To allow partially trusted code to call strong-named assemblies, add the following assembly-level attribute to your assembly attribute file.</span></span>  
  
```vb  
<assembly:AllowPartiallyTrustedCallers>  
```  
  
```csharp  
[assembly:AllowPartiallyTrustedCallers]  
```  
  
 <span data-ttu-id="e277e-109">**AllowPartiallyTrustedCallersAttribute** è efficace solo quando viene applicato da un assembly con nome sicuro a livello di assembly.</span><span class="sxs-lookup"><span data-stu-id="e277e-109">**AllowPartiallyTrustedCallersAttribute** is effective only when applied by a strong-named assembly at the assembly level.</span></span> <span data-ttu-id="e277e-110">Per ulteriori informazioni sull'applicazione di attributi a livello di assembly, vedere l'argomento relativo all'applicazione degli attributi nella [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentazione di SDK.</span><span class="sxs-lookup"><span data-stu-id="e277e-110">For more information about applying attributes at the assembly level, see "Applying Attributes" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="e277e-111">Quando è presente **AllowPartiallyTrustedCallersAttribute**, i controlli di sicurezza **FullTrustLinkDemand** predefiniti non vengono eseguiti, per rendere possibile la chiamata all'assembly da qualsiasi altro assembly parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="e277e-111">When **AllowPartiallyTrustedCallersAttribute** is present, the default **FullTrustLinkDemand** security checks are prevented, making the assembly callable from any other partially trusted assembly.</span></span> <span data-ttu-id="e277e-112">Tutti i controlli di sicurezza, inclusi gli attributi di sicurezza dichiarativi a livello di classe o di metodo, devono essere dichiarati in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="e277e-112">All security checks, including class-level or method-level declarative security attributes, must be explicitly stated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e277e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e277e-113">See Also</span></span>  
 [<span data-ttu-id="e277e-114">Utilizzo di assembly personalizzati con i report</span><span class="sxs-lookup"><span data-stu-id="e277e-114">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
