---
title: Configurare la trasformazione comando OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parameters [Integration Services]
- OLE DB Command transformation
ms.assetid: c800f167-3d2e-4c10-8ba3-a02f1872ccea
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d1714a6b798c6d8256052fd3c16bd86182480bcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722984"
---
# <a name="configure-the-ole-db-command-transformation"></a><span data-ttu-id="e3155-102">Configurazione della trasformazione Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="e3155-102">Configure the OLE DB Command Transformation</span></span>
  <span data-ttu-id="e3155-103">È possibile aggiungere e configurare una trasformazione Comando OLE DB solo se il pacchetto include almeno un'attività Flusso di dati e un'origine, quale un'origine file flat o un'origine OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e3155-103">To add and configure an OLE DB Command transformation, the package must already include at least one Data Flow task and a source such as a Flat File source or an OLE DB source.</span></span> <span data-ttu-id="e3155-104">Questa trasformazione viene in genere utilizzata per l'esecuzione di query con parametri.</span><span class="sxs-lookup"><span data-stu-id="e3155-104">This transformation is typically used for running parameterized queries.</span></span>  
  
### <a name="to-configure-the-ole-db-command-transformation"></a><span data-ttu-id="e3155-105">Per configurare la trasformazione Comando OLE DB</span><span class="sxs-lookup"><span data-stu-id="e3155-105">To configure the OLE DB Command transformation</span></span>  
  
1.  <span data-ttu-id="e3155-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]aprire il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che contiene il pacchetto desiderato.</span><span class="sxs-lookup"><span data-stu-id="e3155-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="e3155-107">In Esplora soluzioni fare doppio clic sul pacchetto per aprirlo.</span><span class="sxs-lookup"><span data-stu-id="e3155-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="e3155-108">Fare clic sulla scheda **Flusso di dati** e quindi, dalla **casella degli strumenti**trascinare la trasformazione Comando OLE DB sull'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e3155-108">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the OLE DB Command transformation to the design surface.</span></span>  
  
4.  <span data-ttu-id="e3155-109">Connettere la trasformazione Comando OLE DB al flusso di dati trascinando un connettore, la freccia verde o la freccia rossa, da un'origine dei dati o una trasformazione precedente alla trasformazione Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e3155-109">Connect the OLE DB Command transformation to the data flow by dragging a connector-the green or red arrow-from a data source or a previous transformation to the OLE DB Command transformation.</span></span>  
  
5.  <span data-ttu-id="e3155-110">Fare clic con il pulsante destro del mouse sul componente e scegliere Modifica o **Visualizza editor avanzato**.</span><span class="sxs-lookup"><span data-stu-id="e3155-110">Right-click the component and select Edit or Show **Advanced Editor**.</span></span>  
  
6.  <span data-ttu-id="e3155-111">Nella scheda **Gestioni connessioni** selezionare una gestione connessione OLE DB dall'elenco **Gestione connessione** .</span><span class="sxs-lookup"><span data-stu-id="e3155-111">On the **Connection Managers** tab, select an OLE DB connection manager in the **Connection Manager** list.</span></span> <span data-ttu-id="e3155-112">Per altre informazioni, vedere [Gestione connessione OLE DB](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e3155-112">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
7.  <span data-ttu-id="e3155-113">Fare clic sulla scheda **Proprietà componente** e quindi sul pulsante con i puntini di sospensione **(...)** nella casella **SqlCommand** .</span><span class="sxs-lookup"><span data-stu-id="e3155-113">Click the **Component Properties** tab and click the ellipsis button **(...)** in the **SqlCommand** box.</span></span>  
  
8.  <span data-ttu-id="e3155-114">In **Editor valore stringa**digitare l'istruzione SQL con parametri usando un punto interrogativo (?) come indicatore per ogni parametro.</span><span class="sxs-lookup"><span data-stu-id="e3155-114">In the **String Value Editor**, type the parameterized SQL statement using a question mark (?) as the parameter marker for each parameter.</span></span>  
  
9. <span data-ttu-id="e3155-115">Fare clic su **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="e3155-115">Click **Refresh**.</span></span> <span data-ttu-id="e3155-116">Quando si fa clic su **Aggiorna**la trasformazione crea una colonna per ogni parametro nella raccolta Colonne esterne e imposta la proprietà DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="e3155-116">When you click **Refresh**, the transformation creates a column for each parameter in the External Columns collection and sets the DBParamInfoFlags property.</span></span>  
  
10. <span data-ttu-id="e3155-117">Fare clic sulla scheda **Proprietà input e output** .</span><span class="sxs-lookup"><span data-stu-id="e3155-117">Click the **Input and Output Properties** tab.</span></span>  
  
11. <span data-ttu-id="e3155-118">Espandere **Input comando OLE DB**e quindi **Colonne esterne**.</span><span class="sxs-lookup"><span data-stu-id="e3155-118">Expand **OLE DB Command Input**, and then expand **External Columns**.</span></span>  
  
