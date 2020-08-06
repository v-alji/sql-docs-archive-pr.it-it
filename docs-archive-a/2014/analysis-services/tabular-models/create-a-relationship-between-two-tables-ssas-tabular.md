---
title: Creare una relazione tra due tabelle (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.managereldb.f1
- sql12.asvs.bidtoolset.createrelatdb.f1
ms.assetid: 052d77b7-7922-408a-a200-786016ee4d15
author: minewiskan
ms.author: owend
ms.openlocfilehash: 33481b8d50be9ca632bcade932d51df86c1910a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626923"
---
# <a name="create-a-relationship-between-two-tables-ssas-tabular"></a><span data-ttu-id="32870-102">Creare una relazione tra due tabelle (SSAS tabulare)</span><span class="sxs-lookup"><span data-stu-id="32870-102">Create a Relationship Between Two Tables (SSAS Tabular)</span></span>
  <span data-ttu-id="32870-103">Se per le tabelle presenti nell'origine dati non sono attualmente disponibili relazioni o se si aggiungono nuove tabelle, è possibile creare nuove relazioni utilizzando gli strumenti di Progettazione modelli.</span><span class="sxs-lookup"><span data-stu-id="32870-103">If the tables in your data source do not have existing relationships, or if you add new tables, you can use the tools in the model designer to create new relationships.</span></span> <span data-ttu-id="32870-104">Per informazioni sulla modalità d'uso delle relazioni nei modelli tabulari, vedere [Relazioni &#40;SSAS tabulare&#41;](relationships-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="32870-104">For information about how relationships are used in tabular models, see [Relationships &#40;SSAS Tabular&#41;](relationships-ssas-tabular.md).</span></span>  
  
## <a name="create-a-relationship-between-two-tables"></a><span data-ttu-id="32870-105">Creare una relazione tra due tabelle</span><span class="sxs-lookup"><span data-stu-id="32870-105">Create a relationship between two tables</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-click-and-drag"></a><span data-ttu-id="32870-106">Per creare una relazione tra due tabelle in Vista diagramma, visualizzabile facendo clic e trascinando</span><span class="sxs-lookup"><span data-stu-id="32870-106">To create a relationship between two tables in Diagram View (Click and drag)</span></span>  
  
1.  <span data-ttu-id="32870-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]scegliere **Vista modelli** dal menu **Modello**, quindi fare clic su **Vista diagramma**.</span><span class="sxs-lookup"><span data-stu-id="32870-107">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="32870-108">Fare clic su una colonna all'interno di una tabella e, tenendo premuto il pulsante, trascinare il cursore in una colonna di ricerca correlata di una relativa tabella, quindi rilasciarlo.</span><span class="sxs-lookup"><span data-stu-id="32870-108">Click (and hold) on a column within a table, then drag the cursor to a related lookup column in a related lookup table, and then release.</span></span> <span data-ttu-id="32870-109">La relazione verrà creata automaticamente nell'ordine corretto.</span><span class="sxs-lookup"><span data-stu-id="32870-109">The relationship will be created in the correct order automatically.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-diagram-view-right-click"></a><span data-ttu-id="32870-110">Per creare una relazione tra due tabelle in Vista diagramma, visualizzabile facendo clic con il pulsante destro del mouse</span><span class="sxs-lookup"><span data-stu-id="32870-110">To create a relationship between two tables in Diagram View (Right-click)</span></span>  
  
1.  <span data-ttu-id="32870-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]scegliere **Vista modelli** dal menu **Modello**, quindi fare clic su **Vista diagramma**.</span><span class="sxs-lookup"><span data-stu-id="32870-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, then click **Model View**, and then click **Diagram View**.</span></span>  
  
2.  <span data-ttu-id="32870-112">Fare clic con il pulsante destro del mouse sull'intestazione di una tabella o su una colonna, quindi scegliere **Crea relazione**.</span><span class="sxs-lookup"><span data-stu-id="32870-112">Right-click a table heading or column, and then click **Create Relationship**.</span></span>  
  
3.  <span data-ttu-id="32870-113">Nella finestra di dialogo **Crea relazione** fare clic sulla freccia in giù accanto a **Tabella**e selezionare una tabella nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="32870-113">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="32870-114">Questa tabella deve trovarsi sul lato "molti" di una relazione "uno-a-molti".</span><span class="sxs-lookup"><span data-stu-id="32870-114">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
4.  <span data-ttu-id="32870-115">Per **Colonna**, selezionare la colonna che contiene i dati correlata a **Colonna di ricerca correlata**.</span><span class="sxs-lookup"><span data-stu-id="32870-115">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span> <span data-ttu-id="32870-116">La colonna viene selezionata automaticamente se è stato fatto clic con il pulsante destro del mouse su una colonna per creare la relazione.</span><span class="sxs-lookup"><span data-stu-id="32870-116">The column is automatically selected if you right-clicked on a column to create the relationship.</span></span>  
  
5.  <span data-ttu-id="32870-117">Per **Tabella di ricerca correlata**, selezionare una tabella che dispone almeno di una colonna di dati correlata alla tabella appena selezionata per **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="32870-117">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="32870-118">Questa tabella deve trovarsi sul lato "uno" di una relazione "uno-a-molti", per indicare che i valori nella colonna selezionata non contengono duplicati.</span><span class="sxs-lookup"><span data-stu-id="32870-118">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="32870-119">Se si tenta di creare la relazione nell'ordine errato (uno-a-molti anziché molti-a-uno), verrà visualizzata un'icona accanto al campo **Colonna di ricerca correlata** .</span><span class="sxs-lookup"><span data-stu-id="32870-119">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="32870-120">Invertire l'ordine per creare una relazione valida.</span><span class="sxs-lookup"><span data-stu-id="32870-120">Reverse the order to create a valid relationship.</span></span>  
  
6.  <span data-ttu-id="32870-121">Per **Colonna di ricerca correlata**, selezionare una colonna che dispone di valori univoci che corrispondono ai valori della colonna selezionata per **Colonna**.</span><span class="sxs-lookup"><span data-stu-id="32870-121">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
7.  <span data-ttu-id="32870-122">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="32870-122">Click **Create**.</span></span>  
  
#### <a name="to-create-a-relationship-between-two-tables-in-data-view"></a><span data-ttu-id="32870-123">Per creare una relazione tra due tabelle in Vista dati</span><span class="sxs-lookup"><span data-stu-id="32870-123">To create a relationship between two tables in Data View</span></span>  
  
1.  <span data-ttu-id="32870-124">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]scegliere **Crea relazioni** dal menu **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="32870-124">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Table** menu, and then click **Create Relationships**.</span></span>  
  
2.  <span data-ttu-id="32870-125">Nella finestra di dialogo **Crea relazione** fare clic sulla freccia in giù accanto a **Tabella**e selezionare una tabella nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="32870-125">In the **Create Relationship** dialog box, click the down arrow for **Table**, and select a table from the dropdown list.</span></span>  
  
     <span data-ttu-id="32870-126">Questa tabella deve trovarsi sul lato "molti" di una relazione "uno-a-molti".</span><span class="sxs-lookup"><span data-stu-id="32870-126">In a "one-to-many" relationship, this table should be on the "many" side.</span></span>  
  
3.  <span data-ttu-id="32870-127">Per **Colonna**, selezionare la colonna che contiene i dati correlata a **Colonna di ricerca correlata**.</span><span class="sxs-lookup"><span data-stu-id="32870-127">For **Column**, select the column that contains the data that is related to **Related Lookup Column**.</span></span>  
  
4.  <span data-ttu-id="32870-128">Per **Tabella di ricerca correlata**, selezionare una tabella che dispone almeno di una colonna di dati correlata alla tabella appena selezionata per **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="32870-128">For **Related Lookup Table**, select a table that has at least one column of data that is related to the table you just selected for **Table**.</span></span>  
  
     <span data-ttu-id="32870-129">Questa tabella deve trovarsi sul lato "uno" di una relazione "uno-a-molti", per indicare che i valori nella colonna selezionata non contengono duplicati.</span><span class="sxs-lookup"><span data-stu-id="32870-129">In a "one-to-many" relationship, this table should be on the "one" side, meaning that the values in the selected column do not contain duplicates.</span></span> <span data-ttu-id="32870-130">Se si tenta di creare la relazione nell'ordine errato (uno-a-molti anziché molti-a-uno), verrà visualizzata un'icona accanto al campo **Colonna di ricerca correlata** .</span><span class="sxs-lookup"><span data-stu-id="32870-130">If you attempt to create the relationship in the wrong order (one-to-many instead of many-to-one), an icon will appear next to the **Related Lookup Column** field.</span></span> <span data-ttu-id="32870-131">Invertire l'ordine per creare una relazione valida.</span><span class="sxs-lookup"><span data-stu-id="32870-131">Reverse the order to create a valid relationship.</span></span>  
  
5.  <span data-ttu-id="32870-132">Per **Colonna di ricerca correlata**, selezionare una colonna che dispone di valori univoci che corrispondono ai valori della colonna selezionata per **Colonna**.</span><span class="sxs-lookup"><span data-stu-id="32870-132">For **Related Lookup Column**, select a column that has unique values that match the values in the column you selected for **Column**.</span></span>  
  
6.  <span data-ttu-id="32870-133">Fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="32870-133">Click **Create**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32870-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32870-134">See Also</span></span>  
 <span data-ttu-id="32870-135">[Eliminare relazioni &#40;SSAS tabulare&#41;](delete-relationships-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="32870-135">[Delete Relationships &#40;SSAS Tabular&#41;](delete-relationships-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="32870-136">Relazioni &#40;SSAS tabulare&#41;</span><span class="sxs-lookup"><span data-stu-id="32870-136">Relationships &#40;SSAS Tabular&#41;</span></span>](relationships-ssas-tabular.md)  
  
  
