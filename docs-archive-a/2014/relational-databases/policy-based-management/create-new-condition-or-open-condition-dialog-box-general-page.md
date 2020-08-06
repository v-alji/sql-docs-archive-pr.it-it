---
title: Finestra di dialogo Crea nuova condizione o Apri condizione, pagina Generale | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.condition.f1
ms.assetid: 106954bf-e4ba-412b-9c1a-907d06153dcd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 72e4a77df553ac8e97609e82bd51c8fd93b64b23
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637813"
---
# <a name="create-new-condition-or-open-condition-dialog-box-general-page"></a><span data-ttu-id="9d868-102">Finestra di dialogo Crea nuova condizione o Apri condizione, pagina Generale</span><span class="sxs-lookup"><span data-stu-id="9d868-102">Create New Condition or Open Condition Dialog Box, General Page</span></span>
  <span data-ttu-id="9d868-103">Utilizzare questa finestra di dialogo per creare o modificare una condizione della gestione basata su criteri.</span><span class="sxs-lookup"><span data-stu-id="9d868-103">Use this dialog box to create or change a Policy-Based Management condition.</span></span> <span data-ttu-id="9d868-104">Una condizione è un'espressione booleana che specifica un set di stati consentiti per una destinazione gestita della gestione basata su criteri in relazione ai facet.</span><span class="sxs-lookup"><span data-stu-id="9d868-104">A condition is a Boolean expression that specifies a set of allowed states of a Policy-Based Management managed target with regard to facets.</span></span> <span data-ttu-id="9d868-105">Le proprietà che è possibile selezionare nella casella **Espressione/Campo** variano a seconda del facet usato.</span><span class="sxs-lookup"><span data-stu-id="9d868-105">The properties that can be selected in the **Expression/Field** box depend upon the facet that is used.</span></span> <span data-ttu-id="9d868-106">Per altre informazioni sulla correlazione delle condizioni con facet e criteri, vedere [Amministrazione di server tramite la gestione basata su criteri](administer-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="9d868-106">For more information about how conditions relate to facets and policies, see [Administer Servers by Using Policy-Based Management](administer-servers-by-using-policy-based-management.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="9d868-107">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9d868-107">Options</span></span>  
 <span data-ttu-id="9d868-108">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9d868-108">**Name**</span></span>  
 <span data-ttu-id="9d868-109">Per una nuova condizione, digitare il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="9d868-109">For a new condition, type the new condition name.</span></span> <span data-ttu-id="9d868-110">Per una condizione esistente, il nome è già visualizzato.</span><span class="sxs-lookup"><span data-stu-id="9d868-110">For an existing condition, the name is displayed.</span></span>  
  
 <span data-ttu-id="9d868-111">**Facet**</span><span class="sxs-lookup"><span data-stu-id="9d868-111">**Facet**</span></span>  
 <span data-ttu-id="9d868-112">Facet utilizzato dalla condizione.</span><span class="sxs-lookup"><span data-stu-id="9d868-112">The facet used by this condition.</span></span>  
  
 <span data-ttu-id="9d868-113">**AndOr**</span><span class="sxs-lookup"><span data-stu-id="9d868-113">**AndOr**</span></span>  
 <span data-ttu-id="9d868-114">Quando si aggiungono più espressioni, indica se queste devono essere unite in join tramite **And** o **Or**.</span><span class="sxs-lookup"><span data-stu-id="9d868-114">When you add multiple expressions, indicates whether the expressions should be joined by using **And** or **Or**.</span></span> <span data-ttu-id="9d868-115">Se è disponibile un'unica espressione, il campo rimane vuoto.</span><span class="sxs-lookup"><span data-stu-id="9d868-115">Remains blank when there is only one expression.</span></span>  
  
 <span data-ttu-id="9d868-116">**Campo**</span><span class="sxs-lookup"><span data-stu-id="9d868-116">**Field**</span></span>  
 <span data-ttu-id="9d868-117">Ogni facet espone una o più proprietà che è possibile impostare.</span><span class="sxs-lookup"><span data-stu-id="9d868-117">Each facet exposes one or more properties that can be set.</span></span> <span data-ttu-id="9d868-118">Nella casella del campo, effettuare una selezione dall'elenco di proprietà disponibili per creare un'espressione per questa condizione.</span><span class="sxs-lookup"><span data-stu-id="9d868-118">In the field box, select a property from the list of available properties to create an expression for this condition.</span></span>  
  
 <span data-ttu-id="9d868-119">**Operatore**</span><span class="sxs-lookup"><span data-stu-id="9d868-119">**Operator**</span></span>  
 <span data-ttu-id="9d868-120">Selezionare un operatore di confronto per l'espressione.</span><span class="sxs-lookup"><span data-stu-id="9d868-120">Select a comparison operator for this expression.</span></span> <span data-ttu-id="9d868-121">Gli operatori sono i seguenti: =! = >, >= <, <=, [NOT]LIKE, [NOT]IN.</span><span class="sxs-lookup"><span data-stu-id="9d868-121">Operators are as follows: =, !=, >, >=, <, <=, [NOT]LIKE, [NOT]IN.</span></span> <span data-ttu-id="9d868-122">Per alcune proprietà non sono disponibili tutti gli operatori.</span><span class="sxs-lookup"><span data-stu-id="9d868-122">Not all operators are available for some properties.</span></span>  
  
 <span data-ttu-id="9d868-123">**Valore**</span><span class="sxs-lookup"><span data-stu-id="9d868-123">**Value**</span></span>  
 <span data-ttu-id="9d868-124">Impostazione del valore per l'espressione.</span><span class="sxs-lookup"><span data-stu-id="9d868-124">The value setting for this expression.</span></span> <span data-ttu-id="9d868-125">I valori consentiti dipendono dal facet.</span><span class="sxs-lookup"><span data-stu-id="9d868-125">The allowed values depend on the facet.</span></span> <span data-ttu-id="9d868-126">I valori possono essere TRUE/FALSE, di tipo stringa o numerico.</span><span class="sxs-lookup"><span data-stu-id="9d868-126">Values can be TRUE/FALSE, string, or numeric.</span></span> <span data-ttu-id="9d868-127">I valori stringa devono essere racchiusi tra virgolette singole, ad esempio: **'AdventureWorks'**.</span><span class="sxs-lookup"><span data-stu-id="9d868-127">String values must be enclosed in single quotation marks, for example: **'AdventureWorks'**.</span></span> <span data-ttu-id="9d868-128">Per alcune proprietà non sono disponibili tutti gli operatori.</span><span class="sxs-lookup"><span data-stu-id="9d868-128">Not all operators are available for some properties.</span></span>  
  
