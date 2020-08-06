---
title: Configurare l'opzione di configurazione del server scan for startup procs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- scan for startup procs option
ms.assetid: 6bf9d252-e766-458d-9dcd-23d895f032a2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: fbf46fc7476e6e879991cfe3f649fd5617f3275e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626873"
---
# <a name="configure-the-scan-for-startup-procs-server-configuration-option"></a><span data-ttu-id="78274-102">Configurare l'opzione di configurazione del server scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="78274-102">Configure the scan for startup procs Server Configuration Option</span></span>
  <span data-ttu-id="78274-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **scan for startup procs** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78274-103">This topic describes how to configure the **scan for startup procs** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="78274-104">Con l'opzione **scan for startup procs** è possibile eseguire un'analisi per l'esecuzione automatica di stored procedure all'avvio di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78274-104">Use the **scan for startup procs** option to scan for automatic execution of stored procedures at [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] startup time.</span></span> <span data-ttu-id="78274-105">Se l'opzione è impostata su 1, in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene eseguita l'analisi e vengono eseguite tutte le stored procedure a esecuzione automatica definite nel server.</span><span class="sxs-lookup"><span data-stu-id="78274-105">If this option is set to 1, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] scans for and runs all automatically run stored procedures that are defined on the server.</span></span> <span data-ttu-id="78274-106">Il valore predefinito di **scan for startup procs** è 0 (nessuna analisi).</span><span class="sxs-lookup"><span data-stu-id="78274-106">The default value for **scan for startup procs** is 0 (do not scan).</span></span>  
  
 <span data-ttu-id="78274-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="78274-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="78274-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="78274-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="78274-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="78274-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="78274-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="78274-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="78274-111">**Per configurare l'opzione scan for startup procs utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="78274-111">**To configure the scan for startup procs option, using:**</span></span>  
  
     [<span data-ttu-id="78274-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78274-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="78274-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78274-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="78274-114">**Completamento:**  [Dopo la configurazione dell'opzione scan for startup procs](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="78274-114">**Follow Up:**  [After you configure the scan for startup procs option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="78274-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="78274-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="78274-116">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="78274-116">Recommendations</span></span>  
  
-   <span data-ttu-id="78274-117">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="78274-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
-   <span data-ttu-id="78274-118">È possibile impostare il valore dell'opzione usando **sp_configure**. L'opzione viene tuttavia impostata automaticamente se si usa **sp_procoption**, che consente di contrassegnare o meno impostare le stored procedure eseguite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="78274-118">The value for this option can be set by using **sp_configure**; however, it will be set automatically if you use **sp_procoption**, which is used to mark or unmark automatically run stored procedures.</span></span> <span data-ttu-id="78274-119">Se si usa **sp_procoption** per contrassegnare la prima stored procedure come procedura automatica, l'opzione viene automaticamente impostata su 1.</span><span class="sxs-lookup"><span data-stu-id="78274-119">When **sp_procoption** is used to mark the first stored procedure as an autoproc, this option is set automatically to a value of 1.</span></span> <span data-ttu-id="78274-120">Se si usa **sp_procoption** per annullare il contrassegno dell'ultima stored procedure come procedura automatica, l'opzione viene automaticamente impostata su 0.</span><span class="sxs-lookup"><span data-stu-id="78274-120">When **sp_procoption** is used to unmark the last stored procedure as an autoproc, this option is automatically set to a value of 0.</span></span> <span data-ttu-id="78274-121">Se si usa **sp_procoption** per contrassegnare e annullare il contrassegno di procedure automatiche e se si vuole annullare sempre questo contrassegno prima di eliminarle, non è necessario impostare manualmente questa opzione.</span><span class="sxs-lookup"><span data-stu-id="78274-121">If you use **sp_procoption** to mark and unmark autoprocs, and if you always unmark autoprocs before dropping them, there is no need to set this option manually.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="78274-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="78274-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="78274-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="78274-123">Permissions</span></span>  
 <span data-ttu-id="78274-124">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="78274-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="78274-125">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="78274-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="78274-126">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="78274-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="78274-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="78274-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="78274-128">Per configurare l'opzione scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="78274-128">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="78274-129">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="78274-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="78274-130">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="78274-130">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="78274-131">In **Varie**impostare il valore dell'opzione **Analisi per procedure di avvio** su True o False dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="78274-131">Under **Miscellaneous**, change the **Scan for Startup Procs** option to True or False by selecting the value you want from the drop-down list box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="78274-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="78274-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-scan-for-startup-procs-option"></a><span data-ttu-id="78274-133">Per configurare l'opzione scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="78274-133">To configure the scan for startup procs option</span></span>  
  
1.  <span data-ttu-id="78274-134">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="78274-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="78274-135">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="78274-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="78274-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="78274-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="78274-137">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `scan for startup procs` su `1`.</span><span class="sxs-lookup"><span data-stu-id="78274-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `scan for startup procs` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;  
GO  
RECONFIGURE  
GO  
EXEC sp_configure 'scan for startup procs', 1 ;  
GO  
RECONFIGURE  
GO  
  
```  
  
##  <a name="follow-up-after-you-configure-the-scan-for-startup-procs-option"></a><a name="FollowUp"></a> <span data-ttu-id="78274-138">Completamento: Dopo la configurazione dell'opzione scan for startup procs</span><span class="sxs-lookup"><span data-stu-id="78274-138">Follow Up: After you configure the scan for startup procs option</span></span>  
 <span data-ttu-id="78274-139">Per poter rendere effettiva l'impostazione, è necessario riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="78274-139">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78274-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78274-140">See Also</span></span>  
 <span data-ttu-id="78274-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78274-141">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="78274-142">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="78274-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="78274-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="78274-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="78274-144">sp_procoption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="78274-144">sp_procoption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-procoption-transact-sql)  
  
  
