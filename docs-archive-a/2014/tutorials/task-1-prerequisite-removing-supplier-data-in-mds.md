---
title: 'Attività 1 (prerequisito): rimozione dei dati fornitore in MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6f0a4287-7fd4-4f18-b7e4-a5191a9d4a3c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e78dc5ff04f95d42cf440e3f80b1b349e0315a69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635909"
---
# <a name="task-1-prerequisite-removing-supplier-data-in-mds"></a><span data-ttu-id="8031b-102">Attività 1 (prerequisito): Rimozione dei dati fornitore in MDS</span><span class="sxs-lookup"><span data-stu-id="8031b-102">Task 1 (Prerequisite): Removing Supplier Data in MDS</span></span>
  <span data-ttu-id="8031b-103">In questa attività vengono rimossi i dati fornitore archiviati in MDS.</span><span class="sxs-lookup"><span data-stu-id="8031b-103">In this task, you remove the supplier data stored in MDS.</span></span> <span data-ttu-id="8031b-104">I dati sono stati caricati manualmente usando il **componente aggiuntivo di Excel di MDS** nella lezione precedente.</span><span class="sxs-lookup"><span data-stu-id="8031b-104">You uploaded the data manually using **MDS Excel Add-in** in the previous lesson.</span></span> <span data-ttu-id="8031b-105">Tramite il pacchetto SSIS creato durante questa lezione i dati vengono caricati automaticamente in MDS.</span><span class="sxs-lookup"><span data-stu-id="8031b-105">The SSIS package you create in this lesson will automatically upload the data to MDS for you.</span></span> <span data-ttu-id="8031b-106">Pertanto, prima di testare il pacchetto SSIS, è necessario rimuovere i dati fornitore da MDS, la gerarchia derivata, le entità Supplier e State e creare l'entità Supplier senza alcun dato.</span><span class="sxs-lookup"><span data-stu-id="8031b-106">Therefore, before testing the SSIS package, you need to remove the supplier data from MDS, remove the derived hierarchy, remove supplier and state entities, and create the supplier entity with no data.</span></span>  
  
1.  <span data-ttu-id="8031b-107">Avviare **Gestione dati master** passando a `http://localhost/MDS` o al sito Web e all'applicazione specificati durante la configurazione di MDS.</span><span class="sxs-lookup"><span data-stu-id="8031b-107">Launch **Master Data Manager** by navigating to `http://localhost/MDS` or the website and application you specified when configuring MDS.</span></span> <span data-ttu-id="8031b-108">Se il **Gestione dati master** aperto, fare clic su **SQL Server 2012 Master Data Services** nella parte superiore per passare alla **Home page**.</span><span class="sxs-lookup"><span data-stu-id="8031b-108">If you kept the **Master Data Manager** open, click **SQL Server 2012 Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="8031b-109">Fare clic su **Amministrazione sistema** nella sezione **attività amministrative** .</span><span class="sxs-lookup"><span data-stu-id="8031b-109">Click **System Administration** in the **Administrative Tasks** section.</span></span>  
  
3.  <span data-ttu-id="8031b-110">Posizionare il puntatore del mouse su **Gestisci** nel menu e fare clic su **gerarchie derivate**.</span><span class="sxs-lookup"><span data-stu-id="8031b-110">Hover the mouse over **Manage** on the menu and click **Derived Hierarchies**.</span></span> <span data-ttu-id="8031b-111">Prima di eliminare le entità nel modello **Suppliers** è necessario eliminare la gerarchia derivata **SuppliersInState** .</span><span class="sxs-lookup"><span data-stu-id="8031b-111">You need to delete the derived hierarchy **SuppliersInState** before deleting the entities in the **Suppliers** model.</span></span>  
  
4.  <span data-ttu-id="8031b-112">Selezionare **SuppliersInState** dall'elenco **gerarchia derivata** e fare clic sul pulsante **X (Elimina)** sulla barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="8031b-112">Select **SuppliersInState** from the **Derived Hierarchy** list and click **X (Delete)** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="8031b-113">Fare clic su **OK** per confermare l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="8031b-113">Click **OK** to confirm deletion.</span></span>  
  
