---
title: 'Lezione 8: creare indicatori di prestazioni chiave | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a6c8ac2b-64ba-456f-b418-7bf0afe145d1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3beaab8a34844ecbd633eb5fabbacf37edfede2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714708"
---
# <a name="lesson-8-create-key-performance-indicators"></a><span data-ttu-id="8381a-102">Lezione 8: Creare indicatori di prestazioni chiave</span><span class="sxs-lookup"><span data-stu-id="8381a-102">Lesson 8: Create Key Performance Indicators</span></span>
  <span data-ttu-id="8381a-103">In questa lezione verranno creati indicatori di prestazioni chiave (KPI).</span><span class="sxs-lookup"><span data-stu-id="8381a-103">In this lesson, you will create Key Performance Indicators (KPIs).</span></span> <span data-ttu-id="8381a-104">Gli indicatori di prestazioni chiave vengono usati per misurare le prestazioni di un valore, definito mediante una misura di *base* , rispetto a un valore *target* , definito anch'esso da una misura o da un valore assoluto.</span><span class="sxs-lookup"><span data-stu-id="8381a-104">KPIs are used to gauge performance of a value, defined by a *Base* measure, against a *Target* value, also defined by a measure or by an absolute value.</span></span> <span data-ttu-id="8381a-105">Nelle applicazioni client per la creazione di report, gli indicatori KPI possono fornire ai professionisti aziendali un modo rapido e semplice per comprendere i risultati aziendali positivi nel loro complesso o per identificare tendenze significative.</span><span class="sxs-lookup"><span data-stu-id="8381a-105">In reporting client applications, KPIs can provide business professionals a quick and easy way to understand a summary of business success or to identify trends.</span></span> <span data-ttu-id="8381a-106">Per altre informazioni, vedere [KPI &#40;SSAS tabulare&#41;](tabular-models/kpis-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="8381a-106">To learn more, see [KPIs &#40;SSAS Tabular&#41;](tabular-models/kpis-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="8381a-107">Tempo previsto per il completamento della lezione: **15 minuti**</span><span class="sxs-lookup"><span data-stu-id="8381a-107">Estimated time to complete this lesson: **15 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8381a-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8381a-108">Prerequisites</span></span>  
 <span data-ttu-id="8381a-109">Questo argomento fa parte di un'esercitazione sulla creazione di modelli tabulari, con lezioni che è consigliabile completare nell'ordine indicato.</span><span class="sxs-lookup"><span data-stu-id="8381a-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="8381a-110">Prima di eseguire le attività in questa lezione è necessario aver completato la lezione precedente: [Lezione 7: Creare misure](lesson-6-create-measures.md).</span><span class="sxs-lookup"><span data-stu-id="8381a-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 7: Create Measures](lesson-6-create-measures.md).</span></span>  
  
## <a name="create-key-performance-indicators"></a><span data-ttu-id="8381a-111">Creare indicatori di prestazioni chiave</span><span class="sxs-lookup"><span data-stu-id="8381a-111">Create Key Performance Indicators</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-sales-performance-kpi"></a><span data-ttu-id="8381a-112">Per creare un indicatore KPI relativo alle prestazioni delle vendite Internet trimestrali correnti</span><span class="sxs-lookup"><span data-stu-id="8381a-112">To create an Internet Current Quarter Sales Performance KPI</span></span>  
  
1.  <span data-ttu-id="8381a-113">In Progettazione modelli fare clic sulla tabella (scheda) **Internet Sales** .</span><span class="sxs-lookup"><span data-stu-id="8381a-113">In the model designer, click the **Internet Sales** table (tab).</span></span>  
  
2.  <span data-ttu-id="8381a-114">Nella griglia delle misure fare clic su una cella vuota.</span><span class="sxs-lookup"><span data-stu-id="8381a-114">In the measure grid, click an empty cell.</span></span>  
  
