---
title: Visualizzare o configurare l'opzione di configurazione del server backup compression default | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], backup compression default option
- backup compression [SQL Server], backup compression default Option
ms.assetid: 23029395-3e93-4c29-b7d6-e5a47a3526ff
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f02458c069d7c155b199e24feb7ef028ae0f258a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638085"
---
# <a name="view-or-configure-the-backup-compression-default-server-configuration-option"></a><span data-ttu-id="efdd2-102">Visualizzare o configurare l'opzione di configurazione del server backup compression default</span><span class="sxs-lookup"><span data-stu-id="efdd2-102">View or Configure the backup compression default Server Configuration Option</span></span>
  <span data-ttu-id="efdd2-103">Questo argomento illustra come visualizzare o configurare l'opzione di configurazione del server **Valore predefinito di compressione backup** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oppure [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efdd2-103">This topic describes how to view or configure the **backup compression default** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="efdd2-104">Con l'opzione **backup compression default** è possibile determinare se nell'istanza del server vengono creati backup compressi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="efdd2-104">The **backup compression default** option determines whether the server instance creates compressed backups by default.</span></span> <span data-ttu-id="efdd2-105">Quando è installato [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , l'opzione **Valore predefinito di compressione backup** è disattivata.</span><span class="sxs-lookup"><span data-stu-id="efdd2-105">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed, the **backup compression default** option is off.</span></span>  
  
 <span data-ttu-id="efdd2-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="efdd2-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="efdd2-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="efdd2-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="efdd2-108">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="efdd2-108">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="efdd2-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="efdd2-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="efdd2-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="efdd2-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="efdd2-111">**Per visualizzare o configurare l'opzione backup compression default tramite:**</span><span class="sxs-lookup"><span data-stu-id="efdd2-111">**To view or configure the backup compression default option, using:**</span></span>  
  
     [<span data-ttu-id="efdd2-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="efdd2-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="efdd2-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="efdd2-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="efdd2-114">**Completamento:**  [Dopo la configurazione dell'opzione backup compression default](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="efdd2-114">**Follow Up:**  [After you configure the backup compression default option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="efdd2-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="efdd2-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="efdd2-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="efdd2-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="efdd2-117">La compressione dei backup non è disponibile in tutte le edizioni di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efdd2-117">Backup compression is not available in all editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="efdd2-118">Per ulteriori informazioni, vedere [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="efdd2-118">For more information, see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="efdd2-119">Per impostazione predefinita, la compressione aumenta significativamente l'utilizzo della CPU, il che può avere un impatto negativo sulle operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="efdd2-119">By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="efdd2-120">Potrebbe pertanto essere necessario creare backup compressi con priorità bassa in una sessione in cui l'utilizzo della CPU è limitato da [Resource Governor](../../relational-databases/resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="efdd2-120">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../../relational-databases/resource-governor/resource-governor.md).</span></span> <span data-ttu-id="efdd2-121">Per ulteriori informazioni, vedere [Utilizzo di Resource Governor per limitare l'utilizzo della CPU da parte della compressione dei backup &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="efdd2-121">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](../../relational-databases/backup-restore/use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="efdd2-122">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="efdd2-122">Recommendations</span></span>  
  
-   <span data-ttu-id="efdd2-123">Quando si crea un singolo backup, si imposta una configurazione di log shipping o si crea un piano di manutenzione, è possibile eseguire l'override dell'impostazione predefinita a livello del server.</span><span class="sxs-lookup"><span data-stu-id="efdd2-123">When you are creating an individual backup, configuring a log shipping configuration, or creating a maintenance plan, you can override the server-level default.</span></span>  
  
-   <span data-ttu-id="efdd2-124">La compressione dei backup è supportata sia per i dispositivi di backup su disco sia per quelli su nastro.</span><span class="sxs-lookup"><span data-stu-id="efdd2-124">Backup compression is supported for both disk backup devices and tape backup devices.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="efdd2-125">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="efdd2-125">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="efdd2-126">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="efdd2-126">Permissions</span></span>  
 <span data-ttu-id="efdd2-127">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="efdd2-127">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="efdd2-128">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="efdd2-128">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="efdd2-129">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="efdd2-129">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="efdd2-130">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="efdd2-130">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-configure-the-backup-compression-default-option"></a><span data-ttu-id="efdd2-131">Per visualizzare o configurare l'opzione backup compression default</span><span class="sxs-lookup"><span data-stu-id="efdd2-131">To view or configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="efdd2-132">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="efdd2-132">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="efdd2-133">Fare clic sul nodo **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="efdd2-133">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="efdd2-134">Sotto **Backup e ripristino**, **Comprimi backup** viene visualizzata l'impostazione corrente dell'opzione **backup compression default** .</span><span class="sxs-lookup"><span data-stu-id="efdd2-134">Under **Backup and restore**, **Compress backup** shows the current setting of the **backup compression default** option.</span></span> <span data-ttu-id="efdd2-135">Questa impostazione determina l'impostazione predefinita a livello di server per la compressione di backup, come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="efdd2-135">This setting determines the server-level default for compressing backups, as follows:</span></span>  
  
    -   <span data-ttu-id="efdd2-136">Se la casella **Comprimi backup** è vuota, per impostazione predefinita i nuovi backup non sono compressi.</span><span class="sxs-lookup"><span data-stu-id="efdd2-136">If the **Compress backup** box is blank, new backups are uncompressed by default.</span></span>  
  
    -   <span data-ttu-id="efdd2-137">Se la casella **Comprimi backup** è selezionata, per impostazione predefinita i nuovi backup vengono compressi.</span><span class="sxs-lookup"><span data-stu-id="efdd2-137">If the **Compress backup** box is checked, new backups are compressed by default.</span></span>  
  
     <span data-ttu-id="efdd2-138">Se si è un membro del ruolo predefinito del server **sysadmin** o **serveradmin** , è anche possibile modificare l'impostazione predefinita facendo clic sulla casella **Comprimi backup** .</span><span class="sxs-lookup"><span data-stu-id="efdd2-138">If you are a member of the **sysadmin** or **serveradmin** fixed server role, you can also change the default setting by clicking the **Compress backup** box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="efdd2-139">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="efdd2-139">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-backup-compression-default-option"></a><span data-ttu-id="efdd2-140">Per visualizzare l'opzione backup compression default</span><span class="sxs-lookup"><span data-stu-id="efdd2-140">To view the backup compression default option</span></span>  
  
1.  <span data-ttu-id="efdd2-141">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efdd2-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="efdd2-142">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="efdd2-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="efdd2-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="efdd2-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="efdd2-144">In questo esempio vengono eseguite query sulla vista del catalogo [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) per determinare il valore per `backup compression default`.</span><span class="sxs-lookup"><span data-stu-id="efdd2-144">This example queries the [sys.configurations](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view to determine the value for `backup compression default`.</span></span> <span data-ttu-id="efdd2-145">Il valore 0 indica che la compressione dei backup è disabilitata, mentre il valore 1 che è abilitata.</span><span class="sxs-lookup"><span data-stu-id="efdd2-145">A value of 0 means that backup compression is off, and a value of 1 means that backup compression is enabled.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
SELECT value   
FROM sys.configurations   
WHERE name = 'backup compression default' ;  
GO  
  
```  
  
#### <a name="to-configure-the-backup-compression-default-option"></a><span data-ttu-id="efdd2-146">Per configurare l'opzione backup compression default</span><span class="sxs-lookup"><span data-stu-id="efdd2-146">To configure the backup compression default option</span></span>  
  
1.  <span data-ttu-id="efdd2-147">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efdd2-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="efdd2-148">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="efdd2-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="efdd2-149">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="efdd2-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="efdd2-150">In questo esempio viene illustrato come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per configurare l'istanza del server per creare backup compressi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="efdd2-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the server instance to create compressed backups by default.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
EXEC sp_configure 'backup compression default', 1 ;  
RECONFIGURE WITH OVERRIDE ;  
GO  
  
```  
  
 <span data-ttu-id="efdd2-151">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="efdd2-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-backup-compression-default-option"></a><a name="FollowUp"></a> <span data-ttu-id="efdd2-152">Completamento: Dopo la configurazione dell'opzione backup compression default</span><span class="sxs-lookup"><span data-stu-id="efdd2-152">Follow Up: After you configure the backup compression default option</span></span>  
 <span data-ttu-id="efdd2-153">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="efdd2-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdd2-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efdd2-154">See Also</span></span>  
 <span data-ttu-id="efdd2-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efdd2-155">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="efdd2-156">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="efdd2-156">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="efdd2-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efdd2-157">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="efdd2-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="efdd2-158">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="efdd2-159">Panoramica del backup &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="efdd2-159">Backup Overview &#40;SQL Server&#41;</span></span>](../../relational-databases/backup-restore/backup-overview-sql-server.md)  
  
  
