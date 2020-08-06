---
title: Proprietà della tabella (SSAS tabulare) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9613609c42de8fd3a4aab7aec3208dfe3d31be4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723107"
---
# <a name="table-properties-ssas-tabular"></a><span data-ttu-id="668e4-102">Table Properties (SSAS Tabular)</span><span class="sxs-lookup"><span data-stu-id="668e4-102">Table Properties (SSAS Tabular)</span></span>
  <span data-ttu-id="668e4-103">In questo argomento vengono descritte le proprietà delle tabelle dei modelli tabulari.</span><span class="sxs-lookup"><span data-stu-id="668e4-103">This topic describes tabular model table properties.</span></span> <span data-ttu-id="668e4-104">Le proprietà descritte differiscono da quelle presenti nella finestra di dialogo Modifica proprietà tabella, che consentono di definire quali colonne vengono importate dall'origine.</span><span class="sxs-lookup"><span data-stu-id="668e4-104">The properties described here are different from those in the Edit Table Properties dialog box, which define which columns from the source are imported.</span></span>  
  
 <span data-ttu-id="668e4-105">Sezioni dell'argomento:</span><span class="sxs-lookup"><span data-stu-id="668e4-105">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="668e4-106">Proprietà tabella</span><span class="sxs-lookup"><span data-stu-id="668e4-106">Table Properties</span></span>](#bkmk_properties)  
  
