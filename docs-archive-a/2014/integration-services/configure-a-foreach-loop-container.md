---
title: Configurare un contenitore ciclo foreach | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Foreach Loop containers
- containers [Integration Services], Foreach Loop
ms.assetid: 519c6f96-5e1f-47d2-b96a-d49946948c25
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 85fb399f51e22e091fac9b1d8d332b9a12e7d77e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624874"
---
# <a name="configure-a-foreach-loop-container"></a><span data-ttu-id="70713-102">Configurare un contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="70713-102">Configure a Foreach Loop Container</span></span>
  <span data-ttu-id="70713-103">Questa procedura descrive la configurazione di un contenitore Ciclo Foreach, incluse le espressioni di proprietà a livello di enumeratore e contenitore.</span><span class="sxs-lookup"><span data-stu-id="70713-103">This procedure describes how to configure a Foreach Loop container, including property expressions at the enumerator and container levels.</span></span>  
  
### <a name="to-configure-the-foreach-loop-container"></a><span data-ttu-id="70713-104">Per configurare il contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="70713-104">To configure the Foreach Loop container</span></span>  
  
1.  <span data-ttu-id="70713-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="70713-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="70713-106">Fare clic sulla scheda **Flusso di controllo** e quindi fare doppio clic su Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="70713-106">Click the **Control Flow** tab and double-click the Foreach Loop.</span></span>  
  
3.  <span data-ttu-id="70713-107">Nella finestra di dialogo **Editor ciclo Foreach** fare clic su **Generale** e, facoltativamente, modificare il nome e la descrizione del ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="70713-107">In the **Foreach Loop Editor** dialog box, click **General** and, optionally, modify the name and description of the Foreach Loop.</span></span>  
  
4.  <span data-ttu-id="70713-108">Fare clic su **Raccolta** e selezionare un tipo di enumeratore nell'elenco **Enumeratore** .</span><span class="sxs-lookup"><span data-stu-id="70713-108">Click **Collection** and select an enumerator type from the **Enumerator** list.</span></span>  
  
