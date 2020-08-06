---
title: Finestra di dialogo Modifica proprietà tabella (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.edittablepropdb.f1
ms.assetid: 8d913e83-7246-44cc-8fc7-31729023c0d8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6664d244f5f653610b37bd628abdb2263e015c0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636450"
---
# <a name="edit-table-properties-dialog-box-ssas"></a><span data-ttu-id="d2879-102">Finestra di dialogo Modifica proprietà tabella (SSAS)</span><span class="sxs-lookup"><span data-stu-id="d2879-102">Edit Table Properties Dialog Box (SSAS)</span></span>
  <span data-ttu-id="d2879-103">La finestra di dialogo **Modifica proprietà tabella** consente di visualizzare e modificare le proprietà di tabelle importate in Progettazione modelli tramite l'Importazione guidata tabella.</span><span class="sxs-lookup"><span data-stu-id="d2879-103">The **Edit Table Properties** dialog box enables you to view and modify the properties of tables that are imported into the model designer by using the Table Import Wizard.</span></span> <span data-ttu-id="d2879-104">Per accedere a questa finestra di dialogo, in Progettazione modelli selezionare una tabella, quindi scegliere **Proprietà tabella** dal menu **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="d2879-104">To access this dialog box, in the model designer, select a table, then click the **Table** menu, and then click **Table Properties**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="d2879-105">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d2879-105">UI element list</span></span>  
 <span data-ttu-id="d2879-106">Le opzioni per questa finestra di dialogo sono diverse, a seconda che i dati siano stati originariamente importati selezionando tabelle da un elenco o utilizzando una query SQL.</span><span class="sxs-lookup"><span data-stu-id="d2879-106">The options for this dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span>  
  
## <a name="table-preview-mode"></a><span data-ttu-id="d2879-107">Modalità Anteprima tabella</span><span class="sxs-lookup"><span data-stu-id="d2879-107">Table Preview Mode</span></span>  
 <span data-ttu-id="d2879-108">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="d2879-108">**Table name**</span></span>  
 <span data-ttu-id="d2879-109">Visualizza il nome della tabella dati nel modello.</span><span class="sxs-lookup"><span data-stu-id="d2879-109">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2879-110">Il nome della tabella non può essere modificato in questo punto.</span><span class="sxs-lookup"><span data-stu-id="d2879-110">You cannot edit the name here.</span></span> <span data-ttu-id="d2879-111">Tuttavia, è possibile modificarlo facendo clic con il pulsante destro del mouse sulla scheda della tabella nella parte inferiore di Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="d2879-111">However, you can change the name of the table by right-clicking the table tab at the bottom of the model designer.</span></span>  
  
 <span data-ttu-id="d2879-112">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="d2879-112">**Connection name**</span></span>  
 <span data-ttu-id="d2879-113">Visualizza il nome della connessione attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="d2879-113">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="d2879-114">**Nome origine**</span><span class="sxs-lookup"><span data-stu-id="d2879-114">**Source name**</span></span>  
 <span data-ttu-id="d2879-115">Consente di visualizzare o modificare la tabella dalla quale vengono ottenuti i dati.</span><span class="sxs-lookup"><span data-stu-id="d2879-115">Display or change the table from which the data is obtained.</span></span>  
  
 <span data-ttu-id="d2879-116">Se per l'origine si imposta una tabella con colonne diverse rispetto alla tabella corrente, viene visualizzato un messaggio indicante che le colonne sono diverse.</span><span class="sxs-lookup"><span data-stu-id="d2879-116">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="d2879-117">Sarà necessario quindi selezionare le colonne che si desidera inserire nella tabella corrente e fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d2879-117">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="d2879-118">Selezionando la casella di controllo a sinistra della tabella è possibile sostituire l'intera tabella.</span><span class="sxs-lookup"><span data-stu-id="d2879-118">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2879-119">Quando si modifica l'origine dati di una tabella, essenzialmente si sostituisce il contenuto della tabella corrente con il contenuto della nuova tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="d2879-119">When you change the data source of a table, you essentially replace the contents of the current table with the contents of the new source table.</span></span>  
  
 <span data-ttu-id="d2879-120">**Nomi colonne da**</span><span class="sxs-lookup"><span data-stu-id="d2879-120">**Column names from**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="d2879-121">**Origine**</span><span class="sxs-lookup"><span data-stu-id="d2879-121">**Source**</span></span>|<span data-ttu-id="d2879-122">Selezionare questa opzione per sostituire i nomi delle colonne correnti con i nomi delle colonne della tabella di origine selezionata.</span><span class="sxs-lookup"><span data-stu-id="d2879-122">Select this option to replace the current column names with the column names from the selected source table.</span></span>|  
|<span data-ttu-id="d2879-123">**Modello**</span><span class="sxs-lookup"><span data-stu-id="d2879-123">**Model**</span></span>|<span data-ttu-id="d2879-124">Selezionare questa opzione per utilizzare i nomi delle colonne correnti poiché presenti nel modello.</span><span class="sxs-lookup"><span data-stu-id="d2879-124">Select this option to use the current column names as they exist in the model.</span></span>|  
  
 <span data-ttu-id="d2879-125">**Aggiorna anteprima**</span><span class="sxs-lookup"><span data-stu-id="d2879-125">**Refresh preview**</span></span>  
 <span data-ttu-id="d2879-126">Fare clic per visualizzare le colonne di dati nella tabella di origine attualmente selezionata.</span><span class="sxs-lookup"><span data-stu-id="d2879-126">Click to view the columns of data in the currently selected source table.</span></span>  
  
 <span data-ttu-id="d2879-127">**Passa a**</span><span class="sxs-lookup"><span data-stu-id="d2879-127">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="d2879-128">**Anteprima tabella**</span><span class="sxs-lookup"><span data-stu-id="d2879-128">**Table preview**</span></span>|<span data-ttu-id="d2879-129">Selezionare questa opzione per visualizzare l'anteprima della tabella selezionata e un numero limitato di righe di dati.</span><span class="sxs-lookup"><span data-stu-id="d2879-129">Select this option to preview the selected table and a limited number of rows of data.</span></span>|  
|<span data-ttu-id="d2879-130">**Editor di query**</span><span class="sxs-lookup"><span data-stu-id="d2879-130">**Query editor**</span></span>|<span data-ttu-id="d2879-131">Selezionare questa opzione per visualizzare la query sull'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="d2879-131">Select this option to view the query against the selected data source.</span></span> <span data-ttu-id="d2879-132">Questa opzione non è disponibile per tutte le origini dati.</span><span class="sxs-lookup"><span data-stu-id="d2879-132">This option is not available for all data sources.</span></span>|  
  
 <span data-ttu-id="d2879-133">**Casella di controllo nell'intestazione di colonna**</span><span class="sxs-lookup"><span data-stu-id="d2879-133">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="d2879-134">Selezionare la casella di controllo per includere la colonna nell'importazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d2879-134">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="d2879-135">Deselezionare la casella di controllo per rimuovere la colonna dall'importazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="d2879-135">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="d2879-136">**Pulsante freccia in giù nell'intestazione di colonna**</span><span class="sxs-lookup"><span data-stu-id="d2879-136">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="d2879-137">Consente di filtrare i dati nella colonna.</span><span class="sxs-lookup"><span data-stu-id="d2879-137">Filter data in the column.</span></span>  
  
 <span data-ttu-id="d2879-138">**Cancella filtri di riga**</span><span class="sxs-lookup"><span data-stu-id="d2879-138">**Clear row filters**</span></span>  
 <span data-ttu-id="d2879-139">Fare clic per rimuovere qualsiasi filtro applicato.</span><span class="sxs-lookup"><span data-stu-id="d2879-139">Click to remove any filters that have been applied.</span></span>  
  
 <span data-ttu-id="d2879-140">**OK**</span><span class="sxs-lookup"><span data-stu-id="d2879-140">**OK**</span></span>  
 <span data-ttu-id="d2879-141">Fare clic per applicare tutte le modifiche apportate, inclusa la sostituzione delle colonne.</span><span class="sxs-lookup"><span data-stu-id="d2879-141">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="query-design-mode"></a><span data-ttu-id="d2879-142">Modalità Progettazione query</span><span class="sxs-lookup"><span data-stu-id="d2879-142">Query Design Mode</span></span>  
 <span data-ttu-id="d2879-143">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="d2879-143">**Table name**</span></span>  
 <span data-ttu-id="d2879-144">Visualizza il nome della tabella dati nel modello.</span><span class="sxs-lookup"><span data-stu-id="d2879-144">Displays the name of the data table in the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d2879-145">Il nome della tabella non può essere modificato in questo punto, ma facendo clic con il pulsante destro del mouse sulla scheda della tabella nella parte inferiore della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d2879-145">You cannot edit the name here; however, you can change the name of the table by right-clicking the table tab at the bottom of the designer.</span></span>  
  
 <span data-ttu-id="d2879-146">**Nome connessione**</span><span class="sxs-lookup"><span data-stu-id="d2879-146">**Connection name**</span></span>  
 <span data-ttu-id="d2879-147">Visualizza il nome della connessione attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="d2879-147">Displays the name of the connection that is currently in use.</span></span>  
  
 <span data-ttu-id="d2879-148">**Passa a**</span><span class="sxs-lookup"><span data-stu-id="d2879-148">**Switch to**</span></span>  
 |||  
|-|-|  
|<span data-ttu-id="d2879-149">**Anteprima tabella**</span><span class="sxs-lookup"><span data-stu-id="d2879-149">**Table preview**</span></span>|<span data-ttu-id="d2879-150">Selezionare questa opzione per visualizzare l'anteprima della tabella selezionata e alcune righe di dati.</span><span class="sxs-lookup"><span data-stu-id="d2879-150">Select this option to preview the selected table and a few rows of data.</span></span>|  
|<span data-ttu-id="d2879-151">**Editor di query**</span><span class="sxs-lookup"><span data-stu-id="d2879-151">**Query editor**</span></span>|<span data-ttu-id="d2879-152">Selezionare questa opzione per visualizzare la query che sarà eseguita sull'origine dati selezionata.</span><span class="sxs-lookup"><span data-stu-id="d2879-152">Select this option to view the query that will be issued against the selected data source.</span></span>|  
  
 <span data-ttu-id="d2879-153">**Istruzione SQL**</span><span class="sxs-lookup"><span data-stu-id="d2879-153">**Sql statement**</span></span>  
 <span data-ttu-id="d2879-154">Visualizza l'istruzione SQL eseguita sull'origine dati corrente per recuperare le righe.</span><span class="sxs-lookup"><span data-stu-id="d2879-154">Displays the SQL statement that is issued against the current data source to retrieve rows.</span></span> <span data-ttu-id="d2879-155">Per impostazione predefinita, vengono recuperate tutte le righe, tuttavia è possibile anche recuperare un subset di righe progettando un filtro o modificando manualmente l'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="d2879-155">By default, all rows are retrieved, but you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="d2879-156">**Convalida**</span><span class="sxs-lookup"><span data-stu-id="d2879-156">**Validate**</span></span>  
 <span data-ttu-id="d2879-157">Fare clic per verificare che l'istruzione sia sintatticamente corretta per l'origine dati e il provider selezionati.</span><span class="sxs-lookup"><span data-stu-id="d2879-157">Click to verify that the statement is syntactically correct for the selected data source and provider.</span></span>  
  
 <span data-ttu-id="d2879-158">**Progetta**</span><span class="sxs-lookup"><span data-stu-id="d2879-158">**Design**</span></span>  
 <span data-ttu-id="d2879-159">Fare clic per aprire una finestra Progettazione query visiva e compilare un'istruzione per la query.</span><span class="sxs-lookup"><span data-stu-id="d2879-159">Click to open a visual query designer and build a query statement.</span></span> <span data-ttu-id="d2879-160">Per informazioni sull'utilizzo della finestra di progettazione, premere F1 dalla finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d2879-160">For information about how to use the designer, press F1 from the designer.</span></span>  
  
 <span data-ttu-id="d2879-161">**OK**</span><span class="sxs-lookup"><span data-stu-id="d2879-161">**OK**</span></span>  
 <span data-ttu-id="d2879-162">Fare clic per applicare tutte le modifiche apportate, inclusa la sostituzione delle colonne.</span><span class="sxs-lookup"><span data-stu-id="d2879-162">Click to apply all changes that you made, including replacing columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2879-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2879-163">See Also</span></span>  
 [<span data-ttu-id="d2879-164">Tabelle e colonne &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="d2879-164">Tables and Columns &#40;SSAS Tabular&#41;</span></span>](tabular-models/tables-and-columns-ssas-tabular.md)  
  
  
