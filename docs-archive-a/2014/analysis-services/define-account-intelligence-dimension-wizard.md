---
title: Definizione funzionalità di Business Intelligence per la contabilità (creazione guidata dimensione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dimensionwizard.accountintelligencetypemapping.f1
ms.assetid: cbcff072-3a7e-4e98-858f-1b4265461561
author: minewiskan
ms.author: owend
ms.openlocfilehash: 90871e2299d1531db1b678b1f4b16ddd7f1db767
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635263"
---
# <a name="define-account-intelligence-dimension-wizard"></a><span data-ttu-id="a4ecf-102">Definizione funzionalità di Business Intelligence per la contabilità (Creazione guidata dimensione)</span><span class="sxs-lookup"><span data-stu-id="a4ecf-102">Define Account Intelligence (Dimension Wizard)</span></span>
  <span data-ttu-id="a4ecf-103">La pagina **Funzionalità di Business Intelligence per la contabilità** consente di eseguire il mapping tra i tipi di conto definiti nell'istanza [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] e i tipi di conto definiti nell'attributo della dimensione associato al tipo di attributo **Tipo conto** nella dimensione.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined in the dimension attribute associated with the **Account Type** attribute type in the dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4ecf-104"> Questa pagina viene visualizzata solo se è stata selezionata l'opzione **Dimensione standard** nella pagina **Selezione tipo di dimensione** e se un attributo della dimensione è stato mappato al tipo di attributo **Tipo conto** nella pagina **Impostazione tipo di dimensione** .</span><span class="sxs-lookup"><span data-stu-id="a4ecf-104">This page is displayed only if you selected **Standard dimension** on the **Select the Dimension Type** page and if you mapped a dimension attribute to the **Account Type** attribute type on the **Specify Dimension Type** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a4ecf-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a4ecf-105">Options</span></span>  
 <span data-ttu-id="a4ecf-106">**Tipi di conto tabella di origine**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="a4ecf-107">Visualizza i valori contenuti nell'attributo della dimensione assegnato al tipo di attributo **Tipo conto** nella pagina **Impostazione chiave e tipo della dimensione** .</span><span class="sxs-lookup"><span data-stu-id="a4ecf-107">Displays the values contained in the dimension attribute assigned to the **Account Type** attribute type in the **Specify Dimension Key and Type** page.</span></span>  
  
 <span data-ttu-id="a4ecf-108">**Tipi di conto predefiniti**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="a4ecf-109">Consente di selezionare il tipo di conto definito nell'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] di cui eseguire il mapping ai tipi di conto nella tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="a4ecf-110">Nella tabella seguente vengono elencati i tipi di conto definiti in un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4ecf-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="a4ecf-111">Valore</span><span class="sxs-lookup"><span data-stu-id="a4ecf-111">Value</span></span>|<span data-ttu-id="a4ecf-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4ecf-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4ecf-113">**Asset**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-113">**Asset**</span></span>|<span data-ttu-id="a4ecf-114">Valore degli elementi posseduti in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="a4ecf-115">**Balance**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-115">**Balance**</span></span>|<span data-ttu-id="a4ecf-116">Conteggio di alcuni elementi in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="a4ecf-117">**Expense**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-117">**Expense**</span></span>|<span data-ttu-id="a4ecf-118">Valore di elementi spesi.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-118">Value of things spent.</span></span>|  
|<span data-ttu-id="a4ecf-119">**Flusso**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-119">**Flow**</span></span>|<span data-ttu-id="a4ecf-120">Conteggio incrementale degli elementi.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="a4ecf-121">**Income**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-121">**Income**</span></span>|<span data-ttu-id="a4ecf-122">Valore di elementi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-122">Value of things received.</span></span>|  
|<span data-ttu-id="a4ecf-123">**Liability**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-123">**Liability**</span></span>|<span data-ttu-id="a4ecf-124">Valore degli elementi dovuti in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="a4ecf-125">**Statistiche**</span><span class="sxs-lookup"><span data-stu-id="a4ecf-125">**Statistical**</span></span>|<span data-ttu-id="a4ecf-126">Rapporto calcolato di alcuni elementi oppure conteggio di elementi non aggregabili.</span><span class="sxs-lookup"><span data-stu-id="a4ecf-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4ecf-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4ecf-127">See Also</span></span>  
 <span data-ttu-id="a4ecf-128">[Guida sensibile al contesto della creazione guidata dimensione](dimension-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="a4ecf-128">[Dimension Wizard F1 Help](dimension-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="a4ecf-129">[Dimensioni &#40;Analysis Services Dati multidimensionali&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="a4ecf-129">[Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="a4ecf-130">Dimensioni nei modelli multidimensionali</span><span class="sxs-lookup"><span data-stu-id="a4ecf-130">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
