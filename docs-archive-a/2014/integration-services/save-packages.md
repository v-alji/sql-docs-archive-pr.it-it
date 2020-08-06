---
title: Salvare pacchetti | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 17c1de2c-637f-45c2-a148-79294bae0af4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 102e2c3eab001c230722bf3485d6ea9731aa99a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722904"
---
# <a name="save-packages"></a><span data-ttu-id="1278f-102">Salvataggio di pacchetti</span><span class="sxs-lookup"><span data-stu-id="1278f-102">Save Packages</span></span>
  <span data-ttu-id="1278f-103">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] è possibile usare Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] per compilare i pacchetti e quindi salvarli nel file system come file XML, con estensione dtsx.</span><span class="sxs-lookup"><span data-stu-id="1278f-103">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] you build packages by using [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer and save the packages to the file system as XML files (.dtsx files).</span></span> <span data-ttu-id="1278f-104">È inoltre possibile salvare copie del file XML di un pacchetto nel database msdb in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o nell'archivio pacchetti.</span><span class="sxs-lookup"><span data-stu-id="1278f-104">You can also save copies of the package XML file to the msdb database in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="1278f-105">L'archivio pacchetti è costituito dalle cartelle del percorso del file system gestito dal servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1278f-105">The package store represents the folders in the file system location that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages.</span></span>  
  
 <span data-ttu-id="1278f-106">Se si salva un pacchetto nel file system, successivamente sarà possibile utilizzare il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] per importarlo in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] o nell'archivio pacchetti.</span><span class="sxs-lookup"><span data-stu-id="1278f-106">If you save a package to the file system, you can later use the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service to import the package to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to the package store.</span></span> <span data-ttu-id="1278f-107">Per altre informazioni, vedere [Importare ed esportare pacchetti &#40;servizio SSIS&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="1278f-107">For more information, see [Import and Export Packages &#40;SSIS Service&#41;](../../2014/integration-services/import-and-export-packages-ssis-service.md).</span></span>  
  
 <span data-ttu-id="1278f-108">È inoltre possibile usare l'utilità della riga di comando **dtutil**per copiare un pacchetto dal file system al database msdb e viceversa.</span><span class="sxs-lookup"><span data-stu-id="1278f-108">You can also use a command prompt utility, **dtutil**, to copy a package between the file system and msdb.</span></span> <span data-ttu-id="1278f-109">Per altre informazioni, vedere [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="1278f-109">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
### <a name="to-save-a-package"></a><span data-ttu-id="1278f-110">Per salvare un pacchetto</span><span class="sxs-lookup"><span data-stu-id="1278f-110">To save a package</span></span>  
  
-   [<span data-ttu-id="1278f-111">Salvare un pacchetto nel file System</span><span class="sxs-lookup"><span data-stu-id="1278f-111">Save a Package to the File System</span></span>](../../2014/integration-services/save-a-package-to-the-file-system.md)  
  
-   [<span data-ttu-id="1278f-112">Salvataggio di una copia di un pacchetto</span><span class="sxs-lookup"><span data-stu-id="1278f-112">Save a Copy of a Package</span></span>](../../2014/integration-services/save-a-copy-of-a-package.md)  
  
  
