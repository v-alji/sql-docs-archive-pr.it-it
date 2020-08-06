---
title: Integration Services (SSIS) e ambienti Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- studio environments [Integration Services]
- tools [Integration Services], Business Intelligence Development Studio
- Business Intelligence Development Studio, Integration Services in
- SQL Server Management Studio [Integration Services]
- SSIS, studio environments
- SQL Server Integration Services, studio environments
- tools [Integration Services], SQL Server Management Studio
ms.assetid: 4eb73e65-d9f3-4ac6-a408-abfa85afc537
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfe0cf7ef482dce3870db8c730c597daf1d539e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628877"
---
# <a name="integration-services-ssis-and-studio-environments"></a><span data-ttu-id="82f2e-102">Integration Services (SSIS) e ambienti Studio</span><span class="sxs-lookup"><span data-stu-id="82f2e-102">Integration Services (SSIS) and Studio Environments</span></span>
  <span data-ttu-id="82f2e-103">In[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sono inclusi due strumenti per l'utilizzo di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="82f2e-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] includes two studios for working with [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] <span data-ttu-id="82f2e-104">per lo sviluppo di pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] richiesti da una soluzione aziendale.</span><span class="sxs-lookup"><span data-stu-id="82f2e-104">for developing the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages that a business solution requires.</span></span> <span data-ttu-id="82f2e-105">In[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] è disponibile il progetto di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in cui è possibile creare pacchetti.</span><span class="sxs-lookup"><span data-stu-id="82f2e-105">[!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project in which you create packages.</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="82f2e-106">per la gestione dei pacchetti in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="82f2e-106">for managing packages in a production environment.</span></span>  
  
## <a name="sql-server-data-tools"></a><span data-ttu-id="82f2e-107">SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="82f2e-107">SQL Server Data Tools</span></span>  
 <span data-ttu-id="82f2e-108">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]è possibile effettuare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="82f2e-108">Working in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="82f2e-109">Eseguire l'Importazione/Esportazione guidata di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] per creare pacchetti di base per la copia dei dati da un'origine a una destinazione.</span><span class="sxs-lookup"><span data-stu-id="82f2e-109">Run the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to create basic packages that copy data from a source to a destination.</span></span>  
  
-   <span data-ttu-id="82f2e-110">Creare pacchetti che includono complessi flussi di controllo, flussi di dati, logica guidata dagli eventi e funzionalità di registrazione.</span><span class="sxs-lookup"><span data-stu-id="82f2e-110">Create packages that include complex control flow, data flow, event-driven logic, and logging.</span></span>  
  
-   <span data-ttu-id="82f2e-111">Testare ed eseguire il debug dei pacchetti usando le funzionalità di monitoraggio e risoluzione dei problemi di Progettazione [!INCLUDE[ssIS](../includes/ssis-md.md)] e le funzionalità di debug di [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82f2e-111">Test and debug packages by using the troubleshooting and monitoring features in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, and the debugging features in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="82f2e-112">Creare configurazioni che aggiornano le proprietà e gli oggetti dei pacchetti in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="82f2e-112">Create configurations that update the properties of packages and package objects at run time.</span></span>  
  
-   <span data-ttu-id="82f2e-113">Creare un'utilità di distribuzione tramite cui installare i pacchetti e le relative dipendenze in altri computer.</span><span class="sxs-lookup"><span data-stu-id="82f2e-113">Create a deployment utility that can install packages and their dependencies on other computers.</span></span>  
  
-   <span data-ttu-id="82f2e-114">Salvare copie dei pacchetti nel database msdb di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], nell'archivio pacchetti di [!INCLUDE[ssIS](../includes/ssis-md.md)] e nel file system.</span><span class="sxs-lookup"><span data-stu-id="82f2e-114">Save copies of packages to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
 <span data-ttu-id="82f2e-115">Per altre informazioni su [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], vedere [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span><span class="sxs-lookup"><span data-stu-id="82f2e-115">For more information about [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], see [SQL Server Data Tools](https://msdn.microsoft.com/library/hh272686.aspx).</span></span>  
  
## <a name="sql-server-management-studio"></a><span data-ttu-id="82f2e-116">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="82f2e-116">SQL Server Management Studio</span></span>  
 <span data-ttu-id="82f2e-117">In[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] è disponibile il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] che consente di gestire pacchetti, monitorare i pacchetti in esecuzione e determinare l'impatto e la derivazione dei dati per gli oggetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="82f2e-117">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] provides the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that you use to manage packages, monitor running packages, and determine impact and data lineage for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] objects.</span></span>  
  
 <span data-ttu-id="82f2e-118">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]è possibile effettuare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="82f2e-118">Working in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], you can perform the following tasks:</span></span>  
  
-   <span data-ttu-id="82f2e-119">Creare cartelle per organizzare i pacchetti in modo utile all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="82f2e-119">Create folders to organize packages in a way that is meaningful to your organization.</span></span>  
  
-   <span data-ttu-id="82f2e-120">Eseguire pacchetti archiviati nel computer locale tramite l'Utilità di esecuzione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="82f2e-120">Run packages that are stored on the local computer by using the Execute Package utility.</span></span>  
  
-   <span data-ttu-id="82f2e-121">Eseguire l'Utilità di esecuzione pacchetti per generare una riga di comando da usare per l'esecuzione dell'utilità del prompt dei comandi **dtexec** (dtexec.exe).</span><span class="sxs-lookup"><span data-stu-id="82f2e-121">Run the Execute Package utility to generate a command line to use when you run the **dtexec** command prompt utility (dtexec.exe).</span></span>  
  
-   <span data-ttu-id="82f2e-122">Importare ed esportare pacchetti da e verso il database msdb di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], l'archivio pacchetti [!INCLUDE[ssIS](../includes/ssis-md.md)] e il file system.</span><span class="sxs-lookup"><span data-stu-id="82f2e-122">Import and export packages to and from the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database, the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, and the file system.</span></span>  
  
