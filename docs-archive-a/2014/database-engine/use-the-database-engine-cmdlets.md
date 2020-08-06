---
title: Usare cmdlet del motore di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Cmdlets [SQL Server], Encode-Sqlname
- Encode-Sqlname cmdlet
- PowerShell [SQL Server], Encode-Sqlname
- Convert-UrnToPath cmdlet
- PowerShell [SQL Server], cmdlets
- Cmdlets [SQL Server]
- PowerShell [SQL Server], Convert-UrnToPath
- Cmdlets [SQL Server], Convert-UrnToPath
- Decode-Sqlname cmdlet
- PowerShell [SQL Server], Decode-Sqlname
- Cmdlets [SQL Server], Decode-Sqlname
ms.assetid: 720aa982-09ae-41a3-b603-a91004cfbe3e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 015500c7c985f9f1a1d190954406844f3b184932
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624299"
---
# <a name="use-the-database-engine-cmdlets"></a><span data-ttu-id="2d7e6-102">Utilizzo di cmdlet del motore di database</span><span class="sxs-lookup"><span data-stu-id="2d7e6-102">Use the Database Engine cmdlets</span></span>
  <span data-ttu-id="2d7e6-103">I cmdlet di Windows PowerShell sono comandi a una sola funzione che in genere presentano una convenzione di denominazione verbo-nome, ad esempio **Get-Help** o **Set-MachineName**.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-103">Windows PowerShell cmdlets are single-function commands that typically have a verb-noun naming convention, such as **Get-Help** or **Set-MachineName**.</span></span> <span data-ttu-id="2d7e6-104">Il provider [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per Windows PowerShell fornisce cmdlet specifici di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d7e6-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider for Windows PowerShell supplies cmdlets specific to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="database-engine-cmdlets"></a><span data-ttu-id="2d7e6-105">Cmdlet del motore di database</span><span class="sxs-lookup"><span data-stu-id="2d7e6-105">Database Engine cmdlets</span></span>  
 [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="2d7e6-106">implementa un numero ridotto di cmdlet per [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d7e6-106">implements a small number of cmdlets for the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="2d7e6-107">Questi cmdlet vengono utilizzati principalmente per eseguire script Transact-SQL esistenti dai nuovi script di PowerShell, valutare criteri di gestione basata su criteri e aiutare nella specifica degli identificatori di SQL Server nei percorsi del provider SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-107">These cmdlets are primarily used to run existing Transact-SQL scripts from new PowerShell scripts, evaluate policy-based management policies, and aid in specifying SQL Server identifiers in SQL Server Provider paths.</span></span>  
  
 <span data-ttu-id="2d7e6-108">La maggior parte degli script di Windows PowerShell funzionano con [!INCLUDE[ssDE](../includes/ssde-md.md)] tramite il provider SQL Server PowerShell e i modelli a oggetti di facilità di gestione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-108">Most Windows PowerShell scripts work with the [!INCLUDE[ssDE](../includes/ssde-md.md)] by using the SQL Server PowerShell provider and the SQL Server manageability object models.</span></span> <span data-ttu-id="2d7e6-109">Per altre informazioni, vedere [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2d7e6-109">For more information, see [SQL Server PowerShell](../powershell/sql-server-powershell.md).</span></span>  
  
### <a name="get-cmdlet-help"></a><span data-ttu-id="2d7e6-110">Ottenere la Guida sui cmdlet</span><span class="sxs-lookup"><span data-stu-id="2d7e6-110">Get Cmdlet Help</span></span>  
 <span data-ttu-id="2d7e6-111">Nell'ambiente di Windows PowerShell il cmdlet **Get-Help** offre informazioni della Guida su ogni cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-111">In the Windows PowerShell environment, the **Get-Help** cmdlet provides help information for each cmdlet.</span></span> <span data-ttu-id="2d7e6-112">Il cmdlet**Get-Help** restituisce informazioni come la sintassi, le definizioni dei parametri, i tipi di input e di output e una descrizione dell'azione eseguita dal cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-112">**Get-Help** returns information such as the syntax, parameter definitions, input and output types, and a description of the action performed by the cmdlet.</span></span> <span data-ttu-id="2d7e6-113">Per altre informazioni, vedere [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="2d7e6-113">For more information, see [Get Help SQL Server PowerShell](../../2014/database-engine/get-help-sql-server-powershell.md).</span></span>  
  
### <a name="partial-parameter-names"></a><span data-ttu-id="2d7e6-114">Nomi di parametri parziali</span><span class="sxs-lookup"><span data-stu-id="2d7e6-114">Partial Parameter Names</span></span>  
 <span data-ttu-id="2d7e6-115">Non è necessario specificare il nome completo di un parametro di un cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-115">You do not have to specify the entire name of a cmdlet parameter.</span></span> <span data-ttu-id="2d7e6-116">Basta specificare una parte del nome sufficiente a identificarlo in modo univoco rispetto agli altri parametri che sono supportati dal cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-116">You only have to specify enough of the name to uniquely separate it from the other parameters that are supported by the cmdlet.</span></span> <span data-ttu-id="2d7e6-117">Negli esempi che seguono vengono illustrati tre modi di specificare il parametro **Invoke-Sqlcmd -QueryTimeout** :</span><span class="sxs-lookup"><span data-stu-id="2d7e6-117">For example, these examples show three ways of specifying the **Invoke-Sqlcmd -QueryTimeout** parameter:</span></span>  
  
```powershell
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTimeout 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryTime 3  
Invoke-Sqlcmd -Query "SELECT @@VERSION;" -QueryT 3  
```  
  
## <a name="database-engine-cmdlet-tasks"></a><span data-ttu-id="2d7e6-118">Attività del cmdlet del motore di database</span><span class="sxs-lookup"><span data-stu-id="2d7e6-118">Database Engine cmdlet Tasks</span></span>  
  
|<span data-ttu-id="2d7e6-119">Descrizione dell'attività</span><span class="sxs-lookup"><span data-stu-id="2d7e6-119">Task Description</span></span>|<span data-ttu-id="2d7e6-120">Argomento</span><span class="sxs-lookup"><span data-stu-id="2d7e6-120">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="2d7e6-121">Descrive l'uso di **Invoke-Sqlcmd** per eseguire script o comandi di **sqlcmd** che contengono le istruzioni [!INCLUDE[tsql](../includes/tsql-md.md)] o XQuery.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-121">Describes using **Invoke-Sqlcmd** to run **sqlcmd** scripts or commands that contain [!INCLUDE[tsql](../includes/tsql-md.md)] or XQuery statements.</span></span> <span data-ttu-id="2d7e6-122">Può accettare l'input di **sqlcmd** come parametro di input della stringa di caratteri o come nome di un file script da aprire.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-122">It can accept the **sqlcmd** input as either a character string input parameter, or as the name of a script file to open.</span></span>|[<span data-ttu-id="2d7e6-123">Cmdlet Invoke-Sqlcmd</span><span class="sxs-lookup"><span data-stu-id="2d7e6-123">Invoke-Sqlcmd cmdlet</span></span>](../../2014/database-engine/invoke-sqlcmd-cmdlet.md)|  
|<span data-ttu-id="2d7e6-124">Descrive l'uso di **Invoke-PolicyEvaluation** per indicare se un set di destinazioni di oggetti [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] è conforme alle condizioni definite nei criteri di gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-124">Describes using **Invoke-PolicyEvaluation** to report whether a target set of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects comply with the conditions that are defined in policy-based management policies.</span></span> <span data-ttu-id="2d7e6-125">Facoltativamente, il cmdlet può essere utilizzato per riconfigurare qualsiasi opzione impostabile negli oggetti di destinazione che non sono conformi alle condizioni dei criteri.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-125">Optionally, the cmdlet can be used to reconfigure any settable options in the target objects that do not comply with the policy conditions.</span></span>|[<span data-ttu-id="2d7e6-126">cmdlet Invoke-PolicyEvaluation</span><span class="sxs-lookup"><span data-stu-id="2d7e6-126">Invoke-PolicyEvaluation cmdlet</span></span>](../../2014/database-engine/invoke-policyevaluation-cmdlet.md)|  
|<span data-ttu-id="2d7e6-127">Viene descritto l'utilizzo di `Encode-Sqlname` e `Decode-Sqlname` per gestire identificatori SQL Server che contengono caratteri non supportati nei percorsi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-127">Describes using `Encode-Sqlname` and `Decode-Sqlname` to handle SQL Server identifiers that contain characters not supported in Windows PowerShell paths.</span></span>|[<span data-ttu-id="2d7e6-128">Codificare e decodificare identificatori di SLQ Server</span><span class="sxs-lookup"><span data-stu-id="2d7e6-128">Encode and Decode SQL Server Identifiers</span></span>](../powershell/encode-and-decode-sql-server-identifiers.md)|  
|<span data-ttu-id="2d7e6-129">Viene descritto l'utilizzo di `Convert-UrnToPath` per convertire un nome di risorsa uniforme (Uniform Resource Name, URN) dell'oggetto facilità di gestione di SQL Server nel percorso del provider SQL Server equivalente.</span><span class="sxs-lookup"><span data-stu-id="2d7e6-129">Describes using `Convert-UrnToPath` to convert a SQL Server Manageability Object Uniform Resource Name (URN) to the equivalent SQL Server Provider path.</span></span>|[<span data-ttu-id="2d7e6-130">Conversione di URN in percorsi di provider di SQL Server</span><span class="sxs-lookup"><span data-stu-id="2d7e6-130">Convert URNs to SQL Server Provider Paths</span></span>](../../2014/database-engine/convert-urns-to-sql-server-provider-paths.md)|  
  
## <a name="see-also"></a><span data-ttu-id="2d7e6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d7e6-131">See Also</span></span>  
 <span data-ttu-id="2d7e6-132">[Provider di SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="2d7e6-132">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 <span data-ttu-id="2d7e6-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="2d7e6-133">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 [<span data-ttu-id="2d7e6-134">Panoramica dei cmdlet di PowerShell per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2d7e6-134">Overview of PowerShell Cmdlets for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](availability-groups/windows/overview-of-powershell-cmdlets-for-always-on-availability-groups-sql-server.md)  
  
  
