---
title: Sincronizzare gli orologi dei server di destinazione (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- clocks [SQL Server]
- master servers [SQL Server], clock synchronization
- synchronization [SQL Server], target server clocks
- target servers [SQL Server], clock synchronization
ms.assetid: 4fb80502-d271-4d06-bcbc-bfbbceb5f2a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e7150cd42699503ab22cdd89fb6206194bd64e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711564"
---
# <a name="synchronize-target-server-clocks-sql-server-management-studio"></a><span data-ttu-id="680ff-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="680ff-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span></span>
  <span data-ttu-id="680ff-103">In questo argomento viene descritto come sincronizzare gli orologi dei server di destinazione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] con l'orologio del server master tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="680ff-103">This topic describes how to synchronize target server clocks in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] with the master server clock by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="680ff-104">La sincronizzazione di questi orologi di sistema supporta le pianificazioni dei processi.</span><span class="sxs-lookup"><span data-stu-id="680ff-104">Synchronizing these system clocks supports your job schedules.</span></span>  
  
 <span data-ttu-id="680ff-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="680ff-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="680ff-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="680ff-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="680ff-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="680ff-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="680ff-108">**Per sincronizzare gli orologi dei server di destinazione utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="680ff-108">**To synchronize target server clocks, using:**</span></span>  
  
     [<span data-ttu-id="680ff-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="680ff-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="680ff-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="680ff-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="680ff-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="680ff-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="680ff-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="680ff-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="680ff-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="680ff-113">Permissions</span></span>  
 <span data-ttu-id="680ff-114">È richiesta l'appartenenza al ruolo predefinito del server **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="680ff-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="680ff-115">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="680ff-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="680ff-116">Per sincronizzare gli orologi dei server di destinazione</span><span class="sxs-lookup"><span data-stu-id="680ff-116">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="680ff-117">In **Esplora oggetti** fare clic sul segno più per espandere il server di cui si desidera sincronizzare gli orologi del server di destinazione con l'orologio del server master.</span><span class="sxs-lookup"><span data-stu-id="680ff-117">In **Object Explorer,** click the plus sign to expand the server where you want to synchronize the target server clocks with the master server clock.</span></span>  
  
2.  <span data-ttu-id="680ff-118">Fare clic con il pulsante destro del mouse su **SQL Server Agent**, scegliere **Amministrazione multiserver**e selezionare **Gestione server di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="680ff-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="680ff-119">Nella finestra di dialogo **Gestione server di destinazione** , fare clic su **Invia istruzioni**.</span><span class="sxs-lookup"><span data-stu-id="680ff-119">In the **Manage Target Servers** dialog box, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="680ff-120">Nell'elenco **Tipo istruzione** selezionare **Sincronizza orologi**.</span><span class="sxs-lookup"><span data-stu-id="680ff-120">In the **Instruction type** list, select **Synchronize clocks**.</span></span>  
  
5.  <span data-ttu-id="680ff-121">In **Destinatari**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="680ff-121">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="680ff-122">Fare clic su **Tutti i server di destinazione** per sincronizzare gli orologi di tutti i server di destinazione con l'orologio del server master.</span><span class="sxs-lookup"><span data-stu-id="680ff-122">Click **All target servers** to synchronize all target server clocks with the master server clock.</span></span>  
  
    -   <span data-ttu-id="680ff-123">Fare clic su **Solo i server di destinazione** seguenti per sincronizzare gli orologi di alcuni server e quindi selezionare ogni server di destinazione di cui si desidera sincronizzare l'orologio con quello del server master.</span><span class="sxs-lookup"><span data-stu-id="680ff-123">Click **These target servers** to synchronize certain server clocks, and then select each target server whose clock you want to synchronize with the master server clock.</span></span>  
  
6.  <span data-ttu-id="680ff-124">Al termine, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="680ff-124">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="680ff-125">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="680ff-125">Using Transact-SQL</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="680ff-126">Per sincronizzare gli orologi dei server di destinazione</span><span class="sxs-lookup"><span data-stu-id="680ff-126">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="680ff-127">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="680ff-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="680ff-128">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="680ff-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="680ff-129">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="680ff-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- resynchronizes the SEATTLE1 target server  
    EXEC dbo.sp_resync_targetserver  
        N'SEATTLE1' ;  
    GO  
    ```  
  
 <span data-ttu-id="680ff-130">Per ulteriori informazioni, vedere [sp_resync_targetserver &#40;&#41;Transact-SQL ](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="680ff-130">For more information, see [sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span></span>  
  
  
