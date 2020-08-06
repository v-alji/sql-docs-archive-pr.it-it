---
title: Selezione attributi dimensione (creazione guidata dimensione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.dimensionattributes.f1
ms.assetid: f58a3e14-ab27-44d3-8c26-f5c9ee7583b0
author: minewiskan
ms.author: owend
ms.openlocfilehash: a4961092517ce1d38cfd4086ec083a939242652d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626347"
---
# <a name="select-dimension-attributes-dimension-wizard"></a><span data-ttu-id="af445-102">Selezione attributi dimensione (Creazione guidata dimensione)</span><span class="sxs-lookup"><span data-stu-id="af445-102">Select Dimension Attributes (Dimension Wizard)</span></span>
  <span data-ttu-id="af445-103">La pagina **Selezione attributi dimensione** consente di selezionare e modificare gli attributi della dimensione da creare.</span><span class="sxs-lookup"><span data-stu-id="af445-103">Use the **Select Dimension Attributes** page to select and modify the attributes for the dimension to be created.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af445-104">Se non è possibile leggere i valori di una colonna, ingrandire la finestra della procedura guidata e modificare la larghezza di ogni intestazione di colonna fino a leggerne i valori.</span><span class="sxs-lookup"><span data-stu-id="af445-104">If you cannot read the values for any column, maximize the wizard window and change the width of each column heading until you can read the values.</span></span>  
  
 <span data-ttu-id="af445-105">**Per aprire la Creazione guidata dimensione.**</span><span class="sxs-lookup"><span data-stu-id="af445-105">**To open the Dimension Wizard**</span></span>  
  
-   <span data-ttu-id="af445-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]fare clic con il pulsante destro del mouse sulla cartella **Dimensioni**in **Esplora soluzioni** per scegliere un progetto di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , quindi fare clic su **Nuova dimensione**.</span><span class="sxs-lookup"><span data-stu-id="af445-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], in **Solution Explorer**, right-click the **Dimensions** folder for an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project, and then click **New Dimension**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="af445-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="af445-107">Options</span></span>  
 <span data-ttu-id="af445-108">(Colonna con caselle di controllo)</span><span class="sxs-lookup"><span data-stu-id="af445-108">(Column with check boxes)</span></span>  
 <span data-ttu-id="af445-109">Selezionare questa opzione per includere un attributo nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="af445-109">Select to include an attribute in the dimension.</span></span>  
  
 <span data-ttu-id="af445-110">Per includere un attributo specifico, selezionare la casella di controllo relativa a tale attributo.</span><span class="sxs-lookup"><span data-stu-id="af445-110">To include a specific attribute, select the check box for that attribute.</span></span>  
  
 <span data-ttu-id="af445-111">Per includere tutti gli attributi, selezionare la casella di controllo nell'intestazione di colonna.</span><span class="sxs-lookup"><span data-stu-id="af445-111">To include all attributes, select the check box in the column header.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af445-112">Impossibile deselezionare la casella di controllo per l'attributo chiave.</span><span class="sxs-lookup"><span data-stu-id="af445-112">The check box for the key attribute cannot be cleared.</span></span>  
  
 <span data-ttu-id="af445-113">**Nome attributo**</span><span class="sxs-lookup"><span data-stu-id="af445-113">**Attribute Name**</span></span>  
 <span data-ttu-id="af445-114">Elenca gli attributi disponibili.</span><span class="sxs-lookup"><span data-stu-id="af445-114">Lists the available attributes.</span></span>  
  
 <span data-ttu-id="af445-115">Per modificare il nome di un attributo, fare clic sul nome dell’attributo e digitare un nuovo nome.</span><span class="sxs-lookup"><span data-stu-id="af445-115">To change the name of an attribute, click the attribute name and type a new name for the attribute.</span></span>  
  
 <span data-ttu-id="af445-116">**Consenti esplorazione**</span><span class="sxs-lookup"><span data-stu-id="af445-116">**Enable Browsing**</span></span>  
 <span data-ttu-id="af445-117">Selezionare per rendere disponibile l'attributo all'utente finale per l’esplorazione e l’applicazione di filtri.</span><span class="sxs-lookup"><span data-stu-id="af445-117">Select to make the attribute available to the end user for browsing and filtering.</span></span> <span data-ttu-id="af445-118">**Consenti esplorazione** deve essere selezionato per l'attributo chiave.</span><span class="sxs-lookup"><span data-stu-id="af445-118">**Enable Browsing** must be selected for the key attribute.</span></span> <span data-ttu-id="af445-119">Per gli attributi non chiave, **Consenti esplorazione** non è selezionato per impostazione predefinita. Gli attributi non chiave vengono pertanto visualizzati solo come proprietà del membro.</span><span class="sxs-lookup"><span data-stu-id="af445-119">For non-key attributes, the default is not to have **Enable Browsing** selected, which causes the non-key attributes to be shown only as member properties.</span></span>  
  
 <span data-ttu-id="af445-120">Nella maggior parte dei casi, l'attributo è reso disponibile o non disponibile per l'esplorazione impostando la proprietà `AttributeHierarchyEnabled` rispettivamente su `True` o su `False`.</span><span class="sxs-lookup"><span data-stu-id="af445-120">In most cases, the attribute is made available or not available for browsing by setting the `AttributeHierarchyEnabled` property to `True` or `False`, respectively.</span></span> <span data-ttu-id="af445-121">Nei tre casi seguenti, la procedura guidata utilizza comunque impostazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="af445-121">However, in the following three cases, the wizard uses different settings.</span></span>  
  
