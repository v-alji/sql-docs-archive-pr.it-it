---
title: Creazione del proxy del servizio Web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, proxies
- proxies [Reporting Services]
- XML Web service [Reporting Services], proxies
- Web service [Reporting Services], proxies
- Web references [Reporting Services]
ms.assetid: b1217843-8d3d-49f3-a0d2-d35b0db5b2df
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0d080b96fa29e906c044561a684d58275af9f61e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713819"
---
# <a name="creating-the-web-service-proxy"></a><span data-ttu-id="85b81-102">Creazione del proxy del servizio Web</span><span class="sxs-lookup"><span data-stu-id="85b81-102">Creating the Web Service Proxy</span></span>
  <span data-ttu-id="85b81-103">Un client e un servizio Web possono comunicare utilizzando messaggi SOAP, che incapsulano i parametri di input e di output in formato XML.</span><span class="sxs-lookup"><span data-stu-id="85b81-103">A client and a Web service can communicate using SOAP messages, which encapsulate the input and output parameters as XML.</span></span> <span data-ttu-id="85b81-104">Una classe proxy esegue il mapping dei parametri agli elementi XML, quindi invia i messaggi SOAP in una rete.</span><span class="sxs-lookup"><span data-stu-id="85b81-104">A proxy class maps parameters to XML elements and then sends the SOAP messages over a network.</span></span> <span data-ttu-id="85b81-105">In questo modo, la classe proxy elimina l'esigenza di comunicare con il servizio Web a livello SOAP e consente di richiamare i metodi del servizio Web in qualsiasi ambiente di sviluppo che supporti i proxy del servizio Web e SOAP.</span><span class="sxs-lookup"><span data-stu-id="85b81-105">In this way, the proxy class frees you from having to communicate with the Web service at the SOAP level and allows you to invoke Web service methods in any development environment that supports SOAP and Web service proxies.</span></span>  
  
 <span data-ttu-id="85b81-106">Esistono due modi per aggiungere una classe proxy al progetto di sviluppo utilizzando [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] : con lo strumento WSDL in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] e aggiungendo un riferimento Web in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="85b81-106">There are two ways to add a proxy class to your development project using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: with the WSDL tool in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], and by adding a Web reference in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="85b81-107">Nelle sezioni seguenti questo argomento viene illustrato in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="85b81-107">The following sections discuss this subject in further detail.</span></span>  
  
## <a name="adding-the-proxy-using-the-wsdl-tool"></a><span data-ttu-id="85b81-108">Aggiunta del proxy utilizzando lo strumento WSDL</span><span class="sxs-lookup"><span data-stu-id="85b81-108">Adding the Proxy Using the WSDL Tool</span></span>  
 <span data-ttu-id="85b81-109">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK include lo strumento WSDL (Web Services Description Language) (Wsdl.exe) che consente di generare un proxy del servizio Web per l'utilizzo nell'ambiente di sviluppo di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85b81-109">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK includes the Web Services Description Language tool (Wsdl.exe), which enables you to generate a Web service proxy for use in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] development environment.</span></span> <span data-ttu-id="85b81-110">Il modo più comune per creare un proxy client in linguaggi che supportano i servizi Web (attualmente C# e [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] ) consiste nell'usare lo strumento WSDL.</span><span class="sxs-lookup"><span data-stu-id="85b81-110">The most common way to create a client proxy in languages that support Web services (currently C# and [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) is to use the WSDL tool.</span></span>  
  
 <span data-ttu-id="85b81-111">**Per aggiungere una classe proxy al progetto usando Wsdl.exe**</span><span class="sxs-lookup"><span data-stu-id="85b81-111">**To add a proxy class to your project using Wsdl.exe**</span></span>  
  
