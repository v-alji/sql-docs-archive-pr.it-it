---
title: Finestra di dialogo Specifica mapping colonne (grafico accuratezza modello di data mining) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.miningmodeleditor.accuracychart.coltotablecolmapping.f1
ms.assetid: 68e9e2d2-173f-4363-a515-fc60bfee3af0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8ede835567f678f4152b3d1944f3c2c7160c6837
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635776"
---
# <a name="specify-column-mapping-dialog-box-mining-accuracy-chart"></a><span data-ttu-id="1f945-102">Finestra di dialogo Impostazione mapping colonne (Grafico accuratezza modello di data mining)</span><span class="sxs-lookup"><span data-stu-id="1f945-102">Specify Column Mapping Dialog Box (Mining Accuracy Chart)</span></span>
  <span data-ttu-id="1f945-103">Usare la scheda **Impostazione mapping colonne** per selezionare tabelle da un'origine dati esterna ed eseguire il mapping delle colonne a un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="1f945-103">Use the **Specify Column Mapping** tab to select tables from an external data source and map the columns to a data mining model.</span></span> <span data-ttu-id="1f945-104">È quindi possibile utilizzare i dati esterni per eseguire il test dell'accuratezza di un modello di data mining e visualizzare i risultati nel grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="1f945-104">You can then use the external data to test the accuracy of a mining model and displays the results in the accuracy chart.</span></span>  
  
 <span data-ttu-id="1f945-105">**Per altre informazioni:** [Test e convalida &#40;Data mining&#41;](data-mining/testing-and-validation-data-mining.md)</span><span class="sxs-lookup"><span data-stu-id="1f945-105">**For more information:** [Testing and Validation &#40;Data Mining&#41;](data-mining/testing-and-validation-data-mining.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="1f945-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="1f945-106">Options</span></span>  
 <span data-ttu-id="1f945-107">**Struttura di data mining**</span><span class="sxs-lookup"><span data-stu-id="1f945-107">**Mining Structure**</span></span>  
 <span data-ttu-id="1f945-108">Consente di visualizzare la struttura di data mining selezionata contenente il modello di cui verrà eseguito il test.</span><span class="sxs-lookup"><span data-stu-id="1f945-108">Displays the selected mining structure that contains the model that you will test.</span></span>  
  
 <span data-ttu-id="1f945-109">**Seleziona struttura**</span><span class="sxs-lookup"><span data-stu-id="1f945-109">**Select Structure**</span></span>  
 <span data-ttu-id="1f945-110">Fare clic per aprire la finestra di dialogo **Seleziona struttura di data mining** e selezionare una struttura di data mining diversa.</span><span class="sxs-lookup"><span data-stu-id="1f945-110">Click to open the **Select Mining Structure** dialog box and select a different mining structure.</span></span>  
  
 <span data-ttu-id="1f945-111">**Seleziona tabella/e di input**</span><span class="sxs-lookup"><span data-stu-id="1f945-111">**Select Input Table(s)**</span></span>  
 <span data-ttu-id="1f945-112">Consente di visualizzare le tabelle di input selezionate che sono utilizzate per la creazione del grafico di accuratezza.</span><span class="sxs-lookup"><span data-stu-id="1f945-112">Displays the selected input tables that are used to generate the lift chart.</span></span> <span data-ttu-id="1f945-113">Selezionare la tabella che contiene i dati di test da utilizzare per verificare l'accuratezza dei modelli.</span><span class="sxs-lookup"><span data-stu-id="1f945-113">Select the table that contains the test data that you will use to test the accuracy of the models.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1f945-114">Se il riquadro non contiene alcuna tabella, fare clic su **Seleziona tabella del case** per aggiungere tabelle da una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="1f945-114">If the pane does not contain any tables, click **Select Case Table** to add tables from a data source view.</span></span>  
  
 <span data-ttu-id="1f945-115">**Rimuovi tabella**</span><span class="sxs-lookup"><span data-stu-id="1f945-115">**Remove Table**</span></span>  
 <span data-ttu-id="1f945-116">Consente di rimuovere la tabella selezionata.</span><span class="sxs-lookup"><span data-stu-id="1f945-116">Removes the selected table.</span></span> <span data-ttu-id="1f945-117">Questo pulsante è disabilitato se non è stata selezionata una tabella oppure se nell'elenco **Seleziona tabella/e di input** non ne viene visualizzata alcuna.</span><span class="sxs-lookup"><span data-stu-id="1f945-117">This button is disabled if a table has not been selected or if no tables are displayed in the **Select Input Tables** list.</span></span>  
  
 <span data-ttu-id="1f945-118">**Seleziona tabella del case**</span><span class="sxs-lookup"><span data-stu-id="1f945-118">**Select Case Table**</span></span>  
 <span data-ttu-id="1f945-119">Fare clic per aprire la finestra di dialogo **Seleziona tabella** e selezionare una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="1f945-119">Click to open the **Select Table** dialog box and select a data source view.</span></span>  
  
 <span data-ttu-id="1f945-120">**Nota** Questo pulsante viene visualizzato solo se non è stata selezionata una tabella del case.</span><span class="sxs-lookup"><span data-stu-id="1f945-120">**Note** This button appears only if a case table has not been selected.</span></span> <span data-ttu-id="1f945-121">Per attivare il pulsante in modo da selezionare una diversa tabella del case, cancellare l'elenco selezionando tutte le tabelle esistenti e facendo clic su **Rimuovi tabella**.</span><span class="sxs-lookup"><span data-stu-id="1f945-121">To enable the button so that you can select a different case table, clear the list by selecting all existing tables and then clicking **Remove Table**.</span></span>  
  
 <span data-ttu-id="1f945-122">**Seleziona tabella nidificata**</span><span class="sxs-lookup"><span data-stu-id="1f945-122">**Select Nested Table**</span></span>  
 <span data-ttu-id="1f945-123">Consente di aprire la finestra di dialogo **Seleziona tabella** .</span><span class="sxs-lookup"><span data-stu-id="1f945-123">Opens the **Select Table** dialog box.</span></span> <span data-ttu-id="1f945-124">Questo pulsante viene visualizzato solo se è stata selezionata una tabella del case.</span><span class="sxs-lookup"><span data-stu-id="1f945-124">This button appears only if a case table has been selected.</span></span> <span data-ttu-id="1f945-125">Se nella struttura di data mining associata non è inclusa una tabella nidificata, il pulsante è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="1f945-125">If the associated mining structure does not contain a nested table, this button is disabled.</span></span>  
  
 <span data-ttu-id="1f945-126">**Modifica join**</span><span class="sxs-lookup"><span data-stu-id="1f945-126">**Modify Join**</span></span>  
 <span data-ttu-id="1f945-127">Consente di aprire la finestra di dialogo **Specifica join nidificato** .</span><span class="sxs-lookup"><span data-stu-id="1f945-127">Opens the **Specify Nested Join** dialog box.</span></span> <span data-ttu-id="1f945-128">Questo pulsante è attivo solo se si seleziona una tabella nidificata.</span><span class="sxs-lookup"><span data-stu-id="1f945-128">This button is active only if the nested table is selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f945-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f945-129">See Also</span></span>  
 <span data-ttu-id="1f945-130">[Attività e procedure di test e convalida &#40;di data mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="1f945-130">[Testing and Validation Tasks and How-tos &#40;Data Mining&#41;](data-mining/testing-and-validation-tasks-and-how-tos-data-mining.md) </span></span>  
 [<span data-ttu-id="1f945-131">Progettazione Grafico accuratezza modello di data mining &#40;&#41;di data mining</span><span class="sxs-lookup"><span data-stu-id="1f945-131">Mining Accuracy Chart Designer &#40;Data Mining&#41;</span></span>](mining-accuracy-chart-designer-data-mining.md)  
  
  
