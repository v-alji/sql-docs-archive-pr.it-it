---
title: 'Passaggio 4: Distribuzione del pacchetto della lezione 6 | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: b613cef7-7993-4d89-a429-a8251d74d435
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8c5109dc96af138bbd0c8c0087e8b73cf3bac435
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637995"
---
# <a name="step-4-deploying-the-lesson-6-package"></a><span data-ttu-id="49003-102">Passaggio 4: Distribuzione del pacchetto della lezione 6</span><span class="sxs-lookup"><span data-stu-id="49003-102">Step 4: Deploying the Lesson 6 Package</span></span>
  <span data-ttu-id="49003-103">La distribuzione del pacchetto implica l'aggiunta del pacchetto al catalogo SSISDB in Integration Services in un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49003-103">Deploying the package involves adding the package to the SSISDB catalog in Integration Services on an instance of SQL Server.</span></span> <span data-ttu-id="49003-104">In questa lezione verranno illustrate le procedure per aggiungere il pacchetto creato nella lezione 6 al catalogo SSISDB, impostare il parametro ed eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="49003-104">In this lesson you will add the Lesson 6 package to the SSISDB catalog, set the parameter, and execute the package.</span></span> <span data-ttu-id="49003-105">Per questa lezione verrà usato SQL Server Management Studio per aggiungere il pacchetto della lezione 6 al catalogo SSISDB e distribuire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="49003-105">For this lesson you will use SQL Server Management Studio to add the Lesson 6 package to the SSISDB catalog, and deploy the package.</span></span> <span data-ttu-id="49003-106">Dopo avere distribuito il pacchetto, modificare il parametro in modo da puntare a un nuovo percorso, quindi eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="49003-106">After deploying the package you will modify the parameter to point to a new location then execute the package.</span></span>  
  
 <span data-ttu-id="49003-107">In questa lezione verranno illustrate le procedure seguenti:</span><span class="sxs-lookup"><span data-stu-id="49003-107">In this lesson you will:</span></span>  
  
-   <span data-ttu-id="49003-108">Aggiungere il pacchetto al catalogo SSISDB nel nodo SSIS in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49003-108">Add the package to the SSISDB catalog in the SSIS node in SQL Server.</span></span>  
  
-   <span data-ttu-id="49003-109">Distribuire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="49003-109">Deploy the package.</span></span>  
  
-   <span data-ttu-id="49003-110">Impostare il valore di parametro del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="49003-110">Set the package parameter value.</span></span>  
  
-   <span data-ttu-id="49003-111">Eseguire il pacchetto in SSMS.</span><span class="sxs-lookup"><span data-stu-id="49003-111">Execute the package in SSMS.</span></span>  
  
### <a name="to-locate-or-add-the-ssisdb-catalog"></a><span data-ttu-id="49003-112">Per individuare o aggiungere il catalogo SSISDB</span><span class="sxs-lookup"><span data-stu-id="49003-112">To Locate or add the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="49003-113">Fare clic sul pulsante Start, scegliere Tutti i programmi, Microsoft SQL Server 2012, quindi fare clic su SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="49003-113">Click Start, point to All Programs, point to Microsoft SQL Server 2012, and then click SQL Management Studio.</span></span>  
  
2.  <span data-ttu-id="49003-114">Nella finestra di dialogo Connetti al server verificare le impostazioni predefinite, quindi fare clic su Connetti.</span><span class="sxs-lookup"><span data-stu-id="49003-114">On the Connect to Server dialog box, verify the default settings, and then click Connect.</span></span> <span data-ttu-id="49003-115">Per eseguire la connessione, è necessario che nella casella Nome server sia presente il nome del computer in cui è installato SQL Server.</span><span class="sxs-lookup"><span data-stu-id="49003-115">To connect, the Server name box must contain the name of the computer where SQL Server is installed.</span></span> <span data-ttu-id="49003-116">Se il motore di database è un'istanza denominata, nella casella Nome server deve essere contenuto anche il nome dell'istanza nel formato <nome_computer>\\<nome_istanza>.</span><span class="sxs-lookup"><span data-stu-id="49003-116">If the Database Engine is a named instance, the Server name box should also contain the instance name in the format <computer_name>\\<instance_name>.</span></span>  
  
3.  <span data-ttu-id="49003-117">In Esplora oggetti espandere Cataloghi di Integration Services.</span><span class="sxs-lookup"><span data-stu-id="49003-117">In Object Explorer expand Integration Services Catalogs.</span></span>  
  
4.  <span data-ttu-id="49003-118">Se in Cataloghi di Integration Services non è elencato alcun catalogo, aggiungere il catalogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="49003-118">If there are no catalogs listed under Integration Services Catalogs then add the SSISDB catalog.</span></span>  
  
