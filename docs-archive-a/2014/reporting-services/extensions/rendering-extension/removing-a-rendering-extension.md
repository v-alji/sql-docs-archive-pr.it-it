---
title: Rimozione di un'estensione per il rendering | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629235"
---
# <a name="removing-a-rendering-extension"></a><span data-ttu-id="419c5-102">Rimozione di un'estensione per il rendering</span><span class="sxs-lookup"><span data-stu-id="419c5-102">Removing a Rendering Extension</span></span>
  <span data-ttu-id="419c5-103">Per rimuovere un' [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] estensione per il rendering, è sufficiente rimuovere l' `Extension` elemento per l'estensione per il rendering dal file di rsreportserver.config, situato in **%programmi%\microsoft SQL Server \ MSRS10_50. \<Instance Name> Cartella \Reporting Services\ReportServer**</span><span class="sxs-lookup"><span data-stu-id="419c5-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] rendering extension, simply remove the `Extension` element for your rendering extension from the rsreportserver.config file, located in **%ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<Instance Name>\Reporting Services\ReportServer** folder.</span></span> <span data-ttu-id="419c5-104">Se sono state apportate voci per un Progettazione report e un server di report, rimuovere `Extension` anche l'elemento dal [file di configurazione RSReportDesigner](../../report-server/rsreportdesigner-configuration-file.md) .</span><span class="sxs-lookup"><span data-stu-id="419c5-104">If you made entries for a Report Designer as well as a report server, remove the `Extension` element from the [RSReportDesigner Configuration File](../../report-server/rsreportdesigner-configuration-file.md) as well.</span></span> <span data-ttu-id="419c5-105">Dopo la rimozione delle informazioni di configurazione, l'estensione per il rendering non è più disponibile per il componente.</span><span class="sxs-lookup"><span data-stu-id="419c5-105">After the configuration information is removed, the rendering extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419c5-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="419c5-106">See Also</span></span>  
 <span data-ttu-id="419c5-107">[File di configurazione di Reporting Services](../../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="419c5-107">[Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="419c5-108">[Implementazione di un'estensione per il rendering](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="419c5-108">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 <span data-ttu-id="419c5-109">[Panoramica delle estensioni per il rendering](rendering-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="419c5-109">[Rendering Extensions Overview](rendering-extensions-overview.md) </span></span>  
 <span data-ttu-id="419c5-110">[Implementazione dell'interfaccia IRenderingExtension](implementing-the-irenderingextension-interface.md) </span><span class="sxs-lookup"><span data-stu-id="419c5-110">[Implementing the IRenderingExtension Interface](implementing-the-irenderingextension-interface.md) </span></span>  
 <span data-ttu-id="419c5-111">[Considerazioni sulla sicurezza per le estensioni](../security-considerations-for-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="419c5-111">[Security Considerations for Extensions](../security-considerations-for-extensions.md) </span></span>  
 [<span data-ttu-id="419c5-112">Distribuzione di un'estensione per il rendering</span><span class="sxs-lookup"><span data-stu-id="419c5-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
  
  
