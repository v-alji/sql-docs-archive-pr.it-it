---
title: Installare SQL Server 2014 in Server Core | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 1dd294cc-5b69-4d0c-9005-3e307b75678b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d2614c43bb763757db7db46b1c7a966221da96f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713464"
---
# <a name="install-sql-server-2014-on-server-core"></a><span data-ttu-id="dd877-102">Installare SQL Server 2014 in Server Core</span><span class="sxs-lookup"><span data-stu-id="dd877-102">Install SQL Server 2014 on Server Core</span></span>
  <span data-ttu-id="dd877-103">È possibile installare [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un'installazione Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-103">You can install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="dd877-104">In questo argomento vengono fornite informazioni dettagliate specifiche dell'installazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in Server Core.</span><span class="sxs-lookup"><span data-stu-id="dd877-104">This topic provides setup-specific details for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core.</span></span>  
  
 <span data-ttu-id="dd877-105">L'opzione di installazione Server Core per il sistema operativo [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] offre un ambiente minimo per l'esecuzione di ruoli del server specifici.</span><span class="sxs-lookup"><span data-stu-id="dd877-105">The Server Core installation option for the [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] operating system provides a minimal environment for running specific server roles.</span></span> <span data-ttu-id="dd877-106">Ciò consente di ridurre i requisiti di manutenzione e gestione e la superficie di attacco per i ruoli del server in questione.</span><span class="sxs-lookup"><span data-stu-id="dd877-106">This helps to reduce maintenance and management requirements and the attack surface for those server roles.</span></span> <span data-ttu-id="dd877-107">Per ulteriori informazioni sull'implementazione di Server Core in [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] , vedere [Server Core per Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) ( https://go.microsoft.com/fwlink/?LinkId=202439) .</span><span class="sxs-lookup"><span data-stu-id="dd877-107">For more information on Server Core as implemented on [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)], see [Server Core for Windows Server 2008 R2](https://go.microsoft.com/fwlink/?LinkId=202439) (https://go.microsoft.com/fwlink/?LinkId=202439).</span></span> <span data-ttu-id="dd877-108">Per altre informazioni sull'implementazione di Server Core in [!INCLUDE[win8srv](../../includes/win8srv-md.md)], vedere [Server Core for Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx) (Server Core per Windows Server 2012).</span><span class="sxs-lookup"><span data-stu-id="dd877-108">For more information on Server Core as implemented on [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Server Core for Windows Server 2012](https://msdn.microsoft.com/library/hh846323\(VS.85\).aspx) (https://msdn.microsoft.com/library/hh846323(VS.85).aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dd877-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="dd877-109">Prerequisites</span></span>  
  
|<span data-ttu-id="dd877-110">Requisito</span><span class="sxs-lookup"><span data-stu-id="dd877-110">Requirement</span></span>|<span data-ttu-id="dd877-111">Modalità di installazione</span><span class="sxs-lookup"><span data-stu-id="dd877-111">How to install</span></span>|  
|-----------------|--------------------|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="dd877-112">2.0 SP2</span><span class="sxs-lookup"><span data-stu-id="dd877-112">2.0 SP2</span></span>|<span data-ttu-id="dd877-113">Incluso in installazioni Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-113">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span> <span data-ttu-id="dd877-114">Se non è abilitato, per impostazione predefinita viene abilitato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="dd877-114">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="dd877-115">Non è possibile eseguire le versioni 2.0, 3.0 e 3.5 side-by-side in un computer.</span><span class="sxs-lookup"><span data-stu-id="dd877-115">It is not possible to run versions 2.0, 3.0, and 3.5 side by side on a computer.</span></span> <span data-ttu-id="dd877-116">Durante l'installazione di .NET Framework 3.5 SP1 si ottengono automaticamente i livelli 2.0 e 3.0.</span><span class="sxs-lookup"><span data-stu-id="dd877-116">When you install the .NET Framework 3.5 SP1, you get the 2.0 and 3.0 layers automatically.</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="dd877-117">3.5 SP1 Full Profile</span><span class="sxs-lookup"><span data-stu-id="dd877-117">3.5 SP1 Full Profile</span></span>|<span data-ttu-id="dd877-118">Incluso in installazioni Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span><span class="sxs-lookup"><span data-stu-id="dd877-118">Included in Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1.</span></span> <span data-ttu-id="dd877-119">Se non è abilitato, per impostazione predefinita viene abilitato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="dd877-119">If it is not enabled, Setup enables it by default.</span></span><br /><br /> <span data-ttu-id="dd877-120">In un computer con sistema operativo Windows Server, è necessario scaricare e installare .NET Framework 3.5 SP1 prima di eseguire il programma di installazione per installare i componenti dipendenti da .NET 3.5 SP1.</span><span class="sxs-lookup"><span data-stu-id="dd877-120">On a computer with Windows server operating system you must download and install .NET Framework 3.5 SP1 before you run Setup, to install components dependent on .NET 3.5 SP1.</span></span><br /><br /> <span data-ttu-id="dd877-121">Per ulteriori informazioni sui suggerimenti e indicazioni su come acquisire e abilitare .NET Framework 3,5 in [!INCLUDE[win8srv](../../includes/win8srv-md.md)] , vedere Considerazioni sulla [distribuzione di Microsoft .NET Framework 3,5](https://msdn.microsoft.com/library/windows/hardware/hh975396) ( https://msdn.microsoft.com/library/windows/hardware/hh975396) .</span><span class="sxs-lookup"><span data-stu-id="dd877-121">For more information about the recommendations and guidance on how to acquire and enable .NET Framework 3.5 in [!INCLUDE[win8srv](../../includes/win8srv-md.md)], see [Microsoft .NET Framework 3.5 Deployment Considerations](https://msdn.microsoft.com/library/windows/hardware/hh975396) (https://msdn.microsoft.com/library/windows/hardware/hh975396).</span></span>|  
|[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <span data-ttu-id="dd877-122">4 Server Core Profile</span><span class="sxs-lookup"><span data-stu-id="dd877-122">4 Server Core Profile</span></span>|<span data-ttu-id="dd877-123">Per tutte le edizioni di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , ad eccezione di [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], uno dei prerequisiti di installazione prevede l'installazione di [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile.</span><span class="sxs-lookup"><span data-stu-id="dd877-123">For all editions of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] except [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)], Setup installs the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile as a prerequisite.</span></span><br /><br /> <span data-ttu-id="dd877-124">Per [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)] , scaricare il [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] profilo 4 server core da [Microsoft .NET Framework 4 (programma di installazione autonomo) per Server Core](https://www.microsoft.com/download/details.aspx?id=17718) ( https://www.microsoft.com/download/details.aspx?id=17718) e installarlo prima di procedere con l'installazione.</span><span class="sxs-lookup"><span data-stu-id="dd877-124">For [!INCLUDE[ssExpressEd11](../../includes/ssexpressed11-md.md)], download the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] 4 Server Core Profile from [Microsoft .NET Framework 4 (Standalone Installer) for Server Core](https://www.microsoft.com/download/details.aspx?id=17718) (https://www.microsoft.com/download/details.aspx?id=17718), and install it before you proceed with the setup.</span></span>|  
|<span data-ttu-id="dd877-125">Windows Installer 4.5</span><span class="sxs-lookup"><span data-stu-id="dd877-125">Windows Installer 4.5</span></span>|<span data-ttu-id="dd877-126">Fornito con installazioni Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-126">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
|<span data-ttu-id="dd877-127">Windows PowerShell 2.0</span><span class="sxs-lookup"><span data-stu-id="dd877-127">Windows PowerShell 2.0</span></span>|<span data-ttu-id="dd877-128">Fornito con installazioni Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-128">Shipped with Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>|  
  
##  <a name="supported-features"></a><a name="BK_SupportedFeatures"></a> <span data-ttu-id="dd877-129">Funzionalità supportate</span><span class="sxs-lookup"><span data-stu-id="dd877-129">Supported Features</span></span>  
 <span data-ttu-id="dd877-130">Utilizzare la tabella seguente per identificare le funzionalità supportate in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in un'installazione Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-130">Use the following table to find which features are supported in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|<span data-ttu-id="dd877-131">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="dd877-131">Feature</span></span>|<span data-ttu-id="dd877-132">Supportato</span><span class="sxs-lookup"><span data-stu-id="dd877-132">Supported</span></span>|  
|-------------|---------------|  
|<span data-ttu-id="dd877-133">Servizi[!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd877-133">[!INCLUDE[ssDE](../../includes/ssde-md.md)] Services</span></span>|<span data-ttu-id="dd877-134">Sì</span><span class="sxs-lookup"><span data-stu-id="dd877-134">Yes</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dd877-135">Replica</span><span class="sxs-lookup"><span data-stu-id="dd877-135">Replication</span></span>|<span data-ttu-id="dd877-136">Sì</span><span class="sxs-lookup"><span data-stu-id="dd877-136">Yes</span></span>|  
|<span data-ttu-id="dd877-137">Ricerca full-text</span><span class="sxs-lookup"><span data-stu-id="dd877-137">Full Text Search</span></span>|<span data-ttu-id="dd877-138">Sì</span><span class="sxs-lookup"><span data-stu-id="dd877-138">Yes</span></span>|  
|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]|<span data-ttu-id="dd877-139">Sì</span><span class="sxs-lookup"><span data-stu-id="dd877-139">Yes</span></span>|  
|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|<span data-ttu-id="dd877-140">No</span><span class="sxs-lookup"><span data-stu-id="dd877-140">No</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="dd877-141">Data Tools (SSDT)</span><span class="sxs-lookup"><span data-stu-id="dd877-141">Data Tools (SSDT)</span></span>|<span data-ttu-id="dd877-142">No</span><span class="sxs-lookup"><span data-stu-id="dd877-142">No</span></span>|  
|<span data-ttu-id="dd877-143">Connettività strumenti client</span><span class="sxs-lookup"><span data-stu-id="dd877-143">Client Tools Connectivity</span></span>|<span data-ttu-id="dd877-144">Sì</span><span class="sxs-lookup"><span data-stu-id="dd877-144">Yes</span></span>|  
|<span data-ttu-id="dd877-145">Server Integration Services<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="dd877-145">Integration Services Server<sup>[1]</sup></span></span>|<span data-ttu-id="dd877-146">Sì</span><span class="sxs-lookup"><span data-stu-id="dd877-146">Yes</span></span>|  
|<span data-ttu-id="dd877-147">Compatibilità con le versioni precedenti di strumenti client.</span><span class="sxs-lookup"><span data-stu-id="dd877-147">Client Tools Backward Compatibility</span></span>|<span data-ttu-id="dd877-148">No</span><span class="sxs-lookup"><span data-stu-id="dd877-148">No</span></span>|  
|<span data-ttu-id="dd877-149">SDK di strumenti client</span><span class="sxs-lookup"><span data-stu-id="dd877-149">Client Tools SDK</span></span>|<span data-ttu-id="dd877-150">No</span><span class="sxs-lookup"><span data-stu-id="dd877-150">No</span></span>|  
|<span data-ttu-id="dd877-151">Documentazione online di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd877-151">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online</span></span>|<span data-ttu-id="dd877-152">No</span><span class="sxs-lookup"><span data-stu-id="dd877-152">No</span></span>|  
|<span data-ttu-id="dd877-153">Strumenti di gestione - Di base</span><span class="sxs-lookup"><span data-stu-id="dd877-153">Management Tools - Basic</span></span>|<span data-ttu-id="dd877-154">Solo remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="dd877-154">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="dd877-155">Strumenti di gestione - Completa</span><span class="sxs-lookup"><span data-stu-id="dd877-155">Management Tools - Complete</span></span>|<span data-ttu-id="dd877-156">Solo remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="dd877-156">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="dd877-157">Controller di Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="dd877-157">Distributed Replay Controller</span></span>|<span data-ttu-id="dd877-158">No</span><span class="sxs-lookup"><span data-stu-id="dd877-158">No</span></span>|  
|<span data-ttu-id="dd877-159">Client Riesecuzione distribuita</span><span class="sxs-lookup"><span data-stu-id="dd877-159">Distributed Replay Client</span></span>|<span data-ttu-id="dd877-160">Solo remoto<sup>[2]</sup></span><span class="sxs-lookup"><span data-stu-id="dd877-160">Remote Only<sup>[2]</sup></span></span>|  
|<span data-ttu-id="dd877-161">SDK di Connettività SQL Client</span><span class="sxs-lookup"><span data-stu-id="dd877-161">SQL Client Connectivity SDK</span></span>|<span data-ttu-id="dd877-162">Sì</span><span class="sxs-lookup"><span data-stu-id="dd877-162">Yes</span></span>|  
|<span data-ttu-id="dd877-163">Microsoft Sync Framework</span><span class="sxs-lookup"><span data-stu-id="dd877-163">Microsoft Sync Framework</span></span>|<span data-ttu-id="dd877-164">Sì<sup>[3]</sup></span><span class="sxs-lookup"><span data-stu-id="dd877-164">Yes<sup>[3]</sup></span></span>|  
|[!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)]|<span data-ttu-id="dd877-165">No</span><span class="sxs-lookup"><span data-stu-id="dd877-165">No</span></span>|  
|[!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)]|<span data-ttu-id="dd877-166">No</span><span class="sxs-lookup"><span data-stu-id="dd877-166">No</span></span>|  
  
 <span data-ttu-id="dd877-167"><sup>[1]</sup> Per ulteriori informazioni sul nuovo server Integration Services e sulle relative funzionalità in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , vedere [Integration Services &#40;server SSIS&#41;](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="dd877-167"><sup>[1]</sup>For more information about the new Integration Services Server and its features in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], see [Integration Services &#40;SSIS&#41; Server](../../integration-services/catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="dd877-168"><sup>[2]</sup> L'installazione di queste funzionalità in Server Core non è supportata.</span><span class="sxs-lookup"><span data-stu-id="dd877-168"><sup>[2]</sup>Installation of these features on Server Core is not supported.</span></span> <span data-ttu-id="dd877-169">Questi componenti possono essere installati in un server diverso da [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core e connessi ai servizi del [!INCLUDE[ssDE](../../includes/ssde-md.md)] installati in Server Core.</span><span class="sxs-lookup"><span data-stu-id="dd877-169">These components can be installed on a different server that is not [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, and connected to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] services installed on Server Core.</span></span>  
  
 <span data-ttu-id="dd877-170"><sup>[3]</sup> Microsoft Sync Framework non è incluso nel [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] pacchetto di installazione.</span><span class="sxs-lookup"><span data-stu-id="dd877-170"><sup>[3]</sup>Microsoft Sync Framework is not included in the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation package.</span></span> <span data-ttu-id="dd877-171">È possibile scaricare la versione appropriata di Sync Framework dall' [area download Microsoft](https://go.microsoft.com/fwlink/?LinkId=221788) ( https://go.microsoft.com/fwlink/?LinkId=221788) pagina e installarla in un computer che esegue l'installazione Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd877-171">You can download the appropriate version of Sync Framework from this [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=221788) (https://go.microsoft.com/fwlink/?LinkId=221788) page and install it on a computer that is running Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
## <a name="supported-scenario-matrix"></a><span data-ttu-id="dd877-172">Matrice di scenario supportata</span><span class="sxs-lookup"><span data-stu-id="dd877-172">Supported Scenario Matrix</span></span>  
 <span data-ttu-id="dd877-173">Nella tabella seguente viene illustrata la matrice di scenario supportata per l'installazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in un'installazione Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 e [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-173">The following table shows the supported scenario matrix for installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 and [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd877-174">Edizioni di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd877-174">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] editions</span></span>|<span data-ttu-id="dd877-175">Tutte le [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] edizioni a 64 bit<sup>[1]</sup></span><span class="sxs-lookup"><span data-stu-id="dd877-175">All [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 64-bit editions<sup>[1]</sup></span></span>|  
|<span data-ttu-id="dd877-176">Lingua di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd877-176">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] language</span></span>|<span data-ttu-id="dd877-177">Tutte le lingue</span><span class="sxs-lookup"><span data-stu-id="dd877-177">All languages</span></span>|  
|<span data-ttu-id="dd877-178">Lingua di[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nella combinazione lingua/impostazioni locali del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="dd877-178">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] language on OS language/locale (combination)</span></span>|<span data-ttu-id="dd877-179">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in lingua inglese nel sistema operativo Windows il lingua giapponese</span><span class="sxs-lookup"><span data-stu-id="dd877-179">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on JPN (Japanese) Windows</span></span><br /><br /> <span data-ttu-id="dd877-180">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in lingua inglese nel sistema operativo Windows in lingua tedesca</span><span class="sxs-lookup"><span data-stu-id="dd877-180">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on GER (German) Windows</span></span><br /><br /> <span data-ttu-id="dd877-181">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in lingua inglese nel sistema operativo Windows in lingua cinese (Cina)</span><span class="sxs-lookup"><span data-stu-id="dd877-181">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on CHS (Chinese-China) Windows</span></span><br /><br /> <span data-ttu-id="dd877-182">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in lingua inglese nel sistema operativo Windows in lingua araba (Arabia Saudita)</span><span class="sxs-lookup"><span data-stu-id="dd877-182">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ARA (Arabic (SA)) Windows</span></span><br /><br /> <span data-ttu-id="dd877-183">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in lingua inglese nel sistema operativo Windows in lingua tailandese (Thai)</span><span class="sxs-lookup"><span data-stu-id="dd877-183">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on THA (Thai) Windows</span></span><br /><br /> <span data-ttu-id="dd877-184">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in lingua inglese nel sistema operativo Windows in lingua turca</span><span class="sxs-lookup"><span data-stu-id="dd877-184">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on TRK (Turkish) Windows</span></span><br /><br /> <span data-ttu-id="dd877-185">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in lingua inglese nel sistema operativo Windows in lingua portoghese (Portogallo)</span><span class="sxs-lookup"><span data-stu-id="dd877-185">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on pt-PT (Portuguese Portugal) Windows</span></span><br /><br /> <span data-ttu-id="dd877-186">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in lingua inglese nel sistema operativo Windows in lingua inglese</span><span class="sxs-lookup"><span data-stu-id="dd877-186">ENG [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on ENG (English) Windows</span></span>|  
|<span data-ttu-id="dd877-187">Edizione di Windows</span><span class="sxs-lookup"><span data-stu-id="dd877-187">Windows edition</span></span>|[!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="dd877-188">64 bit x64 Datacenter</span><span class="sxs-lookup"><span data-stu-id="dd877-188">64-bit x64 Datacenter</span></span><br /><br /> [!INCLUDE[win8srv](../../includes/win8srv-md.md)] <span data-ttu-id="dd877-189">64 bit x64 Standard</span><span class="sxs-lookup"><span data-stu-id="dd877-189">64-bit x64 Standard</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="dd877-190">SP1 64 bit x64 Data Center Server Core</span><span class="sxs-lookup"><span data-stu-id="dd877-190">SP1 64-bit x64 Data Center Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="dd877-191">SP1 64 bit x64 Enterprise Server Core</span><span class="sxs-lookup"><span data-stu-id="dd877-191">SP1 64-bit x64 Enterprise Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="dd877-192">SP1 64 bit x64 Standard Server Core</span><span class="sxs-lookup"><span data-stu-id="dd877-192">SP1 64-bit x64 Standard Server Core</span></span><br /><br /> [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] <span data-ttu-id="dd877-193">SP1 64 bit x64 Web Server Core</span><span class="sxs-lookup"><span data-stu-id="dd877-193">SP1 64-bit x64 Web Server Core</span></span>|  
  
 <span data-ttu-id="dd877-194"><sup>[1]</sup> L'installazione della versione a 32 bit delle [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] edizioni di non è supportata in Server Core.</span><span class="sxs-lookup"><span data-stu-id="dd877-194"><sup>[1]</sup>Installing the 32-bit version of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] editions is not supported on Server Core.</span></span>  
  
## <a name="upgrading"></a><span data-ttu-id="dd877-195">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="dd877-195">Upgrading</span></span>  
 <span data-ttu-id="dd877-196">Nelle installazioni Server Core è supportato l'aggiornamento da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] a [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd877-196">On Server Core installations, upgrading from [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] to [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is supported.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="dd877-197">Installazione</span><span class="sxs-lookup"><span data-stu-id="dd877-197">Installation</span></span>  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="dd877-198">non supporta l'installazione tramite apposita procedura guidata nel sistema operativo Server Core.</span><span class="sxs-lookup"><span data-stu-id="dd877-198">does not support setup by using the installation wizard on the Server Core operating system.</span></span> <span data-ttu-id="dd877-199">In caso di installazione in Server Core, il programma di installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prevede il supporto della modalità non interattiva completa tramite il parametro /Q o della modalità non interattiva semplice tramite il parametro /QS.</span><span class="sxs-lookup"><span data-stu-id="dd877-199">When installing on Server Core, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup supports full quiet mode by using the /Q parameter, or Quiet Simple mode by using the /QS parameter.</span></span> <span data-ttu-id="dd877-200">Per altre informazioni, vedere [Installare SQL Server 2014 dal prompt dei comandi](install-sql-server-from-the-command-prompt.md).</span><span class="sxs-lookup"><span data-stu-id="dd877-200">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="dd877-201">Non è possibile eseguire l'installazione side-by-side di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] con le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un computer che esegue [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span><span class="sxs-lookup"><span data-stu-id="dd877-201">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] cannot be installed side-by-side with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span></span>  
  
 <span data-ttu-id="dd877-202">Indipendentemente dal metodo di installazione, è necessario confermare l'accettazione delle condizioni di licenza del software come utente singolo o per conto di un'entità, a meno che l'utilizzo del software non sia disciplinato da un contratto separato, ad esempio un contratto multilicenza [!INCLUDE[msCoName](../../includes/msconame-md.md)] o un contratto di terze parti con un fornitore di software indipendente o un OEM.</span><span class="sxs-lookup"><span data-stu-id="dd877-202">Regardless of the installation method, you are required to confirm acceptance of the software license terms as an individual or on behalf of an entity, unless your use of the software is governed by a separate agreement such as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing agreement or a third-party agreement with an ISV or OEM.</span></span>  
  
 <span data-ttu-id="dd877-203">Le condizioni di licenza vengono visualizzate per la revisione e l'accettazione nell'interfaccia utente del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="dd877-203">The license terms are displayed for review and acceptance in the Setup user interface.</span></span> <span data-ttu-id="dd877-204">Le installazioni automatiche che utilizzano i parametri /Q o /QS devono includere il parametro /IACCEPTSQLSERVERLICENSETERMS.</span><span class="sxs-lookup"><span data-stu-id="dd877-204">Unattended installations (using the /Q or /QS parameters) must include the /IACCEPTSQLSERVERLICENSETERMS parameter.</span></span> <span data-ttu-id="dd877-205">È possibile esaminare separatamente le condizioni di licenza alla pagina relativa alle [condizioni di licenza software Microsoft](https://go.microsoft.com/fwlink/?LinkId=148209).</span><span class="sxs-lookup"><span data-stu-id="dd877-205">You can review the license terms separately at [Microsoft Software License Terms](https://go.microsoft.com/fwlink/?LinkId=148209).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd877-206">A seconda della modalità di ricezione del software, ad esempio attraverso un contratto multilicenza [!INCLUDE[msCoName](../../includes/msconame-md.md)] , l'utilizzo del software potrebbe essere soggetto a condizioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="dd877-206">Depending on how you received the software (for example, through [!INCLUDE[msCoName](../../includes/msconame-md.md)] volume licensing), your use of the software may be subject to additional terms and conditions.</span></span>  
  
 <span data-ttu-id="dd877-207">Per installare funzionalità specifiche, utilizzare il parametro /FEATURES e specificare la funzionalità padre oppure i valori delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="dd877-207">To install specific features, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="dd877-208">Per ulteriori informazioni sui parametri delle funzionalità e sul relativo utilizzo, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="dd877-208">For more information about feature parameters and their use, see the following sections.</span></span>  
  
### <a name="feature-parameters"></a><span data-ttu-id="dd877-209">Parametri delle funzionalità</span><span class="sxs-lookup"><span data-stu-id="dd877-209">Feature Parameters</span></span>  
  
|<span data-ttu-id="dd877-210">Parametro della funzionalità</span><span class="sxs-lookup"><span data-stu-id="dd877-210">Feature parameter</span></span>|<span data-ttu-id="dd877-211">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd877-211">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="dd877-212">SQLENGINE</span><span class="sxs-lookup"><span data-stu-id="dd877-212">SQLENGINE</span></span>|<span data-ttu-id="dd877-213">Viene installato solo il [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-213">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="dd877-214">REPLICA</span><span class="sxs-lookup"><span data-stu-id="dd877-214">REPLICATION</span></span>|<span data-ttu-id="dd877-215">Viene installato il componente di replica insieme al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-215">Installs the Replication component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="dd877-216">FULLTEXT</span><span class="sxs-lookup"><span data-stu-id="dd877-216">FULLTEXT</span></span>|<span data-ttu-id="dd877-217">Viene installato il componente FullText insieme al [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-217">Installs the FullText component along with [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="dd877-218">AS</span><span class="sxs-lookup"><span data-stu-id="dd877-218">AS</span></span>|<span data-ttu-id="dd877-219">Vengono installati tutti i componenti di [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd877-219">Installs all [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="dd877-220">IS</span><span class="sxs-lookup"><span data-stu-id="dd877-220">IS</span></span>|<span data-ttu-id="dd877-221">Vengono installati tutti i componenti di [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd877-221">Installs all [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components.</span></span>|  
|<span data-ttu-id="dd877-222">CONN</span><span class="sxs-lookup"><span data-stu-id="dd877-222">CONN</span></span>|<span data-ttu-id="dd877-223">Vengono installati i componenti di connettività.</span><span class="sxs-lookup"><span data-stu-id="dd877-223">Installs the connectivity components.</span></span>|  
  
 <span data-ttu-id="dd877-224">Vedere l'esempio seguente relativo all'utilizzo di parametri delle funzionalità:</span><span class="sxs-lookup"><span data-stu-id="dd877-224">See the following examples of the usage of feature parameters:</span></span>  
  
|<span data-ttu-id="dd877-225">Parametro e valori</span><span class="sxs-lookup"><span data-stu-id="dd877-225">Parameter and values</span></span>|<span data-ttu-id="dd877-226">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd877-226">Description</span></span>|  
|--------------------------|-----------------|  
|<span data-ttu-id="dd877-227">/FEATURES=SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dd877-227">/FEATURES=SQLEngine</span></span>|<span data-ttu-id="dd877-228">Viene installato solo il [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-228">Installs only the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>|  
|<span data-ttu-id="dd877-229">/FEATURES=SQLEngine,FullText</span><span class="sxs-lookup"><span data-stu-id="dd877-229">/FEATURES=SQLEngine,FullText</span></span>|<span data-ttu-id="dd877-230">Installa il [!INCLUDE[ssDE](../../includes/ssde-md.md)] e il componente full-text.</span><span class="sxs-lookup"><span data-stu-id="dd877-230">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and full-text.</span></span>|  
|<span data-ttu-id="dd877-231">/FEATURES=SQLEngine,Conn</span><span class="sxs-lookup"><span data-stu-id="dd877-231">/FEATURES=SQLEngine,Conn</span></span>|<span data-ttu-id="dd877-232">Vengono installati il [!INCLUDE[ssDE](../../includes/ssde-md.md)] e i componenti di connettività.</span><span class="sxs-lookup"><span data-stu-id="dd877-232">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)] and the connectivity components.</span></span>|  
|<span data-ttu-id="dd877-233">/FEATURES=SQLEngine,AS,IS,Conn</span><span class="sxs-lookup"><span data-stu-id="dd877-233">/FEATURES=SQLEngine,AS,IS,Conn</span></span>|<span data-ttu-id="dd877-234">Vengono installati il [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]e i componenti di connettività.</span><span class="sxs-lookup"><span data-stu-id="dd877-234">Installs the [!INCLUDE[ssDE](../../includes/ssde-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], and the connectivity components.</span></span>|  
  
### <a name="installation-options"></a><span data-ttu-id="dd877-235">Opzione di installazione</span><span class="sxs-lookup"><span data-stu-id="dd877-235">Installation Options</span></span>  
 <span data-ttu-id="dd877-236">Il programma di installazione supporta le seguenti opzioni di installazione durante l'installazione di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in un sistema operativo Server Core:</span><span class="sxs-lookup"><span data-stu-id="dd877-236">The Setup supports the following installation options while installing [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on a Server Core operating system:</span></span>  
  
1.  <span data-ttu-id="dd877-237">**Installazione dalla riga di comando**</span><span class="sxs-lookup"><span data-stu-id="dd877-237">**Installation from Command Line**</span></span>  
  
     <span data-ttu-id="dd877-238">Per installare funzionalità specifiche tramite l'opzione di installazione del prompt dei comandi, utilizzare il parametro /FEATURES e specificare la funzionalità padre o i valori delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="dd877-238">To install specific features using the command prompt installation option, use the /FEATURES parameter and specify the parent feature or feature values.</span></span> <span data-ttu-id="dd877-239">Di seguito è riportato un esempio di utilizzo dei parametri dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dd877-239">The following is an example of using the parameters from the command line:</span></span>  
  
    ```cmd
    setup.exe /qs /ACTION=Install /FEATURES=SQLEngine,Replication /INSTANCENAME=MSSQLSERVER /SQLSVCACCOUNT="<DomainName\UserName>" /SQLSVCPASSWORD="<StrongPassword>" /SQLSYSADMINACCOUNTS="<DomainName\UserName>" /AGTSVCACCOUNT="NT AUTHORITY\Network Service" /TCPENABLED=1 /IACCEPTSQLSERVERLICENSETERMS  
    ```  
  
2.  <span data-ttu-id="dd877-240">**Installazione tramite il file di configurazione**</span><span class="sxs-lookup"><span data-stu-id="dd877-240">**Installation using Configuration File**</span></span>  
  
     <span data-ttu-id="dd877-241">Il programma di installazione supporta l'utilizzo del file di configurazione solo tramite il prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="dd877-241">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="dd877-242">Il file di configurazione è un file di testo con la struttura di base di un parametro (coppia nome/valore) e un commento descrittivo.</span><span class="sxs-lookup"><span data-stu-id="dd877-242">The configuration file is a text file with the basic structure of a parameter (name/value pair) and a descriptive comment.</span></span> <span data-ttu-id="dd877-243">L'estensione del file di configurazione specificato al prompt dei comandi deve essere INI.</span><span class="sxs-lookup"><span data-stu-id="dd877-243">The configuration file specified at the command prompt should have an .INI file name extension.</span></span> <span data-ttu-id="dd877-244">Vedere gli esempi di ConfigurationFile.INI seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd877-244">See the following examples of ConfigurationFile.INI:</span></span>  
  
    -   <span data-ttu-id="dd877-245">Installazione del [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd877-245">Installing [!INCLUDE[ssDE](../../includes/ssde-md.md)]</span></span>  
  
         <span data-ttu-id="dd877-246">L'esempio seguente illustra come installare una nuova istanza autonoma che include il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dd877-246">The following example shows how to install a new stand-alone instance that includes the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)]:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine, and Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Accept the License agreement to continue with Installation  
  
        IAcceptSQLServerLicenseTerms="True"
        ```  
  
    -   <span data-ttu-id="dd877-247">Installazione dei componenti di connettività</span><span class="sxs-lookup"><span data-stu-id="dd877-247">Installing connectivity components</span></span>  
  
         <span data-ttu-id="dd877-248">Nell'esempio seguente viene illustrato come installare i componenti di connettività.</span><span class="sxs-lookup"><span data-stu-id="dd877-248">The following example shows how to install the connectivity components:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=Conn  
  
        ; Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True
        ```  
  
    -   <span data-ttu-id="dd877-249">Installazione di tutte le funzionalità supportate</span><span class="sxs-lookup"><span data-stu-id="dd877-249">Installing all supported features</span></span>  
  
         <span data-ttu-id="dd877-250">Nell'esempio seguente viene illustrato come installare tutte le funzionalità di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] supportate in Server Core.</span><span class="sxs-lookup"><span data-stu-id="dd877-250">The following example shows how to install all supported features of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] on Server Core:</span></span>  
  
        ```  
        ; ssNoVersion Configuration File  
        [OPTIONS]  
        ; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE. This is a required parameter.   
  
        ACTION="Install"  
  
        ; Specifies features to install, uninstall, or upgrade. The lists of features include SQLEngine, FullText, Replication, AS, IS, and Conn.   
  
        FEATURES=SQLENGINE,FullText,Replication,AS,IS,Conn  
  
        ; Specify a default or named instance. MSSQLSERVER is the default instance for non-Express editions and SQLExpress for Express editions. This parameter is required when installing the ssNoVersion Database Engine (SQL), or Analysis Services (AS).  
  
        INSTANCENAME="MSSQLSERVER"  
  
        ; Specify the Instance ID for the ssNoVersion features you have specified. ssNoVersion directory structure, registry structure, and service names will incorporate the instance ID of the ssNoVersion instance.   
  
        INSTANCEID="MSSQLSERVER"  
  
        ; Account for ssNoVersion service: Domain\User or system account.   
  
        SQLSVCACCOUNT="NT Service\MSSQLSERVER"  
  
        ; Windows account(s) to provision as ssNoVersion system administrators.   
  
        SQLSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; The name of the account that the Analysis Services service runs under.   
  
        ASSVCACCOUNT= "NT Service\MSSQLServerOLAPService"  
  
        ; Specifies the list of administrator accounts that need to be provisioned.   
  
        ASSYSADMINACCOUNTS="<DomainName\UserName>"  
  
        ; Specifies the server mode of the Analysis Services instance. Valid values are MULTIDIMENSIONAL, POWERPIVOT or TABULAR. ASSERVERMODE is case-sensitive. All values must be expressed in upper case.   
  
        ASSERVERMODE="MULTIDIMENSIONAL"  
  
        ; Optional value, which specifies the state of the TCP protocol for the ssNoVersion service. Supported values are: 0 to disable the TCP protocol, and 1 to enable the TCP protocol.  
  
        TCPENABLED=1  
  
        ;Specifies acceptance of License Terms  
  
        IAcceptSQLServerLicenseTerms="True"  
        ```  
  
     <span data-ttu-id="dd877-251">Negli esempi seguenti è illustrato come avviare il programma di installazione usando un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dd877-251">The following examples show how you can launch the Setup using a configuration file.</span></span>  
  
    -   <span data-ttu-id="dd877-252">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="dd877-252">Configuration file</span></span>  
  
         <span data-ttu-id="dd877-253">Di seguito sono riportati alcuni esempi di utilizzo del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="dd877-253">Following are some examples of how to use the configuration file:</span></span>  
  
        -   <span data-ttu-id="dd877-254">Per specificare il file di configurazione al prompt dei comandi:</span><span class="sxs-lookup"><span data-stu-id="dd877-254">To specify the configuration file at the command prompt:</span></span>  
  
        ```cmd
        setup.exe /QS /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
        -   <span data-ttu-id="dd877-255">Per specificare le password al prompt dei comandi anziché nel file di configurazione:</span><span class="sxs-lookup"><span data-stu-id="dd877-255">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
        ```cmd
        setup.exe /QS /SQLSVCPASSWORD="************" /ASSVCPASSWORD="************"  /ConfigurationFile=MyConfigurationFile.INI  
        ```  
  
    -   <span data-ttu-id="dd877-256">DefaultSetup.ini</span><span class="sxs-lookup"><span data-stu-id="dd877-256">DefaultSetup.ini</span></span>  
  
         <span data-ttu-id="dd877-257">Se il file DefaultSetup.ini si trova nelle cartelle \x86 e \x64, al livello radice dei supporti di origine di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , aprirlo e aggiungere il parametro *Features* al file.</span><span class="sxs-lookup"><span data-stu-id="dd877-257">If you have the DefaultSetup.ini file in the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media, open the DefaultSetup.ini file, and then add the *Features* parameter to the file.</span></span>  
  
         <span data-ttu-id="dd877-258">Se il file DefaultSetup.ini non esiste, è possibile crearlo e copiarlo nelle cartelle \x86 e \x64, al livello radice dei supporti di origine di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="dd877-258">If the DefaultSetup.ini file does not exist, you can create it and copy it to the \x86 and \x64 folders at the root level of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source media.</span></span>  
  
## <a name="configuring-remote-access-of-ssnoversion-running-on-server-core"></a><span data-ttu-id="dd877-259">Configurazione dell'accesso remoto di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione in Server Core</span><span class="sxs-lookup"><span data-stu-id="dd877-259">Configuring Remote Access of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Running on Server Core</span></span>  
 <span data-ttu-id="dd877-260">Eseguire le azioni descritte di seguito per configurare l'accesso remoto di un'istanza di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in esecuzione in un'installazione Server Core di [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-260">Perform the actions described below to configure remote access of a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] instance that is running on a Server Core installation of [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)].</span></span>  
  
### <a name="enable-remote-connections-on-the-instance-of-ssnoversion"></a><span data-ttu-id="dd877-261">Abilitare connessioni remote nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd877-261">Enable remote connections on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="dd877-262">Per abilitare connessioni remote, utilizzare in locale SQLCMD.exe ed eseguire le istruzioni seguenti nell'istanza Server Core:</span><span class="sxs-lookup"><span data-stu-id="dd877-262">To enable remote connections, use SQLCMD.exe locally and execute the following statements against the Server Core instance:</span></span>  
  
-   `EXEC sys.sp_configure N'remote access', N'1'`  
  
     `GO`  
  
-   `RECONFIGURE WITH OVERRIDE`  
  
     `GO`  
  
### <a name="enable-and-start-the-ssnoversion-browser-service"></a><span data-ttu-id="dd877-263">Abilitare e avviare il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser</span><span class="sxs-lookup"><span data-stu-id="dd877-263">Enable and start the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service</span></span>  
 <span data-ttu-id="dd877-264">Per impostazione predefinita, il servizio Browser è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="dd877-264">By default, the Browser service is disabled.</span></span>  <span data-ttu-id="dd877-265">Se risulta disabilitato in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in esecuzione in Server Core, eseguire il comando riportato di seguito dal prompt dei comandi per abilitarlo:</span><span class="sxs-lookup"><span data-stu-id="dd877-265">If it is disabled on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] running on Server Core, run the following command from the command prompt to enable it:</span></span>  
  
 `sc config SQLBROWSER start= auto`  
  
 <span data-ttu-id="dd877-266">Dopo averlo abilitato, eseguire il comando seguente dal prompt dei comandi per avviarlo:</span><span class="sxs-lookup"><span data-stu-id="dd877-266">After it is enabled, run the following command from the command prompt to start the service:</span></span>  
  
 `net start SQLBROWSER`  
  
### <a name="create-exceptions-in-windows-firewall"></a><span data-ttu-id="dd877-267">Creazione di eccezioni in Windows Firewall</span><span class="sxs-lookup"><span data-stu-id="dd877-267">Create exceptions in Windows Firewall</span></span>  
 <span data-ttu-id="dd877-268">Per creare eccezioni per l'accesso di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in Windows Firewall, seguire i passaggi specificati in [Configurare Windows Firewall per consentire l'accesso a SQL Server](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="dd877-268">To create exceptions for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access in Windows Firewall, follow the steps specified in [Configure the Windows Firewall to Allow SQL Server Access](../../sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access.md).</span></span>  
  
### <a name="enable-tcpip-on-the-instance-of-ssnoversion"></a><span data-ttu-id="dd877-269">Abilitare TCP/IP nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd877-269">Enable TCP/IP on the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="dd877-270">Il protocollo TCP/IP può essere abilitato tramite Windows PowerShell per un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in Server Core.</span><span class="sxs-lookup"><span data-stu-id="dd877-270">The TCP/IP protocol can be enabled through Windows PowerShell for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on Server Core.</span></span> <span data-ttu-id="dd877-271">A tale scopo, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="dd877-271">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="dd877-272">Avviare Gestione attività nel computer in cui è in esecuzione [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core.</span><span class="sxs-lookup"><span data-stu-id="dd877-272">On the computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, launch Task Manager.</span></span>  
  
2.  <span data-ttu-id="dd877-273">Nella scheda **Applicazioni** fare clic su **Nuova attività**.</span><span class="sxs-lookup"><span data-stu-id="dd877-273">On the **Applications** tab, click **New Task**.</span></span>  
  
3.  <span data-ttu-id="dd877-274">Nella finestra di dialogo **Crea una nuova attività** digitare **sqlps.exe** nel campo **Apri** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd877-274">In the **Create New Task** dialog box, type **sqlps.exe** in the **Open** field and then click **OK**.</span></span> <span data-ttu-id="dd877-275">Verrà visualizzata la finestra di \*\* [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] PowerShell\*\* .</span><span class="sxs-lookup"><span data-stu-id="dd877-275">This opens the **[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window.</span></span>  
  
4.  <span data-ttu-id="dd877-276">Nella finestra di **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** eseguire lo script seguente per abilitare il protocollo TCP/IP:</span><span class="sxs-lookup"><span data-stu-id="dd877-276">In the **Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Powershell** window, run the following script to enable the TCP/IP protocol:</span></span>  
  
```powershell
$smo = 'Microsoft.SqlServer.Management.Smo.'  
$wmi = New-Object ($smo + 'Wmi.ManagedComputer')  
# Enable the TCP protocol on the default instance.  If the instance is named, replace MSSQLSERVER with the instance name in the following line.  
$uri = "ManagedComputer[@Name='" + (get-item env:\computername).Value + "']/ServerInstance[@Name='MSSQLSERVER']/ServerProtocol[@Name='Tcp']"  
$Tcp = $wmi.GetSmoObject($uri)  
$Tcp.IsEnabled = $true  
$Tcp.Alter()  
$Tcp  
```  
  
## <a name="uninstallation"></a><span data-ttu-id="dd877-277">Disinstallazione</span><span class="sxs-lookup"><span data-stu-id="dd877-277">Uninstallation</span></span>  
 <span data-ttu-id="dd877-278">Dopo aver eseguito l'accesso a un computer in cui è in esecuzione [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 o [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, si dispone di un ambiente desktop limitato con un prompt dei comandi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="dd877-278">After you log on to a computer that is running [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] Server Core SP1 or [!INCLUDE[win8srv](../../includes/win8srv-md.md)] Server Core, you have a limited desktop environment with an Administrator command prompt.</span></span> <span data-ttu-id="dd877-279">Il prompt può essere utilizzato per avviare la disinstallazione di un'istanza di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-279">You can use this command prompt to initiate uninstallation of an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="dd877-280">Per disinstallare un'istanza di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], avviare l'operazione dal prompt dei comandi in modalità non interattiva completa tramite il parametro /Q o in modalità non interattiva semplice tramite il parametro /QS.</span><span class="sxs-lookup"><span data-stu-id="dd877-280">To uninstall an instance of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], launch the uninstallation from the command prompt in full quiet mode by using the /Q parameter, or quiet simple mode by using the /QS parameter.</span></span> <span data-ttu-id="dd877-281">Il parametro /QS consente di tenere traccia dello stato di avanzamento tramite l'interfaccia utente, ma non supporta input.</span><span class="sxs-lookup"><span data-stu-id="dd877-281">The /QS parameter shows progress through the UI, but does not accept any input.</span></span> <span data-ttu-id="dd877-282">/Q viene eseguito in modalità non interattiva senza alcuna interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="dd877-282">/Q runs in a quiet mode without any user interface.</span></span>  
  
 <span data-ttu-id="dd877-283">Per disinstallare un'istanza esistente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="dd877-283">To uninstall an existing instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
```cmd
setup.exe /Q /Action=Uninstall /FEATURES=SQLEngine,AS,IS /INSTANCENAME=MSSQLSERVER  
```  
  
 <span data-ttu-id="dd877-284">Per rimuovere un'istanza denominata, specificare il nome dell'istanza anziché il nome "MSSQLSERVER" dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="dd877-284">To remove a named instance, specify the name of the instance instead of "MSSQLSERVER" in the preceding example.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="dd877-285">Se si chiude il prompt dei comandi inavvertitamente, è possibile avviare un nuovo prompt dei comandi eseguendo la procedura descritta di seguito.</span><span class="sxs-lookup"><span data-stu-id="dd877-285">If you accidentally close the command prompt, you can start a new command prompt by following these steps:</span></span>  
> 
>  1.  <span data-ttu-id="dd877-286">Premere Ctrl+Maiusc+Esc per visualizzare Gestione attività.</span><span class="sxs-lookup"><span data-stu-id="dd877-286">Press Ctrl+Shift+Esc to display Task Manager.</span></span>  
> 2.  <span data-ttu-id="dd877-287">Nella scheda **Applicazioni** fare clic su **Nuova attività**.</span><span class="sxs-lookup"><span data-stu-id="dd877-287">On the **Applications** tab, click **New Task**.</span></span>  
> 3.  <span data-ttu-id="dd877-288">Nella finestra di dialogo **Crea una nuova attività** digitare **cmd** nel campo **Apri** e quindi [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dd877-288">In the **Create New Task** dialog box, type **cmd** in the **Open** field and then [!INCLUDE[clickOK](../../includes/clickok-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd877-289">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd877-289">See Also</span></span>  
 <span data-ttu-id="dd877-290">[Installare SQL Server 2014 usando un file di configurazione](install-sql-server-using-a-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="dd877-290">[Install SQL Server 2014 Using a Configuration File](install-sql-server-using-a-configuration-file.md) </span></span>  
 <span data-ttu-id="dd877-291">[Installare SQL Server 2014 dal prompt dei comandi](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="dd877-291">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="dd877-292">[Funzionalità supportate dalle edizioni di SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span><span class="sxs-lookup"><span data-stu-id="dd877-292">[Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md) </span></span>  
 <span data-ttu-id="dd877-293">[Guida Introduzione dell'opzione di installazione Server Core](https://go.microsoft.com/fwlink/?LinkId=221422) </span><span class="sxs-lookup"><span data-stu-id="dd877-293">[Server Core Installation Option Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=221422) </span></span>  
 <span data-ttu-id="dd877-294">[Configurazione di un'installazione Server Core: Panoramica](https://go.microsoft.com/fwlink/?LinkId=221423) </span><span class="sxs-lookup"><span data-stu-id="dd877-294">[Configuring a Server Core installation: Overview](https://go.microsoft.com/fwlink/?LinkId=221423) </span></span>  
 <span data-ttu-id="dd877-295">[Cmdlet del cluster di failover in Windows PowerShell elencati per attività](https://go.microsoft.com/fwlink/?LinkId=221419) </span><span class="sxs-lookup"><span data-stu-id="dd877-295">[Failover Cluster Cmdlets in Windows PowerShell Listed by Task Focus](https://go.microsoft.com/fwlink/?LinkId=221419) </span></span>  
 [<span data-ttu-id="dd877-296">Mapping di comandi Cluster.exe a cmdlet di Windows PowerShell per i cluster di failover</span><span class="sxs-lookup"><span data-stu-id="dd877-296">Mapping Cluster.exe Commands to Windows PowerShell Cmdlets for Failover Clusters</span></span>](https://go.microsoft.com/fwlink/?LinkId=221421)  
