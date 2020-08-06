---
title: Creare una dimensione di tipo valuta | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], currency
- currency [Analysis Services]
- converting currency
- currency dimensions [Analysis Services]
ms.assetid: b1f037d1-ce47-4e47-a1c2-5ec9e781cff6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 91123fb5fda898e90056057114295335fbd1d32c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714676"
---
# <a name="create-a-currency-type-dimension"></a><span data-ttu-id="36fba-102">Creare una dimensione di tipo Valuta</span><span class="sxs-lookup"><span data-stu-id="36fba-102">Create a Currency type Dimension</span></span>
  <span data-ttu-id="36fba-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] una dimensione di tipo valuta è una dimensione i cui attributi rappresentano un elenco di valute per la creazione di report finanziari.</span><span class="sxs-lookup"><span data-stu-id="36fba-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], a currency type dimension is a dimension whose attributes represent a list of currencies for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="36fba-104">Una dimensione di tipo Valuta consente di aggiungere funzionalità di conversione di valuta a un cubo in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36fba-104">A currency dimension lets you add currency conversion capabilities to a cube in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="36fba-105">Per aggiungere funzionalità di conversione di valuta a un cubo, è possibile utilizzare la Configurazione guidata funzionalità di Business Intelligence per definire un comando script MDX (Multidimensional Expressions) che consenta di convertire le misure di valuta in valori appropriati per le impostazioni locali dell'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="36fba-105">To add currency conversion to a cube, you use the Business Intelligence Wizard define a Multidimensional Expressions (MDX) script command that converts currency measures to values that are appropriate for the locale of the client application.</span></span> <span data-ttu-id="36fba-106">Per creare tale script MDX, nella Configurazione guidata funzionalità di Business Intelligence sono necessarie le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="36fba-106">To create this MDX script, the Business Intelligence Wizard needs the following information:</span></span>  
  
-   <span data-ttu-id="36fba-107">Una dimensione di tipo Valuta che rappresenta le valute di origine,</span><span class="sxs-lookup"><span data-stu-id="36fba-107">A currency dimension that represents source currencies.</span></span> <span data-ttu-id="36fba-108">ovvero la dimensione di tipo Valuta di origine.</span><span class="sxs-lookup"><span data-stu-id="36fba-108">(This dimension is the source currency dimension.)</span></span>  
  
