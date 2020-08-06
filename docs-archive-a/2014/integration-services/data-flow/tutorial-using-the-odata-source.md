---
title: "Esercitazione: uso dell'origine OData [SSIS] | Microsoft Docs"
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 2c64cf8b-5edb-48df-8ffe-697096258f71
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a13b04494ed00251774b490b1cc929769a869acb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636287"
---
# <a name="tutorial-using-the-odata-source-ssis"></a><span data-ttu-id="849bb-102">Esercitazione: utilizzo dell'origine OData [SSIS]</span><span class="sxs-lookup"><span data-stu-id="849bb-102">Tutorial: Using the OData Source [SSIS]</span></span>
  <span data-ttu-id="849bb-103">In questa esercitazione viene eseguito il processo per estrarre la raccolta **Dipendenti** del servizio **Northwind** OData di esempio (http://services.odata.org/V3/Northwind/Northwind.svc/) e caricarla in un file flat.</span><span class="sxs-lookup"><span data-stu-id="849bb-103">This tutorial walks you through the process to extract the **Employees** collection from the sample **Northwind** OData service (http://services.odata.org/V3/Northwind/Northwind.svc/), and then load it into a flat file.</span></span>  
  
## <a name="1-create-an-integration-services-project"></a><span data-ttu-id="849bb-104">1. Creare un progetto di Integration Services</span><span class="sxs-lookup"><span data-stu-id="849bb-104">1. Create an Integration Services Project</span></span>  
  
1.  <span data-ttu-id="849bb-105">Avviare **SQL Server Data Tools** o [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="849bb-105">Launch **SQL Server Data Tools** or [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="849bb-106">Fare clic su **File**, scegliere **Nuovo** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="849bb-106">Click **File**, point to **New**, and click **Project**.</span></span>  
  
3.  <span data-ttu-id="849bb-107">Nella finestra di dialogo **Nuovo progetto** espandere **Installato**, **Modelli**, **Business Intelligence**, quindi scegliere **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="849bb-107">In the **New Project** dialog box, expand **Installed**, expand **Templates**, expand **Business Intelligence**, and click **Integration Services**.</span></span>  
  
4.  <span data-ttu-id="849bb-108">Selezionare **Progetto di Integration Services** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="849bb-108">Select **Integration Services Project** for the type of project.</span></span>  
  
5.  <span data-ttu-id="849bb-109">Immettere un **nome** e selezionare un **percorso** per il progetto, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="849bb-109">Enter a **name** and select a **location** for the project, and click **OK**.</span></span>  
  
## <a name="2-add-and-configure-odata-source-to-the-ssis-package"></a><span data-ttu-id="849bb-110">2. Aggiungere e configurare l'origine OData per il pacchetto SSIS</span><span class="sxs-lookup"><span data-stu-id="849bb-110">2. Add and Configure OData Source to the SSIS Package</span></span>  
  
1.  <span data-ttu-id="849bb-111">Trascinare un' **Attività Flusso di dati** da **Casella degli strumenti SSIS** all'area di progettazione del flusso di controllo del pacchetto SSIS.</span><span class="sxs-lookup"><span data-stu-id="849bb-111">Drag-drop a **Data Flow Task** from the **SSIS Toolbox** on to the control flow design surface of your SSIS package.</span></span>  
  
2.  <span data-ttu-id="849bb-112">Fare clic sulla scheda **Flusso di dati** oppure fare doppio clic sull' **attività Flusso di dati** appena aggiunta per avviare l' **area di progettazione Flusso di dati**.</span><span class="sxs-lookup"><span data-stu-id="849bb-112">Click the **Data Flow** tab, or double click on the newly added **Data Flow Task** to launch the **Data Flow design surface**.</span></span>  
  
3.  <span data-ttu-id="849bb-113">Trascinare **Origine Odata** dal gruppo **Comune** in **Casella degli strumenti SSIS**.</span><span class="sxs-lookup"><span data-stu-id="849bb-113">Drag-drop **OData Source** from the **Common** group in the **SSIS Toolbox**.</span></span> <span data-ttu-id="849bb-114">Quando si installa per la prima volta, **Origine Odata** viene visualizzato nel gruppo **Comune** in **Casella degli strumenti SSIS**.</span><span class="sxs-lookup"><span data-stu-id="849bb-114">When the **OData Source** is first installed, it will appear under the **Common** group in the **SSIS Toolbox**.</span></span>  
  
4.  <span data-ttu-id="849bb-115">Fare doppio clic sul componente **Origine OData** per aprire la finestra di dialogo **Editor origine OData** .</span><span class="sxs-lookup"><span data-stu-id="849bb-115">Double click the **OData Source** component to launch the **OData Source Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="849bb-116">Fare clic su **Nuovo** per aggiungere una nuova gestione connessione OData.</span><span class="sxs-lookup"><span data-stu-id="849bb-116">Click **New...** to add a new OData Connection Manager.</span></span>  
  
6.  <span data-ttu-id="849bb-117">Immettere l'URL del servizio OData in **percorso documento di servizio**.</span><span class="sxs-lookup"><span data-stu-id="849bb-117">Enter the OData service URL for **Service document location**.</span></span> <span data-ttu-id="849bb-118">Può essere l'URL del documento di servizio o l'URL di un'entità o di un feed specifico.</span><span class="sxs-lookup"><span data-stu-id="849bb-118">This can be the URL to the service document, or to a specific feed or entity.</span></span> <span data-ttu-id="849bb-119">Ai fini di questa esercitazione, digitare [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/) .</span><span class="sxs-lookup"><span data-stu-id="849bb-119">For the purpose of this tutorial, type [http://services.odata.org/V3/Northwind/Northwind.svc/](http://services.odata.org/V3/Northwind/Northwind.svc/).</span></span>  
  
7.  <span data-ttu-id="849bb-120">Verificare che sia selezionato **Autenticazione di Windows** come **autenticazione** da utilizzare per accedere al servizio OData.</span><span class="sxs-lookup"><span data-stu-id="849bb-120">Confirm that **Windows Authentication** is selected for the **authentication** to use to access the OData Service.</span></span> <span data-ttu-id="849bb-121">**Autenticazione di Windows** è selezionato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="849bb-121">**Windows Authentication** is selected by default.</span></span> <span data-ttu-id="849bb-122">Per utilizzare l'autenticazione di base, selezionare **Usa il nome utente e la password seguenti**.</span><span class="sxs-lookup"><span data-stu-id="849bb-122">To use basic authentication, select **Use this user name and password**.</span></span>  
  
8.  <span data-ttu-id="849bb-123">Fare clic su **Test connessione** per la connessione e fare clic su **OK** per creare un'istanza della gestione connessione OData.</span><span class="sxs-lookup"><span data-stu-id="849bb-123">Click **Test Connection** to the connection, and click **OK** to create an instance of OData Connection Manager.</span></span>  
  
9. <span data-ttu-id="849bb-124">Nella finestra di dialogo **Editor origine OData** , verificare che **Raccolta** sia selezionato per l'opzione **Utilizza raccolta in percorso risorse** .</span><span class="sxs-lookup"><span data-stu-id="849bb-124">In the **OData Source Editor** Dialog Box, confirm that **Collection** is selected for **Use collection on resource path** option.</span></span>  
  
10. <span data-ttu-id="849bb-125">Selezionare **Dipendenti** nell'elenco a discesa **Raccolta**.</span><span class="sxs-lookup"><span data-stu-id="849bb-125">From the **Collection** drop down list, select **Employees**.</span></span>  
  
11. <span data-ttu-id="849bb-126">Immettere tutti i filtri o le opzioni query OData aggiuntive per **Opzioni query**.</span><span class="sxs-lookup"><span data-stu-id="849bb-126">Enter any additional OData query options or filters for **Query Options**.</span></span> <span data-ttu-id="849bb-127">Ex.</span><span class="sxs-lookup"><span data-stu-id="849bb-127">Ex.</span></span> <span data-ttu-id="849bb-128">$orderby=CompanyName&$top=100.</span><span class="sxs-lookup"><span data-stu-id="849bb-128">$orderby=CompanyName&$top=100.</span></span> <span data-ttu-id="849bb-129">Ai fini di questa esercitazione immettere **$top=5**.</span><span class="sxs-lookup"><span data-stu-id="849bb-129">For the purpose of this tutorial, enter **$top=5**.</span></span>  
  
12. <span data-ttu-id="849bb-130">Fare clic su **Anteprima** per visualizzare un'anteprima dei dati.</span><span class="sxs-lookup"><span data-stu-id="849bb-130">Click **Preview** to preview the data.</span></span>  
  
13. <span data-ttu-id="849bb-131">Fare clic su **Colonne** nel riquadro di navigazione sinistro per passare alla pagina **Colonne** .</span><span class="sxs-lookup"><span data-stu-id="849bb-131">Click **Columns** in the left navigation pane to switch to the **Columns** page.</span></span>  
  
14. <span data-ttu-id="849bb-132">Scegliere **EmployeeID**, **FirstName**e **LastName** da **Colonne esterne disponibili** selezionando le caselle di controllo.</span><span class="sxs-lookup"><span data-stu-id="849bb-132">Select **EmployeeID**, **FirstName**, and **LastName** from **Available External Columns** by checking the check boxes.</span></span>  
  
15. <span data-ttu-id="849bb-133">Fare clic su **OK** per chiudere la finestra di dialogo **Editor origine OData** .</span><span class="sxs-lookup"><span data-stu-id="849bb-133">Click **OK** to close the **OData Source Editor** dialog box.</span></span>  
  
## <a name="3-add-flat-file-destination-and-test-the-solution"></a><span data-ttu-id="849bb-134">3. Aggiungere la destinazione del file flat e testare la soluzione</span><span class="sxs-lookup"><span data-stu-id="849bb-134">3. Add Flat File Destination and Test the Solution</span></span>  
  
1.  <span data-ttu-id="849bb-135">Trascinare una **Destinazione file flat** dalla **casella degli strumenti SSIS** all'area di progettazione del flusso di dati sotto il componente **Origine Odata** .</span><span class="sxs-lookup"><span data-stu-id="849bb-135">Now, drag-drop a **Flat File Destination** from **SSIS Toolbox** to the Data Flow design surface below the **OData Source** component.</span></span>  
  
2.  <span data-ttu-id="849bb-136">Connettere il componente **Origine Odata** al componente **Destinazione file flat** utilizzando la freccia blu.</span><span class="sxs-lookup"><span data-stu-id="849bb-136">Connect **OData Source** component with the **Flat File Destination** component using blue arrow.</span></span>  
  
3.  <span data-ttu-id="849bb-137">Fare doppio clic su **Destinazione file flat**.</span><span class="sxs-lookup"><span data-stu-id="849bb-137">Double-click on **Flat File Destination**.</span></span> <span data-ttu-id="849bb-138">Viene visualizzata la finestra di dialogo **Editor destinazione file flat** .</span><span class="sxs-lookup"><span data-stu-id="849bb-138">You should see the **Flat File Destination Editor** dialog box.</span></span>  
  
4.  <span data-ttu-id="849bb-139">Nella finestra di dialogo **Editor destinazione file flat** fare clic su **Nuovo** per creare una nuova gestione connessione file flat.</span><span class="sxs-lookup"><span data-stu-id="849bb-139">In the **Flat File Destination Editor** dialog box, click **New** to create a new flat file connection manager.</span></span>  
  
5.  <span data-ttu-id="849bb-140">Nella finestra di dialogo **Formato file flat** selezionare **Delimitato**.</span><span class="sxs-lookup"><span data-stu-id="849bb-140">In the **Flat File Format** dialog box, select **Delimited**.</span></span> <span data-ttu-id="849bb-141">Viene visualizzata la finestra di dialogo **Editor gestione connessione file flat** .</span><span class="sxs-lookup"><span data-stu-id="849bb-141">You should see the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
6.  <span data-ttu-id="849bb-142">Nella finestra di dialogo **Editor gestione connessione file flat** immettere **c:\Employees.txt**in **Nome file**.</span><span class="sxs-lookup"><span data-stu-id="849bb-142">In the **Flat File Connection Manager Editor** dialog box, for the **File name**, enter **c:\Employees.txt**.</span></span>  
  
7.  <span data-ttu-id="849bb-143">Fare clic su **Colonne**nel pannello di navigazione sinistro.</span><span class="sxs-lookup"><span data-stu-id="849bb-143">In the left navigation pane, click **Columns**.</span></span> <span data-ttu-id="849bb-144">In questa pagina è possibile visualizzare l'anteprima dei dati.</span><span class="sxs-lookup"><span data-stu-id="849bb-144">You can preview the data on this page.</span></span>  
  
8.  <span data-ttu-id="849bb-145">Fare clic su OK per chiudere la finestra di dialogo **Editor gestione connessione file flat** .</span><span class="sxs-lookup"><span data-stu-id="849bb-145">Click OK to close the **Flat File Connection Manager** Editor dialog box.</span></span>  
  
9. <span data-ttu-id="849bb-146">Nella finestra di dialogo **Editor destinazione file flat** fare clic su **Mapping** nel riquadro di navigazione sinistro.</span><span class="sxs-lookup"><span data-stu-id="849bb-146">In the **Flat File Destination Editor** dialog box, click **Mappings** in the left navigation pane.</span></span> <span data-ttu-id="849bb-147">Controllare i mapping.</span><span class="sxs-lookup"><span data-stu-id="849bb-147">Review the mappings.</span></span>  
  
10. <span data-ttu-id="849bb-148">Fare clic su OK per chiudere la finestra di dialogo **Editor destinazione file flat** .</span><span class="sxs-lookup"><span data-stu-id="849bb-148">Click OK to close the **Flat File Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="849bb-149">Compilare ed eseguire il pacchetto SSIS.</span><span class="sxs-lookup"><span data-stu-id="849bb-149">Compile and execute the SSIS package.</span></span> <span data-ttu-id="849bb-150">Verificare che il file di output venga creato con l'ID, il nome e il cognome di 5 dipendenti dal feed OData.</span><span class="sxs-lookup"><span data-stu-id="849bb-150">Verify that the output file is created with ID, First Name, and Last Name for 5 employees from the OData feed.</span></span>  
  
  
