---
title: Visualizzare o modificare il livello di compatibilità di un database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- compatibility levels [SQL Server], viewing
- compatibility [SQL Server], databases
- compatibility levels [SQL Server], changing
ms.assetid: 579867ec-57cb-4cb8-af35-9688c1e9e15d
author: stevestein
ms.author: sstein
ms.openlocfilehash: 35cf7af50eba333440c42a1bac428df1fff156b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724760"
---
# <a name="view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="c22c7-102">Visualizzare o modificare il livello di compatibilità di un database</span><span class="sxs-lookup"><span data-stu-id="c22c7-102">View or Change the Compatibility Level of a Database</span></span>
  <span data-ttu-id="c22c7-103">In questo argomento si illustra come visualizzare o modificare il livello di compatibilità di un database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c22c7-103">This topic describes how to view or change the compatibility level of a database in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c22c7-104">Prima di modificare il livello di compatibilità di un database, è importante comprendere quale impatto avrà la modifica sulle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c22c7-104">Before you change the compatibility level of a database, you should understand the impact of the change on your applications.</span></span> <span data-ttu-id="c22c7-105">Per altre informazioni, vedere [Livello di compatibilità ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span><span class="sxs-lookup"><span data-stu-id="c22c7-105">For more information, see [ALTER DATABASE Compatibility Level &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-compatibility-level).</span></span>  
  
 <span data-ttu-id="c22c7-106">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="c22c7-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c22c7-107">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="c22c7-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c22c7-108">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c22c7-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c22c7-109">**Per visualizzare o modificare il livello di compatibilità di un database utilizzando:**</span><span class="sxs-lookup"><span data-stu-id="c22c7-109">**To view or change the compatibility level of a database, using:**</span></span>  
  
     [<span data-ttu-id="c22c7-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c22c7-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c22c7-111">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c22c7-111">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c22c7-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c22c7-112">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c22c7-113">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="c22c7-113">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c22c7-114">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c22c7-114">Permissions</span></span>  
 <span data-ttu-id="c22c7-115">È richiesta l'autorizzazione ALTER per il database.</span><span class="sxs-lookup"><span data-stu-id="c22c7-115">Requires ALTER permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c22c7-116">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c22c7-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="c22c7-117">Per visualizzare o modificare il livello di compatibilità di un database</span><span class="sxs-lookup"><span data-stu-id="c22c7-117">To view or change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="c22c7-118">Dopo essersi connessi all'istanza appropriata del [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Esplora oggetti fare clic sul nome del server.</span><span class="sxs-lookup"><span data-stu-id="c22c7-118">After connecting to the appropriate instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], in Object Explorer, click the server name.</span></span>  
  
2.  <span data-ttu-id="c22c7-119">Espandere **Database**e, a seconda del database, selezionare un database utente o espandere **Database di sistema** e selezionare un database di sistema.</span><span class="sxs-lookup"><span data-stu-id="c22c7-119">Expand **Databases**, and, depending on the database, either select a user database or expand **System Databases** and select a system database.</span></span>  
  
3.  <span data-ttu-id="c22c7-120">Fare clic con il pulsante destro del mouse sul database, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="c22c7-120">Right-click the database, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="c22c7-121">Verrà visualizzata la finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="c22c7-121">The **Database Properties** dialog box opens.</span></span>  
  
4.  <span data-ttu-id="c22c7-122">Nel riquadro **Selezione pagina** fare clic su **Opzioni**.</span><span class="sxs-lookup"><span data-stu-id="c22c7-122">In the **Select a page** pane, click **Options**.</span></span>  
  
     <span data-ttu-id="c22c7-123">Il livello di compatibilità corrente viene visualizzato nella casella di riepilogo **Livello di compatibilità** .</span><span class="sxs-lookup"><span data-stu-id="c22c7-123">The current compatibility level is displayed in the **Compatibility level** list box.</span></span>  
  
5.  <span data-ttu-id="c22c7-124">Per modificare il livello di compatibilità, selezionare un'opzione diversa dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="c22c7-124">To change the compatibility level, select a different option from the list.</span></span> <span data-ttu-id="c22c7-125">Scegliere tra **SQL Server 2008 (100)**, **SQL Server 2012 (110)** o **SQL Server 2014 (120)**.</span><span class="sxs-lookup"><span data-stu-id="c22c7-125">The choices are **SQL Server 2008 (100)**, **SQL Server 2012 (110)**, or **SQL Server 2014 (120)**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c22c7-126">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c22c7-126">Using Transact-SQL</span></span>  
  
#### <a name="to-view-the-compatibility-level-of-a-database"></a><span data-ttu-id="c22c7-127">Per visualizzare il livello di compatibilità di un database</span><span class="sxs-lookup"><span data-stu-id="c22c7-127">To view the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="c22c7-128">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c22c7-128">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c22c7-129">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c22c7-129">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c22c7-130">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c22c7-130">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c22c7-131">In questo esempio viene restituito il livello di compatibilità del database [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c22c7-131">This example returns the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```sql  
USE AdventureWorks2012;  
GO  
SELECT compatibility_level  
FROM sys.databases WHERE name = 'AdventureWorks2012';  
GO  
  
```  
  
#### <a name="to-change-the-compatibility-level-of-a-database"></a><span data-ttu-id="c22c7-132">Per modificare il livello di compatibilità di un database</span><span class="sxs-lookup"><span data-stu-id="c22c7-132">To change the compatibility level of a database</span></span>  
  
1.  <span data-ttu-id="c22c7-133">Connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c22c7-133">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c22c7-134">Dalla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="c22c7-134">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c22c7-135">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c22c7-135">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="c22c7-136">In questo esempio viene modificato il livello di compatibilità di [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c22c7-136">This example changes the compatibility level of the [!INCLUDE[ssSampleDBobject](../../includes/sssql14-md.md)].</span></span>  
  
```sql  
ALTER DATABASE AdventureWorks2012  
SET COMPATIBILITY_LEVEL = 120;  
GO  
```  
  
  
