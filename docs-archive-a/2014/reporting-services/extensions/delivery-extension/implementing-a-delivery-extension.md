---
title: Implementazione di un'estensione per il recapito | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery [Reporting Services]
- custom delivery extensions [Reporting Services]
- extensions [Reporting Services], delivery
- delivery extensions [Reporting Services]
ms.assetid: 600cd229-efcd-480e-8c95-3c3c39ff4e7a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af1e804e029dae77fb7836577aa8d4a45ad20109
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638300"
---
# <a name="implementing-a-delivery-extension"></a><span data-ttu-id="de7c0-102">Implementazione di un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-102">Implementing a Delivery Extension</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="de7c0-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] consente agli utenti di creare e pubblicare report che dopo la creazione e la pubblicazione possono essere recapitati in diverse posizioni.</span><span class="sxs-lookup"><span data-stu-id="de7c0-103">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enables users to create and publish reports that, once created and published, can be delivered to various locations.</span></span> <span data-ttu-id="de7c0-104">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] include inoltre diverse estensioni per il recapito e un'API di recapito tramite cui gli sviluppatori possono creare estensioni per il recapito aggiuntive per estendere ulteriormente le funzionalità di recapito in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de7c0-104">In addition, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes several delivery extensions and a delivery API that enable developers to create additional delivery extensions to further extend the functionality of delivery in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="de7c0-105">Per un'implementazione di esempio di un'estensione per il recapito, vedere la pagina degli [esempi del prodotto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="de7c0-105">For a sample implementation of a delivery extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de7c0-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="de7c0-106">In This Section</span></span>  
 <span data-ttu-id="de7c0-107">[Panoramica sulle estensioni per il recapito] recapito-estensioni-overview.md)</span><span class="sxs-lookup"><span data-stu-id="de7c0-107">[Delivery Extensions Overview]delivery-extensions-overview.md)</span></span>  
 <span data-ttu-id="de7c0-108">Vengono fornite informazioni introduttive per la scrittura di un'estensione per il recapito personalizzata per [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de7c0-108">Introduces how to write a custom delivery extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="de7c0-109">Preparazione all'implementazione di un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-109">Preparing to Implement a Delivery Extension</span></span>](preparing-to-implement-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-110">Vengono descritte le interfacce e le classi disponibili per l'implementazione di un'estensione per il recapito di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], nonché i problemi da considerare prima dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="de7c0-110">Describes the interfaces and classes available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, as well as issues to consider before implementation.</span></span>  
  
 [<span data-ttu-id="de7c0-111">Creazione di una libreria di estensioni per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-111">Creating a Delivery Extension Library</span></span>](creating-a-delivery-extension-library.md)  
 <span data-ttu-id="de7c0-112">Vengono descritte le operazioni di assegnazione di uno spazio dei nomi per l'estensione per il recapito di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e di compilazione dell'estensione per il recapito nella DLL di una libreria.</span><span class="sxs-lookup"><span data-stu-id="de7c0-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension and compiling your delivery extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="de7c0-113">Implementazione dell'interfaccia IDeliveryExtension per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-113">Implementing the IDeliveryExtension Interface for a Delivery Extension</span></span>](implementing-the-ideliveryextension-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-114">Vengono descritti gli attributi di un'estensione per il recapito e come implementare una classe personalizzata dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="de7c0-114">Describes the attributes of a delivery extension, and how to implement your own delivery extension class.</span></span>  
  
 [<span data-ttu-id="de7c0-115">Uso della classe Notification per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-115">Using a Notification Class for a Delivery Extension</span></span>](using-a-notification-class-for-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-116">Vengono descritti gli attributi di una classe **Notification** e come usarla nell'implementazione dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="de7c0-116">Describes the attributes of a **Notification** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="de7c0-117">Uso della classe Setting per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-117">Using the Setting Class for a Delivery Extension</span></span>](using-the-setting-class-for-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-118">Vengono descritti gli attributi di una classe **Setting** e come usarla nell'implementazione dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="de7c0-118">Describes the attributes of a **Setting** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="de7c0-119">Utilizzo dell'interfaccia IDeliveryReportServerInformation per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-119">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-120">Vengono descritti gli attributi di una classe **IDeliveryReportServerInformation** e come usarla nell'implementazione dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="de7c0-120">Describes the attributes of a **IDeliveryReportServerInformation** interface and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="de7c0-121">Utilizzo della classe Report per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-121">Using the Report Class for a Delivery Extension</span></span>](using-the-report-class-for-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-122">Vengono descritti gli attributi di una classe **Report** e come usarla nell'implementazione dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="de7c0-122">Describes the attributes of a **Report** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="de7c0-123">Utilizzo della classe RenderedOutputFile per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-123">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-124">Vengono descritti gli attributi di una classe **RenderedOutputFile** e come usarla nell'implementazione dell'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="de7c0-124">Describes the attributes of a **RenderedOutputFile** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="de7c0-125">Implementazione dell'interfaccia ISubscriptionBaseUIUserControl per un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-125">Implementing the ISubscriptionBaseUIUserControl Interface for a Delivery Extension</span></span>](implementing-the-isubscriptionbaseuiusercontrol-interface.md)  
 <span data-ttu-id="de7c0-126">Vengono descritti gli attributi di un controllo utente di un'estensione per il recapito e come implementare un'interfaccia utente personalizzata per una sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="de7c0-126">Describes the attributes of a delivery extension user control and how to implement your own user interface for a subscription.</span></span>  
  
 [<span data-ttu-id="de7c0-127">Distribuzione di un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-127">Deploying a Delivery Extension</span></span>](deploying-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-128">Viene descritto come distribuire un'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="de7c0-128">Describes how to deploy your delivery extension.</span></span>  
  
 [<span data-ttu-id="de7c0-129">Esecuzione del debug del codice dell'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-129">Debugging Delivery Extension Code</span></span>](debugging-delivery-extension-code.md)  
 <span data-ttu-id="de7c0-130">Viene descritto come eseguire il debug del codice in un'estensione per il recapito.</span><span class="sxs-lookup"><span data-stu-id="de7c0-130">Describes how to debug code in your delivery extension.</span></span>  
  
 [<span data-ttu-id="de7c0-131">Rimozione di un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="de7c0-131">Removing a Delivery Extension</span></span>](removing-a-delivery-extension.md)  
 <span data-ttu-id="de7c0-132">Viene descritto come rimuovere un'estensione per il recapito da un server di report.</span><span class="sxs-lookup"><span data-stu-id="de7c0-132">Describes how to remove a delivery extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de7c0-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de7c0-133">See Also</span></span>  
 <span data-ttu-id="de7c0-134">[Estensioni Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="de7c0-134">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="de7c0-135">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="de7c0-135">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
