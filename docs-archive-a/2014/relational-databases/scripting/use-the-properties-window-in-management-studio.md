---
title: Utilizzo della finestra Proprietà in Management Studio
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- viewing properties
- Properties window [SQL Server Management Studio]
- complex properties [SQL Server Management Studio]
ms.assetid: 903d4aca-f57c-43d9-a893-702eceaa7004
author: rothja
ms.author: jroth
ms.openlocfilehash: 5030bf85fc87482b11e91967ff8fb1baf77a213e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637209"
---
# <a name="use-the-properties-window-in-management-studio"></a><span data-ttu-id="a7163-102">Utilizzo della finestra Proprietà in Management Studio</span><span class="sxs-lookup"><span data-stu-id="a7163-102">Use the Properties Window in Management Studio</span></span>
  <span data-ttu-id="a7163-103">Nella finestra Proprietà è indicato lo stato di un elemento in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], ad esempio una connessione o un operatore Showplan, e vengono riportate informazioni su oggetti di database come ad esempio tabelle, visualizzazioni e finestre di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a7163-103">The Properties window describes the state of an item in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], such as a connection or a Showplan operator, and information about database objects such as tables, views, and designers.</span></span>  
  
 <span data-ttu-id="a7163-104">È possibile utilizzare la finestra Proprietà per visualizzare le proprietà della connessione corrente.</span><span class="sxs-lookup"><span data-stu-id="a7163-104">You can use the Properties window to view the properties of the current connection.</span></span> <span data-ttu-id="a7163-105">In questa finestra molte proprietà solo di sola lettura ma è possibile modificarle altrove in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7163-105">Many properties are read-only in the Properties window but can be changed elsewhere in the [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="a7163-106">La proprietà Database di una query, ad esempio, è di sola lettura nella finestra Proprietà ma può essere modificata sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="a7163-106">For example, the Database property of a query is read-only in the Properties window, but can be changed on the tool bar.</span></span>  
  
### <a name="to-view-properties-using-the-properties-window"></a><span data-ttu-id="a7163-107">Per visualizzare le proprietà utilizzando la finestra Proprietà</span><span class="sxs-lookup"><span data-stu-id="a7163-107">To view properties using the Properties window</span></span>  
  
1.  <span data-ttu-id="a7163-108">Se la finestra Proprietà non è visibile, scegliere **Finestra Proprietà** dal menu **Visualizza** oppure premere F4.</span><span class="sxs-lookup"><span data-stu-id="a7163-108">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="a7163-109">Impostare lo stato attivo sull'oggetto che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a7163-109">Set the focus on the object that you want to view.</span></span>  
  
3.  <span data-ttu-id="a7163-110">Cercare una proprietà specifica nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a7163-110">Look for a specific property in the Properties window.</span></span>  
  
### <a name="to-view-connection-properties-of-a-query-window"></a><span data-ttu-id="a7163-111">Per visualizzare le proprietà di connessione di una finestra di query</span><span class="sxs-lookup"><span data-stu-id="a7163-111">To view connection properties of a query window</span></span>  
  
1.  <span data-ttu-id="a7163-112">Se la finestra Proprietà non è visibile, scegliere **Finestra Proprietà** dal menu **Visualizza** oppure premere F4.</span><span class="sxs-lookup"><span data-stu-id="a7163-112">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
2.  <span data-ttu-id="a7163-113">Nella finestra Proprietà è possibile vedere tutte le proprietà di connessione.</span><span class="sxs-lookup"><span data-stu-id="a7163-113">In the Properties window, you can see all the connection properties.</span></span>  
  
### <a name="to-view-the-properties-of-a-showplan-operator"></a><span data-ttu-id="a7163-114">Per visualizzare le proprietà di un operatore Showplan</span><span class="sxs-lookup"><span data-stu-id="a7163-114">To view the properties of a Showplan operator</span></span>  
  
1.  <span data-ttu-id="a7163-115">Scegliere **Includi piano di esecuzione effettivo** dal menu **Query**.</span><span class="sxs-lookup"><span data-stu-id="a7163-115">On the **Query** menu, click **Include Actual Execution Plan**.</span></span>  
  
2.  <span data-ttu-id="a7163-116">Nell'editor di query SQL digitare ed eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="a7163-116">In the SQL Query Editor, type and execute a query.</span></span>  
  
3.  <span data-ttu-id="a7163-117">Se la finestra Proprietà non è visibile, scegliere **Finestra Proprietà** dal menu **Visualizza** oppure premere F4.</span><span class="sxs-lookup"><span data-stu-id="a7163-117">If the Properties window is not visible, click **Properties Window** on the **View** menu, or press F4.</span></span>  
  
4.  <span data-ttu-id="a7163-118">Nella scheda **Piano di esecuzione** dell'editor di query SQL fare clic sulle icone degli operatori per visualizzare informazioni sugli operatori nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="a7163-118">On the **Execution plan** tab of the SQL Query Editor click the icons of the operators to view information about the operators in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7163-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7163-119">See Also</span></span>  
 [<span data-ttu-id="a7163-120">Finestra Proprietà &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a7163-120">Properties Window &#40;Management Studio&#41;</span></span>](../../ssms/properties-window-management-studio.md)  
  
  
