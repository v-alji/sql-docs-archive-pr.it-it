---
title: Abilitare o disabilitare la raccolta dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collector [SQL Server], disabling
- data collector [SQL Server], enabling
ms.assetid: 0137971b-fb48-4a3e-822a-3df2b9bb09d7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: af5cc647a63d3a9451086fc9e2211dec809e88fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625410"
---
# <a name="enable-or-disable-data-collection"></a><span data-ttu-id="97df0-102">Abilitazione o disabilitazione della raccolta dati</span><span class="sxs-lookup"><span data-stu-id="97df0-102">Enable or Disable Data Collection</span></span>
  <span data-ttu-id="97df0-103">In questo argomento viene descritto come abilitare o disabilitare una raccolta dati in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97df0-103">This topic describes how to enable or disable data collection in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="97df0-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="97df0-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="97df0-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="97df0-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="97df0-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="97df0-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="97df0-107">**Per abilitare o disabilitare la raccolta dati utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="97df0-107">**To enable or disable data collection, using:**</span></span>  
  
     [<span data-ttu-id="97df0-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97df0-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="97df0-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97df0-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="97df0-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="97df0-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="97df0-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="97df0-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="97df0-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="97df0-112">Permissions</span></span>  
 <span data-ttu-id="97df0-113">Per eseguire questa procedura, è necessaria l'appartenenza al ruolo predefinito del database **dc_admin** o **dc_operator** (con autorizzazione EXECUTE).</span><span class="sxs-lookup"><span data-stu-id="97df0-113">Requires membership in the **dc_admin** or **dc_operator** (with EXECUTE permission) fixed database role to execute this procedure.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="97df0-114">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97df0-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="97df0-115">Per abilitare l'agente di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="97df0-115">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="97df0-116">In Esplora oggetti espandere il nodo **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="97df0-116">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="97df0-117">Fare clic con il pulsante destro del mouse su **Raccolta dati**, quindi scegliere **Abilita raccolta dati**.</span><span class="sxs-lookup"><span data-stu-id="97df0-117">Right-click **Data Collection**, and then click **Enable Data Collection**.</span></span>  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="97df0-118">Per disabilitare l'agente di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="97df0-118">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="97df0-119">In Esplora oggetti espandere il nodo **Gestione** .</span><span class="sxs-lookup"><span data-stu-id="97df0-119">In Object Explorer, expand the **Management** node.</span></span>  
  
2.  <span data-ttu-id="97df0-120">Fare clic con il pulsante destro del mouse su **Raccolta dati**, quindi scegliere **Disabilita raccolta dati**.</span><span class="sxs-lookup"><span data-stu-id="97df0-120">Right-click **Data Collection**, and then click **Disable Data Collection**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="97df0-121">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="97df0-121">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-the-data-collector"></a><span data-ttu-id="97df0-122">Per abilitare l'agente di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="97df0-122">To enable the data collector</span></span>  
  
1.  <span data-ttu-id="97df0-123">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97df0-123">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="97df0-124">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="97df0-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="97df0-125">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="97df0-125">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="97df0-126">Questo esempio usa [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) per abilitare l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="97df0-126">This example uses [sp_syscollector_enable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) to enable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_enable_collector ;  
```  
  
#### <a name="to-disable-the-data-collector"></a><span data-ttu-id="97df0-127">Per disabilitare l'agente di raccolta dati</span><span class="sxs-lookup"><span data-stu-id="97df0-127">To disable the data collector</span></span>  
  
1.  <span data-ttu-id="97df0-128">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97df0-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="97df0-129">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="97df0-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="97df0-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="97df0-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="97df0-131">Questo esempio usa [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) per disabilitare l'agente di raccolta dati.</span><span class="sxs-lookup"><span data-stu-id="97df0-131">This example uses [sp_syscollector_disable_collector](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) to disable the data collector.</span></span>  
  
```sql  
USE msdb;  
GO  
EXEC dbo.sp_syscollector_disable_collector;  
```  
  
## <a name="see-also"></a><span data-ttu-id="97df0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97df0-132">See Also</span></span>  
 <span data-ttu-id="97df0-133">[Raccolta dati](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="97df0-133">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="97df0-134">Stored procedure di sistema &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="97df0-134">System Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/system-stored-procedures-transact-sql)  
  
  
