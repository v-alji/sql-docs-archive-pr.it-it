---
title: Architettura di un elemento del report personalizzato | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a053eb55547da9030eebe9036667cca2e14606f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623911"
---
# <a name="custom-report-item-architecture"></a><span data-ttu-id="91cca-102">Architettura di un elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="91cca-102">Custom Report Item Architecture</span></span>
  <span data-ttu-id="91cca-103">Un elemento del report personalizzato è un'estensione di RDL (Report Definition Language) che consente agli sviluppatori di aggiungere funzionalità per le quali non è disponibile il supporto nativo in RDL o di estendere le funzionalità dei controlli esistenti.</span><span class="sxs-lookup"><span data-stu-id="91cca-103">A custom report item is an extension to the Report Definition Language (RDL) that allows developers to add functionality that's not natively supported in RDL or extend the functionality of existing controls.</span></span> <span data-ttu-id="91cca-104">Un elemento del report personalizzato è costituito da due componenti principali: il componente della fase di esecuzione e quello della fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="91cca-104">There are two main components to a custom report item: the run-time component and the design-time component.</span></span> <span data-ttu-id="91cca-105">Questi componenti vengono implementati come assembly [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] e possono essere scritti in qualsiasi linguaggio conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="91cca-105">These components are implemented as [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assemblies, and can be written in any CLS-compliant language.</span></span>  
  
## <a name="the-run-time-component"></a><span data-ttu-id="91cca-106">Componente della fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="91cca-106">The Run-Time Component</span></span>  
 <span data-ttu-id="91cca-107">Il componente della fase di esecuzione per un elemento del report personalizzato viene chiamato da Elaborazione report in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="91cca-107">The run-time component for a custom report item is called by the report processor at run time.</span></span> <span data-ttu-id="91cca-108">Questo componente accetta i dati passati da Elaborazione report in fase di esecuzione, elabora tali dati e restituisce un'immagine contenente l'elemento del report personalizzato di cui è stato eseguito il rendering.</span><span class="sxs-lookup"><span data-stu-id="91cca-108">The run-time component accepts data passed by the report processor at run time, processes this data, and returns an image containing the rendered custom report item.</span></span>  
  
 <span data-ttu-id="91cca-109">![Componente della fase di esecuzione di un elemento del report personalizzato](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Componente della fase di esecuzione di un elemento del report personalizzato")</span><span class="sxs-lookup"><span data-stu-id="91cca-109">![Custom report item run-time component](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Custom report item run-time component")</span></span>  
  
## <a name="the-design-time-component"></a><span data-ttu-id="91cca-110">Componente della fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="91cca-110">The Design-Time Component</span></span>  
 <span data-ttu-id="91cca-111">Il componente della fase di progettazione consente la definizione e la modifica dell'elemento del report personalizzato nell'interfaccia di Progettazione report in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91cca-111">The design-time component allows the custom report item to be defined and manipulated in the Report Designer interface in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="91cca-112">Questo componente è costituito da diversi controlli secondari che definiscono l'aspetto e le proprietà dell'elemento del report personalizzato nell'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="91cca-112">The design-time component consists of several sub-controls that control the appearance and properties of the custom report item in the design environment.</span></span>  
  
 <span data-ttu-id="91cca-113">![Componente della fase di progettazione di un elemento del report personalizzato](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Componente della fase di progettazione di un elemento del report personalizzato")</span><span class="sxs-lookup"><span data-stu-id="91cca-113">![Custom report item design-time component](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Custom report item design-time component")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91cca-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91cca-114">See Also</span></span>  
 <span data-ttu-id="91cca-115">[Creazione di un componente runtime dell'elemento del report personalizzato](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="91cca-115">[Creating a Custom Report Item Run-Time Component](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="91cca-116">[Creazione di un componente della fase di progettazione di un elemento del report personalizzato](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="91cca-116">[Creating a Custom Report Item Design-Time Component](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span></span>  
 [<span data-ttu-id="91cca-117">Procedura: Distribuire un elemento del report personalizzato</span><span class="sxs-lookup"><span data-stu-id="91cca-117">How to: Deploy a Custom Report Item</span></span>](../custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