5.  <span data-ttu-id="49003-119">Per aggiungere il catalogo SSISDB, fare clic con il pulsante destro del mouse su Cataloghi di Integration Services e scegliere Crea catalogo.</span><span class="sxs-lookup"><span data-stu-id="49003-119">To Add the SSISDB catalog, right-click Integration Services Catalogs and click Create Catalog.</span></span>  
  
6.  <span data-ttu-id="49003-120">Nella finestra di dialogo Crea catalogo selezionare Abilita integrazione con CLR.</span><span class="sxs-lookup"><span data-stu-id="49003-120">On the Create Catalog dialog box select Enable CLR Integration.</span></span>  
  
7.  <span data-ttu-id="49003-121">Nella casella Password digitare una nuova password, quindi digitarla nuovamente nella casella Conferma password.</span><span class="sxs-lookup"><span data-stu-id="49003-121">In the Password box, type a new password then type it again in the Retype Password box.</span></span> <span data-ttu-id="49003-122">Assicurarsi di ricordare la password digitata.</span><span class="sxs-lookup"><span data-stu-id="49003-122">Be sure to remember the password you type.</span></span>  
  
8.  <span data-ttu-id="49003-123">Fare clic su OK per aggiungere il catalogo SSISDB.</span><span class="sxs-lookup"><span data-stu-id="49003-123">Click OK to add the SSISDB catalog.</span></span>  
  
### <a name="to-add-the-package-to-the-ssisdb-catalog"></a><span data-ttu-id="49003-124">Per aggiungere il pacchetto al catalogo SSISDB</span><span class="sxs-lookup"><span data-stu-id="49003-124">To add the package to the SSISDB catalog</span></span>  
  
1.  <span data-ttu-id="49003-125">In Esplora oggetti fare clic con il pulsante destro del mouse su SSISDB, quindi scegliere Crea cartella.</span><span class="sxs-lookup"><span data-stu-id="49003-125">In Object Explorer, right-click SSISDB and click Create Folder.</span></span>  
  
2.  <span data-ttu-id="49003-126">Nella finestra di dialogo Crea cartella digitare SSIS Tutorial nella casella Nome cartella e fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="49003-126">In the Create Folder dialog box type SSIS Tutorial in the Folder name box and click OK.</span></span>  
  
3.  <span data-ttu-id="49003-127">Espandere la cartella SSIS Tutorial, fare clic con il pulsante destro del mouse su Progetti e scegliere Importa pacchetti.</span><span class="sxs-lookup"><span data-stu-id="49003-127">Expand the SSIS Tutorial folder, right-click Projects, and click Import Packages.</span></span>  
  
4.  <span data-ttu-id="49003-128">Nella pagina introduttiva della Conversione guidata progetto di Integration Services fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="49003-128">On the Integration Services Project Conversion Wizard Introduction page click Next.</span></span>  
  
5.  <span data-ttu-id="49003-129">Nella pagina Individua pacchetti verificare che sia selezionato File system nell'elenco Origine, quindi fare clic su Sfoglia.</span><span class="sxs-lookup"><span data-stu-id="49003-129">On the Locate Packages page, ensure that File system is selected in the Source list, then click Browse.</span></span>  
  
6.  <span data-ttu-id="49003-130">Nella finestra di dialogo Sfoglia cartella selezionare la cartella contenente il progetto SSIS Tutorial, quindi fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="49003-130">On the Browse For Folder dialog box, browse to the folder containing the SSIS Tutorial project, then click OK.</span></span>  
  
7.  <span data-ttu-id="49003-131">Scegliere Avanti.</span><span class="sxs-lookup"><span data-stu-id="49003-131">Click Next.</span></span>  
  
8.  <span data-ttu-id="49003-132">Nella pagina Seleziona pacchetti verranno visualizzati tutti e sei i pacchetti di SSIS Tutorial.</span><span class="sxs-lookup"><span data-stu-id="49003-132">On the Select Packages page you should see all six packages from the SSIS Tutorial.</span></span> <span data-ttu-id="49003-133">Nell'elenco Pacchetti selezionare Lesson 6.dtsx, quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="49003-133">In the Packages list, select Lesson 6.dtsx, then click Next.</span></span>  
  
9. <span data-ttu-id="49003-134">Nella pagina Seleziona destinazione digitare SSIS Tutorial Deployment nella casella Nome progetto, quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="49003-134">On the Select Destination page, type SSIS Tutorial Deployment in the Project Name box then click Next.</span></span>  
  
10. <span data-ttu-id="49003-135">Fare clic su Avanti in tutte le pagine rimanenti della procedura guidata finché non si giunge alla pagina Verifica.</span><span class="sxs-lookup"><span data-stu-id="49003-135">Click Next on each of the remaining wizard pages until you get to the Review page.</span></span>  
  
