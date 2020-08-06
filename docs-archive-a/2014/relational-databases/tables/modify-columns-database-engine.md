---
title: Modificare colonne (motore di database) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying data types
- column data types [SQL Server]
- data types [SQL Server], columns
ms.assetid: b67b95c5-61ef-4bd8-9a3e-1640eb7583ac
author: stevestein
ms.author: sstein
ms.openlocfilehash: a73c25d91b742f1cc1f7edcc8a95cdf226b2683c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629736"
---
# <a name="modify-columns-database-engine"></a><span data-ttu-id="aa2b3-102">Modificare colonne (motore di database)</span><span class="sxs-lookup"><span data-stu-id="aa2b3-102">Modify Columns (Database Engine)</span></span>
  <span data-ttu-id="aa2b3-103">È possibile modificare il tipo di dati di una colonna in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa2b3-103">You can modify the data type of a column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="aa2b3-104">La modifica del tipo di dati di una colonna in cui sono già contenuti dati può comportare la perdita definitiva di tali dati al momento della conversione.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-104">Modifying the data type of a column that already contains data can result in the permanent loss of data when the existing data is converted to the new type.</span></span> <span data-ttu-id="aa2b3-105">È possibile inoltre che si verifichino errori nel codice e nelle applicazioni che dipendono dalla colonna modificata,</span><span class="sxs-lookup"><span data-stu-id="aa2b3-105">In addition, code and applications that depend on the modified column may fail.</span></span> <span data-ttu-id="aa2b3-106">incluse query, viste, stored procedure, funzioni definite dall'utente e applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-106">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="aa2b3-107">Tali errori inoltre tendono a propagarsi a cascata.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-107">Note that these failures will cascade.</span></span> <span data-ttu-id="aa2b3-108">Possono ad esempio verificarsi errori in una stored procedure che chiama una funzione definita dall'utente che dipende dalla colonna modificata.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-108">For example, a stored procedure that calls a user-defined function that depends on the modified column may fail.</span></span> <span data-ttu-id="aa2b3-109">È pertanto opportuno valutare seriamente ogni eventuale modifica da apportare a una colonna prima di procedere.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-109">Carefully consider any changes you want to make to a column before making it.</span></span>  
  
 <span data-ttu-id="aa2b3-110">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="aa2b3-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aa2b3-111">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="aa2b3-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aa2b3-112">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="aa2b3-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aa2b3-113">**Per modificare il tipo di dati di una colonna:**</span><span class="sxs-lookup"><span data-stu-id="aa2b3-113">**To modify the data type of a column, using:**</span></span>  
  
     [<span data-ttu-id="aa2b3-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa2b3-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="aa2b3-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa2b3-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aa2b3-116">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="aa2b3-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aa2b3-117">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="aa2b3-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aa2b3-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="aa2b3-118">Permissions</span></span>  
 <span data-ttu-id="aa2b3-119">È necessario disporre dell'autorizzazione ALTER per la tabella.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-119">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aa2b3-120">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aa2b3-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="aa2b3-121">Per modificare il tipo di dati di una colonna</span><span class="sxs-lookup"><span data-stu-id="aa2b3-121">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="aa2b3-122">In **Esplora oggetti**fare clic con il pulsante destro del mouse sulle colonne della tabella di cui modificare la scala e scegliere **Progetta**.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-122">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="aa2b3-123">Selezionare la colonna per la quale si desidera modificare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-123">Select the column for which you want to modify the data type.</span></span>  
  
3.  <span data-ttu-id="aa2b3-124">Nella scheda **Proprietà colonne** fare clic sulla cella della griglia relativa alla proprietà **Tipo di dati** , quindi selezionare un nuovo tipo di dati dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-124">In the **Column Properties** tab, click the grid cell for the **Data Type** property and choose a new data type from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="aa2b3-125">Scegliere **Salva**_nome tabella_ dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="aa2b3-126">Quando si modifica il tipo di dati di una colonna, in Progettazione tabelle verrà applicata la lunghezza predefinita del tipo di dati selezionato, anche se ne è stata già specificata un'altra.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-126">When you modify the data type of a column, Table Designer applies the default length of the data type you selected, even if you have already specified another.</span></span> <span data-ttu-id="aa2b3-127">È pertanto opportuno impostare sempre la lunghezza del tipo di dati per il valore desiderato dopo avere specificato il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-127">Always set the data type length for to the desired value after specifying the data type.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="aa2b3-128">Se si tenta di modificare il tipo di dati di una colonna correlata alle altre tabelle, Progettazione tabelle chiede all'utente di confermare anche la modifica da apportare alle colonne nelle altre tabelle.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-128">If you attempt to modify the data type of a column that relates to other tables, Table Designer asks you to confirm that the change should be made to the columns in the other tables as well.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="aa2b3-129">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="aa2b3-129">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="aa2b3-130">Per modificare il tipo di dati di una colonna</span><span class="sxs-lookup"><span data-stu-id="aa2b3-130">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="aa2b3-131">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa2b3-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa2b3-132">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="aa2b3-133">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="aa2b3-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exy (column_a INT ) ;  
    GO  
    INSERT INTO dbo.doc_exy (column_a) VALUES (10) ;  
    GO  
    ALTER TABLE dbo.doc_exy ALTER COLUMN column_a DECIMAL (5, 2) ;  
    GO  
  
    ```  
  
 <span data-ttu-id="aa2b3-134">Per altre informazioni, vedere [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="aa2b3-134">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
