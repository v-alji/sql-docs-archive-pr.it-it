---
title: Configurare l'opzione di configurazione del server cursor threshold | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cursor threshold option
ms.assetid: 189f2067-c6c4-48bd-9bd9-65f6b2021c12
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0d7fd9ecafda270a02f1fba9f5dd74adc9e299d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638100"
---
# <a name="configure-the-cursor-threshold-server-configuration-option"></a><span data-ttu-id="1e0d9-102">Configurare l'opzione di configurazione del server cursor threshold</span><span class="sxs-lookup"><span data-stu-id="1e0d9-102">Configure the cursor threshold Server Configuration Option</span></span>
  <span data-ttu-id="1e0d9-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **cursor threshold** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e0d9-103">This topic describes how to configure the **cursor threshold** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1e0d9-104">Con l'opzione **cursor threshold** è possibile specificare il numero delle righe del set di cursori in corrispondenza del quale i keyset del cursore vengono generati in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-104">The **cursor threshold** option specifies the number of rows in the cursor set at which cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="1e0d9-105">Quando i cursori generano un keyset per un set di risultati, Query Optimizer produce una stima del numero di righe che verranno restituite per tale set di risultati.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-105">When cursors generate a keyset for a result set, the query optimizer estimates the number of rows that will be returned for that result set.</span></span> <span data-ttu-id="1e0d9-106">Se il numero stimato di righe restituite supera la soglia, il cursore viene generato in modo asincrono ed è pertanto possibile recuperare le righe dal cursore durante il popolamento del cursore stesso.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-106">If the query optimizer estimates that the number of returned rows is greater than this threshold, the cursor is generated asynchronously, allowing the user to fetch rows from the cursor while the cursor continues to be populated.</span></span> <span data-ttu-id="1e0d9-107">In caso contrario, il cursore viene generato in modo sincrono e la query attende che vengano restituite tutte le righe.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-107">Otherwise, the cursor is generated synchronously, and the query waits until all rows are returned.</span></span>  
  
 <span data-ttu-id="1e0d9-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="1e0d9-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="1e0d9-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="1e0d9-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="1e0d9-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1e0d9-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="1e0d9-111">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="1e0d9-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="1e0d9-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1e0d9-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="1e0d9-113">**Per configurare l'opzione cursor threshold tramite:**</span><span class="sxs-lookup"><span data-stu-id="1e0d9-113">**To configure the cursor threshold option, using:**</span></span>  
  
     [<span data-ttu-id="1e0d9-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e0d9-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="1e0d9-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e0d9-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="1e0d9-116">**Completamento:**  [Dopo la configurazione dell'opzione cursor threshold](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="1e0d9-116">**Follow Up:**  [After you configure the cursor threshold option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1e0d9-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1e0d9-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="1e0d9-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="1e0d9-118">Limitations and Restrictions</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1e0d9-119">non supporta la generazione asincrona di cursori [!INCLUDE[tsql](../../includes/tsql-md.md)] gestiti da keyset o statici.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-119">does not support generating keyset-driven or static [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors asynchronously.</span></span> [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="1e0d9-120">, ad esempio OPEN o FETCH, vengono eseguite in batch. Non è quindi necessario generare i cursori [!INCLUDE[tsql](../../includes/tsql-md.md)] in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-120">cursor operations such as OPEN or FETCH are batched, so there is no need for the asynchronous generation of [!INCLUDE[tsql](../../includes/tsql-md.md)] cursors.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1e0d9-121">supporta ancora i cursori API del server statici o gestiti da keyset asincroni nei casi in cui l'istruzione OPEN a bassa latenza costituisce un problema, a causa dei round trip del client per ogni operazione del cursore.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-121">continues to support asynchronous keyset-driven or static application programming interface (API) server cursors where low latency OPEN is a concern, due to client round trips for each cursor operation.</span></span>  
  
-   <span data-ttu-id="1e0d9-122">L'accuratezza con cui Query Optimizer è in grado di stimare il numero di righe in un keyset dipende dal livello di aggiornamento delle statistiche relative a tutte le tabelle del cursore.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-122">The accuracy of the query optimizer to determine an estimate for the number of rows in a keyset depends on the currency of the statistics for each of the tables in the cursor.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="1e0d9-123">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="1e0d9-123">Recommendations</span></span>  
  
-   <span data-ttu-id="1e0d9-124">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-124">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="1e0d9-125">Se si imposta **cursor threshold** su -1, tutti i keyset vengono generati in modo sincrono, a vantaggio dei set di cursori di dimensioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-125">If you set **cursor threshold** to -1, all keysets are generated synchronously, which benefits small cursor sets.</span></span> <span data-ttu-id="1e0d9-126">Se si imposta **cursor threshold** su 0, tutti i keyset dei cursori vengono generati in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-126">If you set **cursor threshold** to 0, all cursor keysets are generated asynchronously.</span></span> <span data-ttu-id="1e0d9-127">Se si impostano altri valori, Query Optimizer verifica il numero di righe previste nel set di cursori. Se tale numero supera il valore impostato per **cursor threshold**, il keyset viene compilato in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-127">With other values, the query optimizer compares the number of expected rows in the cursor set and builds the keyset asynchronously if it exceeds the number set in **cursor threshold**.</span></span> <span data-ttu-id="1e0d9-128">Non impostare **cursor threshold** su un valore troppo basso, in quanto è opportuno che i set di risultati di dimensioni ridotte vengano compilati in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-128">Do not set **cursor threshold** too low, because small result sets are better built synchronously.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1e0d9-129">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1e0d9-129">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1e0d9-130">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1e0d9-130">Permissions</span></span>  
 <span data-ttu-id="1e0d9-131">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-131">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="1e0d9-132">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-132">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="1e0d9-133">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-133">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1e0d9-134">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1e0d9-134">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="1e0d9-135">Per configurare l'opzione cursor threshold</span><span class="sxs-lookup"><span data-stu-id="1e0d9-135">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="1e0d9-136">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-136">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="1e0d9-137">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-137">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="1e0d9-138">In **Varie**specificare il valore desiderato per l'opzione **Cursor Threshold** .</span><span class="sxs-lookup"><span data-stu-id="1e0d9-138">Under **Miscellaneous**, change the **Cursor Threshold** option to the value you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1e0d9-139">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1e0d9-139">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-cursor-threshold-option"></a><span data-ttu-id="1e0d9-140">Per configurare l'opzione cursor threshold</span><span class="sxs-lookup"><span data-stu-id="1e0d9-140">To configure the cursor threshold option</span></span>  
  
1.  <span data-ttu-id="1e0d9-141">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e0d9-141">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1e0d9-142">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-142">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1e0d9-143">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-143">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1e0d9-144">Questo esempio mostra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare l'opzione `cursor threshold` su `0` in modo che i keyset del cursore vengano generati in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-144">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the `cursor threshold` option to `0` so that cursor keysets are generated asynchronously.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'cursor threshold', 0 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
 <span data-ttu-id="1e0d9-145">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-145">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-cursor-threshold-option"></a><a name="FollowUp"></a> <span data-ttu-id="1e0d9-146">Completamento: Dopo la configurazione dell'opzione cursor threshold</span><span class="sxs-lookup"><span data-stu-id="1e0d9-146">Follow Up: After you configure the cursor threshold option</span></span>  
 <span data-ttu-id="1e0d9-147">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="1e0d9-147">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0d9-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e0d9-148">See Also</span></span>  
 <span data-ttu-id="1e0d9-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e0d9-149">[@@CURSOR_ROWS &#40;Transact-SQL&#41;](/sql/t-sql/functions/cursor-rows-transact-sql) </span></span>  
 <span data-ttu-id="1e0d9-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e0d9-150">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="1e0d9-151">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="1e0d9-151">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="1e0d9-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1e0d9-152">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="1e0d9-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1e0d9-153">UPDATE STATISTICS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/update-statistics-transact-sql)  
  
  
