---
title: Riquadro query (visualizzazione Stima modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.prediction.query.f1
ms.assetid: fdeec72e-d0bd-4453-9eaa-46436e4d6edc
author: minewiskan
ms.author: owend
ms.openlocfilehash: e17a27190891ea9e00be21d5013d0767d61ac148
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626952"
---
# <a name="query-pane-mining-model-prediction-view"></a><span data-ttu-id="b0187-102">Riquadro Query (visualizzazione Stima modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="b0187-102">Query Pane (Mining Model Prediction View)</span></span>
  <span data-ttu-id="b0187-103">Nel riquadro **Query** vengono visualizzate le istruzioni DMX (Data Mining Extensions) create dal generatore delle query di stima.</span><span class="sxs-lookup"><span data-stu-id="b0187-103">The **Query** pane displays the Data Mining Expressions (DMX) statements created by Prediction Query Builder.</span></span> <span data-ttu-id="b0187-104">È possibile modificare le istruzioni e quindi fare clic sul pulsante **Passa alla visualizzazione dei risultati della query** per visualizzare i risultati restituiti.</span><span class="sxs-lookup"><span data-stu-id="b0187-104">You can modify the statements and then click the **Switch to query result view** button to return the results.</span></span> <span data-ttu-id="b0187-105">Se si torna alla visualizzazione **Progettazione**, tutte le modifiche apportate all'istruzione andranno perdute.</span><span class="sxs-lookup"><span data-stu-id="b0187-105">If you switch back to the **Design** view, any changes you made to the statement will be lost.</span></span>  
  
 <span data-ttu-id="b0187-106">**Per altre informazioni:** [Istruzioni DMX &#40;Data Mining Extensions&#41; per la manipolazione dei dati](/sql/dmx/dmx-statements-data-manipulation), [Creare una query DMX in SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span><span class="sxs-lookup"><span data-stu-id="b0187-106">**For More Information:** [Data Mining Extensions &#40;DMX&#41; Data Manipulation Statements](/sql/dmx/dmx-statements-data-manipulation), [Create a DMX Query in SQL Server Management Studio](data-mining/create-a-dmx-query-in-sql-server-management-studio.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="b0187-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b0187-107">Options</span></span>  
 <span data-ttu-id="b0187-108">**Passa alla visualizzazione dei risultati della query**</span><span class="sxs-lookup"><span data-stu-id="b0187-108">**Switch to query result view**</span></span>  
 <span data-ttu-id="b0187-109">Fare clic su questo pulsante per spostarsi tra i riquadri **Progettazione**, **Query**e **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="b0187-109">Click to switch between the **Design**, **Query**, and **Result** panes.</span></span> <span data-ttu-id="b0187-110">Se si passa al riquadro **Risultato** , verrà eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="b0187-110">Switching to the **Result** pane runs the query.</span></span>  
  
 <span data-ttu-id="b0187-111">**Salva risultati query**</span><span class="sxs-lookup"><span data-stu-id="b0187-111">**Save the query result**</span></span>  
 <span data-ttu-id="b0187-112">Consente di aprire la finestra di dialogo **Salva risultati query di data mining** .</span><span class="sxs-lookup"><span data-stu-id="b0187-112">Opens the **Save Data Mining Query Result** dialog box.</span></span>  
  
 <span data-ttu-id="b0187-113">**Query singleton**</span><span class="sxs-lookup"><span data-stu-id="b0187-113">**Singleton query**</span></span>  
 <span data-ttu-id="b0187-114">Consente di generare una query singleton, in cui i dati di input vengono specificati direttamente anziché creando un riferimento a una tabella di valori di input.</span><span class="sxs-lookup"><span data-stu-id="b0187-114">Lets you create a singleton query, in which you provide the input data directly in your query instead of providing a reference to a table of input values.</span></span> <span data-ttu-id="b0187-115">La tabella **Seleziona tabelle di input** viene sostituita dalla tabella **Input query singleton** .</span><span class="sxs-lookup"><span data-stu-id="b0187-115">The **Select Input Table(s)** table is replaced by a **Singleton Query Input** table.</span></span> <span data-ttu-id="b0187-116">Se si passa a una query singleton, la query di stima corrente andrà perduta.</span><span class="sxs-lookup"><span data-stu-id="b0187-116">The current prediction query will be lost if you switch to a singleton query.</span></span>  
  
 <span data-ttu-id="b0187-117">**Aggiorna risultati query**</span><span class="sxs-lookup"><span data-stu-id="b0187-117">**Refresh query results**</span></span>  
 <span data-ttu-id="b0187-118">Consente di rielaborare la query di stima.</span><span class="sxs-lookup"><span data-stu-id="b0187-118">Reprocesses the prediction query.</span></span> <span data-ttu-id="b0187-119">Questa opzione è attivata solo nel riquadro **Risultato** .</span><span class="sxs-lookup"><span data-stu-id="b0187-119">This is enabled only in the **Result** pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0187-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0187-120">See Also</span></span>  
 <span data-ttu-id="b0187-121">[Interfacce di query di data mining](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="b0187-121">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 <span data-ttu-id="b0187-122">[Guida di riferimento alle istruzioni DMX&#41; &#40;di Data Mining Extensions](/sql/dmx/data-mining-extensions-dmx-statements) </span><span class="sxs-lookup"><span data-stu-id="b0187-122">[Data Mining Extensions &#40;DMX&#41; Statement Reference](/sql/dmx/data-mining-extensions-dmx-statements) </span></span>  
 [<span data-ttu-id="b0187-123">Generatore delle query di stima &#40;Data Mining&#41;</span><span class="sxs-lookup"><span data-stu-id="b0187-123">Prediction Query Builder &#40;Data Mining&#41;</span></span>](prediction-query-builder-data-mining.md)  
  
  
