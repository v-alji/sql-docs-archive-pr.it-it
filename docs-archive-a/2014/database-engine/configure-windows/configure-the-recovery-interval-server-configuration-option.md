---
title: Configurare l'opzione di configurazione del server recovery interval | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- restoring recovery interval [SQL Server]
- checkpoints [SQL Server]
- recovery interval option [SQL Server]
- default recovery interval option
- time [SQL Server], recovery interval
- interval for recovery [SQL Server]
- maximum number of minutes per database recovery
- recovery [SQL Server], recovery interval option
ms.assetid: e4734b3b-8fbe-4b65-9c48-91b5a3dd18e1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 560d514ba8dd1503b59b3b59ecf404d876e24cd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624943"
---
# <a name="configure-the-recovery-interval-server-configuration-option"></a><span data-ttu-id="34a75-102">Configurare l'opzione di configurazione del server recovery interval</span><span class="sxs-lookup"><span data-stu-id="34a75-102">Configure the recovery interval Server Configuration Option</span></span>
  <span data-ttu-id="34a75-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **recovery interval** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34a75-103">This topic describes how to configure the **recovery interval** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="34a75-104">Con l'opzione **recovery interval** è possibile definire un limite superiore di tempo da impiegare per il recupero di un database.</span><span class="sxs-lookup"><span data-stu-id="34a75-104">The **recovery interval** option defines an upper limit on the time recovering a database should take.</span></span> <span data-ttu-id="34a75-105">Il valore specificato per questa opzione viene utilizzato nel [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] per stabilire approssimativamente la frequenza di generazione dei checkpoint automatici in un database specificato tramite [checkpoint automatici](../../relational-databases/logs/database-checkpoints-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="34a75-105">The [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses the value specified for this option to determine approximately how often [automatic checkpoints](../../relational-databases/logs/database-checkpoints-sql-server.md) to issue automatic checkpoints on a given database.</span></span>  
  
 <span data-ttu-id="34a75-106">Il valore predefinito di recovery-interval è 0. In questo modo, tramite il [!INCLUDE[ssDE](../../includes/ssde-md.md)] è possibile configurare automaticamente l'intervallo di recupero.</span><span class="sxs-lookup"><span data-stu-id="34a75-106">The default recovery-interval value is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to automatically configure the recovery interval.</span></span> <span data-ttu-id="34a75-107">In genere, con l'intervallo di recupero predefinito vengono generati checkpoint automatici circa una volta al minuto per i database attivi e in un tempo di recupero inferiore al minuto.</span><span class="sxs-lookup"><span data-stu-id="34a75-107">Typically, the default recovery interval results in automatic checkpoints occurring approximately once a minute for active databases and a recovery time of less than one minute.</span></span> <span data-ttu-id="34a75-108">I valori superiori indicano il tempo di recupero massimo approssimativo, in minuti.</span><span class="sxs-lookup"><span data-stu-id="34a75-108">Higher values indicate the approximate maximum recovery time, in minutes.</span></span> <span data-ttu-id="34a75-109">Ad esempio, impostando l'intervallo di recupero su 3, il tempo di recupero massimo risulterà di circa 3 minuti.</span><span class="sxs-lookup"><span data-stu-id="34a75-109">For example, setting the recovery interval to 3 indicates a maximum recovery time of approximately three minutes.</span></span>  
  
 <span data-ttu-id="34a75-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="34a75-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="34a75-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="34a75-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="34a75-112">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="34a75-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="34a75-113">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="34a75-113">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="34a75-114">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="34a75-114">Security</span></span>](#Security)  
  
