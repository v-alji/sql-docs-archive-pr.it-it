---
title: Finestra di dialogo Salva risultati query di data mining (visualizzazione Stima modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dm.savedataminingqueryresult.f1
helpviewer_keywords:
- Save Data Mining Query Result dialog box
ms.assetid: 112fb527-7466-4fd4-9cf1-75596135648f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0838c90f0797a0db9c8a66cd8c5f877aaecdad0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625629"
---
# <a name="save-data-mining-query-result-dialog-box-mining-model-prediction-view"></a><span data-ttu-id="baf15-102">Finestra di dialogo Salva risultati query di data mining (visualizzazione Stima modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="baf15-102">Save Data Mining Query Result Dialog Box (Mining Model Prediction View)</span></span>
  <span data-ttu-id="baf15-103">Utilizzare la finestra di dialogo **Salva risultati query di data mining** per salvare i risultati di una query di data mining in una nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="baf15-103">Use the **Save Data Mining Query Result** dialog box to save the results of a data mining query to a new table.</span></span>  
  
 <span data-ttu-id="baf15-104">La nuova tabella verrà creata nel database definito dall'origine dati.</span><span class="sxs-lookup"><span data-stu-id="baf15-104">The new table will be created in the database defined by the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="baf15-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="baf15-105">Options</span></span>  
 <span data-ttu-id="baf15-106">**Origine dati**</span><span class="sxs-lookup"><span data-stu-id="baf15-106">**Data Source**</span></span>  
 <span data-ttu-id="baf15-107">Consente di selezionare un'origine dati nel progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="baf15-107">Select a data source from the current project.</span></span> <span data-ttu-id="baf15-108">Se l'origine dati corretta non esiste, fare clic su **Nuova** per creare una nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="baf15-108">If the correct data source does not exist, click **New** to create a new data source.</span></span>  
  
 <span data-ttu-id="baf15-109">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="baf15-109">**New**</span></span>  
 <span data-ttu-id="baf15-110">Consente di avviare la **Creazione guidata origine dati**.</span><span class="sxs-lookup"><span data-stu-id="baf15-110">Opens the **Data Source Wizard**.</span></span>  
  
 <span data-ttu-id="baf15-111">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="baf15-111">**Table Name**</span></span>  
 <span data-ttu-id="baf15-112">Consente di digitare un nome per la nuova tabella.</span><span class="sxs-lookup"><span data-stu-id="baf15-112">Type a name for the new table.</span></span>  
  
 <span data-ttu-id="baf15-113">**Sovrascrivi se esistente**</span><span class="sxs-lookup"><span data-stu-id="baf15-113">**Overwrite if exists**</span></span>  
 <span data-ttu-id="baf15-114">Selezionare questa opzione se si desidera sovrascrivere una tabella esistente con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="baf15-114">Select this option if you want to overwrite an existing table with the same name.</span></span>  
  
 <span data-ttu-id="baf15-115">La sovrascrittura della tabella esistente è necessaria se si verificano una o più delle condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="baf15-115">Overwriting the existing table is required if any of the following is true:</span></span>  
  
-   <span data-ttu-id="baf15-116">Sono state aggiunte colonne alla query di stima.</span><span class="sxs-lookup"><span data-stu-id="baf15-116">You added columns to the prediction query.</span></span>  
  
-   <span data-ttu-id="baf15-117">Sono stati modificati i nomi o i tipi di dati di tutte le colonne nella query di stima.</span><span class="sxs-lookup"><span data-stu-id="baf15-117">You changed the names or data types of any columns in the prediction query.</span></span>  
  
-   <span data-ttu-id="baf15-118">È stata eseguita un'istruzione ALTER nella tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="baf15-118">You ran an ALTER statement on the destination table.</span></span>  
  
 <span data-ttu-id="baf15-119">In caso di più colonne con lo stesso nome, ad esempio diverse colonne derivate con il nome di colonna predefinito **Espressione**, è necessario creare un alias per ogni colonna con un nome duplicato.</span><span class="sxs-lookup"><span data-stu-id="baf15-119">If multiple columns have the same name (for example, several derived columns might have the default column name **Expression**), you must create an alias for each column with a duplicate name.</span></span> <span data-ttu-id="baf15-120">Se i nomi delle colonne non sono univoci, verrà generato un errore quando il progettista tenta di salvare i risultati in SQL Server, in quanto i nomi delle colonne di una tabella devono essere univoci.</span><span class="sxs-lookup"><span data-stu-id="baf15-120">If the columns do not have unique names, an error will be raised when the designer tries to save the results to SQL Server, because columns in a table must have unique names.</span></span>  
  
 <span data-ttu-id="baf15-121">**Aggiungi a vista origine dati**</span><span class="sxs-lookup"><span data-stu-id="baf15-121">**Add to DSV**</span></span>  
 <span data-ttu-id="baf15-122">(Facoltativo) Selezionare una vista origine dati inclusa nel progetto per aggiungere la tabella a un'origine dati esistente.</span><span class="sxs-lookup"><span data-stu-id="baf15-122">(Optional) Select a data source view contained in the project if you want to add the table to an existing data source.</span></span>  
  
 <span data-ttu-id="baf15-123">Questa opzione è utile se si desidera utilizzare tutte le tabelle correlate per un modello, ad esempio i dati di training, i dati di origine della stima e i risultati delle query, nella stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="baf15-123">This option is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf15-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baf15-124">See Also</span></span>  
 <span data-ttu-id="baf15-125">[Generatore di query di stima &#40;&#41;di data mining](prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="baf15-125">[Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md) </span></span>  
 <span data-ttu-id="baf15-126">[Interfacce di query di data mining](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="baf15-126">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="baf15-127">Guida di riferimento alle istruzioni DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="baf15-127">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
