---
title: Configurare l'opzione di configurazione del server locks | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- locks option [SQL Server]
ms.assetid: b0cf0f86-7652-4574-a9fb-908e10d03973
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e45f4cc539be585966eb0beb30d4938b504c3419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724928"
---
# <a name="configure-the-locks-server-configuration-option"></a><span data-ttu-id="15914-102">Configurare l'opzione di configurazione del server locks</span><span class="sxs-lookup"><span data-stu-id="15914-102">Configure the locks Server Configuration Option</span></span>
  <span data-ttu-id="15914-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **locks** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15914-103">This topic describes how to configure the **locks** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="15914-104">Con l'opzione **locks** è possibile impostare il numero massimo di blocchi disponibili e pertanto limitare la quantità di memoria utilizzata per i blocchi stessi dal [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15914-104">The **locks** option sets the maximum number of available locks, thereby limiting the amount of memory the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] uses for them.</span></span> <span data-ttu-id="15914-105">L'impostazione predefinita è 0, che consente al [!INCLUDE[ssDE](../../includes/ssde-md.md)] di allocare e deallocare le strutture di blocco in modo dinamico, in base alle variazioni dei requisiti di sistema.</span><span class="sxs-lookup"><span data-stu-id="15914-105">The default setting is 0, which allows the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to allocate and deallocate lock structures dynamically, based on changing system requirements.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="15914-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="15914-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="15914-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="15914-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="15914-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="15914-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="15914-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="15914-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="15914-110">**Per configurare l'opzione locks utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="15914-110">**To configure the locks option, using:**</span></span>  
  
     [<span data-ttu-id="15914-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15914-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="15914-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15914-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="15914-113">**Completamento:**  [Dopo la configurazione dell'opzione locks](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="15914-113">**Follow Up:**  [After you configure the locks option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="15914-114">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="15914-114">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="15914-115">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="15914-115">Recommendations</span></span>  
  
-   <span data-ttu-id="15914-116">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15914-116">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="15914-117">Quando si avvia il server con l'opzione **locks** impostata su 0, viene acquisita dal [!INCLUDE[ssDE](../../includes/ssde-md.md)] una quantità di memoria sufficiente per un pool iniziale di 2.500 strutture di blocco tramite Gestione blocchi.</span><span class="sxs-lookup"><span data-stu-id="15914-117">When the server is started with **locks** set to 0, the lock manager acquires sufficient memory from the [!INCLUDE[ssDE](../../includes/ssde-md.md)] for an initial pool of 2,500 lock structures.</span></span> <span data-ttu-id="15914-118">Quando il pool di blocchi è esaurito, viene acquisita memoria aggiuntiva per il pool.</span><span class="sxs-lookup"><span data-stu-id="15914-118">As the lock pool is exhausted, additional memory is acquired for the pool.</span></span>  
  
     <span data-ttu-id="15914-119">In genere, se per il pool di blocchi è necessaria una quantità di memoria superiore a quella disponibile nel pool di memoria del [!INCLUDE[ssDE](../../includes/ssde-md.md)] ed è disponibile ulteriore memoria del computer, ovvero non è stata raggiunta la soglia **max server memory** , tale memoria viene allocata dinamicamente dal [!INCLUDE[ssDE](../../includes/ssde-md.md)] per soddisfare la richiesta di blocchi.</span><span class="sxs-lookup"><span data-stu-id="15914-119">Generally, if more memory is required for the lock pool than is available in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool, and more computer memory is available (the **max server memory** threshold has not been reached), the [!INCLUDE[ssDE](../../includes/ssde-md.md)] allocates memory dynamically to satisfy the request for locks.</span></span> <span data-ttu-id="15914-120">Se tuttavia questa modalità di allocazione di memoria determina il paging a livello del sistema operativo, ad esempio se un'altra applicazione eseguita sul computer in cui si trova l'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sta utilizzando la memoria disponibile, lo spazio aggiuntivo per i blocchi non viene allocato.</span><span class="sxs-lookup"><span data-stu-id="15914-120">However, if allocating that memory would cause paging at the operating system level (for example, if another application is running on the same computer as an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and using that memory), more lock space is not allocated.</span></span> <span data-ttu-id="15914-121">Il pool di blocchi dinamico può acquisire fino al 40% della memoria disponibile per il [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15914-121">The dynamic lock pool does not acquire more than 60 percent of the memory allocated to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="15914-122">Se il pool di blocchi raggiunge il 60% della memoria acquisita da un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)]oppure se nel computer non è disponibile ulteriore memoria, eventuali richieste aggiuntive di blocchi generano un errore.</span><span class="sxs-lookup"><span data-stu-id="15914-122">After the lock pool has reached 60 percent of the memory acquired by an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or no more memory is available on the computer, further requests for locks generate an error.</span></span>  
  
     <span data-ttu-id="15914-123">La configurazione consigliata prevede che [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzi i blocchi dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="15914-123">Allowing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use locks dynamically is the recommended configuration.</span></span> <span data-ttu-id="15914-124">È tuttavia possibile impostare l'opzione **locks** e impedire l'allocazione dinamica di risorse di blocco da parte di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15914-124">However, you can set **locks** and override the ability of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to allocate lock resources dynamically.</span></span> <span data-ttu-id="15914-125">Se l'opzione **locks** è impostata su un valore diverso da 0, il [!INCLUDE[ssDE](../../includes/ssde-md.md)] è in grado di allocare solo il numero di blocchi corrispondente al valore specificato in **locks**.</span><span class="sxs-lookup"><span data-stu-id="15914-125">When **locks** is set to a value other than 0, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] cannot allocate more locks than the value specified in **locks**.</span></span> <span data-ttu-id="15914-126">Aumentare tale valore se in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene visualizzato un messaggio indicante che è stato superato il numero di blocchi disponibili.</span><span class="sxs-lookup"><span data-stu-id="15914-126">Increase this value if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] displays a message that you have exceeded the number of available locks.</span></span> <span data-ttu-id="15914-127">Poiché ogni blocco richiede memoria (96 byte), l'aumento del valore può richiedere anche l'aumento della quantità di memoria destinata al server.</span><span class="sxs-lookup"><span data-stu-id="15914-127">Because each lock consumes memory (96 bytes per lock), increasing this value can require increasing the amount of memory dedicated to the server.</span></span>  
  
-   <span data-ttu-id="15914-128">L'opzione **locks** influisce inoltre sul momento in cui si verifica l'escalation dei blocchi.</span><span class="sxs-lookup"><span data-stu-id="15914-128">The **locks** option also affects when lock escalation occurs.</span></span> <span data-ttu-id="15914-129">Se l'opzione **locks** è impostata su 0, l'escalation dei blocchi si verifica quando la memoria utilizzata dalle strutture di blocco correnti raggiunge il 40% del pool di memoria del [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15914-129">When **locks** is set to 0, lock escalation occurs when the memory used by the current lock structures reaches 40 percent of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] memory pool.</span></span> <span data-ttu-id="15914-130">Se l'opzione **locks** è impostata su un valore diverso da 0, l'escalation dei blocchi si verifica quando il numero dei blocchi raggiunge il 40% del valore specificato per l'opzione **locks**.</span><span class="sxs-lookup"><span data-stu-id="15914-130">When **locks** is not set to 0, lock escalation occurs when the number of locks reaches 40 percent of the value specified for **locks**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="15914-131">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="15914-131">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="15914-132">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="15914-132">Permissions</span></span>  
 <span data-ttu-id="15914-133">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="15914-133">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="15914-134">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="15914-134">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="15914-135">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="15914-135">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="15914-136">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="15914-136">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="15914-137">Per configurare l'opzione locks</span><span class="sxs-lookup"><span data-stu-id="15914-137">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="15914-138">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="15914-138">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="15914-139">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="15914-139">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="15914-140">Nell'area **Parallelismo**digitare il valore desiderato per l'opzione **locks** .</span><span class="sxs-lookup"><span data-stu-id="15914-140">Under **Parallelism**, type the desired value for the **locks** option.</span></span>  
  
     <span data-ttu-id="15914-141">L'opzione **locks** consente di impostare il numero massimo di blocchi disponibili e pertanto limitare la quantità di memoria utilizzata per i blocchi stessi da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="15914-141">Use the **locks** option to set the maximum number of available locks, thereby limiting the amount of memory [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses for them.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="15914-142">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="15914-142">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-locks-option"></a><span data-ttu-id="15914-143">Per configurare l'opzione locks</span><span class="sxs-lookup"><span data-stu-id="15914-143">To configure the locks option</span></span>  
  
1.  <span data-ttu-id="15914-144">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="15914-144">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="15914-145">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="15914-145">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="15914-146">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="15914-146">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="15914-147">Questo esempio mostra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `locks` su `20000`per poter stabilire il numero di blocchi disponibili a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="15914-147">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `locks` option to set the number of locks available for all users to `20000`.</span></span>  
  
```sql  
Use AdventureWorks2012 ;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'locks', 20000;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="15914-148">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="15914-148">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-locks-option"></a><a name="FollowUp"></a> <span data-ttu-id="15914-149">Completamento: Dopo la configurazione dell'opzione locks</span><span class="sxs-lookup"><span data-stu-id="15914-149">Follow Up: After you configure the locks option</span></span>  
 <span data-ttu-id="15914-150">Per poter rendere effettiva l'impostazione, è necessario riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="15914-150">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15914-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15914-151">See Also</span></span>  
 <span data-ttu-id="15914-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="15914-152">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="15914-153">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="15914-153">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="15914-154">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="15914-154">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
