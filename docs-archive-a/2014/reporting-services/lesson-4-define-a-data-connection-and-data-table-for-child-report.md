---
title: 'Lesson 4: Define a Data Connection and Data Table for Child Report (Lezione 4: Definire una connessione dati e una tabella dati per il report figlio) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a6aa2c56-227c-43c5-a28e-c7104131ac5e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6d9144d960ad933afa65f9d4483e96b5f732d944
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625218"
---
# <a name="lesson-4-define-a-data-connection-and-data-table-for-child-report"></a><span data-ttu-id="9b1a1-102">Lezione 4: Definire una connessione dati e una tabella di dati per il report figlio</span><span class="sxs-lookup"><span data-stu-id="9b1a1-102">Lesson 4: Define a Data Connection and Data Table for Child Report</span></span>
  <span data-ttu-id="9b1a1-103">Dopo aver progettato il report padre, il passaggio successivo consiste nel creare una connessione dati e una tabella di dati per il report figlio.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-103">After you design the parent report, you next step is to create a data connection and a data table for the child report.</span></span> <span data-ttu-id="9b1a1-104">In questa esercitazione la connessione dati è al database AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="9b1a1-105">È anche possibile scegliere di connettersi al database AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-datatable-by-adding-a-dataset-for-child-report"></a><span data-ttu-id="9b1a1-106">Per definire una connessione dati e l'oggetto DataTable aggiungendo un oggetto DataSet (per il report figlio)</span><span class="sxs-lookup"><span data-stu-id="9b1a1-106">To define a data connection and DataTable by adding a DataSet (for child report)</span></span>  
  
1.  <span data-ttu-id="9b1a1-107">Scegliere **Aggiungi nuovo elemento**dal menu **sito Web** .</span><span class="sxs-lookup"><span data-stu-id="9b1a1-107">On the **Website** menu, click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="9b1a1-108">Nella finestra di dialogo **Aggiungi nuovo elemento** fare clic su **set di dati** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-108">In the **Add New Item** dialog box, click **DataSet** and then click **Add**.</span></span> <span data-ttu-id="9b1a1-109">Quando richiesto, è necessario aggiungere l'elemento alla cartella **App_Code** facendo clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-109">When prompted, you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="9b1a1-110">Verrà aggiunto un nuovo file XSD **DataSet2.xsd** al progetto e verrà aperto Progettazione DataSet.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-110">This adds a new XSD file **DataSet2.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="9b1a1-111">Dalla finestra della casella degli strumenti trascinare un controllo **TableAdapter** nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-111">From the Toolbox window, drag a **TableAdapter** control to the design surface.</span></span> <span data-ttu-id="9b1a1-112">Viene avviata la configurazione guidata **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="9b1a1-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="9b1a1-113">Nella pagina **scegliere la connessione dati** fare clic su **nuova connessione**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="9b1a1-114">Nella finestra di dialogo **Aggiungi connessione** effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b1a1-114">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="9b1a1-115">Nella casella **nome server** immettere il server in cui si trova il database **AdventureWorks2008** .</span><span class="sxs-lookup"><span data-stu-id="9b1a1-115">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="9b1a1-116">L'istanza predefinita di SQL Server Express è **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-116">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="9b1a1-117">Nella sezione **Accesso al server** selezionare l'opzione di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-117">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="9b1a1-118">**Usa autenticazione di Windows** è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-118">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="9b1a1-119">Nell'elenco **a discesa selezionare o immettere un nome di database** fare clic su **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-119">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="9b1a1-120">Fare clic su **OK** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-120">Click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="9b1a1-121">Se è stato selezionato **Usa autenticazione di SQL Server** nel passaggio 5 (b), selezionare l'opzione per includere i dati sensibili nella stringa o per impostare le informazioni nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-121">If you selected **Use SQL Server Authentication** in Step 5 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
7.  <span data-ttu-id="9b1a1-122">Nella pagina **Salva stringa di connessione nel file di configurazione dell'applicazione** Digitare il nome per la stringa di connessione o accettare l'impostazione predefinita **AdventureWorks2008ConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-122">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="9b1a1-123">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-123">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="9b1a1-124">Nella pagina **scegliere un tipo di comando** selezionare **Usa istruzioni SQL**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-124">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="9b1a1-125">Nella pagina **immettere un'istruzione SQL** immettere la query Transact-SQL seguente per recuperare i dati dal database **AdventureWorks2008** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-125">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT PurchaseOrderID, PurchaseOrderDetailID, OrderQty, ProductID, ReceivedQty, RejectedQty, StockedQty FROM Purchasing.PurchaseOrderDetail  
    ```  
  
     <span data-ttu-id="9b1a1-126">È anche possibile creare la query facendo clic su **Generatore di query**, quindi verificare la query facendo clic sul pulsante **Esegui query** .</span><span class="sxs-lookup"><span data-stu-id="9b1a1-126">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query** button.</span></span> <span data-ttu-id="9b1a1-127">Se non vengono restituiti i dati previsti dalla query, è possibile che si stia utilizzando una versione precedente di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-127">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="9b1a1-128">Per ulteriori informazioni sull'installazione della versione **AdventureWorks2008** di AdventureWorks, vedere [procedura dettagliata: installazione del database AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="9b1a1-128">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
10. <span data-ttu-id="9b1a1-129">Nella pagina **scegliere i metodi per la generazione** deselezionare **Crea metodi per inviare aggiornamenti direttamente al database (GenerateDBDirectMethods)** e quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-129">On the **Choose Methods to Generate** page, uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="9b1a1-130">A questo punto è stata completata la configurazione di ADO.NET [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) come origine dati per il report.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-130">You have now completed configuring the ADO.NET [DataTable](https://msdn.microsoft.com/library/system.data.datatable\(v=vs.100\).aspx) as data source for your report.</span></span> <span data-ttu-id="9b1a1-131">Nella pagina Progettazione DataSet in Visual Studio si dovrebbe visualizzare l'oggetto **DataTable** aggiunto, con le colonne specificate nella query.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-131">On the DataSet Designer page in Visual Studio, you should see the **DataTable** you added, listing the columns specified in the query.</span></span> <span data-ttu-id="9b1a1-132">In DataSet2 sono inclusi i dati della tabella PurhcaseOrderDetail, basati sulla query.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-132">DataSet2 contains the data from the PurhcaseOrderDetail table, based on the query.</span></span>  
  
11. <span data-ttu-id="9b1a1-133">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-133">Save the file.</span></span>  
  
12. <span data-ttu-id="9b1a1-134">Per visualizzare l'anteprima dei dati, fare clic su **Anteprima dati** dal menu **dati** e quindi fare clic su **Anteprima**.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-134">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="9b1a1-135">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="9b1a1-135">Next Task</span></span>  
 <span data-ttu-id="9b1a1-136">È stata creata correttamente una connessione dati e una tabella di dati per il report figlio.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-136">You have successfully created a data connection and data table for the child report.</span></span> <span data-ttu-id="9b1a1-137">Successivamente, verrà progettato il report figlio utilizzando la Creazione guidata report.</span><span class="sxs-lookup"><span data-stu-id="9b1a1-137">Next, you will design the child report using the Report Wizard.</span></span>  
  
  
