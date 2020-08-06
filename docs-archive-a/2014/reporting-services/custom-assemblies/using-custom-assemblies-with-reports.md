---
title: Uso di assembly personalizzati con i report | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom assemblies [Reporting Services]
- assemblies [Reporting Services], custom
- custom assemblies [Reporting Services], about custom assemblies
ms.assetid: 53d141d0-2185-466a-84dc-7b90d284da3d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f77b9da44ebb57617bd45e43d1e1e847e9074662
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713900"
---
# <a name="using-custom-assemblies-with-reports"></a><span data-ttu-id="6651c-102">Utilizzo di assembly personalizzati con i report</span><span class="sxs-lookup"><span data-stu-id="6651c-102">Using Custom Assemblies with Reports</span></span>
  <span data-ttu-id="6651c-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è possibile scrivere codice personalizzato per i valori, gli stili e la formattazione degli elementi dei report.</span><span class="sxs-lookup"><span data-stu-id="6651c-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can write custom code for report item values, styles, and formatting.</span></span> <span data-ttu-id="6651c-104">È ad esempio possibile utilizzare il codice personalizzato per formattare le valute in base alle impostazioni locali, per contrassegnare determinati valori con una formattazione speciale o per applicare altre regole di business in uso nella società.</span><span class="sxs-lookup"><span data-stu-id="6651c-104">For example, you can use custom code to format currencies based on locale, flag certain values with special formatting, or apply other business rules that are in practice for your company.</span></span> <span data-ttu-id="6651c-105">Un modo per includere questo codice nei report consiste nel creare un assembly di codice personalizzato usando l'oggetto a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] cui è possibile fare riferimento dall'interno dei file di definizione del report.</span><span class="sxs-lookup"><span data-stu-id="6651c-105">One way to include this code in your reports is to create a custom code assembly using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that you can reference from within your report definition files.</span></span> <span data-ttu-id="6651c-106">Il server chiama le funzioni degli assembly personalizzati durante l'esecuzione di un report.</span><span class="sxs-lookup"><span data-stu-id="6651c-106">The server calls the functions in your custom assemblies when a report is run.</span></span> <span data-ttu-id="6651c-107">Gli assembly personalizzati possono essere utilizzati per recuperare funzioni specifiche che si intende utilizzare nei report.</span><span class="sxs-lookup"><span data-stu-id="6651c-107">Custom assemblies can be used to retrieve specialized functions that you plan to use in your reports.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6651c-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6651c-108">In This Section</span></span>  
 [<span data-ttu-id="6651c-109">Impostazione di un riferimento agli assembly in un file RDL</span><span class="sxs-lookup"><span data-stu-id="6651c-109">Referencing Assemblies in an RDL File</span></span>](referencing-assemblies-in-an-rdl-file.md)  
 <span data-ttu-id="6651c-110">Viene descritto come fare riferimento agli assembly personalizzati in un file RDL (Report Definition Language).</span><span class="sxs-lookup"><span data-stu-id="6651c-110">Describes how to reference your custom assemblies in a report definition language file.</span></span>  
  
 [<span data-ttu-id="6651c-111">Distribuzione di un assembly personalizzato</span><span class="sxs-lookup"><span data-stu-id="6651c-111">Deploying a Custom Assembly</span></span>](deploying-a-custom-assembly.md)  
 <span data-ttu-id="6651c-112">Viene descritto come distribuire un assembly personalizzato in Progettazione report e nel server di report.</span><span class="sxs-lookup"><span data-stu-id="6651c-112">Describes how to deploy a custom assembly to Report Designer and the report server.</span></span>  
  
 [<span data-ttu-id="6651c-113">Utilizzo di assembly personalizzati con nome sicuro</span><span class="sxs-lookup"><span data-stu-id="6651c-113">Using Strong-Named Custom Assemblies</span></span>](using-strong-named-custom-assemblies.md)  
 <span data-ttu-id="6651c-114">Viene descritto come utilizzare gli assembly personalizzati con nomi sicuri.</span><span class="sxs-lookup"><span data-stu-id="6651c-114">Describes how to use custom assemblies with strong names.</span></span>  
  
 [<span data-ttu-id="6651c-115">Asserzione di autorizzazioni negli assembly personalizzati</span><span class="sxs-lookup"><span data-stu-id="6651c-115">Asserting Permissions in Custom Assemblies</span></span>](asserting-permissions-in-custom-assemblies.md)  
 <span data-ttu-id="6651c-116">Viene descritto come distribuire assembly personalizzati con autorizzazioni limitate e specifiche e come effettuare l'asserzione di tali autorizzazioni nel codice.</span><span class="sxs-lookup"><span data-stu-id="6651c-116">Describes how to deploy custom assemblies with limited and specific permissions and how to assert those permissions in code.</span></span>  
  
 [<span data-ttu-id="6651c-117">Accesso agli assembly personalizzati tramite espressioni</span><span class="sxs-lookup"><span data-stu-id="6651c-117">Accessing Custom Assemblies Through Expressions</span></span>](accessing-custom-assemblies-through-expressions.md)  
 <span data-ttu-id="6651c-118">Viene descritto come chiamare metodi di assembly personalizzati come espressioni di report nelle definizioni del report.</span><span class="sxs-lookup"><span data-stu-id="6651c-118">Describes how to call custom assembly methods as report expressions in your report definitions.</span></span>  
  
 [<span data-ttu-id="6651c-119">Inizializzazione di oggetti assembly personalizzati</span><span class="sxs-lookup"><span data-stu-id="6651c-119">Initializing Custom Assembly Objects</span></span>](initializing-custom-assembly-objects.md)  
 <span data-ttu-id="6651c-120">Viene descritto come inizializzare i valori per gli oggetti degli assembly personalizzati chiamati da un report.</span><span class="sxs-lookup"><span data-stu-id="6651c-120">Describes how to initialize values for custom assembly objects called from a report.</span></span>  
  
 [<span data-ttu-id="6651c-121">Procedura: Eseguire il debug di assembly personalizzati</span><span class="sxs-lookup"><span data-stu-id="6651c-121">How to: Debug Custom Assemblies</span></span>](how-to-debug-custom-assemblies.md)  
 <span data-ttu-id="6651c-122">Viene descritto come eseguire il debug del codice dell'assembly personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6651c-122">Describes how to debug your custom assembly code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6651c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6651c-123">See Also</span></span>  
 [<span data-ttu-id="6651c-124">Report Definition Language &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6651c-124">Report Definition Language &#40;SSRS&#41;</span></span>](../reports/report-definition-language-ssrs.md)  
  
  
