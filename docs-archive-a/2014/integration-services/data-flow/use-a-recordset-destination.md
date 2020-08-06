---
title: Usare una destinazione recordset | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Recordset destination
ms.assetid: a7b143dc-8008-404f-83b0-b45ffbca6029
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 34d1d5a7aa76876a9d8718b691b1d24a8835e2e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636285"
---
# <a name="use-a-recordset-destination"></a><span data-ttu-id="6ac7f-102">Utilizzo di una destinazione recordset</span><span class="sxs-lookup"><span data-stu-id="6ac7f-102">Use a Recordset Destination</span></span>
  <span data-ttu-id="6ac7f-103">La destinazione recordset non salva i dati in un'origine dati esterna,</span><span class="sxs-lookup"><span data-stu-id="6ac7f-103">The Recordset destination does not save data to an external data source.</span></span> <span data-ttu-id="6ac7f-104">ma in un recordset in memoria archiviato in una variabile del pacchetto [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] del tipo di dati `Object`.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-104">Instead, the Recordset destination saves data in memory in a recordset that is stored in an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package variable of the `Object` data type.</span></span> <span data-ttu-id="6ac7f-105">Dopo che la destinazione recordset ha salvato i dati, in genere si utilizza un contenitore Ciclo Foreach con l'enumeratore Foreach ADO per elaborare una riga del recordset alla volta.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-105">After the Recordset destination saves the data, you typically use a Foreach Loop container with the Foreach ADO enumerator to process one row of the recordset at a time.</span></span> <span data-ttu-id="6ac7f-106">L'enumeratore Foreach ADO salva il valore di ogni colonna della riga corrente in una variabile del pacchetto distinta.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-106">The Foreach ADO enumerator saves the value from each column of the current row into a separate package variable.</span></span> <span data-ttu-id="6ac7f-107">Quindi, le attività configurate nel contenitore Ciclo Foreach leggono tali valori dalle variabili ed eseguono alcune azioni.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-107">Then, the tasks that you configure inside the Foreach Loop container read those values from the variables and perform some action with them.</span></span>  
  
 <span data-ttu-id="6ac7f-108">È possibile utilizzare la destinazione recordset in molti scenari diversi.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-108">You can use the Recordset destination in many different scenarios.</span></span> <span data-ttu-id="6ac7f-109">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-109">Here are some examples:</span></span>  
  
-   <span data-ttu-id="6ac7f-110">È possibile usare un'attività Invia messaggi e il linguaggio delle espressioni di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] per inviare un messaggio di posta elettronica personalizzato per ogni riga del recordset.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-110">You can use a Send Mail task and the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language to send a customized e-mail message for each row in the recordset.</span></span>  
  
-   <span data-ttu-id="6ac7f-111">È possibile utilizzare un componente script configurato come origine, all'interno di un'attività Flusso di dati, per leggere i valori delle colonne del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-111">You can use a Script component configured as a source, inside a Data Flow task, to read the column values into the columns of the data flow.</span></span> <span data-ttu-id="6ac7f-112">Quindi, è possibile utilizzare trasformazioni e destinazioni per trasformare e salvare la riga.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-112">Then, you can use transformations and destinations to transform and save the row.</span></span> <span data-ttu-id="6ac7f-113">In questo esempio l'attività Flusso di dati viene eseguita una volta per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-113">In this example, the Data Flow task runs once for each row.</span></span>  
  
 <span data-ttu-id="6ac7f-114">Nelle sezioni seguenti viene descritto il processo generale di utilizzo della destinazione recordset e viene quindi illustrato un esempio specifico di utilizzo della destinazione.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-114">The following sections first describe the general process of using the Recordset destination and then show a specific example of how to use the destination.</span></span>  
  
## <a name="general-steps-to-using-a-recordset-destination"></a><span data-ttu-id="6ac7f-115">Passaggi generali per l'utilizzo di una destinazione recordset</span><span class="sxs-lookup"><span data-stu-id="6ac7f-115">General Steps to Using a Recordset Destination</span></span>  
 <span data-ttu-id="6ac7f-116">Nella procedura seguente sono riepilogati i passaggi necessari per salvare dati in una destinazione recordset e quindi utilizzare il contenitore Ciclo Foreach per elaborare ogni riga.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-116">The following procedure summarizes the steps that are required to save data to a Recordset destination, and then use the Foreach Loop container to process each row.</span></span>  
  
