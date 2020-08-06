---
title: Configurare l'opzione di configurazione del server priority boost | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- priority boost option
ms.assetid: 765f1e83-dd52-44fb-b0c8-1078f213607b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f42d7d2022e07dcac3039557295dc70e4500583d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626877"
---
# <a name="configure-the-priority-boost-server-configuration-option"></a><span data-ttu-id="bcbc9-102">Configurare l'opzione di configurazione del server priority boost</span><span class="sxs-lookup"><span data-stu-id="bcbc9-102">Configure the priority boost Server Configuration Option</span></span>
  <span data-ttu-id="bcbc9-103">In questo articolo viene mostrato come configurare l'opzione di configurazione del server **priority boost** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcbc9-103">This topic describes how to configure the **priority boost** configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="bcbc9-104">Usare l'opzione **priority boost** per specificare se [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve essere eseguito con una priorità di pianificazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 o Windows 2008 R2 superiore a quella di altri processi nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-104">Use the **priority boost** option to specify whether [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should run at a higher [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 2008 or Windows 2008 R2 scheduling priority than other processes on the same computer.</span></span> <span data-ttu-id="bcbc9-105">Se l'opzione viene impostata su 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguito con un valore base di priorità pari a 13 nell'utilità di pianificazione di Windows 2008 o Windows 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-105">If you set this option to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] runs at a priority base of 13 in the Windows 2008 or Windows Server 2008 R2 scheduler.</span></span> <span data-ttu-id="bcbc9-106">L'impostazione predefinita è 0, che corrisponde a un valore base di priorità pari a 7.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-106">The default is 0, which is a priority base of 7.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
 <span data-ttu-id="bcbc9-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="bcbc9-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="bcbc9-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="bcbc9-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="bcbc9-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="bcbc9-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="bcbc9-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="bcbc9-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="bcbc9-111">**Per configurare l'opzione priority boost utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="bcbc9-111">**To configure the priority boost option, using:**</span></span>  
  
     [<span data-ttu-id="bcbc9-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bcbc9-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="bcbc9-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bcbc9-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="bcbc9-114">**Completamento:**  [Dopo la configurazione dell'opzione priority boost](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="bcbc9-114">**Follow Up:**  [After you configure the priority boost option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="bcbc9-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="bcbc9-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="bcbc9-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="bcbc9-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="bcbc9-117">L'aumento eccessivo della priorità può sottrarre risorse a funzionalità di sistema e di rete essenziali, provocando problemi nell'arresto di SQL Server o nell'utilizzo di altre attività dei sistemi operativi nel server.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-117">Raising the priority too high may drain resources from essential operating system and network functions, resulting in problems shutting down SQL Server or using other operating system tasks on the server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="bcbc9-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="bcbc9-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="bcbc9-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="bcbc9-119">Permissions</span></span>  
 <span data-ttu-id="bcbc9-120">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="bcbc9-121">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="bcbc9-122">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="bcbc9-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="bcbc9-123">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bcbc9-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="bcbc9-124">Per configurare l'opzione priority boost</span><span class="sxs-lookup"><span data-stu-id="bcbc9-124">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="bcbc9-125">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="bcbc9-126">Fare clic sul nodo **Processori** .</span><span class="sxs-lookup"><span data-stu-id="bcbc9-126">Click the **Processors** node.</span></span>  
  
3.  <span data-ttu-id="bcbc9-127">In **Thread** selezionare la casella di controllo **Aumenta priorità di SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="bcbc9-127">Under **Threads**, select the **Boost SQL Server priority** check box.</span></span>  
  
4.  <span data-ttu-id="bcbc9-128">Arrestare e riavviare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcbc9-128">Stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="bcbc9-129">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="bcbc9-129">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-priority-boost-option"></a><span data-ttu-id="bcbc9-130">Per configurare l'opzione priority boost</span><span class="sxs-lookup"><span data-stu-id="bcbc9-130">To configure the priority boost option</span></span>  
  
1.  <span data-ttu-id="bcbc9-131">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bcbc9-131">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="bcbc9-132">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-132">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="bcbc9-133">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-133">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="bcbc9-134">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `priority boost` su `1`.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-134">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `priority boost` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'priority boost', 1 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 <span data-ttu-id="bcbc9-135">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-135">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-priority-boost-option"></a><a name="FollowUp"></a> <span data-ttu-id="bcbc9-136">Completamento: Dopo la configurazione dell'opzione priority boost</span><span class="sxs-lookup"><span data-stu-id="bcbc9-136">Follow Up: After you configure the priority boost option</span></span>  
 <span data-ttu-id="bcbc9-137">Per poter rendere effettiva l'impostazione, è necessario riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="bcbc9-137">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcbc9-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcbc9-138">See Also</span></span>  
 <span data-ttu-id="bcbc9-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bcbc9-139">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="bcbc9-140">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="bcbc9-140">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="bcbc9-141">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="bcbc9-141">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
