---
title: Le tabelle di cronologia di backup o ripristino di grandi dimensioni rendono l'aggiornamento apparentemente non risponde | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- backup history tables
- history tables
ms.assetid: f88d86ec-324b-4518-b6d7-1af7e7265812
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 918c20f58c00c535d8ed41d887e9671f5e821a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624528"
---
# <a name="large-backup-or-restore-history-tables-make-upgrade-appear-to-not-respond"></a><span data-ttu-id="55c62-102">Se sono presenti tabelle di cronologia di backup o ripristino di grandi dimensioni, l'aggiornamento potrebbe sembrare che non risponde</span><span class="sxs-lookup"><span data-stu-id="55c62-102">Large backup or restore history tables make upgrade appear to not respond</span></span>
  <span data-ttu-id="55c62-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] sono state aggiunte nuove colonne ad alcune delle tabelle di cronologia di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="55c62-103">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], new columns were added to some of the backup and restore history tables.</span></span> <span data-ttu-id="55c62-104">Per aggiornare queste tabelle, è necessario modificarle in modo da aggiungere le nuove colonne.</span><span class="sxs-lookup"><span data-stu-id="55c62-104">Upgrading these tables requires altering them to add the new columns.</span></span> <span data-ttu-id="55c62-105">Se una o più di queste tabelle contengono un numero elevato di righe, l'aggiornamento richiederà molto tempo per l'istruzione ALTER TABLE che aggiunge colonne a tale tabella.</span><span class="sxs-lookup"><span data-stu-id="55c62-105">If one or more of these tables contains a large number of rows, the upgrade will stall for a substantial amount of time on the ALTER TABLE statement that adds columns to that table.</span></span>  
  
## <a name="component"></a><span data-ttu-id="55c62-106">Componente</span><span class="sxs-lookup"><span data-stu-id="55c62-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="55c62-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55c62-107">Description</span></span>  
 <span data-ttu-id="55c62-108">L'aggiornamento può sembrare non risponde se una delle tabelle di cronologia di backup o ripristino seguenti contiene un numero elevato di righe:</span><span class="sxs-lookup"><span data-stu-id="55c62-108">Upgrade can appear to stop responding if any of the following backup or restore history tables contains a large number of rows:</span></span>  
  
-   <span data-ttu-id="55c62-109">**backupfile**</span><span class="sxs-lookup"><span data-stu-id="55c62-109">**backupfile**</span></span>  
  
-   <span data-ttu-id="55c62-110">**backupmediafamily**</span><span class="sxs-lookup"><span data-stu-id="55c62-110">**backupmediafamily**</span></span>  
  
-   <span data-ttu-id="55c62-111">**backupmediaset**</span><span class="sxs-lookup"><span data-stu-id="55c62-111">**backupmediaset**</span></span>  
  
-   <span data-ttu-id="55c62-112">**backupset**</span><span class="sxs-lookup"><span data-stu-id="55c62-112">**backupset**</span></span>  
  
-   <span data-ttu-id="55c62-113">**restorefile**</span><span class="sxs-lookup"><span data-stu-id="55c62-113">**restorefile**</span></span>  
  
-   <span data-ttu-id="55c62-114">**restorefilegroup**</span><span class="sxs-lookup"><span data-stu-id="55c62-114">**restorefilegroup**</span></span>  
  
-   <span data-ttu-id="55c62-115">**restorehistory**</span><span class="sxs-lookup"><span data-stu-id="55c62-115">**restorehistory**</span></span>  
  
 <span data-ttu-id="55c62-116">Se una di queste tabelle contiene almeno 10.000 righe, verrà segnalato un errore di non conformità.</span><span class="sxs-lookup"><span data-stu-id="55c62-116">If any of these tables has 10,000 or more rows, Upgrade Advisor reports a noncompliance failure.</span></span> <span data-ttu-id="55c62-117">La tabella che supera il numero consentito di righe non viene indicata.</span><span class="sxs-lookup"><span data-stu-id="55c62-117">It does not report which table exceeds the allowed number of rows.</span></span> <span data-ttu-id="55c62-118">La prima tabella che supera le 10.000 righe genera l'errore.</span><span class="sxs-lookup"><span data-stu-id="55c62-118">The first table that exceeds 10,000 rows causes the failure.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="55c62-119">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="55c62-119">Corrective Action</span></span>  
 <span data-ttu-id="55c62-120">Prima di aggiornare un database, se una di queste tabelle supera le 10.000 righe, si consiglia di ridurre questo numero.</span><span class="sxs-lookup"><span data-stu-id="55c62-120">Before you upgrade a database, if any of these tables exceeds 10,000 rows, we recommend that you reduce the number to less than 10,000.</span></span> <span data-ttu-id="55c62-121">Per ridurre le righe in tutte le tabelle, è possibile eseguire il **sp_delete_backuphistory** stored procedure.</span><span class="sxs-lookup"><span data-stu-id="55c62-121">To reduce rows in all of these tables, you can run the **sp_delete_backuphistory** stored procedure.</span></span> <span data-ttu-id="55c62-122">Questa procedura elimina le voci in tutte le tabelle di cronologia di backup e ripristino relative a set di backup precedenti a una data specificata.</span><span class="sxs-lookup"><span data-stu-id="55c62-122">This procedure deletes the entries in all of the backup and restore history tables for backup sets older than a specified date.</span></span> <span data-ttu-id="55c62-123">Per altre informazioni, vedere [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="55c62-123">For more information, see [sp_delete_backuphistory &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="55c62-124">È possibile aggiornare un database le cui tabelle di cronologia di backup e ripristino contengono più di 10.000 righe,</span><span class="sxs-lookup"><span data-stu-id="55c62-124">You can upgrade a database whose backup and restore history tables are larger than 10,000 rows.</span></span> <span data-ttu-id="55c62-125">ma il processo potrebbe sembrare bloccato durante la modifica di tabelle di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="55c62-125">But the upgrade may appear to stall while large tables are being altered.</span></span> <span data-ttu-id="55c62-126">Le dimensioni delle tabelle influiscono sul tempo richiesto per completare il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="55c62-126">The larger the tables, the longer that Setup takes to complete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c62-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55c62-127">See Also</span></span>  
 <span data-ttu-id="55c62-128">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="55c62-128">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="55c62-129">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="55c62-129">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