#### <a name="to-save-data-to-a-recordset-destination-and-process-each-row-by-using-the-foreach-loop-container"></a><span data-ttu-id="6ac7f-117">Per salvare dati in una destinazione recordset ed elaborare ogni riga tramite il contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="6ac7f-117">To save data to a Recordset destination and process each row by using the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="6ac7f-118">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]creare o aprire un pacchetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ac7f-118">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], create or open an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package.</span></span>  
  
2.  <span data-ttu-id="6ac7f-119">Creare una variabile che conterrà il recordset salvato in memoria dalla destinazione recordset, quindi impostare il relativo tipo su `Object`.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-119">Create a variable that will contain the recordset saved into memory by the Recordset destination, and set the variable's type to `Object`.</span></span>  
  
3.  <span data-ttu-id="6ac7f-120">Creare variabili aggiuntive dei tipi appropriati per contenere i valori di ogni colonna del recordset che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-120">Create additional variables of the appropriate types to contain the values of each column in the recordset that you want to use.</span></span>  
  
4.  <span data-ttu-id="6ac7f-121">Aggiungere e configurare la gestione connessione richiesta dall'origine dati che si intende utilizzare nel flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-121">Add and configure the connection manager required by the data source that you plan to use in your data flow.</span></span>  
  
5.  <span data-ttu-id="6ac7f-122">Aggiungere un'attività Flusso di dati al pacchetto, quindi nella scheda Flusso di dati di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] configurare le origini e le trasformazioni per il caricamento e la trasformazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-122">Add a Data Flow task to the package, and on the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, configure sources and transformations to load and transform the data.</span></span>  
  
6.  <span data-ttu-id="6ac7f-123">Aggiungere una destinazione recordset al flusso di dati e connetterla alle trasformazioni.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-123">Add a Recordset destination to the data flow and connect it to the transformations.</span></span> <span data-ttu-id="6ac7f-124">Per la proprietà `VariableName` della destinazione recordset, immettere il nome della variabile creata per contenere il recordset.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-124">For the `VariableName` property of the Recordset destination, enter the name of the variable that you created to hold the recordset.</span></span>  
  
7.  <span data-ttu-id="6ac7f-125">Nella scheda Flusso di controllo di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] aggiungere un contenitore Ciclo Foreach e connetterlo dopo l'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-125">On the Control Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container and connect this container after the Data Flow task.</span></span> <span data-ttu-id="6ac7f-126">Aprire quindi **Editor ciclo Foreach** per configurare il contenitore con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-126">Then, open the **Foreach Loop Editor** to configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="6ac7f-127">Nella pagina **Raccolta** selezionare l'enumeratore Foreach ADO.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-127">On the **Collection** page, select the Foreach ADO Enumerator.</span></span> <span data-ttu-id="6ac7f-128">Quindi, per **Variabile di origine oggetto ADO**, selezionare la variabile che contiene il recordset.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-128">Then, for **ADO object source variable**, select the variable that contains the recordset.</span></span>  
  
    2.  <span data-ttu-id="6ac7f-129">Nella pagina **Mapping variabili** eseguire il mapping dell'indice in base zero di ogni colonna che si desidera usare alla variabile appropriata.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-129">On the **Variable Mappings** page, map the zero-based index of each column that you want to use to the appropriate variable.</span></span>  
  
         <span data-ttu-id="6ac7f-130">A ogni iterazione del ciclo, l'enumeratore popola queste variabili con i valori delle colonne della riga corrente.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-130">On each iteration of the loop, the enumerator populates these variables with the column values from the current row.</span></span>  
  
8.  <span data-ttu-id="6ac7f-131">Nel contenitore Ciclo Foreach aggiungere e configurare attività per elaborare una riga del recordset alla volta leggendo i valori dalle variabili.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-131">Inside the Foreach Loop container, add and configure tasks to process one row of the recordset at a time by reading the values from the variables.</span></span>  
  
## <a name="example-of-using-the-recordset-destination"></a><span data-ttu-id="6ac7f-132">Esempio di utilizzo della destinazione recordset</span><span class="sxs-lookup"><span data-stu-id="6ac7f-132">Example of Using the Recordset Destination</span></span>  
 <span data-ttu-id="6ac7f-133">Nell'esempio seguente l'attività Flusso di dati carica informazioni sui dipendenti di [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] dalla tabella Sales.SalesPerson in una destinazione recordset.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-133">In the following example, the Data Flow task loads information about [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] employees from the Sales.SalesPerson table into a Recordset destination.</span></span> <span data-ttu-id="6ac7f-134">Quindi, un contenitore Ciclo Foreach legge una riga di dati alla volta e chiama un'attività Invia messaggi.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-134">Then, a Foreach Loop container reads one row of data at a time, and calls a Send Mail task.</span></span> <span data-ttu-id="6ac7f-135">L'attività Invia messaggi utilizza espressioni per inviare un messaggio di posta elettronica personalizzato a ogni venditore sull'importo del premio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-135">The Send Mail task uses expressions to send a customized e-mail message to each salesperson about the amount of his or her bonus.</span></span>  
  
