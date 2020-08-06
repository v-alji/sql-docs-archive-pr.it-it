---
title: Sviluppo con Analysis Services Scripting Language (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services Scripting Language
- ASSL
ms.assetid: ce9aca4d-b7ad-451e-bb7f-20c2b0c03f29
author: minewiskan
ms.author: owend
ms.openlocfilehash: fbb64c120e67d5b4ac12e7bd77f0e0c4e5736757
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629061"
---
# <a name="developing-with-analysis-services-scripting-language-assl"></a><span data-ttu-id="1e985-102">Sviluppo con Analysis Services Scripting Language (ASSL)</span><span class="sxs-lookup"><span data-stu-id="1e985-102">Developing with Analysis Services Scripting Language (ASSL)</span></span>
  <span data-ttu-id="1e985-103">ASSL (Analysis Services Scripting Language) è un'estensione di XMLA che aggiunge un linguaggio di definizione dell'oggetto e un linguaggio di comando per la creazione e la gestione di strutture di Analysis Services direttamente sul server.</span><span class="sxs-lookup"><span data-stu-id="1e985-103">Analysis Services Scripting Language (ASSL) is an extension to XMLA that adds an object definition language and command language for creating and managing Analysis Services structures directly on the server.</span></span> <span data-ttu-id="1e985-104">È possibile utilizzare ASSL in un'applicazione personalizzata per comunicare con Analysis Services mediante il protocollo XMLA.</span><span class="sxs-lookup"><span data-stu-id="1e985-104">You can use ASSL in custom application to communicate with Analysis Services over the XMLA protocol.</span></span> <span data-ttu-id="1e985-105">Il linguaggio ASSL è costituito da due componenti:</span><span class="sxs-lookup"><span data-stu-id="1e985-105">ASSL is made up of two parts:</span></span>  
  
-   <span data-ttu-id="1e985-106">Linguaggio DDL (Data Definition Language), o linguaggio di definizione dell'oggetto, che specifica e descrive un'istanza di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] nonché i database e gli oggetti di database che l'istanza contiene.</span><span class="sxs-lookup"><span data-stu-id="1e985-106">A Data Definition Language (DDL), or object definition language, defines and describes an instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], as well as the databases and database objects that the instance contains.</span></span>  
  
-   <span data-ttu-id="1e985-107">Linguaggio di comando che invia comandi di azione, ad esempio `Create`, `Alter` o `Process`, a un'istanza di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1e985-107">A command language that sends action commands, such as `Create`, `Alter`, or `Process`, to an instance of Analysis Services.</span></span> <span data-ttu-id="1e985-108">Questo linguaggio di comando è illustrato nella [XML for Analysis &#40;riferimento&#41; XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span><span class="sxs-lookup"><span data-stu-id="1e985-108">This command language is discussed in the [XML for Analysis  &#40;XMLA&#41; Reference](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-xmla-reference).</span></span>  
  
 <span data-ttu-id="1e985-109">Per visualizzare l'ASSL che descrive una soluzione multidimensionale in [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], è possibile utilizzare il comando Visualizza codice al livello del progetto.</span><span class="sxs-lookup"><span data-stu-id="1e985-109">To view the ASSL that describes a multidimensional solution in [!INCLUDE[ssBIDevStudio](../../../includes/ssbidevstudio-md.md)], you can use the View Code command at the project level.</span></span> <span data-ttu-id="1e985-110">È inoltre possibile creare o modificare script ASSL in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] utilizzando l'editor di query XMLA.</span><span class="sxs-lookup"><span data-stu-id="1e985-110">You can also create or edit ASSL script in [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)] using the XMLA query editor.</span></span> <span data-ttu-id="1e985-111">Gli script compilati possono essere utilizzati per gestire oggetti o eseguire comandi nel server.</span><span class="sxs-lookup"><span data-stu-id="1e985-111">The scripts you build can be used to manage objects or run commands on the server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e985-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e985-112">See Also</span></span>  
 <span data-ttu-id="1e985-113">[Oggetti ASSL e caratteristiche oggetto](assl-objects-and-object-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="1e985-113">[ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md) </span></span>  
 <span data-ttu-id="1e985-114">[Convenzioni XML di ASSL](assl-xml-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="1e985-114">[ASSL XML Conventions](assl-xml-conventions.md) </span></span>  
 [<span data-ttu-id="1e985-115">Origini dati e associazioni &#40;SSAS multidimensionale&#41;</span><span class="sxs-lookup"><span data-stu-id="1e985-115">Data Sources and Bindings &#40;SSAS Multidimensional&#41;</span></span>](../data-sources-and-bindings-ssas-multidimensional.md)  
  
  
