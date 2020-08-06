---
title: Editor destinazione elaborazione dimensione (pagina Gestione connessione) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dimprocessingtransformation.connection.f1
helpviewer_keywords:
- Dimension Processing Destination Editor
ms.assetid: 44aab631-d62d-4895-8fc7-7f1f3b1b68ce
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 50ba42292c1f48c9b1cdf2ba00c709dacd2f9675
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637441"
---
# <a name="dimension-processing-destination-editor-connection-manager-page"></a><span data-ttu-id="99d29-102">Editor destinazione elaborazione dimensione (pagina Gestione connessione)</span><span class="sxs-lookup"><span data-stu-id="99d29-102">Dimension Processing Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="99d29-103">Usare la pagina **Gestione connessione** della finestra di dialogo **Editor destinazione elaborazione dimensione** per specificare una connessione a un progetto di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] o a un'istanza di [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99d29-103">Use the **Connection Manager** page of the **Dimension Processing Destination Editor** dialog box to specify a connection to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project or to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="99d29-104">Per ulteriori informazioni sulla destinazione elaborazione dimensione, vedere [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span><span class="sxs-lookup"><span data-stu-id="99d29-104">To learn more about the Dimension Processing destination, see [Dimension Processing Destination](data-flow/dimension-processing-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="99d29-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="99d29-105">Options</span></span>  
 <span data-ttu-id="99d29-106">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="99d29-106">**Connection manager**</span></span>  
 <span data-ttu-id="99d29-107">Consente di selezionare una gestione connessione esistente nell'elenco o di creare una nuova gestione connessione facendo clic su **Nuova** .</span><span class="sxs-lookup"><span data-stu-id="99d29-107">Select an existing connection manager from the list, or click **New** to create a new connection manager.</span></span>  
  
 <span data-ttu-id="99d29-108">**Nuovo**</span><span class="sxs-lookup"><span data-stu-id="99d29-108">**New**</span></span>  
 <span data-ttu-id="99d29-109">Consente di creare una connessione usando la finestra di dialogo **Aggiungi gestione connessione Analysis Services** .</span><span class="sxs-lookup"><span data-stu-id="99d29-109">Create a new connection by using the **Add Analysis Services Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="99d29-110">**Elenco delle dimensioni disponibili**</span><span class="sxs-lookup"><span data-stu-id="99d29-110">**List of available dimensions**</span></span>  
 <span data-ttu-id="99d29-111">Consente di selezionare la dimensione da elaborare.</span><span class="sxs-lookup"><span data-stu-id="99d29-111">Select the dimension to process.</span></span>  
  
 <span data-ttu-id="99d29-112">**Metodo di elaborazione**</span><span class="sxs-lookup"><span data-stu-id="99d29-112">**Processing method**</span></span>  
 <span data-ttu-id="99d29-113">Consente di selezionare la modalità di elaborazione da applicare alla dimensione selezionata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="99d29-113">Select the processing method to apply to the dimension selected in the list.</span></span> <span data-ttu-id="99d29-114">Il valore predefinito di questa opzione è **Completo**.</span><span class="sxs-lookup"><span data-stu-id="99d29-114">The default value of this option is **Full**.</span></span>  
  
|<span data-ttu-id="99d29-115">Valore</span><span class="sxs-lookup"><span data-stu-id="99d29-115">Value</span></span>|<span data-ttu-id="99d29-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="99d29-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="99d29-117">**Aggiunta (incrementale)**</span><span class="sxs-lookup"><span data-stu-id="99d29-117">**Add (incremental)**</span></span>|<span data-ttu-id="99d29-118">Consente di eseguire un'elaborazione incrementale della dimensione.</span><span class="sxs-lookup"><span data-stu-id="99d29-118">Perform an incremental processing of the dimension.</span></span>|  
|<span data-ttu-id="99d29-119">**Completo**</span><span class="sxs-lookup"><span data-stu-id="99d29-119">**Full**</span></span>|<span data-ttu-id="99d29-120">Consente di eseguire un'elaborazione completa della dimensione.</span><span class="sxs-lookup"><span data-stu-id="99d29-120">Perform full processing of the dimension.</span></span>|  
|<span data-ttu-id="99d29-121">**Aggiornamento**</span><span class="sxs-lookup"><span data-stu-id="99d29-121">**Update**</span></span>|<span data-ttu-id="99d29-122">Consente di eseguire un'elaborazione di aggiornamento della dimensione.</span><span class="sxs-lookup"><span data-stu-id="99d29-122">Perform an update processing of the dimension.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99d29-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99d29-123">See Also</span></span>  
 <span data-ttu-id="99d29-124">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="99d29-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="99d29-125">[Editor destinazione elaborazione dimensione &#40;pagina mapping&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="99d29-125">[Dimension Processing Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/dimension-processing-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="99d29-126">Editor destinazione elaborazione dimensione &#40;pagina Avanzate&#41;</span><span class="sxs-lookup"><span data-stu-id="99d29-126">Dimension Processing Destination Editor &#40;Advanced Page&#41;</span></span>](../../2014/integration-services/dimension-processing-destination-editor-advanced-page.md)  
  
  