#### <a name="to-create-the-project-and-configure-the-variables"></a><span data-ttu-id="6ac7f-136">Per creare il progetto e configurare le variabili</span><span class="sxs-lookup"><span data-stu-id="6ac7f-136">To create the project and configure the variables</span></span>  
  
1.  <span data-ttu-id="6ac7f-137">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]creare un nuovo progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ac7f-137">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], create a new [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project.</span></span>  
  
2.  <span data-ttu-id="6ac7f-138">Scegliere **Variabili** dal menu **SSIS**.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-138">On the **SSIS** menu, select **Variables**.</span></span>  
  
3.  <span data-ttu-id="6ac7f-139">Nella finestra **Variabili** creare le variabili che conterranno il recordset e i valori delle colonne della riga corrente:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-139">In the **Variables** window, create the variables that will hold the recordset and the column values from the current row:</span></span>  
  
    1.  <span data-ttu-id="6ac7f-140">Creare una variabile denominata `BonusRecordset` e impostare il relativo tipo su `Object`.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-140">Create a variable named, `BonusRecordset`, and set its type to `Object`.</span></span>  
  
         <span data-ttu-id="6ac7f-141">La variabile `BonusRecordset` contiene il recordset.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-141">The `BonusRecordset` variable holds the recordset.</span></span>  
  
    2.  <span data-ttu-id="6ac7f-142">Creare una variabile denominata `EmailAddress` e impostare il relativo tipo su `String`.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-142">Create a variable named, `EmailAddress`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="6ac7f-143">La variabile `EmailAddress` contiene l'indirizzo di posta elettronica del venditore.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-143">The `EmailAddress` variable holds the salesperson's e-mail address.</span></span>  
  
    3.  <span data-ttu-id="6ac7f-144">Creare una variabile denominata `FirstName` e impostare il relativo tipo su `String`.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-144">Create a variable named, `FirstName`, and set its type to `String`.</span></span>  
  
         <span data-ttu-id="6ac7f-145">La variabile `FirstName` contiene il nome del venditore.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-145">The `FirstName` variable holds the salesperson's first name.</span></span>  
  
    4.  <span data-ttu-id="6ac7f-146">Creare una variabile denominata `Bonus` e impostare il relativo tipo su `Double`.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-146">Create a variable named, `Bonus`, and set its type to `Double`.</span></span>  
  
         <span data-ttu-id="6ac7f-147">La variabile `Bonus` contiene l'importo del premio del venditore.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-147">The `Bonus` variable holds the amount of the salesperson's bonus.</span></span>  
  
#### <a name="to-configure-the-connection-managers"></a><span data-ttu-id="6ac7f-148">Per configurare le gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="6ac7f-148">To configure the connection managers</span></span>  
  
1.  <span data-ttu-id="6ac7f-149">Nell'area Gestioni connessioni di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] aggiungere e configurare una nuova gestione connessione OLE DB che si connette al database di esempio [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6ac7f-149">In the Connection Managers area of the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add and configure a new OLE DB connection manager that connects to the [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)] sample database.</span></span>  
  
     <span data-ttu-id="6ac7f-150">L'origine OLE DB nell'attività Flusso di dati utilizzerà questa gestione connessione per recuperare dati.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-150">The OLE DB source in the Data Flow task will use this connection manager to retrieve data.</span></span>  
  
2.  <span data-ttu-id="6ac7f-151">Nell'area Gestioni connessioni aggiungere e configurare una nuova gestione connessione SMTP che si connette a un server SMTP disponibile.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-151">In the Connection Managers area, add and configure a new SMTP connection manager that connects to an available SMTP server.</span></span>  
  
     <span data-ttu-id="6ac7f-152">L'attività Invia messaggi nel contenitore Ciclo Foreach utilizzerà questa gestione connessione per inviare posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-152">The Send Mail task inside the Foreach Loop container will use this connection manager to send emails.</span></span>  
  
#### <a name="to-configure-the-data-flow-and-the-recordset-destination"></a><span data-ttu-id="6ac7f-153">Per configurare il flusso di dati e la destinazione recordset</span><span class="sxs-lookup"><span data-stu-id="6ac7f-153">To configure the data flow and the Recordset Destination</span></span>  
  
1.  <span data-ttu-id="6ac7f-154">Nella scheda **Flusso di controllo** di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] aggiungere un'attività Flusso di dati nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-154">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Data Flow task to the design surface.</span></span>  
  
