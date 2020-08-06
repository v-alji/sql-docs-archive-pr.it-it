---
title: Visualizzare e salvare i risultati di una query di stima | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- viewing prediction query results
- displaying prediction query results
- Mining Model Prediction [Analysis Services], viewing results
ms.assetid: abba4d24-3619-44c1-8279-88f27ad627d3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6da4b515c4280969f665dba2cf5bee5281df0a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627526"
---
# <a name="view-and-save-the-results-of-a-prediction-query"></a><span data-ttu-id="86a7b-102">Visualizzare e salvare i risultati di una query di stima</span><span class="sxs-lookup"><span data-stu-id="86a7b-102">View and Save the Results of a Prediction Query</span></span>
  <span data-ttu-id="86a7b-103">Dopo aver definito una query in utilizzando la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Generatore di query di stima, è possibile eseguire la query e visualizzare i risultati passando alla visualizzazione dei risultati della query.</span><span class="sxs-lookup"><span data-stu-id="86a7b-103">After you have defined a query in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using Prediction Query Builder, you can run the query and view the results by switching to the query result view.</span></span>  
  
 <span data-ttu-id="86a7b-104">È possibile salvare i risultati di una query di stima in una tabella in qualsiasi origine dati definita in un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="86a7b-104">You can save the results of a prediction query to a table in any data source that is defined in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="86a7b-105">È possibile creare una nuova tabella oppure salvare i risultati della query in una tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="86a7b-105">You can either create a new table or save the query results to an existing table.</span></span> <span data-ttu-id="86a7b-106">Se si salvano i risultati in una tabella esistente, è possibile scegliere di sovrascrivere i dati attualmente archiviati nella tabella. Altrimenti, i risultati della query verranno accodati ai dati esistenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="86a7b-106">If you save the results to an existing table, you can choose to overwrite the data that is currently stored in the table; otherwise, the query results are appended to the existing data in the table.</span></span>  
  
### <a name="run-a-query-and-view-the-results"></a><span data-ttu-id="86a7b-107">Eseguire una query e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="86a7b-107">Run a query and view the results</span></span>  
  
1.  <span data-ttu-id="86a7b-108">Sulla barra degli strumenti della scheda **Stima modello di data mining** di Progettazione modelli di data mining in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]fare clic su **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="86a7b-108">On the toolbar of the **Mining Model Prediction** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Result** .</span></span>  
  
     <span data-ttu-id="86a7b-109">Verrà aperta la visualizzazione dei risultati della query, tramite cui verrà eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="86a7b-109">The query results view opens and runs the query.</span></span> <span data-ttu-id="86a7b-110">I risultati verranno visualizzati in una griglia nel visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="86a7b-110">The results are displayed in a grid in the viewer.</span></span>  
  
### <a name="save-the-results-of-a-prediction-query-to-a-table"></a><span data-ttu-id="86a7b-111">Salvare i risultati di una query di stima in una tabella</span><span class="sxs-lookup"><span data-stu-id="86a7b-111">Save the results of a prediction query to a table</span></span>  
  
1.  <span data-ttu-id="86a7b-112">Sulla barra degli strumenti della scheda **Stima modello di data mining** di Progettazione modelli di data mining fare clic su **Salva risultati query**.</span><span class="sxs-lookup"><span data-stu-id="86a7b-112">On the toolbar of the **Mining Model Prediction** tab in Data Mining Designer, click **Save query result**.</span></span>  
  
     <span data-ttu-id="86a7b-113">Verrà visualizzata la finestra di dialogo **Salva risultati query di data mining** .</span><span class="sxs-lookup"><span data-stu-id="86a7b-113">The **Save Data Mining Query Result** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="86a7b-114">Selezionare un'origine dati nell'elenco **Origine dati** oppure fare clic su **Nuova** per creare una nuova origine dati.</span><span class="sxs-lookup"><span data-stu-id="86a7b-114">Select a data source from the **Data Source** list, or click **New** to create a new data source.</span></span>  
  
3.  <span data-ttu-id="86a7b-115">Nella casella **Nome tabella** immettere il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="86a7b-115">In the **Table Name** box, enter the name of the table.</span></span> <span data-ttu-id="86a7b-116">Se la tabella esiste già, selezionare **Sovrascrivi se esistente** per sostituire il contenuto della tabella con i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="86a7b-116">If the table already exists, select **Overwrite if exists** to replace the contents of the table with the query results.</span></span> <span data-ttu-id="86a7b-117">Se non si desidera sovrascrivere il contenuto della tabella, non selezionare questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="86a7b-117">If you do not want to overwrite the contents of the table, do not select this check box.</span></span> <span data-ttu-id="86a7b-118">I nuovi risultati della query verranno accodati ai dati esistenti nella tabella.</span><span class="sxs-lookup"><span data-stu-id="86a7b-118">The new query results will be appended to the existing data in the table.</span></span>  
  
4.  <span data-ttu-id="86a7b-119">Selezionare una vista origine dati in **Aggiungi a vista origine dati** se si desidera aggiungere la tabella a una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="86a7b-119">Select a data source view from **Add to DSV** if you want to add the table to a data source view.</span></span>  
  
5.  <span data-ttu-id="86a7b-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="86a7b-120">Click **Save**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="86a7b-121">Se la destinazione non supporta set di righe gerarchici, è possibile aggiungere la parola chiave FALTTENED ai risultati per effettuare il salvataggio come tabella flat.</span><span class="sxs-lookup"><span data-stu-id="86a7b-121">If the destination does not support hierarchical rowsets, you can add the FALTTENED keyword to the results to save as a flat table.</span></span>  
  
  
