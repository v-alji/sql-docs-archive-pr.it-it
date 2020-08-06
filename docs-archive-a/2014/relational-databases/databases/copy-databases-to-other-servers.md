---
title: Copiare database in altri server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- servers [SQL Server], copying databases between
- bulk exporting [SQL Server], between servers
- database copying [SQL Server]
- migrating databases [SQL Server]
- moving databases
- copying databases
- bulk importing [SQL Server], between servers
ms.assetid: 978406d6-a3c8-4902-b1f4-4ced75234be5
author: stevestein
ms.author: sstein
ms.openlocfilehash: bcde6185f25129596b4be7a150d4ee230c54c1a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715400"
---
# <a name="copy-databases-to-other-servers"></a><span data-ttu-id="7ffea-102">Copia di database in altri server</span><span class="sxs-lookup"><span data-stu-id="7ffea-102">Copy Databases to Other Servers</span></span>
  <span data-ttu-id="7ffea-103">È talvolta utile copiare un database da un computer a un altro, ad esempio per eseguire test o controlli di consistenza, sviluppare software, eseguire report, creare un database mirror o rendere il database disponibile per attività di filiali remote.</span><span class="sxs-lookup"><span data-stu-id="7ffea-103">It is sometimes useful to copy a database from one computer to another, whether for testing, checking consistency, developing software, running reports, creating a mirror database, or, possibly, to make the database available to remote-branch operations.</span></span>  
  
 <span data-ttu-id="7ffea-104">È possibile copiare un database in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="7ffea-104">There are several ways to copy a database:</span></span>  
  
-   <span data-ttu-id="7ffea-105">Utilizzo di Copia guidata database</span><span class="sxs-lookup"><span data-stu-id="7ffea-105">Using the Copy Database Wizard</span></span>  
  
     <span data-ttu-id="7ffea-106">È possibile utilizzare Copia guidata database per copiare o spostare database tra server o per aggiornare un database di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="7ffea-106">You can use the Copy Database Wizard to copy or move databases between servers or to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to a later version.</span></span> <span data-ttu-id="7ffea-107">Per altre informazioni, vedere [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7ffea-107">For more information, see [Use the Copy Database Wizard](use-the-copy-database-wizard.md).</span></span>  
  
-   <span data-ttu-id="7ffea-108">Ripristinando un backup del database.</span><span class="sxs-lookup"><span data-stu-id="7ffea-108">Restoring a database backup</span></span>  
  
     <span data-ttu-id="7ffea-109">Per copiare un intero database è possibile utilizzare le istruzioni [!INCLUDE[tsql](../../includes/tsql-md.md)] BACKUP e RESTORE.</span><span class="sxs-lookup"><span data-stu-id="7ffea-109">To copy an entire database, you can use the BACKUP and RESTORE [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="7ffea-110">Generalmente la copia di un database da un computer a un altro viene eseguita mediante il ripristino di un backup completo del database in oggetto per diverse ragioni.</span><span class="sxs-lookup"><span data-stu-id="7ffea-110">Typically, restoring a full backup of a database is used to copy the database from one computer to another for a variety of reasons.</span></span> <span data-ttu-id="7ffea-111">Per informazioni sull'uso delle operazioni di backup e ripristino allo scopo di eseguire la copia di un database, vedere [Copiare database tramite backup e ripristino](copy-databases-with-backup-and-restore.md).</span><span class="sxs-lookup"><span data-stu-id="7ffea-111">For information on using backup and restore to copy a database, see [Copy Databases with Backup and Restore](copy-databases-with-backup-and-restore.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ffea-112">Per impostare un database mirror per il mirroring del database, è necessario ripristinare il database nel server mirror con RESTORE DATABASE *<nome_database>* WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="7ffea-112">To set up a mirror database for database mirroring, you must restore the database onto the mirror server by using RESTORE DATABASE *<database_name>* WITH NORECOVERY.</span></span> <span data-ttu-id="7ffea-113">Per altre informazioni, vedere [Preparazione di un database mirror per il mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7ffea-113">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](../../database-engine/database-mirroring/prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
-   <span data-ttu-id="7ffea-114">Utilizzo della procedura guidata di generazione script per pubblicare database</span><span class="sxs-lookup"><span data-stu-id="7ffea-114">Using the Generate Scripts Wizard to publish databases</span></span>  
  
     <span data-ttu-id="7ffea-115">È possibile utilizzare la procedura guidata Genera script per trasferire un database da un computer locale a un provider di hosting Web.</span><span class="sxs-lookup"><span data-stu-id="7ffea-115">You can use the Generate Scripts Wizard to transfer a database from a local computer to a Web hosting provider.</span></span> <span data-ttu-id="7ffea-116">Per altre informazioni, vedere [Procedura guidata Genera e pubblica script](../scripting/generate-and-publish-scripts-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="7ffea-116">For more information, see [Generate and Publish Scripts Wizard](../scripting/generate-and-publish-scripts-wizard.md).</span></span>  
  
  
