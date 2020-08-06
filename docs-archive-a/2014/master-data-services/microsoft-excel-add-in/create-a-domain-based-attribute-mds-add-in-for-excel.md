---
title: Creare un attributo basato su dominio (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 7b3e30dc-8f41-4a5d-8009-ae5a4426a64b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: bda0c7f63ad380aaea5d980d2e729822ec9a3d22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623379"
---
# <a name="create-a-domain-based-attribute-mds-add-in-for-excel"></a><span data-ttu-id="34183-102">Creare un attributo basato su dominio (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="34183-102">Create a Domain-based Attribute (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="34183-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]gli amministratori possono creare un attributo basato su dominio per vincolare i valori in una colonna a un set di valori specifico.</span><span class="sxs-lookup"><span data-stu-id="34183-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], administrators can create a domain-based attribute when they want to constrain the values in a column to a specific set of values.</span></span>  
  
 <span data-ttu-id="34183-104">I valori possono essere già presenti nel foglio di lavoro oppure possono derivare da un'entità esistente.</span><span class="sxs-lookup"><span data-stu-id="34183-104">The values can already be in the worksheet or they can come from an existing entity.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="34183-105">Se gli utenti digitano un valore nella colonna vincolata, anziché selezionarlo nell'elenco, gli errori vengono visualizzati nella colonna **$InputStatus$** al momento della pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="34183-105">If users type a value in the constrained column, rather than selecting from the list, errors are displayed in the **$InputStatus$** column when they publish.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34183-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="34183-106">Prerequisites</span></span>  
 <span data-ttu-id="34183-107">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="34183-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="34183-108">È necessario disporre dell'autorizzazione di accesso alle aree funzionali **Amministrazione sistema** e **Visualizzatore** .</span><span class="sxs-lookup"><span data-stu-id="34183-108">You must have permission to access the **System Administration** and **Explorer** functional areas.</span></span>  
  
-   <span data-ttu-id="34183-109">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="34183-109">You must be a model administrator.</span></span> <span data-ttu-id="34183-110">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="34183-110">For more information, see [Administrators &#40;Master Data Services&#41;](../administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="34183-111">Il modello e l'entità devono esistere già.</span><span class="sxs-lookup"><span data-stu-id="34183-111">The model and entity must already exist.</span></span>  
  
### <a name="to-perform-this-procedure"></a><span data-ttu-id="34183-112">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="34183-112">To perform this procedure:</span></span>  
  
1.  <span data-ttu-id="34183-113">In Excel caricare l'entità contenente la colonna (attributo) che si desiderare vincolare.</span><span class="sxs-lookup"><span data-stu-id="34183-113">In Excel, load the entity that contains the column (attribute) you want to constrain.</span></span> <span data-ttu-id="34183-114">Per altre informazioni, vedere [caricare i dati da MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="34183-114">For more information, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
2.  <span data-ttu-id="34183-115">Fare clic su una cella nella colonna che si desidera vincolare.</span><span class="sxs-lookup"><span data-stu-id="34183-115">Click any cell in the column you want to constrain.</span></span>  
  
3.  <span data-ttu-id="34183-116">Nel gruppo **Compila modello** fare clic su **Proprietà attributi**.</span><span class="sxs-lookup"><span data-stu-id="34183-116">In the **Build Model** group, click **Attribute Properties**.</span></span>  
  
4.  <span data-ttu-id="34183-117">Nella finestra di dialogo **Proprietà attributi** scegliere **Elenco vincolato (basato su dominio)** nell'elenco **Tipo di attributo**.</span><span class="sxs-lookup"><span data-stu-id="34183-117">In the **Attribute Properties** dialog box, in the **Attribute type** list, choose **Constrained list (domain-based)**.</span></span>  
  
5.  <span data-ttu-id="34183-118">Nell'elenco **Popola l'attributo con valori di** :</span><span class="sxs-lookup"><span data-stu-id="34183-118">In the **Populate the attribute with values from** list:</span></span>  
  
    -   <span data-ttu-id="34183-119">Per usare valori del foglio di lavoro, scegliere **colonna selezionata**.</span><span class="sxs-lookup"><span data-stu-id="34183-119">To use values from the worksheet, choose **the selected column**.</span></span> <span data-ttu-id="34183-120">Verranno create una nuova entità e una nuova tabella di staging con i valori dalla colonna selezionata.</span><span class="sxs-lookup"><span data-stu-id="34183-120">A new entity and new staging table will be created with the values from the selected column.</span></span>  
  
    -   <span data-ttu-id="34183-121">Per utilizzare valori di un'entità esistente, scegliere il nome dell'entità.</span><span class="sxs-lookup"><span data-stu-id="34183-121">To use values from an existing entity, choose the name of the entity.</span></span>  
  
6.  <span data-ttu-id="34183-122">Se si sceglie **colonna selezionata** nel passaggio precedente, nella casella **Nome nuova entità** digitare un nome per la nuova entità.</span><span class="sxs-lookup"><span data-stu-id="34183-122">If you chose **the selected column** in the previous step, in the **New entity name** box, type a name for the new entity.</span></span> <span data-ttu-id="34183-123">Il nome può corrispondere a quello della colonna (attributo).</span><span class="sxs-lookup"><span data-stu-id="34183-123">This can be the same as the column (attribute) name.</span></span>  
  
7.  <span data-ttu-id="34183-124">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="34183-124">Click **OK**.</span></span> <span data-ttu-id="34183-125">In ogni cella nella colonna è ora presente un elenco di valori tra cui gli utenti possono scegliere.</span><span class="sxs-lookup"><span data-stu-id="34183-125">Each cell in the column now has a list of values for users to choose from.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="34183-126">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="34183-126">Next Steps</span></span>  
  
-   <span data-ttu-id="34183-127">Per aggiungere ed eliminare valori nell'elenco vincolato, caricare l'entità su cui l'attributo è basato.</span><span class="sxs-lookup"><span data-stu-id="34183-127">To add and delete values in the constrained list, load the entity that the attribute is based on.</span></span> <span data-ttu-id="34183-128">Per altre informazioni sul caricamento di entità, vedere [caricare i dati da MDS in Excel](export-data-to-excel-from-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="34183-128">For more information on loading entities, see [Load Data from MDS into Excel](export-data-to-excel-from-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34183-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34183-129">See Also</span></span>  
 <span data-ttu-id="34183-130">[Attributi basati su dominio &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="34183-130">[Domain-Based Attributes &#40;Master Data Services&#41;](../domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="34183-131">[Creare un'entità &#40;Componente aggiuntivo MDS per Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span><span class="sxs-lookup"><span data-stu-id="34183-131">[Create an Entity &#40;MDS Add-in for Excel&#41;](create-an-entity-mds-add-in-for-excel.md) </span></span>  
 [<span data-ttu-id="34183-132">Compilazione di un modello &#40;componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="34183-132">Building a Model &#40;MDS Add-in for Excel&#41;</span></span>](building-a-model-mds-add-in-for-excel.md)  
  
  
