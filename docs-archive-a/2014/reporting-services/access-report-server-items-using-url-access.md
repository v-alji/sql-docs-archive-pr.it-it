---
title: Accedere agli elementi del server di report usando l'accesso con URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- referencing URL items for report server access
- URL access [Reporting Services], report servers
ms.assetid: a58b4ca6-129d-45e9-95c7-e9169fe5bba4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6693419490c1b3770ccb41b2645cbdba8996630a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630373"
---
# <a name="access-report-server-items-using-url-access"></a><span data-ttu-id="3a99d-102">Accesso agli elementi del server di report utilizzando l'accesso tramite URL</span><span class="sxs-lookup"><span data-stu-id="3a99d-102">Access Report Server Items Using URL Access</span></span>
  <span data-ttu-id="3a99d-103">Questo argomento descrive come accedere a tipi diversi di elementi del catalogo in un database del server di report o in un sito di SharePoint usando *rs:Command*=*Value*.</span><span class="sxs-lookup"><span data-stu-id="3a99d-103">This topic describes how to access catalog items of different types in a report server data base or in a SharePoint site using *rs:Command*=*Value*.</span></span>  
  
 <span data-ttu-id="3a99d-104">In realtà non è necessario aggiungere questa stringa del parametro.</span><span class="sxs-lookup"><span data-stu-id="3a99d-104">It is not necessary to add this parameter string.</span></span> <span data-ttu-id="3a99d-105">Se la si omette, il tipo di elemento viene valutato dal server di report e il valore del parametro appropriato viene selezionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3a99d-105">If you omit it, the report server evaluates the item type and selects the appropriate parameter value automatically.</span></span> <span data-ttu-id="3a99d-106">Tuttavia, l'uso della stringa *rs:Command*=*Valore* nell'URL migliora le prestazioni del server di report.</span><span class="sxs-lookup"><span data-stu-id="3a99d-106">However, using the *rs:Command*=*Value* string in the URL improves the performance of the report server.</span></span>  
  
 <span data-ttu-id="3a99d-107">Si noti la sintassi del proxy `_vti_bin` negli esempi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="3a99d-107">Note the `_vti_bin` proxy syntax in the examples below.</span></span> <span data-ttu-id="3a99d-108">Per altre informazioni su come usare la sintassi del proxy, vedere [Riferimento ai parametri di accesso con URL](url-access-parameter-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3a99d-108">For more information about using the proxy syntax, see [URL Access Parameter Reference](url-access-parameter-reference.md).</span></span>  
  
## <a name="access-a-report"></a><span data-ttu-id="3a99d-109">Accedere a report</span><span class="sxs-lookup"><span data-stu-id="3a99d-109">Access a Report</span></span>  
 <span data-ttu-id="3a99d-110">Per visualizzare un report nel browser, usare il parametro *RS: Command* = *Render* .</span><span class="sxs-lookup"><span data-stu-id="3a99d-110">To view a report in the browser, use the *rs:Command*=*Render* parameter.</span></span> <span data-ttu-id="3a99d-111">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3a99d-111">For example:</span></span>  
  
 <span data-ttu-id="3a99d-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="3a99d-112">`Native` `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
 <span data-ttu-id="3a99d-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span><span class="sxs-lookup"><span data-stu-id="3a99d-113">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="3a99d-114">È importante che nell'URL sia inclusa la sintassi proxy `_vti_bin` per indirizzare la richiesta tramite SharePoint e il proxy HTTP di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a99d-114">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="3a99d-115">Tramite il proxy viene aggiunto del contesto alla richiesta HTTP. Questo contesto è necessario per garantire l'esecuzione corretta del report per i server di report in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3a99d-115">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
  
## <a name="access-a-resource"></a><span data-ttu-id="3a99d-116">Accedere a una risorsa</span><span class="sxs-lookup"><span data-stu-id="3a99d-116">Access a Resource</span></span>  
 <span data-ttu-id="3a99d-117">Per accedere a una risorsa, usare il parametro *RS: Command* = *GetResourceContents* . Se la risorsa è compatibile con il browser, ad esempio un'immagine, viene aperta nel browser.</span><span class="sxs-lookup"><span data-stu-id="3a99d-117">To access a resource, use the *rs:Command*=*GetResourceContents* parameter.If the resource is compatible with the browser, such as an image, it is opened in the browser.</span></span> <span data-ttu-id="3a99d-118">In caso contrario, verrà chiesto di aprire oppure salvare il file o la risorsa su disco.</span><span class="sxs-lookup"><span data-stu-id="3a99d-118">Otherwise, you are prompted to open or save the file or resource to disk.</span></span>  
  
 <span data-ttu-id="3a99d-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="3a99d-119">`Native` `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`</span></span>  
  
 <span data-ttu-id="3a99d-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span><span class="sxs-lookup"><span data-stu-id="3a99d-120">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`</span></span>  
  
## <a name="access-a-data-source"></a><span data-ttu-id="3a99d-121">Accedere a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="3a99d-121">Access a Data Source</span></span>  
 <span data-ttu-id="3a99d-122">Per accedere a un'origine dati, usare il parametro *RS: Command* = *GetDataSourceContents* .</span><span class="sxs-lookup"><span data-stu-id="3a99d-122">To access a data source, use the *rs:Command*=*GetDataSourceContents* parameter.</span></span> <span data-ttu-id="3a99d-123">Se si browser supporta l'XML, l'origine dati viene visualizzata se la richiesta avviene da parte di un utente autenticato con autorizzazione `Read Contents` per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3a99d-123">If your browser supports XML, the data source definition is displayed if you are an authenticated user with `Read Contents` permission on the data source.</span></span> <span data-ttu-id="3a99d-124">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3a99d-124">For example:</span></span>  
  
 <span data-ttu-id="3a99d-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="3a99d-125">`Native` `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="3a99d-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span><span class="sxs-lookup"><span data-stu-id="3a99d-126">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`</span></span>  
  
 <span data-ttu-id="3a99d-127">La struttura XML potrebbe essere simile a quella illustrata nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="3a99d-127">The XML structure might look similar to the following example:</span></span>  
  
```  
<DataSourceDefinition>  
   <Extension>SQL</Extension>  
   <ConnectString>Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=AdventureWorks2012;Data Source=MYSERVER1;</ConnectString>  
   <CredentialRetrieval>Integrated</CredentialRetrieval>  
   <WindowsCredentials>False</WindowsCredentials>  
   <ImpersonateUser>False</ImpersonateUser>  
   <Prompt />  
   <Enabled>True</Enabled>  
</DataSourceDefinition>  
```  
  
 <span data-ttu-id="3a99d-128">La stringa di connessione viene restituita in base all'impostazione **SecureConnectionLevel** nel server di report.</span><span class="sxs-lookup"><span data-stu-id="3a99d-128">The connection string is returned based on the **SecureConnectionLevel** setting of the report server.</span></span> <span data-ttu-id="3a99d-129">Per altre informazioni sull'impostazione **SecureConnectionLevel** , vedere [Uso di metodi del servizio Web protetti](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span><span class="sxs-lookup"><span data-stu-id="3a99d-129">For more information about the **SecureConnectionLevel** setting, see [Using Secure Web Service Methods](report-server-web-service/net-framework/using-secure-web-service-methods.md).</span></span>  
  
## <a name="access-the-contents-of-a-folder"></a><span data-ttu-id="3a99d-130">Accedere ai contenuti di una cartella</span><span class="sxs-lookup"><span data-stu-id="3a99d-130">Access the Contents of a Folder</span></span>  
 <span data-ttu-id="3a99d-131">Per accedere al contenuto di una cartella, usare il parametro *RS: Command* = *GetChildren* .</span><span class="sxs-lookup"><span data-stu-id="3a99d-131">To access the contents of a folder, use the *rs:Command*=*GetChildren* parameter.</span></span> <span data-ttu-id="3a99d-132">Viene restituita una pagina generica di navigazione della cartella che contiene collegamenti alle sottocartelle, alle origini dati, alle risorse e ai report inclusi nella cartella richiesta.</span><span class="sxs-lookup"><span data-stu-id="3a99d-132">A generic folder-navigation page is returned that contains links to the subfolders, reports, data sources, and resources in the requested folder.</span></span> <span data-ttu-id="3a99d-133">Esempio:</span><span class="sxs-lookup"><span data-stu-id="3a99d-133">For example:</span></span>  
  
 <span data-ttu-id="3a99d-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="3a99d-134">`Native` `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="3a99d-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span><span class="sxs-lookup"><span data-stu-id="3a99d-135">`SharePoint` `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`</span></span>  
  
 <span data-ttu-id="3a99d-136">L'interfaccia utente visualizzata è simile alla modalità di esplorazione delle directory utilizzata da [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="3a99d-136">The user interface you see is similar to the directory browsing mode used by [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Information Server (IIS).</span></span> <span data-ttu-id="3a99d-137">Sotto l'elenco della cartella viene visualizzato anche il numero di versione, incluso il numero di build, del server di report.</span><span class="sxs-lookup"><span data-stu-id="3a99d-137">The version number, including the build number, of the report server is also displayed below the folder listing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a99d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a99d-138">See Also</span></span>  
 <span data-ttu-id="3a99d-139">[Accesso con URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="3a99d-139">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="3a99d-140">Riferimento ai parametri di accesso con URL</span><span class="sxs-lookup"><span data-stu-id="3a99d-140">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
