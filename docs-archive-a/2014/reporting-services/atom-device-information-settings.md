---
title: Impostazioni relative alle informazioni sul dispositivo ATOM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdbac1500063accf868d4b538b82ba9f3b5aebb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628523"
---
# <a name="atom-device-information-settings"></a><span data-ttu-id="81b40-102">Impostazioni relative alle informazioni sul dispositivo ATOM</span><span class="sxs-lookup"><span data-stu-id="81b40-102">ATOM Device Information Settings</span></span>
  <span data-ttu-id="81b40-103">Le impostazioni relative alle informazioni sul dispositivo per l'estensione per il rendering Atom supportano l'invio del nome di un feed Atom e della codifica dei caratteri da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="81b40-103">The device information settings for the Atom rendering extension support submittal of the name of an Atom feed and character encoding to use.</span></span>  
  
 <span data-ttu-id="81b40-104">Nella tabella seguente sono elencate le impostazioni relative alle informazioni sul dispositivo per il rendering in un documento di servizio dati.</span><span class="sxs-lookup"><span data-stu-id="81b40-104">The following table lists the device information settings for rendering to a data service document.</span></span>  
  
|<span data-ttu-id="81b40-105">Impostazione</span><span class="sxs-lookup"><span data-stu-id="81b40-105">Setting</span></span>|<span data-ttu-id="81b40-106">valore</span><span class="sxs-lookup"><span data-stu-id="81b40-106">Value</span></span>|  
|-------------|-----------|  
|`DataFeed`|<span data-ttu-id="81b40-107">Se specificato, esegue il rendering del feed Atom che corrisponde al nome del feed fornito in questa impostazione.</span><span class="sxs-lookup"><span data-stu-id="81b40-107">If specified, renders the Atom feed corresponding to the feed name provided in this setting.</span></span> <span data-ttu-id="81b40-108">In caso contrario, esegue il rendering del documento di servizio Atom per il report.</span><span class="sxs-lookup"><span data-stu-id="81b40-108">If not, renders the Atom service document for the report.</span></span> <span data-ttu-id="81b40-109">Identificatore univoco del feed di dati generato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="81b40-109">The unique auto-generated identifier of the data feed.</span></span> <span data-ttu-id="81b40-110">Questo valore viene utilizzato internamente e non deve essere modificato.</span><span class="sxs-lookup"><span data-stu-id="81b40-110">This  value is used internally and you should not change it.</span></span>|  
|<span data-ttu-id="81b40-111">**Codifica**</span><span class="sxs-lookup"><span data-stu-id="81b40-111">**Encoding**</span></span>|<span data-ttu-id="81b40-112">Il nome IANA (Internet Assigned Numbers Authority) di una codifica dei caratteri supportata da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="81b40-112">The Internet Assigned Numbers Authority (IANA) name of a character encoding that is supported by the .NET Framework.</span></span> <span data-ttu-id="81b40-113">Il valore predefinito è `UTF-8`.</span><span class="sxs-lookup"><span data-stu-id="81b40-113">The default value is `UTF-8`.</span></span> <span data-ttu-id="81b40-114">Esempi di altri valori includono ASCII, UTF-7 e UTF-16.</span><span class="sxs-lookup"><span data-stu-id="81b40-114">Examples of other values include ASCII, UTF-7, and UTF-16.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81b40-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81b40-115">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="81b40-116">[Passaggio delle impostazioni delle informazioni sul dispositivo alle estensioni per il rendering](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="81b40-116">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="81b40-117">[Personalizzare i parametri di estensione per il rendering in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="81b40-117">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="81b40-118">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="81b40-118">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
