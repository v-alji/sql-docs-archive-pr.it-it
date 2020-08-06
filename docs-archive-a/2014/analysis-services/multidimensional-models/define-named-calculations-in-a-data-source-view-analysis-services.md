---
title: Definire calcoli denominati in una vista origine dati (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying named calculations
- data source views [Analysis Services], named calculations
- named calculations [Analysis Services]
ms.assetid: 729e7b12-6185-4b73-8bcb-cfe459b15355
author: minewiskan
ms.author: owend
ms.openlocfilehash: ae901c340fe29c042430d928a4abaea8e8cfe84b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629085"
---
# <a name="define-named-calculations-in-a-data-source-view-analysis-services"></a><span data-ttu-id="aa466-102">Definire calcoli denominati in una vista origine dati (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="aa466-102">Define Named Calculations in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="aa466-103">Un calcolo denominato è un'espressione SQL rappresentata come colonna calcolata.</span><span class="sxs-lookup"><span data-stu-id="aa466-103">A named calculation is a SQL expression represented as a calculated column.</span></span> <span data-ttu-id="aa466-104">Tale espressione presenta l'aspetto e il comportamento di una colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="aa466-104">This expression appears and behaves as a column in the table.</span></span> <span data-ttu-id="aa466-105">Un calcolo denominato consente di estendere lo schema relazionale delle tabelle o delle viste esistenti in una vista origine dati senza modificare le tabelle o le viste nell'origine dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="aa466-105">A named calculation lets you extend the relational schema of existing tables or views in a data source view without modifying the tables or views in the underlying data source.</span></span> <span data-ttu-id="aa466-106">Considera gli esempi che seguono:</span><span class="sxs-lookup"><span data-stu-id="aa466-106">Consider the following examples:</span></span>

-   <span data-ttu-id="aa466-107">Creare un singolo calcolo denominato derivato da più colonne in una tabella dei fatti, ad esempio moltiplicando un'aliquota di imposta per un prezzo di vendita per ottenere l'ammontare delle imposte.</span><span class="sxs-lookup"><span data-stu-id="aa466-107">Create a single named calculation that is derived from multiple columns in a fact table (for example, creating Tax Amount by multiplying a tax rate by a sales price).</span></span>

-   <span data-ttu-id="aa466-108">Creare un nome descrittivo dell'utente per un membro della dimensione.</span><span class="sxs-lookup"><span data-stu-id="aa466-108">Construct a user friendly name for a dimension member.</span></span>

-   <span data-ttu-id="aa466-109">Come miglioramento delle prestazioni delle query, creare un calcolo denominato nella vista origine dati anziché creare un membro calcolato in un cubo.</span><span class="sxs-lookup"><span data-stu-id="aa466-109">As a query performance enhancement, create a named calculation in the DSV instead of creating a calculated member in a cube.</span></span> <span data-ttu-id="aa466-110">I calcoli denominati vengono calcolati durante l'elaborazione, mentre i membri calcolati vengono calcolati in fase di query.</span><span class="sxs-lookup"><span data-stu-id="aa466-110">Named calculations are calculated during processing whereas calculated members are calculated at query time.</span></span>

## <a name="creating-named-calculations"></a><span data-ttu-id="aa466-111">Creazione di calcoli denominati</span><span class="sxs-lookup"><span data-stu-id="aa466-111">Creating Named Calculations</span></span>

> [!NOTE]
>  <span data-ttu-id="aa466-112">Non è possibile aggiungere un calcolo denominato a una query denominata, né basare una query denominata su una tabella contenente un calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="aa466-112">You cannot add a named calculation to a named query, nor can you base a named query on a table that contains a named calculation.</span></span>

 <span data-ttu-id="aa466-113">Quando si crea un calcolo denominato, è necessario specificare un nome, l'espressione SQL e, facoltativamente, una descrizione del calcolo.</span><span class="sxs-lookup"><span data-stu-id="aa466-113">When you create a named calculation, you specify a name, the SQL expression, and, optionally, a description of the calculation.</span></span> <span data-ttu-id="aa466-114">L'espressione SQL può fare riferimento ad altre tabelle della vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="aa466-114">The SQL expression can refer to other tables in the data source view.</span></span> <span data-ttu-id="aa466-115">Dopo la definizione del nuovo calcolo denominato, l'espressione contenuta all'interno viene inviata al provider dell'origine dei dati e convalidata come istruzione SQL seguente, in cui `<Expression>` contiene l'espressione che definisce il calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="aa466-115">After the named calculation is defined, the expression in a named calculation is sent to the provider for the data source and validated as the following SQL statement in which `<Expression>` contains the expression that defines the named calculation.</span></span>

```
SELECT 
   <Table Name in Data Source>.*, 
   <Expression> AS <Column Name> 
FROM 
   <Table Name in Data Source> AS <Table Name in Data Source View>
```

 <span data-ttu-id="aa466-116">Il tipo di dati della colonna viene determinato in base al tipo di dati del valore scalare restituito dall'espressione.</span><span class="sxs-lookup"><span data-stu-id="aa466-116">The data type of the column is determined by the data type of the scalar value returned by the expression.</span></span> <span data-ttu-id="aa466-117">Se il provider non rileva errori nell'espressione, la colonna viene aggiunta alla tabella.</span><span class="sxs-lookup"><span data-stu-id="aa466-117">If the provider does not find any errors in the expression, the column is added to the table.</span></span>

 <span data-ttu-id="aa466-118">È necessario che le colonne a cui fa riferimento l'espressione non siano qualificate oppure siano qualificate solo in base al nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="aa466-118">Columns referenced in the expression should not be qualified or should be qualified by the table name only.</span></span> <span data-ttu-id="aa466-119">Per fare riferimento alla colonna SaleAmount di una tabella, ad esempio, è possibile utilizzare `SaleAmount` o `Sales.SaleAmount` , mentre `dbo.Sales.SaleAmount` genera un errore.</span><span class="sxs-lookup"><span data-stu-id="aa466-119">For example, to refer to the SaleAmount column in a table, `SaleAmount` or `Sales.SaleAmount` is valid, but `dbo.Sales.SaleAmount` generates an error.</span></span>

 <span data-ttu-id="aa466-120">L'espressione non viene racchiusa automaticamente tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="aa466-120">The expression is not automatically enclosed between parentheses.</span></span> <span data-ttu-id="aa466-121">Se pertanto un'espressione, ad esempio un'istruzione SELECT, richiede le parentesi, è necessario digitarle nella casella **Espressione** .</span><span class="sxs-lookup"><span data-stu-id="aa466-121">Therefore, if an expression, such as a SELECT statement, requires parentheses, you must type the parentheses in the **Expression** box.</span></span> <span data-ttu-id="aa466-122">Ad esempio, l'espressione seguente è valida solo se si digitano le parentesi.</span><span class="sxs-lookup"><span data-stu-id="aa466-122">For example, the following expression is valid only if you type the parentheses.</span></span>

```
(SELECT Description FROM Categories WHERE Categories.CategoryID = CategoryID)
```

## <a name="add-or-edit-a-named-calculation"></a><span data-ttu-id="aa466-123">Aggiungere o modificare un calcolo denominato</span><span class="sxs-lookup"><span data-stu-id="aa466-123">Add or Edit a Named Calculation</span></span>

1.  <span data-ttu-id="aa466-124">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto o connettersi al database contenente la vista origine dati in cui si desidera definire un calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="aa466-124">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to define a named calculation.</span></span>

2.  <span data-ttu-id="aa466-125">In Esplora soluzioni espandere la cartella **Viste origine dati** e quindi fare doppio clic sulla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="aa466-125">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>

3.  <span data-ttu-id="aa466-126">Fare clic con il pulsante destro del mouse sulla tabella in cui si desidera definire il calcolo denominato all'interno del riquadro **Tabelle** o **Diagramma** , quindi scegliere **Nuovo calcolo denominato**.</span><span class="sxs-lookup"><span data-stu-id="aa466-126">Right-click the table in which you wish to define the named calculation in either the **Tables** or the **Diagram** pane, and then click **New Named Calculation**.</span></span> <span data-ttu-id="aa466-127">Assicurarsi di fare clic con il pulsante destro del mouse sul nome della tabella e non su un attributo.</span><span class="sxs-lookup"><span data-stu-id="aa466-127">Be sure to right-click on the table name, and not on an attribute.</span></span> <span data-ttu-id="aa466-128">Il menu sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="aa466-128">The menu should look like the following:</span></span>

     <span data-ttu-id="aa466-129">![Schermata dell'area di lavoro del diagramma, menu di scelta rapida](../media/ssas-olapdsv-diagram.gif "Schermata dell'area di lavoro del diagramma, menu di scelta rapida")</span><span class="sxs-lookup"><span data-stu-id="aa466-129">![Screenshot of diagram workspace, right-click menu](../media/ssas-olapdsv-diagram.gif "Screenshot of diagram workspace, right-click menu")</span></span>

    > [!NOTE]
    >  <span data-ttu-id="aa466-130">Per individuare una tabella o una vista, è possibile usare l'opzione **Trova tabella** scegliendola dal menu **Vista origine dati** o facendo clic con il pulsante destro del mouse su un'area vuota nei riquadri **Tabelle** o **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="aa466-130">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>

4.  <span data-ttu-id="aa466-131">Nella finestra di dialogo **Create Named Calculations (Crea calcolo denominato)** effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa466-131">In the **Create Named Calculations** dialog box, do the following:</span></span>

    -   <span data-ttu-id="aa466-132">Nella casella di testo **Nome colonna** digitare il nome della nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="aa466-132">In the **Column name** text box, type the name of the new column.</span></span>

    -   <span data-ttu-id="aa466-133">Nella casella di testo **Descrizione** digitare una descrizione per la nuova colonna.</span><span class="sxs-lookup"><span data-stu-id="aa466-133">In the **Description** text box type a description for the new column.</span></span>

    -   <span data-ttu-id="aa466-134">Nella casella di testo **Espressione** digitare l'espressione che restituisce il contenuto della nuova colonna nel sottolinguaggio SQL appropriato per il provider di dati.</span><span class="sxs-lookup"><span data-stu-id="aa466-134">In the **Expression** text box, type the expression that yields the content of the new column in the SQL dialect appropriate for the data provider.</span></span>

5.  <span data-ttu-id="aa466-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa466-135">Click **OK**.</span></span>

     <span data-ttu-id="aa466-136">La colonna del calcolo denominato viene visualizzata come ultima colonna nella tabella della vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="aa466-136">The named calculation column appears as the last column in the data source view table.</span></span> <span data-ttu-id="aa466-137">L'icona della calcolatrice indica che nella colonna è contenuto un calcolo denominato.</span><span class="sxs-lookup"><span data-stu-id="aa466-137">A calculator symbol indicates that the column contains a named calculation.</span></span>

## <a name="delete-a-named-calculation"></a><span data-ttu-id="aa466-138">Eliminare un calcolo denominato</span><span class="sxs-lookup"><span data-stu-id="aa466-138">Delete a Named Calculation</span></span>
 <span data-ttu-id="aa466-139">Quando si tenta di eliminare un calcolo denominato, viene visualizzato un elenco degli oggetti definiti nel progetto o nel database che verranno invalidati dall'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="aa466-139">When you attempt to delete a named calculation, you are prompted with a list of the objects defined in the project or database that will be invalidated by the deletion.</span></span> <span data-ttu-id="aa466-140">Esaminare attentamente l'elenco prima di eliminare il calcolo.</span><span class="sxs-lookup"><span data-stu-id="aa466-140">Review the list carefully before deleting the calculation.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa466-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa466-141">See Also</span></span>
 [<span data-ttu-id="aa466-142">Definire query denominate in una vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="aa466-142">Define Named Queries in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-queries-in-a-data-source-view-analysis-services.md)


