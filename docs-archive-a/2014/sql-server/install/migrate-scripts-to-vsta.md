---
title: Eseguire la migrazione degli script a VSTA | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SSIS Script task, converting scripts
- Script component [Integration Services], converting scripts
- Script task [Integration Services], converting scripts
- SSIS Script component, converting scripts
ms.assetid: d685098b-86a1-46bf-939a-63d56951e009
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: afbc19c35f99a5abc5a6ebd92024e42baa6a9237
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724380"
---
# <a name="migrate-scripts-to-vsta"></a><span data-ttu-id="b40da-102">Migrare script a VSTA</span><span class="sxs-lookup"><span data-stu-id="b40da-102">Migrate Scripts to VSTA</span></span>
  <span data-ttu-id="b40da-103">Quando si aggiornano [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] i pacchetti a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] esegue la migrazione degli script in qualsiasi attività script o componente di script a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span><span class="sxs-lookup"><span data-stu-id="b40da-103">When you upgrade [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] packages to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] migrates the scripts in any Script tasks or Script components to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="b40da-104">VSTA è l'ambiente di scripting utilizzato da [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b40da-104">VSTA is the scripting environment that [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] uses.</span></span> <span data-ttu-id="b40da-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] l'ambiente di scripting per [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] è [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for Applications (VSA).</span><span class="sxs-lookup"><span data-stu-id="b40da-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], the scripting environment for [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] for Applications (VSA).</span></span>  
  
 <span data-ttu-id="b40da-106">Se gli script nelle attività Script o nei componenti di script fanno riferimento a interfacce, potrebbe essere necessario modificare tali riferimenti prima di aggiornare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="b40da-106">If the scripts in either the Script tasks or Script components reference interfaces, you might have to modify those references before you upgrade the package.</span></span> <span data-ttu-id="b40da-107">In caso contrario, il pacchetto non verrà aggiornato o gli script non verranno convalidati, a seconda del metodo di aggiornamento utilizzato.</span><span class="sxs-lookup"><span data-stu-id="b40da-107">Otherwise, the package will not be upgraded or the scripts will not be validated, depending on the upgrade method that you use.</span></span> <span data-ttu-id="b40da-108">Per modificare questi riferimenti, sostituire i riferimenti alle interfacce IDTS*xxx*90 con riferimenti alle interfacce IDTS*xxx*100 corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b40da-108">To modify these references, replace references to IDTS*xxx*90 interfaces with references to the corresponding IDTS*xxx*100 interfaces.</span></span>  
  
 <span data-ttu-id="b40da-109">Per ulteriori informazioni su come eseguire la migrazione degli script e aggiornare i pacchetti, vedere [upgrade Integration Services packages](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span><span class="sxs-lookup"><span data-stu-id="b40da-109">For more information about how to migrate scripts and upgrade packages, see [Upgrade Integration Services Packages](../../integration-services/install-windows/upgrade-integration-services-packages.md).</span></span>  
  
## <a name="understanding-migration-failures"></a><span data-ttu-id="b40da-110">Informazioni sugli errori di migrazione</span><span class="sxs-lookup"><span data-stu-id="b40da-110">Understanding Migration Failures</span></span>  
 <span data-ttu-id="b40da-111">Quando si esegue la migrazione degli script, la migrazione può non riuscire a causa di uno dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b40da-111">When you migrate the scripts, the migration can fail because of one of the following reasons:</span></span>  
  
-   <span data-ttu-id="b40da-112">Il punto di ingresso per lo script VSA è stato rinominato.</span><span class="sxs-lookup"><span data-stu-id="b40da-112">The entry point for the VSA script was renamed.</span></span>  
  
     <span data-ttu-id="b40da-113">Il punto di ingresso specifica il metodo nella classe `ScriptMain` nel progetto VSTA chiamato dal runtime di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] come punto di ingresso nel codice dell'attività Script.</span><span class="sxs-lookup"><span data-stu-id="b40da-113">The entry point specifies the method in the `ScriptMain` class in the VSTA project that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] runtime calls as the entry point into the Script task code.</span></span> <span data-ttu-id="b40da-114">La classe `ScriptMain` è la classe predefinita generata dai modelli di script.</span><span class="sxs-lookup"><span data-stu-id="b40da-114">The `ScriptMain` class is the default class that the script templates generate.</span></span>  
  
-   <span data-ttu-id="b40da-115">Nello script VSA non è presente alcun punto di ingresso o sono presenti più punti di ingresso.</span><span class="sxs-lookup"><span data-stu-id="b40da-115">There is no entry point or there are multiple entry points in the VSA script.</span></span>  
  
-   <span data-ttu-id="b40da-116">Non è stato possibile aggiungere riferimenti ad assembly.</span><span class="sxs-lookup"><span data-stu-id="b40da-116">Assembly references could not be added.</span></span>  
  
-   <span data-ttu-id="b40da-117">La classe `ScriptMain` è stata modificata per ereditare dalle altre classi oltre alla classe `ScriptObjectModelSSIS`.</span><span class="sxs-lookup"><span data-stu-id="b40da-117">The `ScriptMain` class was modified to inherit from other classes in addition to the `ScriptObjectModelSSIS` class.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="b40da-118">non [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] supporta l'ereditarietà multipla.</span><span class="sxs-lookup"><span data-stu-id="b40da-118">[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] does not support multiple inheritance.</span></span>  
  
 <span data-ttu-id="b40da-119">Non è possibile convertire uno script VSA che usa [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] in uno script VSTA che usa [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b40da-119">You cannot convert a VSA script that uses [!INCLUDE[vbprvblong](../../includes/vbprvblong-md.md)] to a VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="b40da-120">Tuttavia, è possibile creare un nuovo script VSTA che utilizza [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b40da-120">However, you can create a new VSTA script that uses [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csharp_orcas_long](../../includes/csharp-orcas-long-md.md)].</span></span> <span data-ttu-id="b40da-121">Per altre informazioni, vedere [Scrittura di codice e debug dell'attività Script](../../integration-services/control-flow/script-task.md) e [Codifica e debug del componente Script](../../integration-services/data-flow/transformations/script-component.md).</span><span class="sxs-lookup"><span data-stu-id="b40da-121">For more information, see [Coding and Debugging the Script Task](../../integration-services/control-flow/script-task.md) and [Coding and Debugging the Script Component](../../integration-services/data-flow/transformations/script-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b40da-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b40da-122">See Also</span></span>  
 [<span data-ttu-id="b40da-123">Estensione di pacchetti tramite scripting</span><span class="sxs-lookup"><span data-stu-id="b40da-123">Extending Packages with Scripting</span></span>](../../relational-databases/server-management-objects-smo/tasks/scripting.md)  
  
  