11. <span data-ttu-id="49003-136">Nella pagina Verifica fare clic su Converti.</span><span class="sxs-lookup"><span data-stu-id="49003-136">On the Review page, click Convert.</span></span>  
  
12. <span data-ttu-id="49003-137">Al termine della conversione fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="49003-137">When the conversion completes, click Close.</span></span>  
  
 <span data-ttu-id="49003-138">Quando si chiude la Conversione guidata progetto di Integration Services, SSIS visualizza la Distribuzione guidata Integration Services.</span><span class="sxs-lookup"><span data-stu-id="49003-138">When you close the Integration Services Project Conversion Wizard, SSIS displays the Integration Services Deployment Wizard.</span></span> <span data-ttu-id="49003-139">Usare questa procedura guidata per distribuire il pacchetto della lezione 6.</span><span class="sxs-lookup"><span data-stu-id="49003-139">You will use this wizard now to deploy the Lesson 6 package.</span></span>  
  
1.  <span data-ttu-id="49003-140">Nella pagina introduttiva della Distribuzione guidata Integration Services verificare i passaggi per la distribuzione del progetto, quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="49003-140">On the Integration Services Deployment Wizard Introduction page, review the steps for deploying the project, then click Next.</span></span>  
  
2.  <span data-ttu-id="49003-141">Nella pagina Seleziona destinazione verificare che il nome del server sia l'istanza di SQL Server che contiene il catalogo SSISDB e che il percorso mostri SSIS Tutorial Deployment, quindi fare clic su Avanti.</span><span class="sxs-lookup"><span data-stu-id="49003-141">On the Select Destination page verify that the server name is the instance of SQL Server containing the SSISDB catalog and that the path shows SSIS Tutorial Deployment, then click Next.</span></span>  
  
3.  <span data-ttu-id="49003-142">Nella pagina Verifica rivedere il riepilogo, quindi fare clic su Distribuisci.</span><span class="sxs-lookup"><span data-stu-id="49003-142">On the Review page, review the Summary then click Deploy.</span></span>  
  
4.  <span data-ttu-id="49003-143">Al termine della distribuzione fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="49003-143">When the deployment completes, click Close.</span></span>  
  
5.  <span data-ttu-id="49003-144">In Esplora oggetti fare clic con il pulsante destro del mouse su Cataloghi di Integration Services e scegliere Aggiorna.</span><span class="sxs-lookup"><span data-stu-id="49003-144">In Object Explorer, right-click Integration Services Catalogs and click Refresh.</span></span>  
  
6.  <span data-ttu-id="49003-145">Espandere Cataloghi di Integration Services, quindi SSISDB.</span><span class="sxs-lookup"><span data-stu-id="49003-145">Expand Integration Services Catalogs then expand SSISDB.</span></span> <span data-ttu-id="49003-146">Continuare a espandere l'albero in SSIS Tutorial finché non si espande tutto il progetto.</span><span class="sxs-lookup"><span data-stu-id="49003-146">Continue to Expand the tree under SSIS Tutorial until you have completely expanded the project.</span></span> <span data-ttu-id="49003-147">Nel nodo Pacchetti del nodo SSIS Tutorial Deployment verrà visualizzato Lesson 6.dtsx.</span><span class="sxs-lookup"><span data-stu-id="49003-147">You should see Lesson 6.dtsx under the Packages node of the SSIS Tutorial Deployment node.</span></span>  
  
 <span data-ttu-id="49003-148">Per verificare che il pacchetto sia completo, fare clic con il pulsante destro del mouse su Lesson 6.dtsx e scegliere Configura.</span><span class="sxs-lookup"><span data-stu-id="49003-148">To verify that the package is complete, right-click Lesson 6.dtsx and click Configure.</span></span> <span data-ttu-id="49003-149">Nella finestra di dialogo Configura selezionare Parametri e verificare che sia presente una voce con Lesson 6.dtsx come Contenitore, VarFolderName come Nome e il percorso di New Sample Data come valore, quindi fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="49003-149">On the Configure dialog box, select Parameters and verify that there is an entry with Lesson 6.dtsx as the Container, VarFolderName as the Name and the path to New Sample Data as the value, then click Close.</span></span>  
  
 <span data-ttu-id="49003-150">Prima di continuare, creare una nuova cartella di dati di esempio, denominarla Sample Data Two e copiarvi i tre file di esempio originali.</span><span class="sxs-lookup"><span data-stu-id="49003-150">Before continuing create a new sample data folder, name it Sample Data Two, and copy any three of the original sample files into it.</span></span>  
  