1.  <span data-ttu-id="85b81-112">Dal prompt dei comandi utilizzare Wsdl.exe per creare una classe proxy, specificando almeno l'URL del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="85b81-112">From a command prompt, use Wsdl.exe to create a proxy class, specifying (at a minimum) the URL to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="85b81-113">Nell'istruzione del prompt dei comandi seguente viene ad esempio specificato un URL per l'endpoint di gestione del servizio Web ReportServer:</span><span class="sxs-lookup"><span data-stu-id="85b81-113">For example, the following command prompt statement specifies a URL for the management endpoint of the Report Server Web service:</span></span>  
  
    ```  
    wsdl /language:CS /n:"Microsoft.SqlServer.ReportingServices2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="85b81-114">Lo strumento WSDL accetta diversi argomenti del prompt dei comandi per la generazione di un proxy.</span><span class="sxs-lookup"><span data-stu-id="85b81-114">The WSDL tool accepts a number of command-prompt arguments for generating a proxy.</span></span> <span data-ttu-id="85b81-115">Nell'esempio precedente sono specificati il linguaggio C# e uno spazio dei nomi suggerito da utilizzare nel proxy (per impedire il conflitto tra i nomi in caso di utilizzo di più di un endpoint servizio Web) e viene generato un file C# denominato ReportingService2010.cs.</span><span class="sxs-lookup"><span data-stu-id="85b81-115">The preceding example specifies the language C#, a suggested namespace to use in the proxy (to prevent name collision if using more than one Web service endpoint), and generates a C# file called ReportingService2010.cs.</span></span> <span data-ttu-id="85b81-116">Se nell'esempio fosse stato specificato [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], sarebbe stato generato un file proxy denominato ReportingService2010.vb.</span><span class="sxs-lookup"><span data-stu-id="85b81-116">If the example had specified [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)], the example would have generated a proxy file with the name ReportingService2010.vb.</span></span> <span data-ttu-id="85b81-117">Questo file viene creato nella directory dalla quale si esegue il comando.</span><span class="sxs-lookup"><span data-stu-id="85b81-117">This file is created in the directory from which you run the command.</span></span>  
  
2.  <span data-ttu-id="85b81-118">Compilare la classe proxy in un file di assembly (con estensione dll) e farvi riferimento nel progetto oppure aggiungere la classe come elemento del progetto.</span><span class="sxs-lookup"><span data-stu-id="85b81-118">Compile the proxy class into an assembly file (with the extension .dll) and reference it in your project, or add the class as a project item.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85b81-119">Quando si aggiunge manualmente una classe proxy al progetto, è necessario aggiungere un riferimento a System.Web.Services.dll.</span><span class="sxs-lookup"><span data-stu-id="85b81-119">When you add a proxy class to your project manually, you need to add a reference to System.Web.Services.dll.</span></span> <span data-ttu-id="85b81-120">Se si aggiunge il proxy utilizzando un riferimento Web in Visual Studio .NET, il riferimento viene creato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="85b81-120">If you add the proxy using a Web reference in Visual Studio .NET, the reference is automatically created for you.</span></span> <span data-ttu-id="85b81-121">Per ulteriori informazioni, vedere "Aggiunta del proxy utilizzando un riferimento Web in Visual Studio" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="85b81-121">For more information, see "Adding the Proxy Using a Web Reference in Visual Studio" later in this topic.</span></span>  
  
     <span data-ttu-id="85b81-122">Dopo avere aggiunto la classe proxy come elemento nel progetto, il file associato viene visualizzato in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="85b81-122">After you add the proxy class as an item to your project, the associated file appears in Solution Explorer.</span></span>  
  
3.  <span data-ttu-id="85b81-123">Per chiamare il servizio a livello di programmazione, creare un'istanza della classe proxy.</span><span class="sxs-lookup"><span data-stu-id="85b81-123">To call the service programmatically, create an instance of the proxy class.</span></span>  
  
     <span data-ttu-id="85b81-124">Nell'esempio di codice seguente viene illustrata la sintassi per la creazione di un'istanza della classe proxy <xref:ReportService2010.ReportingService2010> in un progetto.</span><span class="sxs-lookup"><span data-stu-id="85b81-124">The following code example shows the syntax for creating an instance of the <xref:ReportService2010.ReportingService2010> proxy class in a project:</span></span>  
  
```vb  
Dim service As New ReportingService2010()  
```  
  
```csharp  
ReportingService2010 service = new ReportingService2010();  
  
