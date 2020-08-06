---
title: Connettersi a qualsiasi componente SQL Server da SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], SQL Server Management Studio
- saving connections
- components [SQL Server], connections
- SQL Server Management Studio [SQL Server], connections
ms.assetid: 5eeb41bd-b25b-4d3b-a005-a7d9e4b5978e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 9cd3e185ea6f289a2a6db46cdca2cb310fefbcf9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717255"
---
# <a name="connect-to-any-sql-server-component-from-sql-server-management-studio"></a><span data-ttu-id="c7e13-102">Connessione ai componenti di SQL Server da SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7e13-102">Connect to Any SQL Server Component from SQL Server Management Studio</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="c7e13-103">offre funzionalità per la gestione di qualsiasi componente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7e13-103">provides functionality for managing every component of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c7e13-104">Utilizzare [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] per collegarsi a:</span><span class="sxs-lookup"><span data-stu-id="c7e13-104">Use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to connect to:</span></span>  
  
-   <span data-ttu-id="c7e13-105">Istanza del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7e13-105">An instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="c7e13-106">.</span><span class="sxs-lookup"><span data-stu-id="c7e13-106">.</span></span>  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]<span data-ttu-id="c7e13-107">.</span><span class="sxs-lookup"><span data-stu-id="c7e13-107">.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]<span data-ttu-id="c7e13-108">.</span><span class="sxs-lookup"><span data-stu-id="c7e13-108">.</span></span>  
  
 <span data-ttu-id="c7e13-109">Sebbene [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] consenta di lavorare con le query senza prima stabilire una connessione a un'origine dei dati, la maggior parte delle altre attività richiede una connessione.</span><span class="sxs-lookup"><span data-stu-id="c7e13-109">Although [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] allows you to work with queries without first establishing a connection to a data source, most other tasks require a connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="c7e13-110">offre la finestra di dialogo **Connetti al server** per configurare le proprietà di connessione ai componenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7e13-110">provides the **Connect to Server** dialog box to configure connection properties to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] components.</span></span> <span data-ttu-id="c7e13-111">All'avvio di [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] , si apre la finestra di dialogo **Connetti al server** in cui viene chiesto di connettersi a un server.</span><span class="sxs-lookup"><span data-stu-id="c7e13-111">When [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] starts, it opens the **Connect to Server** dialog box and prompts you to connect to a server.</span></span> <span data-ttu-id="c7e13-112">La finestra di dialogo **Connetti al server** visualizza le ultime impostazioni di connessione usate.</span><span class="sxs-lookup"><span data-stu-id="c7e13-112">The **Connect to Server** dialog box retains the connection settings from the last time it was used.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c7e13-113">È possibile disattivare questa caratteristica per impedire che venga iniziata automaticamente una connessione.</span><span class="sxs-lookup"><span data-stu-id="c7e13-113">This feature can be turned off so no connection is automatically initiated.</span></span> <span data-ttu-id="c7e13-114">Per altre informazioni, vedere [Opzioni di avvio del servizio del motore di database](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span><span class="sxs-lookup"><span data-stu-id="c7e13-114">For more information, see [Database Engine Service Startup Options](../../database-engine/configure-windows/database-engine-service-startup-options.md).</span></span>  
  
## <a name="saving-connections"></a><span data-ttu-id="c7e13-115">salvataggio di connessioni</span><span class="sxs-lookup"><span data-stu-id="c7e13-115">Saving Connections</span></span>  
 <span data-ttu-id="c7e13-116">È possibile salvare le connessioni in specifici server in Server registrati, oppure salvarle in progetti con Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="c7e13-116">You can save connections to specific servers in Registered Servers, or you can save connections in projects with Solution Explorer.</span></span>  
  
### <a name="saving-connections-in-registered-servers"></a><span data-ttu-id="c7e13-117">Salvataggio delle connessioni in Server registrati</span><span class="sxs-lookup"><span data-stu-id="c7e13-117">Saving Connections in Registered Servers</span></span>  
 <span data-ttu-id="c7e13-118">Quando viene registrato un server, in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] le informazioni di connessione vengono salvate in Server registrati.</span><span class="sxs-lookup"><span data-stu-id="c7e13-118">When you register a server, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] saves the connection information in Registered Servers.</span></span> <span data-ttu-id="c7e13-119">Per connettersi a un server registrato, fare doppio clic sul nome desiderato in Server registrati.</span><span class="sxs-lookup"><span data-stu-id="c7e13-119">To connect to a registered server, double-click the server name in Registered Servers.</span></span> <span data-ttu-id="c7e13-120">Esplora oggetti aprirà una connessione al server.</span><span class="sxs-lookup"><span data-stu-id="c7e13-120">Object Explorer then opens a connection to the server.</span></span>  
  
### <a name="saving-connections-in-solution-explorer"></a><span data-ttu-id="c7e13-121">Salvataggio delle connessioni in Esplora soluzioni</span><span class="sxs-lookup"><span data-stu-id="c7e13-121">Saving Connections in Solution Explorer</span></span>  
 <span data-ttu-id="c7e13-122">Esplora soluzioni consente di archiviare query correlate, script, connessioni e altre informazioni associate in un progetto.</span><span class="sxs-lookup"><span data-stu-id="c7e13-122">Solution Explorer allows you to store related queries, scripts, connections, and other associated information in a project.</span></span> <span data-ttu-id="c7e13-123">Ogni progetto script contiene un nodo chiamato **Connessioni**, in cui è possibile salvare una o più connessioni.</span><span class="sxs-lookup"><span data-stu-id="c7e13-123">Each script project contains a node called **Connections**, where you can save one or more connections.</span></span> <span data-ttu-id="c7e13-124">Per aggiungere una connessione, fare clic con il pulsante destro del mouse su **Connessioni**e scegliere **Nuova connessione**.</span><span class="sxs-lookup"><span data-stu-id="c7e13-124">To add a connection, right-click **Connections**, and then click **New Connection**.</span></span> <span data-ttu-id="c7e13-125">Per accedere a una connessione salvata, espandere **Connessioni** e fare doppio clic sulla connessione.</span><span class="sxs-lookup"><span data-stu-id="c7e13-125">To access a saved connection, expand **Connections** and double-click the connection.</span></span> [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] <span data-ttu-id="c7e13-126">apre una finestra di query associata a quella connessione.</span><span class="sxs-lookup"><span data-stu-id="c7e13-126">opens a query window associated with that connection.</span></span> <span data-ttu-id="c7e13-127">Gli script salvati mantengono l'associazione con una specifica connessione.</span><span class="sxs-lookup"><span data-stu-id="c7e13-127">When saved, scripts retain their association to a specific connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e13-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7e13-128">See Also</span></span>  
 <span data-ttu-id="c7e13-129">[Usa SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span><span class="sxs-lookup"><span data-stu-id="c7e13-129">[Use SQL Server Management Studio](../sql-server-management-studio-ssms.md) </span></span>  
 [<span data-ttu-id="c7e13-130">Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="c7e13-130">Object Explorer</span></span>](../object/object-explorer.md)  
  
  
