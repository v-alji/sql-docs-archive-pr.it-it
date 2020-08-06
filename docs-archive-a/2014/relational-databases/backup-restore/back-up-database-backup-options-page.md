---
title: Backup database (pagina Opzioni di backup) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backupdatabase.options.f1
- swb.backupdatabase.options.f1
ms.assetid: df0ddcdb-c94e-472b-b786-469ae8117b93
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ffd527ba4334244c7fd4c5d4a73099093cb8520b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637944"
---
# <a name="back-up-database-backup-options-page"></a><span data-ttu-id="85495-102">Backup database (pagina Opzioni di backup)</span><span class="sxs-lookup"><span data-stu-id="85495-102">Back Up Database (Backup Options Page)</span></span>
  <span data-ttu-id="85495-103">Utilizzare la pagina  **Opzioni di backup** della finestra di dialogo **Backup database** per visualizzare o modificare le opzioni di backup del database.</span><span class="sxs-lookup"><span data-stu-id="85495-103">Use the  **Backup Options** page of the **Back Up Database** dialog box to view or modify database backup options.</span></span>  
  
 <span data-ttu-id="85495-104">**Per creare un backup utilizzando SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="85495-104">**To create a backup by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="85495-105">Creazione di un backup completo del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85495-105">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](create-a-full-database-backup-sql-server.md)  
  
