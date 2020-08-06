---
title: Aprire Progettazione query e Progettazione viste (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- opening View Designer
- View Designer, opening
- Query Designer [SQL Server], opening
- opening Query Designer
ms.assetid: b473f258-d53c-41c0-9ad9-528a2ff141f4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3a36a0a9f014759269517a5774167f84c19b0b18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629126"
---
# <a name="open-the-query-and-view-designer-visual-database-tools"></a><span data-ttu-id="9fc53-102">Aprire Progettazione query e Progettazione viste (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="9fc53-102">Open the Query and View Designer (Visual Database Tools)</span></span>
  <span data-ttu-id="9fc53-103">Progettazione query e Progettazione viste viene aperto quando si apre la definizione di una vista, si visualizzano i risultati di una query o di una vista oppure si crea o si apre una query.</span><span class="sxs-lookup"><span data-stu-id="9fc53-103">The Query and View Designer opens when you open the definition of a view, show the results for a query or view, or create or open a query.</span></span> <span data-ttu-id="9fc53-104">È costituito da quattro riquadri separati:</span><span class="sxs-lookup"><span data-stu-id="9fc53-104">It consists of four separate panes:</span></span>  
  
-   <span data-ttu-id="9fc53-105">Il riquadro Diagramma contiene una rappresentazione grafica delle tabelle o degli oggetti con valori di tabella selezionati dalla connessione dati.</span><span class="sxs-lookup"><span data-stu-id="9fc53-105">The Diagram pane presents a graphic display of the tables or table-valued objects you have selected from the data connection.</span></span> <span data-ttu-id="9fc53-106">Mostra inoltre le eventuali relazioni di join da cui sono collegati.</span><span class="sxs-lookup"><span data-stu-id="9fc53-106">It also shows any join relationships among them.</span></span>  
  
-   <span data-ttu-id="9fc53-107">Il riquadro Criteri consente di specificare le opzioni per le query, ad esempio le colonne di dati da visualizzare, come ordinare i risultati e quali righe selezionare, immettendo le proprie scelte in una griglia simile a un foglio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="9fc53-107">The Criteria pane allows you to specify query options - such as which data columns to display, how to order the results, and what rows to select - by entering your choices into a spreadsheet-like grid.</span></span>  
  
-   <span data-ttu-id="9fc53-108">Utilizzando il riquadro SQL è possibile creare un'istruzione SQL personalizzata. Per creare un'istruzione, è anche possibile utilizzare i riquadri Criteri e Diagramma, ma in questo caso le istruzioni SQL verranno comunque create nel riquadro SQL.</span><span class="sxs-lookup"><span data-stu-id="9fc53-108">You can use the SQL pane to create your own SQL statement, or you can use the Criteria pane and Diagram pane to create the statement, in which case the SQL statements will be created in the SQL pane.</span></span> <span data-ttu-id="9fc53-109">Mentre si compila la query, il riquadro SQL viene aggiornato e riformattato automaticamente in modo da semplificarne la lettura.</span><span class="sxs-lookup"><span data-stu-id="9fc53-109">As you build your query, the SQL pane automatically updates and reformats to be easily read.</span></span>  
  
-   <span data-ttu-id="9fc53-110">Nel riquadro Risultati vengono visualizzati i risultati dell'ultima query di selezione (Select) eseguita.</span><span class="sxs-lookup"><span data-stu-id="9fc53-110">The Results pane shows the results of the most recently executed Select query.</span></span> <span data-ttu-id="9fc53-111">I risultati di altri tipi di query vengono visualizzati in finestre di messaggio.</span><span class="sxs-lookup"><span data-stu-id="9fc53-111">(The results of other query types are displayed in message boxes.)</span></span>  
  
-   <span data-ttu-id="9fc53-112">Questi riquadri sono utili mentre si lavora sia nel caso delle query che delle viste.</span><span class="sxs-lookup"><span data-stu-id="9fc53-112">These panes are useful for working with both queries and views.</span></span>  
  
-   <span data-ttu-id="9fc53-113">Quando si apre una vista o una query, vengono aperti anche alcuni o tutti i riquadri,</span><span class="sxs-lookup"><span data-stu-id="9fc53-113">When you open a view or query some or all of the panes open with it.</span></span> <span data-ttu-id="9fc53-114">a seconda delle impostazioni effettuate nella finestra di dialogo **Opzioni** e del sistema di gestione di database a cui si è connessi.</span><span class="sxs-lookup"><span data-stu-id="9fc53-114">Which ones open depend on the settings in the **Options** dialog box and what database management system you're connected to.</span></span> <span data-ttu-id="9fc53-115">Per impostazione predefinita, vengono aperti tutti e quattro i riquadri.</span><span class="sxs-lookup"><span data-stu-id="9fc53-115">The default is that all four open.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-a-view"></a><span data-ttu-id="9fc53-116">Per aprire Progettazione query e Progettazione viste per una vista</span><span class="sxs-lookup"><span data-stu-id="9fc53-116">To open the Query and View Designer for a view</span></span>  
  
1.  <span data-ttu-id="9fc53-117">In Esplora oggetti, fare clic con il pulsante destro del mouse sulla vista da aprire e selezionare **Progetta** o **Apri vista**.</span><span class="sxs-lookup"><span data-stu-id="9fc53-117">In Object Explorer, right-click the view you want to open and click **Design** or **Open View**.</span></span>  
  
     <span data-ttu-id="9fc53-118">Se si sceglie **Progetta**, i riquadri di Progettazione query e Progettazione viste verranno visualizzati in base alle opzioni selezionate nella finestra di dialogo **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="9fc53-118">If you chose **Design**, the Query and View Designer panes open as dictated by the options selected in the **Options** dialog box.</span></span> <span data-ttu-id="9fc53-119">Se invece si sceglie **Apri vista**, per impostazione predefinita verrà visualizzato solo il riquadro Risultati.</span><span class="sxs-lookup"><span data-stu-id="9fc53-119">If you chose **Open View**, only the Results pane opens by default.</span></span>  
  
### <a name="to-open-the-query-and-view-designer-for-an-existing-query"></a><span data-ttu-id="9fc53-120">Per aprire Progettazione query e Progettazione viste per una query esistente</span><span class="sxs-lookup"><span data-stu-id="9fc53-120">To open the Query and View Designer for an existing query</span></span>  
  
1.  <span data-ttu-id="9fc53-121">In Esplora soluzioni espandere la cartella **Query** .</span><span class="sxs-lookup"><span data-stu-id="9fc53-121">In Solution Explorer, expand the **Queries** folder.</span></span>  
  
2.  <span data-ttu-id="9fc53-122">Fare doppio clic sulla query che si desidera aprire.</span><span class="sxs-lookup"><span data-stu-id="9fc53-122">Double-click the query you want to open.</span></span>  
  
3.  <span data-ttu-id="9fc53-123">Evidenziare le istruzioni della query, fare clic con il pulsante destro del mouse sull'area evidenziata e scegliere **Progetta query in Editor**.</span><span class="sxs-lookup"><span data-stu-id="9fc53-123">Highlight the query statement(s), right-click the highlighted area and click **Design Query in Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fc53-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fc53-124">See Also</span></span>  
 <span data-ttu-id="9fc53-125">[Procedure per la progettazione di query e viste &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="9fc53-125">[Design Queries and Views How-to Topics &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="9fc53-126">Strumenti di progettazione di query e viste &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="9fc53-126">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](query-and-view-designer-tools-visual-database-tools.md)  
  
  
