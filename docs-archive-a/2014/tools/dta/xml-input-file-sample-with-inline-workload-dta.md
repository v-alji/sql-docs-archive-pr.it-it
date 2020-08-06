---
title: Esempio di file di input XML con carico di lavoro inline (DTA) | Microsoft Docs
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
ms.assetid: 7c04fe1d-6669-44a1-8b73-36d469e9b002
author: stevestein
ms.author: sstein
ms.openlocfilehash: 93b2ab4279378b4cd392d97a9b65f299d0e9c6dc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626997"
---
# <a name="xml-input-file-sample-with-inline-workload-dta"></a><span data-ttu-id="0dc58-102">Esempio di file di input XML con carico di lavoro inline (DTA)</span><span class="sxs-lookup"><span data-stu-id="0dc58-102">XML Input File Sample with Inline Workload (DTA)</span></span>
  <span data-ttu-id="0dc58-103">Copiare e incollare questo esempio di file di input XML che specifica un carico di lavoro con l'elemento **EventString** nell'editor XML o nell'editor di testo preferito.</span><span class="sxs-lookup"><span data-stu-id="0dc58-103">Copy and paste this sample of an XML input file that specifies a workload with the **EventString** element into your favorite XML editor or text editor.</span></span> <span data-ttu-id="0dc58-104">È possibile utilizzare l'elemento **EventString** per specificare il carico di lavoro di uno script [!INCLUDE[tsql](../../includes/tsql-md.md)] nel file XML invece di utilizzare un file del carico di lavoro separato.</span><span class="sxs-lookup"><span data-stu-id="0dc58-104">You can use the **EventString** element to specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script workload in the XML input file instead of using a separate workload file.</span></span> <span data-ttu-id="0dc58-105">Dopo aver copiato questo esempio nello strumento di modifica desiderato, sostituire i valori specificati per gli elementi **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**e **TuningOptions** con i valori per la sessione di ottimizzazione specifica.</span><span class="sxs-lookup"><span data-stu-id="0dc58-105">After copying this sample into your editing tool, replace the values specified for the **Server**, **Database**, **Schema**, **Table**, **Workload**, **EventString**, and **TuningOptions** elements with those for your specific tuning session.</span></span> <span data-ttu-id="0dc58-106">Per altre informazioni su tutti gli attributi e gli elementi figlio che è possibile usare con questi elementi, vedere [Guida di riferimento ai file di input XML &#40;Ottimizzazione guidata motore di database&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span><span class="sxs-lookup"><span data-stu-id="0dc58-106">For more information about all of the attributes and child elements that you can use with these elements, see the [XML Input File Reference &#40;Database Engine Tuning Advisor&#41;](xml-input-file-reference-database-engine-tuning-advisor.md).</span></span> <span data-ttu-id="0dc58-107">Nell'esempio seguente viene utilizzato solo un subset delle opzioni relative agli attributi e agli elementi figlio disponibili.</span><span class="sxs-lookup"><span data-stu-id="0dc58-107">The following sample uses only a subset of available attribute and child element options.</span></span>  
  
## <a name="code"></a><span data-ttu-id="0dc58-108">Codice</span><span class="sxs-lookup"><span data-stu-id="0dc58-108">Code</span></span>  
 [!code-xml[InputFileSamples#InlineWorkloadInputFile](../../snippets/xml/SQL14/dta_xml/inputfilesamples/xml/dta_xml_input_file_samples.xml#inlineworkloadinputfile)]  
  
## <a name="comments"></a><span data-ttu-id="0dc58-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="0dc58-109">Comments</span></span>  
 <span data-ttu-id="0dc58-110">`USE database_name` nel carico di lavoro inline contenuto nell'elemento **EventString** .</span><span class="sxs-lookup"><span data-stu-id="0dc58-110">`USE database_name` statements can be specified in the inline workload that is contained in the **EventString** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dc58-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dc58-111">See Also</span></span>  
 <span data-ttu-id="0dc58-112">[Avvio e utilizzo di Ottimizzazione guidata motore di database](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0dc58-112">[Start and Use the Database Engine Tuning Advisor](../../relational-databases/performance/start-and-use-the-database-engine-tuning-advisor.md) </span></span>  
 <span data-ttu-id="0dc58-113">[Visualizzare e utilizzare l'output di Ottimizzazione guidata motore di database](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="0dc58-113">[View and Work with the Output from the Database Engine Tuning Advisor](../../relational-databases/performance/view-and-work-with-the-output-from-the-database-engine-tuning-advisor.md) </span></span>  
 [<span data-ttu-id="0dc58-114">Guida di riferimento ai file di input XML&#40; (Ottimizzazione guidata motore di database)&#41;</span><span class="sxs-lookup"><span data-stu-id="0dc58-114">XML Input File Reference &#40;Database Engine Tuning Advisor&#41;</span></span>](xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
