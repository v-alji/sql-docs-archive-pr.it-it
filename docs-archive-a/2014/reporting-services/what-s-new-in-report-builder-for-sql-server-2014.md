---
title: Novità di Generatore report per SQL Server 2014 |&#39;Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8223c19b-4b0d-4b1d-a042-9a726c18e708
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ce72af225130bc3f081a53008a303c5213db636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629714"
---
# <a name="what39s-new-in-report-builder-for-sql-server-2014"></a><span data-ttu-id="7d4f6-102">Novità di Generatore report per SQL Server 2014&#39;</span><span class="sxs-lookup"><span data-stu-id="7d4f6-102">What&#39;s New in Report Builder for SQL Server 2014</span></span>
  <span data-ttu-id="7d4f6-103">In [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] sono state introdotte numerose funzionalità di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d4f6-103">The [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] introduces a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span>  
  
 <span data-ttu-id="7d4f6-104">Per informazioni sulle funzionalità di questa versione per altri [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] prodotti e tecnologie, vedere Novità [di SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="7d4f6-104">For information about features in this release for other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="7d4f6-105">Per le informazioni e le risorse più recenti relative alle nuove funzionalità di questa versione, vedere [informazioni aggiuntive sulle novità di SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span><span class="sxs-lookup"><span data-stu-id="7d4f6-105">For the most recent information and resources regarding new features in this release, see [Additional information on what is new in SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span></span>  
  
##  <a name="excel-renderer-for-microsoft-excel-2007-2010-and-microsoft-excel-2003"></a><a name="ExcelRenderer"></a><span data-ttu-id="7d4f6-106">Renderer di Excel per Microsoft Excel 2007-2010 e Microsoft Excel 2003</span><span class="sxs-lookup"><span data-stu-id="7d4f6-106">Excel Renderer for Microsoft Excel 2007-2010 and Microsoft Excel 2003</span></span>  
 <span data-ttu-id="7d4f6-107">L'estensione per il rendering di Excel in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], nuova in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], consente di eseguire il rendering di un report come documento di Excel compatibile con [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010 e con [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 grazie a Microsoft Office Compatibility Pack per i formati di file Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Excel rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as an Excel document that is compatible with [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010 as well as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="7d4f6-108">Il formato è Office Open XML mentre l'estensione di file è xlsx.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-108">The format is Office Open XML and the file extension of files is .xlsx.</span></span>  
  
 <span data-ttu-id="7d4f6-109">Con questa estensione per il rendering di Excel vengono rimosse le limitazioni della versione precedente, compatibile con Excel 2003.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-109">This Excel-rendering extension removes limitations of the earlier version, compatible with Excel 2003.</span></span> <span data-ttu-id="7d4f6-110">Di seguito sono elencati i miglioramenti dell'estensione per il rendering:</span><span class="sxs-lookup"><span data-stu-id="7d4f6-110">The following lists the improvement in the rendering extension:</span></span>  
  
-   <span data-ttu-id="7d4f6-111">Il numero massimo di righe per foglio di lavoro è 1.048.576.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-111">Maximum rows per worksheet is 1,048,576.</span></span>  
  
-   <span data-ttu-id="7d4f6-112">Il numero massimo di colonne per foglio di lavoro è 16.384.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-112">Maximum columns per worksheet is 16,384.</span></span>  
  
-   <span data-ttu-id="7d4f6-113">Il numero di colori consentiti in un foglio di lavoro è di circa 16 milioni (colore a 24 bit).</span><span class="sxs-lookup"><span data-stu-id="7d4f6-113">Number of colors allowed in a worksheet is approximately 16 million (24-bit color).</span></span>  
  
-   <span data-ttu-id="7d4f6-114">La compressione ZIP consente una riduzione delle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-114">ZIP compression provides smaller files sizes.</span></span>  
  
 <span data-ttu-id="7d4f6-115">Per altre informazioni, vedere [Esportazione in Microsoft Excel &#40;Generatore report e SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7d4f6-115">For more information, see [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="word-renderer-for-microsoft-word-2007-2010-and-microsoft-word-2003"></a><a name="WordRenderer"></a><span data-ttu-id="7d4f6-116">Renderer di Word per Microsoft Word 2007-2010 e Microsoft Word 2003</span><span class="sxs-lookup"><span data-stu-id="7d4f6-116">Word Renderer for Microsoft Word 2007-2010 and Microsoft Word 2003</span></span>  
 <span data-ttu-id="7d4f6-117">L'estensione per il rendering di Word in [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], nuova in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], consente di eseguire il rendering di un report come documento di Word compatibile con [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010 e con [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 grazie a [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Compatibility Pack per i formati di file Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-117">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Word rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as a Word document that is compatible with [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010 as well as [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="7d4f6-118">Il formato è Office Open XML mentre l'estensione di file è docx.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-118">The format is Office Open XML and the file extension of files is docx.</span></span>  
  
 <span data-ttu-id="7d4f6-119">Oltre a rendere le funzionalità che sono nuove in Word 2007-2010 disponibili per i report esportati, i file \*.docx di report esportati tendono a essere più piccoli.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-119">In addition to making the features that are new in Word 2007-2010 available to exported reports, \*.docx files of exported reports tend to be smaller.</span></span> <span data-ttu-id="7d4f6-120">I report esportati tramite il renderer di Word sono in genere notevolmente più piccoli rispetto agli stessi report esportati utilizzando il renderer di Word 2003.</span><span class="sxs-lookup"><span data-stu-id="7d4f6-120">Reports exported by using the Word renderer are typically significantly smaller than the same reports exported by using the Word 2003 renderer.</span></span>  
  
 <span data-ttu-id="7d4f6-121">Per altre informazioni, vedere [Esportazione in Microsoft Word &#40;Generatore report e SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="7d4f6-121">For more information, see [Exporting to Microsoft Word &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4f6-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d4f6-122">See Also</span></span>  
 [<span data-ttu-id="7d4f6-123">Generatore report in SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="7d4f6-123">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
