---
title: Configurare l'opzione di configurazione del server index create memory | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- index create memory option
ms.assetid: 3d722d9b-bada-4bf5-a9d7-bfc556bb4915
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6cd0aeb93d3fb68089338335068fdaaae19919fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715699"
---
# <a name="configure-the-index-create-memory-server-configuration-option"></a><span data-ttu-id="c7fa7-102">Configurare l'opzione di configurazione del server index create memory</span><span class="sxs-lookup"><span data-stu-id="c7fa7-102">Configure the index create memory Server Configuration Option</span></span>
  <span data-ttu-id="c7fa7-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **index create memory** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7fa7-103">This topic describes how to configure the **index create memory** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c7fa7-104">Con l'opzione **index create memory** è possibile controllare la quantità massima di memoria allocata inizialmente per la creazione di indici.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-104">The **index create memory** option controls the maximum amount of memory initially allocated for creating indexes.</span></span> <span data-ttu-id="c7fa7-105">Il valore predefinito per questa opzione è 0 (configurazione automatica).</span><span class="sxs-lookup"><span data-stu-id="c7fa7-105">The default value for this option is 0 (self-configuring).</span></span> <span data-ttu-id="c7fa7-106">Se in un secondo momento risulta necessaria una quantità maggiore di memoria per la creazione degli indici e la memoria è disponibile, verrà usata dal server, superando quindi le impostazioni relative a questa opzione.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-106">If more memory is later needed for index creation and the memory is available, the server will use it; thereby, exceeding the setting of this option.</span></span> <span data-ttu-id="c7fa7-107">Se non è disponibile ulteriore memoria, la creazione degli indici continuerà, usando la memoria già allocata.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-107">If additional memory is not available, the index creation will continue using the memory already allocated.</span></span>  
  
 <span data-ttu-id="c7fa7-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c7fa7-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c7fa7-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c7fa7-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c7fa7-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c7fa7-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c7fa7-111">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c7fa7-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c7fa7-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c7fa7-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c7fa7-113">**Per configurare l'opzione index create memory tramite:**</span><span class="sxs-lookup"><span data-stu-id="c7fa7-113">**To configure the index create memory option, using:**</span></span>  
  
     [<span data-ttu-id="c7fa7-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7fa7-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c7fa7-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7fa7-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="c7fa7-116">**Completamento:**  [Dopo la configurazione dell'opzione index create memory](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c7fa7-116">**Follow Up:**  [After you configure the index create memory option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c7fa7-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c7fa7-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c7fa7-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c7fa7-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c7fa7-119">L'impostazione dell'opzione **min memory per query** ha la precedenza sull'opzione **index create memory**.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-119">The setting of the **min memory per query** option has precedence over the **index create memory** option.</span></span> <span data-ttu-id="c7fa7-120">Se si modificano entrambe le opzioni e **index create memory** è minore di **min memory per query**, verrà visualizzato un messaggio di avviso, ma il valore risulterà impostato.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-120">If you change both options and the **index create memory** is less than **min memory per query**, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="c7fa7-121">Durante l'esecuzione della query verrà visualizzato un avviso analogo.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-121">During query execution, you receive a similar warning.</span></span>  
  
-   <span data-ttu-id="c7fa7-122">Quando si usano tabelle e indici partizionati, è possibile che i requisiti minimi di memoria aumentino in modo significativo in caso di indici partizionati non allineati e di un grado elevato di parallelismo.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-122">When using partitioned tables and indexes, the minimum memory requirements for index creation may increase significantly if there are non-aligned partitioned indexes and a high degree of parallelism.</span></span> <span data-ttu-id="c7fa7-123">Con questa opzione è possibile controllare la quantità totale iniziale di memoria allocata per tutte le partizioni dell'indice in un'unica operazione di creazione dell'indice.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-123">This option controls the total initial amount of memory allocated for all index partitions in a single index creation operation.</span></span> <span data-ttu-id="c7fa7-124">Se la quantità impostata tramite questa opzione è inferiore rispetto al valore minimo necessario per l'esecuzione, la query verrà terminata e verrà visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-124">The query will terminate with an error message if the amount set by this option is less than the minimum required to run the query.</span></span>  
  
-   <span data-ttu-id="c7fa7-125">Il valore di esecuzione per questa opzione non supererà la quantità di memoria effettiva che può essere usata per il sistema operativo e la piattaforma hardware in cui viene eseguito [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7fa7-125">The run value for this option will not exceed the actual amount of memory that can be used for the operating system and hardware platform on which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span> <span data-ttu-id="c7fa7-126">Nei sistemi operativi a 32 bit questo valore sarà minore di 3 gigabyte (GB).</span><span class="sxs-lookup"><span data-stu-id="c7fa7-126">On 32-bit operating systems, the run value will be less than 3 gigabytes (GB).</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c7fa7-127">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c7fa7-127">Recommendations</span></span>  
  
-   <span data-ttu-id="c7fa7-128">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c7fa7-128">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="c7fa7-129">**Index Create Memory** è un'opzione a configurazione automatica e solitamente non richiede alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-129">The **index create memory** option is self-configuring and usually works without requiring adjustment.</span></span> <span data-ttu-id="c7fa7-130">Se tuttavia si riscontrano difficoltà nella creazione di indici, valutare l'opportunità di aumentare il valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-130">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c7fa7-131">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c7fa7-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c7fa7-132">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c7fa7-132">Permissions</span></span>  
 <span data-ttu-id="c7fa7-133">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="c7fa7-134">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c7fa7-135">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="c7fa7-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c7fa7-136">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7fa7-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="c7fa7-137">Per configurare l'opzione index create memory</span><span class="sxs-lookup"><span data-stu-id="c7fa7-137">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="c7fa7-138">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c7fa7-139">Fare clic sul nodo **Memoria** .</span><span class="sxs-lookup"><span data-stu-id="c7fa7-139">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="c7fa7-140">In **Memoria per la creazione degli indici**digitare o selezionare il valore desiderato per l'opzione index create memory.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-140">Under **Index creation memory**, type or select the desired value for the index create memory option.</span></span>  
  
     <span data-ttu-id="c7fa7-141">L'opzione **index create memory** consente di gestire la quantità di memoria usata dagli ordinamenti per la creazione di indici.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-141">Use the **index create memory** option to control the amount of memory used by index creation sorts.</span></span> <span data-ttu-id="c7fa7-142">**index create memory** è un'opzione a configurazione automatica e nella maggior parte può essere usata senza apportare alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-142">The **index create memory** option is self-configuring and should work in most cases without requiring adjustment.</span></span> <span data-ttu-id="c7fa7-143">Se tuttavia si riscontrano difficoltà nella creazione di indici, valutare l'opportunità di aumentare il valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-143">However, if you experience difficulties creating indexes, consider increasing the value of this option from its run value.</span></span> <span data-ttu-id="c7fa7-144">Gli ordinamenti per le query sono gestiti tramite l'opzione **min memory per query** .</span><span class="sxs-lookup"><span data-stu-id="c7fa7-144">Query sorts are controlled through the **min memory per query** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c7fa7-145">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7fa7-145">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-index-create-memory-option"></a><span data-ttu-id="c7fa7-146">Per configurare l'opzione index create memory</span><span class="sxs-lookup"><span data-stu-id="c7fa7-146">To configure the index create memory option</span></span>  
  
1.  <span data-ttu-id="c7fa7-147">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7fa7-147">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c7fa7-148">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-148">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c7fa7-149">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-149">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c7fa7-150">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `index create memory` su `4096`.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-150">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `index create memory` option to `4096`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
EXEC sp_configure 'index create memory', 4096  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="c7fa7-151">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-151">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-index-create-memory-option"></a><a name="FollowUp"></a> <span data-ttu-id="c7fa7-152">Completamento: Dopo la configurazione dell'opzione index create memory</span><span class="sxs-lookup"><span data-stu-id="c7fa7-152">Follow Up: After you configure the index create memory option</span></span>  
 <span data-ttu-id="c7fa7-153">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="c7fa7-153">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7fa7-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7fa7-154">See Also</span></span>  
 <span data-ttu-id="c7fa7-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c7fa7-155">[sys.configurations &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) </span></span>  
 <span data-ttu-id="c7fa7-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c7fa7-156">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c7fa7-157">[Opzioni di configurazione del server Server Memory](server-memory-server-configuration-options.md) </span><span class="sxs-lookup"><span data-stu-id="c7fa7-157">[Server Memory Server Configuration Options](server-memory-server-configuration-options.md) </span></span>  
 <span data-ttu-id="c7fa7-158">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c7fa7-158">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="c7fa7-159">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c7fa7-159">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
