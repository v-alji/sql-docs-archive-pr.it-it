---
title: 'Lezione 2: generare classi dallo schema RDL utilizzando lo strumento XSD | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a81c87f1-7977-4b30-b6ac-b38b3e2b6398
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 2c5db118ad8f94afc72cea44b9a2489f2b4fd7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719091"
---
# <a name="lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool"></a><span data-ttu-id="e35b8-102">Lezione 2: Generare classi dallo schema RDL con lo strumento xsd</span><span class="sxs-lookup"><span data-stu-id="e35b8-102">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>
  <span data-ttu-id="e35b8-103">Dopo aver creato il progetto di [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], è necessario recuperare una copia locale dello schema di definizione del report ed eseguire lo strumento per la definizione di XML Schema (Xsd.exe).</span><span class="sxs-lookup"><span data-stu-id="e35b8-103">After you have created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project, the next step is to retrieve a local copy of the report definition schema and run the XML Schema Definition Tool (Xsd.exe).</span></span>  
  
### <a name="to-generate-the-rdl-classes"></a><span data-ttu-id="e35b8-104">Per generare le classi RDL</span><span class="sxs-lookup"><span data-stu-id="e35b8-104">To generate the RDL classes</span></span>  
  
1.  <span data-ttu-id="e35b8-105">Aprire un'istanza di [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (o Web browser equivalenti) e passare all'URL seguente:</span><span class="sxs-lookup"><span data-stu-id="e35b8-105">Open an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (or equivalent Web browser) and navigate to the following URL:</span></span>  
  
    ```  
    https://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition/ReportDefinition.xsd  
    ```  
  
2.  <span data-ttu-id="e35b8-106">Una volta aperto lo schema RDL nel browser, passare al menu **file** e selezionare **Salva con nome**.</span><span class="sxs-lookup"><span data-stu-id="e35b8-106">Once the RDL schema has been opened in the browser, browse to the **File** menu, and select **Save As**.</span></span>  
  
3.  <span data-ttu-id="e35b8-107">Passare al percorso in cui è stato creato il progetto di [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] e salvare lo schema con il nome ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="e35b8-107">Browse to the location where you created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project and save the schema with the file name ReportDefinition.xsd.</span></span>  
  
4.  <span data-ttu-id="e35b8-108">Dopo aver salvato il file, aprire un'istanza del prompt dei [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] comandi.</span><span class="sxs-lookup"><span data-stu-id="e35b8-108">After the file has been saved, open an instance of the [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] command prompt.</span></span> <span data-ttu-id="e35b8-109">Per aprire un'istanza del prompt dei comandi, fare clic sul menu Start, scegliere **tutti i programmi**, **Microsoft Visual Studio 2010**, scegliere **strumenti di Visual Studio** e fare clic su **prompt dei comandi di Visual Studio (2010)**.</span><span class="sxs-lookup"><span data-stu-id="e35b8-109">To open an instance of the command prompt, click the Start menu, point to **All Programs**, point to **Microsoft Visual Studio 2010**, point to **Visual Studio Tools** and click **Visual Studio Command Prompt (2010)**.</span></span>  
  
5.  <span data-ttu-id="e35b8-110">Modificare il percorso corrente sul percorso in cui è stato salvato il file ReportDefinition.xsd:</span><span class="sxs-lookup"><span data-stu-id="e35b8-110">Change the current path to the location where you saved the ReportDefinition.xsd file:</span></span>  
  
     `CD\<ReportDefinition.xsd Path>`  
  
6.  <span data-ttu-id="e35b8-111">Generare il file ReportDefinition.cs che contiene le classi per lo schema RDL con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e35b8-111">Generate the ReportDefinition.cs file that contains the classes for the RDL schema with the following command:</span></span>  
  
     `xsd /c /n:SampleRDLSchema ReportDefinition.xsd`  
  
     <span data-ttu-id="e35b8-112">Per generare il file ReportDefinition.vb utilizzare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e35b8-112">To generate a ReportDefinition.vb file use this command:</span></span>  
  
     `xsd /c /l:VB /n:SampleRDLSchema ReportDefinition.xsd`  
  
7.  <span data-ttu-id="e35b8-113">Aggiungere il progetto ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="e35b8-113">Add ReportDefinition.xsd your project.</span></span> <span data-ttu-id="e35b8-114">Scegliere **Aggiungi elemento esistente**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="e35b8-114">From the **Project** menu, click **Add Existing Item**.</span></span> <span data-ttu-id="e35b8-115">Individuare il percorso del file ReportDefinition. xsd, selezionare ReportDefinition. xsd, quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="e35b8-115">Browse to the location of the ReportDefinition.xsd file, select ReportDefinition.xsd, and click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e35b8-116">Dopo aver aggiunto il file ReportDefinition. xsd al progetto, si noterà **Esplora soluzioni** che il file ReportDefinition.cs (. vb) non è presente.</span><span class="sxs-lookup"><span data-stu-id="e35b8-116">After you have added the ReportDefinition.xsd file to the project you will notice in **Solution Explorer** that the ReportDefinition.cs (.vb) file is not there.</span></span> <span data-ttu-id="e35b8-117">Per visualizzare il file, fare clic sul pulsante per espandere/comprimere accanto al file ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="e35b8-117">To display the file, click the expand/collapse button next to the ReportDefinition.xsd file.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="e35b8-118">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="e35b8-118">Next Lesson</span></span>  
 <span data-ttu-id="e35b8-119">Nella lezione successiva verrà scritto codice per caricare la definizione di un report da un server di report utilizzando le classi generate dallo schema RDL.</span><span class="sxs-lookup"><span data-stu-id="e35b8-119">In the next lesson, you will write code to load a report definition from a report server using the classes you generated from the RDL schema.</span></span> <span data-ttu-id="e35b8-120">Vedere [lezione 3: caricare una definizione del report dal server di report](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="e35b8-120">See [Lesson 3: Load a Report Definition from the Report Server](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e35b8-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e35b8-121">See Also</span></span>  
 <span data-ttu-id="e35b8-122">[Aggiornamento dei report mediante le classi generate dallo schema RDL &#40;esercitazione su SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="e35b8-122">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="e35b8-123">Report Definition Language &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e35b8-123">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
