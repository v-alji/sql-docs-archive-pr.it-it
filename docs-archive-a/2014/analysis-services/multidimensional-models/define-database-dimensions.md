---
title: Definire le dimensioni del database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], defining
ms.assetid: fe84588b-66a3-4100-a1cf-59b21b7adf01
author: minewiskan
ms.author: owend
ms.openlocfilehash: ad5334e71b0f133f80933a7d1702d8ada7565501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712567"
---
# <a name="define-database-dimensions"></a><span data-ttu-id="da107-102">Definire le dimensioni del database</span><span class="sxs-lookup"><span data-stu-id="da107-102">Define Database Dimensions</span></span>
  <span data-ttu-id="da107-103">Utilizzare Progettazione dimensioni in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] per configurare una dimensione di database esistente in un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] progetto o un database di.</span><span class="sxs-lookup"><span data-stu-id="da107-103">Use Dimension Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to configure an existing database dimension in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project or database.</span></span> <span data-ttu-id="da107-104">Progettazione dimensioni consente di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="da107-104">You can use Dimension Designer to do the following:</span></span>  
  
-   <span data-ttu-id="da107-105">Configurare le proprietà a livello di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="da107-105">Configure the dimension-level properties.</span></span>  
  
-   <span data-ttu-id="da107-106">Aggiungere e configurare gli attributi delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="da107-106">Add and configure dimension attributes.</span></span>  
  
-   <span data-ttu-id="da107-107">Definire e configurare le gerarchie definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="da107-107">Define and configure user-defined hierarchies.</span></span>  
  
-   <span data-ttu-id="da107-108">Definire e configurare le relazioni tra gli attributi.</span><span class="sxs-lookup"><span data-stu-id="da107-108">Define and configure relationships between attributes.</span></span>  
  
-   <span data-ttu-id="da107-109">Definire le traduzioni delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="da107-109">Define dimension translations.</span></span>  
  
-   <span data-ttu-id="da107-110">nonché esplorare la struttura e visualizzare i dati delle dimensioni elaborate.</span><span class="sxs-lookup"><span data-stu-id="da107-110">For processed dimensions, you can browse the dimension structure and view data.</span></span>  
  
 <span data-ttu-id="da107-111">Dopo aver modificato una dimensione, un attributo o una gerarchia, è necessario elaborare tale dimensione per visualizzare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="da107-111">After you modify a dimension, attribute, or hierarchy, you must process that dimension to view the changes.</span></span> <span data-ttu-id="da107-112">In modalità progetto, le modifiche vengono distribuite all'istanza di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] prima dell'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="da107-112">When working in project mode, you deploy the changes to the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance before processing.</span></span>  
  
 <span data-ttu-id="da107-113">Per altre informazioni su come aprire una dimensione in Progettazione dimensioni, vedere [Modificare o eliminare una dimensione di database in Esplora soluzioni](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="da107-113">For more information about how to open a dimension in Dimension Designer, see [Modify or Delete a Database Dimension in Solution Explorer](database-dimensions-modify-or-delete-a-database-dimension-in-solution-explorer.md).</span></span>  
  
 <span data-ttu-id="da107-114">In Progettazione dimensioni sono disponibili tre diverse schede, descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="da107-114">Dimension Designer has three different tabs, which are described in the following table.</span></span>  
  
|<span data-ttu-id="da107-115">Scheda</span><span class="sxs-lookup"><span data-stu-id="da107-115">Tab</span></span>|<span data-ttu-id="da107-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="da107-116">Description</span></span>|  
|---------|-----------------|  
|<span data-ttu-id="da107-117">**Struttura dimensione**</span><span class="sxs-lookup"><span data-stu-id="da107-117">**Dimension Structure**</span></span>|<span data-ttu-id="da107-118">Utilizzare questa scheda per utilizzare la struttura di una dimensione: per esaminare o creare lo schema della vista origine dati per una dimensione, per utilizzare gli attributi e per organizzare gli attributi in gerarchie definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="da107-118">Use this tab to work with the structure of a dimension-to examine or create the data source view schema for a dimension, to work with attributes, and to organize attributes in user-defined hierarchies.</span></span>|  
|<span data-ttu-id="da107-119">**Relazioni tra attributi**</span><span class="sxs-lookup"><span data-stu-id="da107-119">**Attribute Relationships**</span></span>|<span data-ttu-id="da107-120">Utilizzare questa scheda per creare, modificare o eliminare le relazioni tra attributi di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="da107-120">Use this tab to create, modify, or delete the attribute relationships of a dimension.</span></span>|  
|<span data-ttu-id="da107-121">**Traduzioni**</span><span class="sxs-lookup"><span data-stu-id="da107-121">**Translations**</span></span>|<span data-ttu-id="da107-122">Utilizzare questa scheda per aggiungere e modificare traduzioni di metadati delle dimensioni in diverse lingue.</span><span class="sxs-lookup"><span data-stu-id="da107-122">Use this tab to add and edit translations of dimension metadata in different languages.</span></span>|  
|<span data-ttu-id="da107-123">**Browser**</span><span class="sxs-lookup"><span data-stu-id="da107-123">**Browser**</span></span>|<span data-ttu-id="da107-124">Utilizzare questa scheda per esaminare i membri di una dimensione elaborata e per controllare le traduzioni dei metadati delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="da107-124">Use this tab to examine the members of a processed dimension and to review translations of dimension metadata.</span></span>|  
  
 <span data-ttu-id="da107-125">Negli argomenti seguenti vengono descritte le attività che è possibile eseguire in Progettazioni dimensioni.</span><span class="sxs-lookup"><span data-stu-id="da107-125">The following topics describe the tasks that you can perform in Dimension Designer.</span></span>  
  
 [<span data-ttu-id="da107-126">Riferimento alle proprietà degli attributo delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="da107-126">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
 <span data-ttu-id="da107-127">Descrive come definire e configurare un attributo di una dimensione.</span><span class="sxs-lookup"><span data-stu-id="da107-127">Describes how to define and configure a dimension attribute.</span></span>  
  
 [<span data-ttu-id="da107-128">Creare gerarchie definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="da107-128">Create User-Defined Hierarchies</span></span>](user-defined-hierarchies-create.md)  
 <span data-ttu-id="da107-129">Descrive come definire e configurare una gerarchia definita dall'utente.</span><span class="sxs-lookup"><span data-stu-id="da107-129">Describes how to define and configure a user-defined hierarchy.</span></span>  
  
 [<span data-ttu-id="da107-130">Definire relazioni tra attributi</span><span class="sxs-lookup"><span data-stu-id="da107-130">Define Attribute Relationships</span></span>](attribute-relationships-define.md)  
 <span data-ttu-id="da107-131">Descrive come definire e configurare una relazione tra attributi.</span><span class="sxs-lookup"><span data-stu-id="da107-131">Describes how to define and configure an attribute relationship.</span></span>  
  
 [<span data-ttu-id="da107-132">Utilizzare la Configurazione guidata funzionalità di Business Intelligence per migliorare le dimensioni</span><span class="sxs-lookup"><span data-stu-id="da107-132">Use the Business Intelligence Wizard to Enhance Dimensions</span></span>](../use-the-business-intelligence-wizard-to-enhance-dimensions.md)  
 <span data-ttu-id="da107-133">Viene descritto come utilizzare la Configurazione guidata funzionalità di Business Intelligence per ottimizzare una dimensione.</span><span class="sxs-lookup"><span data-stu-id="da107-133">Describes how to use the Business Intelligence Wizard to enhance a dimension.</span></span>  
  
  