3.  <span data-ttu-id="8381a-115">Nella barra della formula sopra la tabella digitare la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="8381a-115">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Sales Performance :=IFERROR([Internet Current Quarter Sales]/[Internet Previous Quarter Sales Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="8381a-116">Dopo avere completato la compilazione della formula, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8381a-116">When you have finished building the formula, press ENTER.</span></span>  
  
     <span data-ttu-id="8381a-117">Tale misura definirà fungerà da misura di base per l'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="8381a-117">This measure will serve as the Base measure for the KPI.</span></span>  
  
4.  <span data-ttu-id="8381a-118">Nella griglia delle misure fare clic con il pulsante destro del mouse sulla misura **Internet Current Quarter Sales Performance** , quindi scegliere **Crea KPI**.</span><span class="sxs-lookup"><span data-stu-id="8381a-118">In the measure grid, right-click the **Internet Current Quarter Sales Performance** measure, and then click **Create KPI**.</span></span>  
  
     <span data-ttu-id="8381a-119">Verrà visualizzata la finestra di dialogo **Indicatore di prestazioni chiave** .</span><span class="sxs-lookup"><span data-stu-id="8381a-119">The **Key Performance Indicator** dialog box opens.</span></span>  
  
5.  <span data-ttu-id="8381a-120">Nella finestra di dialogo **Indicatore di prestazioni chiave** selezionare l'opzione **Valore assoluto**in **Definisci valore di destinazione** .</span><span class="sxs-lookup"><span data-stu-id="8381a-120">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
6.  <span data-ttu-id="8381a-121">Nel campo **valore assoluto** Digitare `1.1` , quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8381a-121">In the **Absolute Value** field, type `1.1`, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="8381a-122">In **Definisci soglie stato**, nel campo del dispositivo di scorrimento a sinistra (in basso), digitare `1` e quindi nel campo del dispositivo di scorrimento a destra (alto), digitare `1.07` .</span><span class="sxs-lookup"><span data-stu-id="8381a-122">In **Define Status Thresholds**, in the left (low) slider field, type `1`, and then in the right (high) slider field, type `1.07`.</span></span>  
  
8.  <span data-ttu-id="8381a-123">In **Seleziona stile icona**selezionare un tipo di icona a rombo (rosso), triangolo (giallo) o cerchio (verde).</span><span class="sxs-lookup"><span data-stu-id="8381a-123">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="8381a-124">Si noti il campo espandibile **Descrizioni** sotto gli stili di icona disponibili.</span><span class="sxs-lookup"><span data-stu-id="8381a-124">Notice the **Descriptions** expandable field below the available icon styles.</span></span> <span data-ttu-id="8381a-125">È possibile digitare le descrizioni per i diversi elementi KPI per semplificarne l'identificazione nelle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="8381a-125">You can type descriptions for the various KPI elements to make them more identifiable in client applications.</span></span>  
  
9. <span data-ttu-id="8381a-126">Fare clic su **OK** per completare l'indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="8381a-126">Click **OK** to complete the KPI.</span></span>  
  
     <span data-ttu-id="8381a-127">Nella griglia delle misure osservare l'icona accanto alla misura **Internet Current Quarter Sales Performance** .</span><span class="sxs-lookup"><span data-stu-id="8381a-127">In the measure grid, notice the icon next to the **Internet Current Quarter Sales Performance** measure.</span></span> <span data-ttu-id="8381a-128">Questa icona indica che la misura funge da valore di base per un indicatore KPI.</span><span class="sxs-lookup"><span data-stu-id="8381a-128">This icon indicates that this measure serves as a Base value for a KPI.</span></span>  
  
#### <a name="to-create-an-internet-current-quarter-margin-performance-kpi"></a><span data-ttu-id="8381a-129">Per creare un indicatore KPI relativo alle prestazioni dei margini Internet trimestrali correnti</span><span class="sxs-lookup"><span data-stu-id="8381a-129">To create an Internet Current Quarter Margin Performance KPI</span></span>  
  
1.  <span data-ttu-id="8381a-130">Nella griglia delle misure per la tabella **Internet Sales** fare clic su una cella vuota.</span><span class="sxs-lookup"><span data-stu-id="8381a-130">In the measure grid for the **Internet Sales** table, click an empty cell.</span></span>  
  
2.  <span data-ttu-id="8381a-131">Nella barra della formula sopra la tabella digitare la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="8381a-131">In the formula bar, above the table, type the following formula:</span></span>  
  
     `Internet Current Quarter Margin Performance :=IF([Internet Previous Quarter Margin Proportion to QTD]<>0,([Internet Current Quarter Margin]-[Internet Previous Quarter Margin Proportion to QTD])/[Internet Previous Quarter Margin Proportion to QTD],BLANK())`  
  
     <span data-ttu-id="8381a-132">Dopo avere completato la compilazione della formula, premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="8381a-132">When you have finished building the formula, press ENTER.</span></span>  
  
3.  <span data-ttu-id="8381a-133">Nella griglia delle misure fare clic con il pulsante destro del mouse sulla misura **Internet Current Quarter Margin Performance** , quindi scegliere **Crea KPI**.</span><span class="sxs-lookup"><span data-stu-id="8381a-133">In the measure grid, right-click the **Internet Current Quarter Margin Performance** measure, and then click **Create KPI**.</span></span>  
  
4.  <span data-ttu-id="8381a-134">Nella finestra di dialogo **Indicatore di prestazioni chiave** selezionare l'opzione **Valore assoluto**in **Definisci valore di destinazione** .</span><span class="sxs-lookup"><span data-stu-id="8381a-134">In the **Key Performance Indicator** dialog box, in **Define Target Value**, select the **Absolute Value** option.</span></span>  
  
5.  <span data-ttu-id="8381a-135">Nel campo **valore assoluto** Digitare `1.25` .</span><span class="sxs-lookup"><span data-stu-id="8381a-135">In the **Absolute Value** field, type `1.25`.</span></span>  
  
6.  <span data-ttu-id="8381a-136">In **Definisci soglie stato**far scorrere il dispositivo di scorrimento sinistro (in basso) fino a quando non viene visualizzato **0.8**, quindi far scorrere il dispositivo di scorrimento destro (in alto) fino a quando non viene visualizzato **1.03**.</span><span class="sxs-lookup"><span data-stu-id="8381a-136">In **Define Status Thresholds**, slide the left (low) slider field until the field displays **0.8**, and then slide the right (high) slider field, until the field displays **1.03**.</span></span>  
  
7.  <span data-ttu-id="8381a-137">In **Seleziona stile icona** selezionare l'icona a forma di rombo (rossa), di triangolo (gialla) o di cerchio (verde) e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8381a-137">In **Select Icon Style**, select the diamond (red), triangle (yellow), circle (green) icon type, and then click **OK**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8381a-138">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8381a-138">Next Step</span></span>  
 <span data-ttu-id="8381a-139">Per continuare questa esercitazione, passare alla lezione successiva: [Lezione 9: Creare prospettive](lesson-8-create-perspectives.md).</span><span class="sxs-lookup"><span data-stu-id="8381a-139">To continue this tutorial, go to the next lesson: [Lesson 9: Create Perspectives](lesson-8-create-perspectives.md).</span></span>  
  
  
