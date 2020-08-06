---
title: Configurazione attributi dimensione (configurazione guidata funzionalità di Business Intelligence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.biwizard.acctintelligence.selectattributes.f1
ms.assetid: 3d046e63-bcb1-4ab1-9c37-652463fa68c3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1d2e9bc83b7a6d83b6d2808b472d67169266ff07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625750"
---
# <a name="configure-dimension-attributes-business-intelligence-wizard"></a><span data-ttu-id="e5c46-102">Configurazione attributi dimensione (Configurazione guidata funzionalità di Business Intelligence)</span><span class="sxs-lookup"><span data-stu-id="e5c46-102">Configure Dimension Attributes (Business Intelligence Wizard)</span></span>
  <span data-ttu-id="e5c46-103">Utilizzare la pagina **Configurazione attributi dimensione** per eseguire il mapping tra gli attributi di dimensione e i tipi di attributo utilizzati da [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] per identificare gli attributi per le dimensioni di tipo Conto.</span><span class="sxs-lookup"><span data-stu-id="e5c46-103">Use the **Configure Dimension Attributes** page to map the dimension attributes to the attribute types that [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] uses to identify attributes for account dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="e5c46-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e5c46-104">Options</span></span>  
 <span data-ttu-id="e5c46-105">**Tipo dimensione**</span><span class="sxs-lookup"><span data-stu-id="e5c46-105">**Dimension type**</span></span>  
 <span data-ttu-id="e5c46-106">Consente di visualizzare il tipo di dimensione selezionato.</span><span class="sxs-lookup"><span data-stu-id="e5c46-106">Displays the selected dimension type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5c46-107">Questa opzione non è disponibile perché la `Type` proprietà della dimensione non può essere modificata in un valore diverso da *account* per le dimensioni di tipo conto.</span><span class="sxs-lookup"><span data-stu-id="e5c46-107">This option is not available because the `Type` property of the dimension cannot be changed to a value other than *Account* for account dimensions.</span></span>  
  
 <span data-ttu-id="e5c46-108">**Attributi dimensione**</span><span class="sxs-lookup"><span data-stu-id="e5c46-108">**Dimension attributes**</span></span>  
 <span data-ttu-id="e5c46-109">Consente di visualizzare i tipi di attributo validi di cui è possibile eseguire il mapping agli attributi della dimensione esistenti.</span><span class="sxs-lookup"><span data-stu-id="e5c46-109">Displays the valid attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="e5c46-110">**Includere**</span><span class="sxs-lookup"><span data-stu-id="e5c46-110">**Include**</span></span>  
 <span data-ttu-id="e5c46-111">Selezionare una casella di controllo per includere nella dimensione il tipo di attributo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e5c46-111">Select a check box to include the corresponding attribute type in the dimension.</span></span>  
  
 <span data-ttu-id="e5c46-112">**Tipo di attributo**</span><span class="sxs-lookup"><span data-stu-id="e5c46-112">**Attribute Type**</span></span>  
 <span data-ttu-id="e5c46-113">Consente di visualizzare i tipi di attributo di cui è possibile eseguire il mapping agli attributi della dimensione esistenti.</span><span class="sxs-lookup"><span data-stu-id="e5c46-113">Lists the attribute types that can be mapped to existing dimension attributes in the dimension.</span></span>  
  
 <span data-ttu-id="e5c46-114">**Attributo dimensione**</span><span class="sxs-lookup"><span data-stu-id="e5c46-114">**Dimension Attribute**</span></span>  
 <span data-ttu-id="e5c46-115">Consente di selezionare l'attributo della dimensione di cui è necessario eseguire il mapping al tipo di attributo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="e5c46-115">Select the dimension attribute that should be mapped to the corresponding attribute type.</span></span>  
  
 <span data-ttu-id="e5c46-116">**Imposta misure semiadditive in base al tipo di conto**</span><span class="sxs-lookup"><span data-stu-id="e5c46-116">**Set measures to be semiadditive based on account type**</span></span>  
 <span data-ttu-id="e5c46-117">Selezionare questa opzione per modificare ogni misura associata alla dimensione corrente da aggregare in base al tipo di conto.</span><span class="sxs-lookup"><span data-stu-id="e5c46-117">Select to change every measure associated with this dimension to be aggregated by account type.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e5c46-118">Questa opzione non viene visualizzata se la Configurazione guidata funzionalità di Business Intelligence è stata avviata da Progettazione dimensioni oppure facendo clic con il pulsante destro del mouse su una dimensione in Esplora soluzioni in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e5c46-118">This option does not appear if the Business Intelligence Wizard was started from Dimension Designer or by right-clicking a dimension in Solution Explorer in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c46-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5c46-119">See Also</span></span>  
 <span data-ttu-id="e5c46-120">[Guida sensibile al contesto della configurazione guidata funzionalità di Business Intelligence](business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="e5c46-120">[Business Intelligence Wizard F1 Help](business-intelligence-wizard-f1-help.md) </span></span>  
 <span data-ttu-id="e5c46-121">[Progettazione cubi &#40;Analysis Services-Dati multidimensionali&#41;](cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e5c46-121">[Cube Designer &#40;Analysis Services - Multidimensional Data&#41;](cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e5c46-122">Progettazione dimensioni &#40;Analysis Services-Dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="e5c46-122">Dimension Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](dimension-designer-analysis-services-multidimensional-data.md)  
  
  
