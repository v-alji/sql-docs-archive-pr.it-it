---
title: Requisiti di sicurezza per la gestione dei servizi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent service, security
- services [SQL Server], security
- SQL Server services, security
- WMI Providers [SQL Server]
- server configuration [SQL Server]
- security [SQL Server], services
- services [SQL Server], WMI
ms.assetid: 1874a317-ddb2-425d-98d9-b53e1be6fc6a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 46a777858c01bf3057093d34b29b9a2093668e97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723063"
---
# <a name="security-requirements-for-managing-services"></a><span data-ttu-id="8894e-102">Requisiti di sicurezza per la gestione dei servizi</span><span class="sxs-lookup"><span data-stu-id="8894e-102">Security Requirements for Managing Services</span></span>
  <span data-ttu-id="8894e-103">Per gestire i servizi [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, usare Gestione configurazione SQL Server o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8894e-103">To manage the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent Services, use either SQL Server Configuration Manager or [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="8894e-104">Gestire i servizi su server del cluster tramite Amministrazione cluster.</span><span class="sxs-lookup"><span data-stu-id="8894e-104">Manage the services on clustered servers with the Cluster Administrator.</span></span>  
  
 <span data-ttu-id="8894e-105">Per gestire il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e impostare le opzioni di configurazione del server, è necessario essere membri del ruolo predefinito del server **serveradmin** o **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="8894e-105">To manage the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service and set the server configuration options, you must be a member of the **serveradmin** fixed server role or the **sysadmin** fixed server role.</span></span> <span data-ttu-id="8894e-106">I membri del gruppo **Administrators** di Windows possono avviare e arrestare i servizi e configurare le opzioni server disponibili in Windows.</span><span class="sxs-lookup"><span data-stu-id="8894e-106">Members of the Windows **Administrators** group can start and stop services and configure the server options that Windows provides.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8894e-107">Per un corretto funzionamento, è necessario che gli account utilizzati per i servizi siano configurati con dominio, file system e autorizzazioni per il Registro di sistema appropriati.</span><span class="sxs-lookup"><span data-stu-id="8894e-107">To operate properly, the accounts used for the services must be configured with the correct domain, file system, and registry permissions.</span></span> <span data-ttu-id="8894e-108">Per informazioni sulle autorizzazioni necessarie, vedere [Configurare account di servizio e autorizzazioni di Windows](configure-windows-service-accounts-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8894e-108">For information about the required permissions, see [Configure Windows Service Accounts and Permissions](configure-windows-service-accounts-and-permissions.md).</span></span>  
  
## <a name="windows-management-instrumentation"></a><span data-ttu-id="8894e-109">Strumentazione gestione Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="8894e-109">Windows Management Instrumentation</span></span>  
 <span data-ttu-id="8894e-110">Per visualizzare e modificare alcune delle proprietà del server in Gestione configurazione SQL Server e [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] viene utilizzato il servizio Strumentazione gestione Windows (WMI).</span><span class="sxs-lookup"><span data-stu-id="8894e-110">SQL Server Configuration Manager and [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] use Windows Management Instrumentation (WMI) to display and modify some of the server properties.</span></span> <span data-ttu-id="8894e-111">Per gestire i servizi e ottenere informazioni sullo stato dei servizi, è necessario che l'utente sia autorizzato ad accedere all'oggetto WMI.</span><span class="sxs-lookup"><span data-stu-id="8894e-111">To manage services and obtain the status of the services, the user must have rights to access the WMI object.</span></span> <span data-ttu-id="8894e-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]WMI viene utilizzato dalle proprietà del server seguenti:</span><span class="sxs-lookup"><span data-stu-id="8894e-112">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the following server property pages use WMI:</span></span>  
  
-   <span data-ttu-id="8894e-113">Avvio automatico servizi</span><span class="sxs-lookup"><span data-stu-id="8894e-113">Autostart Services</span></span>  
  
-   <span data-ttu-id="8894e-114">Parametri di avvio</span><span class="sxs-lookup"><span data-stu-id="8894e-114">Startup Parameters</span></span>  
  
-   <span data-ttu-id="8894e-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8894e-115">Security</span></span>  
  
-   <span data-ttu-id="8894e-116">Impostazioni varie</span><span class="sxs-lookup"><span data-stu-id="8894e-116">Misc Server Settings</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="8894e-117">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="8894e-117">Related Tasks</span></span>  
 [<span data-ttu-id="8894e-118">Configurazione di WMI per mostrare lo stato del server in Strumenti SQL Server</span><span class="sxs-lookup"><span data-stu-id="8894e-118">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
## <a name="related-content"></a><span data-ttu-id="8894e-119">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="8894e-119">Related Content</span></span>  
 [<span data-ttu-id="8894e-120">Concetti relativi al provider WMI per Gestione configurazione</span><span class="sxs-lookup"><span data-stu-id="8894e-120">WMI Provider for Configuration Management Concepts</span></span>](../../relational-databases/wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
