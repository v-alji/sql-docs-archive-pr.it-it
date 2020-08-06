---
title: Implementazione di un'estensione per il rendering | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendering extensions [Reporting Services]
- custom rendering extensions [Reporting Services]
- transformations [Reporting Services]
- extensions [Reporting Services], rendering
- rendering extensions [Reporting Services], implementing
ms.assetid: 4a5c64f5-2391-4597-ba3f-81d265b23703
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03deb7c818de8d875f69b585ae6015fc178e707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629237"
---
# <a name="implementing-a-rendering-extension"></a><span data-ttu-id="b34f1-102">Implementazione di un'estensione per il rendering</span><span class="sxs-lookup"><span data-stu-id="b34f1-102">Implementing a Rendering Extension</span></span>
  <span data-ttu-id="b34f1-103">Un'estensione per il rendering è un componente o un modulo di un server di report che consente di trasformare le informazioni sul layout e i dati del report in un formato specifico del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b34f1-103">A rendering extension is a component or module of a report server that transforms report data and layout information into a device-specific format.</span></span> <span data-ttu-id="b34f1-104">SQL Server Reporting Services include sei estensioni per il rendering, ovvero HTML, Excel, Word, CSV o Text, XML, Image e PDF.</span><span class="sxs-lookup"><span data-stu-id="b34f1-104">SQL Server Reporting Services includes six rendering extensions: HTML, Excel, Word, CSV or Text, XML, Image, and PDF.</span></span> <span data-ttu-id="b34f1-105">È possibile creare estensioni per il rendering aggiuntive per generare report in altri formati.</span><span class="sxs-lookup"><span data-stu-id="b34f1-105">You can create additional rendering extensions to generate reports in other formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b34f1-106">Per determinare quali sono le estensioni per il rendering disponibili, è possibile visualizzare l'elenco delle estensioni installate nel file RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="b34f1-106">To determine which rendering extensions are available, you can view the list of installed extensions in the RSReportServer.config file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b34f1-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b34f1-107">In This Section</span></span>  
 [<span data-ttu-id="b34f1-108">Panoramica delle estensioni per il rendering</span><span class="sxs-lookup"><span data-stu-id="b34f1-108">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
 <span data-ttu-id="b34f1-109">Vengono fornite informazioni introduttive per la scrittura di un'estensione per il rendering personalizzata per [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b34f1-109">Introduces how to write a custom rendering extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="b34f1-110">Implementazione dell'interfaccia IRenderingExtension</span><span class="sxs-lookup"><span data-stu-id="b34f1-110">Implementing the IRenderingExtension Interface</span></span>](implementing-the-irenderingextension-interface.md)  
 <span data-ttu-id="b34f1-111">Vengono descritti gli attributi di un'estensione per il rendering.</span><span class="sxs-lookup"><span data-stu-id="b34f1-111">Describes the attributes of a rendering extension.</span></span>  
  
 [<span data-ttu-id="b34f1-112">Distribuzione di un'estensione per il rendering</span><span class="sxs-lookup"><span data-stu-id="b34f1-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
 <span data-ttu-id="b34f1-113">Viene descritto come distribuire un'estensione per il rendering in un server di report.</span><span class="sxs-lookup"><span data-stu-id="b34f1-113">Describes how to deploy a rendering extension on a report server.</span></span>  
  
 [<span data-ttu-id="b34f1-114">Rimozione di un'estensione per il rendering</span><span class="sxs-lookup"><span data-stu-id="b34f1-114">Removing a Rendering Extension</span></span>](removing-a-rendering-extension.md)  
 <span data-ttu-id="b34f1-115">Viene descritto come rimuovere un'estensione per il rendering da un server di report.</span><span class="sxs-lookup"><span data-stu-id="b34f1-115">Describes how to remove a rendering extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34f1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b34f1-116">See Also</span></span>  
 <span data-ttu-id="b34f1-117">[Estensioni di Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="b34f1-117">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="b34f1-118">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="b34f1-118">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
