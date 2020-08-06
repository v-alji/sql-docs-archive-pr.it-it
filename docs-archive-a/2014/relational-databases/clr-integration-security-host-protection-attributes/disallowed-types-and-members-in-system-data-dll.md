---
title: Tipi e membri non consentiti in System.Data.dll | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- host protection attributes [CLR integration]
- common language runtime [SQL Server], host protection attributes
ms.assetid: ee5f55e9-fbef-401a-be18-a2e5873c8720
author: rothja
ms.author: jroth
ms.openlocfilehash: cd62f6f0a90bd167f20a33f8de749acc982f39b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626811"
---
# <a name="disallowed-types-and-members-in-systemdatadll"></a><span data-ttu-id="31f2d-102">Tipi e membri non consentiti in System.Data.dll</span><span class="sxs-lookup"><span data-stu-id="31f2d-102">Disallowed Types and Members in System.Data.dll</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="31f2d-103">la programmazione Common Language Integration (CLR) non consente l'utilizzo di un tipo o di un membro che dispone di un oggetto `HostProtectionAttribute` che specifica un' `System.Security.Permissions.HostProtectionResource` enumerazione con un valore `ExternalProcessMgmt` , `ExternalThreading` , `MayLeakOnAbort` , `SecurityInfrastructure` , `SelfAffectingProcessMgmnt` , `SelfAffectingThreading` , **SharedState**, `Synchronization` o `UI` .</span><span class="sxs-lookup"><span data-stu-id="31f2d-103">common language integration (CLR) programming disallows the use of a type or member that has a `HostProtectionAttribute` that specifies a `System.Security.Permissions.HostProtectionResource` enumeration with a value of `ExternalProcessMgmt`, `ExternalThreading`, `MayLeakOnAbort`, `SecurityInfrastructure`, `SelfAffectingProcessMgmnt`, `SelfAffectingThreading`, **SharedState**, `Synchronization`, or `UI`.</span></span> <span data-ttu-id="31f2d-104">Nella tabella seguente sono elencati i membri e i tipi dell'assembly System.Data.dll i cui valori degli attributi di protezione host non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="31f2d-104">The following table lists the members and types of the System.Data.dll assembly whose Host Protection Attribute (HPA) values are disallowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="31f2d-105">Questo elenco è stato generato dagli assembly supportati.</span><span class="sxs-lookup"><span data-stu-id="31f2d-105">This list was generated from the supported assemblies.</span></span> <span data-ttu-id="31f2d-106">Per ulteriori informazioni, vedere [supported .NET Framework libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="31f2d-106">For more information, see [Supported .NET Framework Libraries](../clr-integration/database-objects/supported-net-framework-libraries.md).</span></span>  
  
|<span data-ttu-id="31f2d-107">Tipo o membro</span><span class="sxs-lookup"><span data-stu-id="31f2d-107">Type or Member</span></span>|<span data-ttu-id="31f2d-108">Valori dell'attributo di protezione host</span><span class="sxs-lookup"><span data-stu-id="31f2d-108">HPA Value(s)</span></span>|  
|--------------------|--------------------|  
|<span data-ttu-id="31f2d-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span><span class="sxs-lookup"><span data-stu-id="31f2d-109">System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery()</span></span>|<span data-ttu-id="31f2d-110">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="31f2d-110">ExternalThreading</span></span>|  
|<span data-ttu-id="31f2d-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span><span class="sxs-lookup"><span data-stu-id="31f2d-111">System.Data.SqlClient.SqlCommand.BeginExecuteReader()</span></span>|<span data-ttu-id="31f2d-112">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="31f2d-112">ExternalThreading</span></span>|  
|<span data-ttu-id="31f2d-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span><span class="sxs-lookup"><span data-stu-id="31f2d-113">System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader()</span></span>|<span data-ttu-id="31f2d-114">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="31f2d-114">ExternalThreading</span></span>|  
|<span data-ttu-id="31f2d-115">System.Data.SqlClient.SqlDependency..ctor()</span><span class="sxs-lookup"><span data-stu-id="31f2d-115">System.Data.SqlClient.SqlDependency..ctor()</span></span>|<span data-ttu-id="31f2d-116">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="31f2d-116">ExternalThreading</span></span>|  
|<span data-ttu-id="31f2d-117">System.Data.SqlClient.SqlDependency.Start()</span><span class="sxs-lookup"><span data-stu-id="31f2d-117">System.Data.SqlClient.SqlDependency.Start()</span></span>|<span data-ttu-id="31f2d-118">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="31f2d-118">ExternalThreading</span></span>|  
|<span data-ttu-id="31f2d-119">System.Data.SqlClient.SqlDependency.Stop()</span><span class="sxs-lookup"><span data-stu-id="31f2d-119">System.Data.SqlClient.SqlDependency.Stop()</span></span>|<span data-ttu-id="31f2d-120">ExternalThreading</span><span class="sxs-lookup"><span data-stu-id="31f2d-120">ExternalThreading</span></span>|  
|<span data-ttu-id="31f2d-121">System.Data.TypedDataSetGenerator</span><span class="sxs-lookup"><span data-stu-id="31f2d-121">System.Data.TypedDataSetGenerator</span></span>|<span data-ttu-id="31f2d-122">SharedState, Synchronization</span><span class="sxs-lookup"><span data-stu-id="31f2d-122">SharedState, Synchronization</span></span>|  
|<span data-ttu-id="31f2d-123">System.Xml.XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="31f2d-123">System.Xml.XmlDataDocument</span></span>|<span data-ttu-id="31f2d-124">Sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="31f2d-124">Synchronization</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="31f2d-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31f2d-125">See Also</span></span>  
 <span data-ttu-id="31f2d-126">[Attributi di protezione host e programmazione dell'integrazione con CLR](host-protection-attributes-and-clr-integration-programming.md) </span><span class="sxs-lookup"><span data-stu-id="31f2d-126">[Host Protection Attributes and CLR Integration Programming](host-protection-attributes-and-clr-integration-programming.md) </span></span>  
 <span data-ttu-id="31f2d-127">[Tipi e membri non consentiti in Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span><span class="sxs-lookup"><span data-stu-id="31f2d-127">[Disallowed Types and Members in Microsoft.VisualBasic.dll](disallowed-types-and-members-in-microsoft-visualbasic-dll.md) </span></span>  
 <span data-ttu-id="31f2d-128">[Tipi e membri non consentiti in mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span><span class="sxs-lookup"><span data-stu-id="31f2d-128">[Disallowed Types and Members in mscorlib.dll](disallowed-types-and-members-in-mscorlib-dll.md) </span></span>  
 <span data-ttu-id="31f2d-129">[Tipi e membri non consentiti in System.dll](disallowed-types-and-members-in-system-dll.md) </span><span class="sxs-lookup"><span data-stu-id="31f2d-129">[Disallowed Types and Members in System.dll](disallowed-types-and-members-in-system-dll.md) </span></span>  
 [<span data-ttu-id="31f2d-130">Tipi e membri non consentiti in System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="31f2d-130">Disallowed Types and Members in System.Core.dll</span></span>](disallowed-types-and-members-in-system-core-dll.md)  
  
  