6.  <span data-ttu-id="8031b-114">Posizionare il puntatore del mouse su **Gestisci** nel menu e fare clic su **entità**.</span><span class="sxs-lookup"><span data-stu-id="8031b-114">Hover the mouse over **Manage** on the menu and click **Entities**.</span></span>  
  
7.  <span data-ttu-id="8031b-115">Fare clic su **Supplier** e fare clic sul pulsante **Elimina (X)** sulla barra degli strumenti per eliminare l'entità.</span><span class="sxs-lookup"><span data-stu-id="8031b-115">Click **Supplier** and click **Delete (X)** button on toolbar to delete the entity.</span></span> <span data-ttu-id="8031b-116">Fare clic su **OK** nelle finestre di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8031b-116">Click **OK** on message boxes.</span></span>  
  
8.  <span data-ttu-id="8031b-117">Ripetere il passaggio precedente per eliminare l'entità **stato** .</span><span class="sxs-lookup"><span data-stu-id="8031b-117">Repeat the previous step to delete **State** entity.</span></span>  
  
9. <span data-ttu-id="8031b-118">Non chiudere **Gestione dati master**.</span><span class="sxs-lookup"><span data-stu-id="8031b-118">Don't close **Master Data Manager**.</span></span>  
  
10. <span data-ttu-id="8031b-119">Consente di passare alla finestra di Excel in cui è stato **pulito e associato Suppliers.xls** file aperto.</span><span class="sxs-lookup"><span data-stu-id="8031b-119">Switch to the Excel window that has **Cleansed and Matched Suppliers.xls** file open.</span></span> <span data-ttu-id="8031b-120">Passare alla scheda **Sheet1** in basso.</span><span class="sxs-lookup"><span data-stu-id="8031b-120">Switch to the **Sheet1** tab at the bottom.</span></span>  
  
11. <span data-ttu-id="8031b-121">Selezionare solo la **prima riga con le intestazioni**.</span><span class="sxs-lookup"><span data-stu-id="8031b-121">Select only the **first row with headers**.</span></span> <span data-ttu-id="8031b-122">Non selezionare nessun'altra riga.</span><span class="sxs-lookup"><span data-stu-id="8031b-122">Don't select any other row.</span></span> <span data-ttu-id="8031b-123">Si desidera creare le entità in base alle colonne di Excel, ma non si desidera caricare i dati.</span><span class="sxs-lookup"><span data-stu-id="8031b-123">You want to create the entities based on the Excel columns but don't want to upload any data.</span></span> <span data-ttu-id="8031b-124">Pertanto, selezionare solo la prima riga con le intestazioni.</span><span class="sxs-lookup"><span data-stu-id="8031b-124">Therefore you select only the first row with the headers.</span></span>  
  
12. <span data-ttu-id="8031b-125">Fare clic su **dati master** sulla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="8031b-125">Click **Master Data** on the menu bar.</span></span>  
  
13. <span data-ttu-id="8031b-126">Fare clic su **Crea entità** nella barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="8031b-126">Click **Create Entity** from the ribbon.</span></span>  
  
14. <span data-ttu-id="8031b-127">Nella finestra di dialogo **Gestisci connessioni** , se non si visualizza la connessione al **Server MDS locale** in **connessioni esistenti**, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="8031b-127">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="8031b-128">Selezionare **Crea una nuova connessione**e fare clic sul pulsante **nuovo** .</span><span class="sxs-lookup"><span data-stu-id="8031b-128">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="8031b-129">Nella finestra di dialogo Aggiungi nuova connessione digitare **Server MDS locale** per **Descrizione** e **http: \/ /localhost/MDS** per **Indirizzo server MDS**, quindi fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8031b-129">In the Add New Connection dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="8031b-130">Nella finestra di dialogo **Gestisci connessioni** selezionare **Server MDS locale** ( `http://localhost/MDS` ), fare clic su **test** per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="8031b-130">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="8031b-131">Fare clic su **OK** nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8031b-131">Click **OK** on the message box.</span></span>  
  