5.  <span data-ttu-id="70713-109">Specificare un enumeratore e impostarne le opzioni nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="70713-109">Specify an enumerator and set enumerator options as follows:</span></span>  
  
    -   <span data-ttu-id="70713-110">Per usare l'enumeratore Foreach File, specificare la cartella che contiene i file da enumerare, specificare un filtro per il nome e il tipo di file e quindi specificare se deve essere restituito il nome completo del file.</span><span class="sxs-lookup"><span data-stu-id="70713-110">To usethe Foreach File enumerator, provide the folder that contains the files to enumerate, specify a filter for the file name and type, and specify whether the fully qualified file name should be returned.</span></span> <span data-ttu-id="70713-111">Indicare inoltre se ricercare ulteriori file nelle sottocartelle.</span><span class="sxs-lookup"><span data-stu-id="70713-111">Also, indicate whether to recurse through subfolders for more files.</span></span>  
  
    -   <span data-ttu-id="70713-112">Per usare l'enumeratore Foreach Item, fare clic su **Colonne**e, nella finestra di dialogo **Colonne For Each Item** , fare clic su **Aggiungi** per aggiungere le colonne.</span><span class="sxs-lookup"><span data-stu-id="70713-112">To use the Foreach Item enumerator, click **Columns**, and, in the **For Each Item Columns** dialog box, click **Add** to add columns.</span></span> <span data-ttu-id="70713-113">Selezionare un tipo di dati nell'elenco **Tipo di dati** per ogni colonna e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70713-113">Select a data type in the **Data Type** list for each column, and click **OK**.</span></span>  
  
         <span data-ttu-id="70713-114">Digitare i valori nelle colonne oppure selezionarli dagli elenchi.</span><span class="sxs-lookup"><span data-stu-id="70713-114">Type values in the columns or select values from lists.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="70713-115">Per aggiungere una nuova riga, fare clic in un punto qualsiasi al di fuori della cella in cui si è digitato.</span><span class="sxs-lookup"><span data-stu-id="70713-115">To add a new row, click anywhere outside the cell in which you typed.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="70713-116">Se un valore non è compatibile con il tipo di dati della colonna, il testo viene evidenziato.</span><span class="sxs-lookup"><span data-stu-id="70713-116">If a value is not compatible with the column data type, the text is highlighted.</span></span>  
  
    -   <span data-ttu-id="70713-117">Per usare l'enumeratore Foreach ADO, selezionare una variabile esistente oppure fare clic su **Nuova variabile** nell'elenco **Variabile di origine oggetto ADO** per specificare la variabile in cui è contenuto il nome dell'oggetto ADO da enumerare e selezionare l'opzione corrispondente alla modalità di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="70713-117">To use the Foreach ADO enumerator, select an existing variable or click **New variable** in the **ADO object source variable** list to specify the variable that contains the name of the ADO object to enumerate, and select an enumeration mode option.</span></span>  
  
         <span data-ttu-id="70713-118">Se si crea una nuova variabile, impostarne le proprietà nella finestra di dialogo **Aggiungi variabile** .</span><span class="sxs-lookup"><span data-stu-id="70713-118">If creating a new variable, set the variable properties in the **Add Variable** dialog box.</span></span>  
  
    -   <span data-ttu-id="70713-119">Per usare l'enumeratore Foreach ADO.NET set di righe dello schema, selezionare un connettore ADO.NET esistente oppure fare clic su **Nuova connessione** nell'elenco **Connessione** e quindi selezionare uno schema.</span><span class="sxs-lookup"><span data-stu-id="70713-119">To use the Foreach ADO.NET Schema Rowset enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then select a schema.</span></span>  
  
         <span data-ttu-id="70713-120">Facoltativamente, fare clic su **Imposta restrizioni** e selezionare le restrizioni dello schema, selezionare la variabile che contiene il valore della restrizione oppure digitare il valore della restrizione e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70713-120">Optionally, click **Set Restrictions** and select schema restrictions, select the variable that contains the restriction value or type the restriction value, and click **OK**.</span></span>  
  
    -   <span data-ttu-id="70713-121">Per usare l'enumeratore Foreach da variabile, selezionare una variabile nell'elenco **Variabile** .</span><span class="sxs-lookup"><span data-stu-id="70713-121">To use the Foreach From Variable enumerator, select a variable in the **Variable** list.</span></span>  
  
    -   <span data-ttu-id="70713-122">Per usare l'enumeratore Foreach NodeList, fare clic su DocumentSourceType e selezionare il tipo di origine nell'elenco, quindi fare clic su DocumentSource.</span><span class="sxs-lookup"><span data-stu-id="70713-122">To use the Foreach NodeList enumerator, click DocumentSourceType and select the source type from the list, and then click DocumentSource.</span></span> <span data-ttu-id="70713-123">A seconda del valore selezionato per DocumentSourceType, selezionare una variabile o una connessione file nell'elenco, creare una nuova variabile o connessione file oppure specificare l'origine XML in **Editor origine documento**.</span><span class="sxs-lookup"><span data-stu-id="70713-123">Depending on the value selected for DocumentSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the XML source in the **Document Source Editor**.</span></span>  
  
         <span data-ttu-id="70713-124">Fare quindi clic su EnumerationType e selezionare un tipo di enumeratore nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="70713-124">Next, click EnumerationType and select an enumeration type from the list.</span></span> <span data-ttu-id="70713-125">Se è EnumerationType è **Navigator, Node o NodeText**, fare clic su OuterXPathStringSourceType e selezionare il tipo di origine, quindi fare clic su OuterXPathString.</span><span class="sxs-lookup"><span data-stu-id="70713-125">If EnumerationType is **Navigator, Node, or NodeText**, click OuterXPathStringSourceType and select the source type, and then click OuterXPathString.</span></span> <span data-ttu-id="70713-126">A seconda del valore impostato per OuterXPathStringSourceType, selezionare una variabile o una connessione file nell'elenco, creare una nuova variabile o connessione file oppure digitare la stringa per l'espressione XPath (XML Path Language) esterna.</span><span class="sxs-lookup"><span data-stu-id="70713-126">Depending on the value set for OuterXPathStringSourceType, select a variable or a file connection from the list, create a new variable or file connection, or type the string for the outer XML Path Language (XPath) expression.</span></span>  
  
         <span data-ttu-id="70713-127">Se EnumerationType è **ElementCollection**, impostare OuterXPathStringSourceType e OuterXPathString come descritto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="70713-127">If EnumerationType is **ElementCollection**,set OuterXPathStringSourceType and OuterXPathString as described above.</span></span> <span data-ttu-id="70713-128">Fare quindi clic su InnerElementType, selezionare un tipo di enumerazione per gli elementi interni e quindi fare clic su InnerXPathStringSourceType.</span><span class="sxs-lookup"><span data-stu-id="70713-128">Then, click InnerElementType and select an enumeration type for the inner elements, and then click InnerXPathStringSourceType.</span></span> <span data-ttu-id="70713-129">A seconda del valore impostato per InnerXPathStringSourceType, selezionare una variabile o una connessione file, creare una nuova variabile o connessione file oppure digitare la stringa per l'espressione XPath interna.</span><span class="sxs-lookup"><span data-stu-id="70713-129">Depending on the value set for InnerXPathStringSourceType, select a variable or a file connection, create a new variable or file connection, or type the string for the inner XPath expression.</span></span>  
  
    -   <span data-ttu-id="70713-130">Per usare l'enumeratore Foreach SMO, selezionare una connessione ADO.NET esistente oppure fare clic su **Nuova connessione** nell'elenco **Connessione** e quindi digitare la stringa da usare oppure fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="70713-130">To use the Foreach SMO enumerator, select an existing ADO.NET connection or click **New connection** in the **Connection** list, and then either type the string to use or click **Browse**.</span></span> <span data-ttu-id="70713-131">Se si fa clic su **Sfoglia**, nella finestra di dialogo **Seleziona enumerazione SMO** selezionare il tipo di oggetto da enumerare e il tipo di enumerazione e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70713-131">If you click **Browse**, in the **Select SMO Enumeration** dialog box, select the object type to enumerate and the enumeration type, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="70713-132">Facoltativamente, fare clic sul pulsante sfoglia **(...)** nella casella di testo **Espressioni** della pagina **Raccolta** per creare espressioni che aggiornano i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="70713-132">Optionally, click the browse button **(...)** in the **Expressions** text box on the **Collection** page to create expressions that update property values.</span></span> <span data-ttu-id="70713-133">Per altre informazioni, vedere [Aggiunta o modifica di un'espressione di proprietà](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="70713-133">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="70713-134">Le proprietà incluse nell'elenco **Proprietà** variano a seconda dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="70713-134">The properties listed in the **Property** list varies by enumerator.</span></span>  
  
