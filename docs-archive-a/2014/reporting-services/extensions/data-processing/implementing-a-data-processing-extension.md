---
title: Implementazione di un'estensione per l'elaborazione dati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom data processing extensions [Reporting Services]
- data sources [Reporting Services], data processing extensions
- data processing extensions [Reporting Services]
- extensions [Reporting Services], data processing
ms.assetid: 8dc2b44e-5ad9-411d-a29f-7213e29321a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5a1b7668f2319e742dcf3f1969fc3c5cc85cd7eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725271"
---
# <a name="implementing-a-data-processing-extension"></a><span data-ttu-id="7f0d2-102">Implementazione di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-102">Implementing a Data Processing Extension</span></span>
  <span data-ttu-id="7f0d2-103">Le estensioni per l'elaborazione dati in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] consentono di eseguire la connessione a un'origine dati e di recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-103">Data processing extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enable you to connect to a data source and retrieve data.</span></span> <span data-ttu-id="7f0d2-104">Fungono inoltre da ponte tra un'origine dati e un set di dati.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-104">They also serve as a bridge between a data source and a dataset.</span></span> <span data-ttu-id="7f0d2-105">Le estensioni per l'elaborazione dati di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] sono modellate in base a un subset delle interfacce dei provider di dati [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f0d2-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions are modeled after a subset of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] data provider interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f0d2-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="7f0d2-106">In This Section</span></span>  
 [<span data-ttu-id="7f0d2-107">Panoramica delle estensioni per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-107">Data Processing Extensions Overview</span></span>](data-processing-extensions-overview.md)  
 <span data-ttu-id="7f0d2-108">Vengono fornite informazioni introduttive per la scrittura di un'estensione per l'elaborazione dati per [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f0d2-108">Introduces how to write a custom data processing extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="7f0d2-109">Preparazione all'implementazione di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-109">Preparing to Implement a Data Processing Extension</span></span>](preparing-to-implement-a-data-processing-extension.md)  
 <span data-ttu-id="7f0d2-110">Vengono descritte le interfacce disponibili quando si implementa un'estensione per l'elaborazione dati di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e vengono indicati i casi in cui è necessario implementare un'interfaccia specifica.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-110">Describes the interfaces available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, as well as when you are required to implement a particular interface.</span></span>  
  
 [<span data-ttu-id="7f0d2-111">Creazione di una libreria di estensioni per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-111">Creating a Data Processing Extension Library</span></span>](creating-a-data-processing-extension-library.md)  
 <span data-ttu-id="7f0d2-112">Vengono descritte le operazioni di assegnazione di uno spazio dei nomi per l'estensione per l'elaborazione dati di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] e di compilazione dell'estensione per l'elaborazione dati nella DLL di una libreria.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension and compiling your data processing extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="7f0d2-113">Implementazione di una classe Connection per un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-113">Implementing a Connection Class for a Data Processing Extension</span></span>](implementing-a-connection-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="7f0d2-114">Vengono descritti gli attributi di una connessione e come implementare una classe **Connection** personalizzata per l'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-114">Describes the attributes of a connection and how to implement your own **Connection** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="7f0d2-115">Implementazione di una classe Command per un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-115">Implementing a Command Class for a Data Processing Extension</span></span>](implementing-a-command-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="7f0d2-116">Vengono descritti gli attributi di un comando e come implementare una classe **Command** personalizzata per l'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-116">Describes the attributes of a command, and how to implement your own **Command** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="7f0d2-117">Implementazione di una classe DataReader per un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-117">Implementing a DataReader Class for a Data Processing Extension</span></span>](implementing-a-datareader-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="7f0d2-118">Vengono descritti gli attributi di un lettore di dati e come implementare una classe **DataReader** personalizzata per l'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-118">Describes the attributes of a data reader and how to implement your own **DataReader** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="7f0d2-119">Uso di un set di dati esterno con Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7f0d2-119">Using an External Dataset with Reporting Services</span></span>](using-an-external-dataset-with-reporting-services.md)  
 <span data-ttu-id="7f0d2-120">Viene descritto come esporre gli oggetti **DataSet** personalizzati nel server di report per l'uso.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-120">Describes how to expose your custom **DataSet** objects to the report server for consumption.</span></span>  
  
 [<span data-ttu-id="7f0d2-121">Distribuzione di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-121">Deploying a Data Processing Extension</span></span>](deploying-a-data-processing-extension.md)  
 <span data-ttu-id="7f0d2-122">Viene descritto come distribuire un'estensione per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-122">Describes how to deploy your data processing extension.</span></span>  
  
 [<span data-ttu-id="7f0d2-123">Debug del codice di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-123">Debugging Data Processing Extension Code</span></span>](debugging-data-processing-extension-code.md)  
 <span data-ttu-id="7f0d2-124">Viene descritto come eseguire il debug del codice nelle estensioni per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-124">Describes how to debug code in your data processing extensions.</span></span>  
  
 [<span data-ttu-id="7f0d2-125">Rimozione di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="7f0d2-125">Removing a Data Processing Extension</span></span>](removing-a-data-processing-extension.md)  
 <span data-ttu-id="7f0d2-126">Viene descritto come rimuovere un'estensione per l'elaborazione dati da un server di report o da Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="7f0d2-126">Describes how to remove a data processing extension from a report server or Report Designer.</span></span>  
  
 <span data-ttu-id="7f0d2-127">Per un esempio di estensione per l'elaborazione dati completamente implementata, vedere la pagina degli [esempi del prodotto SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="7f0d2-127">For a sample of a fully implemented data processing extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f0d2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f0d2-128">See Also</span></span>  
 <span data-ttu-id="7f0d2-129">[Estensioni Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="7f0d2-129">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="7f0d2-130">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="7f0d2-130">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
