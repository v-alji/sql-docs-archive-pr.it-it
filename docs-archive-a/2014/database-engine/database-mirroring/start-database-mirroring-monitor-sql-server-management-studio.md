---
title: Avviare Monitoraggio mirroring del database (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- monitoring database mirroring [SQL Server]
- Database Mirroring Monitor [SQL Server], starting
- database mirroring [SQL Server], monitoring
ms.assetid: 53165335-97ca-4f88-8e78-22f1839dee98
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 67c7b393b28d4d400535281c18c637146a5d8da7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623486"
---
# <a name="start-database-mirroring-monitor-sql-server-management-studio"></a><span data-ttu-id="7d707-102">Avviare Monitoraggio mirroring del database (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7d707-102">Start Database Mirroring Monitor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7d707-103">Monitoraggio mirroring del database è un componente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Monitoraggio avviato da [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d707-103">The Database Mirroring Monitor is part of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Monitor, which is launched from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7d707-104">Il monitoraggio mirroring del database non è disponibile in tutte le edizioni di [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d707-104">Database Mirroring Monitor is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7d707-105">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="7d707-105">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
### <a name="to-launch-the-database-mirroring-monitor"></a><span data-ttu-id="7d707-106">Per avviare Monitoraggio mirroring del database</span><span class="sxs-lookup"><span data-stu-id="7d707-106">To launch the Database Mirroring Monitor</span></span>  
  
1.  <span data-ttu-id="7d707-107">Dopo aver attivato la connessione all'istanza del server principale, in Esplora oggetti fare clic sul nome del server per espandere l'albero.</span><span class="sxs-lookup"><span data-stu-id="7d707-107">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="7d707-108">Espandere **Database**e selezionare il database da monitorare.</span><span class="sxs-lookup"><span data-stu-id="7d707-108">Expand **Databases**, and select the database to be monitored.</span></span>  
  
3.  <span data-ttu-id="7d707-109">Fare clic con il pulsante destro del mouse sul database, selezionare **Attività**e quindi fare clic su **Avvia Monitoraggio mirroring del database**.</span><span class="sxs-lookup"><span data-stu-id="7d707-109">Right-click the database, select **Tasks**, and then click **Launch Database Mirroring Monitor**.</span></span>  
  
4.  <span data-ttu-id="7d707-110">Nella finestra di dialogo **Monitoraggio mirroring del database** fare clic su **Registra database con mirroring** per registrare uno o più database con mirroring.</span><span class="sxs-lookup"><span data-stu-id="7d707-110">In the **Database Mirroring Monitor** dialog box, click **Register Mirrored Database** to register one or more mirrored database.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7d707-111">Quando si registra un database in un partner, automaticamente verrà registrato anche nell'altro partner.</span><span class="sxs-lookup"><span data-stu-id="7d707-111">When you register a database at one partner, the database is automatically registered at the other partner.</span></span> <span data-ttu-id="7d707-112">Se il server di monitoraggio dispone già delle credenziali per la connessione all'istanza dell'altro partner, eseguirà automaticamente la connessione.</span><span class="sxs-lookup"><span data-stu-id="7d707-112">If the monitor already has connection credentials for the other partner instance, those are used to connect.</span></span> <span data-ttu-id="7d707-113">In caso contrario tenterà di eseguire la connessione tramite l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="7d707-113">Otherwise the monitor attempts to connect using Windows Authentication.</span></span> <span data-ttu-id="7d707-114">Se si vuole modificare le credenziali usate per la connessione alle istanze del server, fare clic su **Quando viene scelto OK visualizza la finestra di dialogo Gestione connessioni a istanze server**.</span><span class="sxs-lookup"><span data-stu-id="7d707-114">If you want to change the credentials used to connect to either server instance, click **Show the Manage Server Connections dialog box when I click OK**.</span></span>  
  
 <span data-ttu-id="7d707-115">Per altre informazioni su Monitoraggio mirroring del database, vedere [Panoramica di Monitoraggio mirroring del database](database-mirroring-monitor-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7d707-115">For more information about Database Mirroring Monitor, see [Database Mirroring Monitor Overview](database-mirroring-monitor-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d707-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d707-116">See Also</span></span>  
 <span data-ttu-id="7d707-117">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7d707-117">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="7d707-118">Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7d707-118">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
  
