---
title: Disabilitare i vincoli CHECK con le istruzioni INSERT e UPDATE | Microsoft Docs
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
ms.assetid: c7287ad1-50d2-4e80-bc0c-b5570f7e5f69
author: stevestein
ms.author: sstein
ms.openlocfilehash: 780a2c1bfd9f21c71367ad61f200ec19ab44a608
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628573"
---
# <a name="disable-check-constraints-with-insert-and-update-statements"></a><span data-ttu-id="ee635-102">Disabilitazione di vincoli CHECK con le istruzioni INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="ee635-102">Disable Check Constraints with INSERT and UPDATE Statements</span></span>
  <span data-ttu-id="ee635-103">È possibile disabilitare un vincolo CHECK per transazioni INSERT e UPDATE in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee635-103">You can disable a check constraint for INSERT and UPDATE transactions in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="ee635-104">Dopo aver disabilitato i vincoli CHECK, gli inserimenti o gli aggiornamenti successivi della colonna non saranno convalidati in base alle condizioni del vincolo.</span><span class="sxs-lookup"><span data-stu-id="ee635-104">After you disable the check constraints, future inserts or updates to the column will not be validated against the constraint conditions.</span></span> <span data-ttu-id="ee635-105">Usare questa opzione se si è sicuri che i nuovi dati violeranno il vincolo esistente o se il vincolo si applica solo ai dati già presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="ee635-105">Use this option if you know that new data will violate the existing constraint or if the constraint applies only to the data already in the database.</span></span>  
  
 <span data-ttu-id="ee635-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="ee635-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ee635-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="ee635-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ee635-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ee635-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ee635-109">**Per disabilitare un vincolo CHECK per le istruzioni INSERT e UPDATE:**</span><span class="sxs-lookup"><span data-stu-id="ee635-109">**To disable a check constraint for INSERT and UPDATE statements, using:**</span></span>  
  
     [<span data-ttu-id="ee635-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee635-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ee635-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee635-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ee635-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="ee635-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ee635-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="ee635-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ee635-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="ee635-114">Permissions</span></span>  
 <span data-ttu-id="ee635-115">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="ee635-115">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ee635-116">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ee635-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="ee635-117">Per disabilitare un vincolo CHECK per le istruzioni INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="ee635-117">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="ee635-118">In **Esplora oggetti**, espandere la tabella contenente il vincolo che si desidera modificare, quindi espandere la cartella **Vincoli** .</span><span class="sxs-lookup"><span data-stu-id="ee635-118">In **Object Explorer**, expand the table with the constraint and then expand the **Constraints** folder.</span></span>  
  
2.  <span data-ttu-id="ee635-119">Fare clic con il pulsante destro del mouse sul vincolo e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ee635-119">Right-click the constraint and select **Modify**.</span></span>  
  
3.  <span data-ttu-id="ee635-120">Nella griglia, in **Progettazione tabelle**, fare clic su **Attiva per istruzioni INSERTs e UPDATEs** , quindi scegliere **No** dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="ee635-120">In the grid under **Table Designer**, click **Enforce For INSERTs And UPDATEs** and select **No** from the drop-down menu.</span></span>  
  
4.  <span data-ttu-id="ee635-121">Fare clic su **Close**.</span><span class="sxs-lookup"><span data-stu-id="ee635-121">Click **Close**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ee635-122">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ee635-122">Using Transact-SQL</span></span>  
  
#### <a name="to-disable-a-check-constraint-for-insert-and-update-statements"></a><span data-ttu-id="ee635-123">Per disabilitare un vincolo CHECK per le istruzioni INSERT e UPDATE</span><span class="sxs-lookup"><span data-stu-id="ee635-123">To disable a check constraint for INSERT and UPDATE statements</span></span>  
  
1.  <span data-ttu-id="ee635-124">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee635-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="ee635-125">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="ee635-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="ee635-126">Copiare e incollare gli esempi seguenti nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="ee635-126">Copy and paste the following examples into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    ALTER TABLE Purchasing.PurchaseOrderHeader  
    NOCHECK CONSTRAINT CK_PurchaseOrderHeader_Freight;   
    GO  
    ```  
  
 <span data-ttu-id="ee635-127">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="ee635-127">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
