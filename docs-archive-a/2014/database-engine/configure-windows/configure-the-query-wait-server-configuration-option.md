---
title: Configurare l'opzione di configurazione del server query wait | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], timing out
- time [SQL Server], query wait time
- query wait option [SQL Server]
ms.assetid: 0fc4aa01-65a3-4a33-9ef4-caca41add238
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 638afff2aa05a9fc4e61bc71e8610dba1dda8cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630040"
---
# <a name="configure-the-query-wait-server-configuration-option"></a><span data-ttu-id="eea12-102">Configurare l'opzione di configurazione del server query wait</span><span class="sxs-lookup"><span data-stu-id="eea12-102">Configure the query wait Server Configuration Option</span></span>
  <span data-ttu-id="eea12-103">In questo argomento viene descritto come configurare l'opzione di configurazione del server **query wait** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eea12-103">This topic describes how to configure the **query wait** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="eea12-104">Le query che impegnano una notevole quantità di memoria, ad esempio quelle che eseguono operazioni di ordinamento e di hashing, vengono inserite in una coda se la memoria disponibile è insufficiente per la loro esecuzione.</span><span class="sxs-lookup"><span data-stu-id="eea12-104">Memory-intensive queries (such as those involving sorting and hashing) are queued when there is not enough memory available to run the query.</span></span> <span data-ttu-id="eea12-105">L'opzione **query wait** consente di specificare il tempo in secondi (da 0 a 2147483647) per l'attesa di risorse da parte della query, trascorso il quale si verifica il timeout della query. Il valore predefinito dell'opzione è -1.</span><span class="sxs-lookup"><span data-stu-id="eea12-105">The **query wait** option specifies the time, in seconds (from 0 through 2147483647), that a query waits for resources before it times out. The default value for this option is -1.</span></span> <span data-ttu-id="eea12-106">Vuole dire che il timeout viene calcolato come 25 volte il costo stimato della query.</span><span class="sxs-lookup"><span data-stu-id="eea12-106">This means the time-out is calculated as 25 times the estimated query cost.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eea12-107">Durante l'attesa di memoria disponibile, è possibile che una transazione contenente la query in attesa mantenga attivi i blocchi acquisiti.</span><span class="sxs-lookup"><span data-stu-id="eea12-107">A transaction that contains the waiting query might hold locks while the query waits for memory.</span></span> <span data-ttu-id="eea12-108">In rari casi è possibile che si verifichi un deadlock non rilevabile.</span><span class="sxs-lookup"><span data-stu-id="eea12-108">In rare situations, it is possible for an undetectable deadlock to occur.</span></span> <span data-ttu-id="eea12-109">La riduzione del periodo di tempo rappresentato dall'opzione query wait consente di ridurre la probabilità che si verifichino deadlock di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="eea12-109">Decreasing the query wait time lowers the probability of such deadlocks.</span></span> <span data-ttu-id="eea12-110">Una query rimasta in attesa verrà infine terminata e i blocchi delle transazioni verranno rilasciati.</span><span class="sxs-lookup"><span data-stu-id="eea12-110">Eventually, a waiting query will be terminated and the transaction locks released.</span></span> <span data-ttu-id="eea12-111">L'aumento del tempo massimo di attesa può tuttavia determinare un aumento del periodo di tempo prima che la query venga terminata.</span><span class="sxs-lookup"><span data-stu-id="eea12-111">However, increasing the maximum wait time may increase the amount of time for the query to be terminated.</span></span> <span data-ttu-id="eea12-112">È pertanto sconsigliabile apportare modifiche a questa opzione.</span><span class="sxs-lookup"><span data-stu-id="eea12-112">Changes to this option are not recommended.</span></span>  
  
 <span data-ttu-id="eea12-113">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="eea12-113">**In This Topic**</span></span>  
  
-   <span data-ttu-id="eea12-114">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="eea12-114">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="eea12-115">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="eea12-115">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="eea12-116">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="eea12-116">Security</span></span>](#Security)  
  
-   <span data-ttu-id="eea12-117">**Per configurare l'opzione query wait utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="eea12-117">**To configure the query wait option, using:**</span></span>  
  
     [<span data-ttu-id="eea12-118">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eea12-118">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="eea12-119">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eea12-119">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="eea12-120">**Completamento:**  [Dopo la configurazione dell'opzione query wait](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="eea12-120">**Follow Up:**  [After you configure the query wait option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="eea12-121">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="eea12-121">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="eea12-122">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="eea12-122">Recommendations</span></span>  
  
-   <span data-ttu-id="eea12-123">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eea12-123">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="eea12-124">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="eea12-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="eea12-125">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="eea12-125">Permissions</span></span>  
 <span data-ttu-id="eea12-126">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="eea12-126">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="eea12-127">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="eea12-127">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="eea12-128">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="eea12-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="eea12-129">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="eea12-129">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="eea12-130">Per configurare l'opzione query wait</span><span class="sxs-lookup"><span data-stu-id="eea12-130">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="eea12-131">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="eea12-131">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="eea12-132">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="eea12-132">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="eea12-133">In **Parallelismo**immettere il valore desiderato per l'opzione **query wait** .</span><span class="sxs-lookup"><span data-stu-id="eea12-133">Under **Parallelism**, type the desired value for the **query wait** option.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="eea12-134">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="eea12-134">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-query-wait-option"></a><span data-ttu-id="eea12-135">Per configurare l'opzione query wait</span><span class="sxs-lookup"><span data-stu-id="eea12-135">To configure the query wait option</span></span>  
  
1.  <span data-ttu-id="eea12-136">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eea12-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="eea12-137">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="eea12-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="eea12-138">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="eea12-138">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="eea12-139">In questo esempio si illustra come utilizzare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `query wait` su `7500` secondi.</span><span class="sxs-lookup"><span data-stu-id="eea12-139">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `query wait` option to `7500` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query wait', 7500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="eea12-140">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="eea12-140">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-query-wait-option"></a><a name="FollowUp"></a> <span data-ttu-id="eea12-141">Completamento: Dopo la configurazione dell'opzione query wait</span><span class="sxs-lookup"><span data-stu-id="eea12-141">Follow Up: After you configure the query wait option</span></span>  
 <span data-ttu-id="eea12-142">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="eea12-142">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eea12-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eea12-143">See Also</span></span>  
 <span data-ttu-id="eea12-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eea12-144">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="eea12-145">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eea12-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="eea12-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eea12-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
