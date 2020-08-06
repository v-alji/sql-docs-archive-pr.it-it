---
title: 'Lezione 2: aggiunta di un riferimento Web | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2c2b8b8-6b13-45ca-ab3b-1582447b6807
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 02ca614cb042211ac468246c3003efaa5f2e8fb5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717112"
---
# <a name="lesson-2-adding-a-web-reference"></a><span data-ttu-id="bd1e1-102">Lezione 2: Aggiunta di un riferimento Web</span><span class="sxs-lookup"><span data-stu-id="bd1e1-102">Lesson 2: Adding a Web Reference</span></span>
  <span data-ttu-id="bd1e1-103">L'individuazione di un servizio Web è il processo che consente a un client di individuare un servizio Web e ottenerne la descrizione.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-103">Web service discovery is the process by which a client locates a Web service and obtains its service description.</span></span> <span data-ttu-id="bd1e1-104">Il processo di individuazione di un servizio Web in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] implica l'interrogazione di un sito Web in base a un algoritmo predeterminato.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-104">The process of Web service discovery in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] involves interrogating a Web site following a predetermined algorithm.</span></span> <span data-ttu-id="bd1e1-105">Scopo di questo processo è quello di individuare la descrizione del servizio, ovvero un documento XML scritto nel linguaggio WSDL (Web Services Description Language).</span><span class="sxs-lookup"><span data-stu-id="bd1e1-105">The goal of the process is to locate the service description, which is an XML document that uses the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="bd1e1-106">Nella descrizione del servizio vengono indicati i servizi disponibili e le modalità di interazione con tali servizi.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-106">The service description describes what services are available and how to interact with those services.</span></span> <span data-ttu-id="bd1e1-107">Senza una descrizione del servizio non è possibile interagire con un servizio Web a livello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-107">Without a service description, it is impossible to programmatically interact with a Web service.</span></span>  
  
 <span data-ttu-id="bd1e1-108">L'applicazione deve disporre di un mezzo per comunicare con il servizio Web e per individuarlo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-108">Your application must have a means to communicate with the Web service and to locate it at run time.</span></span> <span data-ttu-id="bd1e1-109">Questo risultato si ottiene tramite l'aggiunta di un riferimento Web al progetto del servizio Web, operazione che consente di generare una classe proxy che si interfaccia con il servizio Web e ne fornisce una rappresentazione locale.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-109">Adding a Web reference to your project for the Web service does this by generating a proxy class that interfaces with the Web service and provides a local representation of the Web service.</span></span> <span data-ttu-id="bd1e1-110">Per ulteriori informazioni, vedere gli argomenti relativi alla generazione di un proxy del servizio Web XML nella documentazione di [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd1e1-110">For more information, see "How to: Generate an XML Web Service Proxy" in your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] documentation.</span></span>  
  
### <a name="to-add-a-web-reference"></a><span data-ttu-id="bd1e1-111">Per aggiungere un riferimento Web</span><span class="sxs-lookup"><span data-stu-id="bd1e1-111">To add a Web reference</span></span>  
  
1.  <span data-ttu-id="bd1e1-112">Scegliere **Aggiungi riferimento al servizio**dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="bd1e1-112">On the **Project** menu, click **Add Service Reference**.</span></span>  
  
2.  <span data-ttu-id="bd1e1-113">Nella finestra di dialogo **Aggiungi riferimento al servizio** fare clic su **Avanzate**.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-113">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
3.  <span data-ttu-id="bd1e1-114">Nella finestra di dialogo **Impostazioni riferimento al servizio** fare clic su **Aggiungi riferimento Web**.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-114">In the **Service Reference Settings** dialog box, click **Add Web Reference**.</span></span>  
  
4.  <span data-ttu-id="bd1e1-115">Nella casella **URL** della finestra di dialogo **Aggiungi riferimento Web** digitare l'URL per ottenere la descrizione del servizio Web ReportServer, ad esempio http://localhost/reportserver/reportservice2010.asmx .</span><span class="sxs-lookup"><span data-stu-id="bd1e1-115">In the **URL** box of the **Add Web Reference** dialog box, type the URL to obtain the service description of the Report Server Web service, such as http://localhost/reportserver/reportservice2010.asmx.</span></span> <span data-ttu-id="bd1e1-116">Fare quindi clic sul pulsante **Vai** per recuperare le informazioni sul servizio Web.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-116">Then click the **Go** button to retrieve information about the Web service.</span></span>  
  
     <span data-ttu-id="bd1e1-117">\- - oppure -</span><span class="sxs-lookup"><span data-stu-id="bd1e1-117">\- or -</span></span>  
  
     <span data-ttu-id="bd1e1-118">Se il servizio Web ReportServer esiste nel computer locale, fare clic sul collegamento **servizi Web nel computer locale** nel riquadro del browser.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-118">If the Report Server Web service exists on the local machine, click the **Web services on the local machine** link in the browser pane.</span></span> <span data-ttu-id="bd1e1-119">quindi fare clic sul collegamento del servizio Web ReportService2010 nell'elenco visualizzato.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-119">Then click the link for the ReportService2010 Web service from the list provided.</span></span>  
  
5.  <span data-ttu-id="bd1e1-120">Nella casella **nome riferimento Web** rinominare il riferimento Web in ReportService2010, ovvero lo spazio dei nomi che verrà utilizzato per questo riferimento Web.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-120">In the **Web reference name** box, rename the Web reference to ReportService2010, which is the namespace you will use for this Web reference.</span></span>  
  
6.  <span data-ttu-id="bd1e1-121">Fare clic su **Aggiungi riferimento** per aggiungere un riferimento Web per il servizio Web di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-121">Click **Add Reference** to add a Web reference for the target Web service.</span></span>  
  
     <span data-ttu-id="bd1e1-122">Tramite [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] verrà scaricata la descrizione del servizio e verrà generata una classe proxy che funge da interfaccia tra l'applicazione e il servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-122">[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] downloads the service description and generates a proxy class to interface between your application and the Report Server Web service.</span></span> <span data-ttu-id="bd1e1-123">È inoltre necessario aggiungere un riferimento allo spazio dei nomi <xref:System.Web.Services> per il riferimento Web da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
7.  <span data-ttu-id="bd1e1-124">Scegliere Aggiungi riferimento dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-124">On the Project menu, click **Add Reference**.</span></span>  
  
8.  <span data-ttu-id="bd1e1-125">Nella finestra di dialogo **Aggiungi riferimento** , nella scheda **.NET** selezionare **System. Web. Services**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd1e1-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
 <span data-ttu-id="bd1e1-126">Per altre informazioni, vedere [Accesso all'API SOAP](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="bd1e1-126">For more information, see [Accessing the SOAP API](../reporting-services/report-server-web-service/accessing-the-soap-api.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1e1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd1e1-127">See Also</span></span>  
 <span data-ttu-id="bd1e1-128">[Servizio Web ReportServer](../reporting-services/report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="bd1e1-128">[Report Server Web Service](../reporting-services/report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="bd1e1-129">[Lezione 3: accesso al servizio Web](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="bd1e1-129">[Lesson 3: Accessing the Web Service](../../2014/tutorials/lesson-3-accessing-the-web-service.md) </span></span>  
 [<span data-ttu-id="bd1e1-130">Accesso al servizio Web ReportServer utilizzando Visual Basic o Visual C&#35; &#40;SSRS tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="bd1e1-130">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
