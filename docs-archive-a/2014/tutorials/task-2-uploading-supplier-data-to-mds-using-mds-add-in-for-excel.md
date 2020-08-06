---
title: 'Attività 2: caricamento dei dati fornitore in MDS tramite Componente aggiuntivo MDS per Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 598deb57-e0cc-4e0a-aeb1-94432c094c67
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 16c5fa9db81649b30c12fae4d2e57afa8bf094e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623656"
---
# <a name="task-2-uploading-supplier-data-to-mds-using-mds-add-in-for-excel"></a><span data-ttu-id="65b61-102">Attività 2: Caricamento dei dati fornitore in MDS tramite il componente aggiuntivo MDS per Excel</span><span class="sxs-lookup"><span data-stu-id="65b61-102">Task 2: Uploading Supplier Data to MDS using MDS Add-in for Excel</span></span>
  <span data-ttu-id="65b61-103">In questa attività verranno pubblicati i dati puliti e fornitore in **MDS** utilizzando il **componente aggiuntivo MDS per Excel**.</span><span class="sxs-lookup"><span data-stu-id="65b61-103">In this task, you publish the cleansed and supplier data to **MDS** using the **MDS Add-in for Excel**.</span></span> <span data-ttu-id="65b61-104">Si crea un'entità denominata **Supplier** nel modello **Suppliers** creato nella lezione precedente.</span><span class="sxs-lookup"><span data-stu-id="65b61-104">You create an entity named **Supplier** in the **Suppliers** model you created in the previous lesson.</span></span> <span data-ttu-id="65b61-105">All'entità sarà associato un attributo per ogni colonna nel file di Excel.</span><span class="sxs-lookup"><span data-stu-id="65b61-105">The entity will have an attribute for each column in the Excel file.</span></span> <span data-ttu-id="65b61-106">Gli attributi di codice e nome dell'entità Supplier corrispondono alle colonne **SupplierID** e **Supplier Name** in Excel.</span><span class="sxs-lookup"><span data-stu-id="65b61-106">The Code and Name attributes of the Supplier entity correspond to the **SupplierID** and **Supplier Name** columns in Excel.</span></span>  
  
1.  <span data-ttu-id="65b61-107">Aprire **Suppliers.xlspuliti e corrispondenti** in **Excel**.</span><span class="sxs-lookup"><span data-stu-id="65b61-107">Open **Cleansed and Matched Suppliers.xls** in **Excel**.</span></span>  
  
2.  <span data-ttu-id="65b61-108">Premere **CTRL + a** per selezionare tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="65b61-108">Press **CTRL+A** to select entire data.</span></span> <span data-ttu-id="65b61-109">È **importante** selezionare tutti i dati nel foglio di calcolo.</span><span class="sxs-lookup"><span data-stu-id="65b61-109">It is **important** that you select the entire data in the spreadsheet.</span></span>  
  
3.  <span data-ttu-id="65b61-110">Fare clic su **dati master** sulla barra dei menu.</span><span class="sxs-lookup"><span data-stu-id="65b61-110">Click **Master Data** on the menu bar.</span></span>  
  
