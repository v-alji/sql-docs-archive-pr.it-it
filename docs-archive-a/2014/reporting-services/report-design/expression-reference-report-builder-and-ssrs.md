---
title: Riferimento dell'espressione (Generatore report e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: bb16e4ab-b13f-48f2-8cfe-1851656875ef
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7854aa2cc256d63fe93ddb049486e782bfaa0e11
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627111"
---
# <a name="expression-reference-report-builder-and-ssrs"></a><span data-ttu-id="a28c3-102">Riferimento dell'espressione (Generatore report e SSRS)</span><span class="sxs-lookup"><span data-stu-id="a28c3-102">Expression Reference (Report Builder and SSRS)</span></span>
  <span data-ttu-id="a28c3-103">Le espressioni del report supportano vari riferimenti a funzioni e raccolte predefinite.</span><span class="sxs-lookup"><span data-stu-id="a28c3-103">Report expressions support a variety of references to built-in functions and built-in collections.</span></span> <span data-ttu-id="a28c3-104">Le espressioni devono disporre di sintassi [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] valida prima che un report possa essere pubblicato o elaborato.</span><span class="sxs-lookup"><span data-stu-id="a28c3-104">Expressions must have valid [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] syntax before a report can be published or processed.</span></span>  
  
 <span data-ttu-id="a28c3-105">Per sviluppare espressioni complesse o espressioni che consentono l'utilizzo di codice o assembly personalizzati, si consiglia di usare Progettazione report di [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a28c3-105">To develop complex expressions or expressions that use custom code or custom assemblies, we recommend that you use Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="a28c3-106">Per altre informazioni, vedere [Riferimenti a codice personalizzato e ad assembly in espressioni in Progettazione report &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)sottostante.</span><span class="sxs-lookup"><span data-stu-id="a28c3-106">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
 <span data-ttu-id="a28c3-107">Usare gli argomenti di questa sezione per la scrittura di espressioni semplici incluse in un report.</span><span class="sxs-lookup"><span data-stu-id="a28c3-107">Use the topics in this section to help write simple expressions in a report.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a28c3-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a28c3-108">In This Section</span></span>  
 [<span data-ttu-id="a28c3-109">Tipi di dati nelle espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-109">Data Types in Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="a28c3-110">Costanti nelle espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-110">Constants in Expressions &#40;Report Builder and SSRS&#41;</span></span>](constants-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="a28c3-111">Operatori nelle espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-111">Operators in Expressions &#40;Report Builder and SSRS&#41;</span></span>](operators-in-expressions-report-builder-and-ssrs.md)  
  
 [<span data-ttu-id="a28c3-112">Raccolte predefinite nelle espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-112">Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-in-expressions-report-builder.md)  
  
 [<span data-ttu-id="a28c3-113">Riferimenti alle raccolte predefinite Globals e Users &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-113">Built-in Globals and Users References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-built-in-globals-and-users-references-report-builder.md)  
  
 [<span data-ttu-id="a28c3-114">Riferimenti alla raccolta dei parametri &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-114">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
 [<span data-ttu-id="a28c3-115">Riferimenti alla raccolta di campi del set di dati &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-115">Dataset Fields Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-dataset-fields-collection-references-report-builder.md)  
  
 [<span data-ttu-id="a28c3-116">Riferimenti a raccolte DataSources e DataSets &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-116">DataSources and DataSets Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-datasources-and-datasets-references-report-builder.md)  
  
 [<span data-ttu-id="a28c3-117">Riferimenti a raccolte di variabili di report e di gruppo &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-117">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  
  
 [<span data-ttu-id="a28c3-118">Riferimenti alla raccolta ReportItems &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-118">ReportItems Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-reportitems-collection-references-report-builder.md)  
  
## <a name="see-also"></a><span data-ttu-id="a28c3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a28c3-119">See Also</span></span>  
 [<span data-ttu-id="a28c3-120">Espressioni &#40;Generatore report e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a28c3-120">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)  
  
  
