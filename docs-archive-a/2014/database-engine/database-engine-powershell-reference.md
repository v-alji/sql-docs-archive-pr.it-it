---
title: Guida di riferimento a PowerShell per il motore di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3c379a43-c497-47dd-8e7d-2b015c068bb7
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2d72f9fcedee02e475369c32a7c263578c9ff156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629589"
---
# <a name="database-engine-powershell-reference"></a><span data-ttu-id="2b6d4-102">Guida di riferimento a PowerShell per il motore di database</span><span class="sxs-lookup"><span data-stu-id="2b6d4-102">Database Engine PowerShell Reference</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="2b6d4-103">include un set di cmdlet di Windows PowerShell 2.0 cmdlet per l'esecuzione di azioni comuni in [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b6d4-103">includes a set of Windows PowerShell 2.0 cmdlets for performing common actions in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="2b6d4-104">È possibile inoltre convertire espressioni di query e Uniform Resource Name (URN) nei percorsi di SQL Server PowerShell o utilizzarli per specificare uno o più oggetti in [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b6d4-104">In addition, Query Expressions and Uniform Resource Names (URN) can be converted to SQL Server PowerShell paths, or used to specify one or more objects in the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="2b6d4-105">Cmdlet del motore di database</span><span class="sxs-lookup"><span data-stu-id="2b6d4-105">Database Engine Cmdlets</span></span>  
 [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] <span data-ttu-id="2b6d4-106">include un numero relativamente basso di cmdlet per il [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b6d4-106">includes relatively few cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="2b6d4-107">La maggior parte degli script di PowerShell che funzionano con [!INCLUDE[ssDE](../includes/ssde-md.md)] utilizzano il provider di PowerShell per SQL Server e i modelli a oggetti di facilità di gestione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2b6d4-107">Most PowerShell scripts working with the [!INCLUDE[ssDE](../includes/ssde-md.md)] use the SQL Server PowerShell provider and the manageability object models.</span></span> <span data-ttu-id="2b6d4-108">Per altre informazioni, vedere [Provider PowerShell per SQL Server](../powershell/sql-server-powershell-provider.md).</span><span class="sxs-lookup"><span data-stu-id="2b6d4-108">For more information, see [SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md).</span></span>  
  
 <span data-ttu-id="2b6d4-109">Per informazioni sulla Guida dei cmdlet di SQL Server in un ambiente Windows PowerShell, vedere [Visualizzazione della Guida di SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2b6d4-109">To learn how to get help about the SQL Server cmdlets in a Windows PowerShell environment, see [Get Help SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="2b6d4-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2b6d4-110">In This Section</span></span>  
 <span data-ttu-id="2b6d4-111">In questa sezione sono incluse informazioni sui cmdlet indicati.</span><span class="sxs-lookup"><span data-stu-id="2b6d4-111">This section contains information about these cmdlets.</span></span>  
  
|<span data-ttu-id="2b6d4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b6d4-112">Description</span></span>|<span data-ttu-id="2b6d4-113">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2b6d4-113">Cmdlet</span></span>|  
|-----------------|------------|  
|<span data-ttu-id="2b6d4-114">Esegue script Transact-SQL e XQuery, ad esempio script che possono essere eseguiti tramite l'utilità `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="2b6d4-114">Runs Transact-SQL and XQuery scripts, such as scripts that can be run using the `sqlcmd` utility.</span></span>|[<span data-ttu-id="2b6d4-115">Cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="2b6d4-115">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="2b6d4-116">Valuta se un oggetto Motore di database è conforme alla gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="2b6d4-116">Evaluates whether a Database Engine object complies with a Policy-based Management policy.</span></span>|[<span data-ttu-id="2b6d4-117">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="2b6d4-117">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
  
### <a name="information-about-other-cmdlets"></a><span data-ttu-id="2b6d4-118">Informazioni su altri cmdlet</span><span class="sxs-lookup"><span data-stu-id="2b6d4-118">Information About Other Cmdlets</span></span>  
 <span data-ttu-id="2b6d4-119">I cmdlet `Encode-Sqlname` e `Decode-Sqlname` consentono di specificare identificatori SQL Server che contengono caratteri non supportati nei percorsi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b6d4-119">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets help you specify SQL Server identifiers that contain characters not supported in PowerShell paths.</span></span> <span data-ttu-id="2b6d4-120">Per altre informazioni, vedere [Identificatori di SQL Server in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2b6d4-120">For more information, see [SQL Server Identifiers in PowerShell](../powershell/sql-server-identifiers-in-powershell.md).</span></span>  
  
 <span data-ttu-id="2b6d4-121">Utilizzare il cmdlet `Convert-UrnToPath` per convertire un Unique Resource Name per un oggetto [!INCLUDE[ssDE](../includes/ssde-md.md)] in un percorso del provider PowerShell per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2b6d4-121">Use the `Convert-UrnToPath` cmdlet to convert a Unique Resource Name for a [!INCLUDE[ssDE](../includes/ssde-md.md)] object to a path for the SQL Server PowerShell provider.</span></span> <span data-ttu-id="2b6d4-122">Per altre informazioni, vedere [Conversione di URN in percorsi di provider di SQL Server](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span><span class="sxs-lookup"><span data-stu-id="2b6d4-122">For more information, see [Convert URNs to SQL Server Provider Paths](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md).</span></span>  
  
## <a name="query-expressions-and-unique-resource-names"></a><span data-ttu-id="2b6d4-123">Espressioni di query e Unique Resource Name</span><span class="sxs-lookup"><span data-stu-id="2b6d4-123">Query Expressions and Unique Resource Names</span></span>  
 <span data-ttu-id="2b6d4-124">Le espressioni di query sono stringhe che utilizzano una sintassi analoga a XPath per specificare un set di criteri utilizzato per enumerare uno o più oggetti in una gerarchia del modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="2b6d4-124">Query expressions are strings that use syntax similar to XPath to specify a set of criteria that enumerate one or more objects in an object model hierarchy.</span></span> <span data-ttu-id="2b6d4-125">L'URN (Unique Resource Name) è un tipo specifico di stringa di espressione di query che identifica un singolo oggetto in modo univoco.</span><span class="sxs-lookup"><span data-stu-id="2b6d4-125">A Unique Resource Name (URN) is a specific type of query expression string that uniquely identifies a single object.</span></span> <span data-ttu-id="2b6d4-126">Per altre informazioni, vedere [Espressioni di query e Uniform Resource Name](../powershell/query-expressions-and-uniform-resource-names.md).</span><span class="sxs-lookup"><span data-stu-id="2b6d4-126">For more information, see [Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b6d4-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b6d4-127">See Also</span></span>  
 [<span data-ttu-id="2b6d4-128">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b6d4-128">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
  
  
