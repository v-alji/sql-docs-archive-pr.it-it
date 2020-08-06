---
title: 'Attività 17: Revisione del progetto di pulizia DQS creato dal pacchetto SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fc6cc258-72f5-4593-8edb-9f5bc66de9db
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0876a0b727e810f8834fcf5445958bf9884a87f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711168"
---
# <a name="task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package"></a><span data-ttu-id="ab354-102">Attività 17: Verifica del progetto DQS Cleansing creato dal pacchetto SSIS</span><span class="sxs-lookup"><span data-stu-id="ab354-102">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>
  <span data-ttu-id="ab354-103">In questa attività viene aperto il progetto DQS creato dal pacchetto SSIS nel client DQS, vengono esaminati i risultati del processo di pulizia e, facoltativamente, viene effettuata la pulizia interattiva e l'esportazione dei risultati.</span><span class="sxs-lookup"><span data-stu-id="ab354-103">In this task, you open the DQS project created by the SSIS package in DQS Client, review the results from the cleansing process, and optionally perform interactive cleansing and export the results.</span></span>  
  
1.  <span data-ttu-id="ab354-104">Avviare **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="ab354-104">Launch **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="ab354-105">Fare clic su **monitoraggio attività** nel riquadro **Amministrazione** .</span><span class="sxs-lookup"><span data-stu-id="ab354-105">Click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
3.  <span data-ttu-id="ab354-106">Ordinare l'elenco in base all' **ora di inizio dell'attività** per visualizzare il record più recente.</span><span class="sxs-lookup"><span data-stu-id="ab354-106">Sort the list based on **Activity Start Time** to see the latest record.</span></span>  
  
4.  <span data-ttu-id="ab354-107">Si noti che il nome del progetto viene visualizzato nel formato seguente: **CleanseAndCurate. cleane Supplier Data. Guid**.</span><span class="sxs-lookup"><span data-stu-id="ab354-107">Notice that you see a name of the project in the following format: **CleanseAndCurate.Cleanse Supplier Data.GUID**.</span></span>  
  
     <span data-ttu-id="ab354-108">![Progetto DQS Cleansing creato dal pacchetto SSIS](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "Progetto DQS Cleansing creato dal pacchetto SSIS")</span><span class="sxs-lookup"><span data-stu-id="ab354-108">![DQS Cleansing Project Created by SSIS Package](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "DQS Cleansing Project Created by SSIS Package")</span></span>  
  
5.  <span data-ttu-id="ab354-109">Si noti che il valore nel campo **is Active** è **Active**.</span><span class="sxs-lookup"><span data-stu-id="ab354-109">Notice that the value in the **Is Active** field is **Active**.</span></span>  
  
6.  <span data-ttu-id="ab354-110">Fare clic sulla scheda **Profiler** nel riquadro inferiore per visualizzare le statistiche del profiler per l'attività di pulizia eseguita dal pacchetto SSIS.</span><span class="sxs-lookup"><span data-stu-id="ab354-110">Click **Profiler** tab in the bottom pane to see profiler statistics for the Cleansing activity that the SSIS package performed.</span></span>  
  
7.  <span data-ttu-id="ab354-111">Fare clic su **Chiudi** per chiudere la schermata di **Amministrazione** .</span><span class="sxs-lookup"><span data-stu-id="ab354-111">Click **Close** to close the **Administration** screen.</span></span>  
  
8.  <span data-ttu-id="ab354-112">Nella pagina principale del **client DQS**fare clic su **Apri progetto Data Quality** nel riquadro **progetti Data Quality** .</span><span class="sxs-lookup"><span data-stu-id="ab354-112">In the main page of **DQS Client**, click **Open Data Quality Project** in the **Data Quality Projects** pane.</span></span>  
  
9. <span data-ttu-id="ab354-113">Nell'elenco di progetti selezionare il progetto creato dal componente SSIS DQS Cleansing.</span><span class="sxs-lookup"><span data-stu-id="ab354-113">In the list of projects, select the project created by SSIS DQS Cleansing component.</span></span> <span data-ttu-id="ab354-114">Il nome del progetto deve essere nel formato: **CleanseAndCurate. cleane Supplier Data. Guid (in rosso)**.</span><span class="sxs-lookup"><span data-stu-id="ab354-114">The name of the project should be in format:  **CleanseAndCurate.Cleanse Supplier Data.GUID (in red color)**.</span></span> <span data-ttu-id="ab354-115">Potrebbe essere necessario ordinare l'elenco in base alla colonna **Data di creazione** e cercare il record più recente.</span><span class="sxs-lookup"><span data-stu-id="ab354-115">You may need to sort the list based on **Date Created** column and look for the latest record.</span></span>  
  
10. <span data-ttu-id="ab354-116">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ab354-116">Click **Next**.</span></span>  
  
11. <span data-ttu-id="ab354-117">La pagina **Gestisci e visualizza risultati** dovrebbe essere familiare dalla pulizia interattiva illustrata in precedenza in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="ab354-117">The **Manage and View Results** page should be familiar to you from the interactive cleansing you did earlier in this tutorial.</span></span>  
  
12. <span data-ttu-id="ab354-118">Esaminare i risultati della pulizia.</span><span class="sxs-lookup"><span data-stu-id="ab354-118">Review the cleansing results.</span></span> <span data-ttu-id="ab354-119">Inoltre, è possibile effettuare la pulizia interattiva ed esportare i risultati in un file di Excel o in un database nella pagina successiva.</span><span class="sxs-lookup"><span data-stu-id="ab354-119">You can also perform interactive cleansing and export results to an Excel file or to a database in the next page.</span></span>  
  
13. <span data-ttu-id="ab354-120">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ab354-120">Click **Next**.</span></span> <span data-ttu-id="ab354-121">In questa pagina di **esportazione** è possibile esportare i risultati in un file di Excel, in un file CSV o in un database SQL.</span><span class="sxs-lookup"><span data-stu-id="ab354-121">In this **Export** page, you can export results to an excel file, CSV file, or to a SQL database.</span></span>  
  
14. <span data-ttu-id="ab354-122">Fare clic su **fine** per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="ab354-122">Click **Finish** to finish the activity.</span></span>  
  
15. <span data-ttu-id="ab354-123">Nella pagina principale del **client DQS**fare clic su **monitoraggio attività** nel riquadro **Amministrazione** .</span><span class="sxs-lookup"><span data-stu-id="ab354-123">In the main page of **DQS Client**, click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
16. <span data-ttu-id="ab354-124">Si noti che il valore del campo **inactive** per il progetto è **terminato** adesso.</span><span class="sxs-lookup"><span data-stu-id="ab354-124">Notice that the value of **IsActive** field for the project is **Ended** now.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ab354-125">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ab354-125">Next Step</span></span>  
 [<span data-ttu-id="ab354-126">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="ab354-126">Conclusion</span></span>](../../2014/tutorials/conclusion.md)  
  
  
