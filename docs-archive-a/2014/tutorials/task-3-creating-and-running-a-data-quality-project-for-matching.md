---
title: 'Attività 3: creazione ed esecuzione di un progetto Data Quality per la corrispondenza | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6260e911-ea8b-4c69-a39d-d1bccd565a32
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 221d6d583c61ee035c20fcb63f0ed5278f2b8678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625098"
---
# <a name="task-3-creating-and-running-a-data-quality-project-for-matching"></a><span data-ttu-id="30bbd-102">Attività 3: Creazione ed esecuzione di un progetto Data Quality per la corrispondenza</span><span class="sxs-lookup"><span data-stu-id="30bbd-102">Task 3: Creating and Running a Data Quality Project for Matching</span></span>
  <span data-ttu-id="30bbd-103">In questa attività viene creato un progetto Data Quality per l'attività di corrispondenza e viene eseguito il processo di corrispondenza nei dati puliti del fornitore per rimuovere tutti i duplicati nei dati.</span><span class="sxs-lookup"><span data-stu-id="30bbd-103">In this task, you create a Data Quality Project for the matching activity and run the matching process on cleansed supplier data to remove any duplicates in the data.</span></span>

1.  <span data-ttu-id="30bbd-104">Nella pagina principale del **client DQS**fare clic su **nuovo progetto Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="30bbd-104">On the main page of **DQS Client**, click **New Data Quality Project**.</span></span>

2.  <span data-ttu-id="30bbd-105">Digitare **Remove Supplier Duplicates** dal **nome del progetto**.</span><span class="sxs-lookup"><span data-stu-id="30bbd-105">Type **Remove Supplier Duplicates** from the **Name of the project**.</span></span>

3.  <span data-ttu-id="30bbd-106">Selezionare **Suppliers** nell'elenco di KB per il campo **Usa Knowledge base** .</span><span class="sxs-lookup"><span data-stu-id="30bbd-106">Select **Suppliers** from the list of KBs for the **Use Knowledge Base** field.</span></span> <span data-ttu-id="30bbd-107">Sono stati creati i criteri di corrispondenza in questa Knowledge Base nella lezione precedente.</span><span class="sxs-lookup"><span data-stu-id="30bbd-107">You have created a matching policy in this knowledge base in the previous lesson.</span></span>

4.  <span data-ttu-id="30bbd-108">Selezionare **corrispondente** nell' **elenco di attività** nel riquadro in basso a destra.</span><span class="sxs-lookup"><span data-stu-id="30bbd-108">Select **Matching** from the **list of activities** from the bottom-right pane.</span></span>

     <span data-ttu-id="30bbd-109">![Nuovo progetto Data Quality - Corrispondenza selezionata](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "Nuovo progetto Data Quality - Corrispondenza selezionata")</span><span class="sxs-lookup"><span data-stu-id="30bbd-109">![New Data Quality Project - Matching Selected](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "New Data Quality Project - Matching Selected")</span></span>

5.  <span data-ttu-id="30bbd-110">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="30bbd-110">Click **Next**.</span></span>

6.  <span data-ttu-id="30bbd-111">Nella pagina **Mappa** selezionare **File di Excel** per **Origine dati**.</span><span class="sxs-lookup"><span data-stu-id="30bbd-111">In the **Map** page, select **Excel File** for **Data Source**.</span></span>

7.  <span data-ttu-id="30bbd-112">Fare clic su **Sfoglia** e selezionare **cleaned Supplier List.xls**, ovvero il file di output dell'attività di pulizia.</span><span class="sxs-lookup"><span data-stu-id="30bbd-112">Click **Browse** and select **Cleansed Supplier List.xls**, which is the output file from the cleansing activity.</span></span>

8.  <span data-ttu-id="30bbd-113">Eseguire il mapping della colonna di origine **SupplierID** al dominio **Supplier ID** , della colonna **Supplier** Name al dominio **Supplier Name** e della colonna **ContactEmailAddress** al dominio **Contact email** .</span><span class="sxs-lookup"><span data-stu-id="30bbd-113">Map **SupplierID** source column to the **Supplier ID** domain, **Supplier Name** column to **Supplier Name** domain, and **ContactEmailAddress** column to **Contact Email** domain.</span></span>

9. <span data-ttu-id="30bbd-114">Fare clic su **Avanti** per passare alla pagina **corrispondente** .</span><span class="sxs-lookup"><span data-stu-id="30bbd-114">Click **Next** to switch to the **Matching** page.</span></span>

10. <span data-ttu-id="30bbd-115">Fare clic su **Avvia** per avviare il processo di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="30bbd-115">Click **Start** to start the matching process.</span></span> <span data-ttu-id="30bbd-116">Verranno visualizzati risultati simili a quelli dell'attività precedente poiché è stato utilizzato lo stesso file di input per la definizione dei criteri di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="30bbd-116">You should see results similar to those from the previous task because you used the same input file for defining the matching policy.</span></span>

11. <span data-ttu-id="30bbd-117">Controllare tutti i record corrispondenti e il punteggio di corrispondenza nella casella di riepilogo.</span><span class="sxs-lookup"><span data-stu-id="30bbd-117">Review all the matched records and their matching score in the list box.</span></span> <span data-ttu-id="30bbd-118">I risultati devono essere uguali a quelli visualizzati nell'attività precedente.</span><span class="sxs-lookup"><span data-stu-id="30bbd-118">The results should be same as the ones you saw in the previous task.</span></span> <span data-ttu-id="30bbd-119">Vedere i passaggi dell'attività precedente per analizzare i risultati di questa attività di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="30bbd-119">See the steps in the previous task to analyze the results from this matching activity.</span></span>

12. <span data-ttu-id="30bbd-120">Fare clic su **Avanti** per passare alla pagina **Esporta** .</span><span class="sxs-lookup"><span data-stu-id="30bbd-120">Click **Next** to switch to the **Export** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="30bbd-121">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="30bbd-121">Next Step</span></span>
 [<span data-ttu-id="30bbd-122">Attività 4: Esportazione dei risultati dell'attività di corrispondenza in un file di Excel</span><span class="sxs-lookup"><span data-stu-id="30bbd-122">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>](../../2014/tutorials/task-4-exporting-the-results-from-matching-activity-to-an-excel-file.md)


