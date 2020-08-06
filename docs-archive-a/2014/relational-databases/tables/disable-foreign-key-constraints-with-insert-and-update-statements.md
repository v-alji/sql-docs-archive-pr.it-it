---
title: Disabilitare i vincoli di chiave esterna con le istruzioni INSERT e UPDATE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- constraints [SQL Server], foreign keys
- foreign keys [SQL Server], disabling constraints
- disabling constraints
- UPDATE statement [SQL Server], foreign key constraints
- INSERT statement [SQL Server], foreign key constraints
ms.assetid: 029168d7-085e-4b13-9b86-5644b67c6e24
author: stevestein
ms.author: sstein
ms.openlocfilehash: e91328f4f12f2a0a27f397c7bd95390a505f3998
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627667"
---
# <a name="disable-foreign-key-constraints-with-insert-and-update-statements"></a><span data-ttu-id="54ede-102">Disabilitazione di vincoli di chiave esterna con le istruzioni INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="54ede-102">Disable Foreign Key Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="54ede-103">È possibile disabilitare un vincolo di chiave esterna durante le transazioni INSERT e UPDATE in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54ede-103">You can disable a foreign key constraint during INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="54ede-104">Usare questa opzione se si è sicuri che i nuovi dati violeranno il vincolo esistente o se il vincolo si applica solo ai dati già presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="54ede-104">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="54ede-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="54ede-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="54ede-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="54ede-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="54ede-107">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="54ede-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="54ede-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="54ede-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="54ede-109">**Per disabilitare un vincolo di chiave esterna per le istruzioni INSERT e UPDATE tramite:**</span><span class="sxs-lookup"><span data-stu-id="54ede-109">**To disable a foreign key constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="54ede-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54ede-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="54ede-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54ede-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="54ede-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="54ede-112">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="54ede-113">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="54ede-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="54ede-114">Dopo aver disabilitato questi vincoli, gli inserimenti o gli aggiornamenti successivi della colonna non saranno convalidati in base alle condizioni del vincolo.</span><span class="sxs-lookup"><span data-stu-id="54ede-114">After you disable these constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="54ede-115">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="54ede-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="54ede-116">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="54ede-116">Permissions</span></span>  
 <span data-ttu-id="54ede-117">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="54ede-117">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="54ede-118">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="54ede-118">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="54ede-119">Per disabilitare un vincolo di chiave esterna per le istruzioni INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="54ede-119">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="54ede-120">In **Esplora oggetti**espandere la tabella contenente il vincolo, quindi espandere la cartella **Chiavi** .</span><span class="sxs-lookup"><span data-stu-id="54ede-120">In **Object Explorer**, expand the table with the constraint and then expand the **Keys** folder.</span></span>  
  
2.  <span data-ttu-id="54ede-121">Fare clic con il pulsante destro del mouse sul vincolo e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="54ede-121">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="54ede-122">Nella griglia in **Progettazione tabelle**fare clic su **Attiva vincolo della chiave esterna** , quindi scegliere **No** nel menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="54ede-122">In the grid under **Table Designer**, click **Enforce Foreign Key Constraint** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="54ede-123">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="54ede-123">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="54ede-124">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="54ede-124">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-foreign-key-constraint-for-insert-and-update-statements"></a><span data-ttu-id="54ede-125">Per disabilitare un vincolo di chiave esterna per le istruzioni INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="54ede-125">To disable a foreign key constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="54ede-126">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="54ede-126">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="54ede-127">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="54ede-127">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="54ede-128">Copiare e incollare gli esempi seguenti nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="54ede-128">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT FK_PurchaseOrderHeader_Employee_EmployeeID;  
    GO  
    ```  
  
 <span data-ttu-id="54ede-129">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="54ede-129">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