## <a name="group-clauses"></a><span data-ttu-id="9d868-129">Raggruppa clausole</span><span class="sxs-lookup"><span data-stu-id="9d868-129">Group Clauses</span></span>  
 <span data-ttu-id="9d868-130">Le clausole possono essere raggruppate in modo che funzionino come un'unità singola separata dal resto della query, in modo analogo all'utilizzo di parentesi per racchiudere un'espressione in un'equazione matematica o in un'istruzione logica.</span><span class="sxs-lookup"><span data-stu-id="9d868-130">Clauses can be grouped to operate as a single unit separate from the rest of the query, just like putting parentheses around an expression in a mathematical equation or logic statement.</span></span> <span data-ttu-id="9d868-131">Il raggruppamento delle clausole è utile quando si compilano query complesse.</span><span class="sxs-lookup"><span data-stu-id="9d868-131">Grouping clauses is useful when you are building complex queries.</span></span>  
  
 <span data-ttu-id="9d868-132">**Per raggruppare le clausole**</span><span class="sxs-lookup"><span data-stu-id="9d868-132">**To group clauses**</span></span>  
  
-   <span data-ttu-id="9d868-133">Premere MAIUSC o CTRL, quindi fare clic su due o più clausole per selezionare un intervallo.</span><span class="sxs-lookup"><span data-stu-id="9d868-133">Press the SHIFT or CTRL keys, and then click two or more clauses to select a range.</span></span> <span data-ttu-id="9d868-134">Fare clic con il pulsante destro del mouse sull'area selezionata, quindi scegliere **Raggruppa clausole**.</span><span class="sxs-lookup"><span data-stu-id="9d868-134">Right-click the selected area, and then click **Group Clauses**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d868-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d868-135">See Also</span></span>  
 [<span data-ttu-id="9d868-136">Amministrazione di server tramite la gestione basata su criteri</span><span class="sxs-lookup"><span data-stu-id="9d868-136">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
