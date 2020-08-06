---
title: Riferimento della libreria del provider WMI Reporting Services (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider Library
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services], library
ms.assetid: 17ba711d-7eff-4423-9168-63dc425a3428
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a98ca22f9d34627e484a698dcf540b31808d07e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627596"
---
# <a name="reporting-services-wmi-provider-library-reference-ssrs"></a><span data-ttu-id="d61ad-102">Riferimento della libreria del provider WMI Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="d61ad-102">Reporting Services WMI Provider Library Reference (SSRS)</span></span>
  <span data-ttu-id="d61ad-103">Il provider WMI (Windows Management Instrumentation) di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] supporta operazioni WMI che consentono di scrivere script e codice per modificare le impostazioni del server di report e di Gestione report.</span><span class="sxs-lookup"><span data-stu-id="d61ad-103">The [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider supports WMI operations that enable you to write scripts and code to modify settings of the report server and Report Manager.</span></span>  
  
 <span data-ttu-id="d61ad-104">Ad esempio, se si vuole modificare l'impostazione relativa all'uso della sicurezza integrata quando il server di report si connette al database del server di report, creare un'istanza della classe MSReportServer_ConfigurationSetting e usare la proprietà DatabaseIntegratedSecurity dell'istanza del server di report.</span><span class="sxs-lookup"><span data-stu-id="d61ad-104">For example, if you want to change whether integrated security is used when the report server connects to the report server database, create an instance of the MSReportServer_ConfigurationSetting class and use the DatabaseIntegratedSecurity property of the of the report server instance.</span></span> <span data-ttu-id="d61ad-105">Le classi mostrate nella tabella seguente rappresentano i componenti di [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d61ad-105">The classes shown in the following table represent [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] components.</span></span> <span data-ttu-id="d61ad-106">Le classi sono definite negli spazi dei nomi [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] o [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d61ad-106">The classes are defined in either the [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)] or the [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)] namespaces.</span></span> <span data-ttu-id="d61ad-107">Ognuna delle classi supporta operazioni di lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="d61ad-107">Each of the classes support read and write operations.</span></span> <span data-ttu-id="d61ad-108">Le operazioni di creazione non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="d61ad-108">Create operations are not supported.</span></span>  
  
## <a name="classes"></a><span data-ttu-id="d61ad-109">Classi</span><span class="sxs-lookup"><span data-stu-id="d61ad-109">Classes</span></span>  
 [<span data-ttu-id="d61ad-110">classe MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="d61ad-110">MSReportServer_Instance Class</span></span>](msreportserver-instance-class.md)  
 <span data-ttu-id="d61ad-111">Fornisce le informazioni di base necessarie affinché un client si connetta a un server di report installato.</span><span class="sxs-lookup"><span data-stu-id="d61ad-111">Provides basic information required for a client to connect to an installed report server.</span></span>  
  
 [<span data-ttu-id="d61ad-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="d61ad-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
 <span data-ttu-id="d61ad-113">Rappresenta i parametri di installazione e di runtime di un'istanza del server di report.</span><span class="sxs-lookup"><span data-stu-id="d61ad-113">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="d61ad-114">Tali parametri sono archiviati nel file di configurazione per il server di report.</span><span class="sxs-lookup"><span data-stu-id="d61ad-114">These parameters are stored in the configuration file for the report server.</span></span>  
  
 <span data-ttu-id="d61ad-115">Per ulteriori informazioni sulle operazioni WMI, vedere la documentazione di WMI SDK inclusa in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="d61ad-115">For more information about WMI operations, see the WMI SDK documentation included with the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d61ad-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d61ad-116">See Also</span></span>  
 <span data-ttu-id="d61ad-117">[Accedere al provider WMI Reporting Services](../tools/access-the-reporting-services-wmi-provider.md) </span><span class="sxs-lookup"><span data-stu-id="d61ad-117">[Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md) </span></span>  
 [<span data-ttu-id="d61ad-118">Riferimento tecnico &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="d61ad-118">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
