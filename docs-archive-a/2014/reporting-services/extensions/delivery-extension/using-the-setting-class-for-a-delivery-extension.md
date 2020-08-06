---
title: Using the Setting Class for a Delivery Extension (Uso della classe Setting per un'estensione per il recapito) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], settings
- Setting class
ms.assetid: 50746639-da7c-46a5-ac7b-e87dd6b91880
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 594cf28391ae4523e1a95ad79ee5b1280ff72218
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712807"
---
# <a name="using-the-setting-class-for-a-delivery-extension"></a><span data-ttu-id="1dab1-102">Utilizzo della classe Setting per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="1dab1-102">Using the Setting Class for a Delivery Extension</span></span>
  <span data-ttu-id="1dab1-103">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting> si trova nello spazio dei nomi <xref:Microsoft.ReportingServices.Interfaces> e rappresenta le informazioni sulle impostazioni dell'estensione per un'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="1dab1-103">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is located in the <xref:Microsoft.ReportingServices.Interfaces> namespace and represents information about extension settings for a delivery extension.</span></span> <span data-ttu-id="1dab1-104">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting> fornisce l'infrastruttura per l'archiviazione delle informazioni relative alle impostazioni necessarie per il corretto funzionamento di un'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="1dab1-104">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class provides infrastructure for storing information about the settings that are required in order for a delivery extension to function properly.</span></span> <span data-ttu-id="1dab1-105">Per il recapito tramite posta elettronica in un server report, ad esempio, a un utente viene richiesto di fornire le impostazioni specifiche del recapito tramite posta elettronica, come l'indirizzo del destinatario, l'indirizzo del mittente, la riga dell'oggetto del messaggio di posta elettronica e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="1dab1-105">For example, in Report Server E-Mail delivery, a user is required to supply settings specific to e-mail delivery, such as the recipient's address, the sender's address, the subject line of the e-mail, and more.</span></span> <span data-ttu-id="1dab1-106">Anche i provider di recapito personalizzati richiederanno senza dubbio che l'utente fornisca impostazioni specifiche per consentire il recapito di notifiche e report da parte dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="1dab1-106">Undoubtedly, your custom delivery providers will require the user to supply specific settings in order for the delivery extension to deliver notifications and reports.</span></span>  
  
 <span data-ttu-id="1dab1-107">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting> viene utilizzata nell'implementazione della proprietà <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> dell'interfaccia <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>.</span><span class="sxs-lookup"><span data-stu-id="1dab1-107">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is used when implementing the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.ExtensionSettings%2A> property of the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface.</span></span> <span data-ttu-id="1dab1-108">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting> viene inoltre utilizzata per l'elaborazione dei dati di impostazione delle estensioni forniti da un utente quando viene creata una sottoscrizione o una notifica.</span><span class="sxs-lookup"><span data-stu-id="1dab1-108">The <xref:Microsoft.ReportingServices.Interfaces.Setting> class is also used for processing the extension setting data that is supplied by a user when a subscription or notification is created.</span></span>  
  
 <span data-ttu-id="1dab1-109">Per un esempio su come usare la classe <xref:Microsoft.ReportingServices.Interfaces.Setting>, vedere [ Esempi del prodotto Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="1dab1-109">For an example of how to use the <xref:Microsoft.ReportingServices.Interfaces.Setting> class, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dab1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dab1-110">See Also</span></span>  
 <span data-ttu-id="1dab1-111">[Implementazione di un'estensione per il recapito](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="1dab1-111">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="1dab1-112">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="1dab1-112">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
