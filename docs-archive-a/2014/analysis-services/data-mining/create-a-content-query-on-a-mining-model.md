---
title: Creazione di una query sul contenuto in un modello di data mining | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: a0ce837a-89ed-46cf-9ce1-801ccb75fa04
author: minewiskan
ms.author: owend
ms.openlocfilehash: 26af1100d6ba80185c1cc4de18548df0e387824c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711160"
---
# <a name="create-a-content-query-on-a-mining-model"></a><span data-ttu-id="fb363-102">Creare una query sul contenuto di un modello di data mining</span><span class="sxs-lookup"><span data-stu-id="fb363-102">Create a Content Query on a Mining Model</span></span>
  <span data-ttu-id="fb363-103">È possibile eseguire una query a livello di codice sul contenuto del modello di data mining utilizzando AMO o XML/A, ma è più facile creare query mediante DMX.</span><span class="sxs-lookup"><span data-stu-id="fb363-103">You can query the mining model content programmatically by using AMO or XML/A, but it is easier to create queries by using DMX.</span></span> <span data-ttu-id="fb363-104">È anche possibile creare query sui set di righe dello schema di data mining stabilendo una connessione all'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] e creando una query tramite le viste a gestione dinamica fornite da [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb363-104">You can also create queries against the data mining schema rowsets by establishing a connection to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and creating a query using the DMVs provided by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fb363-105">Nelle procedure riportate di seguito viene illustrato come creare le query su un modello di data mining utilizzando DMX e come eseguire una query sui set di righe dello schema di data mining.</span><span class="sxs-lookup"><span data-stu-id="fb363-105">The following procedures demonstrate how to create queries against a mining model by using DMX, and how to query the data mining schema rowsets.</span></span>  
  
 <span data-ttu-id="fb363-106">Per un esempio di come creare una query simile con XMLA, vedere [Creare una query di data mining usando XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="fb363-106">For an example of how to create a similar query by using XML/A, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="querying-data-mining-model-content-by-using-dmx"></a><span data-ttu-id="fb363-107">Esecuzione di una query sul contenuto del modello di data mining utilizzando DMX</span><span class="sxs-lookup"><span data-stu-id="fb363-107">Querying Data Mining Model Content by Using DMX</span></span>  
  
#### <a name="to-create-a-dmx-model-content-query"></a><span data-ttu-id="fb363-108">Per creare una query del contenuto del modello DMX</span><span class="sxs-lookup"><span data-stu-id="fb363-108">To create a DMX model content query</span></span>  
  
1.  <span data-ttu-id="fb363-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Esplora modelli** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="fb363-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="fb363-110">Nel riquadro **Esplora modelli** fare clic sull'icona del cubo per modificare l'elenco e visualizzare i modelli di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="fb363-110">In the **Template Explorer** pane, click the cube icon to change the list and display Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="fb363-111">Nell'elenco di categorie del modello, espandere **DMX**, **Contenuto del modello**e quindi fare doppio clic su **Query contenuto**.</span><span class="sxs-lookup"><span data-stu-id="fb363-111">In the list of template categories, expand **DMX**, expand **Model Content**, and double-click **Content Query**.</span></span>  
  
4.  <span data-ttu-id="fb363-112">Nella finestra di dialogo **Connetti a Analysis Services** selezionare l'istanza che contiene il modello di data mining su cui eseguire la query e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="fb363-112">In the **Connect to Analysis Services** dialog box, select the instance that contains the mining model you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="fb363-113">Il modello **Query contenuto** si apre nell'editor del codice adatto.</span><span class="sxs-lookup"><span data-stu-id="fb363-113">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="fb363-114">Nel riquadro dei metadati sono elencati i modelli disponibili nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="fb363-114">The metadata pane lists the models that are available in the current database.</span></span> <span data-ttu-id="fb363-115">Per modificare il database, selezionare un altro database nell'elenco **Database disponibili** .</span><span class="sxs-lookup"><span data-stu-id="fb363-115">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
5.  <span data-ttu-id="fb363-116">Immettere il nome di un modello di data mining nella riga `FROM` [ *\<mining model, name, MyModel>* ] `.CONTENT` .</span><span class="sxs-lookup"><span data-stu-id="fb363-116">Enter the name of a mining model in the line, `FROM` [*\<mining model, name, MyModel>*]`.CONTENT`.</span></span> <span data-ttu-id="fb363-117">Se nel nome del modello di data mining sono inclusi spazi, tale nome deve essere racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="fb363-117">If the mining model name contains spaces, you must enclose the name in brackets.</span></span>  
  
     <span data-ttu-id="fb363-118">Se non si vuole digitare il nome, è possibile selezionare un modello di data mining in **Esplora oggetti** e trascinarlo nel modello.</span><span class="sxs-lookup"><span data-stu-id="fb363-118">If you don't want to type the name, you can select a mining model in **Object Explorer** and drag it into the template.</span></span>  
  
6.  <span data-ttu-id="fb363-119">Nella riga, `SELECT` *\<select list, expr list, \*>* , digitare i nomi delle colonne nel set di righe dello schema del contenuto del modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="fb363-119">In the line, `SELECT`*\<select list, expr list, \*>*, type the names of columns in the mining model content schema rowset.</span></span>  
  
     <span data-ttu-id="fb363-120">Per visualizzare un elenco di colonne che è possibile restituire nelle query del contenuto del modello di data mining, vedere [Contenuto dei modelli di data mining &#40;Analysis Services - Data mining&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="fb363-120">To view a list of columns that you can return in mining model content queries, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>  
  
7.  <span data-ttu-id="fb363-121">Facoltativamente, digitare una condizione nella clausola WHERE del modello per limitare le righe restituite a nodi o valori specifici.</span><span class="sxs-lookup"><span data-stu-id="fb363-121">Optionally, type a condition in the WHERE clause of the template to restrict the rows returned to specific nodes or values.</span></span>  
  
8.  <span data-ttu-id="fb363-122">Fare clic su **Execute**.</span><span class="sxs-lookup"><span data-stu-id="fb363-122">Click **Execute**.</span></span>  
  
## <a name="querying-the-data-mining-schema-rowsets"></a><span data-ttu-id="fb363-123">Esecuzione di una query sui set di righe dello schema di data mining</span><span class="sxs-lookup"><span data-stu-id="fb363-123">Querying the Data Mining Schema Rowsets</span></span>  
  
#### <a name="to-create-a-query-against-the-data-mining-schema-rowset"></a><span data-ttu-id="fb363-124">Per creare una query sul set di righe dello schema di data mining</span><span class="sxs-lookup"><span data-stu-id="fb363-124">To create a query against the data mining schema rowset</span></span>  
  
1.  <span data-ttu-id="fb363-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], sulla barra degli strumenti **Nuova query** fare clic su **Query DMX di Analysis Services**o **Query MDX di Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="fb363-125">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **New Query** toolbar, click **Analysis Services DMX Query**, or **Analysis Services MDX query**.</span></span>  
  
2.  <span data-ttu-id="fb363-126">Nella finestra di dialogo **Connetti ad Analysis Services** selezionare l'istanza che contiene gli oggetti su cui eseguire la query e fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="fb363-126">In the **Connect to Analysis Services** dialog box, select the instance that contains the objects you want to query, and click **Connect**.</span></span>  
  
     <span data-ttu-id="fb363-127">Il modello **Query contenuto** si apre nell'editor del codice adatto.</span><span class="sxs-lookup"><span data-stu-id="fb363-127">The **Content Query** template opens in the appropriate code editor.</span></span> <span data-ttu-id="fb363-128">Nel riquadro dei metadati sono elencati gli oggetti disponibili nel database corrente.</span><span class="sxs-lookup"><span data-stu-id="fb363-128">The metadata pane lists the objects that are available in the current database.</span></span> <span data-ttu-id="fb363-129">Per modificare il database, selezionare un altro database nell'elenco **Database disponibili** .</span><span class="sxs-lookup"><span data-stu-id="fb363-129">To change the database, select a different database from the **Available Databases** list.</span></span>  
  
3.  <span data-ttu-id="fb363-130">Nell'editor di query digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fb363-130">In the query editor, type the following:</span></span>  
  
     `SELECT *`  
  
     `FROM $system.DMSCHEMA_MINING_MODEL_CONTENT`  
  
     `WHERE MODEL_NAME = '<model name>'`  
  
4.  <span data-ttu-id="fb363-131">Fare clic su **Execute**.</span><span class="sxs-lookup"><span data-stu-id="fb363-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="fb363-132">Nel riquadro Risultati verrà visualizzato il contenuto del modello.</span><span class="sxs-lookup"><span data-stu-id="fb363-132">The Results pane displays the contents of the model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb363-133">Per visualizzare un elenco di tutti i set di righe dello schema su cui è possibile eseguire una query nell'istanza corrente, utilizzare la query `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span><span class="sxs-lookup"><span data-stu-id="fb363-133">To view a list of all the schema rowsets that you can query on the current instance, use this query: `SELECT * FROM $system.`DISCOVER_SCHEMA_ROWSETS.</span></span> <span data-ttu-id="fb363-134">In alternativa, per un elenco di set di righe dello schema specifici del data mining, vedere [Set di righe dello schema di data mining](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="fb363-134">Or, for a list of schema rowsets specific to data mining, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb363-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb363-135">See Also</span></span>  
 <span data-ttu-id="fb363-136">[Contenuto del modello di data mining &#40;Analysis Services-&#41;di data mining](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="fb363-136">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="fb363-137">Set di righe dello schema di data mining</span><span class="sxs-lookup"><span data-stu-id="fb363-137">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
