---
title: Creare viste | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- views [SQL Server], creating
ms.assetid: 0b7bd2a1-544c-42ba-8e7b-4822f34d7b64
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8280f6d65d7252cad423abef849207111492c044
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623972"
---
# <a name="create-views"></a><span data-ttu-id="5cc10-102">Creare viste</span><span class="sxs-lookup"><span data-stu-id="5cc10-102">Create Views</span></span>
  <span data-ttu-id="5cc10-103">È possibile creare viste in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cc10-103">You can create views in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="5cc10-104">Una vista può essere utilizzata per gli scopi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5cc10-104">A view can be used for the following purposes:</span></span>  
  
-   <span data-ttu-id="5cc10-105">Per analizzare, semplificare e personalizzare la visualizzazione del database per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="5cc10-105">To focus, simplify, and customize the perception each user has of the database.</span></span>  
  
-   <span data-ttu-id="5cc10-106">Come meccanismo di sicurezza grazie al quale è possibile consentire agli utenti di accedere ai dati tramite una vista, senza concedere loro le autorizzazioni di accesso alle tabelle di base sottostanti.</span><span class="sxs-lookup"><span data-stu-id="5cc10-106">As a security mechanism by allowing users to access data through the view, without granting the users permissions to directly access the underlying base tables.</span></span>  
  
-   <span data-ttu-id="5cc10-107">Per fornire un'interfaccia compatibile con le versioni precedenti con cui emulare una tabella il cui schema è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="5cc10-107">To provide a backward compatible interface to emulate a table whose schema has changed.</span></span>  
  
 <span data-ttu-id="5cc10-108">**Contenuto dell'articolo**</span><span class="sxs-lookup"><span data-stu-id="5cc10-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5cc10-109">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="5cc10-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5cc10-110">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5cc10-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5cc10-111">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5cc10-111">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5cc10-112">**Per creare una vista tramite:**</span><span class="sxs-lookup"><span data-stu-id="5cc10-112">**To create a view, using:**</span></span>  
  
     [<span data-ttu-id="5cc10-113">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5cc10-113">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="5cc10-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5cc10-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5cc10-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="5cc10-115">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5cc10-116">Limitazioni e restrizioni</span><span class="sxs-lookup"><span data-stu-id="5cc10-116">Limitations and Restrictions</span></span>  
 <span data-ttu-id="5cc10-117">È possibile creare una vista solo nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="5cc10-117">A view can be created only in the current database.</span></span>  
  
 <span data-ttu-id="5cc10-118">Una vista può includere al massimo 1.024 colonne.</span><span class="sxs-lookup"><span data-stu-id="5cc10-118">A view can have a maximum of 1,024 columns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5cc10-119">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="5cc10-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5cc10-120">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5cc10-120">Permissions</span></span>  
 <span data-ttu-id="5cc10-121">Sono richieste l'autorizzazione CREATE VIEW per il database e l'autorizzazione ALTER per lo schema in cui viene creata la vista.</span><span class="sxs-lookup"><span data-stu-id="5cc10-121">Requires CREATE VIEW permission in the database and ALTER permission on the schema in which the view is being created.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5cc10-122">Con SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5cc10-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-view-by-using-the-query-and-view-designer"></a><span data-ttu-id="5cc10-123">Per creare una vista tramite Progettazione query e Progettazione viste</span><span class="sxs-lookup"><span data-stu-id="5cc10-123">To create a view by using the Query and View Designer</span></span>  
  
1.  <span data-ttu-id="5cc10-124">In **Esplora oggetti**espandere il database in cui si desidera creare la nuova vista.</span><span class="sxs-lookup"><span data-stu-id="5cc10-124">In **Object Explorer**, expand the database where you want to create your new view.</span></span>  
  
2.  <span data-ttu-id="5cc10-125">Fare clic con il pulsante destro del mouse sulla cartella **Viste** e quindi selezionare **Nuova vista**.</span><span class="sxs-lookup"><span data-stu-id="5cc10-125">Right-click the **Views** folder, then click **New View...**.</span></span>  
  
3.  <span data-ttu-id="5cc10-126">Nella finestra di dialogo **Aggiungi tabella** selezionare gli elementi che si desidera includere nella nuova vista da una delle schede seguenti: Tabelle, Viste, Funzioni e Sinonimi.</span><span class="sxs-lookup"><span data-stu-id="5cc10-126">In the **Add Table** dialog box, select the element or elements that you want to include in your new view from one of the following tabs: Tables, Views, Functions, and Synonyms.</span></span>  
  
4.  <span data-ttu-id="5cc10-127">Fare clic su **Aggiungi**, quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="5cc10-127">Click **Add**, then click **Close**.</span></span>  
  
5.  <span data-ttu-id="5cc10-128">In **Riquadro diagramma**selezionare le colonne o gli altri elementi da includere nella nuova vista.</span><span class="sxs-lookup"><span data-stu-id="5cc10-128">In the **Diagram Pane**, select the columns or other elements to include in the new view.</span></span>  
  
6.  <span data-ttu-id="5cc10-129">Nel riquadro **Criteri**selezionare criteri di ordinamento o filtro aggiuntivi per le colonne.</span><span class="sxs-lookup"><span data-stu-id="5cc10-129">In the **Criteria Pane**, select additional sort or filter criteria for the columns.</span></span>  
  
7.  <span data-ttu-id="5cc10-130">Nel menu **File** scegliere **Salva**_view name_.</span><span class="sxs-lookup"><span data-stu-id="5cc10-130">On the **File** menu, click **Save**_view name_.</span></span>  
  
8.  <span data-ttu-id="5cc10-131">Nella finestra di dialogo **Scegli nome** immettere un nome per la nuova vista, quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="5cc10-131">In the **Choose Name** dialog box, enter a name for the new view and click **OK**.</span></span>  
  
     <span data-ttu-id="5cc10-132">Per altre informazioni su Progettazione query e Progettazione viste, vedere [Strumenti di progettazione di query e viste &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5cc10-132">For more information about the query and view designer, see [Query and View Designer Tools &#40;Visual Database Tools&#41;](../../ssms/visual-db-tools/visual-database-tools.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="5cc10-133">Con Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="5cc10-133">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-view"></a><span data-ttu-id="5cc10-134">Per creare una vista</span><span class="sxs-lookup"><span data-stu-id="5cc10-134">To create a view</span></span>  
  
1.  <span data-ttu-id="5cc10-135">In **Esplora oggetti**connettersi a un'istanza del [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5cc10-135">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="5cc10-136">Sulla barra Standard fare clic su **Nuova query**.</span><span class="sxs-lookup"><span data-stu-id="5cc10-136">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="5cc10-137">Copiare e incollare l'esempio seguente nella finestra Query, quindi fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="5cc10-137">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012 ;   
    GO  
    CREATE VIEW HumanResources.EmployeeHireDate  
    AS  
    SELECT p.FirstName, p.LastName, e.HireDate  
    FROM HumanResources.Employee AS e JOIN Person.Person AS  p  
    ON e.BusinessEntityID = p.BusinessEntityID ;   
    GO  
    -- Query the view  
    SELECT FirstName, LastName, HireDate  
    FROM HumanResources.EmployeeHireDate  
    ORDER BY LastName;  
  
    ```  
  
 <span data-ttu-id="5cc10-138">Per altre informazioni, vedere [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5cc10-138">For more information, see [CREATE VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-view-transact-sql).</span></span>  
  
  
