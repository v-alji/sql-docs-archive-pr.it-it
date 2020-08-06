---
title: 'Lesson 2: Define a Data Connection and Data Table for Child Report (Lezione 2: Definire una connessione dati e una tabella dati per il report padre) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f02dee0c-85ad-45d4-b707-10e9e8541db9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 045ff576061bf12d163668cb9a57651e591768a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624539"
---
# <a name="lesson-2-define-a-data-connection-and-data-table-for-parent-report"></a><span data-ttu-id="9b8d5-102">Lezione 2: Definire una connessione dati e una tabella di dati per il report padre</span><span class="sxs-lookup"><span data-stu-id="9b8d5-102">Lesson 2: Define a Data Connection and Data Table for Parent Report</span></span>
  <span data-ttu-id="9b8d5-103">Dopo aver creato un nuovo progetto di sito Web utilizzando il modello di sito Web ASP.NET per Visual C#, il passaggio successivo consiste nel creare una connessione dati e una tabella di dati per il report padre.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-103">After you create a new website project using the ASP.NET website template for Visual C#, your next step is to create a data connection and a data table for the parent report.</span></span> <span data-ttu-id="9b8d5-104">In questa esercitazione la connessione dati è al database AdventureWorks2008.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-104">In this tutorial the data connection is to the AdventureWorks2008 database.</span></span> <span data-ttu-id="9b8d5-105">È anche possibile scegliere di connettersi al database AdventureWorks2012.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-105">You also have the option of connecting to the AdventureWorks2012 database.</span></span>  
  
### <a name="to-define-a-data-connection-and-data-table-by-adding-a-dataset-for-parent-report"></a><span data-ttu-id="9b8d5-106">Per definire una connessione dati e l'oggetto DataTable aggiungendo un oggetto DataSet (per il report padre)</span><span class="sxs-lookup"><span data-stu-id="9b8d5-106">To define a data connection and Data Table by adding a DataSet (for parent report)</span></span>  
  
1.  <span data-ttu-id="9b8d5-107">Selezionare **Aggiungi nuovo elemento** dal menu **Sito Web**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-107">On the **Website** menu, select **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="9b8d5-108">Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare **DataSet** , quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-108">In the **Add New Item** dialog box, select **DataSet** and click **Add**.</span></span> <span data-ttu-id="9b8d5-109">Quando richiesto, è necessario aggiungere l'elemento alla cartella **App_Code** facendo clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-109">When prompted you should add the item to the **App_Code** folder by clicking **Yes**.</span></span>  
  
     <span data-ttu-id="9b8d5-110">Verrà aggiunto un nuovo file XSD **DataSet1.xsd** al progetto e verrà aperto Progettazione DataSet.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-110">This adds a new XSD file **DataSet1.xsd** to the project and opens the DataSet Designer.</span></span>  
  
3.  <span data-ttu-id="9b8d5-111">Dalla finestra della casella degli strumenti trascinare un controllo **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-111">From the Toolbox window, drag a **[TableAdapter](https://msdn.microsoft.com/library/bz9tthwx\(v=vs.100\).aspx)** control to the design surface.</span></span> <span data-ttu-id="9b8d5-112">Viene avviata la configurazione guidata **TableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="9b8d5-112">This launches the **TableAdapter** Configuration Wizard.</span></span>  
  
4.  <span data-ttu-id="9b8d5-113">Nella pagina **scegliere la connessione dati** fare clic su **nuova connessione**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-113">On the **Choose Your Data Connection** page, click **New Connection**.</span></span>  
  
5.  <span data-ttu-id="9b8d5-114">Se è la prima volta che si crea un'origine dati in Visual Studio, verrà visualizzata la pagina **Scegli origine dati** .</span><span class="sxs-lookup"><span data-stu-id="9b8d5-114">If this is the first time you've created a data source in Visual Studio, you will see the **Choose Data Source** page.</span></span> <span data-ttu-id="9b8d5-115">Nella casella **Origine dati** selezionare **Microsoft SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-115">In the **Data Source** box, select **Microsoft SQL Server**.</span></span>  
  
6.  <span data-ttu-id="9b8d5-116">Nella finestra di dialogo **Aggiungi connessione** effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9b8d5-116">In the **Add Connection** dialog box, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="9b8d5-117">Nella casella **nome server** immettere il server in cui si trova il database **AdventureWorks2008** .</span><span class="sxs-lookup"><span data-stu-id="9b8d5-117">In the **Server name** box, enter the server where the **AdventureWorks2008** database is located.</span></span>  
  
         <span data-ttu-id="9b8d5-118">L'istanza predefinita di SQL Server Express è **(local)\sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-118">The default SQL Server Express instance is **(local)\sqlexpress**.</span></span>  
  
    2.  <span data-ttu-id="9b8d5-119">Nella sezione **Accesso al server** selezionare l'opzione di accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-119">In the **Log on to the server** section, select the option that provides you access to the data.</span></span> <span data-ttu-id="9b8d5-120">**Usa autenticazione di Windows** è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-120">**Use Windows Authentication** is the default.</span></span>  
  
    3.  <span data-ttu-id="9b8d5-121">Nell'elenco **a discesa selezionare o immettere un nome di database** fare clic su **AdventureWorks2008**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-121">From the **Select or enter a database name** drop-down list, click **AdventureWorks2008**.</span></span>  
  
    4.  <span data-ttu-id="9b8d5-122">Fare clic su **OK** e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-122">Click **OK**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="9b8d5-123">Se è stata selezionata l'opzione **Usa autenticazione di SQL Server** nel Passaggio 6 (b), selezionare l'opzione per includere i dati sensibili nella stringa o per impostare le informazioni nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-123">If you selected **Use SQL Server Authentication** in the Step 6 (b), select the option whether to include the sensitive data in the string or set the information in your application code.</span></span>  
  
