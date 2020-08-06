---
title: Connettersi ai dati di origine (client di data mining per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- connections
ms.assetid: 548672ce-e403-4aca-b67a-c2c797f053dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4b4759d94043fdccacdf5b285de50697a18965e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625703"
---
# <a name="connect-to-source-data-data-mining-client-for-excel"></a><span data-ttu-id="7cb1b-102">Connessione ai dati di origine (client di data mining per Excel)</span><span class="sxs-lookup"><span data-stu-id="7cb1b-102">Connect to Source Data (Data Mining Client for Excel)</span></span>
  <span data-ttu-id="7cb1b-103">In questo argomento viene descritto come creare e utilizzare le connessioni utilizzate per archiviare i modelli di data mining e per accedere a dati esterni archiviati in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cb1b-103">This topic describes how to create and use connections used for storing data mining models, and for accessing external data stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7cb1b-104">**Connessioni di data mining.**</span><span class="sxs-lookup"><span data-stu-id="7cb1b-104">**Data mining connections.**</span></span> <span data-ttu-id="7cb1b-105">La connessione iniziale creata all'avvio dei componenti aggiuntivi viene utilizzata per accedere agli algoritmi, analizzare i dati e archiviare la struttura e i modelli di data mining.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-105">The initial connection that you create when you start the add-ins is used to access algorithms, analyze data, and store mining structure and models.</span></span>  
  
 <span data-ttu-id="7cb1b-106">La connessione a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] è necessaria per utilizzare gli strumenti di modellazione e di visualizzazione dei componenti aggiuntivi perché questi ultimi dipendono da strutture dei dati e algoritmi forniti da [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cb1b-106">A connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is required to use the modeling and visualization tools in the add-ins, because the add-ins depend on algorithms and data structures that are provided by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="7cb1b-107">**Connessioni a origini dati esterne.**</span><span class="sxs-lookup"><span data-stu-id="7cb1b-107">**Connections to external data sources.**</span></span> <span data-ttu-id="7cb1b-108">È inoltre possibile creare connessioni a dati esterni durante la compilazione di modelli o il salvataggio dei risultati.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-108">You can also create connections to external data as you are building models or saving the results.</span></span> <span data-ttu-id="7cb1b-109">È ad esempio possibile creare un modello di data mining in un server, quindi eseguire una query di stima sul modello utilizzando i dati archiviati in un'altra istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], in una tabella dati di Excel o in un'origine dati esterna, ad esempio [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-109">For example, you can create a data mining model on one server, and then perform a prediction query against the data mining model by using data stored in another instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], in an Excel data table, or in an external data source such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span></span> <span data-ttu-id="7cb1b-110">Ogni volta che si accede a una nuova origine dati, viene chiesto di creare una connessione tramite una finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-110">Each time that you access a new data source, you will be prompted to create a connection by using a dialog box.</span></span>  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq2"></a> <span data-ttu-id="7cb1b-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7cb1b-111">Prerequisites</span></span>  
 <span data-ttu-id="7cb1b-112">Per questa versione dei componenti aggiuntivi è necessario che l'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] sia SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-112">This version of the add-ins requires that your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] be SQL Server 2012.</span></span> <span data-ttu-id="7cb1b-113">Se si desidera connettersi a una versione precedente di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], è disponibile una versione separata dei componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-113">A separate version of the add-ins is available if you want to connect to an earlier version of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="7cb1b-114">Esistono versioni dei componenti aggiuntivi che supportano SQL Server 2005, SQL Server 2008 e SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-114">There are versions of the add-ins that support SQL Server 2005, SQL Server 2008, and SQL Server 2008 R2.</span></span>  
  
 <span data-ttu-id="7cb1b-115">Per connettersi a un database di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], è necessario disporre delle autorizzazioni per accedere al server di database.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-115">To connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, you must have permissions to access the database server.</span></span> <span data-ttu-id="7cb1b-116">È necessario inoltre che le sessioni di data mining siano abilitate e che l'utente disponga delle autorizzazioni di lettura o lettura/scrittura per gli oggetti di database archiviati nel server.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-116">Moreover, data mining sessions must be enabled, and you must have read or read/write permissions on database objects stored on the server.</span></span>  
  
##  <a name="creating-data-mining-server-connections"></a><a name="bkmk_connect"></a><span data-ttu-id="7cb1b-117">Creazione di connessioni al server di data mining</span><span class="sxs-lookup"><span data-stu-id="7cb1b-117">Creating Data Mining Server Connections</span></span>  
 <span data-ttu-id="7cb1b-118">Il gruppo **connessioni** del client di data mining per Excel e gli strumenti di analisi tabelle per Excel forniscono gli strumenti per la gestione delle connessioni a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7cb1b-118">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel provides tools for managing connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7cb1b-119">È possibile creare la connessione durante l'installazione del componente aggiuntivo o aggiungere una connessione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-119">You can create the connection when you install the add-in, or you can add a connection later.</span></span>  
  
-   <span data-ttu-id="7cb1b-120">È possibile creare più connessioni e modificare le connessioni in qualsiasi momento, a meno che non sia in corso la creazione o l'esecuzione di query su un modello.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-120">You can create multiple connections, and change connections at any time, unless you are in the process of creating or querying a model.</span></span>  
  
     <span data-ttu-id="7cb1b-121">Non cambiare o chiudere una connessione durante l'elaborazione di un modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-121">Do not change or close a connection when a data mining model is being processed.</span></span> <span data-ttu-id="7cb1b-122">Potrebbero infatti verificarsi perdite di dati del modello di data mining oppure il modello potrebbe diventare inutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-122">The data mining model might lose data, or the model might become unusable.</span></span>  
  
-   <span data-ttu-id="7cb1b-123">Solo una connessione può essere attiva in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-123">Only one connection can be active at a particular time.</span></span>  
  
### <a name="connections-in-the-excel-add-ins"></a><span data-ttu-id="7cb1b-124">Connessioni nei componenti aggiuntivi per Excel</span><span class="sxs-lookup"><span data-stu-id="7cb1b-124">Connections in the Excel Add-ins</span></span>  
 <span data-ttu-id="7cb1b-125">Il gruppo **Connections** nel client di data mining per Excel e gli strumenti di analisi tabelle per Excel consentono di gestire le connessioni a un'istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7cb1b-125">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel is where you manage connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
##### <a name="create-a-new-server-connection-in-the-excel-add-ins"></a><span data-ttu-id="7cb1b-126">Creazione di una nuova connessione al server nei componenti aggiuntivi per Excel</span><span class="sxs-lookup"><span data-stu-id="7cb1b-126">Create a new server connection in the Excel add-ins</span></span>  
  
1.  <span data-ttu-id="7cb1b-127">Fare clic sul pulsante **connessione** sulla barra multifunzione **analizza** o **data mining** .</span><span class="sxs-lookup"><span data-stu-id="7cb1b-127">Click the **Connection** button on the **Analyze** or **Data Mining** ribbon.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7cb1b-128">Il testo del pulsante indica se è presente una connessione.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-128">The text of the button indicates if a connection exists.</span></span> <span data-ttu-id="7cb1b-129">Quando non è stata effettuata alcuna connessione nel foglio di foglio, il pulsante contiene il testo " \<No connection> ." Se nella cartella di lavoro è stata precedentemente effettuata una connessione, il nome di tale connessione viene visualizzato nel pulsante.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-129">When no connection has been made in the worksheet, the button contains the text "\<No connection>." If a connection was previously made in the workbook, the name of that connection appears in the button.</span></span>  
  
2.  <span data-ttu-id="7cb1b-130">Nella finestra di dialogo **Analysis Services connessioni** fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-130">In the **Analysis Services Connections** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="7cb1b-131">Nella finestra di dialogo **nuova connessione Analysis Services** Digitare il nome del server.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-131">In the **New Analysis Services Connection** dialog box, type the name of the server.</span></span>  
  
4.  <span data-ttu-id="7cb1b-132">Specificare il metodo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-132">Specify the authentication method.</span></span>  
  
5.  <span data-ttu-id="7cb1b-133">Selezionare un database dall'elenco a discesa **nome catalogo** .</span><span class="sxs-lookup"><span data-stu-id="7cb1b-133">Select a database from the **Catalog name** drop-down list.</span></span> <span data-ttu-id="7cb1b-134">Se nell'istanza non è presente alcun database, selezionare **(impostazione predefinita)**.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-134">If no database exists on the instance, select **(default)**.</span></span>  
  
6.  <span data-ttu-id="7cb1b-135">Digitare un nome descrittivo per la connessione.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-135">Type a friendly name for the connection.</span></span>  
  
7.  <span data-ttu-id="7cb1b-136">Fare clic su **Test connessione** per verificare che il server e il database siano disponibili.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-136">Click **Test Connection** to verify that the server and database are available.</span></span>  
  
8.  <span data-ttu-id="7cb1b-137">Fare clic su **OK**, quindi su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-137">Click **OK**, and then click **Close**.</span></span>  
  
### <a name="connections-using-a-web-service"></a><span data-ttu-id="7cb1b-138">Connessioni tramite un servizio Web</span><span class="sxs-lookup"><span data-stu-id="7cb1b-138">Connections using a Web Service</span></span>  
 <span data-ttu-id="7cb1b-139">Se si utilizza un'architettura thin client per consentire l'esplorazione di cubi e dati di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], è inoltre possibile configurare una connessione a un server di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] tramite servizi Web.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-139">If you are using a thin-client architecture to enable browsing of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubes and data, you can also configure a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server through Web services.</span></span> <span data-ttu-id="7cb1b-140">Per informazioni sulla definizione di un client basato sul Web, vedere la documentazione online di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cb1b-140">For information about how to define a Web-based client, see [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="7cb1b-141">Se si dispone dell'accesso a un server configurato per i servizi Web, sarà possibile specificare il tipo di connessione al momento della creazione della connessione.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-141">If you have access to a server that has been configured for Web services, you can specify the connection type when you first create the connection.</span></span>  
  
##### <a name="create-an-http-connection-to-analysis-services"></a><span data-ttu-id="7cb1b-142">Creazione di una connessione HTTP ad Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7cb1b-142">Create an HTTP connection to Analysis Services</span></span>  
  
1.  <span data-ttu-id="7cb1b-143">Aprire la finestra di dialogo **nuova connessione Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="7cb1b-143">Open the **New Analysis Services Connection** dialog box.</span></span>  
  
2.  <span data-ttu-id="7cb1b-144">Come nome del server digitare http:// seguito dall'URL assegnato al server [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cb1b-144">For the server name, type http:// followed by the URL assigned to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span>  
  
3.  <span data-ttu-id="7cb1b-145">Digitare il nome utente e la password necessari per accedere al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-145">Type the user name and the password that is required to access the Web service.</span></span>  
  
### <a name="connections-in-the-visio-add-in"></a><span data-ttu-id="7cb1b-146">Connessioni nel componente aggiuntivo per Visio</span><span class="sxs-lookup"><span data-stu-id="7cb1b-146">Connections in the Visio Add-In</span></span>  
 <span data-ttu-id="7cb1b-147">A differenza di Excel, in Visio non è disponibile una barra multifunzione degli strumenti e non sono presenti pulsanti specifici per la creazione o il monitoraggio delle connessioni.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-147">Unlike Excel, Visio does not provide a tool ribbon, and there are no buttons specifically for creating or monitoring connections.</span></span> <span data-ttu-id="7cb1b-148">La connessione dati viene invece creata quando si seleziona una forma di data mining e la si rilascia in una pagina di Visio.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-148">Instead, the data connection is created when you first select a data mining shape and drop it onto a Visio page.</span></span> <span data-ttu-id="7cb1b-149">Nella procedura guidata verrà chiesto di selezionare il modello per la forma e di impostare altre opzioni.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-149">A wizard will prompt you to select the model for the shape and to set other options.</span></span>  
  
 <span data-ttu-id="7cb1b-150">Se in precedenza sono state utilizzate connessioni a un'origine dati di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] in Excel, tali connessioni vengono elencate come possibili origini dati da selezionare.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-150">If you have previously used a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source in Excel, these connections are listed as possible data sources from which to select.</span></span>  
  
##### <a name="create-a-connection-for-a-visio-shape"></a><span data-ttu-id="7cb1b-151">Creazione di una connessione per una forma di Visio</span><span class="sxs-lookup"><span data-stu-id="7cb1b-151">Create a connection for a Visio shape</span></span>  
  
1.  <span data-ttu-id="7cb1b-152">Aprire il modello di data mining e selezionare una delle forme di data mining.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-152">Open the Data Mining Template, and select one of the data mining shapes.</span></span>  
  
2.  <span data-ttu-id="7cb1b-153">Trascinare e rilasciare la forma in una pagina vuota.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-153">Drag and drop the shape to a blank page.</span></span>  
  
3.  <span data-ttu-id="7cb1b-154">Nella finestra di dialogo **selezionare un'origine dati** selezionare un'origine dati dall'elenco oppure fare clic su **nuova**.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-154">In the **Select a data source** dialog box, select a data source from the list, or click **New**.</span></span>  
  
4.  <span data-ttu-id="7cb1b-155">Se si seleziona **nuovo**, attenersi alla procedura descritta in precedenza per specificare un server e un nome di catalogo oppure per connettersi tramite un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-155">If you select **New**, follow the procedure that is described earlier to specify a server and catalog name, or to connect through a Web service.</span></span>  
  
##  <a name="changing-connections"></a><a name="bkmk_change"></a><span data-ttu-id="7cb1b-156">Modifica delle connessioni</span><span class="sxs-lookup"><span data-stu-id="7cb1b-156">Changing Connections</span></span>  
 <span data-ttu-id="7cb1b-157">È possibile creare più connessioni nello stesso foglio di lavoro, ma può essere attiva solo una connessione alla volta.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-157">You can create multiple connections in the same worksheet, but only one connection can be active at a time.</span></span> <span data-ttu-id="7cb1b-158">Il nome della connessione corrente viene visualizzato nel pulsante **connessione** .</span><span class="sxs-lookup"><span data-stu-id="7cb1b-158">The name of the current connection is displayed in the **Connection** button.</span></span>  
  
 <span data-ttu-id="7cb1b-159">Nel client di data mining per Excel è inoltre possibile verificare la stringa di connessione e lo stato della connessione corrente facendo clic su **traccia** e quindi su **connessione corrente**.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-159">In the Data Mining Client for Excel, you can also verify the connection string and status for the current connection by clicking **Trace** and then clicking **Current Connection**.</span></span>  
  
#### <a name="use-a-different-server-connection"></a><span data-ttu-id="7cb1b-160">Utilizzo di una connessione a un altro server</span><span class="sxs-lookup"><span data-stu-id="7cb1b-160">Use a different server connection</span></span>  
  
1.  <span data-ttu-id="7cb1b-161">Fare clic su **connessione**.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-161">Click **Connection**.</span></span>  
  
2.  <span data-ttu-id="7cb1b-162">Nel riquadro **connessioni Analysis Services** selezionare una connessione nell'elenco **altre connessioni** e fare clic su **Rendi corrente**.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-162">In the **Analysis Services Connections** pane, select a connection from the **Other Connections** list, and click **Make Current**.</span></span>  
  
3.  <span data-ttu-id="7cb1b-163">Fare clic su **Test connessione** per verificare che la connessione sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-163">Click **Test Connection** to verify that the connection is available.</span></span>  
  
 <span data-ttu-id="7cb1b-164">Al termine dell'elaborazione di un modello di data mining, i risultati vengono archiviati localmente e se si interrompe la connessione a un server per connettersi a un altro server non si hanno ripercussioni sui dati.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-164">After a mining model has finished processing, the results are stored locally, and there is no effect on the data if you close the connection to one server and then connect to another server.</span></span> <span data-ttu-id="7cb1b-165">È consigliabile tuttavia evitare di cambiare connessione o di interrompere la connessione durante l'elaborazione di un modello di data mining, in quanto si potrebbero danneggiare i dati.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-165">However, you should avoid changing connections or losing the connection when a data mining model is being processed, because this could corrupt data.</span></span>  
  
#### <a name="modify-an-existing-server-connection"></a><span data-ttu-id="7cb1b-166">Modifica di una connessione al server esistente</span><span class="sxs-lookup"><span data-stu-id="7cb1b-166">Modify an existing server connection</span></span>  
  
1.  <span data-ttu-id="7cb1b-167">Non è possibile modificare una connessione esistente; se si desidera connettersi a un database o a un server diverso, è necessario creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-167">You cannot modify an existing connection; if you want to connect to a different database or a different server, you should create a new connection.</span></span>  
  
2.  <span data-ttu-id="7cb1b-168">Se è necessario modificare la stringa di connessione per aumentare il timeout per le query o aggiungere altri parametri specifici dell'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], un'opzione consiste nel modificare il file DMC, in cui è archiviata la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-168">If you must modify the connection string to increase the query timeout or add other parameters specific to your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], one option is to edit the .dmc file, where the connection string is stored.</span></span>  
  
     <span data-ttu-id="7cb1b-169">\<drive:>\Users \\<utente \> \AppData\Local\Microsoft\Data componente aggiuntivo Data mining</span><span class="sxs-lookup"><span data-stu-id="7cb1b-169">\<drive:>\Users\\<myusername\>\AppData\Local\Microsoft\Data Mining Add-in</span></span>  
  
##  <a name="connecting-to-external-data-sources"></a><a name="bkmk_extconnections"></a><span data-ttu-id="7cb1b-170">Connessione a origini dati esterne</span><span class="sxs-lookup"><span data-stu-id="7cb1b-170">Connecting to External Data Sources</span></span>  
 <span data-ttu-id="7cb1b-171">Mentre gli strumenti della barra multifunzione **analizza** funzionano esclusivamente con i dati in Excel, gli strumenti della barra multifunzione **data mining** consentono di connettersi direttamente alle origini dati esterne da utilizzare come input per il modello o per il campionamento.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-171">Whereas the tools in the **Analyze** ribbon work exclusively with data in Excel, the tools in the **Data Mining** ribbon let you connect directly to external data sources to use as inputs for your model, or for sampling.</span></span>  
  
 <span data-ttu-id="7cb1b-172">Gli strumenti seguenti in questi componenti aggiuntivi supportano l'utilizzo di dati esterni per il data mining:</span><span class="sxs-lookup"><span data-stu-id="7cb1b-172">The following tools in these add-ins support use of external data for data mining:</span></span>  
  
-   [<span data-ttu-id="7cb1b-173">&#40;di dati di esempio SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-173">Sample Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](sample-data-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="7cb1b-174">Procedura guidata classificazione &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-174">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="7cb1b-175">Procedura guidata stima &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-175">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="7cb1b-176">Creazione guidata cluster &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-176">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="7cb1b-177">Procedura guidata previsione &#40;componenti aggiuntivi Data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-177">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="7cb1b-178">Creazione della struttura di data mining &#40;SQL Server i componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-178">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="7cb1b-179">Grafico di accuratezza &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-179">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="7cb1b-180">Grafico dei profitti &#40;SQL Server componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-180">Profit Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](profit-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="7cb1b-181">Matrice di classificazione &#40;SQL Server i componenti aggiuntivi Data mining&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-181">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
### <a name="using-analysis-services-as-a-data-source"></a><span data-ttu-id="7cb1b-182">Utilizzo di Analysis Services come origine dati</span><span class="sxs-lookup"><span data-stu-id="7cb1b-182">Using Analysis Services as a Data Source</span></span>  
 <span data-ttu-id="7cb1b-183">Non è possibile accedere direttamente ai dati archiviati in un modello tabulare o in un cubo di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cb1b-183">You cannot directly access data stored in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube or tabular model.</span></span> <span data-ttu-id="7cb1b-184">In alternativa, è possibile creare una connessione in Excel al server di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e utilizzare i dati per creare un modello.</span><span class="sxs-lookup"><span data-stu-id="7cb1b-184">Instead, create a connection in Excel to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, and use the data to create a model.</span></span>  
  
### <a name="relational-data-sources"></a><span data-ttu-id="7cb1b-185">Origini dati relazionali</span><span class="sxs-lookup"><span data-stu-id="7cb1b-185">Relational Data Sources</span></span>  
 <span data-ttu-id="7cb1b-186">Se si desidera utilizzare i dati da un'origine relazionale come input al modello, è possibile connettersi alle seguenti versioni di SQL Server:</span><span class="sxs-lookup"><span data-stu-id="7cb1b-186">If you want to use data from a relational source as input to your model, you can connect to the following versions of SQL Server:</span></span>  
  
-   <span data-ttu-id="7cb1b-187">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="7cb1b-187">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="7cb1b-188">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7cb1b-188">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="7cb1b-189">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="7cb1b-189">SQL Server 2012</span></span>  
  
 <span data-ttu-id="7cb1b-190">È inoltre possibile ottenere dati da qualsiasi altra origine dati relazionale supportata come origine dati da [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7cb1b-190">You can also get data from any other relational data source that is supported as a data source by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="7cb1b-191">Per informazioni sulle origini dati supportate, vedere [origini dati nei modelli multidimensionali](multidimensional-models/data-sources-in-multidimensional-models.md) .</span><span class="sxs-lookup"><span data-stu-id="7cb1b-191">For information about supported data sources, see [Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md)</span></span>  
  
 <span data-ttu-id="7cb1b-192">Si noti che i seguenti tipi di dati non possono essere utilizzati per il data mining e si verificherà un errore se vengono inclusi quando si compila un modello:</span><span class="sxs-lookup"><span data-stu-id="7cb1b-192">Note that the following data types cannot be used for data mining and will result in an error if included when you build a model:</span></span>  
  
-   <span data-ttu-id="7cb1b-193">ntext</span><span class="sxs-lookup"><span data-stu-id="7cb1b-193">ntext</span></span>  
  
-   <span data-ttu-id="7cb1b-194">BINARY</span><span class="sxs-lookup"><span data-stu-id="7cb1b-194">binary</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cb1b-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7cb1b-195">See Also</span></span>  
 [<span data-ttu-id="7cb1b-196">Traccia &#40;client di data mining per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="7cb1b-196">Trace &#40;Data Mining Client for Excel&#41;</span></span>](trace-data-mining-client-for-excel.md)  
  
  
