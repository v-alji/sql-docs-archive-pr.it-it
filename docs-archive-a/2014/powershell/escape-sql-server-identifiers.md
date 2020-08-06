---
title: Identificatori di escape di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 8a73e945-daa6-4e5d-93da-10f000f1f3a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1821187632aeeea0b7a18bf9c4d51d933e947d43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628764"
---
# <a name="escape-sql-server-identifiers"></a><span data-ttu-id="64ea1-102">Identificatori di escape di SQL Server</span><span class="sxs-lookup"><span data-stu-id="64ea1-102">Escape SQL Server Identifiers</span></span>
  <span data-ttu-id="64ea1-103">Spesso è possibile utilizzare l'apice inverso di Windows PowerShell (\`) come carattere di escape per i caratteri consentiti negli identificatori delimitati di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ma non per i nomi dei percorsi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64ea1-103">You can often use the Windows PowerShell back-tick escape character (\`) to escape characters that are allowed in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] delimited identifiers but not Windows PowerShell path names.</span></span> <span data-ttu-id="64ea1-104">Tuttavia, alcuni caratteri non supportano l'utilizzo dei caratteri di escape.</span><span class="sxs-lookup"><span data-stu-id="64ea1-104">Some characters, however, cannot be escaped.</span></span> <span data-ttu-id="64ea1-105">Ad esempio, non è possibile utilizzare i caratteri di escape per i due punti (:) in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64ea1-105">For example, you cannot escape the colon character (:) in Windows PowerShell.</span></span> <span data-ttu-id="64ea1-106">Gli identificatori che contengono tale carattere devono essere codificati.</span><span class="sxs-lookup"><span data-stu-id="64ea1-106">Identifiers with that character must be encoded.</span></span> <span data-ttu-id="64ea1-107">La codifica è più affidabile dell'utilizzo dei caratteri di escape in quanto è supportata da tutti i caratteri.</span><span class="sxs-lookup"><span data-stu-id="64ea1-107">Encoding is more reliable than escaping because encoding works for all characters.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="64ea1-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="64ea1-108">Before You Begin</span></span>  
 <span data-ttu-id="64ea1-109">L'apice inverso (\`) è posto generalmente sul tasto superiore sinistro della tastiera, sotto il tasto ESC.</span><span class="sxs-lookup"><span data-stu-id="64ea1-109">The back-tick character (\`) is usually on the key in the upper left of the keyboard, under the ESC key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="64ea1-110">Esempi</span><span class="sxs-lookup"><span data-stu-id="64ea1-110">Examples</span></span>  
 <span data-ttu-id="64ea1-111">Di seguito è riportato un esempio di utilizzo dei caratteri di escape in un carattere #:</span><span class="sxs-lookup"><span data-stu-id="64ea1-111">This is an example of escaping a # character:</span></span>  
  
```  
cd SQLSERVER:\SQL\MyComputer\MyInstance\MyDatabase\MySchema\`#MyTempTable  
```  
  
 <span data-ttu-id="64ea1-112">Di seguito viene riportato un esempio dell'utilizzo di caratteri di escape parentesi in caso di specifica (impostazioni locali) come nome del computer:</span><span class="sxs-lookup"><span data-stu-id="64ea1-112">This is an example of escaping the parenthesis when specifying (local) as a computer name:</span></span>  
  
```  
Set-Location SQLSERVER:\SQL\`(local`)\DEFAULT  
```  
  
## <a name="see-also"></a><span data-ttu-id="64ea1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64ea1-113">See Also</span></span>  
 <span data-ttu-id="64ea1-114">[Identificatori di SQL Server in PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="64ea1-114">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="64ea1-115">[Provider di SQL Server PowerShell](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="64ea1-115">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="64ea1-116">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="64ea1-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
  
  
