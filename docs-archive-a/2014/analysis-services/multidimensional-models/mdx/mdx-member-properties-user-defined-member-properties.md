---
title: Proprietà membro definite dall'utente (MDX) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- custom member properties [MDX]
ms.assetid: b64cc581-e784-42c4-bec8-932abd687423
author: minewiskan
ms.author: owend
ms.openlocfilehash: 75e5df5a0677ee205b5517f4c7ca89a390426971
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714636"
---
# <a name="user-defined-member-properties-mdx"></a><span data-ttu-id="7c76a-102">Proprietà dei membri definite dall'utente (MDX)</span><span class="sxs-lookup"><span data-stu-id="7c76a-102">User-Defined Member Properties (MDX)</span></span>
  <span data-ttu-id="7c76a-103">Le proprietà dei membri definite dall'utente possono essere aggiunte a uno specifico livello denominato di una dimensione come relazioni tra attributi.</span><span class="sxs-lookup"><span data-stu-id="7c76a-103">User-defined member properties can be added to a specific named level in a dimension as attribute relationships.</span></span> <span data-ttu-id="7c76a-104">Le proprietà dei membri definite dall'utente non possono essere aggiunte al livello `(All)` di una gerarchia né alla gerarchia stessa.</span><span class="sxs-lookup"><span data-stu-id="7c76a-104">User-defined member properties cannot be added to the `(All)` level of a hierarchy, or to the hierarchy itself.</span></span>  
  
## <a name="creating-user-defined-member-properties"></a><span data-ttu-id="7c76a-105">Creazione delle proprietà dei membri definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="7c76a-105">Creating User-Defined Member Properties</span></span>  
 <span data-ttu-id="7c76a-106">Le proprietà dei membri definite dall'utente possono essere aggiunte a dimensioni o cubi basati su server tramite l'interfaccia utente o a livello di programmazione:</span><span class="sxs-lookup"><span data-stu-id="7c76a-106">User-defined member properties can be added to server-based dimensions or cubes either through the user interface or programmatically:</span></span>  
  
-   <span data-ttu-id="7c76a-107">Per aggiungere proprietà dei membri definite dall'utente tramite l'interfaccia utente, usare Progettazione dimensioni in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7c76a-107">To add user-defined member properties through the user interface, you use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="7c76a-108">Per altre informazioni, vedere [Definire relazioni tra attributi](../attribute-relationships-define.md).</span><span class="sxs-lookup"><span data-stu-id="7c76a-108">For more information, see [Define Attribute Relationships](../attribute-relationships-define.md).</span></span>  
  
-   <span data-ttu-id="7c76a-109">Per aggiungere proprietà dei membri definite dall'utente a livello di programmazione, è possibile utilizzare AMO (Analysis Manager Objects) o una combinazione di XMLA (XML for Analysis) e ASSL (Analysis Services Scripting Language).</span><span class="sxs-lookup"><span data-stu-id="7c76a-109">To add user-defined member properties programmatically, your application can use either Analysis Manager Objects (AMO) or a combination of XML for Analysis (XMLA) and Analysis Services Scripting Language (ASSL).</span></span> <span data-ttu-id="7c76a-110">Per altre informazioni, vedere [Relazioni tra attributi](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="7c76a-110">For more information, see [Attribute Relationships](../../multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).</span></span>  
  
## <a name="retrieving-user-defined-member-properties"></a><span data-ttu-id="7c76a-111">Recupero delle proprietà dei membri definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="7c76a-111">Retrieving User-Defined Member Properties</span></span>  
 <span data-ttu-id="7c76a-112">È possibile recuperare le proprietà dei membri definite dall'utente usando la `PROPERTIES` parola chiave o la funzione [Properties](/sql/mdx/properties-mdx) .</span><span class="sxs-lookup"><span data-stu-id="7c76a-112">You can retrieve user-defined member properties using either the `PROPERTIES` keyword or the [Properties](/sql/mdx/properties-mdx) function.</span></span>  
  
