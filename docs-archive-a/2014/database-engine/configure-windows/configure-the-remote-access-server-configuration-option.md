---
title: Configurare l'opzione di configurazione del server remote access | Microsoft Docs
ms.custom: ''
ms.date: 10/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote servers [SQL Server], stored procedure execution
ms.assetid: f5de748d-1c55-4714-9661-38fe62e5095f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: eef18ec48ede59544b13545e49dc105909cfac16
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624939"
---
# <a name="configure-the-remote-access-server-configuration-option"></a><span data-ttu-id="aa1e0-102">Configurare l'opzione di configurazione del server remote access</span><span class="sxs-lookup"><span data-stu-id="aa1e0-102">Configure the remote access Server Configuration Option</span></span>
  <span data-ttu-id="aa1e0-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **remote access** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa1e0-103">This topic describes how to configure the **remote access** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="aa1e0-104">Con l'opzione **remote access** è possibile controllare l'esecuzione di stored procedure da server remoti o locali in cui sono in esecuzione istanze di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aa1e0-104">The **remote access** option controls the execution of stored procedures from local or remote servers on which instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are running.</span></span> <span data-ttu-id="aa1e0-105">Il valore predefinito dell'opzione è 1.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-105">This default value for this option is 1.</span></span> <span data-ttu-id="aa1e0-106">In questo modo si ottiene l'autorizzazione a eseguire stored procedure locali da server remoti o stored procedure remote dal server locale.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-106">This grants permission to run local stored procedures from remote servers or remote stored procedures from the local server.</span></span> <span data-ttu-id="aa1e0-107">Per impedire l'esecuzione di stored procedure locali da un server remoto o di stored procedure remote nel server locale, impostare l'opzione su 0.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-107">To prevent local stored procedures from being run from a remote server or remote stored procedures from being run on the local server, set the option to 0.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextDontUse](../../includes/ssnotedepnextdontuse-md.md)] <span data-ttu-id="aa1e0-108">Usare [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) in alternativa.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-108">Use [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql) instead.</span></span>  
  
 <span data-ttu-id="aa1e0-109">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="aa1e0-109">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aa1e0-110">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="aa1e0-110">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aa1e0-111">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="aa1e0-111">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="aa1e0-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="aa1e0-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aa1e0-113">**Per configurare l'opzione remote access utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="aa1e0-113">**To configure the remote access option, using:**</span></span>  
  
     [<span data-ttu-id="aa1e0-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa1e0-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="aa1e0-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa1e0-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="aa1e0-116">**Completamento:**  [Dopo la configurazione dell'opzione remote access](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="aa1e0-116">**Follow Up:**  [After you configure the remote access option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aa1e0-117">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="aa1e0-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="aa1e0-118">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="aa1e0-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="aa1e0-119">L'opzione **remote access** si applica solo ai server aggiunti usando [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql)e viene inclusa per ragioni di compatibilità con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-119">The **remote access** option only applies to servers that are added by using [sp_addserver](/sql/relational-databases/system-stored-procedures/sp-addserver-transact-sql), and is included for backward compatibility.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aa1e0-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="aa1e0-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aa1e0-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="aa1e0-121">Permissions</span></span>  
 <span data-ttu-id="aa1e0-122">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="aa1e0-123">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="aa1e0-124">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="aa1e0-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aa1e0-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa1e0-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="aa1e0-126">Per configurare l'opzione remote access</span><span class="sxs-lookup"><span data-stu-id="aa1e0-126">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="aa1e0-127">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="aa1e0-128">Fare clic sul nodo **Connessioni** .</span><span class="sxs-lookup"><span data-stu-id="aa1e0-128">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="aa1e0-129">In **Connessioni remote**selezionare o deselezionare la casella di controllo **Consenti connessioni remote al server** .</span><span class="sxs-lookup"><span data-stu-id="aa1e0-129">Under **Remote server connections**, select or clear the **Allow remote connections to this server** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="aa1e0-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa1e0-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-access-option"></a><span data-ttu-id="aa1e0-131">Per configurare l'opzione remote access</span><span class="sxs-lookup"><span data-stu-id="aa1e0-131">To configure the remote access option</span></span>  
  
1.  <span data-ttu-id="aa1e0-132">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa1e0-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa1e0-133">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aa1e0-134">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="aa1e0-135">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `remote access` su `0`.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote access` option to `0`.</span></span>  
  
```sql  
EXEC sp_configure 'remote access', 0 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="aa1e0-136">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-access-option"></a><a name="FollowUp"></a> <span data-ttu-id="aa1e0-137">Completamento: Dopo la configurazione dell'opzione remote access</span><span class="sxs-lookup"><span data-stu-id="aa1e0-137">Follow Up: After you configure the remote access option</span></span>  
 <span data-ttu-id="aa1e0-138">Questa impostazione ha effetto solo dopo il riavvio di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="aa1e0-138">This setting does not take effect until you restart SQL Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa1e0-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa1e0-139">See Also</span></span>  
 <span data-ttu-id="aa1e0-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="aa1e0-140">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="aa1e0-141">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="aa1e0-141">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="aa1e0-142">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="aa1e0-142">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
