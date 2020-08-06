---
title: Using the SOAP API in a Web Application (Uso dell'API SOAP in un'applicazione Web) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], Web applications
- impersonation [Reporting Services]
- user impersonation [Reporting Services]
- report servers [Reporting Services], SOAP
- Web applications [Reporting Services]
ms.assetid: e8ca4455-0dc3-4741-8872-3636114938ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e228f01915df633f50b23bf93e892446863c28ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712828"
---
# <a name="using-the-soap-api-in-a-web-application"></a><span data-ttu-id="f3c54-102">Utilizzo dell'API SOAP in un'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="f3c54-102">Using the SOAP API in a Web Application</span></span>
  <span data-ttu-id="f3c54-103">È possibile accedere alle funzionalità complete del server di report tramite l'API SOAP di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="f3c54-103">You can access the full functionality of the report server through the Reporting Services SOAP API.</span></span> <span data-ttu-id="f3c54-104">L'API SOAP è un servizio Web e, in quanto tale, è possibile accedervi in modo semplice per fornire caratteristiche di creazione di report aziendali alle applicazioni aziendali personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f3c54-104">Because it's a Web service, the SOAP API can be easily accessed to provide enterprise reporting features to your custom business applications.</span></span> <span data-ttu-id="f3c54-105">È possibile accedere al servizio Web ReportServer da un'applicazione Web nello stesso modo in cui si accede all'API SOAP da un'applicazione [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f3c54-105">You access the Report Server Web service from a Web application in much the same way that you access the SOAP API from a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="f3c54-106">Utilizzando [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , è possibile generare una classe proxy che espone le proprietà e i metodi del servizio Web ReportServer e consente di utilizzare un'infrastruttura e strumenti familiari per compilare applicazioni aziendali sulla [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] tecnologia.</span><span class="sxs-lookup"><span data-stu-id="f3c54-106">Using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can generate a proxy class that exposes the properties and methods of the Report Server Web service and enables you to use a familiar infrastructure and tools to build business applications on [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] technology.</span></span>  
  
 <span data-ttu-id="f3c54-107">È possibile accedere alla funzionalità di gestione dei report di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] con la stessa facilità da un'applicazione Web o da un'applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="f3c54-107">[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report management functionality is just as easily accessed from a Web application as from a Windows application.</span></span> <span data-ttu-id="f3c54-108">Da un'applicazione Web, è possibile aggiungere e rimuovere gli elementi al e dal database del server di report, impostare la sicurezza degli elementi, modificare gli elementi del database del server di report, gestire le pianificazione e il recapito e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="f3c54-108">From a Web application, you can add and remove items from the report server database, set item security, modify report server database items, manage scheduling and delivery, and more.</span></span>  
  
## <a name="enabling-impersonation"></a><span data-ttu-id="f3c54-109">Abilitazione della rappresentazione</span><span class="sxs-lookup"><span data-stu-id="f3c54-109">Enabling Impersonation</span></span>  
 <span data-ttu-id="f3c54-110">Il primo passaggio per la configurazione dell'applicazione Web consiste nell'attivare la rappresentazione dal client del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="f3c54-110">The first step in configuring your Web application is to enable impersonation from the Web service client.</span></span> <span data-ttu-id="f3c54-111">Con la rappresentazione, le applicazioni [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] possono venire eseguite con l'identità del client per il quale operano.</span><span class="sxs-lookup"><span data-stu-id="f3c54-111">With impersonation, [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] applications can execute with the identity of the client on whose behalf they are operating.</span></span> [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] <span data-ttu-id="f3c54-112">si basa su [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) per autenticare l'utente e passare un token autenticato all'applicazione [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] o, nel caso in cui non sia possibile autenticare l'utente, passare un token non autenticato.</span><span class="sxs-lookup"><span data-stu-id="f3c54-112">relies on [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) to authenticate the user and either pass an authenticated token to the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application or, if unable to authenticate the user, pass an unauthenticated token.</span></span> <span data-ttu-id="f3c54-113">In entrambi i casi, l'applicazione [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] rappresenta il token ricevuto, se la rappresentazione è abilitata.</span><span class="sxs-lookup"><span data-stu-id="f3c54-113">In either case, the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] application impersonates whichever token is received if impersonation is enabled.</span></span> <span data-ttu-id="f3c54-114">È possibile abilitare la rappresentazione nel client modificando il file Web.config dell'applicazione client come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f3c54-114">You can enable impersonation on the client, by modifying the Web.config file of the client application as follows:</span></span>  
  
```  
<!-- Web.config file. -->  
<identity impersonate="true"/>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f3c54-115">Per impostazione predefinita, la rappresentazione è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="f3c54-115">Impersonation is disabled by default.</span></span>  
  
 <span data-ttu-id="f3c54-116">Per ulteriori informazioni sulla [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] rappresentazione, vedere la documentazione di [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="f3c54-116">For more information about [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] impersonation, see the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="managing-the-report-server-using-soap-api"></a><span data-ttu-id="f3c54-117">Gestione del server di report tramite l'API SOAP</span><span class="sxs-lookup"><span data-stu-id="f3c54-117">Managing the Report Server using SOAP API</span></span>  
 <span data-ttu-id="f3c54-118">È inoltre possibile utilizzare l'applicazione Web per gestire un server di report e i relativi contenuti.</span><span class="sxs-lookup"><span data-stu-id="f3c54-118">You can also use your Web application to manage a report server and its contents.</span></span> <span data-ttu-id="f3c54-119">Gestione report, disponibile con [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], è un esempio di applicazione Web compilata completamente utilizzando [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] e l'API SOAP di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="f3c54-119">Report Manager, included with [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], is an example of a Web application that is completely built using [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] and the Reporting Services SOAP API.</span></span> <span data-ttu-id="f3c54-120">È possibile aggiungere le funzionalità di Gestione report alle applicazioni Web personalizzate.</span><span class="sxs-lookup"><span data-stu-id="f3c54-120">You can add the report management functionality of Report Manager to your custom Web applications.</span></span> <span data-ttu-id="f3c54-121">È ad esempio possibile che si desideri restituire un elenco di report disponibili nel database del server di report e visualizzarli in un [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` controllo per consentire agli utenti di scegliere tra loro.</span><span class="sxs-lookup"><span data-stu-id="f3c54-121">For example, you might want to return a list of available reports in the report server database and display them in a [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] `Listbox` control for your users to choose from.</span></span> <span data-ttu-id="f3c54-122">Nel codice seguente viene eseguita la connessione al database del server di report e viene restituito un elenco di elementi disponibili nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="f3c54-122">The following code connects to the report server database and returns a list of items in the report server database.</span></span> <span data-ttu-id="f3c54-123">I report disponibili vengono aggiunti quindi a un controllo ListBox, in cui viene visualizzato il percorso di ogni report.</span><span class="sxs-lookup"><span data-stu-id="f3c54-123">The available reports are then added to a Listbox control, which displays the path of each report.</span></span>  
  
```vb  
Private Sub Page_Load(sender As Object, e As System.EventArgs)  
   ' Create a Web service proxy object and set credentials  
   Dim rs As New ReportingService2005()  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
   ' Return a list of catalog items in the report server database  
   Dim items As CatalogItem() = rs.ListChildren("/", True)  
  
   ' For each report, display the path of the report in a Listbox  
   Dim ci As CatalogItem  
   For Each ci In  items  
      If ci.Type = ItemTypeEnum.Report Then  
         catalogListBox.Items.Add(ci.Path)  
      End If  
   Next ci  
End Sub ' Page_Load   
```  
  
```csharp  
private void Page_Load(object sender, System.EventArgs e)  
{  
   // Create a Web service proxy object and set credentials  
   ReportingService2005 rs = new ReportingService2005();  
   rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
  
   // Return a list of catalog items in the report server database  
   CatalogItem[] items = rs.ListChildren("/", true);  
  
   // For each report, display the path of the report in a Listbox  
   foreach(CatalogItem ci in items)  
   {  
      if (ci.Type == ItemTypeEnum.Report)  
         catalogListBox.Items.Add(ci.Path);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f3c54-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3c54-124">See Also</span></span>  
 <span data-ttu-id="f3c54-125">[Compilazione di applicazioni tramite servizio Web e .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="f3c54-125">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="f3c54-126">[Integrazione di Reporting Services in applicazioni](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="f3c54-126">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="f3c54-127">[Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="f3c54-127">[Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md) </span></span>  
 [<span data-ttu-id="f3c54-128">Uso dell'API SOAP in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="f3c54-128">Using the SOAP API in a Windows Application</span></span>](integrating-reporting-services-using-soap-windows-application.md)  
  
  
