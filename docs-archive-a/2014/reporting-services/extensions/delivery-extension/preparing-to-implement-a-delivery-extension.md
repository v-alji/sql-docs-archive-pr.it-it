---
title: Preparazione all'implementazione di un'estensione per il recapito | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- interfaces [Reporting Services]
- delivery extensions [Reporting Services], implementing
ms.assetid: aee1608d-374f-4ad3-bc23-fe07fdaa52b7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bbf98286e6ed35542d8117b4b87b5ff3425def69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638294"
---
# <a name="preparing-to-implement-a-delivery-extension"></a><span data-ttu-id="11df3-102">Preparazione all'implementazione di un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="11df3-102">Preparing to Implement a Delivery Extension</span></span>
  <span data-ttu-id="11df3-103">Prima di implementare l'estensione per il recapito di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], è necessario definire le interfacce da implementare.</span><span class="sxs-lookup"><span data-stu-id="11df3-103">Before you implement your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you should define the interfaces to implement.</span></span> <span data-ttu-id="11df3-104">È innanzitutto necessario stabilire in che modo verrà utilizzata l'estensione per il recapito, quali impostazioni sono necessarie per l'estensione per il recapito e le funzionalità specifiche da implementare per il recapito delle notifiche dei report.</span><span class="sxs-lookup"><span data-stu-id="11df3-104">You first need to decide how your delivery extension will be used, what settings your delivery extension will require, and the specific functionality you will need to implement in order to deliver report notifications.</span></span>  
  
 <span data-ttu-id="11df3-105">Ogni estensione per il recapito di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] deve fornire le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="11df3-105">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension must provide the following functionality:</span></span>  
  
-   <span data-ttu-id="11df3-106">Un'implementazione dell'interfaccia <xref:Microsoft.ReportingServices.Interfaces.IExtension> che rappresenta l'estensione e un nome di estensione localizzato.</span><span class="sxs-lookup"><span data-stu-id="11df3-106">An <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface implementation that represents the extension and a localized extension name.</span></span>  
  
-   <span data-ttu-id="11df3-107">Un'implementazione di <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> che crea un'estensione per il recapito che può essere utilizzata per recapitare notifiche dei report agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="11df3-107">An <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> implementation that creates a delivery extension that can be used to deliver report notifications to end users.</span></span>  
  
-   <span data-ttu-id="11df3-108">La possibilità di elaborare dati utente specifici per una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="11df3-108">The ability to process specific user data for a subscription.</span></span>  
  
 <span data-ttu-id="11df3-109">Ogni estensione per il recapito può essere estesa per includere la funzionalità seguente:</span><span class="sxs-lookup"><span data-stu-id="11df3-109">Each delivery extension can be enhanced to include the following functionality:</span></span>  
  
-   <span data-ttu-id="11df3-110">Un'implementazione del controllo utente [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] che consente agli utenti finali di utilizzare Gestione report per creare sottoscrizioni dei report che utilizzano l'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="11df3-110">An [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] user control implementation that enables end users to use Report Manager to create report subscriptions that use the delivery extension.</span></span>  
  
 <span data-ttu-id="11df3-111">Nella tabella seguente sono descritte le interfacce e le classi disponibili per le estensioni per il recapito.</span><span class="sxs-lookup"><span data-stu-id="11df3-111">The following table describes the available interfaces and classes for delivery extensions.</span></span>  
  
