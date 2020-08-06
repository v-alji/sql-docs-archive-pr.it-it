---
title: Creare una gerarchia derivata (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, creating
- creating derived hierarchies [Master Data Services]
ms.assetid: fec653c4-11cc-46a2-8dd8-b605341ebb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 20469ad30222e43a3104503cc32187c2e6512743
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716392"
---
# <a name="create-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="5a500-102">Creare una gerarchia derivata (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5a500-102">Create a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="5a500-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]creare una gerarchia derivata quando si desidera una gerarchia basata su livelli tramite cui viene assicurato il posizionamento dei membri al corretto livello.</span><span class="sxs-lookup"><span data-stu-id="5a500-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a derived hierarchy when you want a level-based hierarchy that ensures that members exist at the correct level.</span></span> <span data-ttu-id="5a500-104">Le gerarchie derivate sono basate sulle relazioni tra attributi basati su dominio che esistono in un modello.</span><span class="sxs-lookup"><span data-stu-id="5a500-104">Derived hierarchies are based on the domain-based attribute relationships that exist in a model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a500-105">Se non esiste un valore di attributo basato su dominio per un determinato membro, tale membro non verrà incluso nella gerarchia derivata.</span><span class="sxs-lookup"><span data-stu-id="5a500-105">If a domain-based attribute value doesn't exist for a member, the member is not included in the derived hierarchy.</span></span> <span data-ttu-id="5a500-106">Vedere [Richiedere valori di attributo &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) per richiedere un valore di attributo basato su dominio per tutti i membri.</span><span class="sxs-lookup"><span data-stu-id="5a500-106">See [Require Attribute Values &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) to require a domain-based attribute value for all members.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a500-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5a500-107">Prerequisites</span></span>  
 <span data-ttu-id="5a500-108">Per eseguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="5a500-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5a500-109">È necessario disporre di autorizzazione per accedere all'area funzionale **Amministrazione sistema** .</span><span class="sxs-lookup"><span data-stu-id="5a500-109">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="5a500-110">È necessario essere un amministratore del modello.</span><span class="sxs-lookup"><span data-stu-id="5a500-110">You must be a model administrator.</span></span> <span data-ttu-id="5a500-111">Per ulteriori informazioni, vedere [amministratori &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5a500-111">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-derived-hierarchy"></a><span data-ttu-id="5a500-112">Per creare una gerarchia derivata</span><span class="sxs-lookup"><span data-stu-id="5a500-112">To create a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="5a500-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], fare clic su **Amministrazione sistema**.</span><span class="sxs-lookup"><span data-stu-id="5a500-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="5a500-114">Nella pagina **vista modelli** scegliere **Gestisci** dalla barra dei menu, quindi fare clic su **gerarchie derivate**.</span><span class="sxs-lookup"><span data-stu-id="5a500-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="5a500-115">Nella pagina **Gestione gerarchia derivata** selezionare un modello dall'elenco **Modello** .</span><span class="sxs-lookup"><span data-stu-id="5a500-115">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="5a500-116">Fare clic su **Aggiungi gerarchia derivata**.</span><span class="sxs-lookup"><span data-stu-id="5a500-116">Click **Add derived hierarchy**.</span></span>  
  
5.  <span data-ttu-id="5a500-117">Nella pagina **Aggiungi gerarchia derivata** digitare un nome per la gerarchia nella casella **Nome gerarchia derivata** .</span><span class="sxs-lookup"><span data-stu-id="5a500-117">On the **Add Derived Hierarchy** page, in the **Derived hierarchy name** box, type a name for the hierarchy.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="5a500-118">Usare un nome che descriva i livelli della gerarchia, ad esempio **Prodotto-Subcategoria-Categoria**.</span><span class="sxs-lookup"><span data-stu-id="5a500-118">Use a name that describes the levels in the hierarchy, for example **Product to Subcategory to Category**.</span></span>  
  
6.  <span data-ttu-id="5a500-119">Fare clic su **Salva gerarchia derivata**.</span><span class="sxs-lookup"><span data-stu-id="5a500-119">Click **Save derived hierarchy**.</span></span>  
  
7.  <span data-ttu-id="5a500-120">Nel riquadro **entità e gerarchie disponibili** della pagina **Modifica gerarchia derivata** fare clic su un'entità o una gerarchia e trascinarla nel riquadro **livelli correnti** .</span><span class="sxs-lookup"><span data-stu-id="5a500-120">On the **Edit Derived Hierarchy** page, in the **Available Entities and Hierarchies** pane, click an entity or hierarchy and drag it to the **Current Levels** pane.</span></span>  
  
8.  <span data-ttu-id="5a500-121">Continuare a trascinare entità o gerarchie fino a che la gerarchia non è completa.</span><span class="sxs-lookup"><span data-stu-id="5a500-121">Continue dragging entities or hierarchies until your hierarchy is complete.</span></span>  
  
9. <span data-ttu-id="5a500-122">Fare clic su **Indietro**.</span><span class="sxs-lookup"><span data-stu-id="5a500-122">Click **Back**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a500-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a500-123">See Also</span></span>  
 <span data-ttu-id="5a500-124">[Gerarchie derivate &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5a500-124">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="5a500-125">[Gerarchie derivate con estremità esplicite &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5a500-125">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="5a500-126">Attributi basati su dominio &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5a500-126">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)  
  
  