8.  <span data-ttu-id="9b8d5-124">Nella pagina **Salva stringa di connessione nel file di configurazione dell'applicazione** Digitare il nome per la stringa di connessione o accettare l'impostazione predefinita **AdventureWorks2008ConnectionString**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-124">On the **Save the Connection String to the Application Configuration File** page, type in the name for the connection string or accept the default **AdventureWorks2008ConnectionString**.</span></span> <span data-ttu-id="9b8d5-125">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-125">Click **Next**.</span></span>  
  
9. <span data-ttu-id="9b8d5-126">Nella pagina **scegliere un tipo di comando** selezionare **Usa istruzioni SQL**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-126">On the **Choose a Command Type** page, select **Use SQL Statements**, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="9b8d5-127">Nella pagina **immettere un'istruzione SQL** immettere la query Transact-SQL seguente per recuperare i dati dal database **AdventureWorks2008** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-127">On the **Enter a SQL Statement** page, enter the following Transact-SQL query to retrieve data from the **AdventureWorks2008** database, and then click **Next**.</span></span>  
  
    ```  
    SELECT ProductID, Name, ProductNumber, SafetyStockLevel, ReorderPoint FROM  Production.Product Order By ProductID  
    ```  
  
     <span data-ttu-id="9b8d5-128">È anche possibile creare la query facendo clic su **Generatore di query**, quindi verificare la query facendo clic su **Esegui query**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-128">You can also create the query by clicking **Query Builder**, and then verify the query by clicking **Execute Query**.</span></span> <span data-ttu-id="9b8d5-129">Se non vengono restituiti i dati previsti dalla query, è possibile che si stia utilizzando una versione precedente di AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-129">If the query does not return the expected data, you might be using an earlier version of AdventureWorks.</span></span> <span data-ttu-id="9b8d5-130">Per ulteriori informazioni sull'installazione della versione **AdventureWorks2008** di AdventureWorks, vedere [procedura dettagliata: installazione del database AdventureWorks](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span><span class="sxs-lookup"><span data-stu-id="9b8d5-130">For more information about installing the **AdventureWorks2008** version of AdventureWorks, see [Walkthrough: Installing the AdventureWorks Database](https://msdn.microsoft.com/library/aa992075\(v=vs.100\).aspx).</span></span>  
  
11. <span data-ttu-id="9b8d5-131">Nella pagina **scegliere i metodi per generare** assicurarsi di deselezionare **Crea metodi per inviare aggiornamenti direttamente al database (GenerateDBDirectMethods)**, quindi fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-131">On the **Choose Methods to Generate** page, be sure to uncheck **Create methods to send updates directly to the database (GenerateDBDirectMethods)**, and then click **Finish**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="9b8d5-132">Assicurarsi di deselezionare l'opzione di creazione.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-132">Be sure to uncheck Create</span></span>  
  
     <span data-ttu-id="9b8d5-133">È stata completata la configurazione dell'oggetto DataTable di ADO.NET come origine dati del report.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-133">You have now completed configuring the ADO.NET DataTable object as the data source for your report.</span></span> <span data-ttu-id="9b8d5-134">Nella pagina Progettazione DataSet in Visual Studio si dovrebbe visualizzare l'oggetto DataTable aggiunto, con le colonne specificate nella query.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-134">On the DataSet Designer page in Visual Studio, you should see the DataTable object you added, listing the columns specified in the query.</span></span> <span data-ttu-id="9b8d5-135">In DataSet1 sono inclusi i dati della tabella Product, basati sulla query.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-135">DataSet1 contains the data from the Product table, based on the query.</span></span>  
  
12. <span data-ttu-id="9b8d5-136">Salvare il file.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-136">Save the file.</span></span>  
  
13. <span data-ttu-id="9b8d5-137">Per visualizzare l'anteprima dei dati, fare clic su **Anteprima dati** dal menu **dati** e quindi fare clic su **Anteprima**.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-137">To preview the data, click **Preview Data** on the **Data** menu, and then click **Preview**.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="9b8d5-138">Attività successiva</span><span class="sxs-lookup"><span data-stu-id="9b8d5-138">Next Task</span></span>  
 <span data-ttu-id="9b8d5-139">È stata creata correttamente una connessione dati e una tabella di dati per il report padre.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-139">You have successfully created a data connection and a data table for the parent report.</span></span> <span data-ttu-id="9b8d5-140">Successivamente, verrà progettato il report padre utilizzando la Creazione guidata report.</span><span class="sxs-lookup"><span data-stu-id="9b8d5-140">Next, you will design the parent report using the Report Wizard.</span></span>  
  
  
