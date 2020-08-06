---
title: Aggiunta server di controllo del mirroring (Configurazione guidata sicurezza mirroring del database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.inclwitness.f1
ms.assetid: f04b38a4-f4e2-4d4c-bdac-7cc70e5a5684
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 314d2205463436e2182b8d1a4cc0cc972213bd5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624904"
---
# <a name="include-witness-server-configure-database-mirroring-security-wizard"></a><span data-ttu-id="8d6ba-102">Aggiunta server di controllo del mirroring (Configurazione guidata sicurezza mirroring del database)</span><span class="sxs-lookup"><span data-stu-id="8d6ba-102">Include Witness Server (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="8d6ba-103">Utilizzare questa pagina per specificare se si desidera aggiungere un server di controllo del mirroring in questa configurazione di sicurezza per il mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="8d6ba-103">Use this page to specify whether you want to include a witness server in this security configuration for database mirroring.</span></span>  
  
 <span data-ttu-id="8d6ba-104">**Per configurare il mirroring del database tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-104">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="8d6ba-105">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8d6ba-105">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="8d6ba-106">Avvio della Configurazione guidata sicurezza mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="8d6ba-106">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="8d6ba-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8d6ba-107">Options</span></span>  
 <span data-ttu-id="8d6ba-108">**Sì**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-108">**Yes**</span></span>  
 <span data-ttu-id="8d6ba-109">Fare clic su questo pulsante per aggiungere un'istanza del server di controllo del mirroring nella configurazione di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8d6ba-109">Click to include a witness server instance in the security configuration.</span></span> <span data-ttu-id="8d6ba-110">Il server di controllo del mirroring è necessario per la modalità a disponibilità elevata con failover automatico, che supporta il failover automatico sull'istanza del server mirror in caso si verifichi un errore nell'istanza del server principale.</span><span class="sxs-lookup"><span data-stu-id="8d6ba-110">The witness is necessary for high-safety mode with automatic failover, which supports automatic failover to the mirror server instance if the principal server instance fails.</span></span>  
  
 <span data-ttu-id="8d6ba-111">**No**</span><span class="sxs-lookup"><span data-stu-id="8d6ba-111">**No**</span></span>  
 <span data-ttu-id="8d6ba-112">Fare clic su questo pulsante per impostare la configurazione di sicurezza senza un server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="8d6ba-112">Click to configure security without a witness.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d6ba-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d6ba-113">See Also</span></span>  
 <span data-ttu-id="8d6ba-114">[Proprietà del database &#40;Pagina Mirroring&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="8d6ba-114">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="8d6ba-115">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8d6ba-115">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="8d6ba-116">Server di controllo del mirroring del database</span><span class="sxs-lookup"><span data-stu-id="8d6ba-116">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
