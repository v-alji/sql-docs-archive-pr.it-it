---
title: Convertire URN in percorsi di provider di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: c9b1b8f1-b117-4e87-9704-2170f62c5c8b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 56c2fdb5f84e57fe3f34348108f14418785659a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628972"
---
# <a name="convert-urns-to-sql-server-provider-paths"></a><span data-ttu-id="1bf6a-102">Conversione di URN in percorsi di provider di SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bf6a-102">Convert URNs to SQL Server Provider Paths</span></span>
  <span data-ttu-id="1bf6a-103">Il modello SMO ( [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Objects) consente di compilare URN (Uniform Resource Name) per gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="1bf6a-103">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Management Object model (SMO) builds Uniform Resource Names (URN) for its objects.</span></span> <span data-ttu-id="1bf6a-104">Ogni URN identifica in modo univoco un oggetto SMO e può essere convertito in un percorso di provider di SQL Server PowerShell tramite il cmdlet `Convert-UrnToPath`.</span><span class="sxs-lookup"><span data-stu-id="1bf6a-104">Each URN uniquely identifies a SMO object, and can be converted to a SQL Server PowerShell provider path by using the `Convert-UrnToPath` cmdlet.</span></span>  
  
## <a name="converting-urns-to-paths"></a><span data-ttu-id="1bf6a-105">Conversione di URN in percorsi</span><span class="sxs-lookup"><span data-stu-id="1bf6a-105">Converting URNs to Paths</span></span>  
 <span data-ttu-id="1bf6a-106">Ciascun URN dispone delle stesse informazioni di un percorso dell'oggetto, ma in formato diverso.</span><span class="sxs-lookup"><span data-stu-id="1bf6a-106">Each URN has the same information as a path to the object, but in a different form.</span></span> <span data-ttu-id="1bf6a-107">Ad esempio, di seguito è riportato il percorso di una tabella:</span><span class="sxs-lookup"><span data-stu-id="1bf6a-107">For example, this is the path to a table:</span></span>  
  
 <span data-ttu-id="1bf6a-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span><span class="sxs-lookup"><span data-stu-id="1bf6a-108">SQLSERVER:\SQL\MyComputer\DEFAULT\Databases\AdventureWorks2012\Tables\Person.Address</span></span>  
  
 <span data-ttu-id="1bf6a-109">Di seguito è riportato l'URN dello stesso oggetto:</span><span class="sxs-lookup"><span data-stu-id="1bf6a-109">And this is the URN to the same object:</span></span>  
  
 <span data-ttu-id="1bf6a-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span><span class="sxs-lookup"><span data-stu-id="1bf6a-110">Server[@Name='MyComputer']\Database[@Name='AdventureWorks2012']\Table[@Name='Address' and @Schema='Person']</span></span>  
  
 <span data-ttu-id="1bf6a-111">Se è stato creato un oggetto SMO in uno script di PowerShell, è possibile fare riferimento alla proprietà `Urn` per ottenere l'URN dell'oggetto e quindi utilizzare il cmdlet `Convert-UrnToPath` per convertire la stringa URN SMO in un percorso di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bf6a-111">If you have created a SMO object in a PowerShell script, you can reference the `Urn` property to get the URN for the object, and then use the `Convert-UrnToPath` cmdlet to convert the SMO URN string to a Windows PowerShell path.</span></span> <span data-ttu-id="1bf6a-112">È quindi possibile utilizzare il provider per passare a posizioni diverse nel percorso.</span><span class="sxs-lookup"><span data-stu-id="1bf6a-112">You can then use the provider to navigate to different locations on the path.</span></span>  
  
 <span data-ttu-id="1bf6a-113">Se i nomi di nodo contengono caratteri estesi non supportati nei nomi di percorso di Windows PowerShell, `Convert-UrnToPath` li codifica nella rappresentazione esadecimale.</span><span class="sxs-lookup"><span data-stu-id="1bf6a-113">If node names contain extended characters that are not supported in Windows PowerShell path names, `Convert-UrnToPath` encodes them in their hexadecimal representation.</span></span> <span data-ttu-id="1bf6a-114">Ad esempio, "My:Table" viene restituito come "My%3ATable".</span><span class="sxs-lookup"><span data-stu-id="1bf6a-114">For example "My:Table" is returned as "My%3ATable".</span></span>  
  
 <span data-ttu-id="1bf6a-115">Per esempi dell'utilizzo del cmdlet, in Windows PowerShell eseguire:</span><span class="sxs-lookup"><span data-stu-id="1bf6a-115">For examples of using the cmdlet, in Windows PowerShell, run:</span></span>  
  
```powershell
Get-Help Convert-UrnToPath -Examples  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bf6a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bf6a-116">See Also</span></span>  
 <span data-ttu-id="1bf6a-117">[Espressioni di query e nomi di risorse uniformi](../powershell/query-expressions-and-uniform-resource-names.md) </span><span class="sxs-lookup"><span data-stu-id="1bf6a-117">[Query Expressions and Uniform Resource Names](../powershell/query-expressions-and-uniform-resource-names.md) </span></span>  
 <span data-ttu-id="1bf6a-118">[Provider di SQL Server PowerShell](../powershell/sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="1bf6a-118">[SQL Server PowerShell Provider](../powershell/sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="1bf6a-119">SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bf6a-119">SQL Server PowerShell</span></span>](../powershell/sql-server-powershell.md)  
