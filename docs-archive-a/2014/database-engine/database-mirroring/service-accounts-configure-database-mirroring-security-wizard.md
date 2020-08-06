---
title: Account di servizio (Configurazione guidata sicurezza mirroring del database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.serviceaccounts.f1
ms.assetid: d58d8f93-7888-4d66-af4d-969ef6a2dbee
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58e49467a28e816c6592b1ded212b5aea0e6bc55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716735"
---
# <a name="service-accounts-configure-database-mirroring-security-wizard"></a><span data-ttu-id="7ba7b-102">Account di servizio (Configurazione guidata sicurezza mirroring del database)</span><span class="sxs-lookup"><span data-stu-id="7ba7b-102">Service Accounts (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="7ba7b-103">Quando si utilizza l'autenticazione di Windows, se le istanze del server utilizzano account diversi, specificare gli account di servizio per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7ba7b-103">When using Windows Authentication, if the server instances use different accounts, specify the service accounts for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7ba7b-104">Tali account di servizio devono essere tutti account di dominio negli stessi domini o in domini di tipo trusted.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-104">These service accounts must all be domain accounts (in the same or trusted domains).</span></span>  
  
 <span data-ttu-id="7ba7b-105">Se tutte le istanze del server utilizzano lo stesso account di dominio oppure utilizzano l'autenticazione basata sui certificati, lasciare i campi vuoti.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-105">If all the server instances use the same domain account or use certificate-based authentication, leave the fields blank.</span></span> <span data-ttu-id="7ba7b-106">È sufficiente fare clic su **Fine**per configurare automaticamente gli account tramite la procedura guidata in base all'account della procedura guidata corrente.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-106">Simply click **Finish**, and the wizard automatically configures the accounts based on the account of the current wizard.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7ba7b-107">Se gli endpoint del mirroring del database delle istanze del server sono configurati per l'utilizzo di certificati, è necessario lasciare vuoti tutti i campi degli account di servizio.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-107">If the database mirroring endpoints of the server instances are configured to use certificates, you must leave the service account fields empty.</span></span>  
  
 <span data-ttu-id="7ba7b-108">**Per configurare il mirroring del database tramite SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="7ba7b-108">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="7ba7b-109">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7ba7b-109">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="7ba7b-110">Avvio della Configurazione guidata sicurezza mirroring del database &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7ba7b-110">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="7ba7b-111">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7ba7b-111">Options</span></span>  
 <span data-ttu-id="7ba7b-112">**Server principale**</span><span class="sxs-lookup"><span data-stu-id="7ba7b-112">**Principal**</span></span>  
 <span data-ttu-id="7ba7b-113">Consente di specificare l'account di servizio dell'istanza del server principale.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-113">Specify the service account of the principal server instance.</span></span> <span data-ttu-id="7ba7b-114">Immettere il nome di dominio in lettere maiuscole:</span><span class="sxs-lookup"><span data-stu-id="7ba7b-114">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="7ba7b-115">*NomeDominio* \\ *nome utente*</span><span class="sxs-lookup"><span data-stu-id="7ba7b-115">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="7ba7b-116">**Mirror**</span><span class="sxs-lookup"><span data-stu-id="7ba7b-116">**Mirror**</span></span>  
 <span data-ttu-id="7ba7b-117">Consente di specificare l'account di servizio dell'istanza del server mirror.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-117">Specify the service account of the mirror server instance.</span></span> <span data-ttu-id="7ba7b-118">Immettere il nome di dominio in lettere maiuscole:</span><span class="sxs-lookup"><span data-stu-id="7ba7b-118">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="7ba7b-119">*NomeDominio* \\ *nome utente*</span><span class="sxs-lookup"><span data-stu-id="7ba7b-119">*DOMAINNAME*\\*username*</span></span>  
  
 <span data-ttu-id="7ba7b-120">**Testimone**</span><span class="sxs-lookup"><span data-stu-id="7ba7b-120">**Witness**</span></span>  
 <span data-ttu-id="7ba7b-121">Consente di specificare l'account di servizio dell'istanza del server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="7ba7b-121">Specify the service account of the witness server instance.</span></span> <span data-ttu-id="7ba7b-122">Immettere il nome di dominio in lettere maiuscole:</span><span class="sxs-lookup"><span data-stu-id="7ba7b-122">Enter the domain name in upper case:</span></span>  
  
 <span data-ttu-id="7ba7b-123">*NomeDominio* \\ *nome utente*</span><span class="sxs-lookup"><span data-stu-id="7ba7b-123">*DOMAINNAME*\\*username*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ba7b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ba7b-124">See Also</span></span>  
 <span data-ttu-id="7ba7b-125">[Proprietà del database &#40;Pagina Mirroring&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="7ba7b-125">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="7ba7b-126">[Avviare il monitoraggio mirroring del database &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="7ba7b-126">[Start Database Mirroring Monitor &#40;SQL Server Management Studio&#41;](../database-mirroring/start-database-mirroring-monitor-sql-server-management-studio.md) </span></span>  
 <span data-ttu-id="7ba7b-127">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7ba7b-127">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="7ba7b-128">Configurare gli account di accesso per il mirroring del database o Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7ba7b-128">Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](set-up-login-accounts-database-mirroring-always-on-availability.md)  
  
  
