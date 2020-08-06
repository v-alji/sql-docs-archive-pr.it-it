---
title: Estensione di OLAP tramite personalizzazioni | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- Analysis Services, extensibility
ms.assetid: 348e49fc-4390-43c1-9b6c-61b386ff4373
author: minewiskan
ms.author: owend
ms.openlocfilehash: 93669980e989b1cb11673f45c111de3609bbe920
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725075"
---
# <a name="extending-olap-through-personalizations"></a><span data-ttu-id="1cc72-102">Estensione di OLAP tramite personalizzazioni</span><span class="sxs-lookup"><span data-stu-id="1cc72-102">Extending OLAP through personalizations</span></span>
  <span data-ttu-id="1cc72-103">In Microsoft [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] sono disponibili diverse funzioni intrinseche da utilizzare con i linguaggi MDX (Multidimensional Expressions) e DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="1cc72-103">Microsoft  [!INCLUDE[ssASCurrent](../../../includes/ssascurrent-md.md)] supplies many intrinsic functions for use with the Multidimensional Expressions (MDX) and Data Mining Extensions (DMX) languages.</span></span> <span data-ttu-id="1cc72-104">Queste funzioni sono progettate per consentire l'esecuzione di qualsiasi operazione, dai calcoli statistici standard all'attraversamento dei membri di una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="1cc72-104">These functions are designed to accomplish everything from standard statistical calculations to traversing members in a hierarchy.</span></span> <span data-ttu-id="1cc72-105">Come avviene per qualsiasi altro prodotto complesso e affidabile, tuttavia, si è avvertita l'esigenza di estendere ulteriormente le funzionalità di questo servizio.</span><span class="sxs-lookup"><span data-stu-id="1cc72-105">However, as with any other complex and robust product, there is always the need to extend the functionality of such a product further.</span></span>  
  
 <span data-ttu-id="1cc72-106">A tale scopo, Analysis Services offre la possibilità di aggiungere assembly ed estensioni personalizzate a un'istanza del servizio, per soddisfare le diverse esigenze aziendali ogni volta che le funzionalità standard si rivelano insufficienti.</span><span class="sxs-lookup"><span data-stu-id="1cc72-106">Therefore, Analysis Services provides you with the ability to add assemblies and personalized extensions to an instance of the service, in order to complete your business needs whenever the standard functionality is not enough.</span></span>  
  
## <a name="assemblies"></a><span data-ttu-id="1cc72-107">Assembly</span><span class="sxs-lookup"><span data-stu-id="1cc72-107">Assemblies</span></span>  
 <span data-ttu-id="1cc72-108">Gli assembly consentono di estendere la funzionalità business dei linguaggi MDX e DMX.</span><span class="sxs-lookup"><span data-stu-id="1cc72-108">Assemblies enable you to extend the business functionality of MDX and DMX.</span></span> <span data-ttu-id="1cc72-109">È necessario compilare la funzionalità desiderata in una libreria, ad esempio in una libreria a collegamento dinamico (DLL), quindi aggiungere tale libreria come assembly a un'istanza o a un database di Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="1cc72-109">You build the functionality that you want into a library, such as a dynamic link library (DLL), then add the library as an assembly to an instance of Analysis Services or to an Analysis Services database.</span></span> <span data-ttu-id="1cc72-110">I metodi pubblici della libreria vengono quindi esposti come funzioni definite dall'utente in espressioni MDX e DMX, procedure, calcoli, azioni e applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="1cc72-110">The public methods in the library are then exposed as user-defined functions to MDX and DMX expressions, procedures, calculations, actions, and client applications.</span></span>  
  
## <a name="personalized-extensions"></a><span data-ttu-id="1cc72-111">Estensioni personalizzate</span><span class="sxs-lookup"><span data-stu-id="1cc72-111">Personalized Extensions</span></span>  
 <span data-ttu-id="1cc72-112">Le estensioni della personalizzazione di SQL Server Analysis Services rappresentano la struttura di base dell'implementazione di un'architettura plug-in.</span><span class="sxs-lookup"><span data-stu-id="1cc72-112">SQL Server Analysis Services personalization extensions are the foundation of the idea of implementing a plug-in architecture.</span></span> <span data-ttu-id="1cc72-113">Analysis Services le estensioni di personalizzazione rappresentano una semplice ed elegante modifica all'architettura dell'assembly gestito esistente e vengono esposte nel modello a oggetti Analysis Services [Microsoft. AnalysisServices. AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) , nella sintassi MDX (Multidimensional Expressions) e nei set di righe dello schema.</span><span class="sxs-lookup"><span data-stu-id="1cc72-113">Analysis Services personalization extensions are a simple and elegant modification to the existing managed assembly architecture and are exposed throughout the Analysis Services [Microsoft.AnalysisServices.AdomdServer](/previous-versions/sql/sql-server-2014/ms131779(v=sql.120)) object model, Multidimensional Expressions (MDX) syntax, and schema rowsets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc72-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cc72-114">See Also</span></span>  
 <span data-ttu-id="1cc72-115">[Gestione di assembly di modelli multidimensionali](../multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="1cc72-115">[Multidimensional Model Assemblies Management](../multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="1cc72-116">Analysis Services Personalization Extensions</span><span class="sxs-lookup"><span data-stu-id="1cc72-116">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
  