2.  <span data-ttu-id="6ac7f-155">Nella scheda **Flusso di dati** aggiungere un'origine OLE DB all'attività Flusso di dati e quindi aprire **Editor origine OLE DB.**</span><span class="sxs-lookup"><span data-stu-id="6ac7f-155">On the **Data Flow** tab, add an OLE DB source to the Data Flow task, and then open the **OLE DB Source Editor.**</span></span>  
  
3.  <span data-ttu-id="6ac7f-156">Nella pagina **Gestione connessione** dell'editor configurare l'origine con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-156">On the **Connection Manager** page of the editor, configure the source with the following settings:</span></span>  
  
    1.  <span data-ttu-id="6ac7f-157">Per **Gestione connessione OLE DB**selezionare la gestione connessione OLE DB creata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-157">For **OLE DB connection manager**, select the OLE DB connection manager that you previously created.</span></span>  
  
    2.  <span data-ttu-id="6ac7f-158">Per **Modalità di accesso ai dati**selezionare **Comando SQL**.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-158">For **Data access mode**, select **SQL command**.</span></span>  
  
    3.  <span data-ttu-id="6ac7f-159">Per **Testo comando SQL**immettere la query seguente:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-159">For **SQL command text**, enter the following query:</span></span>  
  
        ```  
        SELECT     Person.Contact.EmailAddress, Person.Contact.FirstName, CONVERT(float, Sales.SalesPerson.Bonus) AS Bonus  
        FROM         Sales.SalesPerson INNER JOIN  
                              Person.Contact ON Sales.SalesPerson.SalesPersonID = Person.Contact.ContactID  
        ```  
  
        > [!NOTE]  
        >  <span data-ttu-id="6ac7f-160">È necessario convertire il valore `currency` nella colonna Bonus in `float` prima che sia possibile caricare tale valore in una variabile del pacchetto il cui tipo è `Double`.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-160">You have to convert the `currency` value in the Bonus column to a `float` before you can load that value into a package variable whose type is `Double`.</span></span>  
  
4.  <span data-ttu-id="6ac7f-161">Nella scheda **Flusso di dati** aggiungere una destinazione recordset e connetterla dopo l'origine OLE DB.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-161">On the **Data Flow** tab, add a Recordset destination, and connect the destination after the OLE DB source.</span></span>  
  
