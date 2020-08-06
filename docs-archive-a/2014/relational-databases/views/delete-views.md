---
title: Eliminare viste | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- dropping views
- deleting views
- views [SQL Server], deleting
- removing views
ms.assetid: 6823c7f8-06ca-4bda-8482-7092f03d52a0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3e05724f7d6384d0407e915207ad60a1cdfb01b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623971"
---
# <a name="delete-views"></a><span data-ttu-id="3dc60-102">Eliminare viste</span><span class="sxs-lookup"><span data-stu-id="3dc60-102">Delete Views</span></span>
  <span data-ttu-id="3dc60-103">È possibile eliminare (rimuovere) le viste in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dc60-103">You can delete (drop) views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)]</span></span>  
  

  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="3dc60-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="3dc60-104">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="3dc60-105">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="3dc60-105">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="3dc60-106">Quando si rimuove una vista, dal catalogo di sistema vengono eliminate la definizione e altre informazioni della vista.</span><span class="sxs-lookup"><span data-stu-id="3dc60-106">When you drop a view, the definition of the view and other information about the view is deleted from the system catalog.</span></span> <span data-ttu-id="3dc60-107">Vengono inoltre eliminate tutte le autorizzazioni per la vista.</span><span class="sxs-lookup"><span data-stu-id="3dc60-107">All permissions for the view are also deleted.</span></span>  
  
-   <span data-ttu-id="3dc60-108">Qualsiasi vista di una tabella che viene eliminata tramite `DROP TABLE` deve essere eliminata in modo esplicito utilizzando `DROP VIEW`.</span><span class="sxs-lookup"><span data-stu-id="3dc60-108">Any view on a table that is dropped by using `DROP TABLE` must be dropped explicitly by using `DROP VIEW`.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="3dc60-109">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="3dc60-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="3dc60-110">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="3dc60-110">Permissions</span></span>  
 <span data-ttu-id="3dc60-111">È richiesta l'autorizzazione ALTER per l'autorizzazione SCHEMA o CONTROL per OBJECT.</span><span class="sxs-lookup"><span data-stu-id="3dc60-111">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="3dc60-112">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="3dc60-112">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="3dc60-113">Per eliminare una vista da un database</span><span class="sxs-lookup"><span data-stu-id="3dc60-113">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="3dc60-114">In **Esplora oggetti**espandere il database contenente la vista da eliminare, quindi espandere la cartella **Viste** .</span><span class="sxs-lookup"><span data-stu-id="3dc60-114">In **Object Explorer**, expand the database that contains the view you want to delete, and then expand the **Views** folder.</span></span>  
  
2.  <span data-ttu-id="3dc60-115">Fare clic con il pulsante destro del mouse sulla vista da eliminare e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="3dc60-115">Right-click the view you want to delete and click **Delete**.</span></span>  
  
3.  <span data-ttu-id="3dc60-116">Nella finestra di dialogo **Elimina oggetto** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="3dc60-116">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="3dc60-117">Fare clic su **Mostra dipendenze** nella finestra di dialogo **Elimina oggetto** per aprire la finestra di dialogo _Dipendenze_ di **nome_vista**.</span><span class="sxs-lookup"><span data-stu-id="3dc60-117">Click **Show Dependencies** in the **Delete Object** dialog box to open the _view_name_**Dependencies** dialog box.</span></span> <span data-ttu-id="3dc60-118">Verranno visualizzati tutti gli oggetti che dipendono dalla vista e tutti gli oggetti da cui dipende la vista.</span><span class="sxs-lookup"><span data-stu-id="3dc60-118">This will show all of the objects that depend on the view and all of the objects on which the view depends.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="3dc60-119">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="3dc60-119">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-view-from-a-database"></a><span data-ttu-id="3dc60-120">Per eliminare una vista da un database</span><span class="sxs-lookup"><span data-stu-id="3dc60-120">To delete a view from a database</span></span>  
  
1.  <span data-ttu-id="3dc60-121">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3dc60-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="3dc60-122">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="3dc60-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="3dc60-123">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="3dc60-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="3dc60-124">Nell'esempio si elimina la vista specificata solo se la vista già esiste.</span><span class="sxs-lookup"><span data-stu-id="3dc60-124">The example deletes the specified view only if the view already exists.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;  
    GO  
    IF OBJECT_ID ('HumanResources.EmployeeHireDate', 'V') IS NOT NULL  
    DROP VIEW HumanResources.EmployeeHireDate;  
    GO  
    ```  
  
 <span data-ttu-id="3dc60-125">Per altre informazioni, vedere [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3dc60-125">For more information, see [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
  
