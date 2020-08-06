---
title: Gestire il completamento alla pressione del tasto TAB (SQL Server PowerShell) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 6296848a-890f-4ad3-8d9f-92ed6a79aa00
author: stevestein
ms.author: sstein
ms.openlocfilehash: 72bcf96245c536d6ea444bc1d7964b7579e793c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637948"
---
# <a name="manage-tab-completion-sql-server-powershell"></a><span data-ttu-id="2f0a5-102">Gestione del completamento alla pressione del tasto TAB (SQL Server PowerShell)</span><span class="sxs-lookup"><span data-stu-id="2f0a5-102">Manage Tab Completion (SQL Server PowerShell)</span></span>
  <span data-ttu-id="2f0a5-103">Gli snap-in di PowerShell per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] introducono tre variabili (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems` e `$SqlServerIncludeSystemObjects`) per controllare il completamento alla pressione del tasto TAB di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins introduce three variables (`$SqlServerMaximumTabCompletion`, `$SqlServerMaximumChildItems`, and `$SqlServerIncludeSystemObjects`) to control Windows PowerShell tab completion.</span></span> <span data-ttu-id="2f0a5-104">Il completamento alla pressione del tasto TAB consente di ridurre la digitazione restituendo tabelle di elementi i cui nomi iniziano con la stringa che si sta digitando.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-104">Tab completion reduces the amount of typing you must do by returning tables of items whose names start with the string you are typing.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="2f0a5-105">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2f0a5-105">Before You Begin</span></span>  
 <span data-ttu-id="2f0a5-106">Con il completamento alla pressione del tasto TAB di Windows PowerShell, dopo aver digitato parte del nome di un percorso o di un cmdlet, è possibile premere il tasto TAB per ottenere un elenco degli elementi il cui nome corrisponde a quanto già digitato.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-106">With Windows PowerShell tab-completion, when you have typed part of a path or cmdlet name, you can hit the Tab key to get a list of the items whose names match what you have already typed.</span></span> <span data-ttu-id="2f0a5-107">È quindi possibile selezionare l'elemento desiderato dall'elenco senza digitare il resto del nome.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-107">You can then select the item you want from the list without having to type the rest of the name.</span></span>  
  
 <span data-ttu-id="2f0a5-108">Se si utilizza un database che contiene molti oggetti, l'elenco di completamento alla pressione del tasto TAB può risultare molto lungo.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-108">If you are working in a database that has a lot of objects, the tab-completion lists can become very large.</span></span> <span data-ttu-id="2f0a5-109">Anche alcuni tipi di oggetto di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , ad esempio le viste, includono numerosi oggetti di sistema.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-109">Some [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] object types, such as views, also have large numbers of system objects.</span></span>  
  
 <span data-ttu-id="2f0a5-110">Gli snap-in di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] introducono tre variabili di sistema che possono essere usate per controllare la quantità di informazioni generata dal completamento alla pressione del tasto TAB e da **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-110">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] snap-ins introduces three system variables that you can use to control the amount of information presented by tab-completion and **Get-ChildItem**.</span></span>  
  
 <span data-ttu-id="2f0a5-111">**$SqlServerMaximumTabCompletion =** *n*</span><span class="sxs-lookup"><span data-stu-id="2f0a5-111">**$SqlServerMaximumTabCompletion =** *n*</span></span>  
 <span data-ttu-id="2f0a5-112">Specifica il numero massimo di oggetti da includere in un elenco di completamento alla pressione del tasto TAB.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-112">Specifies the maximum number of objects to include in a tab-completion list.</span></span> <span data-ttu-id="2f0a5-113">Se si seleziona il tasto TAB in un nodo del percorso con più di *n* oggetti, l'elenco di completamento alla pressione del tasto TAB viene troncato in corrispondenza di *n*.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-113">If you select Tab at a path node having more than *n* objects, the tab-completion list is truncated at *n*.</span></span> <span data-ttu-id="2f0a5-114">*n* è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-114">*n* is an integer.</span></span> <span data-ttu-id="2f0a5-115">L'impostazione predefinita è 0, che indica che non esiste alcun limite al numero di oggetti elencati.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-115">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="2f0a5-116">**$SqlServerMaximumChildItems =** *n*</span><span class="sxs-lookup"><span data-stu-id="2f0a5-116">**$SqlServerMaximumChildItems =** *n*</span></span>  
 <span data-ttu-id="2f0a5-117">Specifica il numero massimo di oggetti visualizzati da **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-117">Specifies the maximum number of objects displayed by **Get-ChildItem**.</span></span> <span data-ttu-id="2f0a5-118">Se **Get-ChildItem** viene eseguito in un nodo del percorso con più di *n* oggetti, l'elenco viene troncato in corrispondenza di *n*.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-118">If **Get-ChildItem** is run at a path node having more than *n* objects, the list is truncated at *n*.</span></span> <span data-ttu-id="2f0a5-119">*n* è un numero intero.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-119">*n* is an integer.</span></span> <span data-ttu-id="2f0a5-120">L'impostazione predefinita è 0, che indica che non esiste alcun limite al numero di oggetti elencati.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-120">0 is the default setting, and means there is no limit to the number of objects listed.</span></span>  
  
 <span data-ttu-id="2f0a5-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span><span class="sxs-lookup"><span data-stu-id="2f0a5-121">**$SqlServerIncludeSystemObjects =** { **$True** | **$False** }</span></span>  
 <span data-ttu-id="2f0a5-122">Se **$True**, gli oggetti di sistema vengono visualizzati dal completamento alla pressione del tasto TAB e da **Get-ChildItem**.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-122">If **$True**, system objects are displayed by tab-completion and **Get-ChildItem**.</span></span> <span data-ttu-id="2f0a5-123">Se **$False**, non viene visualizzato alcun oggetto di sistema.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-123">If **$False**, no system objects are displayed.</span></span> <span data-ttu-id="2f0a5-124">L'impostazione predefinita è **$false**.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-124">The default setting is **$False**.</span></span>  
  
## <a name="set-the-sql-server-tab-completion-variables"></a><span data-ttu-id="2f0a5-125">Impostazione delle variabili per il completamento alla pressione del tasto TAB</span><span class="sxs-lookup"><span data-stu-id="2f0a5-125">Set the SQL Server Tab Completion Variables</span></span>  
 <span data-ttu-id="2f0a5-126">Per tutte le variabile di cui si desidera modificare il valore predefinito, impostare la variabile sul nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="2f0a5-126">For any of the variables you want to change from the default value, set the variable to the new value.</span></span>  
  
### <a name="example-powershell"></a><span data-ttu-id="2f0a5-127">Esempio (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="2f0a5-127">Example (PowerShell)</span></span>  
 <span data-ttu-id="2f0a5-128">Nell'esempio seguente vengono impostate tutte e tre le variabili e vengono elencate le relative impostazioni:</span><span class="sxs-lookup"><span data-stu-id="2f0a5-128">The following example sets all three variables and lists their settings:</span></span>  
  
```powershell
$SqlServerMaximumTabCompletion = 20  
$SqlServerMaximumChildItems = 10  
$SqlServerIncludeSystemObjects = $False  
dir variable:sqlserver*  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f0a5-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f0a5-129">See Also</span></span>  
 [<span data-ttu-id="2f0a5-130">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f0a5-130">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
