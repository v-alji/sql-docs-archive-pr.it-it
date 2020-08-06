---
title: Editor trasformazione Ricerca (pagina connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.referencetable.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: e90d6b69-5a26-43c5-8433-5c3c9588e08c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 381378ac1aca85c6bca825033bc439ebc39fb063
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628809"
---
# <a name="lookup-transformation-editor-connection-page"></a><span data-ttu-id="82c84-102">Editor trasformazione Ricerca (pagina Connessione)</span><span class="sxs-lookup"><span data-stu-id="82c84-102">Lookup Transformation Editor (Connection Page)</span></span>
  <span data-ttu-id="82c84-103">Usare la pagina **Connessione** della finestra di dialogo **Editor trasformazione Ricerca** per selezionare una gestione connessione.</span><span class="sxs-lookup"><span data-stu-id="82c84-103">Use the **Connection** page of the **Lookup Transformation Editor** dialog box to select a connection manager.</span></span> <span data-ttu-id="82c84-104">Se si seleziona una gestione connessione OLE DB, viene anche selezionata anche una query, una tabella o una vista per generare il set di dati di riferimento.</span><span class="sxs-lookup"><span data-stu-id="82c84-104">If you select an OLE DB connection manager, you also select a query, table, or view to generate the reference dataset.</span></span>  
  
 <span data-ttu-id="82c84-105">Per ulteriori informazioni sulla trasformazione Ricerca, vedere [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="82c84-105">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="82c84-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="82c84-106">Options</span></span>  
 <span data-ttu-id="82c84-107">Le opzioni seguenti sono disponibili quando si selezionano **Full cache** e **Gestione connessione della cache** nella pagina Generale della finestra di dialogo **Editor trasformazione Ricerca** .</span><span class="sxs-lookup"><span data-stu-id="82c84-107">The following options are available when you select **Full cache** and **Cache connection manager** on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="82c84-108">**Gestione connessione della cache**</span><span class="sxs-lookup"><span data-stu-id="82c84-108">**Cache connection manager**</span></span>  
 <span data-ttu-id="82c84-109">Selezionare una gestione connessione della cache esistente nell'elenco o fare clic su **Nuova**per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="82c84-109">Select an existing Cache connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="82c84-110">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="82c84-110">**New**</span></span>  
 <span data-ttu-id="82c84-111">Consente di creare una nuova gestione connessione nella finestra di dialogo **Editor gestione connessione della cache** .</span><span class="sxs-lookup"><span data-stu-id="82c84-111">Create a new connection by using the **Cache Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="82c84-112">Le opzioni seguenti sono disponibili quando si selezionano **Full cache**, **Partial cache**o **No cache**e **Gestione connessione OLE DB**nella pagina Generale della finestra di dialogo **Editor trasformazione Ricerca** .</span><span class="sxs-lookup"><span data-stu-id="82c84-112">The following options are available when you select **Full cache**, **Partial cache**, or **No cache**, and **OLE DB connection manager**, on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="82c84-113">**Gestione connessione OLE DB**</span><span class="sxs-lookup"><span data-stu-id="82c84-113">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="82c84-114">Selezionare una gestione connessione OLE DB esistente nell'elenco o fare clic su **Nuova**per creare una nuova connessione.</span><span class="sxs-lookup"><span data-stu-id="82c84-114">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="82c84-115">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="82c84-115">**New**</span></span>  
 <span data-ttu-id="82c84-116">Consente di creare una nuova connessione usando la finestra di dialogo **Configura gestione connessione OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="82c84-116">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="82c84-117">**Tabella o vista**</span><span class="sxs-lookup"><span data-stu-id="82c84-117">**Use a table or view**</span></span>  
 <span data-ttu-id="82c84-118">Consente di selezionare una tabella o una vista esistente nell'elenco oppure di creare una nuova tabella facendo clic su **nuova**.</span><span class="sxs-lookup"><span data-stu-id="82c84-118">Select an existing table or view from the list, or create a new table by clicking **New**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="82c84-119">Se si specifica un'istruzione SQL nella pagina **Avanzate** di **Editor trasformazione Ricerca**, tale istruzione sostituisce il nome di tabella selezionato, in quanto ha priorità su di esso.</span><span class="sxs-lookup"><span data-stu-id="82c84-119">If you specify a SQL statement on the **Advanced** page of the **Lookup Transformation Editor**, that SQL statement overrides and replaces the table name selected here.</span></span> <span data-ttu-id="82c84-120">Per altre informazioni, vedere [Editor trasformazione Ricerca &#40;pagina Avanzate&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="82c84-120">For more information, see [Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span></span>  
  
 <span data-ttu-id="82c84-121">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="82c84-121">**New**</span></span>  
 <span data-ttu-id="82c84-122">Consente di creare una nuova tabella usando la finestra di dialogo **Crea tabella** .</span><span class="sxs-lookup"><span data-stu-id="82c84-122">Create a new table by using the **Create Table** dialog box.</span></span>  
  
 <span data-ttu-id="82c84-123">**Usa i risultati di una query SQL**</span><span class="sxs-lookup"><span data-stu-id="82c84-123">**Use results of an SQL query**</span></span>  
 <span data-ttu-id="82c84-124">Questa opzione consente di visualizzare una query preesistente, compilare una nuova query, controllare la sintassi della query e visualizzare in anteprima i risultati della query.</span><span class="sxs-lookup"><span data-stu-id="82c84-124">Choose this option to browse to a preexisting query, build a new query, check query syntax, and preview query results.</span></span>  
  
 <span data-ttu-id="82c84-125">**Compila query**</span><span class="sxs-lookup"><span data-stu-id="82c84-125">**Build query**</span></span>  
 <span data-ttu-id="82c84-126">Consente di creare l'istruzione Transact-SQL da usare per l'esecuzione tramite **Generatore query**, uno strumento grafico usato per creare query tramite la visualizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="82c84-126">Create the Transact-SQL statement to run by using **Query Builder**, a graphical tool that is used to create queries by browsing through data.</span></span>  
  
 <span data-ttu-id="82c84-127">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="82c84-127">**Browse**</span></span>  
 <span data-ttu-id="82c84-128">Utilizzare questa opzione per visualizzare una query preesistente salvata in un file.</span><span class="sxs-lookup"><span data-stu-id="82c84-128">Use this option to browse to a preexisting query saved as a file.</span></span>  
  
 <span data-ttu-id="82c84-129">**Analizza query**</span><span class="sxs-lookup"><span data-stu-id="82c84-129">**Parse Query**</span></span>  
 <span data-ttu-id="82c84-130">Consente di controllare la sintassi della query.</span><span class="sxs-lookup"><span data-stu-id="82c84-130">Check the syntax of the query.</span></span>  
  
 <span data-ttu-id="82c84-131">**Anteprima**</span><span class="sxs-lookup"><span data-stu-id="82c84-131">**Preview**</span></span>  
 <span data-ttu-id="82c84-132">Consente di visualizzare in anteprima i risultati nella finestra di dialogo **Anteprima risultati query** .</span><span class="sxs-lookup"><span data-stu-id="82c84-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="82c84-133">Questa opzione consente di visualizzare fino a 200 righe.</span><span class="sxs-lookup"><span data-stu-id="82c84-133">This option displays up to 200 rows.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="82c84-134">Risorse esterne</span><span class="sxs-lookup"><span data-stu-id="82c84-134">External Resources</span></span>  
 <span data-ttu-id="82c84-135">Intervento nel blog sulle [modalità cache di ricerca](https://go.microsoft.com/fwlink/?LinkId=219518) su blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="82c84-135">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82c84-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82c84-136">See Also</span></span>  
 <span data-ttu-id="82c84-137">[Editor trasformazione Ricerca &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="82c84-137">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="82c84-138">[Editor trasformazione Ricerca &#40;pagina colonne&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="82c84-138">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="82c84-139">[Editor trasformazione Ricerca &#40;pagina avanzate&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="82c84-139">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="82c84-140">[Editor trasformazione Ricerca &#40;pagina output degli errori&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="82c84-140">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="82c84-141">Ricerca fuzzy - trasformazione</span><span class="sxs-lookup"><span data-stu-id="82c84-141">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
