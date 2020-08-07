---
title: Editor origine ODBC (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.connection.f1
ms.assetid: e2c8dc83-6394-4d6c-9232-97e94be72431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c8b54ce4a1c1b3fea0afb51f1cbf7447971ccab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718564"
---
# <a name="odbc-source-editor-connection-manager-page"></a><span data-ttu-id="2b3a4-102">Editor origine ODBC (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="2b3a4-102">ODBC Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="2b3a4-103">Utilizzare la pagina **Gestione connessione** della finestra di dialogo **ODBC Source Editor** per selezionare la gestione connessione ODBC per l'origine.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-103">Use the **Connection Manager** page of the **ODBC Source Editor** dialog box to select the ODBC connection manager for the source.</span></span> <span data-ttu-id="2b3a4-104">Tramite questa pagina è inoltre possibile selezionare una tabella o una vista del database.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="2b3a4-105">Per ulteriori informazioni sull'origine ODBC, vedere [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="2b3a4-105">For more information about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="2b3a4-106">Elenco attività</span><span class="sxs-lookup"><span data-stu-id="2b3a4-106">Task List</span></span>  
 <span data-ttu-id="2b3a4-107">**Per aprire ODBC Source Editor (pagina Gestione connessione)**</span><span class="sxs-lookup"><span data-stu-id="2b3a4-107">**To open the ODBC Source Editor Connection Manager Page**</span></span>  
  
-   <span data-ttu-id="2b3a4-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], aprire il pacchetto [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] che contiene l'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="2b3a4-109">Nella scheda **Flusso di dati** fare doppio clic sull'origine ODBC.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-109">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2b3a4-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="2b3a4-110">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="2b3a4-111">Gestione connessione</span><span class="sxs-lookup"><span data-stu-id="2b3a4-111">Connection manager</span></span>  
 <span data-ttu-id="2b3a4-112">Selezionare una gestione connessione ODBC esistente nell'elenco oppure fare clic su **nuova** per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-112">Select an existing ODBC connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="2b3a4-113">La connessione può essere a qualsiasi database supportato da ODBC.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-113">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="2b3a4-114">Nuovo</span><span class="sxs-lookup"><span data-stu-id="2b3a4-114">New</span></span>  
 <span data-ttu-id="2b3a4-115">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-115">Click **New**.</span></span> <span data-ttu-id="2b3a4-116">Viene visualizzata la finestra di dialogo **Configura gestione connessione ODBC** in cui è possibile creare una nuova gestione connessione ODBC.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-116">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new ODBC connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="2b3a4-117">Modalità di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="2b3a4-117">Data Access Mode</span></span>  
 <span data-ttu-id="2b3a4-118">Consente di selezionare il metodo per la selezione dei dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-118">Select the method for selecting data from the source.</span></span> <span data-ttu-id="2b3a4-119">Le opzioni disponibili vengono visualizzate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-119">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="2b3a4-120">Opzione</span><span class="sxs-lookup"><span data-stu-id="2b3a4-120">Option</span></span>|<span data-ttu-id="2b3a4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2b3a4-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2b3a4-122">Nome tabella</span><span class="sxs-lookup"><span data-stu-id="2b3a4-122">Table Name</span></span>|<span data-ttu-id="2b3a4-123">Consente di recuperare dati da una tabella o da una vista nell'origine dati ODBC.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-123">Retrieve data from a table or view in the ODBC data source.</span></span> <span data-ttu-id="2b3a4-124">Se si seleziona questa opzione, scegliere un valore nell'elenco per le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b3a4-124">When you select this option, select a value from the list for the following:</span></span>|  
||<span data-ttu-id="2b3a4-125">**Nome tabella o vista**: selezionare una tabella o vista disponibile nell'elenco o digitare un'espressione regolare per identificare la tabella.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-125">**Name of the table or the view**: Select an available table or view from the list or type a regular expression to identify the table.</span></span>|  
||<span data-ttu-id="2b3a4-126">Questo elenco contiene solo le prime 1000 tabelle.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-126">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="2b3a4-127">Se il database contiene più di 1000 tabelle, è possibile digitare l'inizio di un nome di tabella o utilizzare il carattere jolly (\*) per immettere qualsiasi parte del nome e visualizzare la tabella o le tabelle che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-127">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
|<span data-ttu-id="2b3a4-128">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="2b3a4-128">SQL command</span></span>|<span data-ttu-id="2b3a4-129">Consente di recuperare dati dall'origine dati ODBC utilizzando una query SQL.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-129">Retrieve data from the ODBC data source by using an SQL query.</span></span> <span data-ttu-id="2b3a4-130">Scrivere la query nella sintassi del database di origine che si sta utilizzando.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-130">You should write the query in the syntax of the source database you are working with.</span></span> <span data-ttu-id="2b3a4-131">Se si seleziona questa opzione, immettere una query in uno dei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b3a4-131">When you select this option, enter a query in one of the following ways:</span></span>|  
||<span data-ttu-id="2b3a4-132">Immettere il testo della query SQL nel campo **Testo comando SQL** .</span><span class="sxs-lookup"><span data-stu-id="2b3a4-132">Enter the text of the SQL query in the **SQL command text** field.</span></span>|  
||<span data-ttu-id="2b3a4-133">Fare clic su **Sfoglia** per caricare la query SQL da un file di testo.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-133">Click **Browse** to load the SQL query from a text file.</span></span>|  
||<span data-ttu-id="2b3a4-134">Fare clic su **Analizza query** per verificare la sintassi del testo della query.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-134">Click **Parse query** to verify the syntax of the query text.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="2b3a4-135">Anteprima</span><span class="sxs-lookup"><span data-stu-id="2b3a4-135">Preview</span></span>  
 <span data-ttu-id="2b3a4-136">Fare clic su **Anteprima** per visualizzare un massimo di 200 righe dei dati estratti dalla tabella o dalla vista selezionata.</span><span class="sxs-lookup"><span data-stu-id="2b3a4-136">Click **Preview** to view up to the first 200 rows of the data extracted from the table or view you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b3a4-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b3a4-137">See Also</span></span>  
 <span data-ttu-id="2b3a4-138">[Proprietà personalizzate dell'origine ODBC](data-flow/odbc-source-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2b3a4-138">[ODBC Source Custom Properties](data-flow/odbc-source-custom-properties.md) </span></span>  
 <span data-ttu-id="2b3a4-139">[Editor origine ODBC &#40;pagina colonne&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="2b3a4-139">[ODBC Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="2b3a4-140">Editor origine ODBC &#40;pagina Output degli errori&#41;</span><span class="sxs-lookup"><span data-stu-id="2b3a4-140">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
