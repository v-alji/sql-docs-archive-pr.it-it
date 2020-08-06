---
title: Creazione di una dimensione tramite la creazione guidata dimensione | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], creating
ms.assetid: d84f66ae-7551-49bf-99d0-88368ca2dd0e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ec38dc7170b915dce0cedea60c93385560e11f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721932"
---
# <a name="create-a-dimension-using-the-dimension-wizard"></a><span data-ttu-id="a9198-102">Creare una dimensione utilizzando la Creazione guidata dimensione</span><span class="sxs-lookup"><span data-stu-id="a9198-102">Create a Dimension Using the Dimension Wizard</span></span>
  <span data-ttu-id="a9198-103">È possibile creare una nuova dimensione utilizzando Creazione guidata dimensione in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9198-103">You can create a new dimension by using the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-dimension"></a><span data-ttu-id="a9198-104">Per creare una nuova dimensione</span><span class="sxs-lookup"><span data-stu-id="a9198-104">To create a new dimension</span></span>  
  
1.  <span data-ttu-id="a9198-105">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su **dimensioni**, quindi scegliere **nuova dimensione**.</span><span class="sxs-lookup"><span data-stu-id="a9198-105">In **Solution Explorer**, right-click **Dimensions**, and then click **New Dimension**.</span></span>  
  
