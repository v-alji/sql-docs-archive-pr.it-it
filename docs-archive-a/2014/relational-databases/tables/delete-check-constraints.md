---
title: Eliminare vincoli CHECK | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- CHECK constraints, deleting
- constraints [SQL Server], deleting
- constraints [SQL Server], check
- deleting constraints
ms.assetid: 5f86c1a6-f5fa-4e77-a892-f6ae96fc0ab3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 28a7f72993cbf2ed0a8cc76534380090ef0d0a55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628582"
---
# <a name="delete-check-constraints"></a><span data-ttu-id="77f0d-102">Eliminazione dei vincoli CHECK</span><span class="sxs-lookup"><span data-stu-id="77f0d-102">Delete Check Constraints</span></span>
  <span data-ttu-id="77f0d-103">È possibile eliminare un vincolo CHECK in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77f0d-103">You can delete a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="77f0d-104">L'eliminazione dei vincoli CHECK consente di rimuovere le limitazioni sui valori dei dati accettati nella colonna o nella combinazione di colonne inclusa nell'espressione del vincolo.</span><span class="sxs-lookup"><span data-stu-id="77f0d-104">Deleting check constraints removes the limitations on data values that are accepted in the column or columns included in the constraint expression.</span></span>  
  
 <span data-ttu-id="77f0d-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="77f0d-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="77f0d-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="77f0d-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="77f0d-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="77f0d-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="77f0d-108">**Per eliminare un vincolo CHECK:**</span><span class="sxs-lookup"><span data-stu-id="77f0d-108">**To delete a check constraint, using:**</span></span>  
  
     [<span data-ttu-id="77f0d-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77f0d-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="77f0d-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77f0d-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="77f0d-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="77f0d-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="77f0d-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="77f0d-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="77f0d-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="77f0d-113">Permissions</span></span>  
 <span data-ttu-id="77f0d-114">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="77f0d-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="77f0d-115">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77f0d-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="77f0d-116">Per eliminare un vincolo CHECK</span><span class="sxs-lookup"><span data-stu-id="77f0d-116">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="77f0d-117">In **Esplora oggetti**, espandere la tabella con il vincolo CHECK.</span><span class="sxs-lookup"><span data-stu-id="77f0d-117">In **Object Explorer**, expand the table with the check constraint.</span></span>  
  
2.  <span data-ttu-id="77f0d-118">Espandere  **Vincoli**.</span><span class="sxs-lookup"><span data-stu-id="77f0d-118">Expand  **Constraints**.</span></span>  
  
3.  <span data-ttu-id="77f0d-119">Fare clic con il pulsante destro del mouse sul vincolo e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="77f0d-119">Right-click the constraint and click **Delete**.</span></span>  
  
4.  <span data-ttu-id="77f0d-120">Nella finestra di dialogo **Elimina oggetto** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="77f0d-120">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="77f0d-121">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="77f0d-121">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-check-constraint"></a><span data-ttu-id="77f0d-122">Per eliminare un vincolo CHECK</span><span class="sxs-lookup"><span data-stu-id="77f0d-122">To delete a check constraint</span></span>  
  
1.  <span data-ttu-id="77f0d-123">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77f0d-123">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="77f0d-124">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="77f0d-124">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="77f0d-125">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="77f0d-125">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT CHK_ColumnD_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="77f0d-126">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="77f0d-126">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span></span>  
  
  
