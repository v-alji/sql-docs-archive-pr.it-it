---
title: Avviare o arrestare un set di raccolta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection sets [SQL Server], stopping
- collection sets [SQL Server], starting
ms.assetid: 48a7b2fe-6bc3-4278-a7ec-1babc1290345
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e37d4b2edcd7a6e048c405b072bcbf9b1fef78c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636231"
---
# <a name="start-or-stop-a-collection-set"></a><span data-ttu-id="112c2-102">Avviare o arrestare un set di raccolta</span><span class="sxs-lookup"><span data-stu-id="112c2-102">Start or Stop a Collection Set</span></span>
  <span data-ttu-id="112c2-103">In questo argomento viene descritto come avviare o arrestare un set di raccolte in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="112c2-103">This topic describes how to start or stop a collection set in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="112c2-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="112c2-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="112c2-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="112c2-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="112c2-106">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="112c2-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="112c2-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="112c2-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="112c2-108">Indicazioni</span><span class="sxs-lookup"><span data-stu-id="112c2-108">Recommendations</span></span>](#Recommendations)  
  
     [<span data-ttu-id="112c2-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="112c2-109">Security</span></span>](#Security)  
  
-   <span data-ttu-id="112c2-110">**Per avviare o arrestare un set di raccolta utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="112c2-110">**To start or stop a collection set, using:**</span></span>  
  
     [<span data-ttu-id="112c2-111">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="112c2-111">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="112c2-112">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="112c2-112">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="112c2-113">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="112c2-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="112c2-114">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="112c2-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="112c2-115">Le stored procedure dell'agente di raccolta dati e le viste del catalogo vengono archiviate nel database **msdb** .</span><span class="sxs-lookup"><span data-stu-id="112c2-115">Data Collector stored procedures and catalog views are stored in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="112c2-116">A differenza delle normali stored procedure, i parametri per le stored procedure dell'agente di raccolta dati utilizzano parametri fortemente tipizzati e non supportano la conversione automatica del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="112c2-116">Unlike regular stored procedures, the parameters for data collector stored procedures are strictly typed and do not support automatic data type conversion.</span></span> <span data-ttu-id="112c2-117">Se tali parametri non vengono chiamati con i tipi di dati corretti per i parametri di input, come indicato nella descrizione dell'argomento, la stored procedure restituisce un errore.</span><span class="sxs-lookup"><span data-stu-id="112c2-117">If these parameters are not called with the correct input parameter data types, as specified in the argument description, the stored procedure returns an error.</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="112c2-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="112c2-118">Prerequisites</span></span>  
  
-   <span data-ttu-id="112c2-119">È necessario che il servizio SQL Server Agent sia avviato.</span><span class="sxs-lookup"><span data-stu-id="112c2-119">SQL Server Agent must be started.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="112c2-120">Raccomandazioni</span><span class="sxs-lookup"><span data-stu-id="112c2-120">Recommendations</span></span>  
  
-   <span data-ttu-id="112c2-121">Per ottenere informazioni sui set di raccolta, eseguire una query sulla vista del catalogo [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="112c2-121">To obtain information about collection sets, query the [syscollector_collection_sets](/sql/relational-databases/system-catalog-views/syscollector-collection-sets-transact-sql) catalog view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="112c2-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="112c2-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="112c2-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="112c2-123">Permissions</span></span>  
 <span data-ttu-id="112c2-124">È necessaria l'appartenenza al ruolo predefinito del database **dc_operator** .</span><span class="sxs-lookup"><span data-stu-id="112c2-124">Requires membership in the **dc_operator** fixed database role.</span></span> <span data-ttu-id="112c2-125">Se al set di raccolta non è associato un account proxy, è richiesta l'appartenenza al ruolo predefinito del server **sysadmin** . Esempi</span><span class="sxs-lookup"><span data-stu-id="112c2-125">If the collection set does not have a proxy account, membership in the **sysadmin** fixed server role is required.Examples</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="112c2-126">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="112c2-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="112c2-127">Per avviare un set di raccolta</span><span class="sxs-lookup"><span data-stu-id="112c2-127">To start a collection set</span></span>  
  
1.  <span data-ttu-id="112c2-128">In Esplora oggetti espandere il nodo **Gestione** , **Raccolta dati**, quindi **Set di raccolta dati di sistema**.</span><span class="sxs-lookup"><span data-stu-id="112c2-128">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="112c2-129">Fare clic con il pulsante destro del mouse sul set di raccolta che si vuole avviare, quindi scegliere **Avviare il set di raccolta dati**.</span><span class="sxs-lookup"><span data-stu-id="112c2-129">Right-click the collection set that you want to start, and then click **Start Data Collection Set**.</span></span>  
  
     <span data-ttu-id="112c2-130">In una finestra di messaggio verranno visualizzati i risultati di questa azione, mentre una freccia verde sull'icona del set di raccolta indica che il set di raccolta è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="112c2-130">A message box displays the results of this action, and a green arrow on the icon for the collection set indicates that the collection set has started.</span></span>  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="112c2-131">Per arrestare un set di raccolta</span><span class="sxs-lookup"><span data-stu-id="112c2-131">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="112c2-132">In Esplora oggetti espandere il nodo **Gestione** , **Raccolta dati**, quindi **Set di raccolta dati di sistema**.</span><span class="sxs-lookup"><span data-stu-id="112c2-132">In Object Explorer, expand the **Management** node, expand **Data Collection**, and then expand **System Data Collection Sets**.</span></span>  
  
2.  <span data-ttu-id="112c2-133">Fare clic con il pulsante destro del mouse sul set di raccolta che si vuole arrestare e quindi scegliere **Arresta set di raccolta dati**.</span><span class="sxs-lookup"><span data-stu-id="112c2-133">Right-click the collection set that you want to stop, and then click **Stop Data Collection Set**.</span></span>  
  
     <span data-ttu-id="112c2-134">In una finestra di messaggio verranno visualizzati i risultati di questa azione, mentre un cerchio rosso sull'icona del set di raccolta indica che il set di raccolta è stato arrestato.</span><span class="sxs-lookup"><span data-stu-id="112c2-134">A message box displays the results of this action, and a red circle on the icon for the collection set indicates that the collection set has stopped.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="112c2-135">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="112c2-135">Using Transact-SQL</span></span>  
  
#### <a name="to-start-a-collection-set"></a><span data-ttu-id="112c2-136">Per avviare un set di raccolta</span><span class="sxs-lookup"><span data-stu-id="112c2-136">To start a collection set</span></span>  
  
1.  <span data-ttu-id="112c2-137">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="112c2-137">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="112c2-138">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="112c2-138">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="112c2-139">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="112c2-139">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="112c2-140">In questo esempio si usa [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) per avviare il set di raccolta con l'ID `1`.</span><span class="sxs-lookup"><span data-stu-id="112c2-140">This example uses [sp_syscollector_start_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-start-collection-set-transact-sql) to start the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_start_collection_set @collection_set_id = 1;  
```  
  
#### <a name="to-stop-a-collection-set"></a><span data-ttu-id="112c2-141">Per arrestare un set di raccolta</span><span class="sxs-lookup"><span data-stu-id="112c2-141">To stop a collection set</span></span>  
  
1.  <span data-ttu-id="112c2-142">Connettersi al [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="112c2-142">Connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="112c2-143">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="112c2-143">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="112c2-144">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="112c2-144">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="112c2-145">In questo esempio si usa [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) per arrestare il set di raccolta con l'ID `1`.</span><span class="sxs-lookup"><span data-stu-id="112c2-145">This example uses [sp_syscollector_stop_collection_set](/sql/relational-databases/system-stored-procedures/sp-syscollector-stop-collection-set-transact-sql) to stop the collection set that has the ID of `1`.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC sp_syscollector_stop_collection_set @collection_set_id = 1;  
```  
  
## <a name="see-also"></a><span data-ttu-id="112c2-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="112c2-146">See Also</span></span>  
 <span data-ttu-id="112c2-147">[Viste dell'agente di raccolta dati &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="112c2-147">[Data Collector Views &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/data-collector-views-transact-sql) </span></span>  
 [<span data-ttu-id="112c2-148">Raccolta dati</span><span class="sxs-lookup"><span data-stu-id="112c2-148">Data Collection</span></span>](data-collection.md)  
  
  
