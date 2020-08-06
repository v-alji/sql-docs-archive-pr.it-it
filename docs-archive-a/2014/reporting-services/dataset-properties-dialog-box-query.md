---
title: Finestra di dialogo Proprietà set di dati, query | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10160"
- sql12.rtp.rptdesigner.datasetproperties.query.f1
ms.assetid: 1fa34a4b-7de0-4e92-99fa-bc28a206773f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bffb14155d37e67333eb626747e1fcc54e618bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637651"
---
# <a name="dataset-properties-dialog-box-query"></a><span data-ttu-id="95694-102">Finestra di dialogo Proprietà set di dati, Query</span><span class="sxs-lookup"><span data-stu-id="95694-102">Dataset Properties Dialog Box, Query</span></span>
  <span data-ttu-id="95694-103">Selezionare **query** nella finestra di dialogo **Proprietà set** di dati per scegliere un'origine dati e creare una query.</span><span class="sxs-lookup"><span data-stu-id="95694-103">Select **Query** on the **Dataset Properties** dialog box to choose a data source and create a query.</span></span>  
  
 <span data-ttu-id="95694-104">Nella finestra di dialogo **Proprietà set di dati** sono presenti le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="95694-104">The **Dataset Properties** dialog box includes the following:</span></span>  
  
-   [<span data-ttu-id="95694-105">Finestra di dialogo Proprietà set di dati, Parametri</span><span class="sxs-lookup"><span data-stu-id="95694-105">Dataset Properties Dialog Box, Parameters</span></span>](report-data/dataset-properties-dialog-box-parameters.md)  
  
-   [<span data-ttu-id="95694-106">Finestra di dialogo Proprietà set di dati, Campi</span><span class="sxs-lookup"><span data-stu-id="95694-106">Dataset Properties Dialog Box, Fields</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-fields.md)  
  
-   [<span data-ttu-id="95694-107">Finestra di dialogo Proprietà set di dati, Opzioni</span><span class="sxs-lookup"><span data-stu-id="95694-107">Dataset Properties Dialog Box, Options</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-options.md)  
  
-   [<span data-ttu-id="95694-108">Finestra di dialogo Proprietà set di dati, Filtri</span><span class="sxs-lookup"><span data-stu-id="95694-108">Dataset Properties Dialog Box, Filters</span></span>](report-data/dataset-properties-dialog-box-filters.md)  
  
