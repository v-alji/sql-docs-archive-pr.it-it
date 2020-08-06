---
title: Configurare l'opzione di configurazione del server media retention | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- backup retention duration [SQL Server]
- backup sets [SQL Server], retention duration
- media retention option
ms.assetid: 12e9fe6a-20a5-4c6e-9cc9-d500c003b70a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 092e0a2b5cfc30fd2d2362645fc1242bf4a1651e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626882"
---
# <a name="configure-the-media-retention-server-configuration-option"></a><span data-ttu-id="c5cd9-102">Configurare l'opzione di configurazione del server media retention</span><span class="sxs-lookup"><span data-stu-id="c5cd9-102">Configure the media retention Server Configuration Option</span></span>
  <span data-ttu-id="c5cd9-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **media retention** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5cd9-103">This topic describes how to configure the **media retention** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c5cd9-104">Con l'opzione **media retention** è possibile specificare il periodo di memorizzazione di ogni set di backup</span><span class="sxs-lookup"><span data-stu-id="c5cd9-104">The **media retention** option specifies the length of time to retain each backup set.</span></span> <span data-ttu-id="c5cd9-105">e impedire la sovrascrittura dei backup per il numero di giorni indicato.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-105">The option helps protect backups from being overwritten until the specified number of days has elapsed.</span></span> <span data-ttu-id="c5cd9-106">Dopo aver configurato l'opzione **media retention** , non è necessario specificare il periodo di memorizzazione dei backup di sistema ogni volta che si esegue un'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-106">After you configure **media retention** option, you do not have to specify the length of time to retain system backups each time you perform a backup.</span></span> <span data-ttu-id="c5cd9-107">Il valore predefinito è 0 giorni e quella massimo è 365 giorni.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-107">The default value is 0 days, and the maximum value is 365 days.</span></span>  
  
 <span data-ttu-id="c5cd9-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c5cd9-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c5cd9-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c5cd9-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c5cd9-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c5cd9-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c5cd9-111">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c5cd9-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c5cd9-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c5cd9-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c5cd9-113">**Per configurare l'opzione media retention tramite:**</span><span class="sxs-lookup"><span data-stu-id="c5cd9-113">**To configure the media retention option, using:**</span></span>  
  
     [<span data-ttu-id="c5cd9-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5cd9-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c5cd9-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c5cd9-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="c5cd9-116">**Completamento:**  [Dopo la configurazione dell'opzione media retention](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c5cd9-116">**Follow Up:**  [After you configure the media retention option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c5cd9-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c5cd9-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c5cd9-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c5cd9-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c5cd9-119">Se il supporto di backup viene utilizzato prima che sia trascorso il numero di giorni impostato, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-119">If you use the backup medium before the set number of days has passed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] issues a warning message.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="c5cd9-120">non viene visualizzato alcun messaggio di avviso a meno che non venga modificata l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-120">does not issue a warning unless you change the default.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c5cd9-121">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c5cd9-121">Recommendations</span></span>  
  
-   <span data-ttu-id="c5cd9-122">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c5cd9-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="c5cd9-123">È possibile eseguire l'override dell'opzione **media retention** tramite la clausola RETAINDAYS dell'istruzione [BACKUP](/sql/t-sql/statements/backup-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c5cd9-123">The **media retention** option can be overridden by using the RETAINDAYS clause of the [BACKUP](/sql/t-sql/statements/backup-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c5cd9-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c5cd9-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c5cd9-125">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c5cd9-125">Permissions</span></span>  
 <span data-ttu-id="c5cd9-126">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="c5cd9-127">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c5cd9-128">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="c5cd9-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c5cd9-129">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c5cd9-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="c5cd9-130">Per configurare l'opzione media retention</span><span class="sxs-lookup"><span data-stu-id="c5cd9-130">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="c5cd9-131">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c5cd9-132">Fare clic sul nodo **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="c5cd9-132">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="c5cd9-133">In **Backup/Ripristino**nella casella **Periodo di memorizzazione predefinito supporti di backup** digitare o selezionare un valore compreso tra 0 e 365 per impostare il numero di giorni per cui il supporto di backup verrà mantenuto dopo l'esecuzione di un backup del database o del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-133">Under **Backup/Restore**, in the **Default backup media retention** box, type or select a value from 0 through 365 to set the number of days the backup medium will be retained after a database or transaction log backup.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c5cd9-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c5cd9-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-media-retention-option"></a><span data-ttu-id="c5cd9-135">Per configurare l'opzione media retention</span><span class="sxs-lookup"><span data-stu-id="c5cd9-135">To configure the media retention option</span></span>  
  
1.  <span data-ttu-id="c5cd9-136">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5cd9-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c5cd9-137">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c5cd9-138">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c5cd9-139">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `media retention` su `60` giorni.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `media retention` option to `60` days.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'media retention', 60 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="c5cd9-140">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-media-retention-option"></a><a name="FollowUp"></a> <span data-ttu-id="c5cd9-141">Completamento: Dopo la configurazione dell'opzione media retention</span><span class="sxs-lookup"><span data-stu-id="c5cd9-141">Follow Up: After you configure the media retention option</span></span>  
 <span data-ttu-id="c5cd9-142">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="c5cd9-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5cd9-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5cd9-143">See Also</span></span>  
 <span data-ttu-id="c5cd9-144">[Backup e ripristino di database SQL Server](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c5cd9-144">[Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md) </span></span>  
 <span data-ttu-id="c5cd9-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5cd9-145">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="c5cd9-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c5cd9-146">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c5cd9-147">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c5cd9-147">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="c5cd9-148">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c5cd9-148">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
