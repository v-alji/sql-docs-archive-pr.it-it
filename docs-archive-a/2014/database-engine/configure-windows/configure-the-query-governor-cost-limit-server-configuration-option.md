---
title: Configurare l'opzione di configurazione del server query governor cost limit | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], time to execute
- query governor cost limit option [SQL Server]
- time [SQL Server], query run time
ms.assetid: e7b8f084-1052-4133-959b-cebf4add790f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4d4f8420bf8ed8c08d3626c797968c041a40f7c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624944"
---
# <a name="configure-the-query-governor-cost-limit-server-configuration-option"></a><span data-ttu-id="8bc79-102">Configurare l'opzione di configurazione del server query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="8bc79-102">Configure the query governor cost limit Server Configuration Option</span></span>
  <span data-ttu-id="8bc79-103">In questo argomento viene descritto come configurare l' `query governor cost limit` opzione di configurazione del server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bc79-103">This topic describes how to configure the `query governor cost limit` server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="8bc79-104">L'opzione Query Governor Cost Limit consente di specificare un limite di tempo massimo per l'esecuzione di una query.</span><span class="sxs-lookup"><span data-stu-id="8bc79-104">The query governor cost limit option specifies an upper limit on the time period in which a query can run.</span></span> <span data-ttu-id="8bc79-105">Il costo delle query equivale al tempo trascorso, in secondi, stimato per l'esecuzione di una query in una configurazione hardware specifica.</span><span class="sxs-lookup"><span data-stu-id="8bc79-105">Query cost refers to the estimated elapsed time, in seconds, that is required to complete a query on a specific hardware configuration.</span></span> <span data-ttu-id="8bc79-106">Il valore predefinito per questa opzione è 0, cioè Query Governor viene impostato su OFF.</span><span class="sxs-lookup"><span data-stu-id="8bc79-106">The default value for this option is 0, which sets the query governor to off.</span></span> <span data-ttu-id="8bc79-107">In questo modo, tutte le query vengono eseguite senza limitazione di tempo.</span><span class="sxs-lookup"><span data-stu-id="8bc79-107">This allows all queries to run without any time limitation.</span></span> <span data-ttu-id="8bc79-108">Se si specifica un valore diverso da zero e positivo, tramite Query Governor non sarà possibile l'esecuzione delle query il cui costo stimato supera quel valore.</span><span class="sxs-lookup"><span data-stu-id="8bc79-108">If you specify a nonzero, nonnegative value, the query governor disallows execution of any query that has an estimated cost that exceeds that value.</span></span>  
  
 <span data-ttu-id="8bc79-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="8bc79-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="8bc79-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="8bc79-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="8bc79-111">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="8bc79-111">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="8bc79-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8bc79-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="8bc79-113">**Per configurare l'opzione query governor cost limit utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="8bc79-113">**To configure the query governor cost limit option, using:**</span></span>  
  
     [<span data-ttu-id="8bc79-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8bc79-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="8bc79-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8bc79-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="8bc79-116">**Completamento:**  [Dopo la configurazione dell'opzione query governor cost limit](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="8bc79-116">**Follow Up:**  [After you configure the query governor cost limit option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="8bc79-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8bc79-117">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="8bc79-118">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="8bc79-118">Recommendations</span></span>  
  
-   <span data-ttu-id="8bc79-119">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bc79-119">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="8bc79-120">Per modificare il valore di Query Governor Cost Limit a livello di singola connessione, usare l'istruzione [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="8bc79-120">To change the value query governor cost limit on a per-connection basis, use the [SET QUERY_GOVERNOR_COST_LIMIT](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="8bc79-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="8bc79-121">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="8bc79-122">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="8bc79-122">Permissions</span></span>  
 <span data-ttu-id="8bc79-123">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bc79-123">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="8bc79-124">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="8bc79-124">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="8bc79-125">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="8bc79-125">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8bc79-126">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="8bc79-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="8bc79-127">Per configurare l'opzione query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="8bc79-127">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="8bc79-128">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8bc79-128">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="8bc79-129">Fare clic sulla pagina **Connessioni** .</span><span class="sxs-lookup"><span data-stu-id="8bc79-129">Click the **Connections** page.</span></span>  
  
3.  <span data-ttu-id="8bc79-130">Selezionare o deselezionare la casella di controllo **Usa Query Governor per evitare query con esecuzione prolungata** .</span><span class="sxs-lookup"><span data-stu-id="8bc79-130">Select or clear the **Use query governor to prevent long-running queries** check box.</span></span>  
  
     <span data-ttu-id="8bc79-131">Se si seleziona questa casella di controllo, nella casella sottostante immettere un valore positivo che verrà utilizzato da Query Governor per impedire l'esecuzione di qualsiasi query di durata superiore a quel valore.</span><span class="sxs-lookup"><span data-stu-id="8bc79-131">If you select this check box, in the box below, enter a positive value, which the query governor uses to disallow execution of any query with a running length exceeding that value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="8bc79-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="8bc79-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-governor-cost-limit-option"></a><span data-ttu-id="8bc79-133">Per configurare l'opzione query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="8bc79-133">To configure the query governor cost limit option</span></span>  
  
1.  <span data-ttu-id="8bc79-134">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bc79-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="8bc79-135">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="8bc79-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="8bc79-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="8bc79-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="8bc79-137">In questo esempio si illustra come utilizzare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `query governor cost limit` su `120` secondi.</span><span class="sxs-lookup"><span data-stu-id="8bc79-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query governor cost limit` option to `120` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query governor cost limit', 120 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="8bc79-138">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="8bc79-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-governor-cost-limit-option"></a><a name="FollowUp"></a> <span data-ttu-id="8bc79-139">Completamento: Dopo la configurazione dell'opzione query governor cost limit</span><span class="sxs-lookup"><span data-stu-id="8bc79-139">Follow Up: After you configure the query governor cost limit option</span></span>  
 <span data-ttu-id="8bc79-140">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="8bc79-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc79-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bc79-141">See Also</span></span>  
 <span data-ttu-id="8bc79-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8bc79-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="8bc79-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8bc79-143">[SET QUERY_GOVERNOR_COST_LIMIT &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-query-governor-cost-limit-transact-sql) </span></span>  
 <span data-ttu-id="8bc79-144">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="8bc79-144">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="8bc79-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8bc79-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
