---
title: Opzioni attributi cronologici (Configurazione guidata dimensioni a modifica lenta) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.histattriboption.f1
ms.assetid: a176ec66-ec39-4c99-99d1-c1afa8450e1e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fad005d6b8f80973abeb47dd881ef02b669d7b27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636319"
---
# <a name="historical-attribute-options-slowly-changing-dimension-wizard"></a><span data-ttu-id="867e3-102">Opzioni attributi cronologici (Configurazione guidata dimensioni a modifica lenta)</span><span class="sxs-lookup"><span data-stu-id="867e3-102">Historical Attribute Options (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="867e3-103">Utilizzare la finestra di dialogo **Opzioni attributi cronologici** per visualizzare gli attributi cronologici in base a date di inizio e fine o per registrare gli attributi cronologici in una colonna creata appositamente a questo scopo.</span><span class="sxs-lookup"><span data-stu-id="867e3-103">Use the **Historical Attributes Options** dialog box to show historical attributes by start and end dates, or to record historical attributes in a column specially created for this purpose.</span></span>  
  
 <span data-ttu-id="867e3-104">Per ulteriori informazioni su questa procedura guidata, vedere [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="867e3-104">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="867e3-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="867e3-105">Options</span></span>  
 <span data-ttu-id="867e3-106">**Usa una singola colonna per mostrare i record correnti e scaduti**</span><span class="sxs-lookup"><span data-stu-id="867e3-106">**Use a single column to show current and expired records**</span></span>  
 <span data-ttu-id="867e3-107">Se si sceglie di utilizzare una sola colonna per registrare lo stato degli attributi cronologici, saranno disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="867e3-107">If you choose to use a single column to record the status of historical attributes, the following options are available:</span></span>  
  
|<span data-ttu-id="867e3-108">Opzione</span><span class="sxs-lookup"><span data-stu-id="867e3-108">Option</span></span>|<span data-ttu-id="867e3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="867e3-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="867e3-110">**Colonna per l'indicazione del record corrente**</span><span class="sxs-lookup"><span data-stu-id="867e3-110">**Column to indicate current record**</span></span>|<span data-ttu-id="867e3-111">Consente di selezionare una colonna da utilizzare per l'indicazione del record corrente.</span><span class="sxs-lookup"><span data-stu-id="867e3-111">Select a column in which to indicate the current record.</span></span>|  
|<span data-ttu-id="867e3-112">**Valore se corrente**</span><span class="sxs-lookup"><span data-stu-id="867e3-112">**Value when current**</span></span>|<span data-ttu-id="867e3-113">Utilizzare **Vero** o **Corrente** per indicare se si tratta del record corrente.</span><span class="sxs-lookup"><span data-stu-id="867e3-113">Use either **True** or **Current** to show whether the record is current.</span></span>|  
|<span data-ttu-id="867e3-114">**Valore se scaduto**</span><span class="sxs-lookup"><span data-stu-id="867e3-114">**Expiration value**</span></span>|<span data-ttu-id="867e3-115">Utilizzare **Falso** o **Scaduto** per indicare se il record è un valore cronologico.</span><span class="sxs-lookup"><span data-stu-id="867e3-115">Use either **False** or **Expired** to show whether the record is a historical value.</span></span>|  
  
 <span data-ttu-id="867e3-116">**Usa colonne Data inizio e Data fine per identificare i record correnti e scaduti**</span><span class="sxs-lookup"><span data-stu-id="867e3-116">**Use start and end dates to identify current and expired records**</span></span>  
 <span data-ttu-id="867e3-117">La tabella della dimensione per questa opzione deve includere una colonna data.</span><span class="sxs-lookup"><span data-stu-id="867e3-117">The dimension table for this option must include a date column.</span></span> <span data-ttu-id="867e3-118">Se si sceglie di visualizzare gli attributi cronologici in base alle date di inizio e fine, saranno disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="867e3-118">If you choose to show historical attributes by start and end dates, the following options are available:</span></span>  
  
|<span data-ttu-id="867e3-119">Opzione</span><span class="sxs-lookup"><span data-stu-id="867e3-119">Option</span></span>|<span data-ttu-id="867e3-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="867e3-120">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="867e3-121">**Colonna Data inizio**</span><span class="sxs-lookup"><span data-stu-id="867e3-121">**Start date column**</span></span>|<span data-ttu-id="867e3-122">Consente di selezionare la colonna della tabella della dimensione che conterrà la data di inizio.</span><span class="sxs-lookup"><span data-stu-id="867e3-122">Select the column in the dimension table to contain the start date.</span></span>|  
|<span data-ttu-id="867e3-123">**Colonna Data fine**</span><span class="sxs-lookup"><span data-stu-id="867e3-123">**End date column**</span></span>|<span data-ttu-id="867e3-124">Consente di selezionare la colonna della tabella della dimensione che conterrà la data di fine.</span><span class="sxs-lookup"><span data-stu-id="867e3-124">Select the column in the dimension table to contain the end date.</span></span>|  
|<span data-ttu-id="867e3-125">**Variabile per l'impostazione dei valori di data**</span><span class="sxs-lookup"><span data-stu-id="867e3-125">**Variable to set date values**</span></span>|<span data-ttu-id="867e3-126">Consente di selezionare una variabile per la data nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="867e3-126">Select a date variable from the list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="867e3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="867e3-127">See Also</span></span>  
 [<span data-ttu-id="867e3-128">Configurare gli output tramite Configurazione guidata dimensioni a modifica lenta</span><span class="sxs-lookup"><span data-stu-id="867e3-128">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
