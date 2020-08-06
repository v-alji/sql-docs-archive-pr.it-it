---
title: Elementi dei report personalizzati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- extending Reporting Services
- Reporting Services, extending
- custom report items
ms.assetid: 64dcaf2c-1af5-4937-8ff7-98f1ec3b367e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 86b819cb4d305e537a52a2e7f25cdfa3aefa5f9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725315"
---
# <a name="custom-report-items"></a><span data-ttu-id="9d25a-102">Elementi dei report personalizzati</span><span class="sxs-lookup"><span data-stu-id="9d25a-102">Custom Report Items</span></span>
  <span data-ttu-id="9d25a-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è disponibile un set completo di strumenti per la compilazione e la pubblicazione di report aziendali, la gestione di sicurezza e sottoscrizioni e l'estensione della funzionalità di report tramite un'API completa.</span><span class="sxs-lookup"><span data-stu-id="9d25a-103">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] provides a rich set of tools for building and publishing enterprise reports, managing security and subscriptions, and extending the reporting functionality through a comprehensive API.</span></span> <span data-ttu-id="9d25a-104">I report vengono definiti utilizzando un linguaggio XML denominato Report Definition Language (RDL).</span><span class="sxs-lookup"><span data-stu-id="9d25a-104">Reports are defined using an XML-based language called Report Definition Language (RDL).</span></span> <span data-ttu-id="9d25a-105">RDL offre un set di istruzioni che descrivono le informazioni relative al layout e alle query e i tipi di elementi per un report.</span><span class="sxs-lookup"><span data-stu-id="9d25a-105">RDL provides a set of instructions that describe layout, query information, and item types for a report.</span></span> <span data-ttu-id="9d25a-106">È possibile estendere RDL scrivendo un elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9d25a-106">It is possible to extend RDL by writing a custom report item.</span></span> <span data-ttu-id="9d25a-107">Tale elemento è costituito da un componente runtime, che viene chiamato dal componente Elaborazione report in fase di esecuzione, e da un componente della fase di progettazione, che rende disponibile l'elemento del report personalizzato in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="9d25a-107">The custom report item consists of a run-time component, which is called by the report processor at run time, and a design-time component, which allows the custom report item to be available in Report Designer.</span></span>  
  
 <span data-ttu-id="9d25a-108">Per un esempio di elemento del report personalizzato completamente implementato, vedere [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889) (Esempi del prodotto SQL Server Reporting Services).</span><span class="sxs-lookup"><span data-stu-id="9d25a-108">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="custom-report-item-scenarios"></a><span data-ttu-id="9d25a-109">Scenari di elementi del report personalizzati</span><span class="sxs-lookup"><span data-stu-id="9d25a-109">Custom Report Item Scenarios</span></span>  
 <span data-ttu-id="9d25a-110">Gli sviluppatori che devono integrare [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nelle proprie applicazioni possono necessitare di funzionalità non supportate in RDL a livello nativo.</span><span class="sxs-lookup"><span data-stu-id="9d25a-110">Developers who need to integrate [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] into their applications may require functionality that is not natively supported in RDL.</span></span> <span data-ttu-id="9d25a-111">Tali funzionalità includono ad esempio elementi quali controlli di mapping, elenchi orizzontali, elenchi in formato colonna e matrici di tabelle pivot.</span><span class="sxs-lookup"><span data-stu-id="9d25a-111">This may include items such as: map controls, horizontal lists, columnar lists, and repivotable matrixes.</span></span> <span data-ttu-id="9d25a-112">Un componente runtime dell'elemento del report personalizzato può essere sviluppato e distribuito con un'applicazione per soddisfare queste esigenze.</span><span class="sxs-lookup"><span data-stu-id="9d25a-112">A run-time custom report item component can be developed and distributed with an application to fill this need.</span></span>  
  
 <span data-ttu-id="9d25a-113">Oltre a disporre di funzionalità non supportate a livello nativo, alcuni sviluppatori potrebbero avere l'esigenza di estendere le funzionalità esistenti con versioni alternative di controlli già inclusi in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d25a-113">In addition to providing functionality that isn't natively supported, some developers may want to extend existing functionality with alternative versions of controls that are already included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="9d25a-114">In questo scenario, uno sviluppatore potrebbe disporre di tre componenti: un componente runtime, un componente della fase di progettazione e un componente di conversione dell'elemento del report in fase di progettazione che consente di convertire su richiesta un elemento del report esistente in un elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9d25a-114">In this scenario, a developer could provide three components: a run-time component, a design-time component, and a design-time report item conversion component that converts an existing report item into a custom report item on demand.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9d25a-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9d25a-115">In This Section</span></span>  
 [<span data-ttu-id="9d25a-116">Architettura di un elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="9d25a-116">Custom Report Item Architecture</span></span>](custom-report-item-architecture.md)  
 <span data-ttu-id="9d25a-117">Vengono descritti i componenti che costituiscono un elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9d25a-117">Describes the components that make up a custom report item.</span></span>  
  
 [<span data-ttu-id="9d25a-118">Requisiti per l'implementazione di elementi dei report personalizzati</span><span class="sxs-lookup"><span data-stu-id="9d25a-118">Custom Report Item Implementation Requirements</span></span>](custom-report-item-implementation-requirements.md)  
 <span data-ttu-id="9d25a-119">Vengono descritti i prerequisiti per la creazione di un elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9d25a-119">Describes prerequisites for creating a custom report item.</span></span>  
  
 [<span data-ttu-id="9d25a-120">Creazione di un componente runtime dell'elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="9d25a-120">Creating a Custom Report Item Run-Time Component</span></span>](creating-a-custom-report-item-run-time-component.md)  
 <span data-ttu-id="9d25a-121">Vengono descritte le procedure per la creazione di un componente runtime dell'elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9d25a-121">Describes how to create a custom report item run-time component.</span></span>  
  
 [<span data-ttu-id="9d25a-122">Creazione di un componente dell'elemento del report personalizzato per la fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="9d25a-122">Creating a Custom Report Item Design-Time Component</span></span>](creating-a-custom-report-item-design-time-component.md)  
 <span data-ttu-id="9d25a-123">Vengono descritte le procedure per la creazione di un componente dell'elemento del report personalizzato in fase in progettazione.</span><span class="sxs-lookup"><span data-stu-id="9d25a-123">Describes how to create a custom report item design-time component.</span></span>  
  
 [<span data-ttu-id="9d25a-124">Procedura: Distribuire un elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="9d25a-124">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
 <span data-ttu-id="9d25a-125">Vengono descritte le procedure per la distribuzione di un elemento del report personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9d25a-125">Describes how to deploy a custom report item.</span></span>  
  
 [<span data-ttu-id="9d25a-126">Librerie di classi dell'elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="9d25a-126">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
 <span data-ttu-id="9d25a-127">Vengono descritte le classi di infrastruttura dell'elemento del report personalizzato e classi wrapper gestite nello spazio dei nomi `Microsoft.ReportDesigner`.</span><span class="sxs-lookup"><span data-stu-id="9d25a-127">Describes the custom report item infrastructure classes and managed wrapper classes in the `Microsoft.ReportDesigner` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d25a-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d25a-128">See Also</span></span>  
 [<span data-ttu-id="9d25a-129">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9d25a-129">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
