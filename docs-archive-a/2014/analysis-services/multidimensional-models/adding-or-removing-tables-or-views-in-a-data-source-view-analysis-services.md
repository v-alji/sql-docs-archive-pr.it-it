---
title: Aggiunta o rimozione di tabelle o viste in una vista origine dati (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.tablespane.f1
helpviewer_keywords:
- deleting tables
- tables [Analysis Services]
- removing tables
- adding tables
- data source views [Analysis Services], tables
- tables [Analysis Services], data source views
ms.assetid: 98307d04-6548-4d7d-9244-2371dd165249
author: minewiskan
ms.author: owend
ms.openlocfilehash: da1bc2b1ac0af7576cfe3c3593b451f78d6a9fae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637467"
---
# <a name="adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services"></a><span data-ttu-id="5f70b-102">Aggiunta o rimozione di tabelle o viste in una vista origine dati (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="5f70b-102">Adding or Removing Tables or Views in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="5f70b-103">Dopo aver creato una vista origine dati in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], è possibile modificarla in Progettazione vista origine dati aggiungendo o rimuovendo tabelle e colonne, incluse quelle provenienti da un'altra origine dati.</span><span class="sxs-lookup"><span data-stu-id="5f70b-103">After you have created a data source view (DSV) in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can modify it in Data Source View Designer by adding or removing tables and columns, including tables and columns from another data source.</span></span>  
  
 <span data-ttu-id="5f70b-104">Per aprire la vista origine dati in Progettazione vista origine dati, è necessario fare doppio clic sulla vista in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="5f70b-104">To open the DSV in Data Source View Designer, you double-click the DSV in Solution Explorer.</span></span> <span data-ttu-id="5f70b-105">Una volta aperta la vista origine dati, è possibile usare il comando **Aggiungi/Rimuovi tabelle** nella barra dei pulsanti o nel menu per modificare o estendere la vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="5f70b-105">Once you open the DSV, you can use the **Add/Remove Tables** command on the button bar or menu to modify or extend the DSV.</span></span> <span data-ttu-id="5f70b-106">È possibile inoltre utilizzare gli oggetti nel diagramma.</span><span class="sxs-lookup"><span data-stu-id="5f70b-106">You can also work with the objects in the diagram.</span></span> <span data-ttu-id="5f70b-107">Ad esempio, è possibile selezionare un oggetto e utilizzare il tasto CANC sulla tastiera per rimuovere un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5f70b-107">For example, you can select an object and then use the Delete key on your keyboard to remove an object.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="5f70b-108">Prestare attenzione in caso di rimozione di una tabella.</span><span class="sxs-lookup"><span data-stu-id="5f70b-108">Use caution when removing a table.</span></span> <span data-ttu-id="5f70b-109">Se si rimuove una tabella vengono eliminate anche tutte le colonne e relazioni associate dalla vista origine dati e tutti gli oggetti associati a tale tabella non sono più validi.</span><span class="sxs-lookup"><span data-stu-id="5f70b-109">Removing a table deletes all the associated columns and relationships from the DSV and invalidates all objects bound to that table.</span></span>  
  
## <a name="selecting-tables-or-views-to-add-or-remove"></a><span data-ttu-id="5f70b-110">Selezione delle tabelle o delle viste da aggiungere o rimuovere</span><span class="sxs-lookup"><span data-stu-id="5f70b-110">Selecting Tables or Views to Add or Remove</span></span>  
 <span data-ttu-id="5f70b-111">Usando la finestra di dialogo **Aggiungi/Rimuovi tabelle** è possibile spostare tabelle o viste tra gli elenchi **Oggetti disponibili** e **Oggetti inclusi** .</span><span class="sxs-lookup"><span data-stu-id="5f70b-111">Using the **Add/Remove Tables** dialog box, you can move tables or views between the **Available objects** and **Included objects** lists.</span></span> <span data-ttu-id="5f70b-112">Nell'elenco **Oggetti disponibili** vengono incluse inizialmente tutte le tabelle o le viste dell'origine dei dati primaria che non sono già contenute nella vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="5f70b-112">The **Available objects** list initially includes any tables or views in the primary data source that are not already in the data source view.</span></span> <span data-ttu-id="5f70b-113">Se l'origine dati primaria supporta la funzione `OPENROWSET`, è inoltre possibile aggiungere tabelle o viste da altre origini dati nel progetto o nel database.</span><span class="sxs-lookup"><span data-stu-id="5f70b-113">If the primary data source supports the `OPENROWSET` function, you can also add tables or views from other data sources in the project or database.</span></span>  
  
 <span data-ttu-id="5f70b-114">Se si aggiunge o si rimuove una tabella dalla vista origine dati, la tabella verrà aggiunta o rimossa anche dal diagramma corrente selezionato nella vista.</span><span class="sxs-lookup"><span data-stu-id="5f70b-114">Adding or removing a table to the DSV also adds or removes the table to the currently selected diagram in the DSV.</span></span> <span data-ttu-id="5f70b-115">Per altre informazioni sui diagrammi, vedere [Usare diagrammi in Progettazione vista origine dati &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="5f70b-115">For more information on diagrams, see [Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span></span>  
  
 <span data-ttu-id="5f70b-116">Dopo aver spostato una tabella nell'elenco **Oggetti inclusi** della finestra di dialogo **Aggiungi/Rimuovi tabelle** , è possibile aggiungere tutte le tabelle correlate.</span><span class="sxs-lookup"><span data-stu-id="5f70b-116">After you move a table to the **Included objects** list in the **Add/Remove Tables** dialog box, you can add all related tables.</span></span> <span data-ttu-id="5f70b-117">Questa operazione consente di aggiungere le tabelle nell'origine dei dati in base a vincoli di chiave esterna, se esistono.</span><span class="sxs-lookup"><span data-stu-id="5f70b-117">This operation adds tables according to foreign key constraints in the data source, if such constraints exist.</span></span> <span data-ttu-id="5f70b-118">Se non esistono vincoli di chiave esterna, è possibile utilizzare la proprietà `NameMatchingCriteria` della vista origine dati per determinare le relazioni specificando un criterio di corrispondenza per i nomi delle colonne nelle tabelle al fine di generare le relazioni probabili.</span><span class="sxs-lookup"><span data-stu-id="5f70b-118">If foreign key constraints do not exist, you can use the `NameMatchingCriteria` property of the data source view to determine relationships by specifying a criterion for matching column names in tables to generate likely relationships.</span></span> <span data-ttu-id="5f70b-119">Se la `NameMatchingCriteria` proprietà è specificata per la vista origine dati, fare clic su **Aggiungi tabelle correlate** per aggiungere tabelle dall'origine dati con nomi di colonna corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5f70b-119">If the `NameMatchingCriteria`property is specified for the data source view, click **Add Related Tables** to add tables from the data source that have matching column names.</span></span> <span data-ttu-id="5f70b-120">Per ulteriori informazioni sull'impostazione della `NameMatchingCriteria` proprietà, vedere [viste origine dati in modelli multidimensionali](data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="5f70b-120">For more information about setting the `NameMatchingCriteria` property, see [Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5f70b-121">L'aggiunta o la rimozione di oggetti in una vista origine dati non influisce sull'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="5f70b-121">Adding or removing objects in a data source view does not affect the underlying data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f70b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f70b-122">See Also</span></span>  
 <span data-ttu-id="5f70b-123">[Viste origine dati in modelli multidimensionali](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="5f70b-123">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="5f70b-124">Utilizzare diagrammi in Progettazione vista origine dati &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5f70b-124">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
  
