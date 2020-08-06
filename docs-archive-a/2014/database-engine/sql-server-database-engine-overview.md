---
title: Motore di database di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server]
- SQL Server Database Engine
ms.assetid: 65e2f424-1386-45a6-8912-bd053f434073
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a6c243115e940f7af085c0068d2ca5c277aa5162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624318"
---
# <a name="sql-server-database-engine"></a><span data-ttu-id="e39e6-102">Motore di database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e39e6-102">SQL Server Database Engine</span></span>
  <span data-ttu-id="e39e6-103">[!INCLUDE[ssDE](../includes/ssde-md.md)] è il servizio principale per l'archiviazione, l'elaborazione e la sicurezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="e39e6-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="e39e6-104">[!INCLUDE[ssDE](../includes/ssde-md.md)] assicura l'accesso controllato e l'elaborazione rapida delle transazioni per soddisfare i requisiti delle più complesse applicazioni aziendali di gestione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e39e6-104">The [!INCLUDE[ssDE](../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications within your enterprise.</span></span>

 <span data-ttu-id="e39e6-105">Utilizzare [!INCLUDE[ssDE](../includes/ssde-md.md)] per creare database relazionali per i dati relativi all'elaborazione delle transazioni online o all'elaborazione analitica online,</span><span class="sxs-lookup"><span data-stu-id="e39e6-105">Use the [!INCLUDE[ssDE](../includes/ssde-md.md)] to create relational databases for online transaction processing or online analytical processing data.</span></span> <span data-ttu-id="e39e6-106">inclusa la creazione di tabelle per l'archiviazione di dati e oggetti di database, ad esempio indici, viste e stored procedure per la visualizzazione, la gestione e la protezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e39e6-106">This includes creating tables for storing data, and database objects such as indexes, views, and stored procedures for viewing, managing, and securing data.</span></span> <span data-ttu-id="e39e6-107">È possibile utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per gestire gli oggetti di database e [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] per acquisire gli eventi del server.</span><span class="sxs-lookup"><span data-stu-id="e39e6-107">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to manage the database objects, and [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to capture server events.</span></span>

 <span data-ttu-id="e39e6-108">Icona della cartella dei file **di esplorazione del contenuto per area** ![small](../../2014/integration-services/media/filefolder-small.gif "Icona della cartella file piccola") [(motore di database)](whats-new-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="e39e6-108">**Browse Content by Area** ![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [What's New (Database Engine)](whats-new-in-sql-server-2016.md)</span></span>

 <span data-ttu-id="e39e6-109">![Icona cartella file di piccole dimensioni](../../2014/integration-services/media/filefolder-small.gif "Icona della cartella file piccola") [SQL Server motore di database compatibilità con le versioni precedenti](sql-server-database-engine-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e39e6-109">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Database Engine Backward Compatibility](sql-server-database-engine-backward-compatibility.md)</span></span>

 <span data-ttu-id="e39e6-110">![Icona della cartella file piccola](../../2014/integration-services/media/filefolder-small.gif "Icona della cartella file piccola") [strumenti di gestione di SQL Server compatibilità con le versioni precedenti](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="e39e6-110">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Management Tools Backward Compatibility](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span></span>

 <span data-ttu-id="e39e6-111">![Icona cartella file di piccole dimensioni](../../2014/integration-services/media/filefolder-small.gif "Icona della cartella file piccola") [funzionalità e attività del database](../../2014/database-engine/database-engine-features-and-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="e39e6-111">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Database Features and Tasks](../../2014/database-engine/database-engine-features-and-tasks.md)</span></span>

 <span data-ttu-id="e39e6-112">![Icona della cartella file piccola](../../2014/integration-services/media/filefolder-small.gif "Icona della cartella file piccola") [riferimento tecnico](../../2014/database-engine/technical-reference-database-engine.md)</span><span class="sxs-lookup"><span data-stu-id="e39e6-112">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Technical Reference](../../2014/database-engine/technical-reference-database-engine.md)</span></span>

 <span data-ttu-id="e39e6-113">![Icona della cartella file piccola](../../2014/integration-services/media/filefolder-small.gif "Icona della cartella file piccola") Guida [di riferimento a Transact-SQL](/sql/t-sql/language-reference)</span><span class="sxs-lookup"><span data-stu-id="e39e6-113">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Transact-SQL Reference](/sql/t-sql/language-reference)</span></span>

 <span data-ttu-id="e39e6-114">![Icona della cartella file piccola](../../2014/integration-services/media/filefolder-small.gif "Icona della cartella file piccola") [riferimento XQuery](/sql/xquery/xquery-language-reference-sql-server)</span><span class="sxs-lookup"><span data-stu-id="e39e6-114">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [XQuery Reference](/sql/xquery/xquery-language-reference-sql-server)</span></span>

## <a name="see-also"></a><span data-ttu-id="e39e6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e39e6-115">See Also</span></span>
 [<span data-ttu-id="e39e6-116">Centro risorse di SQL Server</span><span class="sxs-lookup"><span data-stu-id="e39e6-116">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=219676)