|<span data-ttu-id="11df3-112">Interfaccia o classe</span><span class="sxs-lookup"><span data-stu-id="11df3-112">Interface or class</span></span>|<span data-ttu-id="11df3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11df3-113">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="11df3-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Interfaccia</span><span class="sxs-lookup"><span data-stu-id="11df3-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Interface</span></span>|<span data-ttu-id="11df3-115">Rappresenta un'estensione in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11df3-115">Represents an extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="11df3-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interfaccia</span><span class="sxs-lookup"><span data-stu-id="11df3-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interface</span></span>|<span data-ttu-id="11df3-117">Rappresenta un'estensione per il recapito in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11df3-117">Represents a delivery extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="11df3-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interfaccia</span><span class="sxs-lookup"><span data-stu-id="11df3-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interface</span></span>|<span data-ttu-id="11df3-119">Contiene informazioni sul server di report richieste dalle estensioni per il recapito (ad esempio, un elenco delle estensioni per il rendering disponibili).</span><span class="sxs-lookup"><span data-stu-id="11df3-119">Contains information about the report server that is required by delivery extensions (for example, a list of the available rendering extensions).</span></span>|  
|<span data-ttu-id="11df3-120">Classe <xref:Microsoft.ReportingServices.Interfaces.Setting></span><span class="sxs-lookup"><span data-stu-id="11df3-120"><xref:Microsoft.ReportingServices.Interfaces.Setting> Class</span></span>|<span data-ttu-id="11df3-121">Rappresenta un'impostazione per un'estensione.</span><span class="sxs-lookup"><span data-stu-id="11df3-121">Represents a setting for an extension.</span></span>|  
|<span data-ttu-id="11df3-122">Classe <xref:Microsoft.ReportingServices.Interfaces.Notification></span><span class="sxs-lookup"><span data-stu-id="11df3-122"><xref:Microsoft.ReportingServices.Interfaces.Notification> Class</span></span>|<span data-ttu-id="11df3-123">Contiene informazioni sulle sottoscrizioni utilizzate dalle estensioni per il recapito dei report.</span><span class="sxs-lookup"><span data-stu-id="11df3-123">Contains subscription information that delivery extensions use to deliver reports.</span></span>|  
|<span data-ttu-id="11df3-124">Classe <xref:Microsoft.ReportingServices.Interfaces.Report></span><span class="sxs-lookup"><span data-stu-id="11df3-124"><xref:Microsoft.ReportingServices.Interfaces.Report> Class</span></span>|<span data-ttu-id="11df3-125">Rappresenta informazioni e metodi specifici del report che consentono alle estensioni per il recapito di recapitare i report agli utenti.</span><span class="sxs-lookup"><span data-stu-id="11df3-125">Represents report-specific information and methods that enable delivery extensions to deliver reports to users.</span></span>|  
|<span data-ttu-id="11df3-126">Classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile></span><span class="sxs-lookup"><span data-stu-id="11df3-126"><xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> Class</span></span>|<span data-ttu-id="11df3-127">Rappresenta l'output di un'estensione per il rendering.</span><span class="sxs-lookup"><span data-stu-id="11df3-127">Represents the output from a rendering extension.</span></span> <span data-ttu-id="11df3-128">Un oggetto <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> contiene il nome file associato e le informazioni sul tipo richiesti dall'estensione per il recapito per elaborare il flusso restituito dall'estensione per il rendering.</span><span class="sxs-lookup"><span data-stu-id="11df3-128">A <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object contains the associated file name and type information that is required by the delivery extension in order to process the stream returned by the rendering extension.</span></span>|  
|<span data-ttu-id="11df3-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interfaccia</span><span class="sxs-lookup"><span data-stu-id="11df3-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interface</span></span>|<span data-ttu-id="11df3-130">Controllo utente che rappresenta il mezzo per il recupero delle informazioni sulla sottoscrizione specifiche dell'estensione dall'utente in Gestione report (ad esempio, un indirizzo di posta elettronica o il percorso di una condivisione file).</span><span class="sxs-lookup"><span data-stu-id="11df3-130">A user control that represents the means to retrieve delivery extension-specific subscription information from the user in Report Manager (for example, an e-mail address or the path to a file share).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11df3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11df3-131">See Also</span></span>  
 <span data-ttu-id="11df3-132">[Estensioni di Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="11df3-132">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="11df3-133">[Implementazione di un'estensione per il recapito](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="11df3-133">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="11df3-134">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="11df3-134">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
