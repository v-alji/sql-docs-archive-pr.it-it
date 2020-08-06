---
title: Configurare l'opzione di configurazione del server min memory per query | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- memory [SQL Server], queries
- minimum query memory
- queries [SQL Server], memory
- min memory per query option
ms.assetid: ecd3fb79-b4a6-432f-9ef5-530e0d42d5a6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 56d85f36840f0900c8b5e986334a99ba610d3930
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630043"
---
# <a name="configure-the-min-memory-per-query-server-configuration-option"></a><span data-ttu-id="c9e85-102">Configurare l'opzione di configurazione del server min memory per query</span><span class="sxs-lookup"><span data-stu-id="c9e85-102">Configure the min memory per query Server Configuration Option</span></span>
  <span data-ttu-id="c9e85-103">In questo argomento viene descritto come configurare l' `min memory per query` opzione di configurazione del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e85-103">This topic describes how to configure the `min memory per query` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c9e85-104">L' `min memory per query` opzione specifica la quantità minima di memoria (in kilobyte) che verrà allocata per l'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="c9e85-104">The `min memory per query` option specifies the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span> <span data-ttu-id="c9e85-105">Se, ad esempio, `min memory per query` è impostato su 2.048 KB, per la query verrà garantita almeno la quantità di memoria totale.</span><span class="sxs-lookup"><span data-stu-id="c9e85-105">For example, if `min memory per query` is set to 2,048 KB, the query is guaranteed to get at least that much total memory.</span></span> <span data-ttu-id="c9e85-106">Il valore predefinito è 1024 KB.</span><span class="sxs-lookup"><span data-stu-id="c9e85-106">The default value is 1,024 KB.</span></span> <span data-ttu-id="c9e85-107">Il valore minimo è 512 KB mentre quello massimo è 2.147.483.647 KB (2 GB).</span><span class="sxs-lookup"><span data-stu-id="c9e85-107">The minimum value 512 KB, and the maximum is 2,147,483,647 KB (2 GB).</span></span>  
  
 <span data-ttu-id="c9e85-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c9e85-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c9e85-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c9e85-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c9e85-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c9e85-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="c9e85-111">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c9e85-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="c9e85-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c9e85-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c9e85-113">**Per configurare l'opzione min memory per query utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="c9e85-113">**To configure the min memory per query option, using:**</span></span>  
  
     [<span data-ttu-id="c9e85-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9e85-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c9e85-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9e85-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="c9e85-116">**Completamento:**  [Dopo la configurazione dell'opzione min memory per query](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c9e85-116">**Follow Up:**  [After you configure the min memory per query option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c9e85-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c9e85-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="c9e85-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="c9e85-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="c9e85-119">La quantità di memoria minima per query ha la precedenza sull' [opzione index create memory](configure-the-index-create-memory-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="c9e85-119">The amount of min memory per query has precedence over the [index create memory Option](configure-the-index-create-memory-server-configuration-option.md).</span></span> <span data-ttu-id="c9e85-120">Se si modificano entrambe le opzioni e index create memory è minore di min memory per query, verrà visualizzato un messaggio di avviso, ma il valore risulterà impostato.</span><span class="sxs-lookup"><span data-stu-id="c9e85-120">If you modify both options and the index create memory is less than min memory per query, you receive a warning message, but the value is set.</span></span> <span data-ttu-id="c9e85-121">Durante l'esecuzione delle query verrà visualizzato un altro avviso simile.</span><span class="sxs-lookup"><span data-stu-id="c9e85-121">During query execution you receive another similar warning.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c9e85-122">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="c9e85-122">Recommendations</span></span>  
  
-   <span data-ttu-id="c9e85-123">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9e85-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="c9e85-124">Con Query Processor di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] si tenta di determinare la quantità ottimale di memoria da allocare per una query.</span><span class="sxs-lookup"><span data-stu-id="c9e85-124">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] query processor tries to determine the optimal amount of memory to allocate to a query.</span></span> <span data-ttu-id="c9e85-125">L'opzione min memory per query consente all'amministratore di specificare la quantità di memoria minima assegnata a ogni query.</span><span class="sxs-lookup"><span data-stu-id="c9e85-125">The min memory per query option lets the administrator specify the minimum amount of memory any single query receives.</span></span> <span data-ttu-id="c9e85-126">In genere la quantità di memoria aumenta se le query comportano operazioni di hashing o di ordinamento per quantità di dati elevate.</span><span class="sxs-lookup"><span data-stu-id="c9e85-126">Queries generally receive more memory than this if they have hash and sort operations on a large volume of data.</span></span> <span data-ttu-id="c9e85-127">L'aumento del valore dell'opzione min memory per query può migliorare le prestazioni per alcune query di dimensioni ridotte o medie, ma può provocare una maggiore contesa per le risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="c9e85-127">Increasing the value of min memory per query may improve performance for some small to medium-sized queries, but doing so could lead to increased competition for memory resources.</span></span> <span data-ttu-id="c9e85-128">L'opzione min memory per query include la memoria allocata per l'ordinamento.</span><span class="sxs-lookup"><span data-stu-id="c9e85-128">The min memory per query option includes memory allocated for sorting.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c9e85-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c9e85-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c9e85-130">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c9e85-130">Permissions</span></span>  
 <span data-ttu-id="c9e85-131">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c9e85-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="c9e85-132">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="c9e85-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="c9e85-133">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="c9e85-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c9e85-134">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c9e85-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="c9e85-135">Per configurare l'opzione min memory per query</span><span class="sxs-lookup"><span data-stu-id="c9e85-135">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="c9e85-136">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c9e85-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="c9e85-137">Fare clic sul nodo **Memoria** .</span><span class="sxs-lookup"><span data-stu-id="c9e85-137">Click the **Memory** node.</span></span>  
  
3.  <span data-ttu-id="c9e85-138">Nella casella **Memoria minima per le query** immettere la quantità minima di memoria, in kilobyte, che verrà allocata per l'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="c9e85-138">In the **Minimum memory per query** box, enter the minimum amount of memory (in kilobytes) that will be allocated for the execution of a query.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c9e85-139">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c9e85-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-min-memory-per-query-option"></a><span data-ttu-id="c9e85-140">Per configurare l'opzione min memory per query</span><span class="sxs-lookup"><span data-stu-id="c9e85-140">To configure the min memory per query option</span></span>  
  
1.  <span data-ttu-id="c9e85-141">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9e85-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c9e85-142">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c9e85-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c9e85-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c9e85-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c9e85-144">In questo esempio si illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `min memory per query` su `3500` KB.</span><span class="sxs-lookup"><span data-stu-id="c9e85-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `min memory per query` option to `3500` KB.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'min memory per query', 3500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-min-memory-per-query-option"></a><a name="FollowUp"></a> <span data-ttu-id="c9e85-145">Completamento: Dopo la configurazione dell'opzione min memory per query</span><span class="sxs-lookup"><span data-stu-id="c9e85-145">Follow Up: After you configure the min memory per query option</span></span>  
 <span data-ttu-id="c9e85-146">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="c9e85-146">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e85-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e85-147">See Also</span></span>  
 <span data-ttu-id="c9e85-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9e85-148">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="c9e85-149">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c9e85-149">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="c9e85-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c9e85-150">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="c9e85-151">Configurare l'opzione di configurazione del server index create memory</span><span class="sxs-lookup"><span data-stu-id="c9e85-151">Configure the index create memory Server Configuration Option</span></span>](configure-the-index-create-memory-server-configuration-option.md)  
  
  