### <a name="to-create-and-populate-a-new-sample-data-folder"></a><span data-ttu-id="49003-151">Per creare e popolare una nuova cartella di dati di esempio</span><span class="sxs-lookup"><span data-stu-id="49003-151">To create and populate a new sample data folder</span></span>  
  
1.  <span data-ttu-id="49003-152">In Esplora risorse al livello di radice dell'unità, ad esempio, C:\\, creare una nuova cartella denominata Sample Data Two.</span><span class="sxs-lookup"><span data-stu-id="49003-152">In Windows Explorer, at the root level of your drive (for example, C:\\), create a new folder named Sample Data Two.</span></span>  
  
2.  <span data-ttu-id="49003-153">Aprire la cartella c:\Programmi\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data, quindi copiare i tre file di esempio dalla cartella.</span><span class="sxs-lookup"><span data-stu-id="49003-153">Open the c:\Program Files\Microsoft SQL Server\110\Samples\Integration Services\Tutorial\Creating a Simple ETL Package\Sample Data folder and then copy any three of the sample files from the folder.</span></span>  
  
3.  <span data-ttu-id="49003-154">Incollare i file copiati nella cartella New Sample Data.</span><span class="sxs-lookup"><span data-stu-id="49003-154">In the New Sample Data folder, paste the copied files.</span></span>  
  
### <a name="to-change-the-package-parameter-to-point-to-the-new-sample-data"></a><span data-ttu-id="49003-155">Per modificare il parametro del pacchetto in modo da puntare ai nuovi dati di esempio</span><span class="sxs-lookup"><span data-stu-id="49003-155">To change the package parameter to point to the new sample data</span></span>  
  
1.  <span data-ttu-id="49003-156">In Esplora oggetti fare clic con il pulsante destro del mouse su Lesson 6.dtsx e scegliere Configura.</span><span class="sxs-lookup"><span data-stu-id="49003-156">In Object Explorer, right click Lesson 6.dtsx and click Configure.</span></span>  
  
2.  <span data-ttu-id="49003-157">Nella finestra di dialogo Configura modificare il valore del parametro in modo da puntare al percorso di Sample Data Two.</span><span class="sxs-lookup"><span data-stu-id="49003-157">On the Configure dialog box, change the parameter value to the path to Sample Data Two.</span></span> <span data-ttu-id="49003-158">Ad esempio C:\Sample Data Two se la nuova cartella è stata posizionata nella cartella radice dell'unità C.</span><span class="sxs-lookup"><span data-stu-id="49003-158">For example C:\Sample Data Two if you placed the new folder in the root folder on the C drive.</span></span>  
  
3.  <span data-ttu-id="49003-159">Fare clic su OK per chiudere la finestra di dialogo Configura.</span><span class="sxs-lookup"><span data-stu-id="49003-159">Click OK to close the Configure dialog box.</span></span>  
  
### <a name="to-test-the-lesson-6-package-deployment"></a><span data-ttu-id="49003-160">Per testare la distribuzione del pacchetto creato nella lezione 6</span><span class="sxs-lookup"><span data-stu-id="49003-160">To test the Lesson 6 package deployment</span></span>  
  
1.  <span data-ttu-id="49003-161">In Esplora oggetti fare clic con il pulsante destro del mouse su Lesson 6.dtsx e scegliere Esegui.</span><span class="sxs-lookup"><span data-stu-id="49003-161">In Object Explorer, right click Lesson 6.dtsx and click Execute.</span></span>  
  
2.  <span data-ttu-id="49003-162">Nella finestra di dialogo Esegui pacchetto fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="49003-162">On the Execute Package dialog box, click OK.</span></span>  
  
3.  <span data-ttu-id="49003-163">Nella finestra di dialogo del messaggio fare clic su Sì per aprire il report della panoramica.</span><span class="sxs-lookup"><span data-stu-id="49003-163">On the message dialog box click Yes to open Overview Report.</span></span>  
  
 <span data-ttu-id="49003-164">Verrà visualizzato il report della panoramica per il pacchetto in cui è presente il nome del pacchetto e un riepilogo dello stato.</span><span class="sxs-lookup"><span data-stu-id="49003-164">The Overview report for the package is displayed showing the name of the package and a status summary.</span></span> <span data-ttu-id="49003-165">La sezione Panoramica sulle esecuzioni illustra il risultato di ogni attività nel pacchetto e la sezione Parametri usati mostra i nomi e i valori di tutti i parametri usati nell'esecuzione del pacchetto, compreso VarFolderName.</span><span class="sxs-lookup"><span data-stu-id="49003-165">The Execution Overview section shows the result from each task in the package and the Parameters Used section shows the names and values of all parameters used in the package execution, including VarFolderName.</span></span>  
  
  
