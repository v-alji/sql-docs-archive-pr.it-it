---
title: Finestra di dialogo Aggiungi tabella (Progettazione query e Progettazione viste) (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.query.addtable
- vdtsql.chm:65565
ms.assetid: fce7adcc-4cf5-4a52-9203-11c13d1ecf08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8d7bf30cbdd37927735c36f184208a1ded957763
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626460"
---
# <a name="add-table-dialog-box-query-and-view-designers-visual-database-tools"></a><span data-ttu-id="7feb4-102">Finestra di dialogo Aggiungi tabella (Progettazione query e Progettazione viste) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7feb4-102">Add Table Dialog Box (Query and View Designers) (Visual Database Tools)</span></span>
  <span data-ttu-id="7feb4-103">Questa finestra di dialogo consente di aggiungere tabelle, viste, funzioni definite dall'utente o sinonimi a una query o a una vista.</span><span class="sxs-lookup"><span data-stu-id="7feb4-103">This dialog box lets you add tables, views, user-defined functions, or synonyms to a query or view.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7feb4-104">Se la tabella viene pubblicata per la replica, è necessario apportare modifiche allo schema usando l'istruzione [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) di Transact-SQL oppure SMO (SQL Server Management Objects).</span><span class="sxs-lookup"><span data-stu-id="7feb4-104">If the table is published for replication, you must make schema changes using the Transact-SQL statement [ALTER TABLE](/sql/t-sql/statements/alter-table-transact-sql) or SQL Server Management Objects (SMO).</span></span> <span data-ttu-id="7feb4-105">Quando si apportano modifiche allo schema utilizzando Progettazione tabelle o Progettazione diagrammi di database, viene effettuato il tentativo di rimuovere e rigenerare la tabella.</span><span class="sxs-lookup"><span data-stu-id="7feb4-105">When schema changes are made using the Table Designer or the Database Diagram Designer, it attempts to drop and recreate the table.</span></span> <span data-ttu-id="7feb4-106">La modifica allo schema non riuscirà, poiché non è consentita la rimozione di oggetti pubblicati.</span><span class="sxs-lookup"><span data-stu-id="7feb4-106">You cannot drop published objects, therefore the schema change will fail.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7feb4-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="7feb4-107">Options</span></span>  
 <span data-ttu-id="7feb4-108">**Tabelle**</span><span class="sxs-lookup"><span data-stu-id="7feb4-108">**Tables**</span></span>  
 <span data-ttu-id="7feb4-109">Elenca le tabelle che è possibile aggiungere al riquadro **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="7feb4-109">Lists the tables you can add to the **Diagram** pane.</span></span> <span data-ttu-id="7feb4-110">Per aggiungere una tabella, selezionarla e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7feb4-110">To add a table, select it and click **Add**.</span></span> <span data-ttu-id="7feb4-111">Per aggiungere contemporaneamente più tabelle, selezionarle e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7feb4-111">To add several tables at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="7feb4-112">**Visualizzazioni**</span><span class="sxs-lookup"><span data-stu-id="7feb4-112">**Views**</span></span>  
 <span data-ttu-id="7feb4-113">Elenca le viste che è possibile aggiungere al riquadro **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="7feb4-113">Lists the views you can add to the **Diagram** pane.</span></span> <span data-ttu-id="7feb4-114">Per aggiungere una vista, selezionarla e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7feb4-114">To add a view, select it and click **Add**.</span></span> <span data-ttu-id="7feb4-115">Per aggiungere contemporaneamente più viste, selezionarle e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7feb4-115">To add several views at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="7feb4-116">**Funzioni**</span><span class="sxs-lookup"><span data-stu-id="7feb4-116">**Functions**</span></span>  
 <span data-ttu-id="7feb4-117">Elenca le funzioni definite dall'utente che è possibile aggiungere al riquadro **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="7feb4-117">Lists the user-defined functions you can add to the **Diagram** pane.</span></span> <span data-ttu-id="7feb4-118">Per aggiungere una funzione, selezionarla e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7feb4-118">To add a function, select it and click **Add**.</span></span> <span data-ttu-id="7feb4-119">Per aggiungere contemporaneamente più funzioni, selezionarle e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7feb4-119">To add several functions at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="7feb4-120">**Sinonimi**</span><span class="sxs-lookup"><span data-stu-id="7feb4-120">**Synonyms**</span></span>  
 <span data-ttu-id="7feb4-121">Elenca i sinonimi che è possibile aggiungere al riquadro **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="7feb4-121">Lists the synonyms you can add to the **Diagram** pane.</span></span> <span data-ttu-id="7feb4-122">Per aggiungere un sinonimo, selezionarlo e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7feb4-122">To add a synonym, select it and click **Add**.</span></span> <span data-ttu-id="7feb4-123">Per aggiungere contemporaneamente più sinonimi, selezionarli e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7feb4-123">To add several synonyms at once, select them and click **Add**.</span></span>  
  
 <span data-ttu-id="7feb4-124">**Aggiorna**</span><span class="sxs-lookup"><span data-stu-id="7feb4-124">**Refresh**</span></span>  
 <span data-ttu-id="7feb4-125">Aggiorna l'elenco includendo tutte le modifiche apportate al database da quando l'elenco è stato recuperato l'ultima volta.</span><span class="sxs-lookup"><span data-stu-id="7feb4-125">Update the list to include any changes made to the database since the list was last retrieved.</span></span>  
  
 <span data-ttu-id="7feb4-126">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="7feb4-126">**Add**</span></span>  
 <span data-ttu-id="7feb4-127">Aggiunge l'elemento o gli elementi selezionati.</span><span class="sxs-lookup"><span data-stu-id="7feb4-127">Add the selected item or items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7feb4-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7feb4-128">See Also</span></span>  
 [<span data-ttu-id="7feb4-129">Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7feb4-129">Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
