---
title: Visualizzare la definizione di una tabella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- showing table properties
- displaying table properties
- tables [SQL Server], properties
- viewing table properties
ms.assetid: 1865fb7c-f480-4100-9007-df5364cd002a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53170a78a104bfce4b4e4177015461f2eb9093e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638333"
---
# <a name="view-the-table-definition"></a><span data-ttu-id="19b18-102">Visualizzare la definizione di una tabella</span><span class="sxs-lookup"><span data-stu-id="19b18-102">View the Table Definition</span></span>
  <span data-ttu-id="19b18-103">È possibile visualizzare proprietà per una tabella in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19b18-103">You can display properties for a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="19b18-104">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="19b18-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="19b18-105">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="19b18-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="19b18-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="19b18-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="19b18-107">**Per visualizzare le proprietà di tabella:**</span><span class="sxs-lookup"><span data-stu-id="19b18-107">**To display table properties, using:**</span></span>  
  
     [<span data-ttu-id="19b18-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="19b18-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="19b18-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="19b18-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="19b18-110">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="19b18-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="19b18-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="19b18-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="19b18-112">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="19b18-112">Permissions</span></span>  
 <span data-ttu-id="19b18-113">È possibile vedere solo proprietà in una tabella se si possiede la tabella o sono state concesse autorizzazioni a quella tabella.</span><span class="sxs-lookup"><span data-stu-id="19b18-113">You can only see properties in a table if you either own the table or have been granted permissions to that table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="19b18-114">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="19b18-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-table-properties-in-the-properties-window"></a><span data-ttu-id="19b18-115">Per visualizzare le proprietà di una tabella nella finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="19b18-115">To show table properties in the Properties window</span></span>  
  
1.  <span data-ttu-id="19b18-116">In Esplora oggetti selezionare la tabella per la quale si desidera mostrare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="19b18-116">In Object Explorer, select the table for which you want to show properties.</span></span>  
  
2.  <span data-ttu-id="19b18-117">Fare clic con il pulsante destro del mouse sulla tabella, quindi scegliere **Proprietà** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="19b18-117">Right-click the table and choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="19b18-118">Per altre informazioni, vedere [Table Properties](table-properties-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="19b18-118">For more information, see [Table Properties](table-properties-ssms.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="19b18-119">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="19b18-119">Using Transact-SQL</span></span>  
  
#### <a name="to-show-table-properties"></a><span data-ttu-id="19b18-120">Per mostrare le proprietà di tabella</span><span class="sxs-lookup"><span data-stu-id="19b18-120">To show table properties</span></span>  
  
1.  <span data-ttu-id="19b18-121">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19b18-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="19b18-122">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="19b18-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="19b18-123">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="19b18-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="19b18-124">Nell'esempio seguente vengono restituite tutte le colonne dalla vista del catalogo `sys.tables` per l'oggetto specificato.</span><span class="sxs-lookup"><span data-stu-id="19b18-124">The example returns all columns from the `sys.tables` catalog view for the specified object.</span></span>  
  
    ```  
    SELECT * FROM sys.tables  
    WHERE object_id = 1973582069;  
  
    ```  
  
 <span data-ttu-id="19b18-125">Per altre informazioni, vedere [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="19b18-125">For more information, see [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
