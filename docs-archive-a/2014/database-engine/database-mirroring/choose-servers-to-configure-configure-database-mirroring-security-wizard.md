---
title: Selezione dei server da configurare (Configurazione guidata sicurezza mirroring del database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.choosesrvrs.f1
ms.assetid: 59e23ff3-d7ee-4e32-9629-0b54d3a258f7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 18e36f5c8ec020b3859dc847d1bbfc019817bcd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626287"
---
# <a name="choose-servers-to-configure-configure-database-mirroring-security-wizard"></a><span data-ttu-id="2bb2f-102">Selezione dei server da configurare (Configurazione guidata sicurezza mirroring del database)</span><span class="sxs-lookup"><span data-stu-id="2bb2f-102">Choose Servers to Configure (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="2bb2f-103">Utilizzare questa pagina per specificare le istanze del server che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-103">Use this page to specify which server instances you want to configure now.</span></span> <span data-ttu-id="2bb2f-104">Prima di proseguire con la procedura guidata è necessario selezionare almeno un'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-104">You must select at least one server instance before continuing the wizard.</span></span>  
  
 <span data-ttu-id="2bb2f-105">Se si deseleziona la casella di controllo corrispondente a un'istanza del server, la procedura guidata non apporterà alcuna modifica a tale istanza.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-105">If you clear the check box for a server instance, the wizard will not make any changes to it.</span></span> <span data-ttu-id="2bb2f-106">Verrà chiesto tuttavia di immettere informazioni sull'istanza, che verranno salvate come parte della configurazione delle altre istanze del server.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-106">The wizard, however, will ask you to enter information about that instance and save this information as part of the configuration of the other server instances.</span></span> <span data-ttu-id="2bb2f-107">Se ad esempio si deseleziona la casella di controllo corrispondente all'istanza del server di controllo del mirroring, la procedura guidata chiederà di immettere l'account del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] del server di controllo del mirroring, perché è necessario creare tale account di accesso come parte della configurazione di sicurezza salvata nelle istanze del server principale e del server mirror.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-107">For example, if you clear the check box for the witness server instance, the wizard will ask you to enter the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service account of the witness because a login for that account must be created as part of the security configuration saved at the principal and mirror server instances.</span></span>  
  
 <span data-ttu-id="2bb2f-108">**Per configurare il mirroring del database tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="2bb2f-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="2bb2f-109">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2bb2f-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="2bb2f-110">Avvio della Configurazione guidata sicurezza mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2bb2f-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="2bb2f-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2bb2f-111">Options</span></span>  
 <span data-ttu-id="2bb2f-112">**Istanza server principale**</span><span class="sxs-lookup"><span data-stu-id="2bb2f-112">**Principal server instance**</span></span>  
 <span data-ttu-id="2bb2f-113">Consente di configurare la sicurezza per il server principale.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-113">Select to configure security for the principal server.</span></span>  
  
 <span data-ttu-id="2bb2f-114">**Istanza server mirror**</span><span class="sxs-lookup"><span data-stu-id="2bb2f-114">**Mirror server instance**</span></span>  
 <span data-ttu-id="2bb2f-115">Consente di configurare la sicurezza per il server mirror.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-115">Select to configure security for the mirror server.</span></span>  
  
 <span data-ttu-id="2bb2f-116">**Istanza server di controllo del mirroring**</span><span class="sxs-lookup"><span data-stu-id="2bb2f-116">**Witness server instance**</span></span>  
 <span data-ttu-id="2bb2f-117">Consente di configurare la sicurezza per il server di controllo del mirroring, se presente.</span><span class="sxs-lookup"><span data-stu-id="2bb2f-117">Select to configure security for the witness server (if present).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb2f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bb2f-118">See Also</span></span>  
 <span data-ttu-id="2bb2f-119">[Proprietà del database &#40;Pagina Mirroring&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="2bb2f-119">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 [<span data-ttu-id="2bb2f-120">Mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="2bb2f-120">Database Mirroring &#40;SQL Server&#41;</span></span>](database-mirroring-sql-server.md)  
  
  
