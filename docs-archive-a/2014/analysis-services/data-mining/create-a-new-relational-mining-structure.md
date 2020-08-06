---
title: Creazione di una nuova struttura di data mining relazionale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], relational
- mining structures [Analysis Services], creating
- relational mining models [Analysis Services]
ms.assetid: 55bac3bd-700e-4f91-bcc6-f3cd8c026da1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b41dd3ac2e6144011c1b3acde27c4b5829a1661
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625042"
---
# <a name="create-a-new-relational-mining-structure"></a><span data-ttu-id="43148-102">Creare una nuova struttura di data mining relazionale</span><span class="sxs-lookup"><span data-stu-id="43148-102">Create a New Relational Mining Structure</span></span>
  <span data-ttu-id="43148-103">Utilizzare la creazione guidata modello di data mining per creare una nuova struttura di data mining, utilizzando i dati di un database relazionale o di un'altra origine, quindi salvare la struttura ed eventuali modelli correlati in un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database di.</span><span class="sxs-lookup"><span data-stu-id="43148-103">Use the Data Mining Wizard to create a new mining structure, using data from a relational database or other source, and then save the structure and any related models to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="to-create-a-relational-mining-structure"></a><span data-ttu-id="43148-104">Per creare una struttura di data mining relazionale</span><span class="sxs-lookup"><span data-stu-id="43148-104">To create a relational mining structure</span></span>  
  
1.  <span data-ttu-id="43148-105">In Esplora soluzioni fare clic con il pulsante destro del mouse sulla cartella **Strutture di data mining** in un progetto di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , quindi scegliere **Nuova struttura di data mining**.</span><span class="sxs-lookup"><span data-stu-id="43148-105">In Solution Explorer, right-click the **Mining Structures** folder in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then click **New Mining Structure**.</span></span>  
  
     <span data-ttu-id="43148-106">Verrà avviata la Creazione guidata modello di data mining.</span><span class="sxs-lookup"><span data-stu-id="43148-106">The Data Mining Wizard opens.</span></span>  
  
2.  <span data-ttu-id="43148-107">Nella pagina iniziale **Creazione guidata modello di data mining** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="43148-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="43148-108">Nella pagina **Selezione metodo di definizione** selezionare **Da database relazionale o data warehouse esistente**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="43148-108">On the **Select the Definition Method** page, select **From existing relational database or data warehouse**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="43148-109">Nella pagina **Select the Data Mining Technique** (Selezione di una tecnica di data mining) selezionare l'algoritmo di data mining che si desidera usare, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="43148-109">On the **Select the Data Mining Technique** page, select the data mining algorithm that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="43148-110">Per altre informazioni sugli algoritmi di data mining, vedere [Algoritmi di data mining &#40;Analysis Services - Data mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="43148-110">For more information about data mining algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
5.  <span data-ttu-id="43148-111">Nella pagina **Selezione vista origine dati** in **Viste origine dati disponibili**fare clic sulla vista origine dati che si desidera usare, quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="43148-111">On the **Select Data Source View** page, under **Available data source views**, click the data source view that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="43148-112">Per altre informazioni sulla creazione di una vista origine dati, vedere [Viste origine dati in modelli multidimensionali](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="43148-112">For more information about creating a data source view, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
6.  <span data-ttu-id="43148-113">Nella pagina **Impostazione tipi di tabelle** in **Tabelle di input**selezionare una tabella del case e una tabella annidata.</span><span class="sxs-lookup"><span data-stu-id="43148-113">On the **Specify Table Types** page, under **Input tables**, select a case table and a nested table.</span></span>  
  
7.  <span data-ttu-id="43148-114">Nella pagina **Impostazione dati di training** in **Struttura modello di data mining**selezionare le colonne chiave, di input e stimabile.</span><span class="sxs-lookup"><span data-stu-id="43148-114">On the **Specify the Training Data** page, under **Mining model structure**, select the key, input, and predictable columns.</span></span>  
  
     <span data-ttu-id="43148-115">Dopo avere selezionato la colonna stimabile, è possibile fare clic sul pulsante **Suggerisci** per visualizzare la finestra di dialogo **Suggerisci colonne correlate** .</span><span class="sxs-lookup"><span data-stu-id="43148-115">After you select the predictable column, you can click the **Suggest** button to open the **Suggest Related Columns** dialog box.</span></span> <span data-ttu-id="43148-116">È possibile accettare le colonne suggerite facendo clic su **OK** in questa finestra di dialogo per includere le colonne selezionate nella struttura di data mining oppure modificare le selezioni nella colonna **Input** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="43148-116">You can accept the suggested columns by clicking **OK** in this dialog box to include the selected columns in the mining structure, or you can change the selections in the **Input** column first, and then click **OK**.</span></span> <span data-ttu-id="43148-117">Per ignorare i suggerimenti, fare clic su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="43148-117">To ignore the suggestions, click **Cancel**.</span></span>  
  
8.  <span data-ttu-id="43148-118">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="43148-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="43148-119">Nella pagina **Impostazione tipo di contenuto e dati delle colonne** in **Struttura modello di data mining**è possibile modificare il tipo di contenuto e di dati per ogni colonna.</span><span class="sxs-lookup"><span data-stu-id="43148-119">On the **Specify Columns' Content and Data Type** page, under **Mining model structure**, you can adjust the content type and data type for each column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43148-120">È possibile fare clic su **Rileva** per rilevare automaticamente se una colonna contiene dati continui o discreti.</span><span class="sxs-lookup"><span data-stu-id="43148-120">You can click **Detect** to automatically detect whether a column contains continuous or discrete data.</span></span> <span data-ttu-id="43148-121">Dopo avere fatto clic su questo pulsante, i tipi di contenuto e di dati verranno aggiornati nelle colonne **Tipo di contenuto** e **Tipo di dati** .</span><span class="sxs-lookup"><span data-stu-id="43148-121">After you click this button, the column content and data types will be updated in the **Content Type** and **Data Type** columns.</span></span> <span data-ttu-id="43148-122">Per altre informazioni sui tipi di contenuto e i tipi di dati, vedere [Tipi di contenuto &#40;Data mining&#41;](content-types-data-mining.md) e [Tipi di dati &#40;data mining&#41;](data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="43148-122">For more information about content types and data types, see [Content Types &#40;Data Mining&#41;](content-types-data-mining.md) and [Data Types &#40;Data Mining&#41;](data-types-data-mining.md).</span></span>  
  
10. <span data-ttu-id="43148-123">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="43148-123">Click **Next**.</span></span>  
  
11. <span data-ttu-id="43148-124">Nella pagina **Completamento procedura guidata** specificare un nome per la struttura di data mining e per il modello di data mining iniziale correlato di cui verrà eseguita la creazione, quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="43148-124">On the **Completing the Wizard** page, provide a name for the mining structure and the related initial mining model that will be created, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43148-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43148-125">See Also</span></span>  
 [<span data-ttu-id="43148-126">Attività e procedure relative alla struttura di data mining</span><span class="sxs-lookup"><span data-stu-id="43148-126">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
