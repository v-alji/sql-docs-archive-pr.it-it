---
title: Impostazione convenzioni di denominazione (generazione guidata schema) (Analysis Services-Dati multidimensionali) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.namingconventions.f1
ms.assetid: 02d830ea-5b1f-4485-9f94-d64b8bea592b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e9588b49331934041cad888142d29d189fc1a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635767"
---
# <a name="specify-naming-conventions-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="86586-102">Impostazione convenzioni di denominazione (Generazione guidata schema) (Analysis Services - Dati multidimensionali)</span><span class="sxs-lookup"><span data-stu-id="86586-102">Specify Naming Conventions (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="86586-103">Utilizzare la pagina **Impostazione convenzioni di denominazione** per definire le convenzioni di denominazione utilizzate in Generazione guidata schema per la creazione di oggetti dello schema.</span><span class="sxs-lookup"><span data-stu-id="86586-103">Use the **Specify Naming Conventions** page to define the naming conventions that the Schema Generation Wizard uses when creating schema objects.</span></span>  
  
## <a name="options"></a><span data-ttu-id="86586-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="86586-104">Options</span></span>  
 <span data-ttu-id="86586-105">**Opzione**</span><span class="sxs-lookup"><span data-stu-id="86586-105">**Option**</span></span>  
 <span data-ttu-id="86586-106">Consente di impostare le convenzioni di denominazione utilizzate nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="86586-106">Specify the naming conventions for the wizard to use.</span></span> <span data-ttu-id="86586-107">Nella tabella seguente vengono descritte le opzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="86586-107">The following table describes the options you can specify.</span></span>  
  
|<span data-ttu-id="86586-108">Opzione</span><span class="sxs-lookup"><span data-stu-id="86586-108">Option</span></span>|<span data-ttu-id="86586-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86586-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="86586-110">**Separatore**</span><span class="sxs-lookup"><span data-stu-id="86586-110">**Separator**</span></span>|<span data-ttu-id="86586-111">Consente di specificare il carattere che separa le parole in un nome di oggetto.</span><span class="sxs-lookup"><span data-stu-id="86586-111">Specifies the character that separates words in an object name.</span></span> <span data-ttu-id="86586-112">Nella colonna **Valore** selezionare **Carattere di sottolineatura**, **Spazio**o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="86586-112">In the **Value** column, select **Underscore**, **Space**, or **None**.</span></span> <span data-ttu-id="86586-113">Il valore predefinito è **Carattere di sottolineatura**.</span><span class="sxs-lookup"><span data-stu-id="86586-113">The default is **Underscore**.</span></span>|  
|<span data-ttu-id="86586-114">**Prefisso colonna chiave primaria**</span><span class="sxs-lookup"><span data-stu-id="86586-114">**Primary key column prefix**</span></span>|<span data-ttu-id="86586-115">Consente di specificare la stringa utilizzata come prefisso per il nome di ogni colonna chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="86586-115">Specifies the string to prefix the name of each primary key column.</span></span> <span data-ttu-id="86586-116">Il valore predefinito è **PK**.</span><span class="sxs-lookup"><span data-stu-id="86586-116">The default is **PK**.</span></span>|  
|<span data-ttu-id="86586-117">**Prefisso colonna chiave esterna**</span><span class="sxs-lookup"><span data-stu-id="86586-117">**Foreign key column prefix**</span></span>|<span data-ttu-id="86586-118">Consente di specificare la stringa utilizzata come prefisso per il nome di ogni colonna chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="86586-118">Specifies the string to prefix the name of each foreign key column.</span></span> <span data-ttu-id="86586-119">Il valore predefinito è **FK**.</span><span class="sxs-lookup"><span data-stu-id="86586-119">The default is **FK**.</span></span>|  
|<span data-ttu-id="86586-120">**Suffisso nome attributo**</span><span class="sxs-lookup"><span data-stu-id="86586-120">**Attribute name suffix**</span></span>|<span data-ttu-id="86586-121">Consente di specificare la stringa da aggiungere al nome di ogni colonna attributo.</span><span class="sxs-lookup"><span data-stu-id="86586-121">Specifies the string to be appended to the name of each attribute column.</span></span> <span data-ttu-id="86586-122">Il valore predefinito è **Nome**.</span><span class="sxs-lookup"><span data-stu-id="86586-122">The default is **Name**.</span></span>|  
|<span data-ttu-id="86586-123">**Suffisso rollup personalizzato**</span><span class="sxs-lookup"><span data-stu-id="86586-123">**Custom rollup suffix**</span></span>|<span data-ttu-id="86586-124">Consente di specificare la stringa da aggiungere al nome di ogni colonna rollup.</span><span class="sxs-lookup"><span data-stu-id="86586-124">Specifies the string to be appended to the name of each rollup column.</span></span> <span data-ttu-id="86586-125">Il valore predefinito è **CustomRollup**.</span><span class="sxs-lookup"><span data-stu-id="86586-125">The default is **CustomRollup**.</span></span>|  
|<span data-ttu-id="86586-126">**Suffisso proprietà rollup personalizzato**</span><span class="sxs-lookup"><span data-stu-id="86586-126">**Custom rollup Properties suffix**</span></span>|<span data-ttu-id="86586-127">Consente di specificare la stringa da aggiungere al nome di ogni colonna di proprietà rollup.</span><span class="sxs-lookup"><span data-stu-id="86586-127">Specifies the string to be appended to the name of each rollup property column.</span></span> <span data-ttu-id="86586-128">Il valore predefinito è **CustomRollupProperties**.</span><span class="sxs-lookup"><span data-stu-id="86586-128">The default is **CustomRollupProperties**.</span></span>|  
|<span data-ttu-id="86586-129">**Suffisso operatore unario**</span><span class="sxs-lookup"><span data-stu-id="86586-129">**Unary operator suffix**</span></span>|<span data-ttu-id="86586-130">Consente di specificare la stringa da aggiungere al nome di ogni colonna di operatore unario.</span><span class="sxs-lookup"><span data-stu-id="86586-130">Specifies the string to be appended to the name of each unary operator column.</span></span> <span data-ttu-id="86586-131">Il valore predefinito è **UnaryOperator**.</span><span class="sxs-lookup"><span data-stu-id="86586-131">The default is **UnaryOperator**.</span></span>|  
  
 <span data-ttu-id="86586-132">**Valore**</span><span class="sxs-lookup"><span data-stu-id="86586-132">**Value**</span></span>  
 <span data-ttu-id="86586-133">Consente di indicare un valore per l'opzione specificata in **Opzione** da usare per la generazione dello schema.</span><span class="sxs-lookup"><span data-stu-id="86586-133">Specify a value for the option specified in **Option** that you want to use when the schema is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86586-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86586-134">See Also</span></span>  
 <span data-ttu-id="86586-135">[Guida sensibile al contesto della generazione guidata schema &#40;Analysis Services-Dati multidimensionali&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="86586-135">[Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="86586-136">Procedure guidate di Analysis Services &#40;dati multidimensionali&#41;</span><span class="sxs-lookup"><span data-stu-id="86586-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
