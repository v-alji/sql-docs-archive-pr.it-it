---
title: Modifica etichette (SQL Server componenti aggiuntivi Data mining) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- data preparation
- relabel
- data cleaning
ms.assetid: af041b39-fdd1-4cb5-a5ef-2f3ddab84614
author: minewiskan
ms.author: owend
ms.openlocfilehash: a625676f60e2da32e19b85a94002b51eeb9ac816
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628996"
---
# <a name="relabel-sql-server-data-mining-add-ins"></a><span data-ttu-id="2fcef-102">Modifica etichette (componenti aggiuntivi Data mining di SQL Server)</span><span class="sxs-lookup"><span data-stu-id="2fcef-102">Relabel (SQL Server Data Mining Add-ins)</span></span>
  <span data-ttu-id="2fcef-103">![Icona di Office 13 per lo strumento Modifica etichette](media/dm13-relabel.gif "Icona di Office 13 per lo strumento Modifica etichette")</span><span class="sxs-lookup"><span data-stu-id="2fcef-103">![Office 13 icon for Relabel tool](media/dm13-relabel.gif "Office 13 icon for Relabel tool")</span></span>

 <span data-ttu-id="2fcef-104">Il client di data mining per Excel consente di creare nuove etichette per i dati per semplificare la comprensione dei risultati dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="2fcef-104">The Data Mining Client for Excel helps you create new labels for data to make it easier to understand the results of analysis.</span></span>

 <span data-ttu-id="2fcef-105">I motivi di modifica delle etichette includono:</span><span class="sxs-lookup"><span data-stu-id="2fcef-105">Reasons for relabeling include:</span></span>

-   <span data-ttu-id="2fcef-106">I dati includono i risultati che sono stati codificati, ad esempio 1 per maschio e 2 per femmina.</span><span class="sxs-lookup"><span data-stu-id="2fcef-106">The data includes results that were coded, such as 1 for Male and 2 for Female.</span></span>

-   <span data-ttu-id="2fcef-107">Sono valori numerici di bucket e si desidera fornire agli intervalli un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="2fcef-107">You are bucketing numeric values and want to give the ranges a descriptive name.</span></span>

-   <span data-ttu-id="2fcef-108">Si desidera semplificare i nomi lunghi.</span><span class="sxs-lookup"><span data-stu-id="2fcef-108">You want to simplify long names.</span></span>

## <a name="using-the-relabel-wizard"></a><span data-ttu-id="2fcef-109">Utilizzo della procedura guidata Modifica etichette</span><span class="sxs-lookup"><span data-stu-id="2fcef-109">Using the Relabel Wizard</span></span>

1.  <span data-ttu-id="2fcef-110">Sulla barra multifunzione **data mining** fare clic su **Pulisci** e quindi selezionare **nuova etichetta**.</span><span class="sxs-lookup"><span data-stu-id="2fcef-110">In the **Data Mining** ribbon, click **Clean** and then select **Re-Label**.</span></span>

2.  <span data-ttu-id="2fcef-111">Selezionare la tabella o l'intervallo di dati contenente i dati che si desidera correggere.</span><span class="sxs-lookup"><span data-stu-id="2fcef-111">Select the table or data range that has the data you want to fix.</span></span>

