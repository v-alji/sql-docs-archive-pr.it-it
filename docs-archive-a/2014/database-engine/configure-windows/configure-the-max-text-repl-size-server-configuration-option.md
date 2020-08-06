---
title: Configurare l'opzione di configurazione del server max text repl size | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- max text repl size option
ms.assetid: 3056cf64-621d-4996-9162-3913f6bc6d5b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2af0cf426583ee328f0a484de1c3539836c0d8af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630048"
---
# <a name="configure-the-max-text-repl-size-server-configuration-option"></a><span data-ttu-id="a4f31-102">Configurare l'opzione di configurazione del server max text repl size</span><span class="sxs-lookup"><span data-stu-id="a4f31-102">Configure the max text repl size Server Configuration Option</span></span>
  <span data-ttu-id="a4f31-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **max text repl size** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4f31-103">This topic describes how to configure the **max text repl size** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a4f31-104">L'opzione **max text repl size** specifica la dimensione massima (in byte) dei `text` `ntext` dati,, `varchar(max)` , `nvarchar(max)` , `varbinary(max)` , `xml` e `image` che è possibile aggiungere a una colonna replicata o a una colonna acquisita in un'unica istruzione INSERT, Update, WRITETEXT o UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="a4f31-104">The **max text repl size** option specifies the maximum size (in bytes) of `text`, `ntext`, `varchar(max)`, `nvarchar(max)`, `varbinary(max)`, `xml`, and `image` data that can be added to a replicated column or captured column in a single INSERT, UPDATE, WRITETEXT, or UPDATETEXT statement.</span></span> <span data-ttu-id="a4f31-105">Il valore predefinito è 65536 byte.</span><span class="sxs-lookup"><span data-stu-id="a4f31-105">The default value is 65536 bytes.</span></span> <span data-ttu-id="a4f31-106">Il valore -1 indica che non esiste alcun limite di dimensioni, tranne il limite imposto dal tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a4f31-106">A value of -1 indicates that there is no size limit, other than the limit imposed by the data type.</span></span>  
  
 <span data-ttu-id="a4f31-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a4f31-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a4f31-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a4f31-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a4f31-109">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a4f31-109">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="a4f31-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a4f31-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a4f31-111">**Per configurare l'opzione max text repl size tramite:**</span><span class="sxs-lookup"><span data-stu-id="a4f31-111">**To configure the max text repl size option, using:**</span></span>  
  
     [<span data-ttu-id="a4f31-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4f31-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a4f31-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a4f31-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="a4f31-114">**Completamento:**  [Dopo la configurazione dell'opzione max text repl size](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="a4f31-114">**Follow Up:**  [After you configure the max text repl size option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a4f31-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a4f31-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="a4f31-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="a4f31-116">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="a4f31-117">Questa opzione si applica alla replica transazionale e a Change Data Capture.</span><span class="sxs-lookup"><span data-stu-id="a4f31-117">This option applies to transactional replication and Change Data Capture.</span></span> <span data-ttu-id="a4f31-118">Se un server è configurato sia per la replica transazionale che per Change Data Capture, il valore specificato si applica a entrambe le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a4f31-118">When a server is configured for both transactional replication and Change Data Capture, the specified value applies to both features.</span></span> <span data-ttu-id="a4f31-119">Questa opzione viene ignorata dalla replica snapshot e da quella di tipo merge.</span><span class="sxs-lookup"><span data-stu-id="a4f31-119">This option is ignored by snapshot replication and merge replication.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a4f31-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a4f31-120">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a4f31-121">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a4f31-121">Permissions</span></span>  
 <span data-ttu-id="a4f31-122">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a4f31-122">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="a4f31-123">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="a4f31-123">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="a4f31-124">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="a4f31-124">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a4f31-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a4f31-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="a4f31-126">Per configurare l'opzione max text repl size</span><span class="sxs-lookup"><span data-stu-id="a4f31-126">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="a4f31-127">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="a4f31-127">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="a4f31-128">Fare clic sul nodo **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="a4f31-128">Click the **Advanced** node.</span></span>  
  
3.  <span data-ttu-id="a4f31-129">Nel gruppo **Varie**impostare il valore desiderato per l'opzione **Dimensioni massime replica testo** .</span><span class="sxs-lookup"><span data-stu-id="a4f31-129">Under **Miscellaneous**, change the **Max Text Replication Size** option to the desired value.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a4f31-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a4f31-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-max-text-repl-size-option"></a><span data-ttu-id="a4f31-131">Per configurare l'opzione max text repl size</span><span class="sxs-lookup"><span data-stu-id="a4f31-131">To configure the max text repl size option</span></span>  
  
1.  <span data-ttu-id="a4f31-132">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4f31-132">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a4f31-133">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a4f31-133">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a4f31-134">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a4f31-134">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="a4f31-135">In questo esempio si illustra come utilizzare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per configurare l'opzione `max text repl size` su `-1`.</span><span class="sxs-lookup"><span data-stu-id="a4f31-135">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to configure the `max text repl size` option to `-1`.</span></span>  
  
```sql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1 ;   
RECONFIGURE ;   
GO  
EXEC sp_configure 'max text repl size', -1 ;   
GO  
RECONFIGURE;   
GO  
  
```  
  
 <span data-ttu-id="a4f31-136">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="a4f31-136">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-max-text-repl-size-option"></a><a name="FollowUp"></a> <span data-ttu-id="a4f31-137">Completamento: Dopo la configurazione dell'opzione max text repl size</span><span class="sxs-lookup"><span data-stu-id="a4f31-137">Follow Up: After you configure the max text repl size option</span></span>  
 <span data-ttu-id="a4f31-138">L'impostazione diventa effettiva immediatamente senza dover riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="a4f31-138">The setting takes effect immediately without restarting the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4f31-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4f31-139">See Also</span></span>  
 <span data-ttu-id="a4f31-140">[Replica di SQL Server](../../relational-databases/replication/sql-server-replication.md) </span><span class="sxs-lookup"><span data-stu-id="a4f31-140">[SQL Server Replication](../../relational-databases/replication/sql-server-replication.md) </span></span>  
 <span data-ttu-id="a4f31-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4f31-141">[INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql) </span></span>  
 <span data-ttu-id="a4f31-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4f31-142">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="a4f31-143">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a4f31-143">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="a4f31-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4f31-144">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="a4f31-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4f31-145">[UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) </span></span>  
 <span data-ttu-id="a4f31-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a4f31-146">[UPDATETEXT &#40;Transact-SQL&#41;](/sql/t-sql/queries/updatetext-transact-sql) </span></span>  
 [<span data-ttu-id="a4f31-147">WRITETEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a4f31-147">WRITETEXT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/queries/writetext-transact-sql)  
  
  