12. <span data-ttu-id="e3155-119">Verificare che in **Colonne esterne** sia elencata una colonna per ogni parametro nell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="e3155-119">Verify that **External Columns** lists a column for each parameter in the SQL statement.</span></span> <span data-ttu-id="e3155-120">I nomi delle colonne sono **Param_0**, **Param_1**e così via.</span><span class="sxs-lookup"><span data-stu-id="e3155-120">The column names are **Param_0**, **Param_1**, and so on.</span></span>  
  
     <span data-ttu-id="e3155-121">Tali nomi non devono essere modificati.</span><span class="sxs-lookup"><span data-stu-id="e3155-121">You should not change the column names.</span></span> <span data-ttu-id="e3155-122">Se si modificano i nomi della colonna, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] genera un errore di convalida per la trasformazione Comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e3155-122">If you change the column names, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a validation error for the OLE DB Command transformation.</span></span>  
  
     <span data-ttu-id="e3155-123">Inoltre, non modificare il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e3155-123">Also, you should not change the data type.</span></span> <span data-ttu-id="e3155-124">La proprietà DataType di ogni colonna viene impostata sul tipo di dati corretto.</span><span class="sxs-lookup"><span data-stu-id="e3155-124">The DataType property of each column is set to the correct data type.</span></span>  
  
13. <span data-ttu-id="e3155-125">Se in **Colonne esterne** non è elencata alcuna colonna, sarà necessario aggiungerle manualmente.</span><span class="sxs-lookup"><span data-stu-id="e3155-125">If **External Columns** lists no columns you must add them manually.</span></span>  
  
    -   <span data-ttu-id="e3155-126">Fare clic su **Aggiungi colonna** una volta per ogni parametro nell'istruzione SQL.</span><span class="sxs-lookup"><span data-stu-id="e3155-126">Click **Add Column** one time for each parameter in the SQL statement.</span></span>  
  
    -   <span data-ttu-id="e3155-127">Modificare i nomi delle colonne in **Param_0**, **Param_1**e così via.</span><span class="sxs-lookup"><span data-stu-id="e3155-127">Update the column names to **Param_0**, **Param_1**, and so on.</span></span>  
  
    -   <span data-ttu-id="e3155-128">Specificare un valore nella proprietà DBParamInfoFlags.</span><span class="sxs-lookup"><span data-stu-id="e3155-128">Specify a value in the DBParamInfoFlags property.</span></span> <span data-ttu-id="e3155-129">Tale valore deve corrispondere a un valore dell'enumerazione OLE DB DBPARAMFLAGSENUM.</span><span class="sxs-lookup"><span data-stu-id="e3155-129">The value must match a value in the OLE DB DBPARAMFLAGSENUM enumeration.</span></span> <span data-ttu-id="e3155-130">Per ulteriori informazioni, vedere la documentazione di riferimento di OLE DB.</span><span class="sxs-lookup"><span data-stu-id="e3155-130">For more information, see the OLE DB reference documentation.</span></span>  
  
    -   <span data-ttu-id="e3155-131">Specificare il tipo di dati della colonna e, a seconda del tipo di dati, specificarne anche la tabella codici, la lunghezza, la precisione e la scala.</span><span class="sxs-lookup"><span data-stu-id="e3155-131">Specify the data type of the column and, depending on the data type, specify the code page, length, precision, and scale of the column.</span></span>  
  
    -   <span data-ttu-id="e3155-132">Per eliminare un parametro non usato, selezionarlo in **Colonne esterne**e fare clic su **Rimuovi colonna**.</span><span class="sxs-lookup"><span data-stu-id="e3155-132">To delete an unused parameter, select the parameter in **External Columns**, and then click **Remove Column**.</span></span>  
  
    -   <span data-ttu-id="e3155-133">Fare clic su **Mapping colonne** ed eseguire il mapping delle colonne nell'elenco **Colonne di input disponibili** ai parametri nell'elenco **Colonne di destinazione disponibili** .</span><span class="sxs-lookup"><span data-stu-id="e3155-133">Click **Column Mappings** and map columns in the **Available Input Columns** list to parameters in the **Available Destination Columns** list.</span></span>  
  
14. <span data-ttu-id="e3155-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3155-134">Click **OK**.</span></span>  
  
15. <span data-ttu-id="e3155-135">Per salvare il pacchetto aggiornato, scegliere **Salva** dal menu **File** .</span><span class="sxs-lookup"><span data-stu-id="e3155-135">To save the updated package, click **Save** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3155-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3155-136">See Also</span></span>  
 <span data-ttu-id="e3155-137">[Trasformazione comando OLE DB](data-flow/transformations/ole-db-command-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="e3155-137">[OLE DB Command Transformation](data-flow/transformations/ole-db-command-transformation.md) </span></span>  
 <span data-ttu-id="e3155-138">[Trasformazioni di Integration Services](data-flow/transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="e3155-138">[Integration Services Transformations](data-flow/transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="e3155-139">[Percorsi in Integration Services](data-flow/integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="e3155-139">[Integration Services Paths](data-flow/integration-services-paths.md) </span></span>  
 [<span data-ttu-id="e3155-140">Attività Flusso di dati</span><span class="sxs-lookup"><span data-stu-id="e3155-140">Data Flow Task</span></span>](control-flow/data-flow-task.md)  
  
  