-   [<span data-ttu-id="85495-106">Creare un backup differenziale del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85495-106">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](create-a-differential-database-backup-sql-server.md)  
  
> [!IMPORTANT]  
>  <span data-ttu-id="85495-107">È possibile definire un piano di manutenzione database per creare backup di database.</span><span class="sxs-lookup"><span data-stu-id="85495-107">You can define a database maintenance plan to create database backups.</span></span> <span data-ttu-id="85495-108">Per altre informazioni, vedere [Piani di manutenzione](../maintenance-plans/maintenance-plans.md) e [Usare la Creazione guidata piano di manutenzione](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="85495-108">For more information, see [Maintenance Plans](../maintenance-plans/maintenance-plans.md) and [Use the Maintenance Plan Wizard](../maintenance-plans/use-the-maintenance-plan-wizard.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="85495-109">Quando si specifica un'attività di backup usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], è possibile generare lo script [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) corrispondente facendo clic sul pulsante **Script** e selezionando una destinazione per lo script.</span><span class="sxs-lookup"><span data-stu-id="85495-109">When you specify a backup task by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you can generate the corresponding [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) script by clicking the **Script** button and then selecting a destination for the script.</span></span>  
  
## <a name="options"></a><span data-ttu-id="85495-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="85495-110">Options</span></span>  
  
### <a name="backup-set"></a><span data-ttu-id="85495-111">Set di backup</span><span class="sxs-lookup"><span data-stu-id="85495-111">Backup set</span></span>  
 <span data-ttu-id="85495-112">Le opzioni del pannello **Set di backup** consentono di specificare informazioni facoltative sul set di backup creato dall'operazione di backup.</span><span class="sxs-lookup"><span data-stu-id="85495-112">The options of the **Backup set** panel allow for you to specify optional information about the backup set created by the back up operation.</span></span>  
  
 <span data-ttu-id="85495-113">**Nome**</span><span class="sxs-lookup"><span data-stu-id="85495-113">**Name**</span></span>  
 <span data-ttu-id="85495-114">Consente di specificare il nome del set di backup.</span><span class="sxs-lookup"><span data-stu-id="85495-114">Specify the backup set name.</span></span> <span data-ttu-id="85495-115">Il sistema suggerisce automaticamente un nome predefinito in base al nome del database e al tipo di backup.</span><span class="sxs-lookup"><span data-stu-id="85495-115">The system automatically suggests a default name based on the database name and the backup type.</span></span>  
  
 <span data-ttu-id="85495-116">Per informazioni sui set di backup, vedere [Set di supporti, gruppi di supporti e set di backup &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="85495-116">For information about backup sets, see [Media Sets, Media Families, and Backup Sets &#40;SQL Server&#41;](media-sets-media-families-and-backup-sets-sql-server.md).</span></span>  
  
 <span data-ttu-id="85495-117">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="85495-117">**Description**</span></span>  
 <span data-ttu-id="85495-118">Consente di immettere una descrizione del set di backup.</span><span class="sxs-lookup"><span data-stu-id="85495-118">Enter a description of the backup set.</span></span>  
  
 <span data-ttu-id="85495-119">**Scadenza set di backup**</span><span class="sxs-lookup"><span data-stu-id="85495-119">**Backup set will expire**</span></span>  
 <span data-ttu-id="85495-120">Scegliere una delle opzioni di scadenza seguenti.</span><span class="sxs-lookup"><span data-stu-id="85495-120">Choose one of the following expiration options.</span></span> <span data-ttu-id="85495-121">Questa opzione è disabilitata se è stato scelto **URL** come destinazione di backup.</span><span class="sxs-lookup"><span data-stu-id="85495-121">This option is disabled if **URL** is chosen as the backup destination.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85495-122">**Dopo**</span><span class="sxs-lookup"><span data-stu-id="85495-122">**After**</span></span>|<span data-ttu-id="85495-123">Consente di specificare il numero di giorni che devono trascorrere prima che il set di backup scada e possa venire sovrascritto.</span><span class="sxs-lookup"><span data-stu-id="85495-123">Specify the number of days that must elapse before this backup set expires and can be overwritten.</span></span> <span data-ttu-id="85495-124">È possibile impostare un valore compreso nell'intervallo da 0 a 99999 giorni. L'impostazione del valore 0 giorni indica che il set di backup non ha scadenza.</span><span class="sxs-lookup"><span data-stu-id="85495-124">This value can be from 0 to 99999 days; a value of 0 days means that the backup set will never expire.</span></span><br /><br /> <span data-ttu-id="85495-125">Il valore predefinito per la scadenza del backup corrisponde al valore impostato nell'opzione **Periodo di memorizzazione predefinito supporti di backup (giorni)** .</span><span class="sxs-lookup"><span data-stu-id="85495-125">The default value for backup expiration is the value set in the **Default backup media retention (in days)** option.</span></span> <span data-ttu-id="85495-126">Per accedere a questa opzione fare clic con il pulsante destro del mouse sul nome del server in Esplora oggetti e selezionare **Proprietà**. Fare quindi clic sulla pagina **Impostazioni database** della finestra di dialogo **Proprietà server** .</span><span class="sxs-lookup"><span data-stu-id="85495-126">To access this, right-click the server name in Object Explorer and select **Properties**; then click the **Database Settings** page of the **Server Properties** dialog box.</span></span>|  
|<span data-ttu-id="85495-127">**On**</span><span class="sxs-lookup"><span data-stu-id="85495-127">**On**</span></span>|<span data-ttu-id="85495-128">Consente di specificare la data di scadenza del set di backup per la possibile sovrascrittura.</span><span class="sxs-lookup"><span data-stu-id="85495-128">Specify a specific date when the backup set expires and can be overwritten.</span></span>|  
  
### <a name="compression"></a><span data-ttu-id="85495-129">Compressione</span><span class="sxs-lookup"><span data-stu-id="85495-129">Compression</span></span>  
 [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] <span data-ttu-id="85495-130">(o versioni successive) supporta la [compressione dei backup](backup-compression-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="85495-130">(or a later version) supports [backup compression](backup-compression-sql-server.md).</span></span>  
  
 <span data-ttu-id="85495-131">**Imposta compressione backup**</span><span class="sxs-lookup"><span data-stu-id="85495-131">**Set backup compression**</span></span>  
 <span data-ttu-id="85495-132">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] o versione successiva selezionare uno dei seguenti valori di compressione dei backup:</span><span class="sxs-lookup"><span data-stu-id="85495-132">In [!INCLUDE[ssEnterpriseEd10](../../../includes/ssenterpriseed10-md.md)] (or a later version), select one of the following backup compression values:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85495-133">**Utilizza l'impostazione predefinita del server**</span><span class="sxs-lookup"><span data-stu-id="85495-133">**Use the default server setting**</span></span>|<span data-ttu-id="85495-134">Fare clic su questa opzione per utilizzare l'impostazione predefinita a livello di server.</span><span class="sxs-lookup"><span data-stu-id="85495-134">Click to use the server-level default.</span></span><br /><br /> <span data-ttu-id="85495-135">Questa impostazione predefinita è specificata dall'opzione di configurazione del server **Valore predefinito di compressione backup** .</span><span class="sxs-lookup"><span data-stu-id="85495-135">This default is set by the **backup compression default** server-configuration option.</span></span> <span data-ttu-id="85495-136">Per informazioni su come visualizzare l'impostazione corrente di questa opzione, vedere [Visualizzare o configurare l'opzione di configurazione del server backup compression default](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="85495-136">For information about how to view the current setting of this option, see [View or Configure the backup compression default Server Configuration Option](../../database-engine/configure-windows/view-or-configure-the-backup-compression-default-server-configuration-option.md).</span></span>|  
|<span data-ttu-id="85495-137">**Comprimi backup**</span><span class="sxs-lookup"><span data-stu-id="85495-137">**Compress backup**</span></span>|<span data-ttu-id="85495-138">Fare clic su questa opzione per comprimere il backup, indipendentemente dall'impostazione predefinita a livello di server.</span><span class="sxs-lookup"><span data-stu-id="85495-138">Click to compress the backup, regardless of the server-level default.</span></span><br /><br /> <span data-ttu-id="85495-139">**\*\* Importante \*\*** Per impostazione predefinita, la compressione aumenta significativamente l'uso della CPU e la CPU aggiuntiva usata dal processo di compressione può avere un impatto negativo sulle operazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="85495-139">**\*\* Important \*\*** By default, compression significantly increases CPU usage, and the additional CPU consumed by the compression process might adversely impact concurrent operations.</span></span> <span data-ttu-id="85495-140">Potrebbe pertanto essere necessario creare backup compressi con priorità bassa in una sessione in cui l'utilizzo della CPU è limitato da [Resource Governor](../resource-governor/resource-governor.md).</span><span class="sxs-lookup"><span data-stu-id="85495-140">Therefore, you might want to create low-priority compressed backups in a session whose CPU usage is limited by [Resource Governor](../resource-governor/resource-governor.md).</span></span> <span data-ttu-id="85495-141">Per ulteriori informazioni, vedere [Utilizzo di Resource Governor per limitare l'utilizzo della CPU da parte della compressione dei backup &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="85495-141">For more information, see [Use Resource Governor to Limit CPU Usage by Backup Compression &#40;Transact-SQL&#41;](use-resource-governor-to-limit-cpu-usage-by-backup-compression-transact-sql.md).</span></span>|  
|<span data-ttu-id="85495-142">**Non comprimere il backup**</span><span class="sxs-lookup"><span data-stu-id="85495-142">**Do not compress backup**</span></span>|<span data-ttu-id="85495-143">Fare clic su questa opzione per creare un backup non compresso, indipendentemente dall'impostazione predefinita a livello di server.</span><span class="sxs-lookup"><span data-stu-id="85495-143">Click to create an uncompressed backup, regardless of the server-level default.</span></span>|  
  
### <a name="encryption"></a><span data-ttu-id="85495-144">Crittografia</span><span class="sxs-lookup"><span data-stu-id="85495-144">Encryption</span></span>  
 <span data-ttu-id="85495-145">Per creare un backup crittografato, selezionare la casella di controllo **Crittografa backup** .</span><span class="sxs-lookup"><span data-stu-id="85495-145">To create an encrypted backup, check the **Encrypt backup** check box.</span></span> <span data-ttu-id="85495-146">Selezionare un algoritmo di crittografia da utilizzare per il passaggio di crittografia e specificare un certificato o una chiave asimmetrica da un elenco di chiavi asimmetriche o di certificati esistenti.</span><span class="sxs-lookup"><span data-stu-id="85495-146">Select an encryption algorithm to use for the encryption step, and provide a Certificate or Asymmetric key from a list of existing certificates or asymmetric keys.</span></span> <span data-ttu-id="85495-147">Gli algoritmi di crittografia disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="85495-147">The available algorithms for encryption are:</span></span>  
  
-   <span data-ttu-id="85495-148">AES 128</span><span class="sxs-lookup"><span data-stu-id="85495-148">AES 128</span></span>  
  
-   <span data-ttu-id="85495-149">AES 192</span><span class="sxs-lookup"><span data-stu-id="85495-149">AES 192</span></span>  
  
-   <span data-ttu-id="85495-150">AES 256</span><span class="sxs-lookup"><span data-stu-id="85495-150">AES 256</span></span>  
  
-   <span data-ttu-id="85495-151">Triple DES</span><span class="sxs-lookup"><span data-stu-id="85495-151">Triple DES</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="85495-152">L'opzione di crittografia è disabilitata se si è scelto di eseguire l'accodamento a un set di backup esistente.</span><span class="sxs-lookup"><span data-stu-id="85495-152">The encryption option is disabled if you selected to append to existing backup set.</span></span>  
>   
>  <span data-ttu-id="85495-153">È consigliabile eseguire il backup del certificato o delle chiavi e archiviarli in un percorso diverso da quello utilizzato per il backup crittografato.</span><span class="sxs-lookup"><span data-stu-id="85495-153">It is recommended practice to back up your certificate or keys and store them in a different location than the backup you encrypted.</span></span>  
>   
>  <span data-ttu-id="85495-154">Sono supportate solo le chiavi che si trovano in Extensible Key Management (EKM).</span><span class="sxs-lookup"><span data-stu-id="85495-154">Only keys residing in the Extensible Key Management (EKM) are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85495-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85495-155">See Also</span></span>  
 <span data-ttu-id="85495-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="85495-156">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 <span data-ttu-id="85495-157">[Backup di un log delle transazioni &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85495-157">[Back Up a Transaction Log &#40;SQL Server&#41;](back-up-a-transaction-log-sql-server.md) </span></span>  
 <span data-ttu-id="85495-158">[Backup di file e filegroup &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="85495-158">[Back Up Files and Filegroups &#40;SQL Server&#41;](back-up-files-and-filegroups-sql-server.md) </span></span>  
 [<span data-ttu-id="85495-159">Esecuzione del backup del log delle transazioni quando il database è danneggiato &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="85495-159">Back Up the Transaction Log When the Database Is Damaged &#40;SQL Server&#41;</span></span>](back-up-the-transaction-log-when-the-database-is-damaged-sql-server.md)  
  
  
