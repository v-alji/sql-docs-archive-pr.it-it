---
title: Disabilitare un vincolo CHECK per la replica | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, disabling
- constraints [SQL Server], disabling
- disabling constraints
- constraints [SQL Server], check
ms.assetid: af98fc70-24dd-4bd3-a0a3-f701dfa67b2c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 98b6ca7c3525edeffdb47f294db568d3c115b2c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623112"
---
# <a name="disable-check-constraints-for-replication"></a><span data-ttu-id="1cf37-102">Disabilitare un vincolo CHECK per la replica</span><span class="sxs-lookup"><span data-stu-id="1cf37-102">Disable Check Constraints for Replication</span></span>
  <span data-ttu-id="1cf37-103">È possibile disabilitare i vincoli CHECK in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cf37-103">You can disable check constraints in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="1cf37-104">I vincoli CHECK possono essere espressamente disabilitati per la replica e ciò può essere utile quando si pubblicano dati da una versione precedente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cf37-104">You can also explicitly disable check constraints for replication, which can be useful if you are publishing data from a previous version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1cf37-105">Se una tabella viene pubblicata usando la replica, i vincoli CHECK vengono disabilitati automaticamente per le operazioni eseguite dagli agenti di replica.</span><span class="sxs-lookup"><span data-stu-id="1cf37-105">If a table is published using replication, check constraints are automatically disabled for operations performed by replication agents.</span></span> <span data-ttu-id="1cf37-106">Quando un agente di replica esegue un accodamento, aggiornamento o una eliminazione a un sottoscrittore, il vincolo non viene controllato; se invece un utente esegue un accodamento, un aggiornamento o una eliminazione, il vincolo viene controllato.</span><span class="sxs-lookup"><span data-stu-id="1cf37-106">When a replication agent performs an insert, update, or delete at a Subscriber, the constraint is not checked; if a user performs an insert, update, or delete, the constraint is checked.</span></span> <span data-ttu-id="1cf37-107">Il vincolo viene disabilitato per l'agente di replica in quanto esso è già stato controllato nel server di pubblicazione quando i dati sono stati inseriti, aggiornati o eliminati.</span><span class="sxs-lookup"><span data-stu-id="1cf37-107">The constraint is disabled for the replication agent because the constraint was already checked at the Publisher when the data was originally inserted, updated, or deleted.</span></span> <span data-ttu-id="1cf37-108">Per altre informazioni, vedere [Specificare le opzioni dello schema](../replication/publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="1cf37-108">For more information, see [Specify Schema Options](../replication/publish/specify-schema-options.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="1cf37-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="1cf37-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="1cf37-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="1cf37-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="1cf37-111">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="1cf37-111">Permissions</span></span>  
 <span data-ttu-id="1cf37-112">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="1cf37-112">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="1cf37-113">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="1cf37-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="1cf37-114">Per disabilitare un vincolo CHECK per la replica</span><span class="sxs-lookup"><span data-stu-id="1cf37-114">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="1cf37-115">In **Esplora oggetti**espandere la tabella contenente il vincolo CHECK che si desidera modificare, quindi espandere la cartella **Vincoli** .</span><span class="sxs-lookup"><span data-stu-id="1cf37-115">In **Object Explorer**, expand the table with the check constraint you want to modify, and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="1cf37-116">Fare clic con il pulsante destro del mouse sul vincolo CHECK da modificare, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="1cf37-116">Right-click the check constraint you wish to modify and then click **Modify**.</span></span>  
  
3.  <span data-ttu-id="1cf37-117">Nella finestra di dialogo **Verifica vincoli** , in **Progettazione tabelle**selezionare un valore **No** per **Attiva per replica**.</span><span class="sxs-lookup"><span data-stu-id="1cf37-117">In the **Check Constraints** dialog box, under **Table Designer**, select a value of **No** for **Enforce For Replication**.</span></span>  
  
4.  <span data-ttu-id="1cf37-118">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="1cf37-118">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="1cf37-119">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="1cf37-119">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-replication"></a><span data-ttu-id="1cf37-120">Per disabilitare un vincolo CHECK per la replica</span><span class="sxs-lookup"><span data-stu-id="1cf37-120">To disable a check constraint for replication</span></span>  
  
1.  <span data-ttu-id="1cf37-121">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cf37-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1cf37-122">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="1cf37-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1cf37-123">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1cf37-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="1cf37-124">Nell'esempio viene creata una tabella con una colonna IDENTITY e un vincolo CHECK sulla tabella.</span><span class="sxs-lookup"><span data-stu-id="1cf37-124">The example creates a table with an IDENTITY column and a CHECK constraint on the table.</span></span> <span data-ttu-id="1cf37-125">Nell'esempio il vincolo viene quindi eliminato e ricreato specificando la clausola NOT FOR REPLICATION.</span><span class="sxs-lookup"><span data-stu-id="1cf37-125">The example then drops the constraint and recreates it specifying the NOT FOR REPLICATION clause.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE TABLE dbo.doc_exd (column_a int IDENTITY (1,1)   
    CONSTRAINT exd_check CHECK (column_a > 1))   
  
    ALTER TABLE dbo.doc_exd   
    DROP CONSTRAINT exd_check;   
    GO  
    ALTER TABLE dbo.doc_exd    
    ADD CONSTRAINT exd_check CHECK NOT FOR REPLICATION (column_a > 1);  
    ```  
  
 <span data-ttu-id="1cf37-126">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1cf37-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>   
## <a name="see-also"></a><span data-ttu-id="1cf37-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cf37-127">See Also</span></span>  
 [<span data-ttu-id="1cf37-128">Specificare le opzioni dello schema</span><span class="sxs-lookup"><span data-stu-id="1cf37-128">Specify Schema Options</span></span>](../replication/publish/specify-schema-options.md)  
  
  
