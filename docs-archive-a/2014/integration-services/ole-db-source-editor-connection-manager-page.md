---
title: Editor origine OLE DB (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.connection.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 53699902-8699-4547-b56b-a5b2079e98b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6b9d841ff902107847a9d85779af41f476315db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636803"
---
# <a name="ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="64f2d-102">Editor origine OLE DB (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="64f2d-102">OLE DB Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="64f2d-103">Usare la pagina **Gestione connessione** della finestra di dialogo **Editor origine OLE DB** per selezionare la gestione connessione OLE DB per l'origine.</span><span class="sxs-lookup"><span data-stu-id="64f2d-103">Use the **Connection Manager** page of the **OLE DB Source Editor** dialog box to select the OLE DB connection manager for the source.</span></span> <span data-ttu-id="64f2d-104">Tramite questa pagina è inoltre possibile selezionare una tabella o una vista del database.</span><span class="sxs-lookup"><span data-stu-id="64f2d-104">This page also lets you select a table or view from the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64f2d-105">Per caricare dati da un'origine dati basata su [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, usare un'origine OLE DB.</span><span class="sxs-lookup"><span data-stu-id="64f2d-105">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, use an OLE DB source.</span></span> <span data-ttu-id="64f2d-106">Non è possibile utilizzare un'origine Excel per caricare dati da un'origine dei dati Excel 2007.</span><span class="sxs-lookup"><span data-stu-id="64f2d-106">You cannot use an Excel source to load data from an Excel 2007 data source.</span></span> <span data-ttu-id="64f2d-107">Per altre informazioni, vedere [Configura gestione connessione OLE DB](configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="64f2d-107">For more information, see [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span></span>  
>   
>  <span data-ttu-id="64f2d-108">Per caricare dati da un'origine dei dati che utilizza [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 o versione precedente, utilizzare un'origine Excel.</span><span class="sxs-lookup"><span data-stu-id="64f2d-108">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 or earlier, use an Excel source.</span></span> <span data-ttu-id="64f2d-109">Per altre informazioni, vedere [Editor origine Excel &#40;pagina Gestione connessione&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="64f2d-109">For more information, see [Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64f2d-110">La `CommandTimeout` proprietà dell'origine OLE DB non è disponibile nell' **Editor origine OLE DB**, ma può essere impostata tramite il **Editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="64f2d-110">The `CommandTimeout` property of the OLE DB source is not available in the **OLE DB Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="64f2d-111">Per ulteriori informazioni su questa proprietà, vedere la sezione relativa all'origine Excel in [Proprietà personalizzate OLE DB](data-flow/ole-db-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="64f2d-111">For more information on this property, see the Excel Source section of [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span></span>  
  
 <span data-ttu-id="64f2d-112">Per ulteriori informazioni sull'origine OLE DB, vedere [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="64f2d-112">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="open-the-ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="64f2d-113">Aprire OLE DB Source Editor (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="64f2d-113">Open the OLE DB Source Editor (Connection Manager Page</span></span>  
  
1.  <span data-ttu-id="64f2d-114">Aggiungere l'origine OLE DB al pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64f2d-114">Add the OLE DB source to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="64f2d-115">Fare clic con il pulsante destro del mouse sul componente di origine, quindi scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="64f2d-115">Right-click the source component and when click **Edit**.</span></span>  
  
3.  <span data-ttu-id="64f2d-116">Fare clic su **Gestione connessione**.</span><span class="sxs-lookup"><span data-stu-id="64f2d-116">Click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="64f2d-117">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="64f2d-117">Static Options</span></span>  
 <span data-ttu-id="64f2d-118">**Gestione connessione OLE DB**</span><span class="sxs-lookup"><span data-stu-id="64f2d-118">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="64f2d-119">Selezionare una gestione connessione esistente nell'elenco o crearne una nuova facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="64f2d-119">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="64f2d-120">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="64f2d-120">**New**</span></span>  
 <span data-ttu-id="64f2d-121">Consente di creare una nuova gestione connessione usando la finestra di dialogo **Configura gestione connessione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="64f2d-121">Create a new connection manager by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="64f2d-122">**Modalità di accesso ai dati**</span><span class="sxs-lookup"><span data-stu-id="64f2d-122">**Data access mode**</span></span>  
 <span data-ttu-id="64f2d-123">Consente di specificare il metodo per la selezione dei dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="64f2d-123">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="64f2d-124">Opzione</span><span class="sxs-lookup"><span data-stu-id="64f2d-124">Option</span></span>|<span data-ttu-id="64f2d-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64f2d-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="64f2d-126">Tabella o vista</span><span class="sxs-lookup"><span data-stu-id="64f2d-126">Table or view</span></span>|<span data-ttu-id="64f2d-127">Consente di recuperare dati da una tabella o da una vista nell'origine dei dati OLE DB.</span><span class="sxs-lookup"><span data-stu-id="64f2d-127">Retrieve data from a table or view in the OLE DB data source.</span></span>|  
|<span data-ttu-id="64f2d-128">Variabile nome vista o nome tabella</span><span class="sxs-lookup"><span data-stu-id="64f2d-128">Table name or view name variable</span></span>|<span data-ttu-id="64f2d-129">Consente di specificare il nome della vista o della tabella in una variabile.</span><span class="sxs-lookup"><span data-stu-id="64f2d-129">Specify the table or view name in a variable.</span></span><br /><br /> <span data-ttu-id="64f2d-130">**Informazioni correlate:** [Uso di variabili nei pacchetti](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="64f2d-130">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="64f2d-131">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="64f2d-131">SQL command</span></span>|<span data-ttu-id="64f2d-132">Consente di recuperare dati dall'origine dei dati OLE DB utilizzando una query SQL.</span><span class="sxs-lookup"><span data-stu-id="64f2d-132">Retrieve data from the OLE DB data source by using a SQL query.</span></span>|  
|<span data-ttu-id="64f2d-133">Comando SQL da variabile</span><span class="sxs-lookup"><span data-stu-id="64f2d-133">SQL command from variable</span></span>|<span data-ttu-id="64f2d-134">Consente di specificare il testo della query SQL in una variabile.</span><span class="sxs-lookup"><span data-stu-id="64f2d-134">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="64f2d-135">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="64f2d-135">**Preview**</span></span>  
 <span data-ttu-id="64f2d-136">Consente di visualizzare in anteprima i risultati nella finestra di dialogo **Vista dati** .</span><span class="sxs-lookup"><span data-stu-id="64f2d-136">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="64f2d-137">L'**anteprima** supporta la visualizzazione di un massimo di 200 righe.</span><span class="sxs-lookup"><span data-stu-id="64f2d-137">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="64f2d-138">Quando vengono visualizzati i dati in anteprima, le colonne con tipo definito dall'utente CLR (UDT) non contengono dati.</span><span class="sxs-lookup"><span data-stu-id="64f2d-138">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="64f2d-139">Contengono invece i valori \<value too big to display> o System.Byte[] display.</span><span class="sxs-lookup"><span data-stu-id="64f2d-139">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="64f2d-140">Il primo viene visualizzato se si accede all'origine dati mediante il provider SQL OLE DB, il secondo se si usa il provider [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="64f2d-140">The former displays when the data source is accessed using the SQL OLE DB provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="64f2d-141">Opzioni dinamiche relative alla modalità di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="64f2d-141">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="64f2d-142">Modalità di accesso ai dati = Tabella o vista</span><span class="sxs-lookup"><span data-stu-id="64f2d-142">Data access mode = Table or view</span></span>  
 <span data-ttu-id="64f2d-143">**Nome tabella o vista**</span><span class="sxs-lookup"><span data-stu-id="64f2d-143">**Name of the table or the view**</span></span>  
 <span data-ttu-id="64f2d-144">Consente di selezionare il nome della tabella o della vista nell'elenco dei nomi disponibili nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="64f2d-144">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="64f2d-145">Modalità di accesso ai dati = Variabile nome vista o nome tabella</span><span class="sxs-lookup"><span data-stu-id="64f2d-145">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="64f2d-146">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="64f2d-146">**Variable name**</span></span>  
 <span data-ttu-id="64f2d-147">Consente di selezionare la variabile che contiene il nome della tabella o vista.</span><span class="sxs-lookup"><span data-stu-id="64f2d-147">Select the variable that contains the name of the table or view.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="64f2d-148">Modalità di accesso ai dati = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="64f2d-148">Data access mode = SQL command</span></span>  
 <span data-ttu-id="64f2d-149">**Testo comando SQL**</span><span class="sxs-lookup"><span data-stu-id="64f2d-149">**SQL command text**</span></span>  
 <span data-ttu-id="64f2d-150">Immettere il testo di una query SQL, fare clic su **Compila query**per compilare la query o fare clic su **Sfoglia**per individuare il file che contiene il testo della query.</span><span class="sxs-lookup"><span data-stu-id="64f2d-150">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="64f2d-151">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="64f2d-151">**Parameters**</span></span>  
 <span data-ttu-id="64f2d-152">Se è stata immessa una query con parametri utilizzando ?</span><span class="sxs-lookup"><span data-stu-id="64f2d-152">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="64f2d-153">come segnaposto per il parametro nel testo della query, usare la finestra di dialogo **Imposta parametri query** per eseguire il mapping tra i parametri di input della query e le variabili del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="64f2d-153">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="64f2d-154">**Compila query**</span><span class="sxs-lookup"><span data-stu-id="64f2d-154">**Build query**</span></span>  
 <span data-ttu-id="64f2d-155">Usare la finestra di dialogo **Generatore query** per creare la query SQL con strumenti grafici visuali.</span><span class="sxs-lookup"><span data-stu-id="64f2d-155">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="64f2d-156">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="64f2d-156">**Browse**</span></span>  
 <span data-ttu-id="64f2d-157">Usare la finestra di dialogo **Apri** per individuare il file contenente il testo della query SQL.</span><span class="sxs-lookup"><span data-stu-id="64f2d-157">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="64f2d-158">**Analizza query**</span><span class="sxs-lookup"><span data-stu-id="64f2d-158">**Parse query**</span></span>  
 <span data-ttu-id="64f2d-159">Consente di verificare la sintassi del testo della query.</span><span class="sxs-lookup"><span data-stu-id="64f2d-159">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="64f2d-160">Modalità di accesso ai dati = Comando SQL da variabile</span><span class="sxs-lookup"><span data-stu-id="64f2d-160">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="64f2d-161">**Nome variabile**</span><span class="sxs-lookup"><span data-stu-id="64f2d-161">**Variable name**</span></span>  
 <span data-ttu-id="64f2d-162">Consente di selezionare la variabile contenente il testo della query SQL.</span><span class="sxs-lookup"><span data-stu-id="64f2d-162">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64f2d-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64f2d-163">See Also</span></span>  
 <span data-ttu-id="64f2d-164">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="64f2d-164">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="64f2d-165">[Editor origine OLE DB &#40;pagina colonne&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="64f2d-165">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="64f2d-166">[Editor origine OLE DB &#40;pagina output degli errori&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="64f2d-166">[OLE DB Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="64f2d-167">[Estrarre dati tramite l'origine OLE DB](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="64f2d-167">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="64f2d-168">Gestione connessione OLE DB</span><span class="sxs-lookup"><span data-stu-id="64f2d-168">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
