---
title: Creazione di una query di data mining tramite XMLA | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 8f6b6008-006c-4792-9bd1-64c30dc3fd41
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0e85b17db0781671fab0874706f12fdac95b30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636960"
---
# <a name="create-a-data-mining-query-by-using-xmla"></a><span data-ttu-id="c75b4-102">Creare una query di data mining usando XMLA</span><span class="sxs-lookup"><span data-stu-id="c75b4-102">Create a Data Mining Query by Using XMLA</span></span>
  <span data-ttu-id="c75b4-103">È possibile creare diverse query sugli oggetti di data mining utilizzando AMO, DMX o XML/A.</span><span class="sxs-lookup"><span data-stu-id="c75b4-103">You can create a variety of queries against data mining objects by using AMO, DMX, or XML/A.</span></span>  
  
 <span data-ttu-id="c75b4-104">XML viene utilizzato per le comunicazioni tra il server Analysis Services e tutti i client.</span><span class="sxs-lookup"><span data-stu-id="c75b4-104">XML is used for communication between the Analysis Services server and all clients.</span></span> <span data-ttu-id="c75b4-105">Pertanto, anche se generalmente è molto più facile creare query sul contenuto utilizzando DMX, è possibile scrivere query tramite le istruzioni DISCOVER e COMMAND di XML/A, tramite un client che supporta il protocollo SOAP o creando una query XML/A in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c75b4-105">Therefore, although it is generally much easier to create content queries by using DMX, you can write queries by using the DISCOVER and COMMAND statements in XML/A, either by using a client that supports the SOAP protocol, or by creating an XML/A query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c75b4-106">In questo argomento viene illustrato come usare i modelli XML/A disponibili in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per creare una query sul contenuto di un modello di data mining archiviato nel server corrente.</span><span class="sxs-lookup"><span data-stu-id="c75b4-106">This topic explains how to use the XML/A templates that are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a model content query against a mining model stored on the current server.</span></span>  
  
## <a name="querying-data-mining-schema-rowsets-by-using-xmla"></a><span data-ttu-id="c75b4-107">Esecuzione di una query sui set di righe dello schema di data mining utilizzando XML/A</span><span class="sxs-lookup"><span data-stu-id="c75b4-107">Querying Data Mining Schema Rowsets by Using XML/A</span></span>  
  
#### <a name="to-open-an-xmla-template"></a><span data-ttu-id="c75b4-108">Per aprire un modello XML/A</span><span class="sxs-lookup"><span data-stu-id="c75b4-108">To open an XML/A template</span></span>  
  
1.  <span data-ttu-id="c75b4-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]scegliere **Esplora modelli** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="c75b4-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="c75b4-110">Fare clic sull'icona del cubo per aprire l'elenco dei modelli di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="c75b4-110">Click the cube icon to open the list of Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="c75b4-111">Nell'elenco di categorie dei modelli espandere prima **XMLA**, poi **Set di righe dello schema**, quindi fare doppio clic su **Discover Schema Rowsets** (Individua set di righe dello schema) per aprire il modello nell'editor del codice appropriato.</span><span class="sxs-lookup"><span data-stu-id="c75b4-111">In the list of template categories, expand **XMLA**, expand **Schema Rowsets**, and double-click **Discover Schema Rowsets** to open the template in the appropriate code editor.</span></span>  
  
4.  <span data-ttu-id="c75b4-112">Nella finestra di dialogo **Connetti a Analysis Services** completare le informazioni di connessione e quindi fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="c75b4-112">In the **Connect to Analysis Services** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="c75b4-113">Verrà visualizzata una nuova finestra dell'editor di query contenente il modello **Individua set di righe dello schema** .</span><span class="sxs-lookup"><span data-stu-id="c75b4-113">A new query editor window opens, populated with the **Discover Schema Rowsets** template.</span></span>  
  
#### <a name="to-discover-column-names-from-the-mining-model-content-schema-rowset"></a><span data-ttu-id="c75b4-114">Per individuare i nomi delle colonne del set di righe dello schema MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="c75b4-114">To discover column names from the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="c75b4-115">Con il modello **Individua set di righe dello schema** aperto, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="c75b4-115">With the **Discover Schema Rowsets** template open, click **Execute**.</span></span>  
  
     <span data-ttu-id="c75b4-116">Viene visualizzato un elenco di set di righe dello schema nel riquadro **Risultati** che contiene i nomi e le colonne di tutti i set di righe disponibili nell'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="c75b4-116">A list of schema rowsets is returned in the **Results** pane that contains the rowset names and rowset columns for all rowsets available on the current instance.</span></span>  
  
