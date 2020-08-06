---
title: Impostare le proprietà di un componente flusso di dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], properties
ms.assetid: 73000ef6-52a2-4dec-8320-0e79acf0c2c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1fd045ba076eed2d65d801015b881a477976f5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636327"
---
# <a name="set-the-properties-of-a-data-flow-component"></a><span data-ttu-id="b671d-102">Impostazione delle proprietà di un componente del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="b671d-102">Set the Properties of a Data Flow Component</span></span>
  <span data-ttu-id="b671d-103">Per impostare le proprietà dei componenti flusso di dati, tra cui origini, destinazioni e trasformazioni, utilizzare una delle funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="b671d-103">To set the properties of data flow components, which include sources, destinations, and transformations, use one of the following features:</span></span>  
  
-   <span data-ttu-id="b671d-104">Editor dei componenti forniti da [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b671d-104">The component editors that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides.</span></span> <span data-ttu-id="b671d-105">Gli editor includono solo le proprietà personalizzate di ogni componente flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="b671d-105">These editors include only the custom properties of each data flow component.</span></span>  
  
-   <span data-ttu-id="b671d-106">Nella finestra **Proprietà** sono elencate sia le proprietà personalizzate a livello di componente per ogni elemento, sia le proprietà comuni a tutti gli elementi del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="b671d-106">The **Properties** window lists the component-level custom properties of each element, as well as the properties common to all data flow elements.</span></span>  
  
-   <span data-ttu-id="b671d-107">La finestra di dialogo **Editor avanzato** consente l'accesso alle proprietà personalizzate di ciascun componente.</span><span class="sxs-lookup"><span data-stu-id="b671d-107">The **Advanced Editor** dialog box provides access to custom properties for each component.</span></span> <span data-ttu-id="b671d-108">La finestra di dialogo **Editor avanzato** consente anche di accedere alle proprietà comuni a tutti i componenti flusso di dati, ossia le proprietà degli input, degli output, degli output degli errori, delle colonne e delle colonne esterne.</span><span class="sxs-lookup"><span data-stu-id="b671d-108">The **Advanced Editor** dialog box also provides access to the properties common to all data flow components-the properties of inputs, outputs, error outputs, columns, and external columns.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-a-component-editor"></a><span data-ttu-id="b671d-109">Per impostare le proprietà di un componente flusso di dati utilizzando l'editor del componente</span><span class="sxs-lookup"><span data-stu-id="b671d-109">To set the properties of a data flow component by using a component editor</span></span>  
  
1.  <span data-ttu-id="b671d-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b671d-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b671d-111">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b671d-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b671d-112">Fare clic sulla scheda **Flusso di controllo** , quindi fare doppio clic sull'attività Flusso di dati che contiene il flusso di dati con il componente di cui si desidera visualizzare e modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="b671d-112">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow with the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="b671d-113">Fare doppio clic sul componente del flusso di dati.</span><span class="sxs-lookup"><span data-stu-id="b671d-113">Double-click the data flow component.</span></span>  
  
5.  <span data-ttu-id="b671d-114">Nell'editor del componente visualizzare o modificare i valori delle proprietà e quindi chiudere l'editor.</span><span class="sxs-lookup"><span data-stu-id="b671d-114">In the component editor, view or modify the property values, and then close the editor.</span></span>  
  
6.  <span data-ttu-id="b671d-115">Per salvare il pacchetto aggiornato, dal menu **File** scegliere **Salva elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="b671d-115">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-properties-window"></a><span data-ttu-id="b671d-116">Per impostare le proprietà di un componente flusso di dati utilizzando la finestra delle proprietà</span><span class="sxs-lookup"><span data-stu-id="b671d-116">To set the properties of a data flow component by using the Properties window</span></span>  
  
1.  <span data-ttu-id="b671d-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b671d-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b671d-118">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b671d-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b671d-119">Fare clic sulla scheda **Flusso di controllo** , quindi fare doppio clic sull'attività Flusso di dati che contiene il componente di cui si desidera visualizzare e modificare le proprietà.</span><span class="sxs-lookup"><span data-stu-id="b671d-119">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="b671d-120">Fare clic con il pulsante destro del mouse sul componente flusso di dati, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b671d-120">Right-click the data flow component, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="b671d-121">Visualizzare o modificare i valori delle proprietà, quindi chiudere la finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="b671d-121">View or modify the property values, and then close the **Properties** window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b671d-122">Molte proprietà sono in sola lettura e non possono essere modificate.</span><span class="sxs-lookup"><span data-stu-id="b671d-122">Many properties are read-only, and cannot be modified.</span></span>  
  
6.  <span data-ttu-id="b671d-123">Per salvare il pacchetto aggiornato, dal menu **File** scegliere **Salva elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="b671d-123">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-advanced-editor"></a><span data-ttu-id="b671d-124">Per impostare le proprietà di un componente flusso di dati utilizzando l'editor avanzato</span><span class="sxs-lookup"><span data-stu-id="b671d-124">To set the properties of a data flow component by using the Advanced Editor</span></span>  
  
1.  <span data-ttu-id="b671d-125">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b671d-125">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b671d-126">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="b671d-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b671d-127">Fare clic sulla scheda **Flusso di controllo** , quindi fare doppio clic sull'attività Flusso di dati che contiene il componente che si desidera visualizzare o modificare.</span><span class="sxs-lookup"><span data-stu-id="b671d-127">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component you want to view or modify.</span></span>  
  
4.  <span data-ttu-id="b671d-128">Nella finestra di progettazione del flusso di dati fare clic con il pulsante destro del mouse sul componente flusso di dati, quindi scegliere **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="b671d-128">In the data flow designer, right-click the data flow component, and then click **Show Advanced Editor**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b671d-129">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]non è possibile utilizzare la finestra di dialogo **Editor avanzato**per i componenti flusso di dati che supportano più input.</span><span class="sxs-lookup"><span data-stu-id="b671d-129">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data flow components that support multiple inputs cannot use the **Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="b671d-130">Nella finestra di dialogo **Editor avanzato** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b671d-130">In the **Advanced Editor** dialog box, do any of the following steps:</span></span>  
  
    -   <span data-ttu-id="b671d-131">Fare clic sulla scheda **Gestioni connessioni** per visualizzare e specificare la connessione usata dal componente.</span><span class="sxs-lookup"><span data-stu-id="b671d-131">To view and specify the connection that the component uses, click the **Connection Managers** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b671d-132">La scheda **Gestioni connessioni** è disponibile solo per i componenti flusso di dati che utilizzano gestioni connessioni per connettersi a origini dati quali file e database.</span><span class="sxs-lookup"><span data-stu-id="b671d-132">The **Connection Managers** tab is available only to data flow components that use connection managers to connect to data sources such as files and databases</span></span>  
  
    -   <span data-ttu-id="b671d-133">Fare clic sulla scheda **Proprietà componente** per visualizzare e modificare le proprietà a livello di componente.</span><span class="sxs-lookup"><span data-stu-id="b671d-133">To view and modify component-level properties, click the **Component Properties** tab.</span></span>  
  
    -   <span data-ttu-id="b671d-134">Fare clic sulla scheda **Mapping colonne** per visualizzare e modificare i mapping tra le colonne esterne e l'output disponibile.</span><span class="sxs-lookup"><span data-stu-id="b671d-134">To view and modify mappings between external columns and the available output, click the **Column Mappings** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b671d-135">La scheda **Mapping colonne** è disponibile solo durante la visualizzazione o la modifica di origini o destinazioni.</span><span class="sxs-lookup"><span data-stu-id="b671d-135">The **Column Mappings** tab is available only when viewing or editing sources or destinations.</span></span>  
  
    -   <span data-ttu-id="b671d-136">Per visualizzare un elenco delle colonne di input disponibili e aggiornare i nomi delle colonne di output, fare clic sulla scheda **Colonne di input** .</span><span class="sxs-lookup"><span data-stu-id="b671d-136">To view a list of the available input columns and to update the names of output columns, click the **Input Columns** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b671d-137">La scheda Colonne di input è disponibile solo quando si utilizzano trasformazioni o destinazioni.</span><span class="sxs-lookup"><span data-stu-id="b671d-137">The Input Columns tab is available only when working with transformations or destinations.</span></span> <span data-ttu-id="b671d-138">Per altre informazioni, vedere [Trasformazioni di Integration Services](transformations/integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="b671d-138">For more information, see [Integration Services Transformations](transformations/integration-services-transformations.md).</span></span>  
  
    -   <span data-ttu-id="b671d-139">Fare clic sulla scheda **Proprietà input e output** per visualizzare e modificare le proprietà degli input, degli output e degli output degli errori, nonché le proprietà delle colonne che contengono.</span><span class="sxs-lookup"><span data-stu-id="b671d-139">To view and modify the properties of inputs, outputs, and error outputs, and the properties of the columns they contain, click the **Input and Output Properties** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="b671d-140">Le origini non includono input,</span><span class="sxs-lookup"><span data-stu-id="b671d-140">Sources have no inputs.</span></span> <span data-ttu-id="b671d-141">mentre le destinazioni non includono output, ad eccezione di un output degli errori facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b671d-141">Destinations have no outputs, except for an optional error output.</span></span>  
  
6.  <span data-ttu-id="b671d-142">Visualizzare o modificare i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="b671d-142">View or modify the property values.</span></span>  
  
7.  <span data-ttu-id="b671d-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b671d-143">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="b671d-144">Per salvare il pacchetto aggiornato, dal menu **File** scegliere **Salva elementi selezionati**.</span><span class="sxs-lookup"><span data-stu-id="b671d-144">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b671d-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b671d-145">See Also</span></span>  
 [<span data-ttu-id="b671d-146">Trasformazioni di Integration Services</span><span class="sxs-lookup"><span data-stu-id="b671d-146">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
