---
title: Configurare l'opzione di configurazione del server fill factor | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- fill factor option [SQL Server]
ms.assetid: b920ec34-ba8b-4bb8-af53-a3ffd06bafa6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 02258c92b4a09277d371e605fd4729ba9fda3461
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629609"
---
# <a name="configure-the-fill-factor-server-configuration-option"></a><span data-ttu-id="09b6a-102">Configurare l'opzione di configurazione del server fill factor</span><span class="sxs-lookup"><span data-stu-id="09b6a-102">Configure the fill factor Server Configuration Option</span></span>
  <span data-ttu-id="09b6a-103">In questo argomento si illustra come configurare l'opzione di configurazione del server **fill factor** in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09b6a-103">This topic describes how to configure the **fill factor** server configuration option in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="09b6a-104">Il fattore di riempimento viene fornito per ottimizzare l'archiviazione dati e le prestazioni degli indici.</span><span class="sxs-lookup"><span data-stu-id="09b6a-104">Fill factor is provided for fine-tuning index data storage and performance.</span></span> <span data-ttu-id="09b6a-105">Quando si crea o si ricompila un indice, il valore del fattore di riempimento consente di determinare la percentuale di spazio in ogni pagina al livello foglia da riempire di dati, riservando il resto come spazio libero per la crescita futura.</span><span class="sxs-lookup"><span data-stu-id="09b6a-105">When an index is created or rebuilt, the fill-factor value determines the percentage of space on each leaf-level page to be filled with data, reserving the rest as free space for future growth.</span></span> <span data-ttu-id="09b6a-106">Per altre informazioni, vedere [Specificare un fattore di riempimento per un indice](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="09b6a-106">For more information, see [Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md).</span></span>  
  
 <span data-ttu-id="09b6a-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="09b6a-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="09b6a-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="09b6a-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="09b6a-109">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="09b6a-109">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="09b6a-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="09b6a-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="09b6a-111">**Per configurare l'opzione fill factor utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="09b6a-111">**To configure the fill factor option, using:**</span></span>  
  
     [<span data-ttu-id="09b6a-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09b6a-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="09b6a-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09b6a-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="09b6a-114">**Completamento:**  [Dopo la configurazione dell'opzione fill factor](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="09b6a-114">**Follow Up:**  [After you configure the fill factor option](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="09b6a-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="09b6a-115">Before You Begin</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="09b6a-116">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="09b6a-116">Recommendations</span></span>  
  
-   <span data-ttu-id="09b6a-117">Questa opzione è avanzata e la relativa modifica è riservata ad amministratori di database esperti o a tecnici dotati di certificazione per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="09b6a-117">This option is an advanced option and should be changed only by an experienced database administrator or certified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] technician.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="09b6a-118">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="09b6a-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="09b6a-119">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="09b6a-119">Permissions</span></span>  
 <span data-ttu-id="09b6a-120">Le autorizzazioni di esecuzione per **sp_configure** senza alcun parametro o solo con il primo parametro vengono assegnate per impostazione predefinita a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="09b6a-120">Execute permissions on **sp_configure** with no parameters or with only the first parameter are granted to all users by default.</span></span> <span data-ttu-id="09b6a-121">Per eseguire **sp_configure** con entrambi i parametri per la modifica di un'opzione di configurazione o per l'esecuzione dell'istruzione RECONFIGURE, a un utente deve essere concessa l'autorizzazione a livello di server ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="09b6a-121">To execute **sp_configure** with both parameters to change a configuration option or to run the RECONFIGURE statement, a user must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="09b6a-122">L'autorizzazione ALTER SETTINGS è assegnata implicitamente ai ruoli predefiniti del server **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="09b6a-122">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="09b6a-123">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09b6a-123">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="09b6a-124">Per configurare l'opzione fill factor</span><span class="sxs-lookup"><span data-stu-id="09b6a-124">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="09b6a-125">In Esplora oggetti fare clic con il pulsante destro del mouse su un server e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="09b6a-125">In Object Explorer, right-click a server and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="09b6a-126">Fare clic sul nodo **Impostazioni database** .</span><span class="sxs-lookup"><span data-stu-id="09b6a-126">Click the **Database Settings** node.</span></span>  
  
3.  <span data-ttu-id="09b6a-127">Nella casella **Fattore di riempimento indice predefinito** digitare o selezionare il fattore di riempimento indice desiderato.</span><span class="sxs-lookup"><span data-stu-id="09b6a-127">In the **Default index fill factor** box, type or select the index fill factor that you want.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="09b6a-128">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09b6a-128">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-the-fill-factor-option"></a><span data-ttu-id="09b6a-129">Per configurare l'opzione fill factor</span><span class="sxs-lookup"><span data-stu-id="09b6a-129">To configure the fill factor option</span></span>  
  
1.  <span data-ttu-id="09b6a-130">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09b6a-130">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="09b6a-131">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="09b6a-131">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="09b6a-132">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="09b6a-132">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="09b6a-133">Questo esempio illustra come usare [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) per impostare il valore dell'opzione `fill factor` su `100`.</span><span class="sxs-lookup"><span data-stu-id="09b6a-133">This example shows how to use [sp_configure](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) to set the value of the `fill factor` option to `100`.</span></span>  
  
```sql  
Use AdventureWorks2012;  
GO  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'fill factor', 100;  
GO  
RECONFIGURE;  
GO  
```  
  
 <span data-ttu-id="09b6a-134">Per altre informazioni, vedere [Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md)sia installato il servizio WMI.</span><span class="sxs-lookup"><span data-stu-id="09b6a-134">For more information, see [Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md).</span></span>  
  
##  <a name="follow-up-after-you-configure-the-fill-factor-option"></a><a name="FollowUp"></a> <span data-ttu-id="09b6a-135">Completamento: Dopo la configurazione dell'opzione fill factor</span><span class="sxs-lookup"><span data-stu-id="09b6a-135">Follow Up: After you configure the fill factor option</span></span>  
 <span data-ttu-id="09b6a-136">Per poter rendere effettiva l'impostazione, è necessario riavviare il server.</span><span class="sxs-lookup"><span data-stu-id="09b6a-136">The server must be restarted before the setting can take effect.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09b6a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09b6a-137">See Also</span></span>  
 <span data-ttu-id="09b6a-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09b6a-138">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 <span data-ttu-id="09b6a-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09b6a-139">[ALTER INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-index-transact-sql) </span></span>  
 <span data-ttu-id="09b6a-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09b6a-140">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 <span data-ttu-id="09b6a-141">[Specificare un fattore di riempimento per un indice](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span><span class="sxs-lookup"><span data-stu-id="09b6a-141">[Specify Fill Factor for an Index](../../relational-databases/indexes/specify-fill-factor-for-an-index.md) </span></span>  
 <span data-ttu-id="09b6a-142">[Opzioni di configurazione del server &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="09b6a-142">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="09b6a-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="09b6a-143">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="09b6a-144">sys.indexes &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="09b6a-144">sys.indexes &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-indexes-transact-sql)  
  
  
