---
title: Editor trasformazione Ricerca fuzzy (scheda Avanzate) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzylookuptransformation.advanced.f1
helpviewer_keywords:
- Fuzzy Lookup Transformation Editor
ms.assetid: 0a2919be-2ea7-4c06-82b8-0ffad5f0dd83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 68f53eb2735dc07656fc8ff2b81c3259caa4847b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713311"
---
# <a name="fuzzy-lookup-transformation-editor-advanced-tab"></a><span data-ttu-id="a3147-102">Editor trasformazione Ricerca fuzzy (scheda Avanzate)</span><span class="sxs-lookup"><span data-stu-id="a3147-102">Fuzzy Lookup Transformation Editor (Advanced Tab)</span></span>
  <span data-ttu-id="a3147-103">Usare la scheda **Avanzate** della finestra di dialogo **Editor trasformazione Ricerca fuzzy** per impostare i parametri relativi alla ricerca fuzzy.</span><span class="sxs-lookup"><span data-stu-id="a3147-103">Use the **Advanced** tab of the **Fuzzy Lookup Transformation Editor** dialog box to set parameters for the fuzzy lookup.</span></span>  
  
 <span data-ttu-id="a3147-104">Per ulteriori informazioni sulla trasformazione Ricerca fuzzy, vedere [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="a3147-104">To learn more about the Fuzzy Lookup transformation, see [Fuzzy Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="a3147-105">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a3147-105">Options</span></span>  
 <span data-ttu-id="a3147-106">**Numero massimo di corrispondenze da restituire per ricerca**</span><span class="sxs-lookup"><span data-stu-id="a3147-106">**Maximum number of matches to output per lookup**</span></span>  
 <span data-ttu-id="a3147-107">Consente di specificare il numero massimo di corrispondenze restituite dalla trasformazione per ogni riga di input.</span><span class="sxs-lookup"><span data-stu-id="a3147-107">Specify the maximum number of matches the transformation can return for each input row.</span></span> <span data-ttu-id="a3147-108">L'impostazione predefinita è **1**.</span><span class="sxs-lookup"><span data-stu-id="a3147-108">The default is **1**.</span></span>  
  
 <span data-ttu-id="a3147-109">**Soglia di somiglianza**</span><span class="sxs-lookup"><span data-stu-id="a3147-109">**Similarity threshold**</span></span>  
 <span data-ttu-id="a3147-110">Consente di impostare la soglia di somiglianza a livello di componente mediante il dispositivo di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="a3147-110">Set the similarity threshold at the component level by using the slider.</span></span> <span data-ttu-id="a3147-111">Più il valore è vicino a 1, maggiore deve essere la somiglianza tra il valore di ricerca e il valore di origine per essere considerata una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="a3147-111">The closer the value is to 1, the closer the resemblance of the lookup value to the source value must be to qualify as a match.</span></span> <span data-ttu-id="a3147-112">L'aumento della soglia può migliorare la velocità di confronto, poiché verrà considerato un numero minore di record candidati.</span><span class="sxs-lookup"><span data-stu-id="a3147-112">Increasing the threshold can improve the speed of matching since fewer candidate records need to be considered.</span></span>  
  
 <span data-ttu-id="a3147-113">**Delimitatori token**</span><span class="sxs-lookup"><span data-stu-id="a3147-113">**Token delimiters**</span></span>  
 <span data-ttu-id="a3147-114">Consente di specificare i delimitatori utilizzati dalla trasformazione per suddividere in token i valori delle colonne.</span><span class="sxs-lookup"><span data-stu-id="a3147-114">Specify the delimiters that the transformation uses to tokenize column values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3147-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3147-115">See Also</span></span>  
 <span data-ttu-id="a3147-116">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a3147-116">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="a3147-117">[Editor trasformazione Ricerca fuzzy &#40;scheda tabella di riferimento&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span><span class="sxs-lookup"><span data-stu-id="a3147-117">[Fuzzy Lookup Transformation Editor &#40;Reference Table Tab&#41;](../../2014/integration-services/fuzzy-lookup-transformation-editor-reference-table-tab.md) </span></span>  
 [<span data-ttu-id="a3147-118">Editor trasformazione Ricerca fuzzy &#40;scheda Colonne&#41;</span><span class="sxs-lookup"><span data-stu-id="a3147-118">Fuzzy Lookup Transformation Editor &#40;Columns Tab&#41;</span></span>](../../2014/integration-services/fuzzy-lookup-transformation-editor-columns-tab.md)  
  
  
