---
title: Rimozione di un'estensione per il recapito | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- removing delivery extensions
- deleting delivery extensions
- delivery extensions [Reporting Services], removing
ms.assetid: dcb7caf2-d19a-4bc5-afb3-2b61ad11cac5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7c4320f46b5013b0fa2accbc81792748c2d9f384
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638292"
---
# <a name="removing-a-delivery-extension"></a><span data-ttu-id="55550-102">Rimozione di un'estensione per il recapito</span><span class="sxs-lookup"><span data-stu-id="55550-102">Removing a Delivery Extension</span></span>
  <span data-ttu-id="55550-103">Per rimuovere un'estensione per il recapito di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], rimuovere semplicemente l'elemento **Extension** per l'estensione dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="55550-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, simply remove the **Extension** element for your delivery extension from the configuration file.</span></span> <span data-ttu-id="55550-104">Dopo la rimozione delle informazioni di configurazione, l'estensione per il recapito non è più disponibile per il server di report.</span><span class="sxs-lookup"><span data-stu-id="55550-104">After the configuration information is removed, the delivery extension is no longer available to the report server.</span></span>  
  
 <span data-ttu-id="55550-105">Dopo aver rimosso l'elemento **Extension** corrispondente di un'estensione per il recapito dal file di configurazione, l'estensione non è più registrata nel server di report.</span><span class="sxs-lookup"><span data-stu-id="55550-105">Once a delivery extension's corresponding **Extension** element is removed from the configuration file, it is no longer registered with the report server.</span></span> <span data-ttu-id="55550-106">Il server di report rimuove la voce dall'elenco di estensioni per il recapito e disattiva qualsiasi sottoscrizione che utilizza tale estensione.</span><span class="sxs-lookup"><span data-stu-id="55550-106">The report server removes the entry from the list of delivery extensions and deactivates any subscriptions which use that delivery extension.</span></span> <span data-ttu-id="55550-107">Quando un'estensione per il recapito viene rimossa, gli utenti non possono più selezionarla come metodo di notifica.</span><span class="sxs-lookup"><span data-stu-id="55550-107">When a delivery extension is removed, users are no longer able to select it as a method of notification.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55550-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55550-108">See Also</span></span>  
 <span data-ttu-id="55550-109">[Implementazione di un'estensione per il recapito](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="55550-109">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="55550-110">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="55550-110">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
