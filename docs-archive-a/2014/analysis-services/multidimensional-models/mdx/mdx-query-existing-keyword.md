---
title: Parola chiave EXISTing (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- EXISTING
helpviewer_keywords:
- Existing keyword
ms.assetid: 651ee9ac-04ef-4316-87c9-a3df5ac27d22
author: minewiskan
ms.author: owend
ms.openlocfilehash: 115444c832fe8fe9b258a0c23b97b97553f32e8e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624391"
---
# <a name="existing-keyword-mdx"></a><span data-ttu-id="34019-102">Parola chiave EXISTING (MDX)</span><span class="sxs-lookup"><span data-stu-id="34019-102">EXISTING Keyword (MDX)</span></span>
  <span data-ttu-id="34019-103">Forza la valutazione di un determinato set all'interno del contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="34019-103">Forces a specified set to be evaluated within the current context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34019-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34019-104">Syntax</span></span>  
  
```  
  
Existing Set_Expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="34019-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="34019-105">Arguments</span></span>  
 <span data-ttu-id="34019-106">*Set_Expression*</span><span class="sxs-lookup"><span data-stu-id="34019-106">*Set_Expression*</span></span>  
 <span data-ttu-id="34019-107">Espressione set MDX (Multidimensional Expression) valida.</span><span class="sxs-lookup"><span data-stu-id="34019-107">A valid Multidimensional Expressions (MDX) set expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34019-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="34019-108">Remarks</span></span>  
 <span data-ttu-id="34019-109">Per impostazione predefinita, i set vengono valutati all'interno del contesto del cubo che include i membri del set.</span><span class="sxs-lookup"><span data-stu-id="34019-109">By default, sets are evaluated within the context of the cube that contains the members of the set.</span></span> <span data-ttu-id="34019-110">È tuttavia possibile forzare la valutazione di un set specificato all'interno del contesto corrente utilizzando la parola chiave `Existing`.</span><span class="sxs-lookup"><span data-stu-id="34019-110">The `Existing` keyword forces a specified set to be evaluated within the current context instead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34019-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="34019-111">Example</span></span>  
 <span data-ttu-id="34019-112">Nell'esempio seguente viene restituito il numero dei rivenditori le cui vendite sono diminuite nel periodo di tempo precedente, in base ai valori del membro State-Province selezionati dall'utente valutati tramite la funzione `Aggregate`.</span><span class="sxs-lookup"><span data-stu-id="34019-112">The following example returns the count of the resellers whose sales have declined over the previous time period, based on user-selected State-Province member values evaluated using the `Aggregate` function.</span></span> <span data-ttu-id="34019-113">È tuttavia possibile forzare la valutazione di un set specificato all'interno del contesto corrente utilizzando la parola chiave [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) e [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) vengono usate per restituire i valori relativi alla diminuzione delle vendite per le categorie di prodotti nella dimensione Product.</span><span class="sxs-lookup"><span data-stu-id="34019-113">The [Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) and [DrilldownLevel (MDX)](/sql/mdx/drilldownlevel-mdx) functions are used to return values for declining sales for product categories in the Product dimension.</span></span> <span data-ttu-id="34019-114">La `Existing` parola chiave impone la valutazione del set nella `Filter` funzione nel contesto corrente, ovvero per i membri Washington e Oregon della gerarchia dell'attributo State-Province.</span><span class="sxs-lookup"><span data-stu-id="34019-114">The `Existing` keyword forces the set in the `Filter` function to be evaluated in the current context - that is, for the Washington and Oregon members of the State-Province attribute hierarchy.</span></span>  
  
```  
WITH MEMBER Measures.[Declining Reseller Sales] AS  
   Count  
      (Filter  
         (Existing  
            (Reseller.Reseller.Reseller)  
         , [Measures].[Reseller Sales Amount] <   
            ([Measures].[Reseller Sales Amount]  
               ,[Date].Calendar.PrevMember  
            )  
        )  
      )  
MEMBER [Geography].[State-Province].x AS   
   Aggregate   
      ( {[Geography].[State-Province].&[WA]&[US]  
         , [Geography].[State-Province].&[OR]&[US] }   
      )  
SELECT NON EMPTY HIERARCHIZE   
      (AddCalculatedMembers   
         (   
            {DrillDownLevel  
               ({[Product].[All Products]}  
               )  
            }   
         )   
      ) DIMENSION PROPERTIES PARENT_UNIQUE_NAME ON COLUMNS   
FROM [Adventure Works]  
WHERE   
      ( [Geography].[State-Province].x  
        , [Date].[Calendar].[Calendar Quarter].&[2003]&[4]  
        ,[Measures].[Declining Reseller Sales]  
      )  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="34019-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34019-115">See Also</span></span>  
 <span data-ttu-id="34019-116">[Conteggio &#40;set&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span><span class="sxs-lookup"><span data-stu-id="34019-116">[Count &#40;Set&#41; &#40;MDX&#41;](/sql/mdx/count-set-mdx) </span></span>  
 <span data-ttu-id="34019-117">[AddCalculatedMembers &#40;&#41;MDX](/sql/mdx/addcalculatedmembers-mdx) </span><span class="sxs-lookup"><span data-stu-id="34019-117">[AddCalculatedMembers &#40;MDX&#41;](/sql/mdx/addcalculatedmembers-mdx) </span></span>  
 <span data-ttu-id="34019-118">[Aggregazione MDX &#40;&#41;](/sql/mdx/aggregate-mdx) </span><span class="sxs-lookup"><span data-stu-id="34019-118">[Aggregate &#40;MDX&#41;](/sql/mdx/aggregate-mdx) </span></span>  
 <span data-ttu-id="34019-119">[Filtrare &#40;&#41;MDX](/sql/mdx/filter-mdx) </span><span class="sxs-lookup"><span data-stu-id="34019-119">[Filter &#40;MDX&#41;](/sql/mdx/filter-mdx) </span></span>  
 <span data-ttu-id="34019-120">[Proprietà &#40;&#41;MDX](/sql/mdx/properties-mdx) </span><span class="sxs-lookup"><span data-stu-id="34019-120">[Properties &#40;MDX&#41;](/sql/mdx/properties-mdx) </span></span>  
 <span data-ttu-id="34019-121">[DrilldownLevel &#40;&#41;MDX](/sql/mdx/drilldownlevel-mdx) </span><span class="sxs-lookup"><span data-stu-id="34019-121">[DrilldownLevel &#40;MDX&#41;](/sql/mdx/drilldownlevel-mdx) </span></span>  
 <span data-ttu-id="34019-122">[Hierarchize &#40;&#41;MDX](/sql/mdx/hierarchize-mdx) </span><span class="sxs-lookup"><span data-stu-id="34019-122">[Hierarchize &#40;MDX&#41;](/sql/mdx/hierarchize-mdx) </span></span>  
 [<span data-ttu-id="34019-123">Guida di riferimento alle funzioni MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="34019-123">MDX Function Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-function-reference-mdx)  
  
  
