---
title: Impostazione opzioni di conversione valuta (configurazione guidata funzionalità di Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.currencyconversion.calculationsettings.f1
ms.assetid: a49d4e1f-bdda-4a83-ab4f-ce8c500e1d6d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 61877deb0bc422d65f977e3fc9de3e678f7d8477
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721835"
---
# <a name="set-currency-conversion-options-business-intelligence-wizard"></a><span data-ttu-id="3a10b-102">Impostazione opzioni di conversione valuta (Configurazione guidata funzionalità di Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="3a10b-102">Set Currency Conversion Options (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="3a10b-103">Utilizzare la pagina **Impostazione opzioni di conversione valuta** per definire i calcoli di conversione della valuta per un gruppo di misure contenente tassi di cambio.</span><span class="sxs-lookup"><span data-stu-id="3a10b-103">Use the **Set Currency Conversion** page to define currency conversion calculations for a measure group that contains exchange rates.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a10b-104">Questa pagina non viene visualizzata se la Configurazione guidata funzionalità di Business Intelligence viene avviata da Progettazione dimensioni oppure facendo clic con il pulsante destro del mouse su una dimensione in Esplora soluzioni in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a10b-104">This page does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="3a10b-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3a10b-105">Options</span></span>  
 <span data-ttu-id="3a10b-106">**Selezionare il gruppo di misure in cui sono contenuti i tassi di cambio**</span><span class="sxs-lookup"><span data-stu-id="3a10b-106">**Select the measure group that contains exchange rates**</span></span>  
 <span data-ttu-id="3a10b-107">Consente di selezionare il gruppo di misure che contiene i tassi di cambio a cui devono fare riferimento i calcoli di conversione della valuta.</span><span class="sxs-lookup"><span data-stu-id="3a10b-107">Select the measure group that contains the exchange rates that the currency conversion calculations should reference.</span></span>  
  
 <span data-ttu-id="3a10b-108">**Specificare la valuta pivot**</span><span class="sxs-lookup"><span data-stu-id="3a10b-108">**Specify the pivot currency**</span></span>  
 <span data-ttu-id="3a10b-109">Consente di selezionare il membro che costituisce la valuta pivot per il gruppo di misure.</span><span class="sxs-lookup"><span data-stu-id="3a10b-109">Select the member that serves as the pivot currency for the measure group.</span></span>  
  
 <span data-ttu-id="3a10b-110">**Specificare come sono stati immessi i tassi di cambio (selezionare una valuta di esempio)**</span><span class="sxs-lookup"><span data-stu-id="3a10b-110">**Select how you entered your exchange rates (select a sample currency)**</span></span>  
 <span data-ttu-id="3a10b-111">Consente di selezionare un membro che rappresenta una valuta di esempio nella dimensione di tipo Valuta per modificare il testo per le opzioni X valuta pivot per 1 valuta di esempio e X valuta di esempio per 1 valuta pivot e migliorare la visualizzazione della direzione del tasso di cambio.</span><span class="sxs-lookup"><span data-stu-id="3a10b-111">Select a member representing a sample currency from the currency dimension to change the text for the X pivot currency per 1 sample currency and X sample currency per 1 pivot currency options to better display the exchange rate direction.</span></span>  
  
 <span data-ttu-id="3a10b-112">**X valuta pivot per 1 valuta di esempio**</span><span class="sxs-lookup"><span data-stu-id="3a10b-112">**X pivot currency per 1 sample currency**</span></span>  
 <span data-ttu-id="3a10b-113">Selezionare questa opzione per indicare che i tassi di cambio nel gruppo di misure di tipo Tasso rappresentano un moltiplicatore per la valuta pivot specificata.</span><span class="sxs-lookup"><span data-stu-id="3a10b-113">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified pivot currency.</span></span>  
  
 <span data-ttu-id="3a10b-114">**X valuta di esempio per 1 valuta pivot**</span><span class="sxs-lookup"><span data-stu-id="3a10b-114">**X sample currency per 1 pivot currency**</span></span>  
 <span data-ttu-id="3a10b-115">Selezionare questa opzione per indicare che i tassi di cambio nel gruppo di misure di tipo Tasso rappresentano un moltiplicatore per la valuta di esempio specificata.</span><span class="sxs-lookup"><span data-stu-id="3a10b-115">Select to indicate that the exchange rates in the rate measure group represent a multiplier for the specified sample currency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a10b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a10b-116">See Also</span></span>  
 <span data-ttu-id="3a10b-117">[Guida sensibile al contesto della configurazione guidata funzionalità di Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3a10b-117">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="3a10b-118">[Progettazione cubi &#40;Analysis Services-Dati multidimensionali&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3a10b-118">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3a10b-119">Progettazione dimensioni &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="3a10b-119">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
