---
title: Importazione di report da Microsoft Access (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Access reports [Reporting Services]
- importing reports
ms.assetid: 4f29d5b8-b77d-4714-a84a-05523df55646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 862d8b90f3c91dffda35971677db7fdc231c1b63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635963"
---
# <a name="import-reports-from-microsoft-access-reporting-services"></a><span data-ttu-id="9fd8b-102">Importazione report da Microsoft Access (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="9fd8b-102">Import Reports from Microsoft Access (Reporting Services)</span></span>
  <span data-ttu-id="9fd8b-103">In Progettazione report, è possibile importare report da un [!INCLUDE[msCoName](../includes/msconame-md.md)] database o un progetto di Access.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-103">In Report Designer, you can import reports from a [!INCLUDE[msCoName](../includes/msconame-md.md)] Access database or project.</span></span> <span data-ttu-id="9fd8b-104">A tale scopo è necessario che Access 2002 o versione successiva sia installato nello stesso computer in cui è installato Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-104">Access 2002 or a later version must be installed on the same computer on which Report Designer is installed.</span></span>  
  
 <span data-ttu-id="9fd8b-105">Con la caratteristica di importazione vengono importati tutti i report inclusi nel progetto o nel database.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-105">When you use the import feature, all reports in the database or project file are imported.</span></span> <span data-ttu-id="9fd8b-106">Se il file di Access include molti report, è possibile creare un progetto report separato per l'importazione e quindi aprire i singoli file RDL nel progetto report principale.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-106">If your Access file contains many reports, you may want to create a separate report project into which to import the reports, and then open the individual RDL files in your main report project.</span></span> <span data-ttu-id="9fd8b-107">È possibile modificare i report dopo l'importazione in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-107">You can edit the reports after they are imported into Report Designer.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="9fd8b-108">non supporta tutti gli oggetti report di Access.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-108">does not support all Access report objects.</span></span> <span data-ttu-id="9fd8b-109">Gli elementi non convertiti vengono visualizzati nella finestra **elenco attività** .</span><span class="sxs-lookup"><span data-stu-id="9fd8b-109">Items that are not converted are displayed in the **Task List** window.</span></span> <span data-ttu-id="9fd8b-110">Per ulteriori informazioni, vedere [funzionalità dei report di Access supportati &#40;&#41;SSRS ](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9fd8b-110">For more information, see [Supported Access Report Features &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span></span>  
  
### <a name="to-import-reports-from-microsoft-access"></a><span data-ttu-id="9fd8b-111">Per importare report da Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="9fd8b-111">To import reports from Microsoft Access</span></span>  
  
1.  <span data-ttu-id="9fd8b-112">Aprire o creare un progetto in cui importare i report.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-112">Open or create a project into which to import the reports.</span></span>  
  
2.  <span data-ttu-id="9fd8b-113">Scegliere **Importa report**dal menu **progetto** , quindi fare clic su **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-113">On the **Project** menu, point to **Import Reports**, and then click **Microsoft Access**.</span></span> <span data-ttu-id="9fd8b-114">In alternativa, fare clic con il pulsante destro del mouse sul progetto in Esplora soluzioni, scegliere **Importa report**, quindi fare clic su **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-114">Alternatively, right-click the project in Solution Explorer, point to **Import Reports**, and then click **Microsoft Access**.</span></span>  
  
3.  <span data-ttu-id="9fd8b-115">Nella finestra di dialogo **Apri** selezionare il database di Access (con estensione mdb, accdb) o il progetto (con estensione ADP) che contiene i report, quindi fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-115">In the **Open** dialog box, select the Access database (.mdb, .accdb) or project (.adp) that contains the reports, and then click **Open**.</span></span> <span data-ttu-id="9fd8b-116">Tutti i report contenuti nel file di progetto o di database verranno importati ed elencati nella cartella Report in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-116">All the reports in the database or project file are imported and listed in the Reports folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="9fd8b-117">Controllare la finestra di **elenco attività** per individuare gli errori di compilazione.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-117">Check the **Task List** window for build errors.</span></span> <span data-ttu-id="9fd8b-118">Per visualizzare la finestra di **elenco attività** , aprire il menu **Visualizza** , scegliere **altre finestre**, quindi fare clic su **elenco attività**.</span><span class="sxs-lookup"><span data-stu-id="9fd8b-118">To view the **Task List** window, open the **View** menu, point to **Other Windows**, and then click **Task List**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd8b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fd8b-119">See Also</span></span>  
 [<span data-ttu-id="9fd8b-120">Progettare report con Progettazione report &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9fd8b-120">Design Reports with Report Designer &#40;SSRS&#41;</span></span>](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md)  
  
  