```  
  
 <span data-ttu-id="85b81-125">Per ulteriori informazioni sullo strumento Wsdl.exe, inclusa la sintassi completa, vedere l'argomento relativo allo strumento WSDL nella documentazione di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="85b81-125">For more information about the Wsdl.exe tool, including its full syntax, see "Web Services Description Language Tool" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span> <span data-ttu-id="85b81-126">Per una spiegazione completa relativa ai proxy del servizio Web, vedere l'argomento relativo alla creazione di un proxy del servizio Web XML nella documentazione di [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="85b81-126">For a full explanation of Web service proxies, see "Creating an XML Web Service Proxy" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="adding-the-proxy-using-a-web-reference-in-visual-studio"></a><span data-ttu-id="85b81-127">Aggiunta del proxy utilizzando un riferimento Web in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85b81-127">Adding the Proxy Using a Web Reference in Visual Studio</span></span>  
 <span data-ttu-id="85b81-128">Un riferimento Web consente l'utilizzo di uno o più servizi Web in un progetto.</span><span class="sxs-lookup"><span data-stu-id="85b81-128">A Web reference enables a project to consume one or more Web services.</span></span> [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] <span data-ttu-id="85b81-129">consente agli utenti di aggiungere ai progetti riferimenti al servizio Web tramite alcuni semplici passaggi.</span><span class="sxs-lookup"><span data-stu-id="85b81-129">enables users to add Web service references to projects by following a few simple steps.</span></span>  
  
 <span data-ttu-id="85b81-130">**Per aggiungere un riferimento Web a un progetto**</span><span class="sxs-lookup"><span data-stu-id="85b81-130">**To add a Web reference to a project**</span></span>  
  
1.  <span data-ttu-id="85b81-131">In **Esplora soluzioni** selezionare il progetto in cui verrà usato il servizio Web.</span><span class="sxs-lookup"><span data-stu-id="85b81-131">In **Solution Explorer**, select the project that will consume the Web service.</span></span>  
  
2.  <span data-ttu-id="85b81-132">Nel menu **Progetto** fare clic su **Aggiungi riferimento Web**.</span><span class="sxs-lookup"><span data-stu-id="85b81-132">On the **Project** menu, click **Add Web Reference**.</span></span>  
  
     <span data-ttu-id="85b81-133">Viene visualizzata la finestra di dialogo **Aggiungi riferimento Web**.</span><span class="sxs-lookup"><span data-stu-id="85b81-133">The **Add Web Reference** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="85b81-134">Nel campo **URL** immettere il percorso completo del servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="85b81-134">In the **URL** field, enter the complete path to the Report Server Web service.</span></span>  
  
     <span data-ttu-id="85b81-135">Un URL semplificato per l'endpoint di esecuzione del report del servizio Web ReportServer potrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="85b81-135">A simplified URL for the report execution endpoint of the Report Server Web service might look like this:</span></span>  
  
    ```  
    http://<Server Name>/reportserver/reportexecution2005.asmx  
    ```  
  
     <span data-ttu-id="85b81-136">L'URL contiene il dominio nel quale viene distribuito il servizio Web ReportServer, il nome della cartella contenente il servizio e il nome del file di individuazione per il servizio.</span><span class="sxs-lookup"><span data-stu-id="85b81-136">The URL contains the domain in which the Report Server Web service is deployed, the name of the folder containing the service, and the name of the discovery file for the service.</span></span> <span data-ttu-id="85b81-137">Per una descrizione completa dei diversi elementi dell'URL, vedere [Accesso all'API SOAP](../accessing-the-soap-api.md).</span><span class="sxs-lookup"><span data-stu-id="85b81-137">For a complete description of the different URL elements, see [Accessing the SOAP API](../accessing-the-soap-api.md).</span></span>  
  
     <span data-ttu-id="85b81-138">Una descrizione delle proprietà e dei metodi forniti dal servizio Web viene visualizzata nel riquadro del visualizzatore a sinistra.</span><span class="sxs-lookup"><span data-stu-id="85b81-138">A description of the methods and properties provided by the Web service appears in the Browser pane on the left.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="85b81-139">Per altre informazioni sugli elementi associati al servizio Web ReportServer, vedere [Metodi del servizio Web ReportServer](../methods/report-server-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="85b81-139">For more information about the items associated with the Report Server Web service, see [Report Server Web Service Methods](../methods/report-server-web-service-methods.md).</span></span>  
  
4.  <span data-ttu-id="85b81-140">Verificare che il progetto possa utilizzare il servizio Web ReportServer, nonché di disporre delle autorizzazioni appropriate per l'accesso al server di report.</span><span class="sxs-lookup"><span data-stu-id="85b81-140">Verify that your project can use the Report Server Web service, and that you have appropriate permission to access the report server.</span></span>  
  
5.  <span data-ttu-id="85b81-141">Nel campo **Nome riferimento Web** immettere il nome che verrà usato nel codice per accedere a livello di programmazione al servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="85b81-141">In the **Web reference name** field, enter a name that you will use in your code to access the Report Server Web service programmatically.</span></span>  
  
6.  <span data-ttu-id="85b81-142">Fare clic sul pulsante **Aggiungi riferimento** per creare un riferimento al servizio Web nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="85b81-142">Select the **Add Reference** button to create a reference in your application to the Web service.</span></span>  
  
     <span data-ttu-id="85b81-143">Il nuovo riferimento verrà visualizzato in **Esplora soluzioni** nel nodo Riferimenti Web per il progetto attivo e con il nome specificato nel campo **Nome riferimento Web**.</span><span class="sxs-lookup"><span data-stu-id="85b81-143">The new reference appears in **Solution Explorer** under the Web References node for the active project, named as specified in the **Web reference name** field.</span></span>  
  
7.  <span data-ttu-id="85b81-144">In **Esplora soluzioni** espandere la cartella Riferimenti Web per visualizzare lo spazio dei nomi per le classi del riferimento Web disponibili per gli elementi del progetto.</span><span class="sxs-lookup"><span data-stu-id="85b81-144">In **Solution Explorer**, expand the Web References folder to note the namespace for the Web reference classes that are available to the items in your project.</span></span>  
  
     <span data-ttu-id="85b81-145">Dopo l'aggiunta di un riferimento Web al progetto, i file associati vengono visualizzati in una sottocartella della cartella Riferimenti Web di **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="85b81-145">After adding a Web reference to your project, the associated files are displayed in a folder within the Web References folder of **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="85b81-146">Dopo avere aggiunto il riferimento Web, utilizzare la sintassi seguente per creare un'istanza della classe proxy:</span><span class="sxs-lookup"><span data-stu-id="85b81-146">After you add the Web reference, use the following syntax to create an instance of the proxy class:</span></span>  
  
```vb  
Dim rs As New myNamespace.myReferenceName.ReportExecutionService()  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
myNamespace.myReferenceName.ReportExecutionService rs = new myNamespace.myReferenceName.ReportExecutionService();  
rs.Url = "http://<Server Name>/reportserver/reportexecution2005.asmx?wsdl"  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
  
```  
  
 <span data-ttu-id="85b81-147">È anche possibile aggiungere una direttiva **using** (**Import** in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) al riferimento al servizio Web ReportServer.</span><span class="sxs-lookup"><span data-stu-id="85b81-147">You can also add a **using** (**Import** in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) directive to the Report Server Web service reference.</span></span> <span data-ttu-id="85b81-148">Quando si utilizza questa direttiva, non è necessario specificare il nome completo dei tipi nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="85b81-148">If you use this directive, you do not need to fully qualify the types in the namespace.</span></span> <span data-ttu-id="85b81-149">A tale scopo, aggiungere al file il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="85b81-149">To do this, add the following code to your file:</span></span>  
  
```vb  
Import myNamespace.myReferenceName  
```  
  
```csharp  
using myNamespace.myReferenceName;  
```  
  
## <a name="see-also"></a><span data-ttu-id="85b81-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85b81-150">See Also</span></span>  
 <span data-ttu-id="85b81-151">[Servizio Web ReportServer](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="85b81-151">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 <span data-ttu-id="85b81-152">[Compilazione di applicazioni tramite servizio Web e .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="85b81-152">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="85b81-153">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="85b81-153">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
