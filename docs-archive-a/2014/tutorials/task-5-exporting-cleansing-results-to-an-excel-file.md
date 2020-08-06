---
title: 'Attività 5: esportazione dei risultati della pulizia in un file di Excel | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: eaeafd65-d0d4-4a7d-a3ad-110ef644e90b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0dbdc1bef348e03e211e4933132985ea2c089b97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635906"
---
# <a name="task-5-exporting-cleansing-results-to-an-excel-file"></a><span data-ttu-id="7d2b3-102">Attività 5: Esportazione dei risultati della pulizia in un file di Excel</span><span class="sxs-lookup"><span data-stu-id="7d2b3-102">Task 5: Exporting Cleansing Results to an Excel File</span></span>
  <span data-ttu-id="7d2b3-103">In questa attività vengono esportati i risultati dell'attività di pulizia in un file di Excel.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-103">In this task, you export results from the cleansing activity to an Excel file.</span></span> <span data-ttu-id="7d2b3-104">Per ulteriori informazioni, vedere l'argomento relativo alla [fase di esportazione](https://msdn.microsoft.com/library/hh213061.aspx#Export) .</span><span class="sxs-lookup"><span data-stu-id="7d2b3-104">See [Export Stage](https://msdn.microsoft.com/library/hh213061.aspx#Export) topic for more details.</span></span>  
  
1.  <span data-ttu-id="7d2b3-105">Nel riquadro di destra selezionare **Excel** per il **tipo di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-105">In the right pane, select **Excel** for the **Destination Type**.</span></span>  
  
2.  <span data-ttu-id="7d2b3-106">Fare clic su **Sfoglia**, specificare il nome del file di output come **Fornitore pulito List.xls**, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-106">Click **Browse**, specify the output file name as **Cleansed Supplier List.xls**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="7d2b3-107">Selezionare **solo i dati** per il formato di **output** per esportare solo i dati puliti.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-107">Select **Data Only** for the **Output** format to export just the cleansed data.</span></span> <span data-ttu-id="7d2b3-108">La seconda opzione, **dati e informazioni pulizia**, consente di esportare i dettagli delle attività di pulizia insieme ai dati puliti.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-108">The second option, **Data and Cleansing Info**, lets you export cleansing activity details along with the cleansed data.</span></span> <span data-ttu-id="7d2b3-109">L'opzione **standardizzazione formato** consente di applicare i formati di output definiti in un dominio ai valori di tale dominio.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-109">The **Standardize Format** option lets you apply any output formats you define on a domain to the values of that domain.</span></span> <span data-ttu-id="7d2b3-110">Non è stato definito un formato di output in un dominio nell'esercitazione.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-110">You have not defined an output format on any domain in the tutorial.</span></span>  
  
     <span data-ttu-id="7d2b3-111">![Pagina Esporta risultati pulizia](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Pagina Esporta risultati pulizia")</span><span class="sxs-lookup"><span data-stu-id="7d2b3-111">![Export Cleansing Results Page](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Export Cleansing Results Page")</span></span>  
  
4.  <span data-ttu-id="7d2b3-112">Fare clic su **Esporta** per esportare i dati.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-112">Click **Export** to export the data.</span></span> <span data-ttu-id="7d2b3-113">Non fare ancora clic su **fine** .</span><span class="sxs-lookup"><span data-stu-id="7d2b3-113">Do not click **Finish** yet.</span></span>  
  
5.  <span data-ttu-id="7d2b3-114">Fare clic su **Chiudi** nella finestra di dialogo **esportazione** .</span><span class="sxs-lookup"><span data-stu-id="7d2b3-114">Click **Close** on the **Exporting** dialog box.</span></span>  
  
6.  <span data-ttu-id="7d2b3-115">Fare clic su **fine** per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-115">Click **Finish** to finish the activity.</span></span> <span data-ttu-id="7d2b3-116">Se si dimentica di esportare i risultati prima di fare clic su **fine**, fare clic su **Apri progetto Data Quality** nella pagina principale del **client DQS**, selezionare **Pulisci fornitore** dall'elenco di progetti e fare clic su **Avanti** nella parte inferiore della schermata per tornare alla fase di **esportazione** del processo di pulizia.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-116">If you forgot to export results before clicking **Finish**, click **Open Data Quality Project** in the main page of **DQS Client**, select **Cleanse Supplier List** from the list of projects, and click **Next** at the bottom of the screen to get to the **Export** stage of cleansing process again.</span></span> <span data-ttu-id="7d2b3-117">È anche possibile passare alla scheda **Gestisci e visualizza risultati** facendo clic sul pulsante **indietro** .</span><span class="sxs-lookup"><span data-stu-id="7d2b3-117">You can also switch to **Manage and View Results** tab by clicking **Back** button.</span></span>  
  
7.  <span data-ttu-id="7d2b3-118">Aprire il **List.xlsfornitore pulito** ed eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d2b3-118">Open the **Cleansed Supplier List.xls** and do the following:</span></span>  
  
    1.  <span data-ttu-id="7d2b3-119">Verificare che non esistano indirizzi di posta elettronica che terminano con adventure-work.com (senza carattere ') cercando adventure-work.com nel foglio di.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-119">Ensure that there are no email addresses that end with adventure-work.com (without character 's') by searching for adventure-work.com in the worksheet.</span></span>  
  
    2.  <span data-ttu-id="7d2b3-120">Vedere che non è presente alcun valore di **USA** nella colonna **Country** .</span><span class="sxs-lookup"><span data-stu-id="7d2b3-120">See that there is no **USA** value in the **Country** column.</span></span>  
  
    3.  <span data-ttu-id="7d2b3-121">Cercare **Los Angeles** e verificare che lo **stato** sia impostato su **CA**.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-121">Search for **Los Angeles** and see that the **State** is set to **CA**.</span></span>  
  
    4.  <span data-ttu-id="7d2b3-122">Verificare che non siano presenti termini **Co.**, **Corp.** e **Inc.**</span><span class="sxs-lookup"><span data-stu-id="7d2b3-122">Confirm that there are no terms **Co.**, **Corp.**, and **Inc.**.</span></span>  
  
    5.  <span data-ttu-id="7d2b3-123">Eliminare la colonna **convalida indirizzo** dal foglio di calcolo e salvare il file di Excel.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-123">Delete the **Address Validation** column from the spreadsheet and save the excel file.</span></span> <span data-ttu-id="7d2b3-124">Questa colonna aggiuntiva corrisponde al dominio composito Address Validation.</span><span class="sxs-lookup"><span data-stu-id="7d2b3-124">This additional column corresponds to the Address Validation composite domain.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="7d2b3-125">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="7d2b3-125">Next Step</span></span>  
 [<span data-ttu-id="7d2b3-126">Attività 6: Importazione di valori dal progetto Cleanse Supplier List</span><span class="sxs-lookup"><span data-stu-id="7d2b3-126">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>](../../2014/tutorials/task-6-importing-values-from-the-cleanse-supplier-list-project.md)  
  
  
