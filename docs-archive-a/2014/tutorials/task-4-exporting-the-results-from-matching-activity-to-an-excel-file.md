---
title: "Attività 4: esportazione dei risultati dall'attività di corrispondenza in un file di Excel | Microsoft Docs"
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 644454c4-3c5a-469a-90ec-e51dc7fb99fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b583e44f887fc0595fb904ec977f1de28c2fecd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720417"
---
# <a name="task-4-exporting-the-results-from-matching-activity-to-an-excel-file"></a><span data-ttu-id="da134-102">Attività 4: Esportazione dei risultati dell'attività di corrispondenza in un file di Excel</span><span class="sxs-lookup"><span data-stu-id="da134-102">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>
  <span data-ttu-id="da134-103">In questa attività vengono esportati i risultati dell'attività di corrispondenza in un file di Excel.</span><span class="sxs-lookup"><span data-stu-id="da134-103">In this task, you export the results from the matching activity to an Excel file.</span></span>

1.  <span data-ttu-id="da134-104">Nella pagina **Esporta** selezionare il **file di Excel** per il **tipo di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="da134-104">In the **Export** page, select **Excel File** for the **Destination Type**.</span></span>

2.  <span data-ttu-id="da134-105">Selezionare l'opzione **risultati sopravvivenza** .</span><span class="sxs-lookup"><span data-stu-id="da134-105">Select **Survivorship Results** option.</span></span> <span data-ttu-id="da134-106">Nel processo di sopravvivenza, DQS determina un record superstite per ogni cluster in base alla **regola di sopravvivenza** selezionata.</span><span class="sxs-lookup"><span data-stu-id="da134-106">In the survivorship process, DQS determines a survivor record for each cluster based on the **Survivorship Rule** you selected.</span></span>

3.  <span data-ttu-id="da134-107">Fare clic su **Sfoglia** e passare alla cartella in cui si desidera archiviare il file di output.</span><span class="sxs-lookup"><span data-stu-id="da134-107">Click **Browse** and navigate to the folder where you want to store the output file.</span></span>

4.  <span data-ttu-id="da134-108">Digitare **Cleansed and matched Suppliers.xls** per il nome e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="da134-108">Type **Cleansed and Matched Suppliers.xls** for the name and click **Open**.</span></span>

5.  <span data-ttu-id="da134-109">Verificare che il **record pivot** sia selezionato per la **regola di sopravvivenza**.</span><span class="sxs-lookup"><span data-stu-id="da134-109">Confirm that **Pivot Record** is selected for the **Survivorship Rule**.</span></span> <span data-ttu-id="da134-110">Quando si seleziona questa opzione, come output da un cluster viene selezionato il record pivot per ogni cluster.</span><span class="sxs-lookup"><span data-stu-id="da134-110">When you select this option, the pivot record for each cluster is picked for the output from a cluster.</span></span> <span data-ttu-id="da134-111">Di seguito sono riportate le altre opzioni per la regola di sopravvivenza:</span><span class="sxs-lookup"><span data-stu-id="da134-111">The other options for the Survivorship Rule are:</span></span>

    1.  <span data-ttu-id="da134-112">**Record più completo:** Il record superstite è quello con il maggior numero di campi popolati.</span><span class="sxs-lookup"><span data-stu-id="da134-112">**Most complete record:** Survivor record is the one with the largest number of populated fields.</span></span>

    2.  <span data-ttu-id="da134-113">**Record più lungo:** Il record superstite è quello con il maggior numero di termini nei campi di origine.</span><span class="sxs-lookup"><span data-stu-id="da134-113">**Longest record:** Survivor record is the one with the largest number of terms in source fields.</span></span>

    3.  <span data-ttu-id="da134-114">Il **record più completo e più lungo:** Il record superstite è quello con il maggior numero di campi popolati e presenta il maggior numero di termini in ogni campo.</span><span class="sxs-lookup"><span data-stu-id="da134-114">**Most complete and longest record:** Survivor record is the one with the largest number of populated fields, and has the largest number of terms in each field.</span></span>

     <span data-ttu-id="da134-115">![Esporta risultati dalla pagina Corrispondenza](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Esporta risultati dalla pagina Corrispondenza")</span><span class="sxs-lookup"><span data-stu-id="da134-115">![Export Results from Matching Page](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Export Results from Matching Page")</span></span>

6.  <span data-ttu-id="da134-116">Fare clic su **Esporta** per esportare i risultati in un file di Excel.</span><span class="sxs-lookup"><span data-stu-id="da134-116">Click **Export** to export the results to an Excel file.</span></span>

7.  <span data-ttu-id="da134-117">Fare clic su **Chiudi** per chiudere la finestra di dialogo **esportazione corrispondente** .</span><span class="sxs-lookup"><span data-stu-id="da134-117">Click **Close** to close the **Matching Export** dialog box.</span></span>

8.  <span data-ttu-id="da134-118">Fare clic su **fine** per completare l'attività di corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="da134-118">Click **Finish** to finish the matching activity.</span></span>

9. <span data-ttu-id="da134-119">Aprire il file di **Suppliers.xlsxpulito e corrispondente** e verificare che non vengano visualizzati duplicati (SupplierID).</span><span class="sxs-lookup"><span data-stu-id="da134-119">Open the **Cleansed and Matched Suppliers.xlsx** file and confirm that you do not see any duplicates (SupplierID).</span></span>

 <span data-ttu-id="da134-120">A questo punto, si dispone di dati fornitore puliti e di cui è stata effettuata la corrispondenza per rimuovere i duplicati.</span><span class="sxs-lookup"><span data-stu-id="da134-120">Now, you have supplier data that has been cleansed and matched to remove duplicates.</span></span>

## <a name="next-step"></a><span data-ttu-id="da134-121">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="da134-121">Next Step</span></span>
 [<span data-ttu-id="da134-122">Lezione 4: Archiviazione dei dati fornitore in MDS</span><span class="sxs-lookup"><span data-stu-id="da134-122">Lesson 4: Storing Supplier Data in MDS</span></span>](../../2014/tutorials/lesson-4-storing-supplier-data-in-mds.md)


