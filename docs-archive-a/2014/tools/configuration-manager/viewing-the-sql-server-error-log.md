---
title: Visualizzazione del log degli errori di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cycling SQL Server error log
- viewing SQL Server error log
- errors [SQL Server], logs
- SQL Server error log
- displaying SQL Server error log
- logs [SQL Server], SQL Server error logs
ms.assetid: 6908c21a-65e3-458f-a272-fee256d86448
author: stevestein
ms.author: sstein
ms.openlocfilehash: 822ae4fba589f005aaee41857a9db3388a309254
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622978"
---
# <a name="viewing-the-sql-server-error-log"></a><span data-ttu-id="b8d95-102">Visualizzazione del log degli errori di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b8d95-102">Viewing the SQL Server Error Log</span></span>
  <span data-ttu-id="b8d95-103">È possibile visualizzare il contenuto del log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per verificare il corretto completamento dei processi, ad esempio le operazioni di backup e ripristino, i comandi batch e altri script e processi.</span><span class="sxs-lookup"><span data-stu-id="b8d95-103">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to ensure that processes have completed successfully (for example, backup and restore operations, batch commands, or other scripts and processes).</span></span> <span data-ttu-id="b8d95-104">La possibilità di esaminare il contenuto del log degli errori può risultare utile per individuare problemi correnti o potenziali, inclusi i messaggi di recupero automatico, in caso di arresto e riavvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , i messaggi del kernel e altri messaggi di errore a livello di server.</span><span class="sxs-lookup"><span data-stu-id="b8d95-104">This can be helpful to detect any current or potential problem areas, including automatic recovery messages (particularly if an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has been stopped and restarted), kernel messages, or other server-level error messages.</span></span>  
  
 <span data-ttu-id="b8d95-105">Per visualizzare il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è possibile utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o un editor di testo.</span><span class="sxs-lookup"><span data-stu-id="b8d95-105">View the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor.</span></span> <span data-ttu-id="b8d95-106">Per ulteriori informazioni sulla visualizzazione del log degli errori, vedere [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="b8d95-106">For more information about how to view the error log, see [Open Log File Viewer](../../relational-databases/logs/log-file-viewer.md).</span></span> <span data-ttu-id="b8d95-107">Il log degli errori si trova per impostazione predefinita nei file `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` e `ERRORLOG.`*n* .</span><span class="sxs-lookup"><span data-stu-id="b8d95-107">By default, the error log is located at `Program Files\Microsoft SQL Server\MSSQL.`*n*`\MSSQL\LOG\ERRORLOG` and `ERRORLOG.`*n* files.</span></span>  
  
 <span data-ttu-id="b8d95-108">A ogni avvio di un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene creato un nuovo log degli errori. È tuttavia possibile usare la stored procedure di sistema [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) per scorrere i file di log degli errori senza dover riavviare l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8d95-108">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started, although the [sp_cycle_errorlog](/sql/relational-databases/system-stored-procedures/sp-cycle-errorlog-transact-sql) system stored procedure can be used to cycle the error log files without having to restart the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b8d95-109">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vengono in genere mantenute le copie di backup dei sei log precedenti e viene assegnata l'estensione 1 alla copia di backup più recente, l'estensione 2 alla penultima copia e così via.</span><span class="sxs-lookup"><span data-stu-id="b8d95-109">Typically, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains backups of the previous six logs and gives the most recent log backup the extension .1, the second most recent the extension .2, and so on.</span></span> <span data-ttu-id="b8d95-110">Il log degli errori corrente non ha alcuna estensione.</span><span class="sxs-lookup"><span data-stu-id="b8d95-110">The current error log has no extension.</span></span>  
  
 <span data-ttu-id="b8d95-111">Tenere presente che è possibile visualizzare anche il log degli errori di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] su istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] che risultano offline o non possono essere avviate.</span><span class="sxs-lookup"><span data-stu-id="b8d95-111">Be aware that you can also view the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log on instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are offline or cannot start.</span></span> <span data-ttu-id="b8d95-112">Per altre informazioni, vedere [Visualizzare file di log offline](../../relational-databases/logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="b8d95-112">For more information, see [View Offline Log Files](../../relational-databases/logs/view-offline-log-files.md).</span></span>  
  
  
