---
title: Aggiungere nuovi elementi a un progetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], item additions
- adding project items
ms.assetid: 76af8692-324f-4f5e-b1a0-d72ca8a107e3
author: stevestein
ms.author: sstein
ms.openlocfilehash: c73c58952c7801b3a0e2c86652feb461292cf37c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637539"
---
# <a name="add-new-items-to-a-project"></a><span data-ttu-id="13322-102">Aggiunta di nuovi elementi a un progetto</span><span class="sxs-lookup"><span data-stu-id="13322-102">Add New Items to a Project</span></span>
  <span data-ttu-id="13322-103">È possibile aggiungere nuovi elementi a un progetto per estendere la funzionalità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13322-103">Add new items to a project to extend application functionality.</span></span> <span data-ttu-id="13322-104">Un nuovo elemento può essere una query o una connessione.</span><span class="sxs-lookup"><span data-stu-id="13322-104">A new item can be a query or a connection.</span></span> [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="13322-105">ha due tipi di progetto: progetto script di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e progetto script di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="13322-105">has two project types: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script Project, and Analysis Services Script Project.</span></span> <span data-ttu-id="13322-106">Gli elementi che è possibile aggiungere varieranno a seconda del tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="13322-106">The project type determines the items that you can add to the project.</span></span> <span data-ttu-id="13322-107">È possibile aggiungere, ad esempio, una query [!INCLUDE[tsql](../../includes/tsql-md.md)] (un file con estensione sql) a un progetto script di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , ma non a un progetto script di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="13322-107">For example, you can add a [!INCLUDE[tsql](../../includes/tsql-md.md)] query (a file with a .sql extension) to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Script project, but you cannot add it to an Analysis Services Script Project.</span></span>  
  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="13322-108">non consente di creare cartelle all'interno dei progetti.</span><span class="sxs-lookup"><span data-stu-id="13322-108">does not allow you to create folders within projects.</span></span> <span data-ttu-id="13322-109">Per organizzare il lavoro, creare più progetti all'interno della soluzione.</span><span class="sxs-lookup"><span data-stu-id="13322-109">To organize your work, create multiple projects within the solution.</span></span>  
  
### <a name="to-add-a-new-query-to-an-existing-project"></a><span data-ttu-id="13322-110">Per aggiungere una nuova query a un progetto esistente</span><span class="sxs-lookup"><span data-stu-id="13322-110">To add a new query to an existing project</span></span>  
  
1.  <span data-ttu-id="13322-111">In Esplora soluzioni selezionare un progetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="13322-111">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="13322-112">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="13322-112">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="13322-113">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare una categoria nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="13322-113">In the **Add New Item** dialog box, select a category in the left pane.</span></span>  
  
4.  <span data-ttu-id="13322-114">Selezionare un modello di query nel riquadro destro e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="13322-114">Select a query template in the right pane, and then click **Add**.</span></span> <span data-ttu-id="13322-115">La nuova query verrà aggiunta nella cartella **Query** del progetto.</span><span class="sxs-lookup"><span data-stu-id="13322-115">The new query is added in the **Queries** folder of the project.</span></span>  
  
5.  <span data-ttu-id="13322-116">Nella finestra di dialogo **Connetti al Motore di database** specificare una connessione per la nuova query e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="13322-116">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="13322-117">Se non si vuole associare una connessione alla nuova query, fare clic su **Annulla** nella finestra di dialogo della connessione.</span><span class="sxs-lookup"><span data-stu-id="13322-117">You can click **Cancel** on the connection dialog if you do not want to associate a connection to the new query.</span></span>  
  
6.  <span data-ttu-id="13322-118">Se lo si desidera, rinominare la query in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="13322-118">Rename the query in Solution Explorer if you wish.</span></span>  
  
### <a name="to-add-a-new-connection-to-an-existing-project"></a><span data-ttu-id="13322-119">Per aggiungere una nuova connessione a un progetto esistente</span><span class="sxs-lookup"><span data-stu-id="13322-119">To add a new connection to an existing project</span></span>  
  
1.  <span data-ttu-id="13322-120">In Esplora soluzioni selezionare un progetto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="13322-120">In Solution Explorer, select a target project.</span></span>  
  
2.  <span data-ttu-id="13322-121">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="13322-121">On the **Project** menu, click **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="13322-122">Selezionare **Connessione** nel riquadro sinistro.</span><span class="sxs-lookup"><span data-stu-id="13322-122">Select **Connection** in the left pane.</span></span>  
  
4.  <span data-ttu-id="13322-123">Selezionare **Nuova connessione** nel riquadro destro e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="13322-123">Select **New Connection** in the right pane, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="13322-124">Nella finestra di dialogo **Connetti al Motore di database** specificare una connessione per la nuova query e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="13322-124">In the **Connect to Database Engine** dialog box, specify a connection for the new query, and then click **Connect**.</span></span> <span data-ttu-id="13322-125">La nuova connessione verrà aggiunta nella cartella **Connessioni** del progetto.</span><span class="sxs-lookup"><span data-stu-id="13322-125">The new connection gets added in the **Connections** folder of the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13322-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13322-126">See Also</span></span>  
 <span data-ttu-id="13322-127">[Esplora soluzioni](solution-explorer.md) </span><span class="sxs-lookup"><span data-stu-id="13322-127">[Solution Explorer](solution-explorer.md) </span></span>  
 <span data-ttu-id="13322-128">[Associare estensioni di file a un editor di codice](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span><span class="sxs-lookup"><span data-stu-id="13322-128">[Associate File Extensions to a Code Editor](../../relational-databases/scripting/associate-file-extensions-to-a-code-editor.md) </span></span>  
 <span data-ttu-id="13322-129">[Aggiungere elementi esistenti a un progetto](add-existing-items-to-a-project.md) </span><span class="sxs-lookup"><span data-stu-id="13322-129">[Add Existing Items to a Project](add-existing-items-to-a-project.md) </span></span>  
 [<span data-ttu-id="13322-130">Rimuovere o eliminare un elemento o un progetto</span><span class="sxs-lookup"><span data-stu-id="13322-130">Remove or Delete an Item or Project</span></span>](remove-or-delete-an-item-or-project.md)  
  
  
