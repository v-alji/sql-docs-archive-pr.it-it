---
title: Regole di confronto e tipi di dati di integrazione CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data types [CLR integration]
- parameter collation [CLR integration]
- collations [CLR integration]
ms.assetid: 6ebaed8e-2e2b-4f6d-bf4b-bc25452de441
author: rothja
ms.author: jroth
ms.openlocfilehash: 1a5b0367487aeb80355b8c5c976818e1b6c1ac04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725967"
---
# <a name="collation-and-clr-integration-data-types"></a><span data-ttu-id="57a02-102">Regole di confronto e tipi di dati di integrazione CLR</span><span class="sxs-lookup"><span data-stu-id="57a02-102">Collation and CLR Integration Data Types</span></span>
  <span data-ttu-id="57a02-103">In [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] l'oggetto `CompareInfo` gestisce le regole di confronto.</span><span class="sxs-lookup"><span data-stu-id="57a02-103">In the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], the `CompareInfo` object handles collations.</span></span> <span data-ttu-id="57a02-104">Le API di stringa di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] utilizzano la proprietà `CompareInfo` associata all'oggetto `CultureInfo` del thread corrente per eseguire confronti tra stringhe.</span><span class="sxs-lookup"><span data-stu-id="57a02-104">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] string application programming interfaces (APIs) use the `CompareInfo` property associated with the `CultureInfo` object of the current thread to perform string comparisons.</span></span> <span data-ttu-id="57a02-105">L'impostazione predefinita dell' `CultureInfo` oggetto è basata sulle impostazioni [!INCLUDE[msCoName](../../includes/msconame-md.md)] locali di Windows per il computer in cui [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="57a02-105">The default setting of the `CultureInfo` object is based on the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows locale setting for the computer on which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="57a02-106">Questo determina la semantica del confronto predefinita, se non viene specificata alcuna `CultureInfo` esplicita, per confronti di valori `System.String`.</span><span class="sxs-lookup"><span data-stu-id="57a02-106">This determines the default comparison semantics, if no explicit `CultureInfo` is specified, for comparisons of `System.String` values.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="57a02-107">non modifica in modo esplicito la proprietà `CompareInfo` sulle regole di confronto del database o del server.</span><span class="sxs-lookup"><span data-stu-id="57a02-107">does not explicitly change the `CompareInfo` property to the database or server collation.</span></span> <span data-ttu-id="57a02-108">Se richiesto, gli utenti devono impostare la proprietà `CompareInfo` appropriata nelle routine.</span><span class="sxs-lookup"><span data-stu-id="57a02-108">If required, users must set the appropriate `CompareInfo` property in their routines.</span></span>  
  
## <a name="parameter-collation"></a><span data-ttu-id="57a02-109">Regole di confronto dei parametri</span><span class="sxs-lookup"><span data-stu-id="57a02-109">Parameter Collation</span></span>  
 <span data-ttu-id="57a02-110">Quando si crea una routine CLR (Common Language Runtime) e un parametro di un metodo CLR associato alla routine è di tipo `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] crea un'istanza del parametro con le regole di confronto predefinite del database che contiene la routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="57a02-110">When you create a common language runtime (CLR) routine, and a parameter of a CLR method bound to the routine is of type `SQLString`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] creates an instance of the parameter with the default collation of the database containing the calling routine.</span></span> <span data-ttu-id="57a02-111">Se un parametro non è del tipo `SqlType` (ad esempio, `String` anziché `SQLString`), le informazioni sulle regole di confronto provenienti dal database non vengono associate al parametro.</span><span class="sxs-lookup"><span data-stu-id="57a02-111">If a parameter is not a `SqlType` (for example, `String` rather than `SQLString`), the collation information from the database is not associated with the parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57a02-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57a02-112">See Also</span></span>  
 [<span data-ttu-id="57a02-113">Tipi di dati di SQL Server in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="57a02-113">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
