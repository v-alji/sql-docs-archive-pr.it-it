---
title: Configurare Gestione report per il passaggio di cookie di autenticazione personalizzati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- authentication [Reporting Services]
- extensions [Reporting Services], custom security
ms.assetid: 91aeb053-149e-4562-ae4c-a688d0e1b2ba
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 90e8798fb91152ec64e7f290dc1522fc8eaa451c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625968"
---
# <a name="configure-report-manager-to-pass-custom-authentication-cookies"></a><span data-ttu-id="9b5c4-102">Configurare Gestione report per il passaggio di cookie di autenticazione personalizzati</span><span class="sxs-lookup"><span data-stu-id="9b5c4-102">Configure Report Manager to Pass Custom Authentication Cookies</span></span>
  <span data-ttu-id="9b5c4-103">Se si sta utilizzando un'estensione di autenticazione personalizzata, è necessario configurare Gestione report per la trasmissione di cookie di autenticazione personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-103">If you are using a custom authentication extension, you should configure Report Manager to transmit custom authentication cookies.</span></span> <span data-ttu-id="9b5c4-104">In caso contrario, i cookie verranno trasmessi solo mediante richieste HTTP specifiche del server di report.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-104">Otherwise, Report Manager will only transmit cookies through HTTP requests specific to the report server.</span></span> <span data-ttu-id="9b5c4-105">Se si desidera trasmettere ulteriori cookie, è necessario modificare il file RSReportServer.Config.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-105">If you want to transmit additional cookies, you must modify the RSReportServer.Config file.</span></span>  
  
## <a name="modifying-the-rsreportserverconfig-file"></a><span data-ttu-id="9b5c4-106">Modifica del file RSReportServer.config</span><span class="sxs-lookup"><span data-stu-id="9b5c4-106">Modifying the RSReportServer.Config File</span></span>  
 <span data-ttu-id="9b5c4-107">È possibile abilitare Gestione report per trasmettere ulteriori cookie al server di report aggiungendo un `PassThroughCookies` elemento <> alle impostazioni di configurazione del Gestione report nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-107">You can enable Report Manager to transmit additional cookies through to the report server by adding a <`PassThroughCookies`> element to the Report Manager configuration settings in the RSReportServer.config file.</span></span> <span data-ttu-id="9b5c4-108">La trasmissione di cookie aggiuntivi è utile in una soluzione di autenticazione Single Sign-On che, insieme ai cookie di autenticazione del server di report, richiede anche cookie di un sistema di autenticazione di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9b5c4-108">Transmitting additional cookies is helpful in a single sign-on authentication solution that requires not only the report server authentication cookies, but also cookies from a third-party authentication system.</span></span>  
  
 <span data-ttu-id="9b5c4-109">Per consentire la trasmissione di ulteriori cookie tramite richieste HTTP quando si utilizza Gestione report, impostare gli elementi seguenti nel file RSReportServer.config:</span><span class="sxs-lookup"><span data-stu-id="9b5c4-109">To enable additional cookies to be transmitted through HTTP requests when using Report Manager, set the following elements in the RSReportServer.config file:</span></span>  
  
```  
<UI>  
   <CustomAuthenticationUI>  
      ...  
      <PassThroughCookies>  
         <PassThroughCookie>cookiename1</PassThroughCookie>  
         <PassThroughCookie>cookiename2</PassThroughCookie>  
      </PassThroughCookies>  
   </CustomAuthenticationUI>  
      ...  
</UI>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b5c4-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b5c4-110">See Also</span></span>  
 <span data-ttu-id="9b5c4-111">[Autenticazione con il server di report](authentication-with-the-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="9b5c4-111">[Authentication with the Report Server](authentication-with-the-report-server.md) </span></span>  
 <span data-ttu-id="9b5c4-112">[File di configurazione RSReportServer](../report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="9b5c4-112">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) </span></span>  
 <span data-ttu-id="9b5c4-113">[Panoramica sulle estensioni di sicurezza](../extensions/security-extension/security-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="9b5c4-113">[Security Extensions Overview](../extensions/security-extension/security-extensions-overview.md) </span></span>  
 [<span data-ttu-id="9b5c4-114">Configurare e amministrare un server di report &#40;modalità nativa SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9b5c4-114">Configure and Administer a Report Server &#40;SSRS Native Mode&#41;</span></span>](../report-server/configure-and-administer-a-report-server-ssrs-native-mode.md)  
  
  
