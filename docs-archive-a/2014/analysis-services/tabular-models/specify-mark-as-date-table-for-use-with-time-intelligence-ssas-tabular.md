---
title: Specificare Contrassegna come tabella data per l'uso con la funzionalità di Business Intelligence per l'ora (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 30841d1f-0c3b-4575-8f4a-27a1492e248c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 81038369b8cb8636a2aa216f1c26783a96d5f7ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711040"
---
# <a name="specify-mark-as-date-table-for-use-with-time-intelligence-ssas-tabular"></a><span data-ttu-id="94c82-102">Specificare Contrassegna come tabella data per l'utilizzo con funzionalità di Business Intelligence per le gerarchie temporali (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="94c82-102">Specify Mark as Date Table for use with Time Intelligence (SSAS Tabular)</span></span>
  <span data-ttu-id="94c82-103">Per utilizzare le funzionalità di Business Intelligence per le gerarchie temporali nelle formule DAX, è necessario specificare una tabella relativa alla data e una colonna (datetime) dell'identificatore univoco del tipo di dati Date.</span><span class="sxs-lookup"><span data-stu-id="94c82-103">In order to use time intelligence functions in DAX formulas, you must specify a date table and a unique identifier (datetime) column of the Date data type.</span></span> <span data-ttu-id="94c82-104">Una volta specificata una colonna nella tabella relativa alla data come identificatore univoco, è possibile creare le relazioni tra le colonne nella tabella in questione e tutte le tabelle dei fatti.</span><span class="sxs-lookup"><span data-stu-id="94c82-104">Once a column in the date table is specified as a unique identifier, you can create relationships between columns in the date table and any fact tables.</span></span>  
  
 <span data-ttu-id="94c82-105">In caso di utilizzo delle funzioni di Business Intelligence per le gerarchie temporali, sono valide le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="94c82-105">When using time intelligence functions, the following rules apply:</span></span>  
  
-   <span data-ttu-id="94c82-106">Quando si utilizzano funzioni di Business Intelligence per le gerarchie temporali di DAX, non specificare mai una colonna di tipo datetime da una tabella dei fatti.</span><span class="sxs-lookup"><span data-stu-id="94c82-106">When using DAX time intelligence functions, never specify a datetime column from a fact table.</span></span> <span data-ttu-id="94c82-107">Creare sempre una tabella relativa alla data separata nel modello con almeno un colonna di tipo datetime con tipo di dati Date e con valori univoci.</span><span class="sxs-lookup"><span data-stu-id="94c82-107">Always create a separate date table in your model with at least one datetime column of Date data type and with unique values.</span></span>  
  
-   <span data-ttu-id="94c82-108">Verificare che la tabella relativa alla data disponga di un intervallo di date continuo.</span><span class="sxs-lookup"><span data-stu-id="94c82-108">Make sure your date table has a continuous date range.</span></span>  
  
-   <span data-ttu-id="94c82-109">È consigliabile che la granularità della colonna di tipo datetime nella tabella relativa alla data sia a livello di giorno, senza frazioni di un giorno.</span><span class="sxs-lookup"><span data-stu-id="94c82-109">The datetime column in the date table should be at day granularity (without fractions of a day).</span></span>  
  
-   <span data-ttu-id="94c82-110">È necessario specificare una tabella relativa alla data e una colonna dell'identificatore univoco utilizzando la finestra di dialogo **Contrassegna come tabella data** .</span><span class="sxs-lookup"><span data-stu-id="94c82-110">You must specify a date table and a unique identifier column by using the **Mark the Date Table** dialog box.</span></span>  
  
-   <span data-ttu-id="94c82-111">Creare le relazioni tra le tabelle dei fatti e le colonne di tipo di dati Date nella tabella relativa alla data.</span><span class="sxs-lookup"><span data-stu-id="94c82-111">Create relationships between fact tables and columns of Date data type in the date table.</span></span>  
  
#### <a name="to-specify-a-date-table-and-unique-identifier"></a><span data-ttu-id="94c82-112">Per specificare una tabella relativa alla data e un identificatore univoco</span><span class="sxs-lookup"><span data-stu-id="94c82-112">To specify a date table and unique identifier</span></span>  
  
1.  <span data-ttu-id="94c82-113">In Progettazione modelli fare clic sulla tabella relativa alla data.</span><span class="sxs-lookup"><span data-stu-id="94c82-113">In the model designer, click the date table.</span></span>  
  
2.  <span data-ttu-id="94c82-114">Fare clic sul menu **Tabella** , selezionare **Data**, quindi scegliere **Contrassegna come tabella data**</span><span class="sxs-lookup"><span data-stu-id="94c82-114">Click the **Table** menu, then click **Date**, and then click **Mark as Date Table**</span></span>  
  
3.  <span data-ttu-id="94c82-115">Nella casella di riepilogo **Data** della finestra di dialogo **Contrassegna come tabella data** selezionare una colonna da utilizzare come identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="94c82-115">In the **Mark as Date Table** dialog box, in the **Date** listbox, select a column to be used as a unique identifier.</span></span> <span data-ttu-id="94c82-116">In questa colonna devono essere inclusi valori univoci e il tipo di dati utilizzato deve essere Date.</span><span class="sxs-lookup"><span data-stu-id="94c82-116">This column must contain unique values and should be of Date data type.</span></span> <span data-ttu-id="94c82-117">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="94c82-117">For example:</span></span>  
  
    |<span data-ttu-id="94c82-118">Data</span><span class="sxs-lookup"><span data-stu-id="94c82-118">Date</span></span>|  
    |----------|  
    |<span data-ttu-id="94c82-119">7/1/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="94c82-119">7/1/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="94c82-120">7/2/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="94c82-120">7/2/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="94c82-121">7/3/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="94c82-121">7/3/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="94c82-122">7/4/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="94c82-122">7/4/2010 12:00:00 AM</span></span>|  
    |<span data-ttu-id="94c82-123">7/5/2010 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="94c82-123">7/5/2010 12:00:00 AM</span></span>|  
  
4.  <span data-ttu-id="94c82-124">Se necessario, creare tutte le relazioni tra le tabelle dei fatti e la tabella relativa alla data.</span><span class="sxs-lookup"><span data-stu-id="94c82-124">If necessary, create any relationships between fact tables and the date table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c82-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94c82-125">See Also</span></span>  
 <span data-ttu-id="94c82-126">[Calcoli &#40;SSAS tabulare&#41;](calculations-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="94c82-126">[Calculations &#40;SSAS Tabular&#41;](calculations-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="94c82-127">Funzioni di Business Intelligence per le attività temporali &#40;&#41;DAX</span><span class="sxs-lookup"><span data-stu-id="94c82-127">Time Intelligence Functions &#40;DAX&#41;</span></span>](/dax/time-intelligence-functions-dax)  
  
  