2.  <span data-ttu-id="a9198-106">Nella pagina **Selezione metodo di creazione** della Creazione guidata dimensione selezionare **Utilizza una tabella esistente**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9198-106">On the **Select Creation Method** page of the Dimension Wizard, select **Use an existing table**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9198-107">Si potrebbe dovere creare occasionalmente una dimensione senza utilizzare una tabella esistente.</span><span class="sxs-lookup"><span data-stu-id="a9198-107">You might occasionally have to create a dimension without using an existing table.</span></span> <span data-ttu-id="a9198-108">Per altre informazioni, vedere [Creare una dimensione generando una tabella non temporale nell'origine dati](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) e [Creare una dimensione temporale generando una tabella dei tempi](create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="a9198-108">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) and [Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
3.  <span data-ttu-id="a9198-109">Nella pagina **Impostazione informazioni origine** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9198-109">On the **Specify Source Information** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="a9198-110">Nell'elenco **Vista origine dati** selezionare una vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="a9198-110">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="a9198-111">Nell'elenco **Tabella principale** selezionare la tabella delle dimensioni principale.</span><span class="sxs-lookup"><span data-stu-id="a9198-111">In the **Main table** list, select the main dimension table.</span></span>  
  
    3.  <span data-ttu-id="a9198-112">Nell'elenco **Colonne chiave** esaminare le colonne chiave selezionate automaticamente dalla procedura guidata in base alla chiave primaria definita nella tabella delle dimensioni principale.</span><span class="sxs-lookup"><span data-stu-id="a9198-112">In the **Key columns** list, review the key columns that the wizard has automatically selected based on the primary key that is defined in the main dimension table.</span></span> <span data-ttu-id="a9198-113">Per modificare questa impostazione predefinita, specificare le colonne chiave che collegano la tabella della dimensione alla tabella dei fatti.</span><span class="sxs-lookup"><span data-stu-id="a9198-113">To change this default setting, specify the key columns that link the dimension table to the fact table.</span></span>  
  
    4.  <span data-ttu-id="a9198-114">Nell'elenco a discesa **Colonna nome** esaminare la colonna del nome selezionata automaticamente dalla procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a9198-114">In the **Name column** drop-down list, review the name column that the wizard has automatically selected.</span></span>  
  
         <span data-ttu-id="a9198-115">Questo nome predefinito è adatto quando la colonna contiene informazioni descrittive.</span><span class="sxs-lookup"><span data-stu-id="a9198-115">This default name is appropriate when the column contains descriptive information.</span></span> <span data-ttu-id="a9198-116">Tuttavia, è possibile specificare un nome che contenga valori più significativi per l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="a9198-116">However, you might want to specify a name that contains values that are more meaningful for the end user.</span></span> <span data-ttu-id="a9198-117">Ad esempio, se un attributo della categoria di prodotto in una dimensione Prodotti usa la colonna **ProductCategoryKey** come colonna chiave, è possibile specificare la colonna **ProductCategoryName** come colonna del nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a9198-117">For example, if a product category attribute in a Products dimension uses the **ProductCategoryKey** column as its key column, you can specify the **ProductCategoryName** column as its name column.</span></span>  
  
         <span data-ttu-id="a9198-118">Se l'elenco **Colonne chiave** contiene più colonne chiave, è necessario specificare una colonna del nome che fornisce i valori del membro per l'attributo chiave.</span><span class="sxs-lookup"><span data-stu-id="a9198-118">If the **Key columns** list contains multiple key columns, you must specify a name column that provides the member values for the key attribute.</span></span> <span data-ttu-id="a9198-119">A questo scopo, è possibile creare un calcolo denominato nella vista origine dati e utilizzarlo come colonna del nome.</span><span class="sxs-lookup"><span data-stu-id="a9198-119">To do this, you can create a named calculation in the data source view and use that as the name column.</span></span>  
  
    5.  <span data-ttu-id="a9198-120">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9198-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="a9198-121">Nella pagina **Selezione tabelle correlate** selezionare le tabelle correlate che si vuole includere nella dimensione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9198-121">On the **Select Related Tables** page, select the related tables that you want to include in your dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9198-122">La pagina **Selezione tabelle correlate** è visualizzata se la tabella delle dimensioni principale specificata ha relazioni con altre tabelle delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a9198-122">The **Select Related Tables** page appears if the main dimension table that you specified has relationships to other dimension tables.</span></span>  
  
5.  <span data-ttu-id="a9198-123">Nella pagina **Selezione attributi dimensione** selezionare gli attributi che si vuole includere nella dimensione e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9198-123">On the **Select Dimension Attributes** page, select the attributes that you want to include in the dimension, and then click **Next**.</span></span>  
  
     <span data-ttu-id="a9198-124">Facoltativamente, è possibile modificare i nomi di attributo, abilitare o disabilitare l'esplorazione e specificare il tipo di attributo.</span><span class="sxs-lookup"><span data-stu-id="a9198-124">Optionally, you can change the attribute names, enable or disable browsing, and specify the attribute type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9198-125">Per rendere attivi i campi **Consenti esplorazione** e **Tipo attributo** , l'attributo deve essere selezionato in modo da essere incluso nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="a9198-125">To make the **Enable Browsing** and **Attribute Type** fields of an attribute active, the attribute must be selected for inclusion in the dimension.</span></span>  
  
6.  <span data-ttu-id="a9198-126">Nella pagina **Funzionalità di Business Intelligence per la contabilità** selezionare il tipo di conto nella colonna **Tipi di conto predefiniti** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a9198-126">On the **Define Account Intelligence** page, in the **Built-In Account Types** column, select the account type, and then click **Next**.</span></span>  
  
     <span data-ttu-id="a9198-127">Il tipo di conto deve corrispondere a quello della tabella di origine elencato nella colonna **Tipi di conto tabella di origine** .</span><span class="sxs-lookup"><span data-stu-id="a9198-127">The account type must correspond to the account type of the source table that is listed in the **Source Table Account Types** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9198-128">La pagina **Funzionalità di Business Intelligence per la contabilità** è visualizzata se è stato definito un attributo di dimensione **Tipo conto** nella pagina **Selezione attributi dimensione** della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="a9198-128">The **Define Account Intelligence** page appears if you defined an **Account Type** dimension attribute on the **Select Dimension Attributes** page of the wizard.</span></span>  
  
7.  <span data-ttu-id="a9198-129">Nella pagina **Completamento procedura guidata** assegnare un nome alla nuova dimensione e quindi esaminare la struttura della dimensione.</span><span class="sxs-lookup"><span data-stu-id="a9198-129">On the **Completing the Wizard** page, enter a name for the new dimension and review the dimension structure.</span></span> <span data-ttu-id="a9198-130">Per apportare modifiche, fare clic su **Indietro**. In caso contrario, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="a9198-130">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9198-131">È possibile utilizzare Progettazione dimensioni al termine della Creazione guidata dimensione per aggiungere, rimuovere e configurare attributi e gerarchie nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="a9198-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9198-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9198-132">See Also</span></span>  
 [<span data-ttu-id="a9198-133">Creare una dimensione utilizzando una tabella esistente</span><span class="sxs-lookup"><span data-stu-id="a9198-133">Create a Dimension by Using an Existing Table</span></span>](create-a-dimension-by-using-an-existing-table.md)  
  
  