|<span data-ttu-id="af445-122">Caso</span><span class="sxs-lookup"><span data-stu-id="af445-122">Case</span></span>|<span data-ttu-id="af445-123">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="af445-123">Settings</span></span>|  
|----------|--------------|  
|<span data-ttu-id="af445-124">Una dimensione contiene una gerarchia padre-figlio e **Consenti esplorazione** non è selezionato.</span><span class="sxs-lookup"><span data-stu-id="af445-124">A dimension contains a parent-child hierarchy and **Enable Browsing** is not selected</span></span>|<span data-ttu-id="af445-125">La procedura guidata lascia la proprietà `AttributeHierarchyEnabled` impostata su `True` e imposta l'attributo `AttributeHierarchyVisible` su `False` per l'attributo chiave.</span><span class="sxs-lookup"><span data-stu-id="af445-125">The wizard leaves the `AttributeHierarchyEnabled` property set to `True`, and sets the `AttributeHierarchyVisible` attribute to `False` for the key attribute.</span></span>|  
|<span data-ttu-id="af445-126">Una tabella in una dimensione contiene una chiave esterna a una tabella che non è nella dimensione</span><span class="sxs-lookup"><span data-stu-id="af445-126">A table in a dimension contains a foreign key to a table that is not in the dimension</span></span>|<span data-ttu-id="af445-127">La procedura guidata seleziona la chiave esterna come un attributo da includere, ma non selezionerà **Consenti esplorazione**.</span><span class="sxs-lookup"><span data-stu-id="af445-127">The wizard selects the foreign key as an attribute to be included, but will not select **Enable Browsing**.</span></span> <span data-ttu-id="af445-128">Se si mantengono queste impostazioni, la proprietà `AttributeHiearchyEnabled` dell’attributo sarà impostata su `True` e la proprietà `AttributeHierarchyVisible` sarà impostata su `False`.</span><span class="sxs-lookup"><span data-stu-id="af445-128">If you keep these settings, the `AttributeHiearchyEnabled` property of the attribute will be set to `True`, and the `AttributeHierarchyVisible` property will be set to `False`.</span></span>|  
|<span data-ttu-id="af445-129">Una dimensione contiene tabelle con schema snowflake raggiungibili tramite colonne chiavi esterne che ammettono valori Null.</span><span class="sxs-lookup"><span data-stu-id="af445-129">A dimension contains snowflake tables that are reached through nullable foreign key columns</span></span><br /><br /> <span data-ttu-id="af445-130">-e-</span><span class="sxs-lookup"><span data-stu-id="af445-130">-and-</span></span><br /><br /> <span data-ttu-id="af445-131">Consenti esplorazione per l'attributo basato sulla chiave della tabella con schema snowflake non è selezionato</span><span class="sxs-lookup"><span data-stu-id="af445-131">Enable Browsing for the attribute that is based on the key of the snowflake table is not selected</span></span>|<span data-ttu-id="af445-132">La procedura guidata creerà il nuovo attributo con la proprietà `AttributeHiearchyEnabled` impostata su `True` e la proprietà `AttributeHierarchyVisible` impostata su `False`.</span><span class="sxs-lookup"><span data-stu-id="af445-132">The wizard will create the new attribute that has the `AttributeHiearchyEnabled` property set to `True`, and the `AttributeHierarchyVisible` property set to `False`.</span></span>|  
  
 <span data-ttu-id="af445-133">**Tipo di attributo**</span><span class="sxs-lookup"><span data-stu-id="af445-133">**Attribute Type**</span></span>  
 <span data-ttu-id="af445-134">(Facoltativo) Impostare il tipo per l'attributo.</span><span class="sxs-lookup"><span data-stu-id="af445-134">(Optional) Set the type for the attribute.</span></span> <span data-ttu-id="af445-135">Il valore predefinito è **Regolare**.</span><span class="sxs-lookup"><span data-stu-id="af445-135">The default value is **Regular**.</span></span> <span data-ttu-id="af445-136">Il tipo di attributo fornisce l’istruzione alle applicazioni client riguardo le informazioni che l'attributo potrebbe contenere.</span><span class="sxs-lookup"><span data-stu-id="af445-136">The attribute type provides guidance to client applications on what information the attribute might contain.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af445-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af445-137">See Also</span></span>  
 <span data-ttu-id="af445-138">[Guida sensibile al contesto della creazione guidata dimensione](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="af445-138">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="af445-139">[Dimensioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="af445-139">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="af445-140">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="af445-140">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
