---
title: Esplorazione dei dati (SQL Server componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- histogram [data mining]
- data visualization
ms.assetid: 714845a9-4c27-461a-9ba3-149e1e818386
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2572c11e92dcf99dfa3adf661603e8f65f05116e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718875"
---
# <a name="explore-data-sql-server-data-mining-add-ins"></a><span data-ttu-id="55f0e-102">Esplorazione dati (componenti aggiuntivi Data mining di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="55f0e-102">Explore Data (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="55f0e-103">![Procedura guidata Esplorazione dati](media/dmc-explore.gif "Procedura guidata Esplorazione dati")</span><span class="sxs-lookup"><span data-stu-id="55f0e-103">![Explore Data wizard](media/dmc-explore.gif "Explore Data wizard")</span></span>  
  
 <span data-ttu-id="55f0e-104">La procedura guidata **Esplora dati** consente di comprendere il tipo e la quantità di dati nella tabella dati.</span><span class="sxs-lookup"><span data-stu-id="55f0e-104">The **Explore Data** wizard helps you understand the type and amount of data in your data table.</span></span> <span data-ttu-id="55f0e-105">La procedura guidata consente di creare un grafico della distribuzione e dei valori delle colonne selezionate, una alla volta.</span><span class="sxs-lookup"><span data-stu-id="55f0e-105">The wizard graphs the distribution and values for the selected columns, one column at a time.</span></span> <span data-ttu-id="55f0e-106">È quindi possibile provare a modificare il modo in cui i dati vengono raggruppati o copiare il grafico del contenuto in una cartella di lavoro di Excel per esaminarlo.</span><span class="sxs-lookup"><span data-stu-id="55f0e-106">You can then experiment with changing the way that data is grouped, or copy the chart that shows the content to an Excel workbook for review.</span></span>  
  
 <span data-ttu-id="55f0e-107">Se nei dati sono contenuti dati numerici continui, è possibile passare tra queste due viste:</span><span class="sxs-lookup"><span data-stu-id="55f0e-107">If your data contains continuous numeric data, you can toggle between these two views:</span></span>  
  
-   <span data-ttu-id="55f0e-108">**Grafico a linee.**</span><span class="sxs-lookup"><span data-stu-id="55f0e-108">**Line graph.**</span></span> <span data-ttu-id="55f0e-109">Questo grafico a linee riporta i valori dei dati sull'asse X e il numero di case sull'asse Y.</span><span class="sxs-lookup"><span data-stu-id="55f0e-109">This graph charts the data values on the X-axis and the number of cases on the y-axis.</span></span>  
  
-   <span data-ttu-id="55f0e-110">**Grafico a barre.**</span><span class="sxs-lookup"><span data-stu-id="55f0e-110">**Bar chart.**</span></span> <span data-ttu-id="55f0e-111">Questo grafico a barre raggruppa i valori in base al numero di case per ogni valore.</span><span class="sxs-lookup"><span data-stu-id="55f0e-111">This graph groups values by the number of cases for each value.</span></span>  
  
 <span data-ttu-id="55f0e-112">Quando tramite la procedura guidata vengono trovati gruppi nei dati, si utilizza la distribuzione effettiva dei valori dei dati.</span><span class="sxs-lookup"><span data-stu-id="55f0e-112">When the wizard finds groups in the data, it uses the actual distribution of data values.</span></span> <span data-ttu-id="55f0e-113">Pertanto, il grafico a barre non visualizza i valori numerici in base a indicatori numerici tipici dell'asse costituiti da numeri interi, ad esempio 10 o 100.</span><span class="sxs-lookup"><span data-stu-id="55f0e-113">Therefore, the bar chart does not show typical whole-number numeric axis markers such as 10 or 100.</span></span> <span data-ttu-id="55f0e-114">Gli intervalli visualizzati nel grafico a barre possono invece essere simili al seguente: 43521-55603 (per la colonna Income).</span><span class="sxs-lookup"><span data-stu-id="55f0e-114">Instead, the ranges shown in the bar chart might be something like 43521-55603 (for the Income column).</span></span>  
  
 <span data-ttu-id="55f0e-115">Se si desidera raggruppare i dati in altri intervalli, è necessario eseguire questa operazione in Excel prima di analizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="55f0e-115">If you want to group your data into other ranges, you should do this in Excel before analyzing the data.</span></span> <span data-ttu-id="55f0e-116">In alternativa, è possibile rietichettare i dati tramite la procedura guidata modifica [etichette](relabel-sql-server-data-mining-add-ins.md) .</span><span class="sxs-lookup"><span data-stu-id="55f0e-116">Or, you can relabel the data by using the [Relabel](relabel-sql-server-data-mining-add-ins.md) wizard.</span></span>  
  
## <a name="using-the-explore-data-wizard"></a><span data-ttu-id="55f0e-117">Utilizzo della procedura guidata Esplorazione dati</span><span class="sxs-lookup"><span data-stu-id="55f0e-117">Using the Explore Data Wizard</span></span>  
  
1.  <span data-ttu-id="55f0e-118">Sulla barra multifunzione **data mining** fare clic su **Esplora dati**.</span><span class="sxs-lookup"><span data-stu-id="55f0e-118">In the **Data Mining** ribbon, click **Explore Data**.</span></span>  
  
2.  <span data-ttu-id="55f0e-119">Nella finestra di dialogo **Seleziona origine** selezionare la tabella o l'intervallo di celle contenente i dati.</span><span class="sxs-lookup"><span data-stu-id="55f0e-119">In the **Select Source** dialog box, select the table or range of cells that contains your data.</span></span>  
  
3.  <span data-ttu-id="55f0e-120">Nella finestra di dialogo **Seleziona colonna** scegliere la colonna da analizzare, dai dati di esempio visualizzati nel riquadro.</span><span class="sxs-lookup"><span data-stu-id="55f0e-120">In the **Select Column** dialog box, choose the column to analyze, from the sample data displayed in the pane.</span></span>  
  
4.  <span data-ttu-id="55f0e-121">Nella finestra di dialogo **Esplora dati** scegliere i tipi di grafico per la visualizzazione della distribuzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="55f0e-121">In the **Explore Data** dialog box, choose the chart types for displaying the distribution of data.</span></span>  
  
5.  <span data-ttu-id="55f0e-122">È possibile aggiungere nuove colonne ai dati, cambiare il modo in cui i dati sono segmentati o copiare il grafico in Excel.</span><span class="sxs-lookup"><span data-stu-id="55f0e-122">Optionally, you can add new columns to the data, change the way that the data is segmented, or copy the chart to Excel.</span></span>  
  
### <a name="requirements"></a><span data-ttu-id="55f0e-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55f0e-123">Requirements</span></span>  
 <span data-ttu-id="55f0e-124">Per utilizzare la procedura guidata **esplorazione dati** , è necessario che i dati si trovino in una tabella dati di Excel.</span><span class="sxs-lookup"><span data-stu-id="55f0e-124">To use the **Explore Data** wizard, your data must be in an Excel data table.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="55f0e-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55f0e-125">See Also</span></span>  
 [<span data-ttu-id="55f0e-126">Elenco di controllo per la preparazione di data mining</span><span class="sxs-lookup"><span data-stu-id="55f0e-126">Checklist of Preparation for Data Mining</span></span>](checklist-of-preparation-for-data-mining.md)  
  
  
