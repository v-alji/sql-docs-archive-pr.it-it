---
title: Finestra di dialogo Proprietà set di dati, Parametri | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10150"
- sql12.rtp.rptdesigner.datasetproperties.parameters.f1
ms.assetid: 43b00aab-e2c3-4e85-abe1-a2b5a21efeed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0073971de373321ce347f416657671e1f497dd1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726571"
---
# <a name="dataset-properties-dialog-box-parameters"></a><span data-ttu-id="9b98a-102">Finestra di dialogo Proprietà set di dati, Parametri</span><span class="sxs-lookup"><span data-stu-id="9b98a-102">Dataset Properties Dialog Box, Parameters</span></span>
  <span data-ttu-id="9b98a-103">Selezionare **Parametri** nella finestra di dialogo **Proprietà set di dati** per aggiungere, modificare ed eliminare parametri di query, inclusi quelli collegati a parametri del report.</span><span class="sxs-lookup"><span data-stu-id="9b98a-103">Select **Parameters** on the **Dataset Properties** dialog box to add, change, and delete query parameters, including query parameters that link to report parameters.</span></span>  
  
 <span data-ttu-id="9b98a-104">Ogni volta che la query viene modificata nella relativa scheda, il comando della query viene analizzato.</span><span class="sxs-lookup"><span data-stu-id="9b98a-104">Whenever the query is changed on the query tab, the query command is parsed.</span></span> <span data-ttu-id="9b98a-105">Per ogni parametro di query identificato, viene creato un parametro del report con un nome identico con distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="9b98a-105">For each query parameter that is identified, a report parameter with an identical case-sensitive name is created.</span></span> <span data-ttu-id="9b98a-106">Per impostazione predefinita, il parametro di query viene aggiunto automaticamente all'elenco dei parametri di query e collegato al parametro del report corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9b98a-106">By default, the query parameter is automatically added to the query parameter list and linked to the corresponding report parameter.</span></span>  
  
 <span data-ttu-id="9b98a-107">In caso di dipendenze dei valori predefiniti di un parametro del report da un altro parametro del report collegato a un parametro di query, l'ordine dei parametri del report visualizzati nella finestra di dialogo **Proprietà parametri report** risulta importante.</span><span class="sxs-lookup"><span data-stu-id="9b98a-107">If there are dependencies for the default values of one report parameter on another report parameter that is linked to a query parameter, the order of report parameters (as they appear in the **Report Parameters Properties** dialog box) is important.</span></span> <span data-ttu-id="9b98a-108">I parametri del report che vengono dopo nell'elenco possono fare riferimento a parametri che vengono prima.</span><span class="sxs-lookup"><span data-stu-id="9b98a-108">Report parameters later in the list can refer to report parameters earlier in the list.</span></span> <span data-ttu-id="9b98a-109">Per altre informazioni sui parametri report, vedere [Parametri report &#40;Generatore report e Progettazione report&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="9b98a-109">For more information about report parameters, see [Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9b98a-110">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9b98a-110">Options</span></span>  
 <span data-ttu-id="9b98a-111">**Aggiungere**</span><span class="sxs-lookup"><span data-stu-id="9b98a-111">**Add**</span></span>  
 <span data-ttu-id="9b98a-112">Consente di aggiungere un nuovo parametro all'elenco.</span><span class="sxs-lookup"><span data-stu-id="9b98a-112">Add a new parameter to the list.</span></span>  
  
 <span data-ttu-id="9b98a-113">**Elimina**</span><span class="sxs-lookup"><span data-stu-id="9b98a-113">**Delete**</span></span>  
 <span data-ttu-id="9b98a-114">Consente di rimuovere il parametro selezionato dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="9b98a-114">Remove the selected parameter from the list.</span></span>  
  
 <span data-ttu-id="9b98a-115">**Nome parametro**</span><span class="sxs-lookup"><span data-stu-id="9b98a-115">**Parameter name**</span></span>  
 <span data-ttu-id="9b98a-116">Digitare il nome di un parametro di query aggiunto al set di dati nella scheda **Query** della finestra di dialogo **Proprietà set di dati** .</span><span class="sxs-lookup"><span data-stu-id="9b98a-116">Type the name of a query parameter that you added to the dataset on the **Query** tab of the **Dataset Properties** dialog box.</span></span>  
  
 <span data-ttu-id="9b98a-117">**Valore del parametro**</span><span class="sxs-lookup"><span data-stu-id="9b98a-117">**Parameter value**</span></span>  
 <span data-ttu-id="9b98a-118">Immettere un valore per il parametro di query.</span><span class="sxs-lookup"><span data-stu-id="9b98a-118">Enter a value for the query parameter.</span></span> <span data-ttu-id="9b98a-119">Può trattarsi di un valore statico o di un'espressione che fa riferimento a un oggetto nel report, ma non a un campo o a un elemento del report.</span><span class="sxs-lookup"><span data-stu-id="9b98a-119">This can be a static value or an expression that refers to an object within the report, but it cannot refer to any report items or fields.</span></span> <span data-ttu-id="9b98a-120">Per impostazione predefinita, in **Valore** è contenuta un'espressione che punta a un parametro del report.</span><span class="sxs-lookup"><span data-stu-id="9b98a-120">By default, **Value** contains an expression that points to a report parameter.</span></span>  
  
 <span data-ttu-id="9b98a-121">**Freccia in su**</span><span class="sxs-lookup"><span data-stu-id="9b98a-121">**Up arrow**</span></span>  
 <span data-ttu-id="9b98a-122">Consente di spostare il parametro selezionato verso l'alto nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9b98a-122">Move the selected parameter up in the list.</span></span>  
  
 <span data-ttu-id="9b98a-123">**Freccia GIÙ**</span><span class="sxs-lookup"><span data-stu-id="9b98a-123">**Down arrow**</span></span>  
 <span data-ttu-id="9b98a-124">Consente di spostare il parametro selezionato verso il basso nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9b98a-124">Move the selected parameter down in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b98a-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b98a-125">See Also</span></span>  
 <span data-ttu-id="9b98a-126">[Parametri report &#40;Generatore report e Progettazione report&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="9b98a-126">[Report Parameters &#40;Report Builder and Report Designer&#41;](../report-design/report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="9b98a-127">[Aggiungere dati a un report &#40;Generatore report e SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="9b98a-127">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="9b98a-128">Modificare l'ordine di un parametro del report &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b98a-128">Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](../report-design/change-the-order-of-a-report-parameter-report-builder-and-ssrs.md)  
  
  
