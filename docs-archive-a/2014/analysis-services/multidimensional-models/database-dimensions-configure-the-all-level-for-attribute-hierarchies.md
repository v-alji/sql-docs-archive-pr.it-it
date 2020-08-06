---
title: Configurare il livello (totale) per le gerarchie di attributi | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- All members
- IsAggregatable property
- topmost levels [Analysis Services]
- (All) levels
- AttributeAllMemberName property
- levels [Analysis Services]
- members [Analysis Services], All
- AllMemberName property
ms.assetid: 0cb35e6f-b10f-483d-b893-78f6ca3979fd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9874a8c8a6861bc7d9e44271b089e8af3a4c0ae2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714684"
---
# <a name="configure-the-all-level-for-attribute-hierarchies"></a><span data-ttu-id="15c4e-102">Configurare il livello (Totale) per le gerarchie di attributi</span><span class="sxs-lookup"><span data-stu-id="15c4e-102">Configure the (All) Level for Attribute Hierarchies</span></span>
  <span data-ttu-id="15c4e-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] il livello (totale) è un livello facoltativo generato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="15c4e-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], the (All) level is an optional, system-generated level.</span></span> <span data-ttu-id="15c4e-104">Contiene un solo membro il cui valore è determinato dall'aggregazione dei valori di tutti i membri nel livello immediatamente subordinato.</span><span class="sxs-lookup"><span data-stu-id="15c4e-104">It contains only one member whose value is the aggregation of the values of all members in the immediately subordinate level.</span></span> <span data-ttu-id="15c4e-105">Questo membro è denominato membro Totale.</span><span class="sxs-lookup"><span data-stu-id="15c4e-105">This member is called the All member.</span></span> <span data-ttu-id="15c4e-106">Si tratta di un membro generato dal sistema non contenuto nella tabella della dimensione.</span><span class="sxs-lookup"><span data-stu-id="15c4e-106">It is a system-generated member that is not contained in the dimension table.</span></span> <span data-ttu-id="15c4e-107">Poiché il membro nel livello (Totale) si trova al primo livello della gerarchia, il relativo valore è determinato dall'aggregazione consolidata dei valori di tutti i membri della gerarchia.</span><span class="sxs-lookup"><span data-stu-id="15c4e-107">Because the member in the (All) level is at the top of the hierarchy, the member's value is the consolidated aggregation of the values of all members in the hierarchy.</span></span> <span data-ttu-id="15c4e-108">Il membro Totale spesso funge da membro predefinito di una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="15c4e-108">The All member often serves as the default member of a hierarchy.</span></span>  
  
 <span data-ttu-id="15c4e-109">La presenza di un livello (Totale) nella gerarchia di un attributo dipende dall'impostazione della proprietà `IsAggregatable` dell'attributo, mentre la presenza di un livello (Totale) in una gerarchia definita dall'utente dipende dall'impostazione della proprietà `IsAggregatable` dell'attributo nel livello superiore della gerarchia definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="15c4e-109">The presence of an (All) level in an attribute hierarchy depends on the `IsAggregatable` property setting for the attribute and the presence of an (All) level in a user-defined hierarchy depends on the `IsAggregatable` property of the attribute at the top-most level of user-defined hierarchy.</span></span> <span data-ttu-id="15c4e-110">Se la proprietà `IsAggregatable` è impostata su `True`, esisterà un livello (Totale).</span><span class="sxs-lookup"><span data-stu-id="15c4e-110">If the `IsAggregatable` property is set to `True`, an (All) level will exist.</span></span> <span data-ttu-id="15c4e-111">Se la proprietà `IsAggregatable` è impostata su `False`, il livello (Totale) non sarà presente.</span><span class="sxs-lookup"><span data-stu-id="15c4e-111">A hierarchy has no (All) level if the `IsAggregatable` property is set to `False`.</span></span>  
  
## <a name="establishing-the-topmost-level"></a><span data-ttu-id="15c4e-112">Determinazione del livello superiore</span><span class="sxs-lookup"><span data-stu-id="15c4e-112">Establishing the Topmost Level</span></span>  
 <span data-ttu-id="15c4e-113">Se la proprietà `IsAggregatable` è impostata su `False` nell'attributo di origine di un livello di una gerarchia, la gerarchia non potrà contenere un livello aggregabile al di sopra di tale livello.</span><span class="sxs-lookup"><span data-stu-id="15c4e-113">If the `IsAggregatable` property is set to `False` on the source attribute of a level in a hierarchy, then no aggregatable level can appear in the hierarchy above that level.</span></span> <span data-ttu-id="15c4e-114">È necessario che il livello non aggregabile sia il livello superiore di qualsiasi gerarchia oppure che la proprietà `IsAggregatable` degli attributi di origine in qualsiasi livello al di sopra di quello non aggregabile sia anch'essa impostata su `False`.</span><span class="sxs-lookup"><span data-stu-id="15c4e-114">A non-aggregatable level must be the topmost level of any hierarchy or the `IsAggregatable` property of the source attributes for any levels above it must also be set to `False`.</span></span>  
  
## <a name="all-member-and-all-level"></a><span data-ttu-id="15c4e-115">Membro Totale e livello (Totale)</span><span class="sxs-lookup"><span data-stu-id="15c4e-115">All Member and (All) Level</span></span>  
 <span data-ttu-id="15c4e-116">Il singolo membro del livello (Totale) è denominato membro Totale.</span><span class="sxs-lookup"><span data-stu-id="15c4e-116">The single member of the (All) level is called the All member.</span></span> <span data-ttu-id="15c4e-117">La `AttributeAllMemberName` proprietà di una dimensione specifica il nome del membro totale per gli attributi in una dimensione.</span><span class="sxs-lookup"><span data-stu-id="15c4e-117">The `AttributeAllMemberName`property on a dimension specifies the name of the All member for attributes in a dimension.</span></span> <span data-ttu-id="15c4e-118">La proprietà `AllMemberName` di una gerarchia specifica il nome del membro Totale per la gerarchia.</span><span class="sxs-lookup"><span data-stu-id="15c4e-118">The `AllMemberName` property on a hierarchy specifies the name of the All member for the hierarchy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c4e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15c4e-119">See Also</span></span>  
 [<span data-ttu-id="15c4e-120">Definire un membro predefinito</span><span class="sxs-lookup"><span data-stu-id="15c4e-120">Define a Default Member</span></span>](attribute-properties-define-a-default-member.md)  
  
  
