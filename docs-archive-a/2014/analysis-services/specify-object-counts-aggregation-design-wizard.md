---
title: Impostazione conteggi oggetti (progettazione guidata aggregazioni) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 305d9d79-d1ab-4704-a7b5-3283842b3996
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66b972395f86746b2d08df234db8aa0c71d03fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630089"
---
# <a name="specify-object-counts-aggregation-design-wizard"></a><span data-ttu-id="084ee-102">Impostazione conteggi oggetti (Progettazione guidata aggregazioni)</span><span class="sxs-lookup"><span data-stu-id="084ee-102">Specify Object Counts (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="084ee-103">Utilizzare la pagina **Impostazione conteggi oggetti** per eseguire automaticamente il conteggio degli oggetti nel cubo o per digitare manualmente conteggi stimati.</span><span class="sxs-lookup"><span data-stu-id="084ee-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="084ee-104">La Progettazione guidata aggregazioni utilizza i conteggi degli oggetti per stimare i requisiti di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="084ee-104">The Aggregation Design Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="084ee-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="084ee-105">Options</span></span>  
 <span data-ttu-id="084ee-106">**Oggetti cubo**</span><span class="sxs-lookup"><span data-stu-id="084ee-106">**Cube Objects**</span></span>  
 <span data-ttu-id="084ee-107">Consente di valutare le dimensioni e gli attributi nel cubo.</span><span class="sxs-lookup"><span data-stu-id="084ee-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="084ee-108">Vengono visualizzati solo gli attributi che non hanno la `AggregationUsage` proprietà impostata su `None` nella pagina **verifica utilizzo aggregazioni** della procedura guidata, perché questi sono gli unici attributi che richiedono la specifica dei conteggi.</span><span class="sxs-lookup"><span data-stu-id="084ee-108">Only the attributes that do not have their `AggregationUsage` property set to `None` in the **Review Aggregation Usage** page of the wizard are shown, because those are the only attributes that require the counts to be specified.</span></span>  
  
 <span data-ttu-id="084ee-109">**Conteggio stimato**</span><span class="sxs-lookup"><span data-stu-id="084ee-109">**Estimated count**</span></span>  
 <span data-ttu-id="084ee-110">Viene visualizzato il numero stimato di righe nel gruppo di misure e il numero di membri di attributi stimato nelle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="084ee-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="084ee-111">È possibile digitare un valore da utilizzare come conteggio stimato o è possibile calcolare i totali stimati.</span><span class="sxs-lookup"><span data-stu-id="084ee-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="084ee-112">Per calcolare i valori di conteggio, digitare `0` nel campo e quindi fare clic su **conteggio**.</span><span class="sxs-lookup"><span data-stu-id="084ee-112">To calculate the count values, type `0` in the field and then click **Count**.</span></span> <span data-ttu-id="084ee-113">I campi che presentano già un conteggio non vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="084ee-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="084ee-114">**Numero di partizioni**</span><span class="sxs-lookup"><span data-stu-id="084ee-114">**Partition count**</span></span>  
 <span data-ttu-id="084ee-115">(Facoltativo) Digitare il numero stimato di righe nel gruppo di misure e il numero di membri di attributi stimato nelle dimensioni del database.</span><span class="sxs-lookup"><span data-stu-id="084ee-115">(Optional) Type the estimated number of rows in the measure group and type the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="084ee-116">**Numero**</span><span class="sxs-lookup"><span data-stu-id="084ee-116">**Count**</span></span>  
 <span data-ttu-id="084ee-117">Consente di calcolare e di ripopolare i valori nella colonna **Conteggio stimato** per tutti i campi vuoti.</span><span class="sxs-lookup"><span data-stu-id="084ee-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="084ee-118">I campi che presentano già un conteggio non vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="084ee-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="084ee-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="084ee-119">See Also</span></span>  
 <span data-ttu-id="084ee-120">[Guida sensibile al contesto della progettazione guidata aggregazioni](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="084ee-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="084ee-121">Procedure guidate di Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="084ee-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
