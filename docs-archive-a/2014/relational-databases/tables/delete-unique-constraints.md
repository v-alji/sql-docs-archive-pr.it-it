---
title: Eliminare vincoli univoci | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing constraints
- UNIQUE constraints [SQL Server], deleting
- constraints [SQL Server], deleting
- deleting constraints
- constraints [SQL Server], unique
ms.assetid: 71e563fc-f5d7-4c2e-a42f-f0695a831f32
author: stevestein
ms.author: sstein
ms.openlocfilehash: f2fe2264aed4eb2f292a6bd1e4e565cebe2a833f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630406"
---
# <a name="delete-unique-constraints"></a><span data-ttu-id="a9562-102">Eliminazione di vincoli univoci</span><span class="sxs-lookup"><span data-stu-id="a9562-102">Delete Unique Constraints</span></span>
  <span data-ttu-id="a9562-103">È possibile eliminare un vincolo univoco in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9562-103">You can delete a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="a9562-104">L'eliminazione di un vincolo univoco consente di rimuovere il requisito di univocità per i valori immessi nella colonna o nella combinazione di colonne inclusa nell'espressione del vincolo ed elimina l'indice univoco corrispondente.</span><span class="sxs-lookup"><span data-stu-id="a9562-104">Deleting a unique constraint removes the requirement for uniqueness for values entered in the column or combination of columns included in the constraint expression and deletes the corresponding unique index.</span></span>  
  
 <span data-ttu-id="a9562-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="a9562-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="a9562-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="a9562-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="a9562-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a9562-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="a9562-108">**Per eliminare un vincolo univoco:**</span><span class="sxs-lookup"><span data-stu-id="a9562-108">**To delete a unique constraint, using:**</span></span>  
  
     [<span data-ttu-id="a9562-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a9562-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="a9562-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a9562-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a9562-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a9562-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a9562-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="a9562-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a9562-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a9562-113">Permissions</span></span>  
 <span data-ttu-id="a9562-114">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="a9562-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="a9562-115">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a9562-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-object-explorer"></a><span data-ttu-id="a9562-116">Per eliminare un vincolo univoco utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="a9562-116">To delete a unique constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="a9562-117">In Esplora oggetti, espandere la tabella contenente il vincolo univoco, quindi espandere la cartella **Vincoli**.</span><span class="sxs-lookup"><span data-stu-id="a9562-117">In Object Explorer, expand the table that contains the unique constraint and then expand **Constraints**.</span></span>  
  
2.  <span data-ttu-id="a9562-118">Fare clic con il pulsante destro del mouse sulla chiave e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a9562-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="a9562-119">Nella finestra di dialogo **Elimina oggetto** verificare che venga specificata la chiave corretta e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9562-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-unique-constraint-using-table-designer"></a><span data-ttu-id="a9562-120">Per eliminare un vincolo univoco utilizzando Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="a9562-120">To delete a unique constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="a9562-121">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulla tabella con il vincolo UNIQUE e selezionare **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="a9562-121">In **Object Explorer**, right-click the table with the unique constraint, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="a9562-122">Scegliere **Indici/chiavi** nel menu **Progettazione tabelle**.</span><span class="sxs-lookup"><span data-stu-id="a9562-122">On the **Table Designer** menu, click **Indexes/Keys**.</span></span>  
  
3.  <span data-ttu-id="a9562-123">Nella finestra di dialogo **Indici/chiavi** selezionare la chiave univoca dall'elenco **Chiave o indice primario/univoco selezionato** .</span><span class="sxs-lookup"><span data-stu-id="a9562-123">In the **Indexes/Keys** dialog box, select the unique key in the **Selected Primary/Unique Key and Index** list.</span></span>  
  
4.  <span data-ttu-id="a9562-124">Fare clic su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a9562-124">Click **Delete**.</span></span>  
  
5.  <span data-ttu-id="a9562-125">Nel menu **File** fare clic su **Salva** _nome tabella_.</span><span class="sxs-lookup"><span data-stu-id="a9562-125">On the **File** menu, click **Save** _table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="a9562-126">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="a9562-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-unique-constraint"></a><span data-ttu-id="a9562-127">Per eliminare un vincolo univoco</span><span class="sxs-lookup"><span data-stu-id="a9562-127">To delete a unique constraint</span></span>  
  
1.  <span data-ttu-id="a9562-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9562-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="a9562-129">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="a9562-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="a9562-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a9562-130">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Return the name of unique constraint.  
    SELECT name  
    FROM sys.objects  
    WHERE type = 'UQ' AND OBJECT_NAME(parent_object_id) = N' DocExc';  
    GO  
    -- Delete the unique constraint.  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT UNQ_ColumnB_DocExc;  
    GO  
    ```  
  
 <span data-ttu-id="a9562-131">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) e [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a9562-131">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.objects &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-objects-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
