---
title: 'Lezione 1: creare il progetto di Visual Studio per lo schema RDL | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f420509c-51aa-4170-8c25-64c2954f4bb9
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: a8411e3f0458ccda8c291d5c86a4467bb051a263
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711207"
---
# <a name="lesson-1-create-the-rdl-schema-visual-studio-project"></a><span data-ttu-id="00eb4-102">Lezione 1: Creare il progetto di Visual Studio per lo schema RDL</span><span class="sxs-lookup"><span data-stu-id="00eb4-102">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>
  <span data-ttu-id="00eb4-103">Per questa esercitazione verrà creata una semplice applicazione console.</span><span class="sxs-lookup"><span data-stu-id="00eb4-103">For this tutorial, you will create a simple console application.</span></span> <span data-ttu-id="00eb4-104">Questa esercitazione presuppone che si stia sviluppando in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="00eb4-104">This tutorial assumes you are developing in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="00eb4-105">Quando si accede al servizio Web ReportServer in esecuzione su [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services, è necessario aggiungere "_SQLExpress" al percorso "ReportServer".</span><span class="sxs-lookup"><span data-stu-id="00eb4-105">When accessing the Report Server Web service running on [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services, you must append "_SQLExpress" to the "ReportServer" path.</span></span> <span data-ttu-id="00eb4-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="00eb4-106">For example:</span></span>  
>   
>  `http://myserver/reportserver_sqlexpress/reportservice2010.asmx"`  
  
### <a name="to-create-the-web-service-proxy"></a><span data-ttu-id="00eb4-107">Per creare il proxy del servizio Web</span><span class="sxs-lookup"><span data-stu-id="00eb4-107">To create the web service proxy</span></span>  
  
1.  <span data-ttu-id="00eb4-108">Dal menu **Start** selezionare **tutti i programmi**, quindi Microsoft Visual Studio, quindi **strumenti di Visual Studio**, quindi prompt dei **comandi di Visual Studio 2010**.</span><span class="sxs-lookup"><span data-stu-id="00eb4-108">From the **Start** menu, select **All Programs**, then Microsoft Visual Studio, then **Visual Studio Tools**, and then **Visual Studio 2010 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="00eb4-109">Nella finestra del prompt dei comandi, eseguire il comando seguente se si utilizza C#:</span><span class="sxs-lookup"><span data-stu-id="00eb4-109">In the command prompt window, run the following command if you are using C#:</span></span>  
  
    ```  
    wsdl /language:CS /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="00eb4-110">Se si utilizza Visual Basic, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="00eb4-110">If you are using Visual Basic, then run the following command:</span></span>  
  
    ```  
    wsdl /language:VB /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="00eb4-111">Questo comando genera un file con estensione cs o vb.</span><span class="sxs-lookup"><span data-stu-id="00eb4-111">This command generates a .cs or .vb file.</span></span> <span data-ttu-id="00eb4-112">Questo file verrà aggiunto all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="00eb4-112">You will add this file to your application.</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="00eb4-113">Per creare un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="00eb4-113">To create a console application</span></span>  
  
1.  <span data-ttu-id="00eb4-114">Scegliere **nuovo**dal menu **file** , quindi fare clic su **progetto** per aprire la finestra di dialogo **nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="00eb4-114">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="00eb4-115">Nel riquadro sinistro, in **modelli installati**, fare clic su **Visual Basic** o sul nodo **Visual C#** e selezionare una categoria di tipi di progetto dall'elenco espanso.</span><span class="sxs-lookup"><span data-stu-id="00eb4-115">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="00eb4-116">Scegliere il tipo di progetto **applicazione console** .</span><span class="sxs-lookup"><span data-stu-id="00eb4-116">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="00eb4-117">Nella casella **nome** immettere un nome per il progetto.</span><span class="sxs-lookup"><span data-stu-id="00eb4-117">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="00eb4-118">Digitare il nome `SampleRDLSchema` .</span><span class="sxs-lookup"><span data-stu-id="00eb4-118">Type the name `SampleRDLSchema`.</span></span>  
  
5.  <span data-ttu-id="00eb4-119">Nella casella **percorso** Digitare il percorso in cui si desidera salvare il progetto oppure fare clic su **Sfoglia** per passare alla cartella.</span><span class="sxs-lookup"><span data-stu-id="00eb4-119">In the **Location** box, type the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="00eb4-120">Una visualizzazione compressa del progetto viene visualizzata in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="00eb4-120">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
7.  <span data-ttu-id="00eb4-121">Nel menu **Progetto** fare clic su **Aggiungi elemento esistente**.</span><span class="sxs-lookup"><span data-stu-id="00eb4-121">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
8.  <span data-ttu-id="00eb4-122">Passare al percorso del file con estensione cs o vb generato, quindi selezionare il file e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="00eb4-122">Navigate to the location for the .cs or .vb file you generated, then select the file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="00eb4-123">È inoltre necessario aggiungere un riferimento allo spazio dei nomi <xref:System.Web.Services> per il riferimento Web da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="00eb4-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
9. <span data-ttu-id="00eb4-124">Scegliere Aggiungi riferimento dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="00eb4-124">On the Project menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="00eb4-125">Nella finestra di dialogo **Aggiungi riferimento** , nella scheda **.NET** selezionare **System. Web. Services**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="00eb4-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
     <span data-ttu-id="00eb4-126">Per ulteriori informazioni su come connettersi al servizio Web ReportServer, vedere [compilazione di applicazioni tramite il servizio Web e il .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="00eb4-126">For more information about how to connect to the Report Server Web service, see [Building Applications Using the Web Service and the .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span></span>  
  
10. <span data-ttu-id="00eb4-127">Espandere il nodo del progetto in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="00eb4-127">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="00eb4-128">Al progetto è stato aggiunto un file di codice con il nome predefinito Program.cs (Module1.vb per [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="00eb4-128">You will see a code file with the default name of Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
11. <span data-ttu-id="00eb4-129">Aprire il file Program.cs (Module1.vb per [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) e sostituire il codice con quanto segue:</span><span class="sxs-lookup"><span data-stu-id="00eb4-129">Open the Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) file and replace the code with the following:</span></span>  
  
     <span data-ttu-id="00eb4-130">Il codice seguente fornisce gli stub del metodo da utilizzare per l'implementazione della funzionalità di caricamento, aggiornamento e salvataggio.</span><span class="sxs-lookup"><span data-stu-id="00eb4-130">The following code provides the method stubs we will use to implement the Load, Update and Save functionality.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.IO;  
    using System.Text;  
    using System.Xml;  
    using System.Xml.Serialization;  
    using ReportService2010;  
  
    namespace SampleRDLSchema  
    {  
        class ReportUpdater  
        {  
            ReportingService2010 _reportService;  
  
            static void Main(string[] args)  
            {  
                ReportUpdater reportUpdater = new ReportUpdater();  
                reportUpdater.UpdateReport();  
            }  
  
            private void UpdateReport()  
            {  
                try  
                {  
                    // Set up the Report Service connection  
                    _reportService = new ReportingService2010();  
                    _reportService.Credentials =  
                        System.Net.CredentialCache.DefaultCredentials;  
                    _reportService.Url =  
                       "http://<Server Name>/reportserver/" +  
                                       "reportservice2010.asmx";  
  
                    // Call the methods to update a report definition  
                    LoadReportDefinition();  
                    UpdateReportDefinition();  
                    PublishReportDefinition();  
                }  
                catch (Exception ex)  
                {  
                    System.Console.WriteLine(ex.Message);  
                }  
            }  
  
            private void LoadReportDefinition()  
            {  
                //Lesson 3: Load a report definition from the report   
                //          catalog  
            }  
  
            private void UpdateReportDefinition()  
            {  
                //Lesson 4: Update the report definition using the    
                //          classes generated from the RDL Schema  
            }  
  
            private void PublishReportDefinition()  
            {  
                //Lesson 5: Publish the updated report definition back   
                //          to the report catalog  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.IO  
    Imports System.Text  
    Imports System.Xml  
    Imports System.Xml.Serialization  
    Imports ReportService2010  
  
    Namespace SampleRDLSchema  
  
        Module ReportUpdater  
  
            Private m_reportService As ReportingService2010  
  
            Public Sub Main(ByVal args As String())  
  
                Try  
                    'Set up the Report Service connection  
                    m_reportService = New ReportingService2010  
                    m_reportService.Credentials = _  
                        System.Net.CredentialCache.DefaultCredentials  
                    m_reportService.Url = _  
                        "http:// <Server Name>/reportserver/" & _  
                               "reportservice2010.asmx"  
  
                    'Call the methods to update a report definition  
                    LoadReportDefinition()  
                    UpdateReportDefinition()  
                    PublishReportDefinition()  
                Catch ex As Exception  
                    System.Console.WriteLine(ex.Message)  
                End Try  
  
            End Sub  
  
            Private Sub LoadReportDefinition()  
                'Lesson 3: Load a report definition from the report   
                '          catalog  
            End Sub  
  
            Private Sub UpdateReportDefinition()  
                'Lesson 4: Update the report definition using the   
                '          classes generated from the RDL Schema  
            End Sub  
  
            Private Sub PublishReportDefinition()  
                'Lesson 5: Publish the updated report definition back   
                '          to the report catalog  
            End Sub  
  
        End Module  
  
    End Namespace   
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="00eb4-131">Lezione successiva</span><span class="sxs-lookup"><span data-stu-id="00eb4-131">Next Lesson</span></span>  
 <span data-ttu-id="00eb4-132">Nella lezione successiva verrà utilizzato lo strumento per la definizione di XML Schema (Xsd.exe) per generare classi dallo schema RDL e includerle nel progetto.</span><span class="sxs-lookup"><span data-stu-id="00eb4-132">In the next lesson, you will use the XML Schema Definition Tool (Xsd.exe) to generate classes from the RDL schema and include them in your project.</span></span> <span data-ttu-id="00eb4-133">Vedere [lezione 2: generare classi dallo schema RDL usando lo strumento XSD](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span><span class="sxs-lookup"><span data-stu-id="00eb4-133">See [Lesson 2: Generate Classes from the RDL Schema using the xsd Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00eb4-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00eb4-134">See Also</span></span>  
 <span data-ttu-id="00eb4-135">[Aggiornamento dei report mediante le classi generate dallo schema RDL &#40;esercitazione su SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="00eb4-135">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="00eb4-136">Report Definition Language &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="00eb4-136">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
