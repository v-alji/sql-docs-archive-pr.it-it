---
title: Definizione Business Intelligence per la contabilità (configurazione guidata funzionalità di Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.mapaccounttype.f1
ms.assetid: fe4c204b-1031-4ac4-9916-8052ce2301cc
author: minewiskan
ms.author: owend
ms.openlocfilehash: 17b8136e79097cd502d6b239ba6867c4e678c70f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712640"
---
# <a name="define-account-intelligence-business-intelligence-wizard"></a><span data-ttu-id="b5a9e-102">Definizione funzionalità di Business Intelligence per la contabilità (Configurazione guidata funzionalità di Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="b5a9e-102">Define Account Intelligence (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="b5a9e-103">La pagina **Definizione funzionalità di Business Intelligence per la contabilità** consente di eseguire il mapping dei tipi di conto definiti nell'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ai tipi di conto definiti da una tabella di origine nell'origine dei dati che fornisce i dati per la dimensione di tipo Conto.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-103">Use the **Define Account Intelligence** page to map account types defined on the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance to account types defined by a source table in the data source that supplies the data for the account dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5a9e-104">Questa pagina verrà visualizzata se è stato eseguito il mapping di un attributo della dimensione al tipo di attributo **Tipo conto** nella pagina **Configurazione attributi dimensione** .</span><span class="sxs-lookup"><span data-stu-id="b5a9e-104">This page will appear if a dimension attribute was mapped to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5a9e-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="b5a9e-105">Options</span></span>  
 <span data-ttu-id="b5a9e-106">**Tipi di conto tabella di origine**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-106">**Source Table Account Types**</span></span>  
 <span data-ttu-id="b5a9e-107">Consente di visualizzare i valori contenuti nell'attributo della dimensione assegnato al tipo di attributo **Tipo conto** nella pagina **Configurazione attributi dimensione** .</span><span class="sxs-lookup"><span data-stu-id="b5a9e-107">Displays the values that are contained in the dimension attribute assigned to the **Account Type** attribute type on the **Configure Dimension Attributes** page.</span></span>  
  
 <span data-ttu-id="b5a9e-108">**Tipi di conto predefiniti**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-108">**Built-In Account Types**</span></span>  
 <span data-ttu-id="b5a9e-109">Consente di selezionare il tipo di conto definito nell'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] di cui eseguire il mapping ai tipi di conto nella tabella di origine.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-109">Select the account type defined on the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance that maps to the account types in the source table.</span></span>  
  
 <span data-ttu-id="b5a9e-110">Nella tabella seguente vengono elencati i tipi di conto definiti in un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5a9e-110">The following table lists the account types that are defined on an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span>  
  
|<span data-ttu-id="b5a9e-111">Valore</span><span class="sxs-lookup"><span data-stu-id="b5a9e-111">Value</span></span>|<span data-ttu-id="b5a9e-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5a9e-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b5a9e-113">**Asset**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-113">**Asset**</span></span>|<span data-ttu-id="b5a9e-114">Valore degli elementi posseduti in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-114">Value of things owned at a specific time.</span></span>|  
|<span data-ttu-id="b5a9e-115">**Balance**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-115">**Balance**</span></span>|<span data-ttu-id="b5a9e-116">Conteggio di alcuni elementi in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-116">Count of something at a specific time.</span></span>|  
|<span data-ttu-id="b5a9e-117">**Expense**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-117">**Expense**</span></span>|<span data-ttu-id="b5a9e-118">Valore di elementi spesi.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-118">Value of things spent.</span></span>|  
|<span data-ttu-id="b5a9e-119">**Flusso**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-119">**Flow**</span></span>|<span data-ttu-id="b5a9e-120">Conteggio incrementale degli elementi.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-120">Incremental count of things.</span></span>|  
|<span data-ttu-id="b5a9e-121">**Income**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-121">**Income**</span></span>|<span data-ttu-id="b5a9e-122">Valore di elementi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-122">Value of things received.</span></span>|  
|<span data-ttu-id="b5a9e-123">**Liability**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-123">**Liability**</span></span>|<span data-ttu-id="b5a9e-124">Valore degli elementi dovuti in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-124">Value of things owed at a specific time.</span></span>|  
|<span data-ttu-id="b5a9e-125">**Statistiche**</span><span class="sxs-lookup"><span data-stu-id="b5a9e-125">**Statistical**</span></span>|<span data-ttu-id="b5a9e-126">Rapporto calcolato di alcuni elementi oppure conteggio di elementi non aggregabili.</span><span class="sxs-lookup"><span data-stu-id="b5a9e-126">Calculated ratio of something, or count of something that does not aggregate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b5a9e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5a9e-127">See Also</span></span>  
 <span data-ttu-id="b5a9e-128">[Guida sensibile al contesto della configurazione guidata funzionalità di Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="b5a9e-128">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="b5a9e-129">[Progettazione cubi &#40;Analysis Services-Dati multidimensionali&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="b5a9e-129">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="b5a9e-130">Progettazione dimensioni &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="b5a9e-130">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