-   <span data-ttu-id="34a75-115">**Per configurare l'opzione di configurazione del server recovery interval mediante**</span><span class="sxs-lookup"><span data-stu-id="34a75-115">**To Configure the recovery interval Server Configuration Option, using:**</span></span>  
  
     [<span data-ttu-id="34a75-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34a75-116">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="34a75-117">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34a75-117">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="34a75-118">**Completamento:**  [Dopo la configurazione dell'opzione recovery interval](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="34a75-118">**Follow Up:**  [After you configure the recovery interval option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="34a75-119">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="34a75-119">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="34a75-120">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="34a75-120">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="34a75-121">L'intervallo di recupero influisce solo sui database in cui viene utilizzato il tempo di recupero di riferimento predefinito (0).</span><span class="sxs-lookup"><span data-stu-id="34a75-121">The recovery interval affects only databases that use the default target recovery time (0).</span></span> <span data-ttu-id="34a75-122">Per ignorare l'intervallo di recupero del server in un database, configurare un tempo di recupero di riferimento non predefinito nel database.</span><span class="sxs-lookup"><span data-stu-id="34a75-122">To override the server recovery interval on a database, configure a non-default target recovery time on the database.</span></span> <span data-ttu-id="34a75-123">Per altre informazioni, vedere [Modificare il tempo di recupero di riferimento di un database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="34a75-123">For more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="34a75-124">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="34a75-124">Recommendations</span></span>  
  
-   <span data-ttu-id="34a75-125">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="34a75-125">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="34a75-126">In genere, è consigliabile mantenere l'intervallo di recupero a 0, a meno che non si verifichino problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="34a75-126">Typically, we recommend that you keep the recovery interval at 0, unless you experience performance problems.</span></span> <span data-ttu-id="34a75-127">Se si decide di aumentare l'impostazione dell'intervallo di recupero, è consigliabile aumentarla gradualmente di piccoli incrementi e valutare l'effetto di ogni aumento incrementale sulle prestazioni del recupero.</span><span class="sxs-lookup"><span data-stu-id="34a75-127">If you decide to increase the recovery-interval setting, we recommend increasing it gradually by small increments and evaluating the effect of each incremental increase on recovery performance.</span></span>  
  
-   <span data-ttu-id="34a75-128">Se si usa **sp_configure** per impostare il valore dell'opzione **recovery interval** su un valore maggiore di 60 (minuti), specificare RECONFIGURE WITH OVERRIDE.</span><span class="sxs-lookup"><span data-stu-id="34a75-128">If you use **sp_configure** to change the value of the **recovery interval** option to more than 60 (minutes), specify RECONFIGURE WITH OVERRIDE.</span></span> <span data-ttu-id="34a75-129">Con WITH OVERRIDE è possibile disabilitare la verifica del valore di configurazione, in particolare per valori non validi o non consigliati.</span><span class="sxs-lookup"><span data-stu-id="34a75-129">WITH OVERRIDE disables configuration value checking (for values that are not valid or are nonrecommended values).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="34a75-130">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="34a75-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="34a75-131">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="34a75-131">Permissions</span></span>  
 <span data-ttu-id="34a75-132">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="34a75-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="34a75-133">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="34a75-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="34a75-134">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="34a75-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="34a75-135">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="34a75-135">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="34a75-136">**Per impostare l'intervallo di recupero**</span><span class="sxs-lookup"><span data-stu-id="34a75-136">**To set the recovery interval**</span></span>  
  
1.  <span data-ttu-id="34a75-137">In Esplora oggetti fare clic con il pulsante destro del mouse sull'istanza del server e selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="34a75-137">In Object Explorer, right-click server instance and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="34a75-138">Fare clic sul nodo **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="34a75-138">Click the **Database settings** node.</span></span>  
  
3.  <span data-ttu-id="34a75-139">In **Recupero**, nella casella **Intervallo di recupero (minuti)** , digitare o selezionare un valore compreso tra 0 e 32767 per impostare il numero massimo di minuti impiegato da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per il recupero di ogni database all'avvio.</span><span class="sxs-lookup"><span data-stu-id="34a75-139">Under **Recovery**, in the **Recovery interval (minutes)** box, type or select a value from 0 through 32767 to set the maximum amount of time, in minutes, that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should spend recovering each database at startup.</span></span> <span data-ttu-id="34a75-140">L'impostazione predefinita è 0, che rappresenta la configurazione automatica di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34a75-140">The default is 0, indicating automatic configuration by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="34a75-141">Ciò equivale a un tempo di recupero inferiore a un minuto e all'impostazione di checkpoint a intervalli di circa un minuto per i database attivi.</span><span class="sxs-lookup"><span data-stu-id="34a75-141">In practice, this means a recovery time of less than one minute and a checkpoint approximately every one minute for active databases.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="34a75-142">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="34a75-142">Using Transact-SQL</span></span>  
  
#### <a name="to-set-the-recovery-interval"></a><span data-ttu-id="34a75-143">Per impostare l'intervallo di recupero</span><span class="sxs-lookup"><span data-stu-id="34a75-143">To set the recovery interval</span></span>  
  
1.  <span data-ttu-id="34a75-144">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="34a75-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="34a75-145">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="34a75-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="34a75-146">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="34a75-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="34a75-147">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `recovery interval` su `3` minuti.</span><span class="sxs-lookup"><span data-stu-id="34a75-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `recovery interval` option to `3` minutes.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'recovery interval', 3 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="34a75-148">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="34a75-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-recovery-internal-option"></a><a name="FollowUp"></a> <span data-ttu-id="34a75-149">Completamento: Dopo la configurazione dell'opzione recovery interval</span><span class="sxs-lookup"><span data-stu-id="34a75-149">Follow Up: After you configure the recovery internal option</span></span>  
 <span data-ttu-id="34a75-150">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="34a75-150">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a75-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34a75-151">See Also</span></span>  
 <span data-ttu-id="34a75-152">[Modificare il tempo di recupero di riferimento di un database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34a75-152">[Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../../relational-databases/logs/change-the-target-recovery-time-of-a-database-sql-server.md) </span></span>  
 <span data-ttu-id="34a75-153">[Checkpoint di database &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34a75-153">[Database Checkpoints &#40;SQL Server&#41;](../../relational-databases/logs/database-checkpoints-sql-server.md) </span></span>  
 <span data-ttu-id="34a75-154">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="34a75-154">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="34a75-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34a75-155">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="34a75-156">[Opzione di configurazione del server show advanced options](show-advanced-options-server-configuration-option.md) </span><span class="sxs-lookup"><span data-stu-id="34a75-156">[show advanced options Server Configuration Option](show-advanced-options-server-configuration-option.md) </span></span>  
 [<span data-ttu-id="34a75-157">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="34a75-157">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
