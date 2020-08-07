---
title: SERVERPROPERTY restituisce il risultato corretto per la proprietà LCID in SQL Server 2005 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- SERVERPROPERTY function
ms.assetid: 833a2fc9-b480-4697-aa7b-9677e78ee0b4
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebb125a86e6e30f2c3638004593da7657f02f1a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715971"
---
# <a name="serverproperty-returns-correct-result-for-lcid-property-in-sql-server-2005"></a><span data-ttu-id="90aaf-102">In SQL Server 2005 SERVERPROPERTY restituisce il valore corretto della proprietà LCID</span><span class="sxs-lookup"><span data-stu-id="90aaf-102">SERVERPROPERTY returns correct result for LCID property in SQL Server 2005</span></span>
  <span data-ttu-id="90aaf-103">Se si esegue SERVERPROPERTY ('LCID') su server che utilizzano regole di confronto binarie, la funzione restituisce l'identificatore delle impostazioni locali (LCID) di Windows corrispondente alle regole di confronto del server.</span><span class="sxs-lookup"><span data-stu-id="90aaf-103">When SERVERPROPERTY('LCID') is run on binary collation servers, the function returns the Windows locale identifier (LCID) that corresponds to the collation of the server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90aaf-104">Per i file batch e di traccia che contengono riferimenti a SERVERPROPERTY ('LCID') e vengono eseguiti in altre istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], questa modifica di comportamento verrà rilevata solo se le regole di confronto delle altre istanze sono identiche a quelle dell'istanza corrente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="90aaf-104">For batch and trace files that contain references to SERVERPROPERTY ('LCID') and are run on other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Upgrade Advisor will detect this behavior change only if the other instances have the same collation as the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="90aaf-105">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="90aaf-105">Corrective Action</span></span>  
 <span data-ttu-id="90aaf-106">Modificare le applicazioni per prevedere che SERVERPROPERTY ('LCID') restituisca l'identificatore LCID di Windows che corrisponde alle regole di confronto del server.</span><span class="sxs-lookup"><span data-stu-id="90aaf-106">Modify applications to expect SERVERPROPERTY('LCID') to return the Windows LCID that corresponds to the collation of the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90aaf-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90aaf-107">See Also</span></span>  
 <span data-ttu-id="90aaf-108">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="90aaf-108">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="90aaf-109">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="90aaf-109">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
