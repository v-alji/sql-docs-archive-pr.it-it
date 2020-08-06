---
title: FOR BROWSe non è consentito nelle viste in modalità di compatibilità 90 o successive | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], FOR BROWSE clause
- FOR BROWSE clause
ms.assetid: 8f49b1c1-d877-4c46-b988-f8cdd8ac0925
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 251e0ae2ff6f19dfcff3b0f8056f6697c1bfc40d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635386"
---
# <a name="for-browse-is-not-allowed-in-views-in-90-or-later-compatibility-modes"></a><span data-ttu-id="b2ade-102">FOR BROWSE non consentita nelle viste in modalità di compatibilità 90 o successiva</span><span class="sxs-lookup"><span data-stu-id="b2ade-102">FOR BROWSE is not allowed in views in 90 or later compatibility modes</span></span>
  <span data-ttu-id="b2ade-103">È stata rilevata la clausola FOR BROWSE in una vista.</span><span class="sxs-lookup"><span data-stu-id="b2ade-103">Upgrade Advisor detected the use of the FOR BROWSE clause in a view.</span></span> <span data-ttu-id="b2ade-104">La clausola FOR BROWSE è consentita (e ignorata) nelle viste se la modalità di compatibilità del database è impostata su 80.</span><span class="sxs-lookup"><span data-stu-id="b2ade-104">The FOR BROWSE clause is allowed (and ignored) in views when the database compatibility mode is set to 80.</span></span> <span data-ttu-id="b2ade-105">Se è impostata la modalità di compatibilità 90 o successiva, la clausola FOR BROWSE non è consentita nelle viste.</span><span class="sxs-lookup"><span data-stu-id="b2ade-105">The FOR BROWSE clause is not allowed in views when the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b2ade-106">Componente</span><span class="sxs-lookup"><span data-stu-id="b2ade-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="b2ade-107">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="b2ade-107">Corrective Action</span></span>  
 <span data-ttu-id="b2ade-108">Quando si esegue l'aggiornamento, la modalità di compatibilità dei database utente non cambia.</span><span class="sxs-lookup"><span data-stu-id="b2ade-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="b2ade-109">Prima di impostare la modalità di compatibilità del database su 90 o successiva, rimuovere la clausola FOR BROWSE dalle definizioni di viste.</span><span class="sxs-lookup"><span data-stu-id="b2ade-109">Before you change the database compatibility mode to 90 or later, remove the FOR BROWSE clause from view definitions.</span></span> <span data-ttu-id="b2ade-110">Per ulteriori informazioni, vedere "sp_dbcmptlevel" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2ade-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2ade-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2ade-111">See Also</span></span>  
 <span data-ttu-id="b2ade-112">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b2ade-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b2ade-113">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="b2ade-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
