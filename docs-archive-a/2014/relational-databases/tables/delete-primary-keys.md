---
title: Eliminare chiavi primarie | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- removing primary keys
- deleting primary keys
- primary keys [SQL Server], deleting
ms.assetid: c472e465-7bdd-4d74-8fc9-e47fca007ccb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 44fa1271143f813364bfd2109f8147f1d04294a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638340"
---
# <a name="delete-primary-keys"></a><span data-ttu-id="2af3b-102">Eliminazione di chiavi primarie</span><span class="sxs-lookup"><span data-stu-id="2af3b-102">Delete Primary Keys</span></span>
  <span data-ttu-id="2af3b-103">È possibile eliminare una chiave primaria in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2af3b-103">You can delete (drop) a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="2af3b-104">Quando viene eliminata la chiave primaria, viene eliminato l'indice corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2af3b-104">When the primary key is deleted, the corresponding index is deleted.</span></span>  
  
 <span data-ttu-id="2af3b-105">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="2af3b-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2af3b-106">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="2af3b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2af3b-107">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2af3b-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2af3b-108">**Per eliminare una chiave primaria:**</span><span class="sxs-lookup"><span data-stu-id="2af3b-108">**To delete a primary key using:**</span></span>  
  
     [<span data-ttu-id="2af3b-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2af3b-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2af3b-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2af3b-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2af3b-111">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2af3b-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2af3b-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="2af3b-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2af3b-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="2af3b-113">Permissions</span></span>  
 <span data-ttu-id="2af3b-114">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="2af3b-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2af3b-115">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2af3b-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-object-explorer"></a><span data-ttu-id="2af3b-116">Per eliminare un vincolo chiave primaria utilizzando Esplora oggetti</span><span class="sxs-lookup"><span data-stu-id="2af3b-116">To delete a primary key constraint using Object Explorer</span></span>  
  
1.  <span data-ttu-id="2af3b-117">In Esplora oggetti, espandere la tabella contenente la chiave primaria, quindi espandere la cartella **Chiavi**.</span><span class="sxs-lookup"><span data-stu-id="2af3b-117">In Object Explorer, expand the table that contains the primary key and then expand **Keys**.</span></span>  
  
2.  <span data-ttu-id="2af3b-118">Fare clic con il pulsante destro del mouse sulla chiave e scegliere **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="2af3b-118">Right-click the key and select **Delete**.</span></span>  
  
3.  <span data-ttu-id="2af3b-119">Nella finestra di dialogo **Elimina oggetto** verificare che venga specificata la chiave corretta e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2af3b-119">In the **Delete Object** dialog box, verify the correct key is specified and click **OK**.</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint-using-table-designer"></a><span data-ttu-id="2af3b-120">Per eliminare un vincolo chiave primaria utilizzando Progettazione tabelle</span><span class="sxs-lookup"><span data-stu-id="2af3b-120">To delete a primary key constraint using Table Designer</span></span>  
  
1.  <span data-ttu-id="2af3b-121">In Esplora oggetti fare clic con il pulsante destro del mouse sulla tabella con la chiave primaria e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="2af3b-121">In Object Explorer, right-click the table with the primary key, and click **Design**.</span></span>  
  
2.  <span data-ttu-id="2af3b-122">Nella griglia della tabella fare clic con il pulsante destro del mouse sulla riga con la chiave primaria, quindi scegliere **Rimuovi chiave primaria** per attivare o disattivare l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="2af3b-122">In the table grid, right-click the row with the primary key and choose **Remove Primary Key** to toggle the setting from on to off.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2af3b-123">Per annullare questa operazione, chiudere la tabella senza salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2af3b-123">To undo this action, close the table without saving the changes.</span></span> <span data-ttu-id="2af3b-124">L'eliminazione di una chiave primaria non può essere annullata senza perdere tutte le altre modifiche apportate alla tabella.</span><span class="sxs-lookup"><span data-stu-id="2af3b-124">Deleting a primary key cannot be undone without losing all other changes made to the table.</span></span>  
  
3.  <span data-ttu-id="2af3b-125">Scegliere **Salva**_nome tabella_ dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="2af3b-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2af3b-126">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2af3b-126">Using Transact-SQL</span></span>  
  
#### <a name="to-delete-a-primary-key-constraint"></a><span data-ttu-id="2af3b-127">Per eliminare un vincolo di chiave primaria</span><span class="sxs-lookup"><span data-stu-id="2af3b-127">To delete a primary key constraint</span></span>  
  
1.  <span data-ttu-id="2af3b-128">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2af3b-128">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="2af3b-129">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="2af3b-129">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="2af3b-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="2af3b-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="2af3b-131">Nell'esempio viene prima identificato il nome del vincolo di chiave primaria, quindi questo viene eliminato.</span><span class="sxs-lookup"><span data-stu-id="2af3b-131">The example first identifies the name of the primary key constraint and then deletes the constraint.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Return the name of primary key.  
    SELECT name  
    FROM sys.key_constraints  
    WHERE type = 'PK' AND OBJECT_NAME(parent_object_id) = N'TransactionHistoryArchive';  
    GO  
    -- Delete the primary key constraint.  
    ALTER TABLE Production.TransactionHistoryArchive  
    DROP CONSTRAINT PK_TransactionHistoryArchive_TransactionID;   
    GO  
    ```  
  
 <span data-ttu-id="2af3b-132">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) e [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="2af3b-132">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql) and [sys.key_constraints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-key-constraints-transact-sql)</span></span>  
  
###  <a name="TsqlExample"></a>  