2.  <span data-ttu-id="c75b4-117">Nel riquadro **query** posizionare il cursore dopo **\<Restriction List>** e premere INVIO per aggiungere una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="c75b4-117">In the **Query** pane, place the cursor after **\<Restriction List>** and press ENTER to add a new line.</span></span>  
  
3.  <span data-ttu-id="c75b4-118">Posizionare il cursore sulla riga vuota e digitare \*\* \<SchemaName> DMSCHEMA_MINING_MODEL_CONTENT \</SchemaName> \*\*</span><span class="sxs-lookup"><span data-stu-id="c75b4-118">Place the cursor on the blank line and type **\<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT\</SchemaName>**</span></span>  
  
     <span data-ttu-id="c75b4-119">La sezione completa delle restrizioni visualizzata sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c75b4-119">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT</SchemaName>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
4.  <span data-ttu-id="c75b4-120">Fare clic su **Execute**.</span><span class="sxs-lookup"><span data-stu-id="c75b4-120">Click **Execute**.</span></span>  
  
     <span data-ttu-id="c75b4-121">Nel riquadro **Risultati** viene visualizzato un elenco dei nomi delle colonne relativo al set di righe dello schema specificato.</span><span class="sxs-lookup"><span data-stu-id="c75b4-121">The **Results** pane shows a list of column names for the specified schema rowset.</span></span>  
  
#### <a name="to-create-a-content-query-using-the-mining-model-content-schema-rowset"></a><span data-ttu-id="c75b4-122">Per creare una query sul contenuto utilizzando il set di righe dello schema MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="c75b4-122">To create a content query using the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="c75b4-123">Nel modello **Individua set di righe dello schema** modificare il tipo di richiesta sostituendo il testo nei tag del tipo di richiesta.</span><span class="sxs-lookup"><span data-stu-id="c75b4-123">In the **Discover Schema Rowsets** template, change the request type by replacing the text inside the request type tags.</span></span>  
  
     <span data-ttu-id="c75b4-124">Sostituire questa riga:</span><span class="sxs-lookup"><span data-stu-id="c75b4-124">Replace this line:</span></span>  
  
     `<RequestType>DISCOVER_SCHEMA_ROWSETS</RequestType>`  
  
     <span data-ttu-id="c75b4-125">con la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="c75b4-125">with the following line:</span></span>  
  
     <span data-ttu-id="c75b4-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span><span class="sxs-lookup"><span data-stu-id="c75b4-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span></span>  
  
2.  <span data-ttu-id="c75b4-127">Modificare l'elenco delle restrizioni per specificare un modello di data mining in base al nome aggiungendo una nuova condizione all'elenco di restrizioni.</span><span class="sxs-lookup"><span data-stu-id="c75b4-127">Change the restriction list to specify a mining model by name, by adding a new condition to the restriction lists.</span></span>  
  
3.  <span data-ttu-id="c75b4-128">Nel modello posizionare il cursore dopo `<Restriction List>` e premere INVIO per aggiungere una nuova riga.</span><span class="sxs-lookup"><span data-stu-id="c75b4-128">In the template, place the cursor after `<Restriction List>` and press ENTER to add a new line.</span></span>  
  
4.  <span data-ttu-id="c75b4-129">Posizionare il cursore sulla riga vuota e digitare **<MODEL_NAME>Nome modello personale</MODEL_NAME>**</span><span class="sxs-lookup"><span data-stu-id="c75b4-129">Place the cursor on the blank line and type **<MODEL_NAME>My model name</MODEL_NAME>**</span></span>  
  
     <span data-ttu-id="c75b4-130">La sezione completa delle restrizioni visualizzata sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c75b4-130">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<MODEL_NAME>My model name</MODEL_NAME>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
5.  <span data-ttu-id="c75b4-131">Fare clic su **Execute**.</span><span class="sxs-lookup"><span data-stu-id="c75b4-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="c75b4-132">Nel riquadro Risultati viene visualizzata la definizione dello schema insieme ai valori del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="c75b4-132">The Results pane displays the schema definition, together with the values for the specified model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75b4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c75b4-133">See Also</span></span>  
 <span data-ttu-id="c75b4-134">[Contenuto del modello di data mining &#40;Analysis Services-&#41;di data mining](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="c75b4-134">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="c75b4-135">Set di righe dello schema di data mining</span><span class="sxs-lookup"><span data-stu-id="c75b4-135">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