3.  <span data-ttu-id="2fcef-112">Nella pagina modifica **etichette** della procedura guidata selezionare una singola colonna scegliendo la colonna nell'elenco a discesa oppure facendo clic sulla colonna nel riquadro **esempi di dati** .</span><span class="sxs-lookup"><span data-stu-id="2fcef-112">In the **Re-label** page of the wizard, select a single column, either by choosing the column from the dropdown list, or by clicking the column in the **Data samples** pane.</span></span>

     <span data-ttu-id="2fcef-113">Il riquadro **esempi di dati** Mostra solo circa 50 righe di dati, ma sono campionate per assicurarsi che venga visualizzata una corretta distribuzione dei valori.</span><span class="sxs-lookup"><span data-stu-id="2fcef-113">The **Data samples** pane only shows about 50 rows of data, but they are sampled to ensure that you see a good spread of values.</span></span>

     <span data-ttu-id="2fcef-114">Fare clic sull'intestazione di colonna per **conteggio** per eseguire l'ordinamento in base al conteggio di ogni valore.</span><span class="sxs-lookup"><span data-stu-id="2fcef-114">Click the column header for **Count** to sort by the count of each value.</span></span>

     <span data-ttu-id="2fcef-115">È anche possibile eseguire l'ordinamento in base alle **etichette originali**, che risulta utile se si desidera rietichettare prima tutti i valori più alti o più bassi.</span><span class="sxs-lookup"><span data-stu-id="2fcef-115">You can also sort by **Original Labels**, which is handy if you want to re-label all the highest or lowest values first.</span></span>

4.  <span data-ttu-id="2fcef-116">Nella pagina **nuova etichetta** dati della procedura guidata, esaminare i valori nella colonna **etichette originali** e decidere come si desidera raggrupparli o modificarli.</span><span class="sxs-lookup"><span data-stu-id="2fcef-116">In the **Re-label** data page of the wizard, review the values in the **Original Labels** column, and decide how you want to group or edit them.</span></span>

5.  <span data-ttu-id="2fcef-117">Digitare un nuovo valore nella riga sotto **nuove etichette**.</span><span class="sxs-lookup"><span data-stu-id="2fcef-117">Type a new value into the row under **New Labels**.</span></span> <span data-ttu-id="2fcef-118">È inoltre possibile scegliere un valore nell'elenco dei valori esistenti.</span><span class="sxs-lookup"><span data-stu-id="2fcef-118">You can also choose a value from the list of existing values.</span></span> <span data-ttu-id="2fcef-119">Mentre si digitano, i nuovi valori diventano disponibili per essere subito riutilizzati.</span><span class="sxs-lookup"><span data-stu-id="2fcef-119">As you type new values, they become available for re-use right away.</span></span>

6.  <span data-ttu-id="2fcef-120">Dopo aver immesso un numero sufficiente di righe, fare clic su **Avanti**. nella pagina **Seleziona destinazione** scegliere il percorso in cui verranno salvati i dati rietichettati.</span><span class="sxs-lookup"><span data-stu-id="2fcef-120">When you have entered enough rows, click **Next**, and on the **Select Destination** page, choose where you'll save the relabeled data.</span></span>

    -   <span data-ttu-id="2fcef-121">**Aggiungi come nuova colonna al foglio di lavoro corrente**</span><span class="sxs-lookup"><span data-stu-id="2fcef-121">**Add as a new column to the current worksheet**</span></span>

         <span data-ttu-id="2fcef-122">Fare clic per aggiungere una nuova colonna alla tabella contenente i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="2fcef-122">Click to add a new column to the table that contains the new values.</span></span>

    -   <span data-ttu-id="2fcef-123">**Copia i dati del foglio modificati in un nuovo foglio di lavoro**</span><span class="sxs-lookup"><span data-stu-id="2fcef-123">**Copy sheet data with changes to a new worksheet**</span></span>

         <span data-ttu-id="2fcef-124">Fare clic per creare un nuovo foglio di lavoro contenente i dati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="2fcef-124">Click to create a new worksheet that contains the updated data.</span></span>

    -   <span data-ttu-id="2fcef-125">**Modifica dati nella posizione originale**</span><span class="sxs-lookup"><span data-stu-id="2fcef-125">**Change data in place**</span></span>

         <span data-ttu-id="2fcef-126">Fare clic per sostituire i dati originali con i nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="2fcef-126">Click to replace the original data with the new values.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fcef-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fcef-127">See Also</span></span>
 [<span data-ttu-id="2fcef-128">Esplorazione e pulizia dei dati</span><span class="sxs-lookup"><span data-stu-id="2fcef-128">Exploring and Cleaning Data</span></span>](exploring-and-cleaning-data.md)


