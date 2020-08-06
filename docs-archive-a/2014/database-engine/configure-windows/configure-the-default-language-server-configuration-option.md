---
title: Configurare l'opzione di configurazione del server default language | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- default language option
ms.assetid: c08c26d8-5a62-487e-a4ee-4c529e4f9287
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b0e62fef112dad2c6c307946bc720adf1f14d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724932"
---
# <a name="configure-the-default-language-server-configuration-option"></a><span data-ttu-id="cade5-102">Configurare l'opzione di configurazione del server default language</span><span class="sxs-lookup"><span data-stu-id="cade5-102">Configure the default language Server Configuration Option</span></span>
  <span data-ttu-id="cade5-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **default language** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cade5-103">This topic describes how to configure the **default language** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="cade5-104">Con l'opzione **default language** è possibile specificare la lingua predefinita per tutti i nuovi account di accesso creati.</span><span class="sxs-lookup"><span data-stu-id="cade5-104">The **default language** option specifies the default language for all newly created logins.</span></span> <span data-ttu-id="cade5-105">Per impostare la lingua predefinita, specificare il valore **langid** della lingua desiderata.</span><span class="sxs-lookup"><span data-stu-id="cade5-105">To set default language, specify the **langid** value of the language you want.</span></span> <span data-ttu-id="cade5-106">È possibile ottenere il valore **langid** eseguendo una query sulla vista di compatibilità **sys.syslanguages** .</span><span class="sxs-lookup"><span data-stu-id="cade5-106">The **langid** value can be obtained by querying the **sys.syslanguages** compatibility view.</span></span>  
  
 <span data-ttu-id="cade5-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="cade5-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cade5-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="cade5-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="cade5-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="cade5-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="cade5-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cade5-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="cade5-111">**Per configurare l'opzione default language tramite:**</span><span class="sxs-lookup"><span data-stu-id="cade5-111">**To configure the default language option, using:**</span></span>  
  
     [<span data-ttu-id="cade5-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cade5-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="cade5-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cade5-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="cade5-114">**Completamento:**  [Dopo la configurazione dell'opzione default language](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="cade5-114">**Follow Up:**  [After you configure the default language option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="cade5-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="cade5-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="cade5-116">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="cade5-116">Recommendations</span></span>  
  
-   <span data-ttu-id="cade5-117">È possibile sostituire la lingua predefinita per un account di accesso mediante CREATE LOGIN o ALTER LOGIN.</span><span class="sxs-lookup"><span data-stu-id="cade5-117">The default language for a login can be overridden by using CREATE LOGIN or ALTER LOGIN.</span></span> <span data-ttu-id="cade5-118">La lingua predefinita di una sessione corrisponde alla lingua dell'account di accesso della sessione, a meno che venga modificata per ogni singola sessione mediante le API ODBC o OLE DB.</span><span class="sxs-lookup"><span data-stu-id="cade5-118">The default language for a session is the language for that session's login, unless overridden on a per-session basis by using the Open Database Connectivity (ODBC) or OLE DB APIs.</span></span> <span data-ttu-id="cade5-119">Si noti che è possibile impostare l'opzione **default language** solo su un ID di lingua definito in [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) , compreso tra 0 e 32.</span><span class="sxs-lookup"><span data-stu-id="cade5-119">Note that you can only set the **default language** option to a language ID defined in [sys.syslanguages](/sql/relational-databases/system-compatibility-views/sys-syslanguages-transact-sql) (0-32).</span></span> <span data-ttu-id="cade5-120">Se si utilizzano database indipendenti, è possibile impostare una lingua predefinita per un database mediante CREATE DATABASE o ALTER DATABASE e per gli utenti di database indipendenti mediante CREATE USER o ALTER USER.</span><span class="sxs-lookup"><span data-stu-id="cade5-120">When you are using contained databases, a default language can be set for a database by using CREATE DATABASE or ALTER DATABASE, and for contained database users by using CREATE USER or ALTER USER.</span></span> <span data-ttu-id="cade5-121">Per l'impostazione di lingue predefinite in un database indipendente vengono accettati il valore **langid** , il nome della lingua o l'alias della lingua come indicato in **sys.syslanguages**.</span><span class="sxs-lookup"><span data-stu-id="cade5-121">Setting default languages in a contained database accepts **langid** value, the language name, or a language alias as listed in **sys.syslanguages**.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="cade5-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cade5-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cade5-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="cade5-123">Permissions</span></span>  
 <span data-ttu-id="cade5-124">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="cade5-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="cade5-125">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="cade5-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="cade5-126">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="cade5-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cade5-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cade5-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="cade5-128">Per configurare l'opzione default language</span><span class="sxs-lookup"><span data-stu-id="cade5-128">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="cade5-129">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="cade5-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="cade5-130">Fare clic sul nodo **Impostazioni varie** .</span><span class="sxs-lookup"><span data-stu-id="cade5-130">Click the **Misc server settings** node.</span></span>  
  
3.  <span data-ttu-id="cade5-131">Nella casella **Lingua predefinita per l'utente** scegliere la lingua in cui verranno visualizzati i messaggi di sistema in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cade5-131">In the **Default language for users** box, choose the language in which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should display system messages.</span></span>  
  
     <span data-ttu-id="cade5-132">La lingua predefinita è l'italiano.</span><span class="sxs-lookup"><span data-stu-id="cade5-132">The default language is English.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="cade5-133">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="cade5-133">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-default-language-option"></a><span data-ttu-id="cade5-134">Per configurare l'opzione default language</span><span class="sxs-lookup"><span data-stu-id="cade5-134">To configure the default language option</span></span>  
  
1.  <span data-ttu-id="cade5-135">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cade5-135">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="cade5-136">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="cade5-136">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="cade5-137">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="cade5-137">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="cade5-138">In questo esempio si illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per configurare l'opzione `default language` sulla lingua francese (`2`).</span><span class="sxs-lookup"><span data-stu-id="cade5-138">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `default language` option to French (`2`).</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'default language', 2 ;  
GO  
RECONFIGURE ;  
GO  
```  
  
 <span data-ttu-id="cade5-139">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="cade5-139">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-default-language-option"></a><a name="FollowUp"></a> <span data-ttu-id="cade5-140">Completamento: Dopo la configurazione dell'opzione default language</span><span class="sxs-lookup"><span data-stu-id="cade5-140">Follow Up: After you configure the default language option</span></span>  
 <span data-ttu-id="cade5-141">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="cade5-141">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cade5-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cade5-142">See Also</span></span>  
 <span data-ttu-id="cade5-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cade5-143">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 <span data-ttu-id="cade5-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cade5-144">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 <span data-ttu-id="cade5-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cade5-145">[CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql) </span></span>  
 <span data-ttu-id="cade5-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cade5-146">[ALTER USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-user-transact-sql) </span></span>  
 <span data-ttu-id="cade5-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cade5-147">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="cade5-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cade5-148">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="cade5-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="cade5-149">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="cade5-150">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="cade5-150">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="cade5-151">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cade5-151">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
