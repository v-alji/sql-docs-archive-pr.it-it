---
title: Impostare la lingua per i parametri del report in un URL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- overriding report language settings
- report servers [Reporting Services], language settings
- languages [Reporting Services]
- URL access [Reporting Services], language overrides
- international considerations [Reporting Services]
- global considerations [Reporting Services]
ms.assetid: e1ccf22f-80d6-45bc-aae0-f5f263275092
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8087a181906517bb60d4cd6839eed0681f52a5eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87716060"
---
# <a name="set-the-language-for-report-parameters-in-a-url"></a><span data-ttu-id="642ed-102">Impostare la lingua per i parametri del report in un URL</span><span class="sxs-lookup"><span data-stu-id="642ed-102">Set the Language for Report Parameters in a URL</span></span>
  <span data-ttu-id="642ed-103">Il parametro di accesso con URL *rs:ParameterLanguage* consente di risolvere un problema di interpretazione dei parametri del report con distinzione delle impostazioni cultura, come date, ore, valuta e numeri, in base alla lingua del browser.</span><span class="sxs-lookup"><span data-stu-id="642ed-103">The *rs:ParameterLanguage* URL access parameter alleviates a problem in which culture-sensitive report parameters, such as dates, times, currency, and numbers, are interpreted using the browser language.</span></span> <span data-ttu-id="642ed-104">Con *rs:ParameterLanguage*l'URL viene ora interpretato in modo indipendente dal browser.</span><span class="sxs-lookup"><span data-stu-id="642ed-104">With *rs:ParameterLanguage*, the URL is now interpreted independently of the browser.</span></span> <span data-ttu-id="642ed-105">Se, ad esempio, per il server di report sono definite le impostazioni internazionali per il tedesco, ma un utente accede a un report tramite un URL utilizzando un browser che è impostato su Inglese (Stati Uniti), i valori dei parametri passati a un server di report vengono interpretati in modo errato.</span><span class="sxs-lookup"><span data-stu-id="642ed-105">For example, if the report server is set to a regional setting of German, but a user is accessing a report via a URL using a browser that is set to English-United States, parameter values that are passed to a report server will be misinterpreted.</span></span>  
  
 <span data-ttu-id="642ed-106">Considerare il seguente URL che rimanda a un report:</span><span class="sxs-lookup"><span data-stu-id="642ed-106">Consider the following URL to a report:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008  
```  
  
 <span data-ttu-id="642ed-107">In questo caso il server, in esecuzione in base alle impostazioni cultura "de-de", genera un URL tramite una sottoscrizione di posta elettronica o un collegamento ipertestuale.</span><span class="sxs-lookup"><span data-stu-id="642ed-107">In the above case, the server, running under a culture of "de-de", generates a URL either through an e-mail subscription or a hyperlink.</span></span> <span data-ttu-id="642ed-108">Il collegamento ipertestuale indica che i parametri del report devono essere interpretati con una data di inizio del 4 ottobre 2008 e una data di fine dell'11 ottobre 2008, in base agli standard di data/ora per il tedesco.</span><span class="sxs-lookup"><span data-stu-id="642ed-108">The hyperlink indicates that the report should be parameterized by a start date of October 4, 2008 and an end date of October 11, 2008 according to German date/time standards.</span></span> <span data-ttu-id="642ed-109">Se tuttavia un utente accede all'URL tramite un browser impostato su "en-us", il server interpreta i valori come il 10 aprile 2008 e  10 novembre 2008, in base agli standard di data/ora per l'inglese degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="642ed-109">However, a user that is accessing the URL through a browser set to "en-us" forces the server to interpret the values as April 10, 2008 and November 10, 2008 under United States English date/time standards.</span></span> <span data-ttu-id="642ed-110">Per risolvere il problema, è possibile usare *rs:ParameterLanguage* per eseguire l'override della lingua del browser per l'interpretazione dei parametri:</span><span class="sxs-lookup"><span data-stu-id="642ed-110">To fix the problem, *rs:ParameterLanguage* can be used to override the browser language for parameter interpretation:</span></span>  
  
```  
http://myrshost/Reportserver?/SampleReports/Product+Line+Sales&rs:Command=Render&StartDate=4/10/2008&EndDate=11/10/2008&rs:ParameterLanguage=de-DE  
```  
  
 <span data-ttu-id="642ed-111">Oltre ai valori **true** e **false** , per il parametro di accesso con URL *rc:Parameters*è ora possibile passare il valore **Collapsed**.</span><span class="sxs-lookup"><span data-stu-id="642ed-111">In addition to a value of **true** and **false** for the URL access parameter *rc:Parameters*, you can now pass a value of **Collapsed**.</span></span> <span data-ttu-id="642ed-112">Quando si usa *rc:Parameters*=**Collapsed** in un URL, l'area dei messaggi di richiesta dei parametri del visualizzatore HTML viene compressa e non è più visualizzata, ma l'utente può comunque scegliere di visualizzarla.</span><span class="sxs-lookup"><span data-stu-id="642ed-112">When using *rc:Parameters*=**Collapsed** on a URL, the parameter prompt area of the HTML viewer is collapsed out of sight, but can still be toggled by the user.</span></span> <span data-ttu-id="642ed-113">Il valore **false** consente di rimuovere l'area dei messaggi di richiesta dei parametri dalla barra degli strumenti del visualizzatore HTML, in modo che non sia più disponibile per l'utente finale.</span><span class="sxs-lookup"><span data-stu-id="642ed-113">A value of **false** removes the parameter prompt area from the HTML viewer toolbar and makes it unavailable to the end-user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="642ed-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="642ed-114">See Also</span></span>  
 <span data-ttu-id="642ed-115">[Accesso con URL &#40;SSRS&#41;](url-access-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="642ed-115">[URL Access &#40;SSRS&#41;](url-access-ssrs.md) </span></span>  
 [<span data-ttu-id="642ed-116">Riferimento ai parametri di accesso con URL</span><span class="sxs-lookup"><span data-stu-id="642ed-116">URL Access Parameter Reference</span></span>](url-access-parameter-reference.md)  
  
  