## <a name="options"></a><span data-ttu-id="95694-109">Opzioni</span><span class="sxs-lookup"><span data-stu-id="95694-109">Options</span></span>  
 <span data-ttu-id="95694-110">**Nome**</span><span class="sxs-lookup"><span data-stu-id="95694-110">**Name**</span></span>  
 <span data-ttu-id="95694-111">Consente di digitare un nome per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="95694-111">Type a name for the dataset.</span></span> <span data-ttu-id="95694-112">Non è possibile specificare un nome uguale a quello di un'area dati o di un gruppo nel report.</span><span class="sxs-lookup"><span data-stu-id="95694-112">The name cannot be the same as a name for any data region or group in the report.</span></span>  
  
 <span data-ttu-id="95694-113">**Origine dati**</span><span class="sxs-lookup"><span data-stu-id="95694-113">**Data Source**</span></span>  
 <span data-ttu-id="95694-114">Consente di selezionare l'origine dati su cui basare il set di dati.</span><span class="sxs-lookup"><span data-stu-id="95694-114">Select the data source on which to base the dataset.</span></span> <span data-ttu-id="95694-115">Per creare una nuova origine dati, fare clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="95694-115">To create a new data source, click **New**.</span></span>  
  
 <span data-ttu-id="95694-116">**Tipo di query**</span><span class="sxs-lookup"><span data-stu-id="95694-116">**Query type**</span></span>  
 <span data-ttu-id="95694-117">Consente di selezionare il tipo di comando o query da utilizzare per il set di dati.</span><span class="sxs-lookup"><span data-stu-id="95694-117">Select the type of command or query to use for the dataset.</span></span> <span data-ttu-id="95694-118">Selezionare **Testo** per eseguire una query che consenta di recuperare dati dal database.</span><span class="sxs-lookup"><span data-stu-id="95694-118">Select **Text** to run a query to retrieve data from the database.</span></span> <span data-ttu-id="95694-119">Selezionare **Tabella** per usare la funzionalità **TableDirect** di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e selezionare tutti i campi all'interno di una tabella.</span><span class="sxs-lookup"><span data-stu-id="95694-119">Select **Table** to use the **TableDirect** feature of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to select all the fields within a table.</span></span> <span data-ttu-id="95694-120">Selezionare **Stored procedure** per eseguire una stored procedure in base al nome.</span><span class="sxs-lookup"><span data-stu-id="95694-120">Select **Stored Procedure** to run a stored procedure by name.</span></span> <span data-ttu-id="95694-121">**Testo** è selezionato per impostazione predefinita e viene usato per la maggior parte delle query.</span><span class="sxs-lookup"><span data-stu-id="95694-121">**Text** is selected by default and is used for most queries.</span></span> <span data-ttu-id="95694-122">Per modificare la query sull'origine dati selezionata, fare clic su **Progettazione query**.</span><span class="sxs-lookup"><span data-stu-id="95694-122">To edit the selected data source query, click **Query Designer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95694-123">Non tutti i tipi di query sono supportati da tutte le origini dati.</span><span class="sxs-lookup"><span data-stu-id="95694-123">Not all query types are supported by all data sources.</span></span> <span data-ttu-id="95694-124">Il tipo **Tabella** , ad esempio, è supportato solo dalle origini dati di tipo **OLE DB** e **ODBC**.</span><span class="sxs-lookup"><span data-stu-id="95694-124">For example, **Table** is supported only by data source types **OLE DB** and **ODBC**.</span></span>  
  
 <span data-ttu-id="95694-125">**Query**</span><span class="sxs-lookup"><span data-stu-id="95694-125">**Query**</span></span>  
 <span data-ttu-id="95694-126">Questa opzione viene visualizzata quando si sceglie l'opzione del tipo di comando **Testo** .</span><span class="sxs-lookup"><span data-stu-id="95694-126">This option appears when you choose the **Text** command type option.</span></span> <span data-ttu-id="95694-127">Digitare una query o importare una query preesistente facendo clic su **Importa**.</span><span class="sxs-lookup"><span data-stu-id="95694-127">Type a query or import a pre-existing query by clicking **Import**.</span></span> <span data-ttu-id="95694-128">Fare clic sul pulsante **espressione** (*FX*) per modificare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="95694-128">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95694-129">Se è disponibile una query compilata in una finestra di progettazione query, il relativo testo verrà visualizzato in questa casella.</span><span class="sxs-lookup"><span data-stu-id="95694-129">If you used a query designer to build a query, the text of the query appears in this box.</span></span>  
  
 <span data-ttu-id="95694-130">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="95694-130">**Table name**</span></span>  
 <span data-ttu-id="95694-131">Immettere il nome della tabella che si desidera utilizzare come set di dati.</span><span class="sxs-lookup"><span data-stu-id="95694-131">Enter the name of the table that you want to use as a dataset.</span></span> <span data-ttu-id="95694-132">Questa opzione viene visualizzata quando si seleziona **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="95694-132">This option appears when you select **Table**.</span></span>  
  
 <span data-ttu-id="95694-133">**Selezionare o immettere un nome di stored procedure**</span><span class="sxs-lookup"><span data-stu-id="95694-133">**Select or enter stored procedure name**</span></span>  
 <span data-ttu-id="95694-134">Digitare o scegliere il nome della stored procedure che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="95694-134">Type or choose the name of the stored procedure that you want to use.</span></span> <span data-ttu-id="95694-135">Fare clic sul pulsante **espressione** (*FX*) per modificare l'espressione.</span><span class="sxs-lookup"><span data-stu-id="95694-135">Click the **Expression** (*fx*) button to edit the expression.</span></span> <span data-ttu-id="95694-136">Questa opzione viene visualizzata quando si sceglie l'opzione del tipo di comando Stored procedure.</span><span class="sxs-lookup"><span data-stu-id="95694-136">This option appears when you choose the Stored Procedure command type option.</span></span>  
  
 <span data-ttu-id="95694-137">**Timeout (in secondi)**</span><span class="sxs-lookup"><span data-stu-id="95694-137">**Time out (in seconds)**</span></span>  
 <span data-ttu-id="95694-138">Digitare il numero di secondi prima del timeout della query. Il valore predefinito è 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="95694-138">Type the number of seconds until the query times out. The default is 30 seconds.</span></span> <span data-ttu-id="95694-139">Il valore nel campo **Timeout** deve essere vuoto o maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="95694-139">The value for **Time out** must be empty or greater than zero.</span></span> <span data-ttu-id="95694-140">Se non si specifica alcun valore, non si verificherà mai il timeout della query.</span><span class="sxs-lookup"><span data-stu-id="95694-140">If it is empty, the query does not time out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95694-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95694-141">See Also</span></span>  
 <span data-ttu-id="95694-142">[Connessioni dati, origini dati e stringhe di connessione in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="95694-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="95694-143">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="95694-143">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="95694-144">[Progettazione query &#40;Generatore report&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="95694-144">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 [<span data-ttu-id="95694-145">Strumenti di progettazione query in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="95694-145">Reporting Services Query Designers</span></span>](../../2014/reporting-services/reporting-services-query-designers.md)  
  
  
