---
title: Rimozione di un'estensione per l'elaborazione dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting data processing extensions
- data processing extensions [Reporting Services], removing
- removing data processing extensions
ms.assetid: 1d89e32b-0631-44f6-8178-a57fb791d26d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9f5dfd3a6a7615fa3fd91c917bba6dbf0808f0f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725264"
---
# <a name="removing-a-data-processing-extension"></a><span data-ttu-id="ac5b2-102">Rimozione di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="ac5b2-102">Removing a Data Processing Extension</span></span>
  <span data-ttu-id="ac5b2-103">Per rimuovere un'estensione per l'elaborazione dati, rimuovere semplicemente l'elemento **Extension** per l'estensione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="ac5b2-103">To remove a data processing extension, simply remove the **Extension** element for your data processing extension from the configuration file.</span></span> <span data-ttu-id="ac5b2-104">Se sono state create voci per un server di report e per Progettazione report, rimuovere l'elemento**Extension** sia dal file RSReportServer.config che dal file RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="ac5b2-104">If you made entries for a report server as well as Report Designer, remove the **Extension** element from both the RSReportServer.config and RSReportDesigner.config files.</span></span> <span data-ttu-id="ac5b2-105">Dopo la rimozione delle informazioni di configurazione, l'estensione per l'elaborazione dati non è più disponibile per il componente.</span><span class="sxs-lookup"><span data-stu-id="ac5b2-105">After the configuration information is removed, the data processing extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5b2-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac5b2-106">See Also</span></span>  
 <span data-ttu-id="ac5b2-107">[Estensioni Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="ac5b2-107">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="ac5b2-108">[Implementazione di un'estensione per l'elaborazione dati](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="ac5b2-108">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="ac5b2-109">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ac5b2-109">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
