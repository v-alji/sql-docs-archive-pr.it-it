---
title: Creare un'entità (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: d354abb3-88fe-4b40-a374-f6256b84ffae
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 87ad67f7347da87c67afc11590df6775af4cf3d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623377"
---
# <a name="create-an-entity-mds-add-in-for-excel"></a><span data-ttu-id="8d189-102">Creare un'entità (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="8d189-102">Create an Entity (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8d189-103">Nel [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], gli amministratori possono creare nuove entità per archiviare i dati.</span><span class="sxs-lookup"><span data-stu-id="8d189-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create new entities to store data.</span></span> <span data-ttu-id="8d189-104">Quando si crea un'entità, è necessario caricare almeno un campionamento dei dati che si desidera archiviare.</span><span class="sxs-lookup"><span data-stu-id="8d189-104">When you create an entity you should load at least a sampling of the data you want to store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8d189-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8d189-105">Prerequisites</span></span>  
 <span data-ttu-id="8d189-106">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="8d189-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8d189-107">È necessario disporre dell'autorizzazione di accesso alle aree funzionali **Amministrazione sistema** e **Visualizzatore** .</span><span class="sxs-lookup"><span data-stu-id="8d189-107">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="8d189-108">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="8d189-108">You must be a model administrator.</span></span> <span data-ttu-id="8d189-109">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8d189-109">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="8d189-110">È necessario disporre di un modello esistente in cui creare l'entità.</span><span class="sxs-lookup"><span data-stu-id="8d189-110">You must have an existing model to create the entity in.</span></span> <span data-ttu-id="8d189-111">Per altre informazioni, vedere [Creare un modello &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8d189-111">For more information, see [Create a Model &#40;Master Data Services&#41;](../create-a-model-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="8d189-112">Verificare che i dati soddisfino i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="8d189-112">Ensure that your data meets the following requirements:</span></span>  
  
    -   <span data-ttu-id="8d189-113">Nei dati deve essere presente una riga di intestazione.</span><span class="sxs-lookup"><span data-stu-id="8d189-113">The data should have a header row.</span></span>  
  
    -   <span data-ttu-id="8d189-114">È utile disporre delle colonne **Nome** e **Codice** .</span><span class="sxs-lookup"><span data-stu-id="8d189-114">It is helpful to have **Name** and **Code** columns.</span></span> <span data-ttu-id="8d189-115">**Codice** è un identificatore univoco per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="8d189-115">**Code** is a unique identifier for each row.</span></span>  
  
    -   <span data-ttu-id="8d189-116">Deve essere presente almeno una riga di dati diversa dall'intestazione.</span><span class="sxs-lookup"><span data-stu-id="8d189-116">You should have at least one row of data other than the header.</span></span> <span data-ttu-id="8d189-117">Non è necessario che siano presenti valori in tutte le colonne, ma i dati devono essere rappresentativi di quelli che saranno presenti nell'entità.</span><span class="sxs-lookup"><span data-stu-id="8d189-117">All columns do not need values, but the data should be representative of the data that will be in the entity.</span></span>  
  
    -   <span data-ttu-id="8d189-118">Se è presente una colonna contenente un identificatore univoco (noto in MDS come **Codice**), assicurarsi che i valori siano univoci.</span><span class="sxs-lookup"><span data-stu-id="8d189-118">If you have a column that contains a unique identifier (known in MDS as **Code**), ensure that the values are unique.</span></span> <span data-ttu-id="8d189-119">Se nessuna colonna contiene identificatori, è possibile generarli automaticamente quando si crea l'entità.</span><span class="sxs-lookup"><span data-stu-id="8d189-119">If no column contains identifiers, you can have them generated automatically when you create the entity.</span></span>  
  
    -   <span data-ttu-id="8d189-120">Verificare che nessuna cella contenga formule.</span><span class="sxs-lookup"><span data-stu-id="8d189-120">Ensure that no cells contain formulas.</span></span>  
  
    -   <span data-ttu-id="8d189-121">Verificare che nessuna cella contenga valori relativi all'ora.</span><span class="sxs-lookup"><span data-stu-id="8d189-121">Ensure that no cells contain time values.</span></span> <span data-ttu-id="8d189-122">In MDS è possibile salvare i valori relativi alla data ma non quelli relativi all'ora.</span><span class="sxs-lookup"><span data-stu-id="8d189-122">Date values can be saved in MDS but time values cannot.</span></span>  
  
### <a name="to-create-an-entity-and-load-data"></a><span data-ttu-id="8d189-123">Per creare un'entità e caricare i dati</span><span class="sxs-lookup"><span data-stu-id="8d189-123">To create an entity and load data</span></span>  
  
1.  <span data-ttu-id="8d189-124">Aprire o creare un foglio di lavoro di Excel contenente i dati che si desidera caricare.</span><span class="sxs-lookup"><span data-stu-id="8d189-124">Open or create an Excel worksheet that contains data you want to load.</span></span>  
  
2.  <span data-ttu-id="8d189-125">Selezionare le celle che si desidera caricare nella nuova entità.</span><span class="sxs-lookup"><span data-stu-id="8d189-125">Select the cells you want to load into the new entity.</span></span>  
  
3.  <span data-ttu-id="8d189-126">Nel gruppo **Compila modello** della scheda **Dati master** fare clic su **Crea entità**.</span><span class="sxs-lookup"><span data-stu-id="8d189-126">On the **Master Data** tab, in the **Build Model** group, click **Create Entity**.</span></span>  
  
4.  <span data-ttu-id="8d189-127">Se viene richiesto di connettersi a un repository MDS, effettuare la connessione.</span><span class="sxs-lookup"><span data-stu-id="8d189-127">If you are prompted to connect to an MDS repository, connect.</span></span>  
  
5.  <span data-ttu-id="8d189-128">Nella finestra di dialogo **Crea entità** lasciare l'intervallo predefinito oppure modificarlo in base ai dati che si vuole caricare.</span><span class="sxs-lookup"><span data-stu-id="8d189-128">In the **Create Entity** dialog box, leave the default range or change it to apply to the data you want to load.</span></span>  
  
6.  <span data-ttu-id="8d189-129">Non deselezionare la casella di controllo **Dati con intestazioni** .</span><span class="sxs-lookup"><span data-stu-id="8d189-129">Do not clear the **My data has headers** check box.</span></span>  
  
7.  <span data-ttu-id="8d189-130">Selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="8d189-130">From the **Model** list, select a model.</span></span>  
  
8.  <span data-ttu-id="8d189-131">Selezionare una versione dall'elenco **Versione** .</span><span class="sxs-lookup"><span data-stu-id="8d189-131">From the **Version** list, select a version.</span></span>  
  
9. <span data-ttu-id="8d189-132">Nella casella **Nome nuova entità** digitare un nome per l'entità.</span><span class="sxs-lookup"><span data-stu-id="8d189-132">In the **New entity name** box, type a name for the entity.</span></span>  
  
10. <span data-ttu-id="8d189-133">Nell'elenco **Codice** selezionare la colonna contenente identificatori univoci o codici generatati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8d189-133">From the **Code** list, select the column that contains unique identifiers or have codes generated automatically.</span></span>  
  
11. <span data-ttu-id="8d189-134">facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8d189-134">Optional.</span></span> <span data-ttu-id="8d189-135">Nell'elenco **Nome** selezionare una colonna contenente i nomi per ogni membro.</span><span class="sxs-lookup"><span data-stu-id="8d189-135">From the **Name** list, select a column that contains names for each member.</span></span>  
  
12. <span data-ttu-id="8d189-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8d189-136">Click **OK**.</span></span> <span data-ttu-id="8d189-137">Dopo che l'entità è stata creata, viene visualizzata una nuova riga di intestazione, le celle vengono evidenziate e il nome del foglio viene aggiornato in base al nome dell'entità.</span><span class="sxs-lookup"><span data-stu-id="8d189-137">When the entity has been created successfully, a new header row is displayed, the cells are highlighted, and the sheet name is updated to match the entity name.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8d189-138">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8d189-138">Next Steps</span></span>  
  
-   <span data-ttu-id="8d189-139">Per visualizzare gli errori che si sono verificati, fare clic su **Mostra stato** nel gruppo **Pubblica e convalida**.</span><span class="sxs-lookup"><span data-stu-id="8d189-139">To view errors that occurred, in the **Publish and Validate** group, click **Show Status**.</span></span> <span data-ttu-id="8d189-140">Verranno visualizzate le colonne ValidationStatus e InputStatus.</span><span class="sxs-lookup"><span data-stu-id="8d189-140">ValidationStatus and InputStatus columns are displayed.</span></span> <span data-ttu-id="8d189-141">Per altre informazioni, vedere [Convalida dei dati &#40;componente aggiuntivo MDS per Excel&#41;](validating-data-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="8d189-141">For more information, see [Validating Data &#40;MDS Add-in for Excel&#41;](validating-data-mds-add-in-for-excel.md).</span></span>  
  
-   <span data-ttu-id="8d189-142">Verificare che gli attributi siano stati creati con il tipo di dati previsto.</span><span class="sxs-lookup"><span data-stu-id="8d189-142">Confirm that the attributes were created as the data type you expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d189-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d189-143">See Also</span></span>  
 [<span data-ttu-id="8d189-144">Creare un attributo basato su dominio &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8d189-144">Create a Domain-based Attribute &#40;MDS Add-in for Excel&#41;</span></span>](create-a-domain-based-attribute-mds-add-in-for-excel.md)  
  
  
