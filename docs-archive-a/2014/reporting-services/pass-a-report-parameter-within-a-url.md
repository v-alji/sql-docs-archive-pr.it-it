---
title: Passare un parametro del report in un URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- URL access [Reporting Services], passing parameters
- passing parameters [Reporting Services]
ms.assetid: f93a94cc-27b5-435a-aa85-69e6ec6459ad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cf41ed82728d5d7c840276e135937b08f83fb131
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723572"
---
# <a name="pass-a-report-parameter-within-a-url"></a><span data-ttu-id="b4d18-102">Passare un parametro del report in un URL</span><span class="sxs-lookup"><span data-stu-id="b4d18-102">Pass a Report Parameter Within a URL</span></span>
  <span data-ttu-id="b4d18-103">È possibile passare parametri del report a un report includendoli in un URL del report.</span><span class="sxs-lookup"><span data-stu-id="b4d18-103">You can pass report parameters to a report by including them in a report URL.</span></span> <span data-ttu-id="b4d18-104">Questi parametri URL non hanno il prefisso in quanto vengono passati direttamente al motore di elaborazione dei report.</span><span class="sxs-lookup"><span data-stu-id="b4d18-104">These URL parameters are not prefixed because they are passed directly to the report processing engine.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b4d18-105">È importante che nell'URL sia inclusa la sintassi proxy `_vti_bin` per indirizzare la richiesta tramite SharePoint e il proxy HTTP di [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b4d18-105">It is important the URL include the `_vti_bin` proxy syntax to route the request through SharePoint and the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] HTTP proxy.</span></span> <span data-ttu-id="b4d18-106">Tramite il proxy viene aggiunto del contesto alla richiesta HTTP. Questo contesto è necessario per garantire l'esecuzione corretta del report per i server di report in modalità SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4d18-106">The proxy adds some context to the HTTP request, context that is required to ensure proper execution of the report for SharePoint mode report servers.</span></span>  
>   
>  <span data-ttu-id="b4d18-107">Se non si include la sintassi del proxy, è necessario anteporre al parametro il prefisso *RP:*.</span><span class="sxs-lookup"><span data-stu-id="b4d18-107">If you don't include the proxy syntax, then you need to prefix the parameter with *rp:*.</span></span>  
  
 <span data-ttu-id="b4d18-108">Tutti i parametri di query possono disporre di parametri di report corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b4d18-108">All query parameters can have corresponding report parameters.</span></span> <span data-ttu-id="b4d18-109">Passare un parametro di query a un report passando il parametro di report corrispondente.</span><span class="sxs-lookup"><span data-stu-id="b4d18-109">You pass a query parameter to a report by passing the corresponding report parameter.</span></span> <span data-ttu-id="b4d18-110">Per altre informazioni, vedere [Compilare una query in Progettazione query relazionale &#40;Generatore report e SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="b4d18-110">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4d18-111">Nei parametri dei report viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b4d18-111">Report parameters are case-sensitive.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="b4d18-112">Ai parametri del report viene applicata la distinzione tra maiuscole e minuscole e in essi vengono utilizzati i caratteri speciali seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4d18-112">Report parameters are case-sensitive and utilize the following special characters:</span></span>  
> 
>  -   <span data-ttu-id="b4d18-113">Qualsiasi spazio nella stringa dell'URL viene sostituito con i caratteri "% 20", in base agli standard di codifica degli URL.</span><span class="sxs-lookup"><span data-stu-id="b4d18-113">Any space characters in the URL string are replaced with the characters "%20," according to URL encoding standards.</span></span>  
> -   <span data-ttu-id="b4d18-114">Lo spazio nella parte di parametro dell'URL viene sostituito con un carattere più (+).</span><span class="sxs-lookup"><span data-stu-id="b4d18-114">A space character in the parameter portion of the URL is replaced with a plus character (+).</span></span>  
> -   <span data-ttu-id="b4d18-115">Il punto e virgola in una parte qualsiasi della stringa viene sostituito con i caratteri "%3A".</span><span class="sxs-lookup"><span data-stu-id="b4d18-115">A semicolon in any portion of the string is replaced with the characters "%3A."</span></span>  
> -   <span data-ttu-id="b4d18-116">La codifica appropriata dell'URL deve venire eseguita automaticamente dai browser.</span><span class="sxs-lookup"><span data-stu-id="b4d18-116">Browsers should automatically perform the proper URL encoding.</span></span> <span data-ttu-id="b4d18-117">Non è necessario codificare manualmente i caratteri.</span><span class="sxs-lookup"><span data-stu-id="b4d18-117">You do not have to encode any of the characters manually.</span></span>  
  
 <span data-ttu-id="b4d18-118">Per impostare un parametro del report all'interno di un URL, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b4d18-118">To set a report parameter within a URL, use the following syntax:</span></span>  
  
```  
  
parameter=value  
```  
  
 <span data-ttu-id="b4d18-119">Per specificare ad esempio due parametri, "ReportMonth" e "ReportYear", definiti in un report, usare l'URL seguente relativo a un server di report in modalità nativa:</span><span class="sxs-lookup"><span data-stu-id="b4d18-119">For example, to specify two parameters, "ReportMonth" and "ReportYear", defined in a report, use the following URL for a native mode report server:</span></span>  
  
