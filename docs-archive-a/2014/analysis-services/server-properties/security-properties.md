---
title: Proprietà di sicurezza | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], properties
- SecurityPackageList property
- BuiltinAdminsAreServerAdmins property
- DisableClientImpersonation property
- ErrorMessageMode property
- RequiredProtectionLevel property
- ServiceAccountIsServerAdmin property
- RequireClientAuthentication property
ms.assetid: 2fc7fe10-0cbb-49ac-aa8c-8ec3f7a7705f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 20133554835803908a340c5369eb66e86b119d72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628009"
---
# <a name="security-properties"></a><span data-ttu-id="96979-102">Proprietà di sicurezza</span><span class="sxs-lookup"><span data-stu-id="96979-102">Security Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="96979-103">supporta le proprietà di sicurezza del server elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="96979-103">supports the security server properties listed in the following table.</span></span> <span data-ttu-id="96979-104">Per altre informazioni sulle proprietà aggiuntive del server e sulla relativa impostazione, vedere [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="96979-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="96979-105">**Si applica a:** modalità server multidimensionale e tabulare</span><span class="sxs-lookup"><span data-stu-id="96979-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="96979-106">Proprietà</span><span class="sxs-lookup"><span data-stu-id="96979-106">Properties</span></span>  
 `RequireClientAuthentication`  
 <span data-ttu-id="96979-107">Proprietà booleana che indica se è necessaria l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="96979-107">A Boolean property that indicates whether client authentication is required.</span></span>  
  
 <span data-ttu-id="96979-108">Il valore predefinito della proprietà è True, che indica che l'autenticazione client è necessaria.</span><span class="sxs-lookup"><span data-stu-id="96979-108">The default value for this property is True, which indicates that client authentication is required.</span></span>  
  
 `SecurityPackageList`  
 <span data-ttu-id="96979-109">Proprietà stringa che contiene un elenco delimitato da virgole di pacchetti SSPI utilizzati dal server per l'autenticazione client.</span><span class="sxs-lookup"><span data-stu-id="96979-109">A string property that contains a comma-separated list of SSPI packages used by server for client authentication.</span></span>  
  
 `DisableClientImpersonation`  
 <span data-ttu-id="96979-110">Proprietà booleana che indica se la rappresentazione client, ad esempio dalle stored procedure, è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="96979-110">A Boolean property that indicates whether client impersonation (for example, from stored procedures) is disabled.</span></span>  
  
 <span data-ttu-id="96979-111">Il valore predefinito della proprietà è False, che indica che la rappresentazione client è abilitata.</span><span class="sxs-lookup"><span data-stu-id="96979-111">The default value for this property is False, which indicates that client impersonation is enabled.</span></span>  
  
 `BuiltinAdminsAreServerAdmins`  
 <span data-ttu-id="96979-112">Proprietà booleana che indica se i membri del gruppo Administrators nel computer locale sono amministratori di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96979-112">A Boolean property that indicates whether members of the local machine administrators group are [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrators.</span></span>  
  
 `ServiceAccountIsServerAdmin`  
 <span data-ttu-id="96979-113">Proprietà booleana che indica se l'account del servizio è un amministratore del server.</span><span class="sxs-lookup"><span data-stu-id="96979-113">A Boolean property that indicates whether the service account is a server administrator.</span></span>  
  
 <span data-ttu-id="96979-114">Il valore predefinito della proprietà è True, che indica che l'account del servizio è un amministratore del server.</span><span class="sxs-lookup"><span data-stu-id="96979-114">The default value for this property is True, which indicates that the service account is a server administrator.</span></span>  
  
 `ErrorMessageMode`  
 <span data-ttu-id="96979-115">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96979-115">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="96979-116">Proprietà a valore integer a 32 bit con segno che definisce il livello di protezione richiesto per tutte le richieste client.</span><span class="sxs-lookup"><span data-stu-id="96979-116">A signed 32-bit integer property that defines the required protection level for all client requests.</span></span> <span data-ttu-id="96979-117">Questa proprietà può assumere uno dei valori elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="96979-117">This property has one of the values listed in the following table.</span></span>  
  
|<span data-ttu-id="96979-118">Valore</span><span class="sxs-lookup"><span data-stu-id="96979-118">Value</span></span>|<span data-ttu-id="96979-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96979-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="96979-120">*0*</span><span class="sxs-lookup"><span data-stu-id="96979-120">*0*</span></span>|<span data-ttu-id="96979-121">Nessun livello di protezione, è consentito l'utilizzo di testo non crittografato.</span><span class="sxs-lookup"><span data-stu-id="96979-121">None, clear text allowed.</span></span>|  
|<span data-ttu-id="96979-122">*1*</span><span class="sxs-lookup"><span data-stu-id="96979-122">*1*</span></span>|<span data-ttu-id="96979-123">Valore predefinito. È necessaria la crittografia, non è consentito l'utilizzo di testo non crittografato.</span><span class="sxs-lookup"><span data-stu-id="96979-123">(Default) Encryption required, no clear-text logging.</span></span>|  
|<span data-ttu-id="96979-124">*2*</span><span class="sxs-lookup"><span data-stu-id="96979-124">*2*</span></span>|<span data-ttu-id="96979-125">Sono ammesse le richieste in testo non crittografato ma solo con firme, livello di protezione più debole rispetto alla crittografia.</span><span class="sxs-lookup"><span data-stu-id="96979-125">Clear-text requests allowed but only with signatures (weaker protection than encryption).</span></span>|  
  
 `AdministrativeDataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="96979-126">Proprietà avanzata che deve essere modificata solo sotto la supervisione del servizio di supporto tecnico [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96979-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96979-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96979-127">See Also</span></span>  
 <span data-ttu-id="96979-128">[Configurare le proprietà del server in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="96979-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="96979-129">Determinare la modalità server di un'istanza di Analysis Services</span><span class="sxs-lookup"><span data-stu-id="96979-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