-   <span data-ttu-id="36fba-109">Un gruppo di misure che rappresenta i tassi di cambio utilizzati.</span><span class="sxs-lookup"><span data-stu-id="36fba-109">A measure group that represents the exchange rates that will be used.</span></span>  
  
 <span data-ttu-id="36fba-110">In base a tali informazioni, tramite la Configurazione guidata funzionalità di Business Intelligence verrà automaticamente progettato un processo di conversione di valuta che identifica la dimensione di tipo Valuta di destinazione appropriata, ovvero la dimensione di tipo Valuta che rappresenta le valute di destinazione.</span><span class="sxs-lookup"><span data-stu-id="36fba-110">From this information, the Business Intelligence Wizard will design a currency conversion process that identifies the appropriate destination currency dimension (the currency dimension that represents destination currencies).</span></span> <span data-ttu-id="36fba-111">In base al numero di conversioni di valuta necessarie alla soluzione di Business Intelligence, tramite la Configurazione guidata funzionalità di Business Intelligence è possibile definire più dimensioni di tipo Valuta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="36fba-111">Depending on the number of currency conversions that your business intelligence solution requires, the Business Intelligence Wizard can define multiple destination currency dimensions.</span></span> <span data-ttu-id="36fba-112">Per altre informazioni sulla definizione di conversioni di valuta, vedere [Conversioni di valuta &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="36fba-112">For more information about defining currency conversions, see [Currency Conversions &#40;Analysis Services&#41;](../currency-conversions-analysis-services.md).</span></span>  
  
 <span data-ttu-id="36fba-113">Per identificare una dimensione come dimensione di tipo Valuta, impostare la proprietà `Type` della dimensione su `Currency`.</span><span class="sxs-lookup"><span data-stu-id="36fba-113">To identify a dimension as a currency dimension, set the `Type` property of the dimension to `Currency`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="36fba-114">Struttura dimensione</span><span class="sxs-lookup"><span data-stu-id="36fba-114">Dimension Structure</span></span>  
 <span data-ttu-id="36fba-115">Una dimensione di tipo Valuta contiene almeno un attributo chiave che identifica singole valute nella tabella della dimensione per la dimensione di tipo Valuta.</span><span class="sxs-lookup"><span data-stu-id="36fba-115">A currency dimension contains, at least, a key attribute identifying individual currencies in the dimension table for the currency dimension.</span></span> <span data-ttu-id="36fba-116">Il valore dell'attributo chiave è diverso nelle dimensioni di tipo Valuta di origine e di destinazione:</span><span class="sxs-lookup"><span data-stu-id="36fba-116">The value of the key attribute is different in both source and destination currency dimensions:</span></span>  
  
-   <span data-ttu-id="36fba-117">Per identificare un attributo come attributo chiave di una dimensione di tipo Valuta di origine, impostare la proprietà `Type` dell'attributo su `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="36fba-117">To identify an attribute as the key attribute of a source currency dimension, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="36fba-118">Per identificare un attributo come dimensione di tipo Valuta di destinazione, impostare la proprietà `Type` dell'attributo su `CurrencyDestination`.</span><span class="sxs-lookup"><span data-stu-id="36fba-118">To identify an attribute as the destination currency dimension, set the `Type` property of the attribute to `CurrencyDestination`.</span></span>  
  
 <span data-ttu-id="36fba-119">Ai fini della generazione di report, sia la dimensione di tipo Valuta di origine che quella di destinazione possono facoltativamente includere gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="36fba-119">For reporting purposes, both source and destination currency dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="36fba-120">Un attributo Nome valuta.</span><span class="sxs-lookup"><span data-stu-id="36fba-120">A currency name attribute.</span></span>  
  
     <span data-ttu-id="36fba-121">Per identificare un attributo come attributo Nome valuta, impostare la proprietà `Type` dell'attributo su `CurrencyName`.</span><span class="sxs-lookup"><span data-stu-id="36fba-121">To identify an attribute as a currency name attribute, set the `Type` property of the attribute to `CurrencyName`.</span></span>  
  
-   <span data-ttu-id="36fba-122">Un attributo Origine valuta.</span><span class="sxs-lookup"><span data-stu-id="36fba-122">A currency source attribute.</span></span>  
  
     <span data-ttu-id="36fba-123">Per identificare un attributo come attributo Origine valuta, impostare la proprietà `Type` dell'attributo su `CurrencySource`.</span><span class="sxs-lookup"><span data-stu-id="36fba-123">To identify an attribute as a currency source attribute, set the `Type` property of the attribute to `CurrencySource`.</span></span>  
  
-   <span data-ttu-id="36fba-124">Un codice ISO (International Standards Organization) valuta.</span><span class="sxs-lookup"><span data-stu-id="36fba-124">A currency International Standards Organization (ISO) code.</span></span>  
  
     <span data-ttu-id="36fba-125">Per identificare un attributo come attributo Codice ISO valuta, impostare la proprietà `Type` dell'attributo su `CurrencyIsoCode`.</span><span class="sxs-lookup"><span data-stu-id="36fba-125">To identify an attribute as a currency ISO code attribute, set the `Type` property of the attribute to `CurrencyIsoCode`.</span></span>  
  
 <span data-ttu-id="36fba-126">Per altre informazioni sui tipi di attributi, vedere [Configurare tipi di attributi](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="36fba-126">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="defining-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="36fba-127">Definizione di funzionalità di Business Intelligence per la contabilità tramite la Configurazione guidata funzionalità di Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="36fba-127">Defining Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="36fba-128">Dopo avere definito una dimensione di tipo Conti e avere aggiunto tale dimensione a un cubo, è possibile utilizzare la Configurazione guidata funzionalità di Business Intelligence per aggiungere funzionalità di Business Intelligence per la contabilità, ad esempio funzionalità di identificazione e mapping dei tipi di conto, alla dimensione.</span><span class="sxs-lookup"><span data-stu-id="36fba-128">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to add account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="36fba-129">Per altre informazioni, vedere [Aggiungere funzionalità di Business Intelligence per la contabilità a una dimensione](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="36fba-129">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36fba-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36fba-130">See Also</span></span>  
 <span data-ttu-id="36fba-131">[Attributi e gerarchie di attributi](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="36fba-131">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="36fba-132">[Guida sensibile al contesto della configurazione guidata funzionalità di Business Intelligence](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="36fba-132">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="36fba-133">Tipi di dimensioni</span><span class="sxs-lookup"><span data-stu-id="36fba-133">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