7.  <span data-ttu-id="70713-135">Facoltativamente, fare clic su **Mapping variabili** per eseguire il mapping delle proprietà degli oggetti ai valori della raccolta e quindi eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="70713-135">Optionally, click **Variable Mappings** to map object properties to the collection value, and then do the following:</span></span>  
  
    1.  <span data-ttu-id="70713-136">Nell'elenco **Variabili** selezionare una variabile oppure fare clic su **\<New Variable>** per creare una nuova variabile.</span><span class="sxs-lookup"><span data-stu-id="70713-136">In the **Variables** list, select a variable or click **\<New Variable>** to create a new variable.</span></span>  
  
    2.  <span data-ttu-id="70713-137">Se si aggiunge una nuova variabile, impostarne le proprietà nella finestra di dialogo **Aggiungi variabile** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70713-137">If you add a new variable, set the variable properties in the **Add Variable** dialog box and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="70713-138">Se si usa l'enumeratore For Each Item, è possibile aggiornare il valore dell'indice nell'elenco **Indice** .</span><span class="sxs-lookup"><span data-stu-id="70713-138">If you use the For Each Item enumerator, you can update the index value in the **Index** list.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="70713-139">Il valore dell'indice indica la colonna dell'elemento su cui eseguire il mapping alla variabile.</span><span class="sxs-lookup"><span data-stu-id="70713-139">The index value indicates which column in the item to map to the variable.</span></span> <span data-ttu-id="70713-140">Solo l'enumeratore For Each Item può utilizzare un valore di indice diverso da 0.</span><span class="sxs-lookup"><span data-stu-id="70713-140">Only the For Each Item enumerator can use an index value other than 0.</span></span>  
  
8.  <span data-ttu-id="70713-141">Facoltativamente, fare clic su **Espressioni** e, nella pagina **Espressioni** , creare espressioni di proprietà per le proprietà del contenitore Ciclo Foreach.</span><span class="sxs-lookup"><span data-stu-id="70713-141">Optionally, click **Expressions** and, on the **Expressions** page, create property expressions for the properties of the Foreach Loop container.</span></span> <span data-ttu-id="70713-142">Per altre informazioni, vedere [Aggiunta o modifica di un'espressione di proprietà](expressions/add-or-change-a-property-expression.md).</span><span class="sxs-lookup"><span data-stu-id="70713-142">For more information, see [Add or Change a Property Expression](expressions/add-or-change-a-property-expression.md).</span></span>  
  
9. <span data-ttu-id="70713-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="70713-143">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70713-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70713-144">See Also</span></span>  
 [<span data-ttu-id="70713-145">Contenitore Ciclo Foreach</span><span class="sxs-lookup"><span data-stu-id="70713-145">Foreach Loop Container</span></span>](control-flow/foreach-loop-container.md)  
  
  
