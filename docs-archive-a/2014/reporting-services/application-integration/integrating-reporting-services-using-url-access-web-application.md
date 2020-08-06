---
title: Uso dell'accesso con URL in un'applicazione Web | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- links [Reporting Services], URL access
- URL access [Reporting Services], Web applications
- POST requests
- direct addressing [Reporting Services]
- Web applications [Reporting Services]
- hyperlinks [Reporting Services]
ms.assetid: 39e7918c-ad2d-4ca6-b099-2dd4dbdb83dc
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cd31f76658f8160cbb2a576debc335588f77e72c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623057"
---
# <a name="using-url-access-in-a-web-application"></a><span data-ttu-id="76aa6-102">Utilizzo dell'accesso con URL in un'applicazione Web</span><span class="sxs-lookup"><span data-stu-id="76aa6-102">Using URL Access in a Web Application</span></span>
  <span data-ttu-id="76aa6-103">L'accesso con URL in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] è progettato in maniera specifica per consentire l'accesso ai singoli report in una rete.</span><span class="sxs-lookup"><span data-stu-id="76aa6-103">URL access in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is specifically designed to enable access to individual reports over a network.</span></span> <span data-ttu-id="76aa6-104">Questo tipo di accesso è ottimale per l'integrazione delle funzionalità di visualizzazione e navigazione del report in un'applicazione Web personalizzata.</span><span class="sxs-lookup"><span data-stu-id="76aa6-104">This type of access is best for integrating report viewing and navigation into a custom Web application.</span></span> <span data-ttu-id="76aa6-105">Per utilizzare l'accesso con URL nelle applicazioni Web, è possibile:</span><span class="sxs-lookup"><span data-stu-id="76aa6-105">To use URL access in Web applications, you can:</span></span>  
  
-   <span data-ttu-id="76aa6-106">Indirizzare un URL a un server di report specifico da un portale o un sito Web.</span><span class="sxs-lookup"><span data-stu-id="76aa6-106">Address a URL to a specific report server from a Web site or portal.</span></span>  
  
-   <span data-ttu-id="76aa6-107">Utilizzare un metodo POST di un form e passare i parametri della stringa di query a un URL del server di report utilizzando i campi del form.</span><span class="sxs-lookup"><span data-stu-id="76aa6-107">Use a form POST method and pass query string parameters to a report server URL using form fields.</span></span>  
  
## <a name="url-access-through-direct-addressing"></a><span data-ttu-id="76aa6-108">Accesso con URL tramite indirizzamento diretto</span><span class="sxs-lookup"><span data-stu-id="76aa6-108">URL Access Through Direct Addressing</span></span>  
 <span data-ttu-id="76aa6-109">Per accedere a un elemento di un server di report o di un database del server di report utilizzando un URL, è sufficiente fornire l'indirizzo dell'URL da un browser o un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="76aa6-109">To access a report server or report server database item using a URL, simply provide the URL address from within a Web browser or application.</span></span> <span data-ttu-id="76aa6-110">È inoltre possibile fornire parametri dell'URL che possono influire sull'aspetto del report o della risorsa a cui si accede.</span><span class="sxs-lookup"><span data-stu-id="76aa6-110">You can also supply parameters to the URL that can affect the appearance of the report or resource that is being accessed.</span></span> <span data-ttu-id="76aa6-111">Un URL può puntare a un server di report tramite la barra degli indirizzi di un browser oppure può essere l'origine di un oggetto **IFrame** che fa parte di un portale o un'applicazione Web di dimensioni più grandi.</span><span class="sxs-lookup"><span data-stu-id="76aa6-111">A URL can target a report server through the address bar of a Web browser, or a URL can be the source of an **IFrame** that is part of a larger Web application or portal.</span></span> <span data-ttu-id="76aa6-112">È possibile includere collegamenti ipertestuali ai report in diverse pagine Web del portale, nonché impostare come destinazione un frame specifico per il report oppure aprire una nuova finestra del browser nel processo.</span><span class="sxs-lookup"><span data-stu-id="76aa6-112">You can include hyperlinks to reports on various Web pages of your portal, as well as target a specific frame for the report or open a new browser window in the process.</span></span>  
  
 <span data-ttu-id="76aa6-113">Nell'esempio seguente il collegamento ipertestuale punta a un frame denominato "main" che potrebbe essere diverso da quello che include il collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="76aa6-113">In the following example, the hyperlink targets a frame named "main", which might be different from the one that includes the hyperlink.</span></span> <span data-ttu-id="76aa6-114">Il collegamento ipertestuale potrebbe fare parte del portale Web.</span><span class="sxs-lookup"><span data-stu-id="76aa6-114">The hyperlink might be part of Web portal.</span></span>  
  
