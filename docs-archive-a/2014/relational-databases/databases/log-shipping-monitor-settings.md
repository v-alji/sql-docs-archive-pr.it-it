---
title: Impostazioni monitoraggio log shipping | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.databaseproperties.logshipping.settings.monitor.f1
ms.assetid: 45e2ba7d-b3aa-4643-9451-bcb991572314
author: stevestein
ms.author: sstein
ms.openlocfilehash: 162fdc1b8b0ef850a7e58d1380c533426e16539c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725864"
---
# <a name="log-shipping-monitor-settings"></a><span data-ttu-id="222a2-102">Impostazioni monitoraggio log shipping</span><span class="sxs-lookup"><span data-stu-id="222a2-102">Log Shipping Monitor Settings</span></span>
  <span data-ttu-id="222a2-103">Utilizzare questa pagina per configurare e modificare le proprietà del server di monitoraggio del log shipping.</span><span class="sxs-lookup"><span data-stu-id="222a2-103">Use this page to configure and to modify the properties of the log shipping monitor server.</span></span>  
  
 <span data-ttu-id="222a2-104">Per approfondimenti sui concetti correlati al log shipping, vedere [Informazioni sul log shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="222a2-104">For an explanation of log shipping concepts, see [About Log Shipping &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="222a2-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="222a2-105">Options</span></span>  
 <span data-ttu-id="222a2-106">**Istanza server di monitoraggio**</span><span class="sxs-lookup"><span data-stu-id="222a2-106">**Monitor server instance**</span></span>  
 <span data-ttu-id="222a2-107">Visualizza il nome dell'istanza del server attualmente configurato come server di monitoraggio per la configurazione per il log shipping.</span><span class="sxs-lookup"><span data-stu-id="222a2-107">Displays the name of the server instance that is currently configured as the monitor server for the log shipping configuration.</span></span>  
  
 <span data-ttu-id="222a2-108">**Connettere**</span><span class="sxs-lookup"><span data-stu-id="222a2-108">**Connect**</span></span>  
 <span data-ttu-id="222a2-109">Consente di scegliere un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da utilizzare come server di monitoraggio e di connettersi a tale istanza.</span><span class="sxs-lookup"><span data-stu-id="222a2-109">Choose and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to be used as the monitor server.</span></span> <span data-ttu-id="222a2-110">È necessario che l'account utilizzato per la connessione sia membro del ruolo predefinito del server sysadmin nell'istanza del server secondario.</span><span class="sxs-lookup"><span data-stu-id="222a2-110">The account used to connect must be a member of the sysadmin fixed server role on the secondary server instance.</span></span>  
  
 <span data-ttu-id="222a2-111">**Tramite rappresentazione dell'account proxy del processo**</span><span class="sxs-lookup"><span data-stu-id="222a2-111">**By impersonating the proxy account of the job**</span></span>  
 <span data-ttu-id="222a2-112">Consente al log shipping di rappresentare l'account proxy di SQL Server Agent durante la connessione all'istanza del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="222a2-112">Have log shipping impersonate the SQL Server Agent proxy account when connecting to the monitor server instance.</span></span> <span data-ttu-id="222a2-113">Per aggiornare lo stato delle operazioni di log shipping i processi di backup, di copia e di ripristino devono potersi connettere al server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="222a2-113">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span>  
  
 <span data-ttu-id="222a2-114">**Tramite l'account di accesso di SQL Server seguente**</span><span class="sxs-lookup"><span data-stu-id="222a2-114">**Using the following SQL Server login**</span></span>  
 <span data-ttu-id="222a2-115">Consente al log shipping di utilizzare un account di accesso specifico di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] durante la connessione all'istanza del server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="222a2-115">Allow log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login when connecting to the monitor server instance.</span></span> <span data-ttu-id="222a2-116">Per aggiornare lo stato delle operazioni di log shipping i processi di backup, di copia e di ripristino devono potersi connettere al server di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="222a2-116">The backup, copy, and restore processes must be able to connect to the monitor server to update the status of log shipping operations.</span></span> <span data-ttu-id="222a2-117">Se si desidera che il log shipping utilizzi un account di accesso specifico di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , selezionare questa opzione e quindi specificare l'account di accesso e la password.</span><span class="sxs-lookup"><span data-stu-id="222a2-117">Choose this option if you want log shipping to use a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login and then specify the login and password.</span></span>  
  
 <span data-ttu-id="222a2-118">**Elimina cronologia dopo**</span><span class="sxs-lookup"><span data-stu-id="222a2-118">**Delete history after**</span></span>  
 <span data-ttu-id="222a2-119">Consente di specificare per quanto tempo le informazioni sulla cronologia di log shipping vengono mantenute sul server di monitoraggio prima di essere eliminate.</span><span class="sxs-lookup"><span data-stu-id="222a2-119">Specify the amount of time to retain log shipping history information on the monitor server before it is deleted.</span></span>  
  
 <span data-ttu-id="222a2-120">**Nome processo**</span><span class="sxs-lookup"><span data-stu-id="222a2-120">**Job name**</span></span>  
 <span data-ttu-id="222a2-121">Indica il nome del processo di gestione degli avvisi di SQL Server Agent utilizzato dal log shipping per generare avvisi in caso di superamento dei valori soglia per il backup o il ripristino.</span><span class="sxs-lookup"><span data-stu-id="222a2-121">Indicates the name of the SQL Server Agent alert job used by log shipping to raise alerts when backup or restore thresholds have been exceeded.</span></span> <span data-ttu-id="222a2-122">Al momento della prima creazione di tale processo è possibile modificarne il nome nell'apposita casella.</span><span class="sxs-lookup"><span data-stu-id="222a2-122">When first creating this job, you can change the name by typing in the box.</span></span>  
  
 <span data-ttu-id="222a2-123">**Pianificare**</span><span class="sxs-lookup"><span data-stu-id="222a2-123">**Schedule**</span></span>  
 <span data-ttu-id="222a2-124">Indica la pianificazione corrente del processo di gestione degli avvisi di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="222a2-124">Indicates the current schedule of the SQL Server Agent alert job.</span></span>  
  
 <span data-ttu-id="222a2-125">**Modifica**</span><span class="sxs-lookup"><span data-stu-id="222a2-125">**Edit**</span></span>  
 <span data-ttu-id="222a2-126">Consente di modificare i parametri del processo di gestione degli avvisi di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="222a2-126">Modify the SQL Server Agent alert job parameters.</span></span>  
  
 <span data-ttu-id="222a2-127">**Disabilita questo processo**</span><span class="sxs-lookup"><span data-stu-id="222a2-127">**Disable this job**</span></span>  
 <span data-ttu-id="222a2-128">Consente di sospendere il processo di gestione degli avvisi di SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="222a2-128">Suspend the SQL Server Agent alert job.</span></span>  
  
  
