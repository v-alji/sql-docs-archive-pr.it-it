---
title: Distribuzione di un'estensione per l'elaborazione dati | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- Extension element
- deploying [Reporting Services], extensions
ms.assetid: e5c0b5a9-1386-47cb-aade-96653ecfaa54
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 84fc2d2853ce7a6aae77f313ef0f4026ad2f35cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725284"
---
# <a name="deploying-a-data-processing-extension"></a><span data-ttu-id="a41fa-102">Distribuzione di un'estensione per l'elaborazione dati</span><span class="sxs-lookup"><span data-stu-id="a41fa-102">Deploying a Data Processing Extension</span></span>
  <span data-ttu-id="a41fa-103">Dopo avere scritto e compilato l'estensione per l'elaborazione dati di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] in una libreria [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], è necessario consentirne l'individuazione da parte del server di report e di Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="a41fa-103">Once you have written and compiled your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension into a [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] library, you need to make it discoverable by the report server and by Report Designer.</span></span> <span data-ttu-id="a41fa-104">A tale scopo, è sufficiente copiare l'estensione nelle directory appropriate e aggiungere voci ai file di configurazione appropriati di [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a41fa-104">This is as easy as copying the extension to the appropriate directories and adding entries to the appropriate [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration files.</span></span>  
  
## <a name="configuration-file-extension-element"></a><span data-ttu-id="a41fa-105">Elemento Extension del file di configurazione</span><span class="sxs-lookup"><span data-stu-id="a41fa-105">Configuration-File Extension Element</span></span>  
 <span data-ttu-id="a41fa-106">Le estensioni per l'elaborazione dati distribuite nel server di report o in Progettazione report devono essere immesse come elementi **Extension** nei file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a41fa-106">Data processing extensions that you deploy to the report server or Report Designer need to be entered as **Extension** elements in the configuration files.</span></span> <span data-ttu-id="a41fa-107">Questi file sono RSReportServer.config per il server di report e RSReportDesigner.config per Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="a41fa-107">These files are RSReportServer.config for the report server and RSReportDesigner.config for Report Designer.</span></span>  
  
 <span data-ttu-id="a41fa-108">Nella tabella riportata di seguito vengono descritti gli attributi dell'elemento **Extension** per le estensioni per l'elaborazione dati.</span><span class="sxs-lookup"><span data-stu-id="a41fa-108">The following table describes the attributes for the **Extension** element for data processing extensions.</span></span>  
  
|<span data-ttu-id="a41fa-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="a41fa-109">Attribute</span></span>|<span data-ttu-id="a41fa-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a41fa-110">Description</span></span>|  
|---------------|-----------------|  
|`Name`|<span data-ttu-id="a41fa-111">Nome univoco per l'estensione, ad esempio, "SQL" per l'estensione per l'elaborazione dati [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] o "OLE DB" per l'estensione per l'elaborazione dati OLE DB.</span><span class="sxs-lookup"><span data-stu-id="a41fa-111">A unique name for the extension, for example, "SQL" for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data processing extension or "OLEDB" for the OLE DB data processing extension.</span></span> <span data-ttu-id="a41fa-112">La lunghezza massima consentita per l'attributo `Name` è di 255 caratteri.</span><span class="sxs-lookup"><span data-stu-id="a41fa-112">The maximum length for the `Name` attribute is 255 characters.</span></span> <span data-ttu-id="a41fa-113">Il nome deve essere univoco tra tutte le voci dell'elemento **Extension** di un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="a41fa-113">The name must be unique among all entries within the **Extension** element of a configuration file.</span></span>|  
|`Type`|<span data-ttu-id="a41fa-114">Elenco delimitato da virgole che include lo spazio dei nomi completo insieme al nome dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a41fa-114">A comma-separated list that includes the fully qualified namespace along with the name of the assembly.</span></span>|  
|`Visible`|<span data-ttu-id="a41fa-115">Il valore `false` indica che l'estensione per l'elaborazione dati non deve essere visibile nelle interfacce utente.</span><span class="sxs-lookup"><span data-stu-id="a41fa-115">A value of `false` indicates that the data processing extension should not be visible in user interfaces.</span></span> <span data-ttu-id="a41fa-116">Se l'attributo non è incluso, il valore predefinito è `true`.</span><span class="sxs-lookup"><span data-stu-id="a41fa-116">If the attribute is not included, the default value is `true`.</span></span>|  
  
 <span data-ttu-id="a41fa-117">Per altre informazioni sui file RSReportServer.config o RSReportDesigner.config, vedere [File di configurazione di Reporting Services](../../report-server/reporting-services-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="a41fa-117">For more information about the RSReportServer.config or RSReportDesigner.config files, see [Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a41fa-118">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a41fa-118">In This Section</span></span>  
  
|<span data-ttu-id="a41fa-119">Argomento</span><span class="sxs-lookup"><span data-stu-id="a41fa-119">Topic</span></span>|<span data-ttu-id="a41fa-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a41fa-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="a41fa-121">Procedura: Distribuire un'estensione per l'elaborazione dati in un server di report</span><span class="sxs-lookup"><span data-stu-id="a41fa-121">How to: Deploy a Data Processing Extension to a Report Server</span></span>](deploying-a-data-processing-extension-to-a-report-server.md)|<span data-ttu-id="a41fa-122">Viene descritto come distribuire un'estensione per l'elaborazione dati in un server di report.</span><span class="sxs-lookup"><span data-stu-id="a41fa-122">Describes how to deploy your data processing extension to a report server.</span></span>|  
|[<span data-ttu-id="a41fa-123">Procedura: Distribuire un'estensione per l'elaborazione dati in Progettazione report</span><span class="sxs-lookup"><span data-stu-id="a41fa-123">How to: Deploy a Data Processing Extension to Report Designer</span></span>](deploying-a-data-processing-extension-to-report-designer.md)|<span data-ttu-id="a41fa-124">Viene descritto come distribuire un'estensione per l'elaborazione dati in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="a41fa-124">Describes how to deploy your data processing extension to Report Designer.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a41fa-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a41fa-125">See Also</span></span>  
 <span data-ttu-id="a41fa-126">[Estensioni Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="a41fa-126">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="a41fa-127">[Implementazione di un'estensione per l'elaborazione dati](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="a41fa-127">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="a41fa-128">Libreria di estensioni di Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a41fa-128">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
