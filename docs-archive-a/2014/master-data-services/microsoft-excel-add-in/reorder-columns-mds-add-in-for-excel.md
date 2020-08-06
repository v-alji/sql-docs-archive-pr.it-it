---
title: Riordinare le colonne (componente aggiuntivo MDS per Excel) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: ac00462e-c0f7-4b8d-86f2-d9eda2598a15
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f0c47a631ffe699936a8d45bcc4e47e0b6f0a985
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714471"
---
# <a name="reorder-columns-mds-add-in-for-excel"></a><span data-ttu-id="9708c-102">Riordinare le colonne (componente aggiuntivo MDS per Excel)</span><span class="sxs-lookup"><span data-stu-id="9708c-102">Reorder Columns (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="9708c-103">In [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]è possibile riordinare le colonne filtrando l'elenco prima del caricamento.</span><span class="sxs-lookup"><span data-stu-id="9708c-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], you can reorder columns by filtering the list before loading.</span></span>  
  
 <span data-ttu-id="9708c-104">Quando si riordinano gli attributi nella finestra di dialogo **Filtro** , i dati vengono caricati in Excel con il nuovo ordine.</span><span class="sxs-lookup"><span data-stu-id="9708c-104">When you reorder attributes in the **Filter** dialog box, the data is loaded into Excel with the new order.</span></span> <span data-ttu-id="9708c-105">Tuttavia, quando si filtrano i dati dell'attributo la volta successiva, verrà ripristinato l'ordine della progettazione originale.</span><span class="sxs-lookup"><span data-stu-id="9708c-105">However, the next time that you filter the attribute data, the order will revert to the order in the original design.</span></span> <span data-ttu-id="9708c-106">Per modificare l'ordine in modo permanente, è consigliabile che un amministratore modifichi l'ordine nell'area **Amministrazione sistema** di Gestione dati master.</span><span class="sxs-lookup"><span data-stu-id="9708c-106">To change the order permanently, an administrator should change the order in the **System Administration** area of Master Data Manager.</span></span> <span data-ttu-id="9708c-107">Per altre informazioni, vedere [Change the Order of Attributes](../change-the-order-of-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="9708c-107">For more information, see [Change the Order of Attributes](../change-the-order-of-attributes.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9708c-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="9708c-108">Prerequisites</span></span>  
 <span data-ttu-id="9708c-109">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="9708c-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="9708c-110">È necessario disporre dell'autorizzazione per accedere all'area funzionale **Esplora** .</span><span class="sxs-lookup"><span data-stu-id="9708c-110">You must have permission to access the **Explorer** functional area.</span></span>  
  
### <a name="to-reorder-mds-managed-columns"></a><span data-ttu-id="9708c-111">Per riordinare le colonne gestite da MDS</span><span class="sxs-lookup"><span data-stu-id="9708c-111">To reorder MDS-managed columns</span></span>  
  
1.  <span data-ttu-id="9708c-112">Aprire Excel e nella scheda **Dati master** connettersi a un repository MDS.</span><span class="sxs-lookup"><span data-stu-id="9708c-112">Open Excel and on the **Master Data** tab, connect to an MDS repository.</span></span> <span data-ttu-id="9708c-113">Per altre informazioni, vedere [Connettersi a un repository MDS &#40;componente aggiuntivo MDS per Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="9708c-113">For more information, see [Connect to an MDS Repository &#40;MDS Add-in for Excel&#41;](connect-to-an-mds-repository-mds-add-in-for-excel.md).</span></span>  
  
2.  <span data-ttu-id="9708c-114">Nel riquadro **Esplora dati master** selezionare un modello e una versione.</span><span class="sxs-lookup"><span data-stu-id="9708c-114">In the **Master Data Explorer** pane, select a model and version.</span></span> <span data-ttu-id="9708c-115">L'elenco di entità viene popolato.</span><span class="sxs-lookup"><span data-stu-id="9708c-115">The list of entities is populated.</span></span>  
  
    -   <span data-ttu-id="9708c-116">Se il riquadro **Esplora dati master** non è visibile, nel gruppo **Connetti e carica** fare clic su **Esplora dati master**.</span><span class="sxs-lookup"><span data-stu-id="9708c-116">If the **Master Data Explorer** pane is not visible, in the **Connect and Load** group, click **Show Explorer**.</span></span>  
  
    -   <span data-ttu-id="9708c-117">Se il riquadro **Esplora dati master** è disabilitato, significa che il foglio esistente contiene già i dati gestiti da MDS.</span><span class="sxs-lookup"><span data-stu-id="9708c-117">If the **Master Data Explorer** pane is disabled, it is because the existing sheet already contains MDS-managed data.</span></span> <span data-ttu-id="9708c-118">Per abilitare il riquadro, aprire un nuovo foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9708c-118">To enable the pane, open a new worksheet.</span></span>  
  
3.  <span data-ttu-id="9708c-119">Nel riquadro **Esplora dati master** , fare clic su un'entità.</span><span class="sxs-lookup"><span data-stu-id="9708c-119">In the **Master Data Explorer** pane, click an entity.</span></span>  
  
4.  <span data-ttu-id="9708c-120">Nel gruppo **Connetti e carica** fare clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="9708c-120">In the **Connect and Load** group, click **Filter**.</span></span>  
  
5.  <span data-ttu-id="9708c-121">Nella finestra di dialogo **Filtro** , nella sezione **Colonne** , nell'elenco di attributi fare clic sull'attributo che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="9708c-121">In the **Filter** dialog box, in the **Columns** section, in the list of attributes, click the attribute you want to move.</span></span>  
  
6.  <span data-ttu-id="9708c-122">A destra dell'elenco, fare clic sulla freccia **SU** o **GIÙ** per spostare l'attributo a sinistra o a destra nel foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9708c-122">To the right of the list, click the **Up** or **Down** arrow to move the attribute left and right in the worksheet.</span></span>  
  
7.  <span data-ttu-id="9708c-123">Ripetere il passaggio 7 per ogni attributo fino a che l'ordine dall'alto in basso rappresenta l'ordine da sinistra a destra che si desidera nel foglio di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9708c-123">Repeat step 7 for each attribute until the top-to-bottom order represents the left-to-right order you want in the worksheet.</span></span>  
  
8.  <span data-ttu-id="9708c-124">Fare clic su **Carica dati**.</span><span class="sxs-lookup"><span data-stu-id="9708c-124">Click **Load Data**.</span></span> <span data-ttu-id="9708c-125">Il foglio viene popolato con dati gestiti da MDS e le colonne vengono visualizzate nell'ordine specificato.</span><span class="sxs-lookup"><span data-stu-id="9708c-125">The sheet is populated with MDS-managed data and the columns are displayed in the order you specified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9708c-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9708c-126">See Also</span></span>  
 [<span data-ttu-id="9708c-127">Caricamento dei dati &#40;Componente aggiuntivo MDS per Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="9708c-127">Loading Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-exporting-data-to-excel-mds-add-in-for-excel.md)  
  
  
