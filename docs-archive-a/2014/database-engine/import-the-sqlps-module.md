---
title: Importare il modulo SQLPS | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: a972c56e-b2af-4fe6-abbd-817406e2c93a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 37e66db05615ce8a285a80e5ac26b0cae411abeb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718702"
---
# <a name="import-the-sqlps-module"></a><span data-ttu-id="04095-102">Importare il modulo SQLPS</span><span class="sxs-lookup"><span data-stu-id="04095-102">Import the SQLPS Module</span></span>
  <span data-ttu-id="04095-103">Il metodo consigliato per gestire [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] da PowerShell consiste nell'importare il modulo `sqlps` in un ambiente Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="04095-103">The recommended way to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] from PowerShell is to import the `sqlps` module into a Windows PowerShell 2.0 environment.</span></span> <span data-ttu-id="04095-104">Il modulo carica e registra gli snap-in e gli assembly di gestibilità di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04095-104">The module loads and registers the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins and manageability assemblies.</span></span>  
  
1.  <span data-ttu-id="04095-105">**Prima di iniziare:**  [sicurezza](#Security)</span><span class="sxs-lookup"><span data-stu-id="04095-105">**Before You Begin:**  [Security](#Security)</span></span>  
  
2.  <span data-ttu-id="04095-106">**Per caricare il modulo:**  [Caricare il Modulo sqlps](#LoadSqlps)</span><span class="sxs-lookup"><span data-stu-id="04095-106">**To load the module:**  [Load the sqlps Module](#LoadSqlps)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="04095-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="04095-107">Before You Begin</span></span>  
 <span data-ttu-id="04095-108">Dopo avere importato il modulo `sqlps` in Windows PowerShell, è quindi possibile:</span><span class="sxs-lookup"><span data-stu-id="04095-108">After importing the `sqlps` module into Windows PowerShell, you can then:</span></span>  
  
-   <span data-ttu-id="04095-109">Eseguire in modo interattivo comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04095-109">Interactively run Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="04095-110">Eseguire file script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04095-110">Run Windows PowerShell script files.</span></span>  
  
-   <span data-ttu-id="04095-111">Eseguire cmdlet di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04095-111">Run [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] cmdlets.</span></span>  
  
-   <span data-ttu-id="04095-112">Utilizzare i percorsi del provider di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per spostarsi nella gerarchia degli oggetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04095-112">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] provider paths to navigate through the hierarchy of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
-   <span data-ttu-id="04095-113">Utilizzare i modelli a oggetti per la gestibilità di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , ad esempio Microsoft.SqlServer.Management.Smo, per gestire oggetti di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="04095-113">Use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] manageability object models (such as Microsoft.SqlServer.Management.Smo) to manage [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="04095-114">I verbi utilizzati nei nomi di due SQL Server cmdlet (`Encode-Sqlname` e `Decode-Sqlname`) non corrispondono ai verbi approvati per Windows PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="04095-114">The verbs used in the names of two SQL Server cmdlets (`Encode-Sqlname` and `Decode-Sqlname`) do not match the approved verbs for Windows PowerShell 2.0.</span></span> <span data-ttu-id="04095-115">Ciò non ha effetto sull'operazione, tuttavia Windows PowerShell genera un avviso quando il modulo `sqlps` viene importato in una sessione.</span><span class="sxs-lookup"><span data-stu-id="04095-115">This has no effect on their operation, but Windows PowerShell raises a warning when the `sqlps` module is imported to a session.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="04095-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="04095-116">Security</span></span>  
 <span data-ttu-id="04095-117">Per impostazione predefinita, Windows PowerShell viene eseguito con i criteri di esecuzione degli script impostati su **Restricted**, che impediscono l'esecuzione degli script di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="04095-117">By default, Windows PowerShell runs with the scripting execution policy set to **Restricted**, which prevents running any Windows PowerShell scripts.</span></span> <span data-ttu-id="04095-118">Per caricare il modulo `sqlps`, è possibile utilizzare il cmdlet `Set-ExecutionPolicy` per abilitare l'esecuzione di script firmati o di qualsiasi script.</span><span class="sxs-lookup"><span data-stu-id="04095-118">To load the `sqlps` module, you can use the `Set-ExecutionPolicy` cmdlet to enable running signed scripts, or any scripts.</span></span> <span data-ttu-id="04095-119">Eseguire solo script da origini attendibili e proteggere tutti i file di input e output utilizzando le autorizzazioni NTFS appropriate.</span><span class="sxs-lookup"><span data-stu-id="04095-119">Only run scripts from trusted sources, and secure all input and output files using the appropriate NTFS permissions.</span></span> <span data-ttu-id="04095-120">Per altre informazioni sull'abilitazione degli script di Windows PowerShell, vedere [Running Windows PowerShell Scripts](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows)(Esecuzione di script di Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="04095-120">For more information about enabling Windows PowerShell scripts, see [Running Windows PowerShell Scripts](https://docs.microsoft.com/powershell/scripting/getting-started/starting-windows-powershell?view=powershell-6#how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows).</span></span>  
  
##  <a name="load-the-sqlps-module"></a><a name="LoadSqlps"></a> <span data-ttu-id="04095-121">Caricare il Modulo sqlps</span><span class="sxs-lookup"><span data-stu-id="04095-121">Load the sqlps Module</span></span>  

### <a name="to-load-the-sqlps-module-in-windows-powershell"></a><span data-ttu-id="04095-122">Per caricare il modulo sqlps in Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="04095-122">To load the sqlps module in Windows PowerShell</span></span>
  
1.  <span data-ttu-id="04095-123">Utilizzare il cmdlet `Set-ExecutionPolicy` per impostare i criteri di esecuzione degli script appropriati.</span><span class="sxs-lookup"><span data-stu-id="04095-123">Use the `Set-ExecutionPolicy` cmdlet to set the appropriate script execution policy.</span></span>  
  
2.  <span data-ttu-id="04095-124">Utilizzare il cmdlet `Import-Module` per importare il modulo sqlps.</span><span class="sxs-lookup"><span data-stu-id="04095-124">Use the `Import-Module` cmdlet to import the sqlps module.</span></span> <span data-ttu-id="04095-125">Specificare il parametro `DisableNameChecking` se si desidera eliminare l'avviso su `Encode-Sqlname` e `Decode-Sqlname`.</span><span class="sxs-lookup"><span data-stu-id="04095-125">Specify the `DisableNameChecking` parameter if you want to suppress the warning about `Encode-Sqlname` and `Decode-Sqlname`.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="04095-126">Esempio (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="04095-126">Example (PowerShell)</span></span>  
 <span data-ttu-id="04095-127">In questo esempio viene caricato il modulo `sqlps` con verifica del nome disabilitata.</span><span class="sxs-lookup"><span data-stu-id="04095-127">This example loads the `sqlps` module with name checking turned off.</span></span>  
  
```powershell
## Import the SQL Server Module.  
  
Import-Module "sqlps" -DisableNameChecking  
```  

## <a name="see-also"></a><span data-ttu-id="04095-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04095-128">See Also</span></span>  
 <span data-ttu-id="04095-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="04095-129">[SQL Server PowerShell](../powershell/sql-server-powershell.md) </span></span>  
 <span data-ttu-id="04095-130">[Provider di SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="04095-130">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="04095-131">Utilizzo di cmdlet del motore di database</span><span class="sxs-lookup"><span data-stu-id="04095-131">Use the Database Engine cmdlets</span></span>](../../2014/database-engine/use-the-database-engine-cmdlets.md)  
