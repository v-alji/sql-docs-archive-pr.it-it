---
title: Requisiti dell'account del servizio per l'aggiornamento a SQL Server 2008 in un controller di dominio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- domain controllers
- service accounts
- network service accounts
- local service accounts
ms.assetid: 574245b6-11e2-4849-b0ca-836d673ecd0d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0680e09548e38760f6ac317fec63152486a4e5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628158"
---
# <a name="service-account-requirements-for-upgrading-to-sql-server-2008-on-a-domain-controller"></a><span data-ttu-id="f15fa-102">Requisiti dell'account del servizio per l'aggiornamento a SQL Server 2008 in un controller di dominio</span><span class="sxs-lookup"><span data-stu-id="f15fa-102">Service account requirements for upgrading to SQL Server 2008 on a domain controller</span></span>
  <span data-ttu-id="f15fa-103">È stata rilevata un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione in un servizio di rete o in un account del servizio locale in un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="f15fa-103">Upgrade Advisor detected an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running under a Network Service or Local Service account on a [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller.</span></span> <span data-ttu-id="f15fa-104">Se [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è installato in un controller di dominio [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], non è possibile eseguire i servizi [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con i privilegi dell'account Servizio locale o Servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="f15fa-104">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)] domain controller, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services cannot run under Local Service account or Network Service account privileges.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f15fa-105">Componente</span><span class="sxs-lookup"><span data-stu-id="f15fa-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="f15fa-106">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="f15fa-106">Corrective Action</span></span>  
 <span data-ttu-id="f15fa-107">Assicurarsi che tutti gli account del servizio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] siano assegnati ad account Dominio o Sistema locale.</span><span class="sxs-lookup"><span data-stu-id="f15fa-107">Make sure that all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service accounts are assigned to either Domain accounts or Local System accounts.</span></span> <span data-ttu-id="f15fa-108">Se questa modifica non viene eseguita prima dell'aggiornamento, l'installazione si bloccherà.</span><span class="sxs-lookup"><span data-stu-id="f15fa-108">Failure to make this change before upgrading will block Setup.</span></span> <span data-ttu-id="f15fa-109">Fanno eccezione i servizi writer SQL, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e Active Directory Helper degli account del servizio, per i quali l'utilizzo dell'account servizio di rete è specificato a livello di codice e non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="f15fa-109">The service accounts SQL Writer, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and Active Directory Helper services are exceptions because they are hard-coded to the Network Service account and cannot be changed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f15fa-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f15fa-110">See Also</span></span>  
 <span data-ttu-id="f15fa-111">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f15fa-111">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f15fa-112">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="f15fa-112">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
