---
title: Opzione di configurazione del server Agent XPs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Agent XPs option
- extended stored procedures [SQL Server], SQL Server Agent
ms.assetid: 2e1c6c64-5ce7-4357-98c7-ac7763a9f9de
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 541c81ea8d9f782a9c1ea391824b90a6fee772d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630054"
---
# <a name="agent-xps-server-configuration-option"></a><span data-ttu-id="75965-102">Opzione di configurazione del server Agent XPs</span><span class="sxs-lookup"><span data-stu-id="75965-102">Agent XPs Server Configuration Option</span></span>
  <span data-ttu-id="75965-103">L'opzione **Agent XPs** consente di abilitare le stored procedure estese del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent nel server.</span><span class="sxs-lookup"><span data-stu-id="75965-103">Use the **Agent XPs** option to enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures on this server.</span></span> <span data-ttu-id="75965-104">Se questa opzione non è attivata, il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non sarà disponibile in Esplora oggetti di [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="75965-104">When this option is not enabled, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent node is not available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer.</span></span>  
  
 <span data-ttu-id="75965-105">Quando si utilizza lo strumento [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per avviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, le stored procedure estese vengono abilitate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="75965-105">When you use the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] tool to start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service, these extended stored procedures are enabled automatically.</span></span> <span data-ttu-id="75965-106">Per ulteriori informazioni, vedere [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="75965-106">For more information, see [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="75965-107">In Esplora oggetti il nodo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent non viene visualizzato a meno che le stored procedure estese non vengano abilitate indipendentemente dallo stato del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="75965-107">Object Explorer does not display the contents of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Agent node unless these extended stored procedures are enabled regardless of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service state.</span></span>  
  
 <span data-ttu-id="75965-108">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="75965-108">The possible values are:</span></span>  
  
-   <span data-ttu-id="75965-109">**0**, che indica che le stored procedure estese di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent non sono disponibili e corrisponde al valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="75965-109">**0**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are not available (the default).</span></span>  
  
-   <span data-ttu-id="75965-110">**1**, che indica che le stored procedure estese di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="75965-110">**1**, indicating that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures are available.</span></span>  
  
 <span data-ttu-id="75965-111">L'impostazione diventa effettiva immediatamente e non richiede l'arresto e il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="75965-111">The setting takes effect immediately without a server stop and restart.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="75965-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="75965-112">Examples</span></span>  
 <span data-ttu-id="75965-113">Nell'esempio seguente viene illustrata l'attivazione delle stored procedure estese di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="75965-113">The following example enables the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent extended stored procedures.</span></span>  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Agent XPs', 1;  
GO  
RECONFIGURE  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="75965-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75965-114">See Also</span></span>  
 <span data-ttu-id="75965-115">[Automatizzazione delle attività amministrative &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span><span class="sxs-lookup"><span data-stu-id="75965-115">[Automated Administration Tasks &#40;SQL Server Agent&#41;](../../ssms/agent/sql-server-agent.md) </span></span>  
 [<span data-ttu-id="75965-116">Avvio, arresto o sospensione del servizio SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="75965-116">Start, Stop, or Pause the SQL Server Agent Service</span></span>](../../ssms/agent/start-stop-or-pause-the-sql-server-agent-service.md)  
  
  
