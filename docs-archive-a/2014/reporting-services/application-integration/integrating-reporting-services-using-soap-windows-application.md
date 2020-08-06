---
title: Using the SOAP API in a Windows Application (Uso dell'API SOAP in un'applicazione Windows) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendered reports [Reporting Services]
- Windows applications [Reporting Services]
- Windows Forms [Reporting Services]
- SOAP [Reporting Services], Windows applications
ms.assetid: e4804792-20cd-4df2-9257-fb958ff447b4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 115ce02da69a8adb2c7a3de4175e528f281eb2b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623062"
---
# <a name="using-the-soap-api-in-a-windows-application"></a><span data-ttu-id="14941-102">Utilizzo dell'API SOAP in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="14941-102">Using the SOAP API in a Windows Application</span></span>
  <span data-ttu-id="14941-103">È possibile accedere alle funzionalità complete del server di report tramite l'API SOAP di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="14941-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="14941-104">L'API SOAP è un servizio Web e, in quanto tale, è possibile accedervi in modo semplice per fornire caratteristiche di creazione di report aziendali alle applicazioni aziendali personalizzate.</span><span class="sxs-lookup"><span data-stu-id="14941-104">The SOAP API is a Web service and, as such, can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="14941-105">È possibile accedere al servizio Web in un'applicazione Windows semplicemente scrivendo codice che consenta di effettuare chiamate al servizio.</span><span class="sxs-lookup"><span data-stu-id="14941-105">You can access the Web service in a Windows application simply by writing code that makes calls to the service.</span></span> <span data-ttu-id="14941-106">Utilizzando [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , è possibile generare una classe proxy che espone le proprietà e i metodi del servizio Web e consente di utilizzare un'infrastruttura e strumenti familiari per compilare applicazioni aziendali basate sulla [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tecnologia.</span><span class="sxs-lookup"><span data-stu-id="14941-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Web service and enables you to use a familiar infrastructure and tools to build business applications built on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
## <a name="integrating-report-management-functionality-using-windows-forms"></a><span data-ttu-id="14941-107">Integrazione delle funzionalità di Gestione report tramite Windows Form</span><span class="sxs-lookup"><span data-stu-id="14941-107">Integrating Report Management Functionality Using Windows Forms</span></span>  
 <span data-ttu-id="14941-108">A differenza dell'accesso con URL, l'API SOAP espone il set completo di funzioni di gestione disponibili tramite il server di report.</span><span class="sxs-lookup"><span data-stu-id="14941-108">Unlike URL access, the SOAP API exposes the complete set of management functions that are available through the report server.</span></span> <span data-ttu-id="14941-109">Questo significa che tutte le funzionalità amministrative di Gestione report sono disponibili per gli sviluppatori tramite SOAP.</span><span class="sxs-lookup"><span data-stu-id="14941-109">This means that the entire administrative functionality of Report Manager is available to developers through SOAP.</span></span> <span data-ttu-id="14941-110">È pertanto possibile sviluppare uno strumento completo di gestione e amministrazione tramite Windows Form.</span><span class="sxs-lookup"><span data-stu-id="14941-110">As such, you can develop a complete management and administration tool using Windows Forms.</span></span> <span data-ttu-id="14941-111">Nell'applicazione Windows è ad esempio possibile consentire agli utenti di recuperare il contenuto dello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="14941-111">For example, in your Windows application, you might want to enable your users to retrieve the contents of the report server namespace.</span></span> <span data-ttu-id="14941-112">A tale scopo, è possibile utilizzare il metodo <xref:ReportService2010.ReportingService2010.ListChildren%2A> del servizio Web per elencare tutti gli elementi del database del server di report, quindi utilizzare un controllo Listview, Treeview o Combobox per consentire agli utenti di visualizzare tali elementi.</span><span class="sxs-lookup"><span data-stu-id="14941-112">To do this, you could use the Web service <xref:ReportService2010.ReportingService2010.ListChildren%2A> method to list all the items in the report server database and then use a Listview, Treeview, or Combobox control to display those items to your users.</span></span> <span data-ttu-id="14941-113">Il codice del servizio Web seguente potrebbe essere utilizzato per recuperare l'elenco corrente di report disponibili nella cartella My Reports di un utente quando un utente fa clic su un pulsante in un modulo:</span><span class="sxs-lookup"><span data-stu-id="14941-113">The following Web service code might be used to retrieve the current list of available reports in a user's My Reports folder when a user clicks a button on a form:</span></span>  
  
```vb  
' Button click event that retrieves a list of reports from  
' the My Reports folder and displays them in a combo box  
Private Sub listReportsButton_Click(sender As Object, e As System.EventArgs)  
   ' Create a new Web service object and set credentials  
   ' to Windows Authentication  
   Dim rs As New ReportingService2010()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return the list of items in My Reports  
   Dim items As CatalogItem() = rs.ListChildren("/Adventureworks 2008 Sample Reports", False)  
  
   Dim ci As CatalogItem  
   For Each ci In  items  
      ' If the item is a report, add it to   
      ' a combo box  
      If ci.TypeName = "Report" Then  
         catalogComboBox.Items.Add(ci.Name)  
      End If  
   Next ci  
End Sub 'listReportsButton_Click  
```  
  
```csharp  
// Button click event that retrieves a list of reports from  
// the My Reports folder and displays them in a combo box  
private void listReportsButton_Click(object sender, System.EventArgs e)  
{  
   // Create a new Web service object and set credentials  
   // to Windows Authentication  
   ReportingService2010 rs = new ReportingService2010();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return the list of items in My Reports  
   CatalogItem[] items = rs.ListChildren("/Adventureworks 2008 Sample Reports", false);  
  
   foreach (CatalogItem ci in items)  
   {  
      // If the item is a report, add it to   
      // a combo box  
      if (ci.TypeName == "Report")  
         catalogComboBox.Items.Add(ci.Name);  
   }  
}  
```  
  
 <span data-ttu-id="14941-114">È quindi possibile consentire agli utenti di selezionare il report dalla casella combinata e di visualizzare in anteprima il report nel form utilizzando un controllo browser o immagine.</span><span class="sxs-lookup"><span data-stu-id="14941-114">From there, you might enable users to select the report from the Combo box and preview the report on the form either using a Web browser control or an image control.</span></span>  
  
## <a name="enabling-report-viewing-and-navigation-using-windows-forms"></a><span data-ttu-id="14941-115">Abilitazione della visualizzazione e della navigazione dei report tramite Windows Form</span><span class="sxs-lookup"><span data-stu-id="14941-115">Enabling Report Viewing and Navigation Using Windows Forms</span></span>  
 <span data-ttu-id="14941-116">Per integrare i report nelle applicazioni Windows Form, sono disponibili due metodi.</span><span class="sxs-lookup"><span data-stu-id="14941-116">There are two methods available for integrating reports into your Windows Forms applications.</span></span>  
  
 <span data-ttu-id="14941-117">È possibile utilizzare l'API SOAP per eseguire il rendering dei report in qualsiasi formato di rendering supportato utilizzando il metodo <xref:ReportExecution2005.ReportExecutionService.Render%2A>.</span><span class="sxs-lookup"><span data-stu-id="14941-117">You can use the SOAP API to render reports to any of the supported rendering formats using the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method.</span></span> <span data-ttu-id="14941-118">L'abilitazione della visualizzazione e della navigazione dei report tramite SOAP presenta alcuni piccoli svantaggi:</span><span class="sxs-lookup"><span data-stu-id="14941-118">There are slight disadvantages to enabling report viewing and navigation through SOAP:</span></span>  
  
-   <span data-ttu-id="14941-119">Non è possibile utilizzare le funzionalità predefinite della barra degli strumenti dei report disponibili nel Visualizzatore HTML tramite accesso con URL.</span><span class="sxs-lookup"><span data-stu-id="14941-119">You cannot take advantage of the built-in functionality of the report toolbar that is included with the HTML Viewer through URL access.</span></span>  
  
-   <span data-ttu-id="14941-120">Se si esegue il rendering in formato HTML, è necessario eseguire separatamente il rendering di qualsiasi immagine o risorsa come flusso aggiuntivo utilizzando il metodo <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="14941-120">If you render to HTML, you must separately render any images or resources as additional streams using the <xref:ReportExecution2005.ReportExecutionService.RenderStream%2A> method.</span></span>  
  
-   <span data-ttu-id="14941-121">Il rendering di report tramite l'accesso con URL offre prestazioni leggermente migliori rispetto all'utilizzo dell'API SOAP.</span><span class="sxs-lookup"><span data-stu-id="14941-121">There is a slight performance advantage to rendering reports using URL access over using the SOAP API.</span></span>  
  
 <span data-ttu-id="14941-122">È tuttavia possibile utilizzare il metodo <xref:ReportExecution2005.ReportExecutionService.Render%2A> dell'API SOAP per eseguire il rendering dei report e salvarli in diversi formati di output a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="14941-122">However, the <xref:ReportExecution2005.ReportExecutionService.Render%2A> method of the SOAP API can be used to render reports and save them to various output formats programmatically.</span></span> <span data-ttu-id="14941-123">Questo è un vantaggio rispetto all'accesso con URL, che richiede l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="14941-123">This is an advantage over URL access, which requires user interaction.</span></span> <span data-ttu-id="14941-124">Quando si esegue il rendering di un report utilizzando il metodo <xref:ReportExecution2005.ReportExecutionService.Render%2A> dell'API SOAP, è possibile scegliere qualsiasi formato di output supportato.</span><span class="sxs-lookup"><span data-stu-id="14941-124">When you render a report using the SOAP API <xref:ReportExecution2005.ReportExecutionService.Render%2A> method, you can render to any of the supported output formats.</span></span>  
  
 <span data-ttu-id="14941-125">È inoltre possibile utilizzare i controlli ReportViewer distribuibili liberamente inclusi in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="14941-125">You can also use the freely distributable ReportViewer controls that are included with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsOrcas](../../includes/vsorcas-md.md)].</span></span> <span data-ttu-id="14941-126">I controlli ReportViewer consentono di incorporare in modo semplice le funzionalità di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nelle applicazioni personalizzate.</span><span class="sxs-lookup"><span data-stu-id="14941-126">The ReportViewer controls make it easy to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] functionality into custom applications.</span></span> <span data-ttu-id="14941-127">Tali controlli sono destinati agli sviluppatori che desiderano fornire report predefiniti e completi come parte del set di caratteristiche di un'applicazione. Un'applicazione di gestione di un sito Web può ad esempio includere report relativi a un'analisi clickstream nei siti Web aziendali.</span><span class="sxs-lookup"><span data-stu-id="14941-127">The ReportViewer controls are intended for developers who want to provide predesigned, fully authored reports as part of an application feature set (for example, a Web site management application might include reports that show click-stream analysis on company Web sites).</span></span> <span data-ttu-id="14941-128">L'incorporamento dei controlli in un'applicazione costituisce un'alternativa efficace all'inclusione dei componenti server di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nella distribuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="14941-128">Embedding the controls in an application provides a streamlined alternative to including the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] server components in your application deployment.</span></span> <span data-ttu-id="14941-129">I controlli forniscono funzionalità per i report, ma senza il supporto aggiuntivo per la creazione, la pubblicazione o la distribuzione e il recapito di report, disponibile in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14941-129">The controls provide report functionality, but without the additional report authoring, publication, or distribution and delivery support that you find in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="14941-130">Sono disponibili due versioni dei controlli ReportViewer: una versione per le applicazioni rich client Windows e una per le applicazioni [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14941-130">There are two versions of the ReportViewer controls, one for rich Windows client applications and one for [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications.</span></span> <span data-ttu-id="14941-131">I controlli supportano sia la modalità di elaborazione locale che quella remota.</span><span class="sxs-lookup"><span data-stu-id="14941-131">The controls support both local processing and remote processing modes.</span></span> <span data-ttu-id="14941-132">In modalità di elaborazione locale l'applicazione fornisce la definizione e i set di dati del report e avvia l'elaborazione del report.</span><span class="sxs-lookup"><span data-stu-id="14941-132">In local processing mode, your application provides the report definition and datasets and triggers report processing.</span></span> <span data-ttu-id="14941-133">In modalità di elaborazione remota il recupero dei dati e l'elaborazione del report vengono eseguiti nel server di report e il controllo viene utilizzato per visualizzare e navigare il report.</span><span class="sxs-lookup"><span data-stu-id="14941-133">In remote processing mode, data retrieval and report processing happen on the report server and the control is used for display and report navigation.</span></span> <span data-ttu-id="14941-134">Questo modello consente di compilare applicazioni complete adatte per ambienti di qualsiasi dimensione, dal desktop all'azienda.</span><span class="sxs-lookup"><span data-stu-id="14941-134">This model allows you to build rich applications that can be scaled from desktop to the enterprise.</span></span>  
  
 <span data-ttu-id="14941-135">I controlli ReportViewer sono descritti nella Guida online di [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14941-135">ReportViewer controls are documented in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] online Help.</span></span> <span data-ttu-id="14941-136">Per ulteriori informazioni, vedere la documentazione di [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="14941-136">For more information, see the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] product documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14941-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14941-137">See Also</span></span>  
 <span data-ttu-id="14941-138">[Compilazione di applicazioni tramite servizio Web e .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="14941-138">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="14941-139">[Integrazione di Reporting Services in applicazioni](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="14941-139">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 [<span data-ttu-id="14941-140">Uso dell'API SOAP in un'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="14941-140">Using the SOAP API in a Web Application</span></span>](integrating-reporting-services-using-soap-web-application.md)  
  
  
