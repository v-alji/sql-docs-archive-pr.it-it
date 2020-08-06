---
title: Sostituire una tabella o una query denominata in una vista origine dati (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- replacing tables
- data source views [Analysis Services], tables
- named queries [Analysis Services], replacing tables
- tables [Analysis Services], data source views
- partitions [Analysis Services], named queries
ms.assetid: 60c2a018-1299-4915-b60e-e73316524def
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b5055de60ba757c9dcfa118e4e2c4748c6534e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630109"
---
# <a name="replace-a-table-or-a-named-query-in-a-data-source-view-analysis-services"></a><span data-ttu-id="d1e62-102">Sostituire una tabella o una query denominata in una vista origine dati (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="d1e62-102">Replace a Table or a Named Query in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="d1e62-103">In Progettazione vista origine dati è possibile sostituire una tabella, una vista o una query denominata di una vista origine dati con una tabella o una vista diversa della stessa origine dati o di un'origine diversa oppure con una query denominata definita nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="d1e62-103">In Data Source View Designer, you can replace a table, view, or named query in a data source view (DSV) with a different table or view from the same or a different data source, or with a named query defined in the DSV.</span></span> <span data-ttu-id="d1e62-104">Quando si sostituisce una tabella, vengono mantenuti i relativi riferimenti eventualmente contenuti in tutti gli altri oggetti di un database o un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , in quanto l'ID oggetto per la tabella della vista origine dati rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="d1e62-104">When you replace a table, all other objects in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project that have references to the table continue to reference the table because the object ID for the table in the DSV does not change.</span></span> <span data-ttu-id="d1e62-105">Vengono mantenute anche le relazioni che sono ancora rilevanti, basate sulla corrispondenza tra nome e tipo di colonna.</span><span class="sxs-lookup"><span data-stu-id="d1e62-105">Any relationships that are still relevant (based on name and column-type matching) are retained.</span></span> <span data-ttu-id="d1e62-106">Se invece si elimina e quindi si aggiunge una tabella, i riferimenti e le relazioni vengono persi e devono essere ricreati.</span><span class="sxs-lookup"><span data-stu-id="d1e62-106">In contrast, if you delete and then add a table, references and relationships are lost and must be recreated.</span></span>  
  
 <span data-ttu-id="d1e62-107">Per sostituire una tabella con un'altra tabella, è necessario disporre di una connessione attiva all'origine dei dati in Progettazione vista origine dati in modalità progetto.</span><span class="sxs-lookup"><span data-stu-id="d1e62-107">To replace a table with another table, you must have an active connection to the source data in Data Source View Designer in project mode.</span></span>  
  
 <span data-ttu-id="d1e62-108">In genere, si sostituisce una tabella della vista origine dati con un'altra tabella dell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="d1e62-108">You most frequently replace a table in the data source view with another table in the data source.</span></span> <span data-ttu-id="d1e62-109">È tuttavia possibile sostituire anche una query denominata con una tabella.</span><span class="sxs-lookup"><span data-stu-id="d1e62-109">However, you can also replace a named query with a table.</span></span> <span data-ttu-id="d1e62-110">Si supponga ad esempio di aver sostituito in precedenza una tabella con una query denominata che ora si desidera riconvertire in tabella.</span><span class="sxs-lookup"><span data-stu-id="d1e62-110">For example, you previously replaced a table with a named query, and now want to revert to a table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d1e62-111">Se si rinomina una tabella in un'origine dati, è necessario seguire la procedura per la sostituzione di una tabella e specificare la tabella rinominata come origine della tabella corrispondente nella vista origine dati prima di aggiornare la vista.</span><span class="sxs-lookup"><span data-stu-id="d1e62-111">If you rename a table in a data source, follow the steps for replacing a table and specify the renamed table as the source of the corresponding table in the DSV before you refresh a DSV.</span></span> <span data-ttu-id="d1e62-112">Se si completa la sostituzione e si rinomina il processo, verranno mantenuti sia la tabella sia i riferimenti e le relazioni corrispondenti nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="d1e62-112">Completing the replacement and renaming process preserves the table, the table's references, and the table's relationships in the DSV.</span></span> <span data-ttu-id="d1e62-113">In caso contrario, quando si aggiorna la vista origine dati, una tabella rinominata nell'origine dati verrà considerata come un elemento da eliminare.</span><span class="sxs-lookup"><span data-stu-id="d1e62-113">Otherwise, when you refresh the DSV, a renamed table in data source is interpreted as being deleted.</span></span> <span data-ttu-id="d1e62-114">Per altre informazioni, vedere [Aggiornare lo schema in una vista origine dati &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d1e62-114">For more information, see [Refresh the Schema in a Data Source View &#40;Analysis Services&#41;](refresh-the-schema-in-a-data-source-view-analysis-services.md).</span></span>  
  
##  <a name="replace-a-table-with-a-named-query"></a><a name="bkmk_nq"></a> <span data-ttu-id="d1e62-115">Sostituire una tabella con una query denominata</span><span class="sxs-lookup"><span data-stu-id="d1e62-115">Replace a table with a named query</span></span>  
  
1.  <span data-ttu-id="d1e62-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto o connettersi al database contenente la vista origine dati in cui si vuole sostituire una tabella o una query denominata.</span><span class="sxs-lookup"><span data-stu-id="d1e62-116">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="d1e62-117">In Esplora soluzioni espandere la cartella **Viste origine dati** e quindi fare doppio clic sulla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="d1e62-117">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="d1e62-118">Aprire la finestra di dialogo **Crea query denominata** .</span><span class="sxs-lookup"><span data-stu-id="d1e62-118">Open the **Create Named Query** dialog box.</span></span> <span data-ttu-id="d1e62-119">Nel riquadro **Tabelle** o **Diagramma** fare clic con il pulsante destro del mouse sulla tabella da sostituire, scegliere **Sostituisci tabella** e quindi fare clic su **Con nuova query denominata**.</span><span class="sxs-lookup"><span data-stu-id="d1e62-119">In either **Tables** or **Diagram** pane, right-click the table that you wish to replace, point to **Replace Table** and then click **With New Named Query**.</span></span>  
  
4.  <span data-ttu-id="d1e62-120">Nella finestra di dialogo **Crea query denominata** definire la query denominata e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1e62-120">In the **Create Named Query** dialog box, define the named query and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="d1e62-121">Salvare la vista origine dati modificata.</span><span class="sxs-lookup"><span data-stu-id="d1e62-121">Save the modified data source view.</span></span>  
  
## <a name="replace-a-table-or-named-query-with-a-table"></a><span data-ttu-id="d1e62-122">Sostituire una tabella o una query denominata con una tabella</span><span class="sxs-lookup"><span data-stu-id="d1e62-122">Replace a table or named query with a table</span></span>  
  
1.  <span data-ttu-id="d1e62-123">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto o connettersi al database contenente la vista origine dati in cui si vuole sostituire una tabella o una query denominata.</span><span class="sxs-lookup"><span data-stu-id="d1e62-123">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you want to replace a table or a named query.</span></span>  
  
2.  <span data-ttu-id="d1e62-124">In Esplora soluzioni espandere la cartella **Viste origine dati** e quindi fare doppio clic sulla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="d1e62-124">In Solution Explorer, expand the **Data Source Views** folder, and then double-click the data source view.</span></span>  
  
3.  <span data-ttu-id="d1e62-125">Aprire la finestra di dialogo **Sostituisci tabella con un'altra tabella** .</span><span class="sxs-lookup"><span data-stu-id="d1e62-125">Open the **Replace Table with Other Table** dialog box.</span></span> <span data-ttu-id="d1e62-126">Nel riquadro **Tabelle** o **Diagramma** fare clic con il pulsante destro del mouse sulla tabella o sulla query denominata da sostituire, scegliere **Sostituisci tabella** e quindi fare clic su **Con altra tabella**.</span><span class="sxs-lookup"><span data-stu-id="d1e62-126">In either **Tables** or **Diagram** pane, right-click the table or named query that you wish to replace, point to **Replace Table** and then click **With Other Table**.</span></span>  
  
4.  <span data-ttu-id="d1e62-127">Nella finestra di dialogo **Sostituisci tabella con un'altra tabella** :</span><span class="sxs-lookup"><span data-stu-id="d1e62-127">In the **Replace Table with Other Table** dialog box:</span></span>  
  
    1.  <span data-ttu-id="d1e62-128">Nell'elenco a discesa **Origine dati** selezionare l'origine dati desiderata.</span><span class="sxs-lookup"><span data-stu-id="d1e62-128">In the **DataSource** drop-down list box, select the desired data source</span></span>  
  
    2.  <span data-ttu-id="d1e62-129">Selezionare la tabella con cui si desidera sostituire la tabella o la query denominata.</span><span class="sxs-lookup"><span data-stu-id="d1e62-129">Select the table with which you wish to replace the table or named query</span></span>  
  
5.  <span data-ttu-id="d1e62-130">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1e62-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d1e62-131">Salvare la vista origine dati modificata.</span><span class="sxs-lookup"><span data-stu-id="d1e62-131">Save the modified data source view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1e62-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1e62-132">See Also</span></span>  
 [<span data-ttu-id="d1e62-133">Viste origine dati in modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="d1e62-133">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
