---
title: Query di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataminingquery.f1
ms.assetid: 948e358a-6245-429f-82c7-4cedc5e048fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 657e4e173815fa25458e296f7eadb3d4d0696a02
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629560"
---
# <a name="data-mining-query"></a><span data-ttu-id="fd483-102">Query di data mining</span><span class="sxs-lookup"><span data-stu-id="fd483-102">Data Mining Query</span></span>
  <span data-ttu-id="fd483-103">Il riquadro di progettazione contiene il generatore delle query di stima di data mining che consente di compilare le query delle stime di data mining.</span><span class="sxs-lookup"><span data-stu-id="fd483-103">The design pane contains the data mining prediction query builder, which you can use to build data mining prediction queries.</span></span> <span data-ttu-id="fd483-104">È possibile progettare query di stima in base a tabelle di input o query di stima singleton.</span><span class="sxs-lookup"><span data-stu-id="fd483-104">You can design either prediction queries based on input tables, or singleton prediction queries.</span></span> <span data-ttu-id="fd483-105">Passare alla visualizzazione dei risultati per eseguire la query e visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="fd483-105">Switch to the result view to run the query and view the results.</span></span> <span data-ttu-id="fd483-106">Nella visualizzazione Query viene visualizzata la query DMX (Data Mining Extensions) creata dal generatore delle query di stima.</span><span class="sxs-lookup"><span data-stu-id="fd483-106">The query view displays the Data Mining Extensions (DMX) query created by the prediction query builder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fd483-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="fd483-107">Options</span></span>  
 <span data-ttu-id="fd483-108">Pulsante Cambia visualizzazione</span><span class="sxs-lookup"><span data-stu-id="fd483-108">Switch view button</span></span>  
 <span data-ttu-id="fd483-109">Fare clic su un'icona per alternare il riquadro di progettazione al riquadro Query.</span><span class="sxs-lookup"><span data-stu-id="fd483-109">Click an icon to switch between the design and query pane.</span></span> <span data-ttu-id="fd483-110">Per impostazione predefinita è aperto il riquadro di progettazione.</span><span class="sxs-lookup"><span data-stu-id="fd483-110">By default, the design pane is open.</span></span>  
  
 <span data-ttu-id="fd483-111">Per passare al riquadro di progettazione, fare clic sull'icona ![Icona Progettazione](../media/ssis-designicon.gif "Icona Progettazione").</span><span class="sxs-lookup"><span data-stu-id="fd483-111">To switch to the design pane, click the ![Design icon](../media/ssis-designicon.gif "Design icon") icon.</span></span>  
  
 <span data-ttu-id="fd483-112">Per passare al riquadro Query, fare clic sull'icona ![Icona SQL](../media/ssis-queryicon.gif "Icona SQL").</span><span class="sxs-lookup"><span data-stu-id="fd483-112">To switch to the query pane, click the ![SQL icon](../media/ssis-queryicon.gif "SQL icon") icon.</span></span>  
  
 <span data-ttu-id="fd483-113">**Modello di data mining**</span><span class="sxs-lookup"><span data-stu-id="fd483-113">**Mining Model**</span></span>  
 <span data-ttu-id="fd483-114">Consente di visualizzare il modello di data mining selezionato sul quale si desidera basare le stime.</span><span class="sxs-lookup"><span data-stu-id="fd483-114">Displays the selected mining model on which you want to base predictions.</span></span>  
  
 <span data-ttu-id="fd483-115">**Seleziona modello**</span><span class="sxs-lookup"><span data-stu-id="fd483-115">**Select Model**</span></span>  
 <span data-ttu-id="fd483-116">Consente di aprire la finestra di dialogo **Seleziona modello di data mining** .</span><span class="sxs-lookup"><span data-stu-id="fd483-116">Opens the **Select Mining Model** dialog box.</span></span>  
  
 <span data-ttu-id="fd483-117">**Colonne di input**</span><span class="sxs-lookup"><span data-stu-id="fd483-117">**Input Columns**</span></span>  
 <span data-ttu-id="fd483-118">Consente di visualizzare le colonne di input selezionate per la generazione delle stime.</span><span class="sxs-lookup"><span data-stu-id="fd483-118">Displays the selected input columns used to generate the predictions.</span></span>  
  
 <span data-ttu-id="fd483-119">**Origine**</span><span class="sxs-lookup"><span data-stu-id="fd483-119">**Source**</span></span>  
 <span data-ttu-id="fd483-120">Consente di selezionare l'origine contenente il campo che verrà utilizzato per la colonna nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fd483-120">Select the source containing the field that you will use for the column from the dropdown list.</span></span> <span data-ttu-id="fd483-121">È possibile usare il modello di data mining selezionato nella tabella **Modello di data mining** , la tabella o le tabelle di input selezionate nella tabella **Seleziona tabella/e di input** , una funzione di stima o un'espressione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="fd483-121">You can either use the mining model selected in the **Mining Model** table, the input table(s) selected in the **Select Input Table(s)** table, a prediction function, or a custom expression.</span></span>  
  
 <span data-ttu-id="fd483-122">È possibile trascinare le colonne dalle tabelle contenenti il modello di data mining e dalle tabelle di input sulla cella.</span><span class="sxs-lookup"><span data-stu-id="fd483-122">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
 <span data-ttu-id="fd483-123">**Campo**</span><span class="sxs-lookup"><span data-stu-id="fd483-123">**Field**</span></span>  
 <span data-ttu-id="fd483-124">Consente di selezionare una colonna nell'elenco di colonne derivato dalla tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="fd483-124">Select a column from the list of columns derived from the source table.</span></span> <span data-ttu-id="fd483-125">Se è stata selezionata l'opzione **Funzione di stima** in **Origine**, la cella conterrà un elenco a discesa delle funzioni di stima disponibili per il modello di data mining selezionato.</span><span class="sxs-lookup"><span data-stu-id="fd483-125">If you selected **Prediction Function** in **Source**, this cell contains a drop-down list of the prediction functions available for the selected mining model.</span></span>  
  
 <span data-ttu-id="fd483-126">**Alias**</span><span class="sxs-lookup"><span data-stu-id="fd483-126">**Alias**</span></span>  
 <span data-ttu-id="fd483-127">Il nome della colonna restituito dal server.</span><span class="sxs-lookup"><span data-stu-id="fd483-127">The name of the column returned by the server.</span></span>  
  
 <span data-ttu-id="fd483-128">**Mostra**</span><span class="sxs-lookup"><span data-stu-id="fd483-128">**Show**</span></span>  
 <span data-ttu-id="fd483-129">Selezionare questa opzione per restituire la colonna o per utilizzarla solo nella clausola WHERE.</span><span class="sxs-lookup"><span data-stu-id="fd483-129">Select to return the column or to only use the column in the WHERE clause.</span></span>  
  
 <span data-ttu-id="fd483-130">**Gruppo**</span><span class="sxs-lookup"><span data-stu-id="fd483-130">**Group**</span></span>  
 <span data-ttu-id="fd483-131">Usare questa opzione con la colonna **And/Or** per raggruppare le espressioni.</span><span class="sxs-lookup"><span data-stu-id="fd483-131">Use with the **And/Or** column to group expressions together.</span></span> <span data-ttu-id="fd483-132">Ad esempio, (espr1 OR espr2) AND espr3.</span><span class="sxs-lookup"><span data-stu-id="fd483-132">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="fd483-133">**And/Or**</span><span class="sxs-lookup"><span data-stu-id="fd483-133">**And/Or**</span></span>  
 <span data-ttu-id="fd483-134">Utilizzare questa opzione per creare una query logica.</span><span class="sxs-lookup"><span data-stu-id="fd483-134">Use to create a logical query.</span></span> <span data-ttu-id="fd483-135">Ad esempio, (espr1 OR espr2) AND espr3.</span><span class="sxs-lookup"><span data-stu-id="fd483-135">For example, (expr1 OR expr2) AND expr3.</span></span>  
  
 <span data-ttu-id="fd483-136">**Criteri/Argomento**</span><span class="sxs-lookup"><span data-stu-id="fd483-136">**Criteria/Argument**</span></span>  
 <span data-ttu-id="fd483-137">Consente di specificare una condizione o un'espressione utente da applicare a una colonna.</span><span class="sxs-lookup"><span data-stu-id="fd483-137">Specify a condition or user expression that applies to the column.</span></span> <span data-ttu-id="fd483-138">È possibile trascinare le colonne dalle tabelle contenenti il modello di data mining e dalle tabelle di input sulla cella.</span><span class="sxs-lookup"><span data-stu-id="fd483-138">Columns can be dragged from the tables containing the mining model and input columns to the cell.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd483-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd483-139">See Also</span></span>  
 <span data-ttu-id="fd483-140">[Interfacce di query di data mining](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span><span class="sxs-lookup"><span data-stu-id="fd483-140">[Data Mining Query Interfaces](https://docs.microsoft.com/analysis-services/data-mining/data-mining-query-tools) </span></span>  
 [<span data-ttu-id="fd483-141">Guida di riferimento alle istruzioni DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="fd483-141">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
