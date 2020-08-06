---
title: Visualizzare proprietà di chiave esterna | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- foreign keys [SQL Server], attributes
- displaying foreign keys attributes
- viewing foreign keys attributes
ms.assetid: b0e57cb7-9b26-4b96-b76a-1f59f5f498c5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5860a0cf26b983d75bab86862ee1e5fdd7737712
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624542"
---
# <a name="view-foreign-key-properties"></a><span data-ttu-id="09bf8-102">Visualizzare Proprietà di chiave esterna</span><span class="sxs-lookup"><span data-stu-id="09bf8-102">View Foreign Key Properties</span></span>
  <span data-ttu-id="09bf8-103">È possibile visualizzare gli attribuiti della chiave esterna di una relazione in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09bf8-103">You can view the foreign key attributes of a relationship in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="09bf8-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="09bf8-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="09bf8-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="09bf8-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="09bf8-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="09bf8-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="09bf8-107">**Per visualizzare gli attributi della chiave esterna di una tabella specifica utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="09bf8-107">**To view the foreign key attributes of a specific table, using:**</span></span>  
  
     [<span data-ttu-id="09bf8-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09bf8-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="09bf8-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09bf8-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="09bf8-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="09bf8-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="09bf8-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="09bf8-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="09bf8-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="09bf8-112">Permissions</span></span>  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] <span data-ttu-id="09bf8-113">Per altre informazioni, vedere [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="09bf8-113">For more information, see [Metadata Visibility Configuration](../security/metadata-visibility-configuration.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="09bf8-114">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="09bf8-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="09bf8-115">Per visualizzare gli attributi della chiave esterna di una relazione in una tabella specifica</span><span class="sxs-lookup"><span data-stu-id="09bf8-115">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="09bf8-116">Aprire Progettazione tabelle per la tabella contenente la chiave esterna che si vuole visualizzare, fare clic con il pulsante destro del mouse su Progettazione tabelle e scegliere **Relazioni** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="09bf8-116">Open the Table Designer for the table containing the foreign key you want to view, right-click in the Table Designer, and choose **Relationships** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="09bf8-117">Nella finestra di dialogo **Relazioni di chiave esterna** selezionare la relazione con le proprietà che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="09bf8-117">In the **Foreign Key Relationships** dialog box, select the relationship with properties you want to view.</span></span>  
  
 <span data-ttu-id="09bf8-118">Se le colonne chiave esterna sono correlate a una chiave primaria, le colonne chiave primaria saranno identificate in **Progettazione tabelle** mediante un simbolo di chiave primaria nel selettore di riga.</span><span class="sxs-lookup"><span data-stu-id="09bf8-118">If the foreign key columns are related to a primary key, the primary key columns are identified in **Table Designer** by a primary key symbol in the row selector.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="09bf8-119">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="09bf8-119">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-foreign-key-attributes-of-a-relationship-in-a-specific-table"></a><span data-ttu-id="09bf8-120">Per visualizzare gli attributi della chiave esterna di una relazione in una tabella specifica</span><span class="sxs-lookup"><span data-stu-id="09bf8-120">To view the foreign key attributes of a relationship in a specific table</span></span>  
  
1.  <span data-ttu-id="09bf8-121">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09bf8-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="09bf8-122">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="09bf8-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="09bf8-123">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="09bf8-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="09bf8-124">Nell'esempio vengono restituite tutte le chiavi esterne e le relative proprietà per tabella `HumanResources.Employee` nel database di esempio.</span><span class="sxs-lookup"><span data-stu-id="09bf8-124">The example returns all foreign keys and their properties for the table `HumanResources.Employee` in the sample database.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    SELECT   
        f.name AS foreign_key_name  
       ,OBJECT_NAME(f.parent_object_id) AS table_name  
       ,COL_NAME(fc.parent_object_id, fc.parent_column_id) AS constraint_column_name  
       ,OBJECT_NAME (f.referenced_object_id) AS referenced_object  
       ,COL_NAME(fc.referenced_object_id, fc.referenced_column_id) AS referenced_column_name  
       ,is_disabled  
       ,delete_referential_action_desc  
       ,update_referential_action_desc  
    FROM sys.foreign_keys AS f  
    INNER JOIN sys.foreign_key_columns AS fc   
       ON f.object_id = fc.constraint_object_id   
    WHERE f.parent_object_id = OBJECT_ID('HumanResources.Employee');  
    ```  
  
 <span data-ttu-id="09bf8-125">Per altre informazioni, vedere [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) e [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="09bf8-125">For more information, see [sys.foreign_keys &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-keys-transact-sql) and [sys.foreign_key_columns &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-foreign-key-columns-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
