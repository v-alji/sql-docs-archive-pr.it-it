---
title: L'aggiornamento modificherà l'account proxy utente SQL Server Agent alla UpgradedProxyAccount temporanea | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
ms.assetid: cd2d08c3-4e56-4034-8b68-0c78df8b5471
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2bca80580a50f2acebed1b6fbea2dec1f6458dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623730"
---
# <a name="upgrading-will-change-the-sql-server-agent-user-proxy-account-to-the-temporary-upgradedproxyaccount"></a><span data-ttu-id="f43ea-102">In seguito all'aggiornamento l'account proxy utente per SQL Server Agent verrà sostituito dall'account temporaneo UpgradedProxyAccount</span><span class="sxs-lookup"><span data-stu-id="f43ea-102">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>
  <span data-ttu-id="f43ea-103">I piani di manutenzione del database con il log shipping abilitato non verranno abilitati dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="f43ea-103">Database maintenance plans that have log shipping enabled will not be enabled after upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f43ea-104">Componente</span><span class="sxs-lookup"><span data-stu-id="f43ea-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f43ea-105">Agent</span><span class="sxs-lookup"><span data-stu-id="f43ea-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="f43ea-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f43ea-106">Description</span></span>  
 <span data-ttu-id="f43ea-107">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è disponibile un nuovo set di funzioni di log shipping che non sono direttamente compatibili con i piani di manutenzione del database.</span><span class="sxs-lookup"><span data-stu-id="f43ea-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides a new set of log shipping functions that are not directly compatible with database maintenance plans.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f43ea-108">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="f43ea-108">Corrective Action</span></span>  
 <span data-ttu-id="f43ea-109">Gli utenti di [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] i cui piani di manutenzione del database contengono funzioni di log shipping devono configurare il log shipping utilizzando le nuove funzioni.</span><span class="sxs-lookup"><span data-stu-id="f43ea-109">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] users that have database maintenance plans that contain log shipping functions should configure log shipping by using the new functions.</span></span> <span data-ttu-id="f43ea-110">Per ulteriori informazioni, cercare "log shipping" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f43ea-110">For more information, search on "log shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f43ea-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f43ea-111">See Also</span></span>  
 <span data-ttu-id="f43ea-112">[SQL Server Agent log shipping categoria di processi causa l'esito negativo dell'aggiornamento](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="f43ea-112">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 [<span data-ttu-id="f43ea-113">Il log shipping non verrà eseguito dopo l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="f43ea-113">Log shipping will not run after upgrading</span></span>](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md)  
  
  