-   [<span data-ttu-id="668e4-107">Per configurare le impostazioni delle proprietà delle tabelle</span><span class="sxs-lookup"><span data-stu-id="668e4-107">To configure table property settings</span></span>](#bkmk_config_prop)  
  
##  <a name="table-properties"></a><a name="bkmk_properties"></a><span data-ttu-id="668e4-108">Proprietà tabella</span><span class="sxs-lookup"><span data-stu-id="668e4-108">Table Properties</span></span>  
 <span data-ttu-id="668e4-109">**Base**</span><span class="sxs-lookup"><span data-stu-id="668e4-109">**Basic**</span></span>  
  
|<span data-ttu-id="668e4-110">Proprietà</span><span class="sxs-lookup"><span data-stu-id="668e4-110">Property</span></span>|<span data-ttu-id="668e4-111">Impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="668e4-111">Default Setting</span></span>|<span data-ttu-id="668e4-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="668e4-112">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="668e4-113">**Connection Name** (Nome connessione)</span><span class="sxs-lookup"><span data-stu-id="668e4-113">**Connection Name**</span></span>|\<connection name>|<span data-ttu-id="668e4-114">Nome della connessione all'origine dati della tabella.</span><span class="sxs-lookup"><span data-stu-id="668e4-114">The name of the connection to the table's data source.</span></span><br /><br /> <span data-ttu-id="668e4-115">Per modificare la connessione, fare clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="668e4-115">To edit the connection, click the button.</span></span>|  
|<span data-ttu-id="668e4-116">**Hidden**</span><span class="sxs-lookup"><span data-stu-id="668e4-116">**Hidden**</span></span>|<span data-ttu-id="668e4-117">Falso</span><span class="sxs-lookup"><span data-stu-id="668e4-117">False</span></span>|<span data-ttu-id="668e4-118">Viene specificato se la tabella è nascosta dalla visualizzazione negli elenchi dei campi del client di creazione report.</span><span class="sxs-lookup"><span data-stu-id="668e4-118">Specifies whether the table is hidden from reporting client field lists.</span></span>|  
|<span data-ttu-id="668e4-119">**Partizioni**</span><span class="sxs-lookup"><span data-stu-id="668e4-119">**Partitions**</span></span>||<span data-ttu-id="668e4-120">Le partizioni per la tabella non possono essere visualizzate nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="668e4-120">Partitions for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="668e4-121">Per visualizzare, creare o modificare partizioni, fare clic sul pulsante per aprire Gestione partizioni.</span><span class="sxs-lookup"><span data-stu-id="668e4-121">To view, create, or edit partitions, click the button to open the Partition Manager.</span></span>|  
|<span data-ttu-id="668e4-122">**Dati di origine**</span><span class="sxs-lookup"><span data-stu-id="668e4-122">**Source Data**</span></span>||<span data-ttu-id="668e4-123">I dati di origine per la tabella non possono essere visualizzati nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="668e4-123">Source data for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="668e4-124">Per visualizzare o modificare i dati di origine, fare clic sul pulsante per aprire la finestra di dialogo Modifica proprietà tabella.</span><span class="sxs-lookup"><span data-stu-id="668e4-124">To view or edit the source data, click the button to open the Edit Table Properties dialog box.</span></span>|  
|<span data-ttu-id="668e4-125">**Descrizione tabella**</span><span class="sxs-lookup"><span data-stu-id="668e4-125">**Table Description**</span></span>||<span data-ttu-id="668e4-126">Descrizione di testo per la tabella.</span><span class="sxs-lookup"><span data-stu-id="668e4-126">A text description for the table.</span></span><br /><br /> <span data-ttu-id="668e4-127">In [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], se un utente finale posiziona il cursore su questa tabella nell'elenco dei campi, la descrizione viene visualizzata come descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="668e4-127">In [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], if an end-user places the cursor over this table in the field list, the description appears as a tooltip.</span></span>|  
|<span data-ttu-id="668e4-128">**Nome tabella**</span><span class="sxs-lookup"><span data-stu-id="668e4-128">**Table Name**</span></span>|\<friendly name>|<span data-ttu-id="668e4-129">Specifica il nome descrittivo della tabella.</span><span class="sxs-lookup"><span data-stu-id="668e4-129">Specifies the table's friendly name.</span></span> <span data-ttu-id="668e4-130">È possibile specificare il nome di tabella quando una tabella viene importata utilizzando l'Importazione guidata tabella oppure in qualsiasi momento dopo l'importazione.</span><span class="sxs-lookup"><span data-stu-id="668e4-130">The table name can be specified when a table is imported using the Table Import Wizard or at any time after import.</span></span> <span data-ttu-id="668e4-131">Il nome della tabella nel modello può essere diverso dalla tabella associata nell'origine.</span><span class="sxs-lookup"><span data-stu-id="668e4-131">The table name in the model can be different from the associated table at the source.</span></span> <span data-ttu-id="668e4-132">Il nome descrittivo della tabella viene visualizzato nell'elenco di campi dell'applicazione client di creazione report, nonché nel database modello in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="668e4-132">The table friendly name appears in the reporting client application field list as well as in the model database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|  
  
 <span data-ttu-id="668e4-133">**Proprietà report**</span><span class="sxs-lookup"><span data-stu-id="668e4-133">**Reporting Properties**</span></span>  
  
 <span data-ttu-id="668e4-134">Per descrizioni dettagliate e informazioni sulla configurazione per le proprietà di creazione dei report, vedere [Proprietà report Power View &#40;SSAS tabulare&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="668e4-134">For detailed descriptions and configuration information for reporting properties, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
|<span data-ttu-id="668e4-135">Proprietà</span><span class="sxs-lookup"><span data-stu-id="668e4-135">Property</span></span>|<span data-ttu-id="668e4-136">Impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="668e4-136">Default Setting</span></span>|<span data-ttu-id="668e4-137">Descrizione</span><span class="sxs-lookup"><span data-stu-id="668e4-137">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="668e4-138">**Set di campi predefiniti**</span><span class="sxs-lookup"><span data-stu-id="668e4-138">**Default Field Set**</span></span>|||  
|<span data-ttu-id="668e4-139">Comportamento tabella</span><span class="sxs-lookup"><span data-stu-id="668e4-139">Table Behavior</span></span>|||  
  
###  <a name="to-configure-table-property-settings"></a><a name="bkmk_config_prop"></a><span data-ttu-id="668e4-140">Per configurare le impostazioni delle proprietà delle tabelle</span><span class="sxs-lookup"><span data-stu-id="668e4-140">To configure table property settings</span></span>  
  
1.  <span data-ttu-id="668e4-141">In Progettazione modelli, in Vista dati fare clic su una tabella (scheda) oppure in Vista diagramma fare clic su un'intestazione di tabella.</span><span class="sxs-lookup"><span data-stu-id="668e4-141">In the model designer, in Data View, click a table (tab), or, in Diagram View, click a table header.</span></span>  
  
2.  <span data-ttu-id="668e4-142">Nella finestra **Proprietà** fare clic su una proprietà, quindi digitare un valore oppure fare clic sul pulsante per ulteriori opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="668e4-142">In the **Properties** window, click on a property, and then type a value or click the button for additional configuration options.</span></span>  
  
  
