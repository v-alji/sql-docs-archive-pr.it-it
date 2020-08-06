---
title: Configurare l'opzione di configurazione del server remote login timeout | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote login timeout option
ms.assetid: 077adebe-0e3f-42a5-a75e-5e6d04847e2b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 58b3405f9b0e51bd43edcaa31e84c8ebbcc48547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624936"
---
# <a name="configure-the-remote-login-timeout-server-configuration-option"></a><span data-ttu-id="7a217-102">Configurare l'opzione di configurazione del server remote login timeout</span><span class="sxs-lookup"><span data-stu-id="7a217-102">Configure the remote login timeout Server Configuration Option</span></span>
  <span data-ttu-id="7a217-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **remote login timeout** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a217-103">This topic describes how to configure the **remote login timeout** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7a217-104">Con l'opzione **remote login timeout** è possibile specificare il numero di secondi che devono trascorrere prima di considerare non riuscito il tentativo di accesso remoto a un server.</span><span class="sxs-lookup"><span data-stu-id="7a217-104">The **remote login timeout** option specifies the number of seconds to wait before returning from a failed attempt to log in to a remote server.</span></span> <span data-ttu-id="7a217-105">Se, ad esempio, si tenta l'accesso a un server remoto non funzionante, con **remote login timeout** viene definito un limite oltre il quale i tentativi di accesso verranno sospesi evitando quindi il protrarsi di tentativi inutili per un periodo di tempo indefinito.</span><span class="sxs-lookup"><span data-stu-id="7a217-105">For example, if you are trying to log in to a remote server and that server is down, **remote login timeout** helps make sure that you do not have to wait indefinitely before your computer stops trying to log in.</span></span> <span data-ttu-id="7a217-106">Il valore predefinito per questa opzione è 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="7a217-106">The default value for this option is 10 seconds.</span></span> <span data-ttu-id="7a217-107">Il valore 0 determina un tempo di attesa infinito.</span><span class="sxs-lookup"><span data-stu-id="7a217-107">A value of 0 allows for an infinite wait.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7a217-108">Il valore predefinito per questa opzione è 20 secondi in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a217-108">The default value for this option is 20 seconds in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="7a217-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="7a217-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7a217-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="7a217-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7a217-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="7a217-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="7a217-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7a217-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7a217-113">**Per configurare l'opzione remote login timeout tramite:**</span><span class="sxs-lookup"><span data-stu-id="7a217-113">**To configure the remote login timeout option, using:**</span></span>  
  
     [<span data-ttu-id="7a217-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a217-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7a217-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a217-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="7a217-116">**Completamento:**  [Dopo la configurazione dell'opzione remote login timeout](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="7a217-116">**Follow Up:**  [After you configure the remote login timeout option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7a217-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="7a217-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="7a217-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="7a217-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="7a217-119">L'opzione **remote login timeout** influisce sulle connessioni ai provider OLE DB stabilite per l'esecuzione di query eterogenee.</span><span class="sxs-lookup"><span data-stu-id="7a217-119">The **remote login timeout** option affects connections to OLE DB providers made for heterogeneous queries.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7a217-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="7a217-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7a217-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="7a217-121">Permissions</span></span>  
 <span data-ttu-id="7a217-122">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7a217-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="7a217-123">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="7a217-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="7a217-124">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="7a217-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7a217-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7a217-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="7a217-126">Per configurare l'opzione remote login timeout</span><span class="sxs-lookup"><span data-stu-id="7a217-126">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="7a217-127">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7a217-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="7a217-128">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="7a217-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="7a217-129">In **Rete**selezionare un valore per la casella **Remote Login Timeout** .</span><span class="sxs-lookup"><span data-stu-id="7a217-129">Under **Network**, select a value for the **Remote Login Timeout** box.</span></span>  
  
     <span data-ttu-id="7a217-130">Utilizzare l'opzione **remote login timeout** per specificare il numero di secondi che devono trascorrere prima di considerare non riuscito il tentativo di accesso remoto.</span><span class="sxs-lookup"><span data-stu-id="7a217-130">Use the **remote login timeout** option to specify the number of seconds to wait before returning from a failed remote login attempt.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7a217-131">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7a217-131">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-login-timeout-option"></a><span data-ttu-id="7a217-132">Per configurare l'opzione remote login timeout</span><span class="sxs-lookup"><span data-stu-id="7a217-132">To configure the remote login timeout option</span></span>  
  
1.  <span data-ttu-id="7a217-133">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a217-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="7a217-134">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="7a217-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="7a217-135">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="7a217-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="7a217-136">In questo esempio si illustra come utilizzare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `remote login timeout` su `35` secondi.</span><span class="sxs-lookup"><span data-stu-id="7a217-136">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote login timeout` option to `35` seconds.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote login timeout', 35 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="7a217-137">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="7a217-137">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-login-timeout-option"></a><a name="FollowUp"></a> <span data-ttu-id="7a217-138">Completamento: Dopo la configurazione dell'opzione remote login timeout</span><span class="sxs-lookup"><span data-stu-id="7a217-138">Follow Up: After you configure the remote login timeout option</span></span>  
 <span data-ttu-id="7a217-139">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="7a217-139">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a217-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a217-140">See Also</span></span>  
 <span data-ttu-id="7a217-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7a217-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="7a217-142">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7a217-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="7a217-143">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7a217-143">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