```  
<a href="http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main" target="main" >  
   Click here for the Territory Sales Drilldown sample report  
</a>  
```  
  
 <span data-ttu-id="76aa6-115">Nell'esempio precedente l'impostazione relativa alle informazioni sul dispositivo, **LinkTarget**, viene passata con un valore "main" nella stringa di query dell'URL.</span><span class="sxs-lookup"><span data-stu-id="76aa6-115">In the previous example, the device information setting **LinkTarget** is passed with a value of "main" in the query string of the URL.</span></span> <span data-ttu-id="76aa6-116">In questo modo, anche qualsiasi collegamento ipertestuale drill-through nel report punta al frame denominato "main".</span><span class="sxs-lookup"><span data-stu-id="76aa6-116">This ensures that any drillthrough hyperlinks in the report also target the frame named "main".</span></span>  
  
 <span data-ttu-id="76aa6-117">Per altre informazioni sulle impostazioni relative alle informazioni sul dispositivo, vedere [Passaggio delle impostazioni relative alle informazioni sul dispositivo alle estensioni per il rendering](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="76aa6-117">For more information about device information settings, see [Passing Device Information Settings to Rendering Extensions](../report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md).</span></span>  
  
 <span data-ttu-id="76aa6-118">Si noti che in numerosi server e browser il numero di caratteri consentito in un URL è limitato.</span><span class="sxs-lookup"><span data-stu-id="76aa6-118">Note that many servers and browsers limit the number of characters allowed in a URL.</span></span> <span data-ttu-id="76aa6-119">In alcuni casi, è previsto un limite di 256 caratteri.</span><span class="sxs-lookup"><span data-stu-id="76aa6-119">In some cases, a 256-character limit is imposed.</span></span> <span data-ttu-id="76aa6-120">Per aggirare questa limitazione, è possibile utilizzare richieste POST con invio del form.</span><span class="sxs-lookup"><span data-stu-id="76aa6-120">To get around this limitation, you can use POST requests using form submission.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76aa6-121">In Internet Explorer la lunghezza massima per gli URL è di 2.083 caratteri.</span><span class="sxs-lookup"><span data-stu-id="76aa6-121">Internet Explorer has a maximum URL length of 2,083 characters.</span></span> <span data-ttu-id="76aa6-122">Questo limite si applica agli URL delle richieste sia POST che GET.</span><span class="sxs-lookup"><span data-stu-id="76aa6-122">This limit applies to both POST and GET request URLs.</span></span> <span data-ttu-id="76aa6-123">Per POST, tuttavia, non vi è un limite imposto dalla dimensione dell'URL per l'invio di coppie nome/valore come parte di un form, in quanto il trasferimento avviene nell'intestazione e non nell'URL.</span><span class="sxs-lookup"><span data-stu-id="76aa6-123">POST, however, is not limited by the size of the URL for submitting name/value pairs as part of a form, because they are transferred in the header and not the URL.</span></span>  
  
## <a name="url-access-through-a-form-post-method"></a><span data-ttu-id="76aa6-124">Accesso con URL tramite un metodo POST del form</span><span class="sxs-lookup"><span data-stu-id="76aa6-124">URL Access Through a Form POST Method</span></span>  
 <span data-ttu-id="76aa6-125">Quando un utente richiede dati da un server di report utilizzando l'accesso con URL, la richiesta HTTP utilizza il metodo GET.</span><span class="sxs-lookup"><span data-stu-id="76aa6-125">When a user requests data from a report server using URL access, the HTTP request uses the GET method.</span></span> <span data-ttu-id="76aa6-126">Si tratta di un'operazione equivalente all'invio di un form con METHOD = "GET".</span><span class="sxs-lookup"><span data-stu-id="76aa6-126">This is equivalent to a form submission where METHOD="GET".</span></span> <span data-ttu-id="76aa6-127">Per le richieste di URL o l'invio di form con METHOD = "GET" il limite è definito dal numero massimo di caratteri che possono essere elaborati da un server o da un browser.</span><span class="sxs-lookup"><span data-stu-id="76aa6-127">URL requests or form submissions that use METHOD="GET" are limited by the maximum number of characters that a server or Web browser can process.</span></span>  
  
 <span data-ttu-id="76aa6-128">Con le richieste POST (METHOD = "POST" e campi di input), le coppie nome/valore vengono trasferite nell'intestazione e non nell'URL.</span><span class="sxs-lookup"><span data-stu-id="76aa6-128">With POST requests (METHOD="POST" and input fields), the name/value pairs are transferred in the header and not the URL.</span></span> <span data-ttu-id="76aa6-129">Le coppie nome/valore della stringa di query non fanno pertanto parte dell'URL ed è quindi possibile fornire elenchi di parametri molto più lunghi e complessi.</span><span class="sxs-lookup"><span data-stu-id="76aa6-129">Therefore, the name/value pairs of the query string are not part of the URL, thus enabling you to provide much longer and more complex parameter lists.</span></span>  
  
 <span data-ttu-id="76aa6-130">Se si utilizza l'accesso diretto, un utente può vedere l'URL per il server di report e potrebbe modificare la stringa di query o annotare la richiesta URL specifica e i parametri del server di report per utilizzarli successivamente.</span><span class="sxs-lookup"><span data-stu-id="76aa6-130">Using direct access, a user can see the URL for the report server, and may be able to modify the  query string or note the particular URL request and report server parameters for later use.</span></span>  
  
 <span data-ttu-id="76aa6-131">L'esempio HTML seguente illustra l'utilizzo di un form che consente di puntare a un server di report con un URL specifico e di passare i parametri della stringa di query come parte dei campi di input del form.</span><span class="sxs-lookup"><span data-stu-id="76aa6-131">The following sample HTML demonstrates the use of a form that you can use to target a report server with a specific URL and pass query string parameters as part of the form's input fields.</span></span>  
  
```  
<FORM id="frmRender" action="http://server/reportserver?/SampleReports/  
   Territory Sales Drilldown" method="post" target="_self">  
   <INPUT type="hidden" name="rs:Command" value="Render">   
   <INPUT type="hidden" name="rc:LinkTarget" value="main">  
   <INPUT type="hidden" name="rs:Format" value="HTML4.0">  
   <INPUT type="submit" value="Button">  
</FORM>  
```  
  
 <span data-ttu-id="76aa6-132">Nell'esempio precedente se un utente fa clic sul pulsante sul form, il server di report restituisce un report visualizzabile in formato HTML indirizzato al frame corrente.</span><span class="sxs-lookup"><span data-stu-id="76aa6-132">In the previous example, if a user clicks the button on the form, the report server returns an HTML-rendered report targeted at the current frame.</span></span> <span data-ttu-id="76aa6-133">Una stringa di accesso con URL paragonabile potrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="76aa6-133">A comparable URL access string might look like the following:</span></span>  
  
```  
http://server/reportserver?/SampleReports/Territory Sales   
Drilldown&rs:Command=Render&rc:LinkTarget=main&rs:Format=HTML4.0  
```  
  
## <a name="see-also"></a><span data-ttu-id="76aa6-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76aa6-134">See Also</span></span>  
 <span data-ttu-id="76aa6-135">[Integrazione di Reporting Services in applicazioni](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="76aa6-135">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="76aa6-136">[Integrazione di Reporting Services tramite l'accesso con URL](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="76aa6-136">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="76aa6-137">[Utilizzo dell'accesso con URL in un'applicazione Windows](integrating-reporting-services-using-url-access-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="76aa6-137">[Using URL Access in a Windows Application](integrating-reporting-services-using-url-access-windows-application.md) </span></span>  
 [<span data-ttu-id="76aa6-138">Accesso con URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="76aa6-138">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
