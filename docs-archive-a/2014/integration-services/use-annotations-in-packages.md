---
title: Usare le annotazioni nei pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- self-documenting packages
- adding annotations
- annotations [Integration Services]
ms.assetid: 48c8ed9a-b10d-490c-9ba7-4b77aa44e3dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 27c7df6afd894ea9730027da1d54786ed8397fad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638457"
---
# <a name="use-annotations-in-packages"></a><span data-ttu-id="27e1b-102">Utilizzo di annotazioni nei pacchetti</span><span class="sxs-lookup"><span data-stu-id="27e1b-102">Use Annotations in Packages</span></span>
  <span data-ttu-id="27e1b-103">In Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] sono disponibili annotazioni che è possibile utilizzare per ottenere pacchetti autodocumentati, più semplici da capire e gestire.</span><span class="sxs-lookup"><span data-stu-id="27e1b-103">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides annotations, which you can use to make packages self-documenting and easier to understand and maintain.</span></span> <span data-ttu-id="27e1b-104">È possibile aggiungere annotazioni alle aree di progettazione dei flussi di controllo, dei flussi di dati e dei gestori di eventi di Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="27e1b-104">You can add annotations to the control flow, data flow, and event handler design surfaces of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="27e1b-105">Nelle annotazioni può essere contenuto qualsiasi tipo di testo e possono essere utilizzate per aggiungere etichette, commenti e altre informazioni descrittive a un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="27e1b-105">The annotations can contain any type of text, and they are useful for adding labels, comments, and other descriptive information to a package.</span></span> <span data-ttu-id="27e1b-106">Le annotazioni sono disponibili solo in modalità progettazione.</span><span class="sxs-lookup"><span data-stu-id="27e1b-106">Annotations are a design-time feature only.</span></span> <span data-ttu-id="27e1b-107">Non possono essere ad esempio scritte nei log.</span><span class="sxs-lookup"><span data-stu-id="27e1b-107">For example, they are not written to logs.</span></span>  
  
 <span data-ttu-id="27e1b-108">Quando si preme INVIO, il testo viene riportato nella riga successiva.</span><span class="sxs-lookup"><span data-stu-id="27e1b-108">When you press ENTER, the text wraps to the next line.</span></span> <span data-ttu-id="27e1b-109">Le dimensioni della casella delle annotazioni aumentano automaticamente man mano che si aggiungono le righe di testo.</span><span class="sxs-lookup"><span data-stu-id="27e1b-109">The annotation box automatically increases in size as you add additional lines of text.</span></span> <span data-ttu-id="27e1b-110">Le annotazioni dei pacchetti vengono rese persistenti come testo non crittografato nella sezione CDATA del file del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="27e1b-110">Package annotations are persisted as clear text in the CDATA section of the package file.</span></span>  
  
 <span data-ttu-id="27e1b-111">Per altre informazioni sulle modifiche al formato del file del pacchetto, vedere [Formato del pacchetto SSIS](../../2014/integration-services/ssis-package-format.md).</span><span class="sxs-lookup"><span data-stu-id="27e1b-111">For more information about changes to the format of the package file, see [SSIS Package Format](../../2014/integration-services/ssis-package-format.md).</span></span>  
  
 <span data-ttu-id="27e1b-112">Quando si salva un pacchetto, Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] salva le annotazioni nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="27e1b-112">When you save the package, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the annotations in the package.</span></span>  
  
### <a name="to-add-an-annotation-to-a-package"></a><span data-ttu-id="27e1b-113">Per aggiungere un'annotazione a un pacchetto</span><span class="sxs-lookup"><span data-stu-id="27e1b-113">To add an annotation to a package</span></span>  
  
-   [<span data-ttu-id="27e1b-114">Aggiunta di un'annotazione a un pacchetto</span><span class="sxs-lookup"><span data-stu-id="27e1b-114">Add an Annotation to a Package</span></span>](../../2014/integration-services/add-an-annotation-to-a-package.md)  
  
  