### <a name="using-the-properties-keyword-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="7c76a-113">Utilizzo della parola chiave PROPERTIES per il recupero delle proprietà dei membri definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="7c76a-113">Using the PROPERTIES Keyword to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="7c76a-114">La sintassi da utilizzare per il recupero delle proprietà dei membri definite dall'utente è simile a quella utilizzata per il recupero delle proprietà intrinseche dei membri dei livelli, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7c76a-114">The syntax that retrieves user-defined member properties is similar to that used to retrieve intrinsic level member properties, as shown in the following syntax:</span></span>  
  
 `DIMENSION PROPERTIES [Dimension.]Level.<Custom_Member_Property>`  
  
 <span data-ttu-id="7c76a-115">La parola chiave `PROPERTIES` compare dopo l'espressione set che specifica l'asse.</span><span class="sxs-lookup"><span data-stu-id="7c76a-115">The `PROPERTIES` keyword appears after the set expression of the axis specification.</span></span> <span data-ttu-id="7c76a-116">Nella query MDX seguente, ad esempio, la parola chiave `PROPERTIES` recupera le proprietà membro definite dall'utente `List Price` e `Dealer Price` e viene visualizzata dopo l'espressione set che identifica i prodotti venduti a gennaio:</span><span class="sxs-lookup"><span data-stu-id="7c76a-116">For example, the following MDX query the `PROPERTIES` keyword retrieves the `List Price` and `Dealer Price` user-defined member properties and appears after the set expression that identifies the products sold in January:</span></span>  
  
```  
SELECT   
   CROSSJOIN([Ship Date].[Calendar].[Calendar Year].Members,   
             [Measures].[Sales Amount]) ON COLUMNS,  
   NON EMPTY Product.Product.MEMBERS  
   DIMENSION PROPERTIES   
              Product.Product.[List Price],  
              Product.Product.[Dealer Price]  ON ROWS  
FROM [Adventure Works]  
WHERE ([Date].[Month of Year].[January])   
```  
  
### <a name="using-the-properties-function-to-retrieve-user-defined-member-properties"></a><span data-ttu-id="7c76a-117">Utilizzo della funzione Properties per il recupero delle proprietà dei membri definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="7c76a-117">Using the Properties Function to Retrieve User-Defined Member Properties</span></span>  
 <span data-ttu-id="7c76a-118">In alternativa, per accedere alle proprietà personalizzate dei membri è possibile utilizzare la funzione `Properties`.</span><span class="sxs-lookup"><span data-stu-id="7c76a-118">Alternatively, you can access custom member properties with the `Properties` function.</span></span> <span data-ttu-id="7c76a-119">Nella query MDX seguente viene ad esempio utilizzata la parola chiave `WITH` per creare un membro calcolato costituito dalla proprietà `List Price` di un membro:</span><span class="sxs-lookup"><span data-stu-id="7c76a-119">For example, the following MDX query uses the `WITH` keyword to create a calculated member consisting of the `List Price` member property:</span></span>  
  
```  
WITH   
   MEMBER [Measures].[Product List Price] AS  
   [Product].[Product].CurrentMember.Properties("List Price")  
SELECT   
   [Measures].[Product List Price] on COLUMNS,  
   [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
```  
  
 <span data-ttu-id="7c76a-120">Per altre informazioni sulla compilazione di membri calcolati, vedere [Compilazione di membri calcolati in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span><span class="sxs-lookup"><span data-stu-id="7c76a-120">For more information about building calculated members, see [Building Calculated Members in MDX &#40;MDX&#41;](mdx-calculated-members-building-calculated-members.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c76a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c76a-121">See Also</span></span>  
 <span data-ttu-id="7c76a-122">[Utilizzo delle proprietà del membro &#40;&#41;MDX](mdx-member-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7c76a-122">[Using Member Properties &#40;MDX&#41;](mdx-member-properties.md) </span></span>  
 [<span data-ttu-id="7c76a-123">Properties &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="7c76a-123">Properties &#40;MDX&#41;</span></span>](/sql/mdx/properties-mdx)  
  
  