4.  <span data-ttu-id="65b61-111">Fare clic sul pulsante **Crea entità** sulla barra multifunzione.</span><span class="sxs-lookup"><span data-stu-id="65b61-111">Click **Create Entity** button on the ribbon.</span></span>  
  
     <span data-ttu-id="65b61-112">![Excel - Scheda Dati master - Pulsante Crea entità](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Scheda Dati master - Pulsante Crea entità")</span><span class="sxs-lookup"><span data-stu-id="65b61-112">![Excel - Master Data Tab - Create Entity Button](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-01.jpg "Excel - Master Data Tab - Create Entity Button")</span></span>  
  
5.  <span data-ttu-id="65b61-113">Nella finestra di dialogo **Gestisci connessioni** , se non si visualizza la connessione al **Server MDS locale** in **connessioni esistenti**, effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="65b61-113">In **Manage Connections** dialog box, if you do not see the connection to **local MDS server** under **Existing connections**, do the following:</span></span>  
  
    1.  <span data-ttu-id="65b61-114">Selezionare **Crea una nuova connessione**e fare clic sul pulsante **nuovo** .</span><span class="sxs-lookup"><span data-stu-id="65b61-114">Select **Create a new connection**, and click **New** button.</span></span>  
  
    2.  <span data-ttu-id="65b61-115">Nella finestra di dialogo **Aggiungi nuova connessione** digitare **Server MDS locale** per **Descrizione** e **http: \/ /localhost/MDS** per **Indirizzo server MDS**, quindi fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="65b61-115">In the **Add New Connection** dialog box, type **Local MDS Server** for **Description** and **http:\//localhost/MDS** for **MDS server address**, and click **OK** to close the dialog box.</span></span>  
  
6.  <span data-ttu-id="65b61-116">Nella finestra di dialogo **Gestisci connessioni** selezionare **Server MDS locale** ( `http://localhost/MDS` ), fare clic su **test** per testare la connessione.</span><span class="sxs-lookup"><span data-stu-id="65b61-116">In **Manage Connections** dialog box, select **Local MDS Server** (`http://localhost/MDS`), click **Test** to test the connection.</span></span> <span data-ttu-id="65b61-117">Fare clic su **OK** nella finestra di messaggio.</span><span class="sxs-lookup"><span data-stu-id="65b61-117">Click **OK** on the message box.</span></span>  
  
7.  <span data-ttu-id="65b61-118">Fare clic su **Connetti** per connettersi al server MDS.</span><span class="sxs-lookup"><span data-stu-id="65b61-118">Click **Connect** to connect to the MDS server.</span></span>  
  
8.  <span data-ttu-id="65b61-119">Nella finestra di dialogo **Crea entità** selezionare **Suppliers** per il **modello**.</span><span class="sxs-lookup"><span data-stu-id="65b61-119">In the **Create Entity** dialog box, select **Suppliers** for the **Model**.</span></span>  
  
9. <span data-ttu-id="65b61-120">Verificare che sia selezionato **VERSION_1** per la **versione**.</span><span class="sxs-lookup"><span data-stu-id="65b61-120">Ensure that **VERSION_1** is selected for **Version**.</span></span>  
  
10. <span data-ttu-id="65b61-121">Immettere **Supplier** per **nome nuova entità**.</span><span class="sxs-lookup"><span data-stu-id="65b61-121">Enter **Supplier** for **New entity name**.</span></span>  
  
11. <span data-ttu-id="65b61-122">Selezionare **SupplierID** per **la colonna contenente un campo identificatore univoco** . è anche possibile generare automaticamente un codice.</span><span class="sxs-lookup"><span data-stu-id="65b61-122">Select **SupplierID** for **the column that contains a unique identifier** field (you can also generate a code automatically).</span></span> <span data-ttu-id="65b61-123">Si sta essenzialmente eseguendo il mapping della colonna **SupplierID** in **Excel** all'attributo **Code** dell'entità **Supplier** .</span><span class="sxs-lookup"><span data-stu-id="65b61-123">You are essentially mapping the **SupplierID** column in **Excel** to the **Code** attribute of **Supplier** entity.</span></span>  
  
12. <span data-ttu-id="65b61-124">Selezionare **Supplier Name** per **la colonna che contiene il campo names** .</span><span class="sxs-lookup"><span data-stu-id="65b61-124">Select **Supplier Name** for **the column that contains names** field.</span></span> <span data-ttu-id="65b61-125">Si sta essenzialmente eseguendo il mapping della colonna **Supplier Name** in **Excel** all'attributo **Name** dell'entità **Supplier** .</span><span class="sxs-lookup"><span data-stu-id="65b61-125">You are essentially mapping the **Supplier Name** column in **Excel** to the **Name** attribute of the **Supplier** entity.</span></span> <span data-ttu-id="65b61-126">Gli attributi del **nome** e del **codice** sono attributi obbligatori per un'entità in MDS.</span><span class="sxs-lookup"><span data-stu-id="65b61-126">The **Code** and **Name** attributes are mandatory attributes for an entity in MDS.</span></span>  
  
     <span data-ttu-id="65b61-127">![Finestra di dialogo Crea entità](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Finestra di dialogo Crea entità")</span><span class="sxs-lookup"><span data-stu-id="65b61-127">![Create Entity Dialog Box](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-02.jpg "Create Entity Dialog Box")</span></span>  
  
13. <span data-ttu-id="65b61-128">Fare clic su **OK** per creare l'entità in MDS, pubblicare i dati master nell'entità e chiudere la finestra di dialogo **Crea entità** .</span><span class="sxs-lookup"><span data-stu-id="65b61-128">Click **OK** to create the entity on MDS, publish the master data to the entity, and close **Create Entity** dialog box.</span></span>  
  
14. <span data-ttu-id="65b61-129">A questo punto, verrà visualizzato un nuovo foglio denominato **Supplier**, che è il nome dell'entità, aggiunto al foglio di calcolo di Excel e nella parte superiore del foglio di lavoro si noterà che il foglio di lavoro è connesso al server MDS.</span><span class="sxs-lookup"><span data-stu-id="65b61-129">Now, you should see a new sheet titled **Supplier**, which is the name of the entity, added to your Excel spreadsheet and at the top of the worksheet you should see that the worksheet is connected to the MDS server.</span></span> <span data-ttu-id="65b61-130">Si noti che il foglio di foglio originale (denominato **Sheet1**) esiste ancora.</span><span class="sxs-lookup"><span data-stu-id="65b61-130">Notice that the original worksheet (titled **Sheet1**) still exists.</span></span>  
  
     <span data-ttu-id="65b61-131">![Excel - Schede Fornitore e Foglio1](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Schede Fornitore e Foglio1")</span><span class="sxs-lookup"><span data-stu-id="65b61-131">![Excel - Supplier and Sheet1 Tabs](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-03.jpg "Excel - Supplier and Sheet1 Tabs")</span></span>  
  
     <span data-ttu-id="65b61-132">![Excel - Visualizzazione dettagli connessione MDS](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Visualizzazione dettagli connessione MDS")</span><span class="sxs-lookup"><span data-stu-id="65b61-132">![Excel - Showing MDS Connection Details](../../2014/tutorials/media/et-ulingsdtomdsusingmdsaddinforexcel-04.jpg "Excel - Showing MDS Connection Details")</span></span>  
  
15. <span data-ttu-id="65b61-133">Mantieni aperto **Excel** .</span><span class="sxs-lookup"><span data-stu-id="65b61-133">Keep **Excel** open.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="65b61-134">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="65b61-134">Next Task</span></span>  
 [<span data-ttu-id="65b61-135">Attività 3: Verifica dei dati in Gestione dati master</span><span class="sxs-lookup"><span data-stu-id="65b61-135">Task 3: Verifying the Data in Master Data Manager</span></span>](../../2014/tutorials/task-3-verifying-the-data-in-master-data-manager.md)  
  
  
