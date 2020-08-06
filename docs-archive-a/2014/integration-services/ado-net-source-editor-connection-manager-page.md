---
title: Editor origine ADO NET (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.connection.f1
ms.assetid: 7de3f438-bdd6-49b5-937a-47369e754943
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19dd9c256f15bc9022f7267cb38b6f91bd4d8a5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721684"
---
# <a name="ado-net-source-editor-connection-manager-page"></a><span data-ttu-id="7912b-102">Editor origine ADO NET (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="7912b-102">ADO NET Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="7912b-103">Usare la pagina **Gestione connessione** della finestra di dialogo **Editor origine ADO.NET** per selezionare la gestione connessione [!INCLUDE[vstecado](../includes/vstecado-md.md)] per l'origine.</span><span class="sxs-lookup"><span data-stu-id="7912b-103">Use the **Connection Manager** page of the **ADO NET Source Editor** dialog box to select the [!INCLUDE[vstecado](../includes/vstecado-md.md)] connection manager for the source.</span></span> <span data-ttu-id="7912b-104">Tramite questa pagina è inoltre possibile selezionare una tabella o una vista del database.</span><span class="sxs-lookup"><span data-stu-id="7912b-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="7912b-105">Per ulteriori informazioni sull'origine ADO NET, vedere [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="7912b-105">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="7912b-106">**Per aprire la pagina Gestione connessione**</span><span class="sxs-lookup"><span data-stu-id="7912b-106">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="7912b-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], aprire il pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] con l'origine ADO NET.</span><span class="sxs-lookup"><span data-stu-id="7912b-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="7912b-108">Nella scheda **Flusso di dati** fare doppio clic sull'origine ADO NET.</span><span class="sxs-lookup"><span data-stu-id="7912b-108">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="7912b-109">In **Editor origine ADO.NET**, fare clic su **Gestione connessione**.</span><span class="sxs-lookup"><span data-stu-id="7912b-109">In the **ADO NET Source Editor**, click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="7912b-110">Opzioni statiche</span><span class="sxs-lookup"><span data-stu-id="7912b-110">Static Options</span></span>  
 <span data-ttu-id="7912b-111">**Gestione connessione ADO.NET**</span><span class="sxs-lookup"><span data-stu-id="7912b-111">**ADO.NET connection manager**</span></span>  
 <span data-ttu-id="7912b-112">Selezionare una gestione connessione esistente nell'elenco o crearne una nuova facendo clic su **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="7912b-112">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="7912b-113">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="7912b-113">**New**</span></span>  
 <span data-ttu-id="7912b-114">Consente di creare una nuova gestione connessione usando la finestra di dialogo **Configura gestione connessione ADO.NET** .</span><span class="sxs-lookup"><span data-stu-id="7912b-114">Create a new connection manager by using the **Configure ADO.NET Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="7912b-115">**Modalità di accesso ai dati**</span><span class="sxs-lookup"><span data-stu-id="7912b-115">**Data access mode**</span></span>  
 <span data-ttu-id="7912b-116">Consente di specificare il metodo per la selezione dei dati dall'origine.</span><span class="sxs-lookup"><span data-stu-id="7912b-116">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="7912b-117">Opzione</span><span class="sxs-lookup"><span data-stu-id="7912b-117">Option</span></span>|<span data-ttu-id="7912b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7912b-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="7912b-119">Tabella o vista</span><span class="sxs-lookup"><span data-stu-id="7912b-119">Table or view</span></span>|<span data-ttu-id="7912b-120">Consente di recuperare dati da una tabella o da una vista nell'origine dei dati [!INCLUDE[vstecado](../includes/vstecado-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7912b-120">Retrieve data from a table or view in the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source.</span></span>|  
|<span data-ttu-id="7912b-121">Comando SQL</span><span class="sxs-lookup"><span data-stu-id="7912b-121">SQL command</span></span>|<span data-ttu-id="7912b-122">Consente di recuperare dati dall'origine dei dati [!INCLUDE[vstecado](../includes/vstecado-md.md)] usando una query SQL.</span><span class="sxs-lookup"><span data-stu-id="7912b-122">Retrieve data from the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source by using a SQL query.</span></span>|  
  
 <span data-ttu-id="7912b-123">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="7912b-123">**Preview**</span></span>  
 <span data-ttu-id="7912b-124">Consente di visualizzare in anteprima i risultati nella finestra di dialogo **Vista dati** .</span><span class="sxs-lookup"><span data-stu-id="7912b-124">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="7912b-125">L'**anteprima** supporta la visualizzazione di un massimo di 200 righe.</span><span class="sxs-lookup"><span data-stu-id="7912b-125">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7912b-126">Quando vengono visualizzati i dati in anteprima, le colonne con tipo definito dall'utente CLR (UDT) non contengono dati.</span><span class="sxs-lookup"><span data-stu-id="7912b-126">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="7912b-127">Contengono invece i valori \<value too big to display> o System.Byte[] display.</span><span class="sxs-lookup"><span data-stu-id="7912b-127">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="7912b-128">Il primo viene visualizzato se si accede all'origine dei dati mediante il [!INCLUDE[vstecado](../includes/vstecado-md.md)] , il secondo se si utilizza il provider [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="7912b-128">The former displays when the data source is accessed by using the [!INCLUDE[vstecado](../includes/vstecado-md.md)] provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="7912b-129">Opzioni dinamiche relative alla modalità di accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="7912b-129">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="7912b-130">Modalità di accesso ai dati = Tabella o vista</span><span class="sxs-lookup"><span data-stu-id="7912b-130">Data access mode = Table or view</span></span>  
 <span data-ttu-id="7912b-131">**Nome tabella o vista**</span><span class="sxs-lookup"><span data-stu-id="7912b-131">**Name of the table or the view**</span></span>  
 <span data-ttu-id="7912b-132">Consente di selezionare il nome della tabella o della vista nell'elenco dei nomi disponibili nell'origine dei dati.</span><span class="sxs-lookup"><span data-stu-id="7912b-132">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="7912b-133">Modalità di accesso ai dati = Comando SQL</span><span class="sxs-lookup"><span data-stu-id="7912b-133">Data access mode = SQL command</span></span>  
 <span data-ttu-id="7912b-134">**Testo comando SQL**</span><span class="sxs-lookup"><span data-stu-id="7912b-134">**SQL command text**</span></span>  
 <span data-ttu-id="7912b-135">Immettere il testo di una query SQL, fare clic su **Compila query**per compilare la query o fare clic su **Sfoglia**per individuare il file che contiene il testo della query.</span><span class="sxs-lookup"><span data-stu-id="7912b-135">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="7912b-136">**Compila query**</span><span class="sxs-lookup"><span data-stu-id="7912b-136">**Build query**</span></span>  
 <span data-ttu-id="7912b-137">Usare la finestra di dialogo **Generatore query** per creare la query SQL con strumenti grafici visuali.</span><span class="sxs-lookup"><span data-stu-id="7912b-137">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="7912b-138">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="7912b-138">**Browse**</span></span>  
 <span data-ttu-id="7912b-139">Usare la finestra di dialogo **Apri** per individuare il file contenente il testo della query SQL.</span><span class="sxs-lookup"><span data-stu-id="7912b-139">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7912b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7912b-140">See Also</span></span>  
 <span data-ttu-id="7912b-141">[Editor origine ADO NET &#40;pagina colonne&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="7912b-141">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="7912b-142">[Editor origine ADO NET &#40;pagina output degli errori&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="7912b-142">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="7912b-143">Gestione connessione ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7912b-143">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