```  
http://myrshost/ReportServer?/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="b4d18-120">Ad esempio, per specificare gli stessi due parametri definiti in un report, utilizzare l'URL seguente per un server di report in modalità integrata SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b4d18-120">For example, to specify the same two parameters defined in a report, use the following URL for a SharePoint integrated mode report server.</span></span> <span data-ttu-id="b4d18-121">Si noti `/_vti_bin`:</span><span class="sxs-lookup"><span data-stu-id="b4d18-121">Note the `/_vti_bin`:</span></span>  
  
```  
http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/AdventureWorks 2008R2/Employee_Sales_Summary_2008R2.rdl&ReportMonth=3&ReportYear=2008  
```  
  
 <span data-ttu-id="b4d18-122">Per passare un valore Null per un parametro, utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b4d18-122">To pass a null value for a parameter, use the following syntax:</span></span>  
  
```  
  
parameter  
:isnull=true  
  
```  
  
 <span data-ttu-id="b4d18-123">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b4d18-123">For example,</span></span>  
  
```  
SalesOrderNumber:isnull=true  
```  
  
 <span data-ttu-id="b4d18-124">Per passare un valore `Boolean`, usare 0 per false e1 per true.</span><span class="sxs-lookup"><span data-stu-id="b4d18-124">To pass a `Boolean` value, use 0 for false and 1 for true.</span></span> <span data-ttu-id="b4d18-125">Per passare un valore `Float`, includere il separatore decimale corrispondente alle impostazioni locali del server.</span><span class="sxs-lookup"><span data-stu-id="b4d18-125">To pass a `Float` value, include the decimal separator of the server locale</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4d18-126">Se il report contiene un parametro del report con un valore predefinito e il valore della proprietà `Prompt` è `false` (ovvero la proprietà Richiesta all'utente non è selezionata in Gestione report), non è possibile passare un valore per tale parametro in un URL.</span><span class="sxs-lookup"><span data-stu-id="b4d18-126">If your report contains a report parameter that has a default value and the value of the `Prompt` property is `false` (that is, the Prompt User property is not selected in Report Manager), then you cannot pass a value for that report parameter within a URL.</span></span> <span data-ttu-id="b4d18-127">In questo modo, gli amministratori possono impedire agli utenti finali di aggiungere o modificare i valori di determinati parametri dei report.</span><span class="sxs-lookup"><span data-stu-id="b4d18-127">This provides administrators an option for preventing end users from adding or modifying the values of certain report parameters.</span></span>  
  
##  <a name="additional-examples"></a><a name="bkmk_examples"></a> <span data-ttu-id="b4d18-128">Esempi aggiuntivi</span><span class="sxs-lookup"><span data-stu-id="b4d18-128">Additional Examples</span></span>  
 <span data-ttu-id="b4d18-129">Nell'esempio di URL seguente sono inclusi spazi e più parametri</span><span class="sxs-lookup"><span data-stu-id="b4d18-129">The following URL example includes spaces and multiple parameters</span></span>  
  
-   <span data-ttu-id="b4d18-130">Nel nome della cartella "SQL Server User Education Team" sono inclusi spazi che vengono sostituiti dal carattere "+".</span><span class="sxs-lookup"><span data-stu-id="b4d18-130">Folder name of "SQL Server User Education Team" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="b4d18-131">Nel nome del report "team project report" sono inclusi spazi che vengono sostituiti dal carattere "+".</span><span class="sxs-lookup"><span data-stu-id="b4d18-131">Report name of "team project report" includes spaces and therefore the "+" replaces each space.</span></span>  
  
-   <span data-ttu-id="b4d18-132">Passaggio di due parametri di "teamgrouping2" con un valore di "xgroup" e "teamgrouping1" con un valore di "ygroup".</span><span class="sxs-lookup"><span data-stu-id="b4d18-132">Passes two parameters of "teamgrouping2" with a value of "xgroup" and "teamgrouping1" with a value of "ygroup".</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup  
```  
  
 <span data-ttu-id="b4d18-133">Nell'esempio di URL seguente è incluso un parametro multivalore "OrderID".</span><span class="sxs-lookup"><span data-stu-id="b4d18-133">The following URL example includes a multi-value parameter "OrderID.</span></span> <span data-ttu-id="b4d18-134">Il formato per il parametro multivalore prevede la ripetizione del nome del parametro per ogni valore.</span><span class="sxs-lookup"><span data-stu-id="b4d18-134">The format for a Multi-Value parameter is to repeat the parameter name for each value.</span></span>  
  
```  
https://myserver/Reportserver?/SQL+Server+User+Education+Team/_ContentTeams/folder123/team+project+report&teamgrouping2=xgroup&teamgrouping1=ygroup&OrderID=747&OrderID=787&OrderID=12  
```  
  
 <span data-ttu-id="b4d18-135">Nell'esempio di URL seguente viene passato un singolo parametro di *SellStartDate* con il valore "7/1/2005", per un server di report in modalità nativa.</span><span class="sxs-lookup"><span data-stu-id="b4d18-135">The following URL example passes a single parameter of *SellStartDate* with a value of "7/1/2005", for a native mode report server.</span></span>  
  
```  
http://myserver/ReportServer/Pages/ReportViewer.aspx?%2fProduct_and_Sales_Report_AdventureWorks&SellStartDate=7/1/2005  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4d18-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4d18-136">See Also</span></span>  
 <span data-ttu-id="b4d18-137">[Accesso con URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b4d18-137">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="b4d18-138">Riferimento ai parametri di accesso con URL</span><span class="sxs-lookup"><span data-stu-id="b4d18-138">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
