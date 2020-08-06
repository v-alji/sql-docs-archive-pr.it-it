---
title: 'Attività 7: aggiunta della trasformazione pulizia DQS al flusso di dati | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0b749c71-dfb6-493a-804f-600290d46eef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 887bc361a51b61e9137404e054bd52e2b630ca5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625083"
---
# <a name="task-7-adding-dqs-cleansing-transform-to-the-data-flow"></a><span data-ttu-id="237ee-102">Attività 7: Aggiunta della trasformazione DQS Cleansing al flusso di dati</span><span class="sxs-lookup"><span data-stu-id="237ee-102">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>
  <span data-ttu-id="237ee-103">In questa attività viene aggiunta una trasformazione DQS Cleansing al flusso di dati per pulire i dati di input del fornitore tramite DQS.</span><span class="sxs-lookup"><span data-stu-id="237ee-103">In this task, you add DQS Cleansing Transform to the data flow to cleanse the input supplier data by using DQS.</span></span> <span data-ttu-id="237ee-104">Per ulteriori informazioni sulla trasformazione, vedere **[trasformazione della pulizia DQS](https://msdn.microsoft.com/library/ee677619.aspx)** .</span><span class="sxs-lookup"><span data-stu-id="237ee-104">See **[DQS Cleansing Transform](https://msdn.microsoft.com/library/ee677619.aspx)** for more details about the transform.</span></span>  
  
1.  <span data-ttu-id="237ee-105">Fare clic con il pulsante destro del mouse su **DQS cleaning** nella scheda **flusso di dati** e scegliere **Rinomina**.</span><span class="sxs-lookup"><span data-stu-id="237ee-105">Right-click **DQS Cleansing** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="237ee-106">Digitare **cleane Supplier Data**e premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="237ee-106">Type **Cleanse Supplier Data**, and press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="237ee-107">Selezionare **Leggi dati fornitore dal file di Excel**. Trascinare il connettore blu per **pulire i dati fornitore**.</span><span class="sxs-lookup"><span data-stu-id="237ee-107">Select **Read Supplier Data from Excel File**; drag the blue connector to **Cleanse Supplier Data**.</span></span> <span data-ttu-id="237ee-108">I componenti sono ora collegati.</span><span class="sxs-lookup"><span data-stu-id="237ee-108">The components are now connected.</span></span>  
  
     <span data-ttu-id="237ee-109">![Leggere dati fornitore-> pulire i dati fornitore](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Leggi dati fornitore -> Pulisci dati fornitore")</span><span class="sxs-lookup"><span data-stu-id="237ee-109">![Read Supplier Data -> Cleanse Supplier Data](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Read Supplier Data -> Cleanse Supplier Data")</span></span>  
  
3.  <span data-ttu-id="237ee-110">Fare doppio clic su **Pulisci dati fornitore**.</span><span class="sxs-lookup"><span data-stu-id="237ee-110">Double-click **Cleanse Supplier Data**.</span></span>  
  
4.  <span data-ttu-id="237ee-111">**Nell'Editor trasformazione DQS**, fare clic su **nuovo** accanto all' **elenco a discesa Gestione connessione Data Quality**.</span><span class="sxs-lookup"><span data-stu-id="237ee-111">In the **DQS Cleansing Transformation Editor**, click **New** next to the **Data Quality Connection Manager drop-down list**.</span></span>  
  
5.  <span data-ttu-id="237ee-112">Nella finestra di dialogo **gestione connessione DQS** , digitare **(local)** o **punto** (.) per connettersi al server locale.</span><span class="sxs-lookup"><span data-stu-id="237ee-112">In the **DQS Cleansing Connection Manager** dialog box, type **(local)** or **period** (.) to connect to the local server.</span></span> <span data-ttu-id="237ee-113">In questa lezione si presuppone che in un server locale sia installato DQS.</span><span class="sxs-lookup"><span data-stu-id="237ee-113">This lesson assumes that you have DQS installed on a local server.</span></span>  
  
6.  <span data-ttu-id="237ee-114">Fare clic su **Test connessione** per testare la connessione al server DQS.</span><span class="sxs-lookup"><span data-stu-id="237ee-114">Click **Test Connection** to test the connection to DQS server.</span></span>  
  
7.  <span data-ttu-id="237ee-115">Scegliere **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="237ee-115">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="237ee-116">Selezionare **Suppliers** per **Data Quality Knowledge base**.</span><span class="sxs-lookup"><span data-stu-id="237ee-116">Select **Suppliers** for the **Data Quality Knowledge Base**.</span></span>  
  
     <span data-ttu-id="237ee-117">![Editor trasformazione DQS Cleansing - KB fornitori](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "Editor trasformazione DQS Cleansing - KB fornitori")</span><span class="sxs-lookup"><span data-stu-id="237ee-117">![DQS Cleansing Transformation Editor - Suppliers KB](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "DQS Cleansing Transformation Editor - Suppliers KB")</span></span>  
  
9. <span data-ttu-id="237ee-118">Passare alla scheda **mapping** nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="237ee-118">Switch to the **Mapping** tab at the top.</span></span>  
  
10. <span data-ttu-id="237ee-119">**Nelle colonne di input disponibili**selezionare **Supplier Name**, **ContactEmailAddress**, **address line**, **City**, **state**, **Country**e **zip code** selezionando le caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="237ee-119">From **Available Input Columns**, select **Supplier Name**, **ContactEmailAddress**, **Address Line**, **City**, **State**, **Country**, and **Zip Code** by selecting the check boxes.</span></span>  
  
     <span data-ttu-id="237ee-120">![Editor trasformazione DQS Cleansing - Mapping](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "Editor trasformazione DQS Cleansing - Mapping")</span><span class="sxs-lookup"><span data-stu-id="237ee-120">![DQS Cleansing Transformation Editor - Mappings](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "DQS Cleansing Transformation Editor - Mappings")</span></span>  
  
11. <span data-ttu-id="237ee-121">Nel riquadro inferiore eseguire il mapping di queste colonne usando gli elenchi a discesa nella colonna **dominio** :</span><span class="sxs-lookup"><span data-stu-id="237ee-121">In the bottom pane, map these columns by using drop-down lists in the **Domain** column:</span></span>  
  
    |<span data-ttu-id="237ee-122">Colonna</span><span class="sxs-lookup"><span data-stu-id="237ee-122">Column</span></span>|<span data-ttu-id="237ee-123">Dominio</span><span class="sxs-lookup"><span data-stu-id="237ee-123">Domain</span></span>|  
    |------------|------------|  
    |<span data-ttu-id="237ee-124">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="237ee-124">Supplier Name</span></span>|<span data-ttu-id="237ee-125">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="237ee-125">Supplier Name</span></span>|  
    |<span data-ttu-id="237ee-126">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="237ee-126">ContactEmailAddress</span></span>|<span data-ttu-id="237ee-127">Indirizzo di posta elettronica del contatto</span><span class="sxs-lookup"><span data-stu-id="237ee-127">Contact Email</span></span>|  
    |<span data-ttu-id="237ee-128">Riga indirizzo</span><span class="sxs-lookup"><span data-stu-id="237ee-128">Address Line</span></span>|<span data-ttu-id="237ee-129">Riga indirizzo</span><span class="sxs-lookup"><span data-stu-id="237ee-129">Address Line</span></span>|  
    |<span data-ttu-id="237ee-130">Città</span><span class="sxs-lookup"><span data-stu-id="237ee-130">City</span></span>|<span data-ttu-id="237ee-131">Città</span><span class="sxs-lookup"><span data-stu-id="237ee-131">City</span></span>|  
    |<span data-ttu-id="237ee-132">State</span><span class="sxs-lookup"><span data-stu-id="237ee-132">State</span></span>|<span data-ttu-id="237ee-133">State</span><span class="sxs-lookup"><span data-stu-id="237ee-133">State</span></span>|  
    |<span data-ttu-id="237ee-134">Paese</span><span class="sxs-lookup"><span data-stu-id="237ee-134">Country</span></span>|<span data-ttu-id="237ee-135">Paese</span><span class="sxs-lookup"><span data-stu-id="237ee-135">Country</span></span>|  
    |<span data-ttu-id="237ee-136">Zip Code</span><span class="sxs-lookup"><span data-stu-id="237ee-136">Zip Code</span></span>|<span data-ttu-id="237ee-137">Zip</span><span class="sxs-lookup"><span data-stu-id="237ee-137">Zip</span></span>|  
  
12. <span data-ttu-id="237ee-138">Fare clic su **OK** per chiudere la finestra di dialogo **Editor trasformazione di pulizia DQS** .</span><span class="sxs-lookup"><span data-stu-id="237ee-138">Click **OK** to close the **DQS Cleansing Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="237ee-139">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="237ee-139">Next Step</span></span>  
 [<span data-ttu-id="237ee-140">Attività 8: Aggiunta della trasformazione Suddivisione condizionale all'output di pulizia della suddivisione</span><span class="sxs-lookup"><span data-stu-id="237ee-140">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>](../../2014/tutorials/task-8-adding-conditional-split-transform-to-split-cleansing-output.md)  
  
  
