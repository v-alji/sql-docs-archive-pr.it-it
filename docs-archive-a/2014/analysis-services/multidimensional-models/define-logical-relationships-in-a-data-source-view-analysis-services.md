---
title: Definire relazioni logiche in una vista origine dati (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- adding relationships
- relationships [Analysis Services], data source views
- data source views [Analysis Services], relationships
ms.assetid: a20d6dae-e769-4131-8a59-7ef56f174220
author: minewiskan
ms.author: owend
ms.openlocfilehash: c46c2b360a4528aeb0eb88348d0d1242b22d8ef5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629090"
---
# <a name="define-logical-relationships-in-a-data-source-view-analysis-services"></a><span data-ttu-id="8c0a8-102">Definire relazioni logiche in una vista origine dati (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="8c0a8-102">Define Logical Relationships in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="8c0a8-103">Creazione guidata vista origine dati e Progettazione vista origine dati consentono di definire automaticamente le relazioni tra le tabelle aggiunte a una vista origine dati, in base alle relazioni di database sottostanti o ai criteri di corrispondenza nomi specificati.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-103">The Data Source View Wizard and Data Source View Designer automatically define relationships between tables added to a data source view (DSV) based on underlying database relationships or name matching criteria you specify.</span></span>  
  
 <span data-ttu-id="8c0a8-104">Nei casi in cui si utilizzano dati da più origini dati, può essere necessario definire manualmente le relazioni logiche nella vista origine dati per integrare le relazioni definite automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-104">In cases where you are working with data from multiple data sources, you may need to manually define logical relationships in the DSV to supplement those relationships that are defined automatically.</span></span> <span data-ttu-id="8c0a8-105">In [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] le relazioni sono necessarie per identificare le tabelle dei fatti e delle dimensioni, per costruire query per il recupero di dati e metadati dalle origini dati sottostanti, nonché per sfruttare i vantaggi delle funzionalità avanzate di Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-105">Relationships are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to identify fact and dimension tables, to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="8c0a8-106">In Progettazione vista origine dati è possibile definire i tipi di relazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c0a8-106">You can define the following types of relationships in Data Source View Designer:</span></span>  
  
-   <span data-ttu-id="8c0a8-107">Una relazione tra due tabelle nella stessa origine dei dati</span><span class="sxs-lookup"><span data-stu-id="8c0a8-107">A relationship from one table to another table in the same data source.</span></span>  
  
-   <span data-ttu-id="8c0a8-108">Una relazione tra una tabella e se stessa, come in una relazione padre figlio</span><span class="sxs-lookup"><span data-stu-id="8c0a8-108">A relationship from one table to itself, as in a parent-child relationship.</span></span>  
  
-   <span data-ttu-id="8c0a8-109">Una relazione tra una tabella di un'origine dei dati e un'altra tabella di un'origine dati diversa.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-109">A relationship from one table in a data source to another table in a different data source.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8c0a8-110">Le relazioni definite in una vista origine dati sono logiche e potrebbero non riflettere le relazioni effettive definite nell'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-110">The relationships defined in a DSV are logical and may not reflect the actual relationships defined in the underlying data source.</span></span> <span data-ttu-id="8c0a8-111">In Progettazione vista origine dati è possibile creare relazioni che non esistono nell'origine dei dati sottostante e rimuovere le relazioni create tramite Progettazione vista origine dati dalle relazioni di chiave esterna esistenti nell'origine dei dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-111">You can create relationships in Data Source View Designer that do not exist in the underlying data source, and remove relationships created by Data Source View Designer from existing foreign key relationships in the underlying data source.</span></span>  
  
 <span data-ttu-id="8c0a8-112">Le relazioni hanno una direzione.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-112">Relationships are directed.</span></span> <span data-ttu-id="8c0a8-113">Per ogni valore nella colonna di origine esiste un valore corrispondente nella colonna di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-113">For every value in the source column, there is a corresponding value in the destination column.</span></span> <span data-ttu-id="8c0a8-114">In un diagramma vista origine dati, ad esempio nei diagrammi visualizzati nel riquadro **Diagramma** , una freccia sulla linea tra due tabelle indica la direzione della relazione.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-114">In a data source view diagram, such as the diagrams displayed in the **Diagram** pane, an arrow on the line between two tables indicates the direction of the relationship.</span></span>  
  
 <span data-ttu-id="8c0a8-115">Questo argomento include le sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c0a8-115">This topic includes the following sections:</span></span>  
  
 [<span data-ttu-id="8c0a8-116">Per aggiungere una relazione tra tabelle, query denominate o viste</span><span class="sxs-lookup"><span data-stu-id="8c0a8-116">To add a relationship between tables, named queries, or views</span></span>](#bkmk_addRel)  
  
 [<span data-ttu-id="8c0a8-117">Per visualizzare o modificare una relazione nel riquadro Diagramma</span><span class="sxs-lookup"><span data-stu-id="8c0a8-117">To view or modify a relationship in the Diagram pane</span></span>](#bkmk_diagrampane)  
  
 [<span data-ttu-id="8c0a8-118">Per visualizzare o modificare una relazione nel riquadro Tabelle</span><span class="sxs-lookup"><span data-stu-id="8c0a8-118">To view or modify a relationship in the Tables pane</span></span>](#bkmk_tablespane)  
  
##  <a name="to-add-a-relationship-between-tables-named-queries-or-views"></a><a name="bkmk_addRel"></a><span data-ttu-id="8c0a8-119">Per aggiungere una relazione tra tabelle, query denominate o viste</span><span class="sxs-lookup"><span data-stu-id="8c0a8-119">To add a relationship between tables, named queries, or views</span></span>  
  
1.  <span data-ttu-id="8c0a8-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto o connettersi al database contenente la vista origine dati in cui si vuole aggiungere una relazione logica.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-120">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to add a logical relationship.</span></span>  
  
2.  <span data-ttu-id="8c0a8-121">In Esplora soluzioni espandere la cartella **Viste origine dati** e quindi fare doppio clic sulla vista origine dati per aprirla in **Progettazione vista origine dati**.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-121">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view to open it in **Data Source View Designer**.</span></span>  
  
3.  <span data-ttu-id="8c0a8-122">Fare clic con il pulsante destro del mouse sulla tabella, sulla query denominata o sulla vista a cui si vuole aggiungere una relazione nel riquadro **Tabelle** e quindi scegliere **Nuova relazione**.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-122">Right-click the table, named query or view to which you want to add a relationship in either the **Tables** pane and then click **New Relationship**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8c0a8-123">Per individuare una tabella, una vista o una query denominata, è possibile usare l'opzione **Trova tabella** scegliendola dal menu **Vista origine dati** o facendo clic con il pulsante destro del mouse su un'area vuota nel riquadro **Tabella** o **Diagramma** .</span><span class="sxs-lookup"><span data-stu-id="8c0a8-123">To locate a table, view or named query, you can use the **Find Table** option by either clicking the **Data Source View** menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
4.  <span data-ttu-id="8c0a8-124">Nella finestra di dialogo **Specifica relazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c0a8-124">In the **Specify Relationship** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="8c0a8-125">Selezionare la tabella, la query denominata o la vista appropriata nell'elenco **Tabella di origine (chiave esterna)** .</span><span class="sxs-lookup"><span data-stu-id="8c0a8-125">Select the appropriate table, named query, or view in the **Source (foreign key) table** list.</span></span>  
  
    2.  <span data-ttu-id="8c0a8-126">Selezionare la tabella, la query denominata o la vista appropriata negli elenchi **Tabella di destinazione (chiave primaria)** .</span><span class="sxs-lookup"><span data-stu-id="8c0a8-126">Select the appropriate table, named query, or view in the **Destination (primary key) table** lists.</span></span>  
  
    3.  <span data-ttu-id="8c0a8-127">Selezionare le colonne negli elenchi **Colonne di origine** e **Colonne di destinazione** per creare una relazione tra le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-127">Select columns from the **Source Columns** and **Destination Columns** lists to create a relationship between the two tables.</span></span>  
  
         <span data-ttu-id="8c0a8-128">Se durante il campionamento dei dati della query denominata, della vista o della tabella sottostante [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] rileva che la relazione è stata definita nella direzione errata, ovvero dalla chiave primaria alla chiave esterna anziché dalla chiave esterna alla chiave primaria, verrà richiesto di invertire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-128">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects, by sampling the data in the underlying table, view, or named query, that you have defined the relationship in the wrong direction (from the primary key to the foreign key rather than from the foreign key to the primary key), you will be prompted to reverse the order.</span></span> <span data-ttu-id="8c0a8-129">Per invertire rapidamente l'ordine, fare clic su **Inverti**.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-129">To quickly reverse the order, click **Reverse**.</span></span>  
  
         <span data-ttu-id="8c0a8-130">Viene anche segnalato se [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] rileva che esiste già una relazione per le colonne selezionate.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-130">If [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] detects that a relationship already exists for the columns you have selected, you will be prompted.</span></span> <span data-ttu-id="8c0a8-131">Non è possibile definire relazioni duplicate.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-131">You cannot define duplicate relationships.</span></span>  
  
    4.  <span data-ttu-id="8c0a8-132">Facoltativamente, digitare una descrizione per la relazione nella casella **Descrizione** .</span><span class="sxs-lookup"><span data-stu-id="8c0a8-132">Optionally, in the **Description** box, type a description for the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-diagram-pane"></a><a name="bkmk_diagrampane"></a><span data-ttu-id="8c0a8-133">Per visualizzare o modificare una relazione nel riquadro diagramma</span><span class="sxs-lookup"><span data-stu-id="8c0a8-133">To view or modify a relationship in the Diagram pane</span></span>  
  
-   <span data-ttu-id="8c0a8-134">Nel riquadro **Diagramma** di **Progettazione vista origine dati**fare clic con il pulsante destro del mouse sulla relazione da visualizzare e scegliere **Modifica relazione** oppure fare semplicemente doppio clic sulla freccia della relazione.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-134">In the **Diagram** pane in **Data Source View Designer**, right-click the relationship that you want to view and click **Edit Relationship** (or simply double-click the relationship arrow).</span></span>  <span data-ttu-id="8c0a8-135">Usare la finestra di dialogo **Modifica relazione** per modificare la relazione.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-135">Use the **Edit Relationship** dialog box to modify the relationship.</span></span>  
  
##  <a name="to-view-or-modify-a-relationship-in-the-tables-pane"></a><a name="bkmk_tablespane"></a><span data-ttu-id="8c0a8-136">Per visualizzare o modificare una relazione nel riquadro tabelle</span><span class="sxs-lookup"><span data-stu-id="8c0a8-136">To view or modify a relationship in the Tables pane</span></span>  
  
1.  <span data-ttu-id="8c0a8-137">Nel riquadro **Tabelle** di **Progettazione vista origine dati**individuare e quindi espandere la tabella, la vista o la query denominata contenente la relazione da visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-137">In the **Tables** pane in **Data Source View Designer**, locate and then expand the table, view or named query containing the relationship that you wish to view or modify.</span></span>  
  
2.  <span data-ttu-id="8c0a8-138">Espandere la cartella **Relazioni** .</span><span class="sxs-lookup"><span data-stu-id="8c0a8-138">Expand the **Relationships** folder.</span></span>  <span data-ttu-id="8c0a8-139">Le relazioni tra la tabella, la vista o la query denominata selezionata e altre tabelle, viste e query denominate vengono visualizzate con un elenco delle colonne delle relazioni.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-139">The relationships between the selected table, view or named query and other tables, views and named queries appear with the relationship column listed.</span></span>  
  
3.  <span data-ttu-id="8c0a8-140">Fare clic con il pulsante destro del mouse sulla relazione da modificare e quindi scegliere **Modifica relazione**.</span><span class="sxs-lookup"><span data-stu-id="8c0a8-140">Right-click the relationship you want to modify, and then click **Edit Relationship**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c0a8-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c0a8-141">See Also</span></span>  
 [<span data-ttu-id="8c0a8-142">Viste origine dati in modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="8c0a8-142">Data Source Views in Multidimensional Models</span></span>](data-source-views-in-multidimensional-models.md)  
  
  
