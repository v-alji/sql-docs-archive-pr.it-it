---
title: Nozioni fondamentali sullo scripting MDX (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], scripts
- calculations [Analysis Services], scripts
- MDX [Analysis Services], scripts
- scripts [MDX]
- cubes [Analysis Services], calculations
- Multidimensional Expressions [Analysis Services], scripts
ms.assetid: fdecb3ce-7c87-4bab-8000-532ba7a29f96
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2f7638339d8fc366ee384d453f6df683f3bd41f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635822"
---
# <a name="mdx-scripting-fundamentals-analysis-services"></a><span data-ttu-id="c2789-102">Nozioni fondamentali sullo scripting MDX (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="c2789-102">MDX Scripting Fundamentals (Analysis Services)</span></span>
  <span data-ttu-id="c2789-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], uno script MDX (Multidimensional Expressions) è costituito da una o più espressioni o istruzioni MDX che popolano un cubo tramite calcoli.</span><span class="sxs-lookup"><span data-stu-id="c2789-103">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], a Multidimensional Expressions (MDX) script is made up of one or more MDX expressions or statements that populate a cube with calculations.</span></span>  
  
 <span data-ttu-id="c2789-104">Uno script MDX definisce il processo di calcolo per un cubo</span><span class="sxs-lookup"><span data-stu-id="c2789-104">An MDX script defines the calculation process for a cube.</span></span> <span data-ttu-id="c2789-105">ed è considerato parte del cubo stesso.</span><span class="sxs-lookup"><span data-stu-id="c2789-105">An MDX script is also considered part of the cube itself.</span></span> <span data-ttu-id="c2789-106">La modifica di uno script MDX associato a un cubo comporta pertanto la modifica immediata del processo di calcolo per il cubo.</span><span class="sxs-lookup"><span data-stu-id="c2789-106">Therefore, changing an MDX script associated with a cube immediately changes the calculation process for the cube.</span></span>  
  
 <span data-ttu-id="c2789-107">Per creare script MDX, è possibile usare Progettazione cubi in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2789-107">To create MDX scripts, you can use Cube Designer in the [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="c2789-108">Per altre informazioni, vedere [Definire le assegnazioni e altri comandi script](../define-assignments-and-other-script-commands.md) e [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892)(Introduzione alla creazione di script MDX in Microsoft SQL Server 2005).</span><span class="sxs-lookup"><span data-stu-id="c2789-108">For more information, see [Define Assignments and Other Script Commands](../define-assignments-and-other-script-commands.md) and [Introduction to MDX Scripting in Microsoft SQL Server 2005](https://go.microsoft.com/fwlink/?LinkId=81892).</span></span>  
  
 <span data-ttu-id="c2789-109">Per problemi di prestazioni relativi a query e calcoli MDX, vedere la sezione relativa all'ottimizzazione MDX nella [guida alle prestazioni di SQL Server Analysis Services](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span><span class="sxs-lookup"><span data-stu-id="c2789-109">For performance issues related to MDX queries and calculations, see the MDX optimization section in the [SQL Server Analysis Services Performance Guide](https://go.microsoft.com/fwlink/p/?LinkId=399050).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2789-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="c2789-110">In This Section</span></span>  
  
|<span data-ttu-id="c2789-111">Argomento</span><span class="sxs-lookup"><span data-stu-id="c2789-111">Topic</span></span>|<span data-ttu-id="c2789-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2789-112">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c2789-113">Script MDX di base &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c2789-113">The Basic MDX Script &#40;MDX&#41;</span></span>](the-basic-mdx-script-mdx.md)|<span data-ttu-id="c2789-114">Include informazioni dettagliate sullo script MDX di base, compreso lo script MDX predefinito inserito in ogni cubo, e sui principi generali di funzionamento degli script MDX nei cubi di [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2789-114">Details the basic MDX script, including the default MDX script provided in each cube, and how MDX scripts generally function within a cube in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="c2789-115">Gestione di ambito e contesto &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c2789-115">Managing Scope and Context &#40;MDX&#41;</span></span>](managing-scope-and-context-mdx.md)|<span data-ttu-id="c2789-116">Descrive come usare l'istruzione [CALCULATE](/sql/mdx/mdx-scripting-calculate) , l'istruzione [SCOPE](/sql/mdx/mdx-scripting-scope) e la funzione [This](/sql/mdx/this-mdx) per gestire il contesto e l'ambito in uno script MDX.</span><span class="sxs-lookup"><span data-stu-id="c2789-116">Describes how to use the [CALCULATE](/sql/mdx/mdx-scripting-calculate) statement, the [SCOPE](/sql/mdx/mdx-scripting-scope) statement, and the [This](/sql/mdx/this-mdx) function to manage context and scope within an MDX script.</span></span>|  
|[<span data-ttu-id="c2789-117">Utilizzo di variabili e parametri &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c2789-117">Using Variables and Parameters &#40;MDX&#41;</span></span>](using-variables-and-parameters-mdx.md)|<span data-ttu-id="c2789-118">Descrive come usare le variabili e i parametri in uno script MDX.</span><span class="sxs-lookup"><span data-stu-id="c2789-118">Describes how to use variables and parameters in an MDX script.</span></span>|  
|[<span data-ttu-id="c2789-119">Gestione degli errori &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c2789-119">Error Handling &#40;MDX&#41;</span></span>](error-handling-mdx.md)|<span data-ttu-id="c2789-120">Illustra la gestione degli errori in uno script MDX.</span><span class="sxs-lookup"><span data-stu-id="c2789-120">Explains error handling within an MDX script.</span></span>|  
|[<span data-ttu-id="c2789-121">Istruzioni e funzioni MDX supportate &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c2789-121">Supported MDX &#40;MDX&#41;</span></span>](supported-mdx-mdx.md)|<span data-ttu-id="c2789-122">Include un elenco di istruzioni, funzioni e operatori MDX supportati negli script MDX.</span><span class="sxs-lookup"><span data-stu-id="c2789-122">Provides a list of supported MDX operators, statements, and functions within an MDX script.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2789-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2789-123">See Also</span></span>  
 [<span data-ttu-id="c2789-124">Guida di riferimento al linguaggio MDX &#40;MDX&#41;</span><span class="sxs-lookup"><span data-stu-id="c2789-124">MDX Language Reference &#40;MDX&#41;</span></span>](/sql/mdx/mdx-language-reference-mdx)  
  
  