16. <span data-ttu-id="8031b-132">Fare clic su **Connetti** per stabilire una connessione al server MDS.</span><span class="sxs-lookup"><span data-stu-id="8031b-132">Click **Connect** to make a connection to the MDS server.</span></span>  
  
17. <span data-ttu-id="8031b-133">Nella finestra di dialogo **Crea entità** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8031b-133">In the **Create Entity** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="8031b-134">Verificare che l' **intervallo** sia impostato su **$1: $1**.</span><span class="sxs-lookup"><span data-stu-id="8031b-134">Confirm that **Range** is set to **$1:$1**.</span></span>  
  
    2.  <span data-ttu-id="8031b-135">Selezionare **Suppliers** per **modello**.</span><span class="sxs-lookup"><span data-stu-id="8031b-135">Select **Suppliers** for **Model**.</span></span>  
  
    3.  <span data-ttu-id="8031b-136">Selezionare **VERSION_1** per **versione**.</span><span class="sxs-lookup"><span data-stu-id="8031b-136">Select **VERSION_1** for **Version**.</span></span>  
  
    4.  <span data-ttu-id="8031b-137">Digitare **Supplier** per **nome nuova entità**.</span><span class="sxs-lookup"><span data-stu-id="8031b-137">Type **Supplier** for **New entity name**.</span></span>  
  
    5.  <span data-ttu-id="8031b-138">Selezionare **SupplierID** per **codice**.</span><span class="sxs-lookup"><span data-stu-id="8031b-138">Select **SupplierID** for **Code**.</span></span>  
  
    6.  <span data-ttu-id="8031b-139">Selezionare **Supplier Name** per **nome**.</span><span class="sxs-lookup"><span data-stu-id="8031b-139">Select **Supplier Name** for **Name**.</span></span>  
  
    7.  <span data-ttu-id="8031b-140">Fare clic su **OK** per creare l'entità e chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="8031b-140">Click **OK** to create the entity and close the dialog box.</span></span>  
  
18. <span data-ttu-id="8031b-141">Chiudere **Excel** e **non salvare** il file.</span><span class="sxs-lookup"><span data-stu-id="8031b-141">Close **Excel** and **do not save** the file.</span></span>  
  
19. <span data-ttu-id="8031b-142">In **Gestione dati master**aggiornare il browser Internet e verificare che l'entità **Supplier** sia visualizzata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8031b-142">In **Master Data Manager**, refresh the internet browser and confirm that **Supplier** entity is displayed in the list.</span></span>  
  
20. <span data-ttu-id="8031b-143">Passare al **Home page** facendo clic **SQL Server Master Data Services 2012** nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="8031b-143">Switch to the **home page** by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
21. <span data-ttu-id="8031b-144">Verificare che il modello **Suppliers** sia selezionato per **Model** e **VERSION_1** sia selezionato per **Version**.</span><span class="sxs-lookup"><span data-stu-id="8031b-144">Confirm that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**.</span></span>  
  
22. <span data-ttu-id="8031b-145">Fare clic su **Esplora**.</span><span class="sxs-lookup"><span data-stu-id="8031b-145">Click **Explorer**.</span></span> <span data-ttu-id="8031b-146">Si noti che l'entità **Supplier** con tutti gli attributi viene creata **senza valori**.</span><span class="sxs-lookup"><span data-stu-id="8031b-146">Notice that the **Supplier** entity with all the attributes is created with **no values**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="8031b-147">passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="8031b-147">Next Step</span></span>  
 [<span data-ttu-id="8031b-148">Attività 2 &#40;&#41; facoltativo: creazione di una vista sottoscrizioni MDS tramite Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="8031b-148">Task 2 &#40;Optional&#41;: Creating a MDS Subscription View using Master Data Manager</span></span>](../../2014/tutorials/task-2-optional-creating-a-mds-subscription-view-using-master-data-manager.md)  
  
  
