---
title: Novità di&#39;(Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, what's new
- what's new [Integration Services]
ms.assetid: da6999c7-e5e3-4a59-a284-1da635995af1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84f0b668407c89e1d6acc3c8cfbda73f129ca19a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636772"
---
# <a name="what39s-new-integration-services"></a><span data-ttu-id="4ed9d-102">Novità di&#39;(Integration Services)</span><span class="sxs-lookup"><span data-stu-id="4ed9d-102">What&#39;s New (Integration Services)</span></span>
  [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="4ed9d-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]è invariato rispetto alla versione precedente.</span><span class="sxs-lookup"><span data-stu-id="4ed9d-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is unchanged from the previous release.</span></span>  
  
 <span data-ttu-id="4ed9d-104">Per informazioni su altri [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] prodotti e tecnologie, vedere Novità [di SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="4ed9d-104">For information about other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="4ed9d-105">Per ulteriori informazioni sulle modifiche correlate a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, vedere Novità [di Analysis Services e Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="4ed9d-105">For more information about changes related to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, see [What's New in Analysis Services and Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span></span>  
  
##  <a name="rich-xml-validation-output-in-the-xml-task"></a><a name="ValidateXML"></a> <span data-ttu-id="4ed9d-106">Output di convalida XML avanzato in Attività XML</span><span class="sxs-lookup"><span data-stu-id="4ed9d-106">Rich XML validation output in the XML Task</span></span>  
 <span data-ttu-id="4ed9d-107">È possibile convalidare documenti XML e ottenere output avanzato degli errori abilitando la proprietà `ValidationDetails` dell'Attività XML.</span><span class="sxs-lookup"><span data-stu-id="4ed9d-107">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span> <span data-ttu-id="4ed9d-108">Prima che fosse disponibile la proprietà `ValidationDetails`, la convalida XML da parte dell'Attività XML restituiva solo un risultato di tipo True o False, senza informazioni sugli errori o sulle rispettive posizioni.</span><span class="sxs-lookup"><span data-stu-id="4ed9d-108">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="4ed9d-109">Attualmente, quando si imposta `ValidationDetails` su True, il file di output contiene informazioni dettagliate su ogni errore, inclusi il numero di riga e la posizione.</span><span class="sxs-lookup"><span data-stu-id="4ed9d-109">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="4ed9d-110">È possibile usare questa informazione per comprendere, individuare e risolvere gli errori nei documenti XML.</span><span class="sxs-lookup"><span data-stu-id="4ed9d-110">You can use this information to understand, locate, and fix errors in XML documents.</span></span> <span data-ttu-id="4ed9d-111">Per ulteriori informazioni, vedere [Validate XML with the XML Task](control-flow/xml-task.md).</span><span class="sxs-lookup"><span data-stu-id="4ed9d-111">For more info, see [Validate XML with the XML Task](control-flow/xml-task.md).</span></span>  
  
 [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="4ed9d-112">ha introdotto la proprietà `ValidationDetails` in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="4ed9d-112">introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="4ed9d-113">Questa nuova proprietà non è stata annunciata o documentata in quel momento.</span><span class="sxs-lookup"><span data-stu-id="4ed9d-113">This new property was not announced or documented at that time.</span></span> <span data-ttu-id="4ed9d-114">La proprietà `ValidationDetails` è disponibile anche in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] e in SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="4ed9d-114">The `ValidationDetails` property is also available in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed9d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ed9d-115">See Also</span></span>  
 [<span data-ttu-id="4ed9d-116">Funzionalità supportate dalle edizioni di SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4ed9d-116">Features Supported by the Editions of SQL Server 2014</span></span>](../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