5.  <span data-ttu-id="6ac7f-162">Aprire l' **editor destinazione recordset**e configurare la destinazione con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-162">Open the **Recordset Destination Editor**, and configure the destination with the following settings:</span></span>  
  
    1.  <span data-ttu-id="6ac7f-163">Nella scheda **Proprietà componente** , per `VariableName` Proprietà selezionare `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="6ac7f-163">On the **Component Properties** tab, for `VariableName` property, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="6ac7f-164">Nella scheda **Colonne di input** selezionare tutte e tre le colonne disponibili.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-164">On the **Input Columns** tab, select all three of the available columns.</span></span>  
  
#### <a name="to-configure-the-foreach-loop-container-and-run-the-package"></a><span data-ttu-id="6ac7f-165">Per configurare il contenitore Ciclo Foreach ed eseguire il pacchetto</span><span class="sxs-lookup"><span data-stu-id="6ac7f-165">To configure the Foreach Loop container and run the package</span></span>  
  
1.  <span data-ttu-id="6ac7f-166">Nella scheda **Flusso di controllo** di Progettazione [!INCLUDE[ssIS](../../includes/ssis-md.md)] aggiungere un contenitore Ciclo Foreach e connetterlo dopo l'attività Flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-166">On the **Control Flow** tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, add a Foreach Loop container, and connect the container after the Data Flow task.</span></span>  
  
2.  <span data-ttu-id="6ac7f-167">Aprire **Editor ciclo Foreach**e configurare il contenitore con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-167">Open the **Foreach Loop Editor**, and configure the container with the following settings:</span></span>  
  
    1.  <span data-ttu-id="6ac7f-168">Nella pagina **raccolta** , per **enumeratore**, selezionare **enumeratore Foreach ADO**e, per **variabile di origine oggetto ADO**, selezionare `User::BonusRecordset` .</span><span class="sxs-lookup"><span data-stu-id="6ac7f-168">On the **Collection** page, for **Enumerator**, select **Foreach ADO Enumerator**, and for **ADO object source variable**, select `User::BonusRecordset`.</span></span>  
  
    2.  <span data-ttu-id="6ac7f-169">Nella pagina **Mapping variabili** eseguire il mapping `User::EmailAddress` all'indice 0, `User::FirstName` all'indice 1 e `User::Bonus` all'indice 2.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-169">On the **Variable Mappings** page, map `User::EmailAddress` to index 0, `User::FirstName` to index 1, and `User::Bonus` to index 2.</span></span>  
  
3.  <span data-ttu-id="6ac7f-170">Nella scheda **Flusso di controllo** aggiungere un'attività Invia messaggi nel contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-170">On the **Control Flow** tab, inside the Foreach Loop container, add a Send Mail task.</span></span>  
  
4.  <span data-ttu-id="6ac7f-171">Aprire **Editor attività Invia messaggi**e quindi nella pagina **Messaggio** configurare l'attività con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-171">Open the **Send Mail Task Editor**, and then on the **Mail** page, configure the task with the following settings:</span></span>  
  
    1.  <span data-ttu-id="6ac7f-172">Per **SmtpConnection**selezionare la gestione connessione SMTP configurata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-172">For **SmtpConnection**, select the SMTP connection manager that was configured previously.</span></span>  
  
    2.  <span data-ttu-id="6ac7f-173">Per **Da**immettere un indirizzo di posta elettronica appropriato.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-173">For **From**, enter an appropriate e-mail address.</span></span>  
  
         <span data-ttu-id="6ac7f-174">Se si utilizza il proprio indirizzo di posta elettronica, sarà possibile verificare la corretta esecuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-174">If you use your own e-mail address, you will be able to confirm that the package runs successfully.</span></span> <span data-ttu-id="6ac7f-175">Si riceveranno notifiche di messaggi non recapitati per i messaggi inviati dall'attività Invia messaggi ai venditori fittizi di [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ac7f-175">You will receive undeliverable receipts for the messages sent by the Send Mail task to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
    3.  <span data-ttu-id="6ac7f-176">Per **A**immettere un indirizzo di posta elettronica predefinito.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-176">For **To**, enter a default e-mail address.</span></span>  
  
         <span data-ttu-id="6ac7f-177">Questo valore non verrà utilizzato ma in fase di esecuzione verrà sostituito con l'indirizzo di posta elettronica di ogni venditore.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-177">This value will not be used, but will be replaced at run time by the e-mail address of each salesperson.</span></span>  
  
    4.  <span data-ttu-id="6ac7f-178">Per **Oggetto**immettere "Your annual bonus".</span><span class="sxs-lookup"><span data-stu-id="6ac7f-178">For **Subject**, enter "Your annual bonus".</span></span>  
  
    5.  <span data-ttu-id="6ac7f-179">Per **MessageSourceType**selezionare **Input diretto**.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-179">For **MessageSourceType**, select **Direct Input**.</span></span>  
  
5.  <span data-ttu-id="6ac7f-180">Nella pagina **Espressioni** di **Editor attività Invia messaggi**fare clic sul pulsante con i puntini di sospensione ( **...** ) per aprire **Editor espressioni di proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-180">On the **Expressions** page of the **Send Mail Task Editor**, click the ellipsis button (**...**) to open the **Property Expressions Editor**.</span></span>  
  
6.  <span data-ttu-id="6ac7f-181">In **Editor espressioni di proprietà**immettere le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-181">In the **Property Expressions Editor**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="6ac7f-182">Per **ToLine**aggiungere l'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-182">For **ToLine**, add the following expression:</span></span>  
  
        ```  
        @[User::EmailAddress]  
        ```  
  
    2.  <span data-ttu-id="6ac7f-183">Per la proprietà **MessageSource** aggiungere l'espressione seguente:</span><span class="sxs-lookup"><span data-stu-id="6ac7f-183">For the **MessageSource** property, add the following expression:</span></span>  
  
        ```  
        "Dear " +  @[User::FirstName] + ": The amount of your bonus for this year is $" +  (DT_WSTR, 12) @[User::Bonus] + ". Thank you!"  
        ```  
  
7.  <span data-ttu-id="6ac7f-184">Eseguire il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="6ac7f-184">Run the package.</span></span>  
  
     <span data-ttu-id="6ac7f-185">Se è stato specificato un server SMTP valido ed è stato fornito il proprio indirizzo di posta elettronica, si riceveranno notifiche di messaggi non recapitati per i messaggi inviati dall'attività Invia messaggi ai venditori fittizi di [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ac7f-185">If you have specified a valid SMTP server and provided your own e-mail address, you will receive undeliverable receipts for the messages that the Send Mail task sends to the fictitious salespersons of [!INCLUDE[ssSampleDBnormal](../../includes/sssampledbnormal-md.md)].</span></span>  
  
  
