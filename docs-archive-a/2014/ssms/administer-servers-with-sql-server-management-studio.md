---
title: Amministrare server con SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], servers
- servers [SQL Server], administering
ms.assetid: 938bb035-e07a-4082-9f93-229d9feb6b06
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb2a6b9afba7d838cf71144f88ed7866c54ad796
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722243"
---
# <a name="administer-servers-with-sql-server-management-studio"></a><span data-ttu-id="830ce-102">Amministrazione di server con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="830ce-102">Administer Servers with SQL Server Management Studio</span></span>
  [!INCLUDE[msCoName](../includes/msconame-md.md)]<span data-ttu-id="830ce-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]è un client di amministrazione completo e integrato progettato per soddisfare i [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requisiti di gestione del server dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="830ce-103">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] is a rich, integrated administrative client designed to meet the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] administrator's server management requirements.</span></span> <span data-ttu-id="830ce-104">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]le attività di amministrazione vengono eseguite utilizzando Esplora oggetti, che consente di connettersi a qualsiasi server del gruppo [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e di visualizzarne graficamente il contenuto.</span><span class="sxs-lookup"><span data-stu-id="830ce-104">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], administrative tasks are accomplished using Object Explorer, which allows you to connect to any server in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] family and graphically browse its contents.</span></span> <span data-ttu-id="830ce-105">Un server può essere un'istanza del [!INCLUDE[ssDE](../includes/ssde-md.md)], di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="830ce-105">A server can be an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], or [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="830ce-106">I componenti di [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] includono Server registrati, Esplora oggetti, Esplora soluzioni, Esplora modelli, la pagina Dettagli Esplora oggetti e la finestra del documento.</span><span class="sxs-lookup"><span data-stu-id="830ce-106">The tool components of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] include Registered Servers, Object Explorer, Solution Explorer, Template Explorer, the Object Explorer Details page, and the document window.</span></span> <span data-ttu-id="830ce-107">Per visualizzare uno strumento, scegliere il nome desiderato dal menu **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="830ce-107">To display a tool, on the **View** menu, click the tool name.</span></span> <span data-ttu-id="830ce-108">Per visualizzare lo strumento Editor di query, fare clic sul pulsante **Nuova query** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="830ce-108">To display the Query Editor tool, click the **New Query** button on the toolbar.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="830ce-109">Per impostazione predefinita, il traffico di rete tra [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] e [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] non è crittografato.</span><span class="sxs-lookup"><span data-stu-id="830ce-109">Network traffic between [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] is unencrypted by default.</span></span> <span data-ttu-id="830ce-110">In [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] lavorare con dati sensibili (comprese le password) solo dopo aver stabilito una connessione crittografata.</span><span class="sxs-lookup"><span data-stu-id="830ce-110">Do not work with sensitive data (including passwords) in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] unless you have established an encrypted connection.</span></span> <span data-ttu-id="830ce-111">Per altre informazioni, vedere [Abilitare le connessioni crittografate al motore di database &#40;Gestione configurazione SQL Server&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="830ce-111">For more information, see [Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;](../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).</span></span>  
  
 <span data-ttu-id="830ce-112">Utilizzare [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] per:</span><span class="sxs-lookup"><span data-stu-id="830ce-112">Use [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="830ce-113">Registrare server.</span><span class="sxs-lookup"><span data-stu-id="830ce-113">Register servers.</span></span>  
  
-   <span data-ttu-id="830ce-114">Connettersi a un'istanza del [!INCLUDE[ssDE](../includes/ssde-md.md)], di [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)] o [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="830ce-114">Connect to an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)], [!INCLUDE[ssAS](../includes/ssas-md.md)], [!INCLUDE[ssRS](../includes/ssrs.md)], or [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
-   <span data-ttu-id="830ce-115">Configurare le proprietà del server.</span><span class="sxs-lookup"><span data-stu-id="830ce-115">Configure server properties.</span></span>  
  
-   <span data-ttu-id="830ce-116">Gestire database e oggetti [!INCLUDE[ssAS](../includes/ssas-md.md)] come ad esempio cubi, dimensioni e assembly.</span><span class="sxs-lookup"><span data-stu-id="830ce-116">Manage database and [!INCLUDE[ssAS](../includes/ssas-md.md)] objects such as cubes, dimensions, and assemblies.</span></span>  
  
-   <span data-ttu-id="830ce-117">Creare oggetti come ad esempio database, tabelle, cubi, utenti di database e account di accesso.</span><span class="sxs-lookup"><span data-stu-id="830ce-117">Create objects, such as databases, tables, cubes, database users, and logins.</span></span>  
  
-   <span data-ttu-id="830ce-118">Gestire file e filegroup.</span><span class="sxs-lookup"><span data-stu-id="830ce-118">Manage files and filegroups.</span></span>  
  
-   <span data-ttu-id="830ce-119">Collegare o scollegare database.</span><span class="sxs-lookup"><span data-stu-id="830ce-119">Attach or detach databases.</span></span>  
  
-   <span data-ttu-id="830ce-120">Avviare strumenti di scripting.</span><span class="sxs-lookup"><span data-stu-id="830ce-120">Launch scripting tools.</span></span>  
  
-   <span data-ttu-id="830ce-121">Gestire la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="830ce-121">Manage security.</span></span>  
  
-   <span data-ttu-id="830ce-122">Visualizzare registri di sistema.</span><span class="sxs-lookup"><span data-stu-id="830ce-122">View system logs.</span></span>  
  
-   <span data-ttu-id="830ce-123">Monitorare l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="830ce-123">Monitor current activity.</span></span>  
  
-   <span data-ttu-id="830ce-124">Configurare la replica.</span><span class="sxs-lookup"><span data-stu-id="830ce-124">Configure replication.</span></span>  
  
-   <span data-ttu-id="830ce-125">Gestire indici full-text.</span><span class="sxs-lookup"><span data-stu-id="830ce-125">Manage full-text indexes.</span></span>  
  
 <span data-ttu-id="830ce-126">Per avviare e arrestare [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, utilizzare Gestione configurazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="830ce-126">To start and stop [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="830ce-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="830ce-127">See Also</span></span>  
 <span data-ttu-id="830ce-128">[Usa SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="830ce-128">[Use SQL Server Management Studio](../database-engine/use-sql-server-management-studio.md) </span></span>  
 [<span data-ttu-id="830ce-129">Visualizzare o modificare le proprietà del server &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="830ce-129">View or Change Server Properties &#40;SQL Server&#41;</span></span>](../database-engine/configure-windows/view-or-change-server-properties-sql-server.md)  
  
  
