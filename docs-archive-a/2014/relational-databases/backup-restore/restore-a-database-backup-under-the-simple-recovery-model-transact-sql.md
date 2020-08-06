---
title: Ripristinare un backup del database nel modello di recupero con registrazione minima (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full backups [SQL Server]
- database restores [SQL Server], full backups
- backing up databases [SQL Server], full backups
- database backups [SQL Server], full backups
- restoring databases [SQL Server], full backups
ms.assetid: a928fa36-e285-476f-9a7b-6840a8bb7283
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e264dd380c3dff40dacc4eb576d34af5195dec01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714440"
---
# <a name="restore-a-database-backup-under-the-simple-recovery-model-transact-sql"></a><span data-ttu-id="fba40-102">Ripristinare un backup del database nel modello di recupero con registrazione minima (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="fba40-102">Restore a Database Backup Under the Simple Recovery Model (Transact-SQL)</span></span>
  <span data-ttu-id="fba40-103">In questo argomento viene descritto come ripristinare un backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="fba40-103">This topic explains how to restore a full database backup.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fba40-104">L'amministratore di sistema che esegue il ripristino del backup completo del database deve essere l'unico utente collegato al database.</span><span class="sxs-lookup"><span data-stu-id="fba40-104">The system administrator restoring the full database backup must be the only person currently using the database to be restored.</span></span>  
  
## <a name="prerequisites-and-recommendations"></a><span data-ttu-id="fba40-105">Prerequisiti e indicazioni</span><span class="sxs-lookup"><span data-stu-id="fba40-105">Prerequisites and Recommendations</span></span>  
  
-   <span data-ttu-id="fba40-106">Per ripristinare un database crittografato, è necessario poter accedere alla chiave asimmetrica o al certificato utilizzato per crittografare il database.</span><span class="sxs-lookup"><span data-stu-id="fba40-106">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="fba40-107">Non è possibile effettuare l'operazione di ripristino del database senza almeno uno di questi due elementi.</span><span class="sxs-lookup"><span data-stu-id="fba40-107">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="fba40-108">Di conseguenza, il certificato utilizzato per crittografare la chiave di crittografia del database deve essere conservato fino a quando il backup è necessario.</span><span class="sxs-lookup"><span data-stu-id="fba40-108">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="fba40-109">Per altre informazioni, vedere [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="fba40-109">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
-   <span data-ttu-id="fba40-110">Per motivi di sicurezza, è consigliabile non collegare o ripristinare database da origini sconosciute o non attendibili.</span><span class="sxs-lookup"><span data-stu-id="fba40-110">For security purposes, we recommend that you do not attach or restore databases from unknown or untrusted sources.</span></span> <span data-ttu-id="fba40-111">Tali database possono contenere codice dannoso che potrebbe eseguire codice [!INCLUDE[tsql](../../includes/tsql-md.md)] indesiderato o causare errori modificando lo schema o la struttura fisica di database.</span><span class="sxs-lookup"><span data-stu-id="fba40-111">Such databases could contain malicious code that might execute unintended [!INCLUDE[tsql](../../includes/tsql-md.md)] code or cause errors by modifying the schema or the physical database structure.</span></span> <span data-ttu-id="fba40-112">Prima di utilizzare un database da un'origine sconosciuta o non attendibile, eseguire [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) sul database in un server non di produzione ed esaminare il codice contenuto nel database, ad esempio le stored procedure o altro codice definito dall'utente.</span><span class="sxs-lookup"><span data-stu-id="fba40-112">Before you use a database from an unknown or untrusted source, run [DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql) on the database on a nonproduction server and also examine the code, such as stored procedures or other user-defined code, in the database.</span></span>  
  
## <a name="database-compatibility-level-after-upgrade"></a><span data-ttu-id="fba40-113">Livello di compatibilità del database dopo l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="fba40-113">Database Compatibility Level After Upgrade</span></span>  
 <span data-ttu-id="fba40-114">I livelli di compatibilità dei database **tempdb**, **model**, **msdb** e **Resource** vengono impostati sul livello di compatibilità di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fba40-114">The compatibility levels of the **tempdb**, **model**, **msdb** and **Resource** databases are set to the compatibility level of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] after upgrade.</span></span> <span data-ttu-id="fba40-115">Il database di sistema **master** mantiene il livello di compatibilità precedente all'aggiornamento a meno che tale livello non fosse minore di 100.</span><span class="sxs-lookup"><span data-stu-id="fba40-115">The **master** system database retains the compatibility level it had before upgrade, unless that level was less than 100.</span></span> <span data-ttu-id="fba40-116">Se il livello di compatibilità di **master** era minore di 100 prima dell'aggiornamento, viene impostato su 100 dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fba40-116">If the compatibility level of **master** was less than 100 before upgrade, it is set to 100 after upgrade.</span></span>  
  
 <span data-ttu-id="fba40-117">Se il livello di compatibilità di un database utente è 100 o superiore prima dell'aggiornamento, rimane invariato dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fba40-117">If the compatibility level of a user database was 100 or higher before upgrade, it remains the same after upgrade.</span></span> <span data-ttu-id="fba40-118">Se il livello di compatibilità è 90 prima dell'aggiornamento, nel database aggiornato viene impostato su 100, ovvero sul livello di compatibilità supportato più basso in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fba40-118">If the compatibility level was 90 before upgrade, in the upgraded database, the compatibility level is set to 100, which is the lowest supported compatibility level in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fba40-119">I nuovi database utente erediteranno il livello di compatibilità del database **model** .</span><span class="sxs-lookup"><span data-stu-id="fba40-119">New user databases will inherit the compatibility level of the **model** database.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="fba40-120">Procedure</span><span class="sxs-lookup"><span data-stu-id="fba40-120">Procedures</span></span>  
  
#### <a name="to-restore-a-full-database-backup"></a><span data-ttu-id="fba40-121">Per ripristinare un backup completo del database</span><span class="sxs-lookup"><span data-stu-id="fba40-121">To restore a full database backup</span></span>  
  
1.  <span data-ttu-id="fba40-122">Eseguire l'istruzione RESTORE DATABASE per ripristinare il backup completo del database, specificando:</span><span class="sxs-lookup"><span data-stu-id="fba40-122">Execute the RESTORE DATABASE statement to restore the full database backup, specifying:</span></span>  
  
    -   <span data-ttu-id="fba40-123">Nome del database da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="fba40-123">The name of the database to restore.</span></span>  
  
    -   <span data-ttu-id="fba40-124">Il dispositivo di backup da cui viene ripristinato il backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="fba40-124">The backup device from where the full database backup is restored.</span></span>  
  
    -   <span data-ttu-id="fba40-125">La clausola NORECOVERY, se è disponibile un backup del log delle transazioni o un backup differenziale del database da applicare dopo il ripristino del backup completo del database.</span><span class="sxs-lookup"><span data-stu-id="fba40-125">The NORECOVERY clause if you have a transaction log or differential database backup to apply after restoring the full database backup.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="fba40-126">Per ripristinare un database crittografato, è necessario poter accedere alla chiave asimmetrica o al certificato utilizzato per crittografare il database.</span><span class="sxs-lookup"><span data-stu-id="fba40-126">To restore a database that is encrypted, you must have access to the certificate or asymmetric key that was used to encrypt the database.</span></span> <span data-ttu-id="fba40-127">Non è possibile effettuare l'operazione di ripristino del database senza almeno uno di questi due elementi.</span><span class="sxs-lookup"><span data-stu-id="fba40-127">Without the certificate or asymmetric key, the database cannot be restored.</span></span> <span data-ttu-id="fba40-128">Di conseguenza, il certificato utilizzato per crittografare la chiave di crittografia del database deve essere conservato fino a quando il backup è necessario.</span><span class="sxs-lookup"><span data-stu-id="fba40-128">As a result, the certificate that is used to encrypt the database encryption key must be retained as long as the backup is needed.</span></span> <span data-ttu-id="fba40-129">Per altre informazioni, vedere [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span><span class="sxs-lookup"><span data-stu-id="fba40-129">For more information, see [SQL Server Certificates and Asymmetric Keys](../security/sql-server-certificates-and-asymmetric-keys.md).</span></span>  
  
2.  <span data-ttu-id="fba40-130">Facoltativamente, specificare:</span><span class="sxs-lookup"><span data-stu-id="fba40-130">Optionally, specify:</span></span>  
  
    -   <span data-ttu-id="fba40-131">La clausola FILE per identificare il set di backup nel dispositivo di backup da ripristinare.</span><span class="sxs-lookup"><span data-stu-id="fba40-131">The FILE clause to identify the backup set on the backup device to restore.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fba40-132">Se si ripristina un database di una versione precedente a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], il database viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fba40-132">If you restore an earlier version database to [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], the database is automatically upgraded.</span></span> <span data-ttu-id="fba40-133">In genere, il database diventa subito disponibile.</span><span class="sxs-lookup"><span data-stu-id="fba40-133">Typically, the database becomes available immediately.</span></span> <span data-ttu-id="fba40-134">Se tuttavia un database di [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] include indici full-text, questi vengono importati, reimpostati o ricompilati dal processo di aggiornamento, a seconda dell'impostazione della proprietà del server  **upgrade_option** .</span><span class="sxs-lookup"><span data-stu-id="fba40-134">However, if a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database has full-text indexes, the upgrade process either imports, resets, or rebuilds them, depending on the setting of the  **upgrade_option** server property.</span></span> <span data-ttu-id="fba40-135">Se l'opzione di aggiornamento è impostata per l'importazione (**upgrade_option** = 2) o la ricompilazione (**upgrade_option** = 0), gli indici full-text non saranno disponibili durante l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="fba40-135">If the upgrade option is set to import (**upgrade_option** = 2) or rebuild (**upgrade_option** = 0), the full-text indexes will be unavailable during the upgrade.</span></span> <span data-ttu-id="fba40-136">A seconda della quantità di dati indicizzati, l'importazione può richiedere diverse ore, mentre la ricompilazione può risultare dieci volte più lunga.</span><span class="sxs-lookup"><span data-stu-id="fba40-136">Depending the amount of data being indexed, importing can take several hours, and rebuilding can take up to ten times longer.</span></span> <span data-ttu-id="fba40-137">Si noti inoltre che quando l'opzione di aggiornamento è impostata sull'importazione, gli indici full-text associati vengono ricompilati se non è disponibile un catalogo full-text.</span><span class="sxs-lookup"><span data-stu-id="fba40-137">Note also that when the upgrade option is set to import, the associated full-text indexes are rebuilt if a full-text catalog is not available.</span></span> <span data-ttu-id="fba40-138">Per modificare l'impostazione della proprietà del server **upgrade_option** , usare [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fba40-138">To change the setting of the **upgrade_option** server property, use [sp_fulltext_service](/sql/relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fba40-139">Esempio</span><span class="sxs-lookup"><span data-stu-id="fba40-139">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="fba40-140">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fba40-140">Description</span></span>  
 <span data-ttu-id="fba40-141">In questo esempio viene eseguito un ripristino da nastro del backup completo del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fba40-141">This example restores the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] full database backup from tape.</span></span>  
  
### <a name="example"></a><span data-ttu-id="fba40-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="fba40-142">Example</span></span>  
  
```  
USE master;  
GO  
RESTORE DATABASE AdventureWorks2012  
   FROM TAPE = '\\.\Tape0';  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="fba40-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fba40-143">See Also</span></span>  
 <span data-ttu-id="fba40-144">[Ripristini di database completi &#40;modello di recupero con registrazione completa&#41;](complete-database-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="fba40-144">[Complete Database Restores &#40;Full Recovery Model&#41;](complete-database-restores-full-recovery-model.md) </span></span>  
 <span data-ttu-id="fba40-145">[Ripristini di database completi &#40;modello di recupero con registrazione minima&#41;](complete-database-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="fba40-145">[Complete Database Restores &#40;Simple Recovery Model&#41;](complete-database-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="fba40-146">[Backup completo del database &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fba40-146">[Full Database Backups &#40;SQL Server&#41;](full-database-backups-sql-server.md) </span></span>  
 <span data-ttu-id="fba40-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="fba40-147">[RESTORE &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-statements-transact-sql) </span></span>  
 <span data-ttu-id="fba40-148">[Informazioni sulla cronologia e sull'intestazione del backup &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="fba40-148">[Backup History and Header Information &#40;SQL Server&#41;](backup-history-and-header-information-sql-server.md) </span></span>  
 [<span data-ttu-id="fba40-149">Ricompilare database di sistema</span><span class="sxs-lookup"><span data-stu-id="fba40-149">Rebuild System Databases</span></span>](../databases/system-databases.md)  
  
  
