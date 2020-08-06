---
title: Configurare l'opzione di configurazione del server remote proc trans | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- remote proc trans option
- distributed transactions [SQL Server], enforcing
ms.assetid: cfbc6158-ab96-44b4-87eb-ea278c1b0c6b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 54fcaafa51eef33acb1ae8d1e2f36022840b76a1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626874"
---
# <a name="configure-the-remote-proc-trans-server-configuration-option"></a><span data-ttu-id="d1742-102">Configurare l'opzione di configurazione del server remote proc trans</span><span class="sxs-lookup"><span data-stu-id="d1742-102">Configure the remote proc trans Server Configuration Option</span></span>
  <span data-ttu-id="d1742-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **remote proc trans** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1742-103">This topic describes how to configure the **remote proc trans** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d1742-104">Con l'opzione **remote proc trans** è possibile proteggere le azioni di una procedura tra server tramite una transazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] DTC (Distributed Transaction Coordinator).</span><span class="sxs-lookup"><span data-stu-id="d1742-104">The **remote proc trans** option helps protect the actions of a server-to-server procedure through a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC) transaction.</span></span>  
  
 <span data-ttu-id="d1742-105">Impostare il valore di **remote proc trans** su 1 per attivare una transazione distribuita coordinata da MS DTC tramite cui vengono protette le proprietà ACID delle transazioni, vale a dire atomicità, consistenza, isolamento e durevolezza.</span><span class="sxs-lookup"><span data-stu-id="d1742-105">Set the value of **remote proc trans** to 1 to provide an MS DTC-coordinated distributed transaction that protects the ACID (atomic, consistent, isolated, and durable) properties of transactions.</span></span> <span data-ttu-id="d1742-106">Le sessioni avviate dopo l'impostazione dell'opzione su 1 ereditano questo valore come impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d1742-106">Sessions begun after setting this option to 1 inherit the configuration setting as their default.</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepNextAvoid](../../includes/ssnotedepnextavoid-md.md)]  
  
 <span data-ttu-id="d1742-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="d1742-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d1742-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="d1742-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d1742-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d1742-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="d1742-110">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="d1742-110">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="d1742-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1742-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d1742-112">**Per configurare l'opzione remote proc trans utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="d1742-112">**To configure the remote proc trans option, using:**</span></span>  
  
     [<span data-ttu-id="d1742-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1742-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d1742-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1742-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="d1742-115">**Completamento:**  [Dopo la configurazione dell'opzione remote proc trans](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="d1742-115">**Follow Up:**  [After you configure the remote proc trans option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d1742-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d1742-116">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="d1742-117">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d1742-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="d1742-118">È necessario consentire le connessioni a server remoti prima di impostare questo valore.</span><span class="sxs-lookup"><span data-stu-id="d1742-118">Remote server connections must be allowed before this value can be set.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="d1742-119">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="d1742-119">Recommendations</span></span>  
  
-   <span data-ttu-id="d1742-120">Questa opzione garantisce la compatibilità con le versioni precedenti di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per le applicazioni che usano stored procedure remote.</span><span class="sxs-lookup"><span data-stu-id="d1742-120">This option is provided for compatibility with earlier versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for applications that use remote stored procedures.</span></span> <span data-ttu-id="d1742-121">Anziché eseguire chiamate a stored procedure remote, utilizzare query distribuite che fanno riferimento a server collegati definiti tramite [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d1742-121">Instead of issuing remote stored procedure calls, use distributed queries that reference linked servers, which are defined by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d1742-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="d1742-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d1742-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="d1742-123">Permissions</span></span>  
 <span data-ttu-id="d1742-124">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="d1742-124">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="d1742-125">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="d1742-125">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="d1742-126">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="d1742-126">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d1742-127">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d1742-127">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="d1742-128">Per configurare l'opzione remote proc trans</span><span class="sxs-lookup"><span data-stu-id="d1742-128">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="d1742-129">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d1742-129">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d1742-130">Fare clic sul nodo **Connessioni** .</span><span class="sxs-lookup"><span data-stu-id="d1742-130">Click the **Connections** node.</span></span>  
  
3.  <span data-ttu-id="d1742-131">In **Connessioni remote**selezionare la casella di controllo **Richiedi transazioni distribuite per le comunicazioni tra server** .</span><span class="sxs-lookup"><span data-stu-id="d1742-131">Under **Remote server connections**, select the **Require Distributed Transactions for server to server communication** check box.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d1742-132">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d1742-132">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-remote-proc-trans-option"></a><span data-ttu-id="d1742-133">Per configurare l'opzione remote proc trans</span><span class="sxs-lookup"><span data-stu-id="d1742-133">To configure the remote proc trans option</span></span>  
  
1.  <span data-ttu-id="d1742-134">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d1742-134">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d1742-135">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="d1742-135">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d1742-136">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="d1742-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d1742-137">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `remote proc trans` su `1`.</span><span class="sxs-lookup"><span data-stu-id="d1742-137">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `remote proc trans` option to `1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'remote proc trans', 1 ;  
GO  
RECONFIGURE ;  
GO  
  
```  
  
 <span data-ttu-id="d1742-138">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="d1742-138">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-remote-proc-trans-option"></a><a name="FollowUp"></a> <span data-ttu-id="d1742-139">Completamento: Dopo la configurazione dell'opzione remote proc trans</span><span class="sxs-lookup"><span data-stu-id="d1742-139">Follow Up: After you configure the remote proc trans option</span></span>  
 <span data-ttu-id="d1742-140">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="d1742-140">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1742-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1742-141">See Also</span></span>  
 <span data-ttu-id="d1742-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d1742-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="d1742-143">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d1742-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 [<span data-ttu-id="d1742-144">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d1742-144">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
