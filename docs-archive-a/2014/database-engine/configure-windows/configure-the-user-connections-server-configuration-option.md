---
title: Configurare l'opzione di configurazione del server user connections | Microsoft Docs
ms.custom: ''
ms.date: 12/02/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- simultaneous connections [SQL Server]
- user connections option [SQL Server]
- users [SQL Server], simultaneous connections
- maximum number of simultaneous user connections
- connections [SQL Server], simultaneous
ms.assetid: 53beee6e-59fe-4276-9abb-8f1cec2a3508
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 68fbb4a17de131c128b5b1bb7cfb35a33b9d0037
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624345"
---
# <a name="configure-the-user-connections-server-configuration-option"></a><span data-ttu-id="17888-102">Configurare l'opzione di configurazione del server user connections</span><span class="sxs-lookup"><span data-stu-id="17888-102">Configure the user connections Server Configuration Option</span></span>
  <span data-ttu-id="17888-103">In questo argomento si illustra come impostare l'opzione di configurazione del server **user connections** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17888-103">This topic describes how to set the **user connections** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="17888-104">Con l'opzione **user connections** è possibile specificare il numero massimo di connessioni utente simultanee permesse in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17888-104">The **user connections** option specifies the maximum number of simultaneous user connections that are allowed on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="17888-105">Il numero effettivo di connessioni utente consentite dipende inoltre dalla versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilizzata nonché dai limiti delle applicazioni e dei componenti hardware.</span><span class="sxs-lookup"><span data-stu-id="17888-105">The actual number of user connections allowed also depends on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you are using, and also the limits of your application or applications and hardware.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="17888-106">è consentito un massimo di 32.767 connessioni utente.</span><span class="sxs-lookup"><span data-stu-id="17888-106">allows a maximum of 32,767 user connections.</span></span> <span data-ttu-id="17888-107">Poiché **user connections** è un'opzione dinamica a configurazione automatica, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] regola automaticamente il numero massimo di connessioni utente come necessario, fino al valore massimo consentito.</span><span class="sxs-lookup"><span data-stu-id="17888-107">Because **user connections** is a dynamic (self-configuring) option, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] adjusts the maximum number of user connections automatically as needed, up to the maximum value allowable.</span></span> <span data-ttu-id="17888-108">Se, ad esempio, sono connessi solo 10 utenti, vengono allocati 10 oggetti connessione utente.</span><span class="sxs-lookup"><span data-stu-id="17888-108">For example, if only 10 users are logged in, 10 user connection objects are allocated.</span></span> <span data-ttu-id="17888-109">Nella maggior parte dei casi, non è necessario modificare il valore dell'opzione.</span><span class="sxs-lookup"><span data-stu-id="17888-109">In most cases, you do not have to change the value for this option.</span></span> <span data-ttu-id="17888-110">Il valore predefinito è 0, che indica che è consentito il numero massimo di connessioni utente (32.767).</span><span class="sxs-lookup"><span data-stu-id="17888-110">The default is 0, which means that the maximum (32,767) user connections are allowed.</span></span>  
  
 <span data-ttu-id="17888-111">Per determinare il numero massimo di connessioni utente consentito dal sistema, è possibile eseguire [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) oppure eseguire una query sulla vista del catalogo [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="17888-111">To determine the maximum number of user connections that your system allows, you can execute [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) or query the [sys.configuration](/sql/relational-databases/system-catalog-views/sys-configurations-transact-sql) catalog view.</span></span>  
  
 <span data-ttu-id="17888-112">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="17888-112">**In This Topic**</span></span>  
  
-   <span data-ttu-id="17888-113">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="17888-113">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="17888-114">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="17888-114">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="17888-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="17888-115">Security</span></span>](#Security)  
  
-   <span data-ttu-id="17888-116">**Per configurare l'opzione user connections utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="17888-116">**To configure the user connections option, using:**</span></span>  
  
     [<span data-ttu-id="17888-117">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17888-117">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="17888-118">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17888-118">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="17888-119">**Completamento:**  [Dopo la configurazione dell'opzione user connections](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="17888-119">**Follow Up:**  [After you configure the user connections option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="17888-120">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="17888-120">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="17888-121">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="17888-121">Recommendations</span></span>  
  
-   <span data-ttu-id="17888-122">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="17888-122">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="17888-123">Tramite l'opzione **user connections** è possibile evitare il sovraccarico del server con un numero eccessivo di connessioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="17888-123">Using the **user connections** option helps avoid overloading the server with too many concurrent connections.</span></span> <span data-ttu-id="17888-124">In base ai requisiti di sistema e ai requisiti degli utenti è possibile stimare il numero di connessioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="17888-124">You can estimate the number of connections based on system and user requirements.</span></span> <span data-ttu-id="17888-125">In un sistema con molti utenti, ad esempio, non tutti gli utenti richiedono una connessione univoca,</span><span class="sxs-lookup"><span data-stu-id="17888-125">For example, on a system with many users, each user would not usually require a unique connection.</span></span> <span data-ttu-id="17888-126">ma le connessioni possono essere condivise tra gli utenti.</span><span class="sxs-lookup"><span data-stu-id="17888-126">Connections can be shared among users.</span></span> <span data-ttu-id="17888-127">Per gli utenti che eseguono applicazioni OLE DB è necessaria una connessione per ogni oggetto connessione aperto, per gli utenti che eseguono applicazioni ODBC è necessaria una connessione per ogni handle di connessione attivo nell'applicazione, mentre per gli utenti che eseguono applicazioni DB-Library è necessaria una connessione per ogni processo avviato che chiama la funzione **dbopen** di DB-Library.</span><span class="sxs-lookup"><span data-stu-id="17888-127">Users running OLE DB applications need a connection for each open connection object, users running Open Database Connectivity (ODBC) applications need a connection for each active connection handle in the application, and users running DB-Library applications need one connection for each process started that calls the DB-Library **dbopen** function.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="17888-128">Se è necessario utilizzare questa opzione, evitare di impostare un valore troppo elevato. Ogni connessione comporta indipendentemente dal fatto che venga utilizzata o meno.</span><span class="sxs-lookup"><span data-stu-id="17888-128">If you must use this option, do not set the value too high, because each connection has overhead regardless of whether the connection is being used.</span></span> <span data-ttu-id="17888-129">Se si supera il numero massimo consentito di connessioni utente, viene visualizzato un messaggio di errore e non saranno consentite ulteriori connessioni fino a quando una di quelle correnti non tornerà disponibile.</span><span class="sxs-lookup"><span data-stu-id="17888-129">If you exceed the maximum number of user connections, you receive an error message and are not able to connect until another connection becomes available.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="17888-130">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="17888-130">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="17888-131">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="17888-131">Permissions</span></span>  
 <span data-ttu-id="17888-132">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="17888-132">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="17888-133">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="17888-133">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="17888-134">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="17888-134">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="17888-135">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="17888-135">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="17888-136">Per configurare l'opzione user connections</span><span class="sxs-lookup"><span data-stu-id="17888-136">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="17888-137">In Esplora oggetti fare clic con il pulsante destro del mouse su un server, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="17888-137">In Object Explorer, right-click a server and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="17888-138">Fare clic sul nodo **Connessioni** .</span><span class="sxs-lookup"><span data-stu-id="17888-138">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="17888-139">Nella casella **Numero massimo di connessioni simultanee**in **Connessioni** digitare o selezionare un valore da 0 a 32767 per impostare il numero massimo di utenti a cui è consentito connettersi simultaneamente all'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17888-139">Under **Connections**, in the **Max number of concurrent connections** box, type or select a value from 0 through 32767 to set the maximum number of users that are allowed to connect simultaneously to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="17888-140">Riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17888-140">Restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="17888-141">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="17888-141">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-user-connections-option"></a><span data-ttu-id="17888-142">Per configurare l'opzione user connections</span><span class="sxs-lookup"><span data-stu-id="17888-142">To configure the user connections option</span></span>  
  
1.  <span data-ttu-id="17888-143">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17888-143">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="17888-144">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="17888-144">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="17888-145">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="17888-145">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="17888-146">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per configurare il valore dell'opzione `user connections` per utenti `325` .</span><span class="sxs-lookup"><span data-stu-id="17888-146">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the value of the `user connections` option to `325` users.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'user connections', 325 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="17888-147">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="17888-147">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-user-connections-option"></a><a name="FollowUp"></a> <span data-ttu-id="17888-148">Completamento: Dopo la configurazione dell'opzione user connections</span><span class="sxs-lookup"><span data-stu-id="17888-148">Follow Up: After you configure the user connections option</span></span>  
 <span data-ttu-id="17888-149">Per poter rendere effettiva l'impostazione, è necessario riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="17888-149">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17888-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17888-150">See Also</span></span>  
 <span data-ttu-id="17888-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="17888-151">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="17888-152">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="17888-152">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="17888-153">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="17888-153">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
