---
title: Esempio di file di input XML con configurazione specificata dall'utente (DTA) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- sample applications [DTA]
ms.assetid: b29c9716-e5c3-4003-9efb-3ade2197b630
author: stevestein
ms.author: sstein
ms.openlocfilehash: 121972518aa114e16cc81517d52a9d9656b067c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635298"
---
# <a name="xml-input-file-sample-with-user-specified-configuration-dta"></a><span data-ttu-id="161ed-102">Esempio di file di input XML con configurazione specificata dall'utente (DTA)</span><span class="sxs-lookup"><span data-stu-id="161ed-102">XML Input File Sample with User-specified Configuration (DTA)</span></span>
  <span data-ttu-id="161ed-103">Copiare e incollare questo esempio di file di input XML che contiene una configurazione specificata dall'utente con l'elemento **Configuration** nell'editor di testo o nell'editor XML preferito.</span><span class="sxs-lookup"><span data-stu-id="161ed-103">Copy and paste this sample of an XML input file that specifies a user-specified configuration with the **Configuration** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="161ed-104">In questo modo sarà possibile eseguire analisi di simulazione</span><span class="sxs-lookup"><span data-stu-id="161ed-104">This enables you to perform "what-if" analysis.</span></span> <span data-ttu-id="161ed-105">che comportano l'uso dell'elemento **Configuration** per specificare un set di strutture di progettazione fisica ipotetiche per il database che si vuole ottimizzare.</span><span class="sxs-lookup"><span data-stu-id="161ed-105">"What-if" analysis involves using the **Configuration** element to specify a set of hypothetical physical design structures for the database you want to tune.</span></span> <span data-ttu-id="161ed-106">Per sapere se è possibile migliorare le prestazioni di elaborazione delle query, verrà quindi utilizzata l'Ottimizzazione guidata motore di database per analizzare gli effetti dell'esecuzione di un carico di lavoro rispetto a questa configurazione ipotetica.</span><span class="sxs-lookup"><span data-stu-id="161ed-106">Then you use Database Engine Tuning Advisor to analyze the effects of running a workload against this hypothetical configuration to find out whether it improves query processing performance.</span></span> <span data-ttu-id="161ed-107">Questo tipo di analisi ha il vantaggio di valutare la nuova configurazione senza l'overhead dovuto all'effettiva implementazione.</span><span class="sxs-lookup"><span data-stu-id="161ed-107">This type of analysis provides the advantage of evaluating the new configuration without incurring the overhead of actually implementing it.</span></span> <span data-ttu-id="161ed-108">Se la configurazione ipotetica non consente di ottenere i miglioramenti delle prestazioni desiderati, è possibile modificarla e analizzarla di nuovo finché non verranno prodotti i risultati necessari.</span><span class="sxs-lookup"><span data-stu-id="161ed-108">If your hypothetical configuration does not provide the performance improvements you want, it is easy to change it and analyze it again until you reach the configuration that produces the results you need.</span></span>  
  
 <span data-ttu-id="161ed-109">Dopo avere copiato questo esempio nello strumento di modifica desiderato, sostituire i valori specificati per gli elementi **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**e **Configuration** con i valori per la sessione di ottimizzazione specifica.</span><span class="sxs-lookup"><span data-stu-id="161ed-109">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **TuningOptions**, and **Configuration** elements with those for your specific tuning session.</span></span> <span data-ttu-id="161ed-110">Per altre informazioni su tutti gli attributi e gli elementi figlio che è possibile usare con questi elementi, vedere [Guida di riferimento ai file di input XML &#40;Ottimizzazione guidata motore di database&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="161ed-110">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="161ed-111">Nell'esempio seguente viene utilizzato solo un subset delle opzioni relative agli attributi e agli elementi figlio disponibili.</span><span class="sxs-lookup"><span data-stu-id="161ed-111">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="161ed-112">Codice</span><span class="sxs-lookup"><span data-stu-id="161ed-112">Code</span></span>  
 [!code-xml[InputFileSamples#UserSpecifiedConfigInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#userspecifiedconfiginputfile)]  
  
## <a name="comments"></a><span data-ttu-id="161ed-113">Commenti</span><span class="sxs-lookup"><span data-stu-id="161ed-113">Comments</span></span>  
  
-   <span data-ttu-id="161ed-114">L'eliminazione di strutture di progettazione fisica non è supportata se si specifica la modalità **Absolute** per l'elemento **Configuration** (`Configuration SpecificationMode="Absolute"`).</span><span class="sxs-lookup"><span data-stu-id="161ed-114">Dropping physical design structures is not supported if you specify the **Absolute** mode for the **Configuration** element (`Configuration SpecificationMode="Absolute"`).</span></span>  
  
-   <span data-ttu-id="161ed-115">La stessa struttura di progettazione fisica non può essere creata ed eliminata in modalità**Relative** o **Absolute**dell'elemento **Configuration** .</span><span class="sxs-lookup"><span data-stu-id="161ed-115">You cannot create and drop the same physical design structure in either mode (**Relative** or **Absolute**) of the **Configuration** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161ed-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="161ed-116">See Also</span></span>  
 <span data-ttu-id="161ed-117">[Avvio e utilizzo di Ottimizzazione guidata motore di database](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="161ed-117">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="161ed-118">[Visualizzare e utilizzare l'output di Ottimizzazione guidata motore di database](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="161ed-118">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="161ed-119">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="161ed-119">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
