---
title: Selezione membri (configurazione guidata funzionalità di Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.memberconversion.f1
ms.assetid: 1a147461-d594-41e7-a41d-09d2d003e1e0
author: minewiskan
ms.author: owend
ms.openlocfilehash: fd5f184e0d9670725609531b6d0a101f8e7f8647
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626333"
---
# <a name="select-members-business-intelligence-wizard"></a><span data-ttu-id="0fe82-102">Selezione membri (Configurazione guidata funzionalità di Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="0fe82-102">Select Members (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="0fe82-103">Utilizzare la pagina **Selezione membri** per determinare i membri ai quali, durante la Configurazione guidata funzionalità di Business Intelligence, dovrà essere applicata la funzionalità di conversione valuta specificata nella pagina **Impostazione opzioni di conversione valuta** .</span><span class="sxs-lookup"><span data-stu-id="0fe82-103">Use the **Select Members** page to determine to which members the Business Intelligence Wizard should apply the currency conversion functionality specified on the **Set Currency Conversion Options** page.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0fe82-104">Questa pagina non viene visualizzata se la Configurazione guidata funzionalità di Business Intelligence viene avviata da Progettazione dimensioni oppure facendo clic con il pulsante destro del mouse su una dimensione in Esplora soluzioni in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0fe82-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="0fe82-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="0fe82-105">Options</span></span>  
 <span data-ttu-id="0fe82-106">**Dimensione di tipo misure**</span><span class="sxs-lookup"><span data-stu-id="0fe82-106">**Measures dimension**</span></span>  
 <span data-ttu-id="0fe82-107">Consente di applicare la funzionalità di conversione valuta a una o più misure nel cubo.</span><span class="sxs-lookup"><span data-stu-id="0fe82-107">Select to apply the currency conversion functionality to one or more measures in the cube.</span></span>  
  
 <span data-ttu-id="0fe82-108">Se selezionata, nella griglia vengono visualizzate le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0fe82-108">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="0fe82-109">Opzione</span><span class="sxs-lookup"><span data-stu-id="0fe82-109">Option</span></span>|<span data-ttu-id="0fe82-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fe82-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0fe82-111">**Tipi di misure predefiniti**</span><span class="sxs-lookup"><span data-stu-id="0fe82-111">**Built-in Measure Types**</span></span>|<span data-ttu-id="0fe82-112">Consente di includere la funzionalità di conversione valuta per la misura specificata.</span><span class="sxs-lookup"><span data-stu-id="0fe82-112">Select to include currency conversion functionality for the specified measure.</span></span>|  
|<span data-ttu-id="0fe82-113">**Misure**</span><span class="sxs-lookup"><span data-stu-id="0fe82-113">**Measures**</span></span>|<span data-ttu-id="0fe82-114">Consente di selezionare la misura nel gruppo di misure di tipo Tasso che contiene il tasso di cambio da usare quando la misura selezionata in **Tipi di misure predefiniti** viene convertita.</span><span class="sxs-lookup"><span data-stu-id="0fe82-114">Select the measure from the rate measure group that contains the exchange rate to use when the measure selected in **Built-in Measure Types** is converted.</span></span>|  
  
 <span data-ttu-id="0fe82-115">**Gerarchia conto**</span><span class="sxs-lookup"><span data-stu-id="0fe82-115">**Account hierarchy**</span></span>  
 <span data-ttu-id="0fe82-116">Consente di applicare la funzionalità di conversione valuta a uno o più membri nella gerarchia conto della dimensione di tipo Conti inclusa nel cubo.</span><span class="sxs-lookup"><span data-stu-id="0fe82-116">Select to apply the currency conversion functionality to one or more members in the account hierarchy of the account dimension included in the cube.</span></span> <span data-ttu-id="0fe82-117">La gerarchia di account è la gerarchia all'interno della dimensione di tipo conto la cui `Type` proprietà è impostata su *account*.</span><span class="sxs-lookup"><span data-stu-id="0fe82-117">The account hierarchy is the hierarchy within the account dimension whose `Type` property is set to *Account*.</span></span>  
  
 <span data-ttu-id="0fe82-118">Se selezionata, nella griglia vengono visualizzate le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0fe82-118">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="0fe82-119">Opzione</span><span class="sxs-lookup"><span data-stu-id="0fe82-119">Option</span></span>|<span data-ttu-id="0fe82-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fe82-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0fe82-121">**Membro conto**</span><span class="sxs-lookup"><span data-stu-id="0fe82-121">**Account Member**</span></span>|<span data-ttu-id="0fe82-122">Consente di includere la funzionalità di conversione valuta per il membro della gerarchia conto specificato.</span><span class="sxs-lookup"><span data-stu-id="0fe82-122">Select to include currency conversion functionality for the specified member of the account hierarchy.</span></span>|  
|<span data-ttu-id="0fe82-123">**Misure**</span><span class="sxs-lookup"><span data-stu-id="0fe82-123">**Measures**</span></span>|<span data-ttu-id="0fe82-124">Consente di selezionare la misura nel gruppo di misure di tipo Tasso che contiene il tasso di cambio da utilizzare quando le misure per il membro selezionato in **Membro conto** vengono convertite.</span><span class="sxs-lookup"><span data-stu-id="0fe82-124">Select the measure from the rate measure group that contains the exchange rate to use when the measures for the member selected in **Account Member** are converted.</span></span>|  
  
 <span data-ttu-id="0fe82-125">**Gerarchia conto basata sul tipo**</span><span class="sxs-lookup"><span data-stu-id="0fe82-125">**Account hierarchy based on type**</span></span>  
 <span data-ttu-id="0fe82-126">Consente di applicare la funzionalità di conversione valuta a tutti i membri di attributi inclusi nella gerarchia conto la cui proprietà `Type` è impostata su un tipo di conto specificato.</span><span class="sxs-lookup"><span data-stu-id="0fe82-126">Select to apply the currency conversion functionality to all members of attributes in the account hierarchy whose `Type` property is set to a specified account type.</span></span>  
  
 <span data-ttu-id="0fe82-127">Se selezionata, nella griglia vengono visualizzate le opzioni elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0fe82-127">If selected, the grid displays the options listed in the following table.</span></span>  
  
|<span data-ttu-id="0fe82-128">Opzione</span><span class="sxs-lookup"><span data-stu-id="0fe82-128">Option</span></span>|<span data-ttu-id="0fe82-129">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0fe82-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0fe82-130">**Tipo di account**</span><span class="sxs-lookup"><span data-stu-id="0fe82-130">**Account Type**</span></span>|<span data-ttu-id="0fe82-131">Consente di includere la funzionalità di conversione valuta per il tipo di conto specificato.</span><span class="sxs-lookup"><span data-stu-id="0fe82-131">Select to include currency conversion functionality for the specified account type.</span></span>|  
|<span data-ttu-id="0fe82-132">**Misure**</span><span class="sxs-lookup"><span data-stu-id="0fe82-132">**Measures**</span></span>|<span data-ttu-id="0fe82-133">Consente di selezionare la misura nel gruppo di misure di tipo Tasso che contiene il tasso di cambio da utilizzare quando le misure per i membri degli attributi che utilizzano il tipo di conto selezionato in **Tipo conto** vengono convertite.</span><span class="sxs-lookup"><span data-stu-id="0fe82-133">Select the measure from the rate measure group that contains the exchange rate to use when measures for the members of attributes using the account type selected in **Account Type** are converted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fe82-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fe82-134">See Also</span></span>  
 <span data-ttu-id="0fe82-135">[Guida sensibile al contesto della configurazione guidata funzionalità di Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="0fe82-135">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="0fe82-136">[Progettazione cubi &#40;Analysis Services-Dati multidimensionali&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="0fe82-136">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="0fe82-137">Progettazione dimensioni &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="0fe82-137">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
