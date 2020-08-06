---
title: Formato file di output XML (ssbdiagnose) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- XML output file format [ssbdiagnose]
- ssbdiagnose
ms.assetid: 3ceb991b-6f15-4504-8828-de5adf448bc5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 612b317f7220f502faf1adc82cf9c1dcc8bc20a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720586"
---
# <a name="xml-output-file-format-ssbdiagnose"></a><span data-ttu-id="804d6-102">Formato del file di output XML (ssbdiagnose)</span><span class="sxs-lookup"><span data-stu-id="804d6-102">XML Output File Format (ssbdiagnose)</span></span>
  <span data-ttu-id="804d6-103">L'utilità **ssbdiagnose** restituisce un file di output in formato XML quando viene eseguita con l'opzione **-XML** .</span><span class="sxs-lookup"><span data-stu-id="804d6-103">The **ssbdiagnose** utility delivers its output as an XML file when you run it with the **-XML** switch.</span></span> <span data-ttu-id="804d6-104">Nel file di output XML vengono elencate informazioni di intestazione e gli errori rilevati nella configurazione o nella conversazione di [!INCLUDE[ssSB](../../includes/sssb-md.md)] analizzata.</span><span class="sxs-lookup"><span data-stu-id="804d6-104">The XML output file lists header information and the errors that it found in the [!INCLUDE[ssSB](../../includes/sssb-md.md)] configuration or conversation that was analyzed.</span></span> <span data-ttu-id="804d6-105">È possibile scrivere un'applicazione per analizzare o generare un report relativo agli errori elencati nel file.</span><span class="sxs-lookup"><span data-stu-id="804d6-105">You can write an application to analyze or report on the errors listed in the file.</span></span> <span data-ttu-id="804d6-106">In alternativa, è possibile visualizzare il file XML in un editor XML generico, ad esempio XML Notepad.</span><span class="sxs-lookup"><span data-stu-id="804d6-106">Or, you can view the XML file in a general XML editor, such as XML Notepad.</span></span>  
  
 <span data-ttu-id="804d6-107">Un file di output di **ssbdiangose** contiene un elemento radice DiagnosticInformation con due tipi di figlio:</span><span class="sxs-lookup"><span data-stu-id="804d6-107">An **ssbdiangose** output file contains a DiagnosticInformation root element with two child types:</span></span>  
  
-   <span data-ttu-id="804d6-108">Un elemento Banner con le informazioni di intestazione.</span><span class="sxs-lookup"><span data-stu-id="804d6-108">A Banner element with header information.</span></span>  
  
-   <span data-ttu-id="804d6-109">Un elemento Issue per ogni problema segnalato da **ssbdiagnose**.</span><span class="sxs-lookup"><span data-stu-id="804d6-109">An Issue element for each issue that is reported by **ssbdiagnose**.</span></span>  
  
## <a name="diagnosticinformation-root-element"></a><span data-ttu-id="804d6-110">Elemento radice DiagnosticInformation</span><span class="sxs-lookup"><span data-stu-id="804d6-110">DiagnosticInformation Root Element</span></span>  
  
-   [<span data-ttu-id="804d6-111">Elemento DiagnosticInformation &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="804d6-111">DiagnosticInformation Element &#40;ssbdiagnose&#41;</span></span>](diagnosticinformation-element-ssbdiagnose.md)  
  
## <a name="banner-element"></a><span data-ttu-id="804d6-112">Elemento Banner</span><span class="sxs-lookup"><span data-stu-id="804d6-112">Banner Element</span></span>  
  
-   [<span data-ttu-id="804d6-113">Elemento Banner &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="804d6-113">Banner Element &#40;ssbdiagnose&#41;</span></span>](banner-element-ssbdiagnose.md)  
  
## <a name="issue-element"></a><span data-ttu-id="804d6-114">Elemento Issue</span><span class="sxs-lookup"><span data-stu-id="804d6-114">Issue Element</span></span>  
  
-   [<span data-ttu-id="804d6-115">Elemento Issue &#40;ssbdiagnose&#41;</span><span class="sxs-lookup"><span data-stu-id="804d6-115">Issue Element &#40;ssbdiagnose&#41;</span></span>](issue-element-ssbdiagnose.md)  
  
## <a name="see-also"></a><span data-ttu-id="804d6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="804d6-116">See Also</span></span>  
 [<span data-ttu-id="804d6-117">Utilità ssbdiagnose &#40;Service Broker&#41;</span><span class="sxs-lookup"><span data-stu-id="804d6-117">ssbdiagnose Utility &#40;Service Broker&#41;</span></span>](ssbdiagnose-utility-service-broker.md)  
  
  
