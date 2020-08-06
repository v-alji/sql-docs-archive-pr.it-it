---
title: Rinominare viste | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], renaming
- renaming views
ms.assetid: 5eed0488-81d2-40e8-8fdf-b0a640a591d0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5cc76ced033a69788270c3fa9277bcca6972e080
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713000"
---
# <a name="rename-views"></a><span data-ttu-id="4935c-102">Rinominare viste</span><span class="sxs-lookup"><span data-stu-id="4935c-102">Rename Views</span></span>
  <span data-ttu-id="4935c-103">È possibile rinominare una vista in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4935c-103">You can rename a view in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="4935c-104">Se si rinomina una vista, è possibile che smettano di funzionare il codice e le applicazioni che dipendono da essa,</span><span class="sxs-lookup"><span data-stu-id="4935c-104">If you rename a view, code and applications that depend on the view may fail.</span></span> <span data-ttu-id="4935c-105">incluse altre viste, query, stored procedure, funzioni definite dall'utente e applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="4935c-105">These include other views, queries, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="4935c-106">Tali errori inoltre tendono a propagarsi a cascata.</span><span class="sxs-lookup"><span data-stu-id="4935c-106">Note that these failures will cascade.</span></span>  
  
 <span data-ttu-id="4935c-107">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="4935c-107">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4935c-108">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="4935c-108">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4935c-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4935c-109">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="4935c-110">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4935c-110">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4935c-111">**Per rinominare una vista usando:**</span><span class="sxs-lookup"><span data-stu-id="4935c-111">**To rename a view, using:**</span></span>  
  
     [<span data-ttu-id="4935c-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4935c-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4935c-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4935c-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
-   <span data-ttu-id="4935c-114">**Completamento:**  [dopo che una vista è stata rinominata](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="4935c-114">**Follow Up:**  [After renaming a view](#FollowUp)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4935c-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4935c-115">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="4935c-116">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4935c-116">Prerequisites</span></span>  
 <span data-ttu-id="4935c-117">Ottenere un elenco di tutte le dipendenze dalla vista.</span><span class="sxs-lookup"><span data-stu-id="4935c-117">Obtain a list of all dependencies on the view.</span></span> <span data-ttu-id="4935c-118">È necessario modificare qualsiasi oggetto, script o applicazione che fa riferimento alla vista per riflettere il nuovo nome di quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="4935c-118">Any objects, scripts or applications that reference the view must be modified to reflect the new name of the view.</span></span> <span data-ttu-id="4935c-119">Per altre informazioni, vedere [Get Information About a View](get-information-about-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="4935c-119">For more information, see [Get Information About a View](get-information-about-a-view.md).</span></span> <span data-ttu-id="4935c-120">Si consiglia di eliminare la vista e di ricrearla con un nuovo nome anziché rinominarla.</span><span class="sxs-lookup"><span data-stu-id="4935c-120">We recommend that you drop the view and recreate it with a new name instead of renaming the view.</span></span> <span data-ttu-id="4935c-121">Se si ricrea la vista, si aggiornano le informazioni sulle dipendenze per gli oggetti a cui viene fatto riferimento nella vista.</span><span class="sxs-lookup"><span data-stu-id="4935c-121">By recreating the view, you update the dependency information for the objects that are referenced in the view.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4935c-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="4935c-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4935c-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="4935c-123">Permissions</span></span>  
 <span data-ttu-id="4935c-124">Sono richieste l'autorizzazione ALTER per SCHEMA o CONTROL per OBJECT e l'autorizzazione CREATE VIEW per il database.</span><span class="sxs-lookup"><span data-stu-id="4935c-124">Requires ALTER permission on SCHEMA or CONTROL permission on OBJECT is required, and CREATE VIEW permission in the database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4935c-125">Utilizzo di SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4935c-125">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-rename-a-view"></a><span data-ttu-id="4935c-126">Per rinominare una vista</span><span class="sxs-lookup"><span data-stu-id="4935c-126">To rename a view</span></span>  
  
1.  <span data-ttu-id="4935c-127">In **Esplora oggetti**espandere il database contenente la vista da rinominare, quindi espandere la cartella **Vista** .</span><span class="sxs-lookup"><span data-stu-id="4935c-127">In **Object Explorer**, expand the database that contains the view you wish to rename and then expand the **View** folder.</span></span>  
  
2.  <span data-ttu-id="4935c-128">Fare clic con il pulsante destro del mouse sulla vista da rinominare e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="4935c-128">Right-click the view you wish to rename and select **Rename**.</span></span>  
  
3.  <span data-ttu-id="4935c-129">Immettere il nuovo nome della vista.</span><span class="sxs-lookup"><span data-stu-id="4935c-129">Enter the view's new name.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4935c-130">Uso di Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4935c-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="4935c-131">**Per rinominare una vista**</span><span class="sxs-lookup"><span data-stu-id="4935c-131">**To rename a view**</span></span>  
  
 <span data-ttu-id="4935c-132">Nonostante sia possibile usare **sp_rename** per modificare il nome della vista, si consiglia di eliminare quella esistente e di ricrearla con il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="4935c-132">While you can use **sp_rename** to change the name of the view, we recommend that you delete the existing view and then re-create it with the new name.</span></span>  
  
 <span data-ttu-id="4935c-133">Per altre informazioni, vedere [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) e [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4935c-133">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql) and [DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql).</span></span>  
  
##  <a name="follow-up-after-renaming-a-view"></a><a name="FollowUp"></a> <span data-ttu-id="4935c-134">Completamento: dopo che una vista è stata rinominata</span><span class="sxs-lookup"><span data-stu-id="4935c-134">Follow Up: After Renaming a View</span></span>  
 <span data-ttu-id="4935c-135">Assicurarsi che tutti gli oggetti, gli script e le applicazioni che fanno riferimento al nome precedente della vista usino ora il nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="4935c-135">Ensure that all objects, scripts, and applications that reference the view's old name now use the new name.</span></span>  
  
  
