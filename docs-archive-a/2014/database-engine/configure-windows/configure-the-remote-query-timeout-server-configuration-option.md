---
title: Configurare l'opzione di configurazione del server remote query timeout | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- time limit for remote queries [SQL Server]
- remote query timeout option
ms.assetid: 888c8448-933b-41e3-8aa1-c206bc0cdb78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 74f82d621d7f0375a6a3ca604abba00f83fc6024
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724183"
---
# <a name="configure-the-remote-query-timeout-server-configuration-option"></a><span data-ttu-id="b71fd-102">Configurare l'opzione di configurazione del server remote query timeout</span><span class="sxs-lookup"><span data-stu-id="b71fd-102">Configure the remote query timeout Server Configuration Option</span></span>
  <span data-ttu-id="b71fd-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **remote query timeout** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b71fd-103">This topic describes how to configure the **remote query timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="b71fd-104">Con l'opzione **remote query timeout** è possibile specificare la durata, in secondi, di un'operazione remota prima del timeout di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Il valore predefinito per questa opzione è 600, che consente un'attesa di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="b71fd-104">The **remote query timeout** option specifies how long, in seconds, a remote operation can take before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] times out. The default value for this option is 600, which allows a 10-minute wait.</span></span> <span data-ttu-id="b71fd-105">Questo valore è applicabile a una connessione in uscita iniziata dal [!INCLUDE[ssDE](../../includes/ssde-md.md)] come query remota</span><span class="sxs-lookup"><span data-stu-id="b71fd-105">This value applies to an outgoing connection initiated by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] as a remote query.</span></span> <span data-ttu-id="b71fd-106">e non influisce sulle query ricevute dal [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b71fd-106">This value has no effect on queries received by the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="b71fd-107">Per disabilitare il timeout, impostare il valore su 0.</span><span class="sxs-lookup"><span data-stu-id="b71fd-107">To disable the time-out, set the value to 0.</span></span> <span data-ttu-id="b71fd-108">Una query rimarrà in attesa finché non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="b71fd-108">A query will wait until it completes.</span></span>  
  
 <span data-ttu-id="b71fd-109">Per le query eterogenee, **remote query timeout** specifica il numero di secondi di attesa (inizializzati nell'oggetto comando tramite la proprietà del set di righe DBPROP_COMMANDTIMEOUT) di set di risultati da parte del provider remoto. Trascorso il numero di secondi impostato, si verifica il timeout della query. Questo valore è utilizzato anche per l'impostazione di DBPROP_GENERALTIMEOUT, se la proprietà è supportata dal provider remoto.</span><span class="sxs-lookup"><span data-stu-id="b71fd-109">For heterogeneous queries, **remote query timeout** specifies the number of seconds (initialized in the command object using the DBPROP_COMMANDTIMEOUT rowset property) that a remote provider should wait for result sets before the query times out. This value is also used to set DBPROP_GENERALTIMEOUT if supported by the remote provider.</span></span> <span data-ttu-id="b71fd-110">L'impostazione determina il timeout delle altre operazioni dopo il numero di secondi specificato.</span><span class="sxs-lookup"><span data-stu-id="b71fd-110">This will cause any other operations to time out after the specified number of seconds.</span></span>  
  
 <span data-ttu-id="b71fd-111">Per le stored procedure remote, con **remote query timeout** è possibile specificare il numero di secondi successivi all'invio di un'istruzione `EXEC` remota, trascorsi i quali si verifica il timeout della stored procedure remota.</span><span class="sxs-lookup"><span data-stu-id="b71fd-111">For remote stored procedures, **remote query timeout** specifies the number of seconds that must elapse after sending a remote `EXEC` statement before the remote stored procedure times out.</span></span>  
  
 <span data-ttu-id="b71fd-112">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="b71fd-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b71fd-113">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="b71fd-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b71fd-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b71fd-114">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="b71fd-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b71fd-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b71fd-116">**Per configurare l'opzione remote query timeout utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="b71fd-116">**To configure the remote query timeout option, using:**</span></span>  
  
     [<span data-ttu-id="b71fd-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b71fd-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="b71fd-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b71fd-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="b71fd-119">**Completamento:**  [Dopo la configurazione dell'opzione remote query timeout](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="b71fd-119">**Follow Up:**  [After you configure the remote query timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b71fd-120">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b71fd-120">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="b71fd-121">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b71fd-121">Prerequisites</span></span>  
  
-   <span data-ttu-id="b71fd-122">È necessario consentire le connessioni a server remoti prima di impostare questo valore.</span><span class="sxs-lookup"><span data-stu-id="b71fd-122">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b71fd-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="b71fd-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b71fd-124">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="b71fd-124">Permissions</span></span>  
 <span data-ttu-id="b71fd-125">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b71fd-125">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="b71fd-126">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="b71fd-126">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="b71fd-127">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="b71fd-127">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b71fd-128">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="b71fd-128">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="b71fd-129">Per configurare l'opzione remote query timeout</span><span class="sxs-lookup"><span data-stu-id="b71fd-129">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="b71fd-130">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b71fd-130">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="b71fd-131">Fare clic sul nodo **Connessioni** .</span><span class="sxs-lookup"><span data-stu-id="b71fd-131">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="b71fd-132">Nella casella **Timeout query remote**di **Connessioni server remoto** digitare o selezionare un valore compreso tra 0 e 2.147.483.647 per impostare il numero massimo di secondi dopo i quali si verifica il timeout di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b71fd-132">Under **Remote server connections**, in the **Remote query timeout** box, type or select a value from 0 through 2,147,483,647 to set the maximum number seconds for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to wait before timing out.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="b71fd-133">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="b71fd-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-query-timeout-option"></a><span data-ttu-id="b71fd-134">Per configurare l'opzione remote query timeout</span><span class="sxs-lookup"><span data-stu-id="b71fd-134">To configure the remote query timeout option</span></span>  
  
1.  <span data-ttu-id="b71fd-135">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b71fd-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="b71fd-136">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="b71fd-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="b71fd-137">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b71fd-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="b71fd-138">Questo esempio mostra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `remote query timeout` su `0` per disabilitare il timeout.</span><span class="sxs-lookup"><span data-stu-id="b71fd-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote query timeout` option to `0` to disable the time-out.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote query timeout', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="b71fd-139">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="b71fd-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-query-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="b71fd-140">Completamento: Dopo la configurazione dell'opzione remote query timeout</span><span class="sxs-lookup"><span data-stu-id="b71fd-140">Follow Up: After you configure the remote query timeout option</span></span>  
 <span data-ttu-id="b71fd-141">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="b71fd-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b71fd-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b71fd-142">See Also</span></span>  
 <span data-ttu-id="b71fd-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b71fd-143">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="b71fd-144">[Proprietà e comportamenti dei set di righe](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span><span class="sxs-lookup"><span data-stu-id="b71fd-144">[Rowset Properties and Behaviors](../../relational-databases/native-client-ole-db-rowsets/rowset-properties-and-behaviors.md) </span></span>  
 <span data-ttu-id="b71fd-145">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b71fd-145">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="b71fd-146">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b71fd-146">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
