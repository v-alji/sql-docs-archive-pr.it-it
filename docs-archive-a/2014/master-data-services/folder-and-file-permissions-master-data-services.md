---
title: Autorizzazioni per file e cartelle (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- security [Master Data Services], file and folder
- folders [Master Data Services]
- files [Master Data Services]
ms.assetid: 6402d81d-7349-47b1-95ca-99b0c0f4f373
author: lrtoyou1223
ms.author: lle
robots: noindex,nofollow
ms.openlocfilehash: 6dc356e074574a4c520b1f4de2f41db0e983c4df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715511"
---
# <a name="folder-and-file-permissions-master-data-services"></a><span data-ttu-id="a4163-102">Autorizzazioni per file e cartelle [Master Data Services]</span><span class="sxs-lookup"><span data-stu-id="a4163-102">Folder and File Permissions (Master Data Services)</span></span>
  <span data-ttu-id="a4163-103">Quando si installa [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], cartelle e file vengono installati nel file system nel percorso di installazione specificato per le funzionalità condivise di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4163-103">When you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], folders and files are installed in the file system at the installation path you specify for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features.</span></span> <span data-ttu-id="a4163-104">Se si usa il percorso di installazione predefinito per [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] le funzionalità condivise, il percorso di installazione per [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] è *unità*: \Programmi\microsoft SQL Server\120\Master Data Services.</span><span class="sxs-lookup"><span data-stu-id="a4163-104">If you use the default installation path for [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shared features, the installation path for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services.</span></span> <span data-ttu-id="a4163-105">Sebbene sia possibile modificare il percorso di installazione delle funzionalità condivise, è necessario considerare le autorizzazioni ereditate dalla cartella padre e quelle impostate in modo esplicito per [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4163-105">Although you can change the shared features installation path, be aware of permissions that are inherited from the parent folder and permissions that are explicitly set for [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span>  
  
## <a name="inherited-permissions"></a><span data-ttu-id="a4163-106">Autorizzazioni ereditate</span><span class="sxs-lookup"><span data-stu-id="a4163-106">Inherited Permissions</span></span>  
 <span data-ttu-id="a4163-107">Le autorizzazioni della cartella di **Microsoft SQL Server** , della cartella di **Master Data Services** e della maggior parte delle sottocartelle e dei file sono ereditate dalla cartella padre specificata nel programma di installazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4163-107">The **Microsoft SQL Server** folder, the **Master Data Services** folder, and most subfolders and files inherit permissions from the parent folder specified in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Setup.</span></span> <span data-ttu-id="a4163-108">Se si sceglie il percorso di installazione predefinito, la cartella padre dalla quale vengono ereditate le autorizzazioni è *unità*:\Programmi.</span><span class="sxs-lookup"><span data-stu-id="a4163-108">If you choose the default installation location, the parent folder that permissions are inherited from is *drive*:\Program Files.</span></span> <span data-ttu-id="a4163-109">Nella tabella seguente vengono descritte le autorizzazioni predefinite per la cartella **Programmi**.</span><span class="sxs-lookup"><span data-stu-id="a4163-109">The following table describes the default permissions for **Program Files**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4163-110">Se si modificano le autorizzazioni predefinite di **Programmi**o si sceglie un percorso di installazione diverso, le autorizzazioni di cartelle e file di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] vengono ereditate dalla relativa cartella padre e possono essere diverse rispetto a quelle descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a4163-110">If you modify default permissions for **Program Files**, or you choose a different installation location, the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] folders and files inherit permissions from their parent folder accordingly, and the permissions might differ from those described in the following table.</span></span>  
  
###### <a name="program-files-default-permissions"></a><span data-ttu-id="a4163-111">Autorizzazioni predefinite di Programmi</span><span class="sxs-lookup"><span data-stu-id="a4163-111">Program Files Default Permissions</span></span>  
  
|<span data-ttu-id="a4163-112">Nome di gruppo o di account</span><span class="sxs-lookup"><span data-stu-id="a4163-112">Group or account name</span></span>|<span data-ttu-id="a4163-113">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a4163-113">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="a4163-114">CREATOR OWNER</span><span class="sxs-lookup"><span data-stu-id="a4163-114">CREATOR OWNER</span></span>|<span data-ttu-id="a4163-115">Autorizzazioni speciali</span><span class="sxs-lookup"><span data-stu-id="a4163-115">Special permissions</span></span>|  
|<span data-ttu-id="a4163-116">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="a4163-116">SYSTEM</span></span>|<span data-ttu-id="a4163-117">Autorizzazioni speciali</span><span class="sxs-lookup"><span data-stu-id="a4163-117">Special permissions</span></span>|  
|<span data-ttu-id="a4163-118">Amministratori</span><span class="sxs-lookup"><span data-stu-id="a4163-118">Administrators</span></span>|<span data-ttu-id="a4163-119">Autorizzazioni speciali</span><span class="sxs-lookup"><span data-stu-id="a4163-119">Special permissions</span></span>|  
|<span data-ttu-id="a4163-120">Utenti</span><span class="sxs-lookup"><span data-stu-id="a4163-120">Users</span></span>|<span data-ttu-id="a4163-121">Lettura ed esecuzione, Visualizzazione contenuto cartella, Lettura</span><span class="sxs-lookup"><span data-stu-id="a4163-121">Read & execute, List folder contents, Read</span></span>|  
|<span data-ttu-id="a4163-122">TrustedInstaller</span><span class="sxs-lookup"><span data-stu-id="a4163-122">TrustedInstaller</span></span>|<span data-ttu-id="a4163-123">Visualizzazione contenuto cartella, Autorizzazioni speciali</span><span class="sxs-lookup"><span data-stu-id="a4163-123">List folder contents, Special permissions</span></span>|  
  
## <a name="explicit-permissions"></a><span data-ttu-id="a4163-124">Autorizzazioni esplicite</span><span class="sxs-lookup"><span data-stu-id="a4163-124">Explicit Permissions</span></span>  
 <span data-ttu-id="a4163-125">La cartella **MDSTempDir** e il file Web.config di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] (nella cartella **WebApplication** ) non ereditano autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a4163-125">The **MDSTempDir** folder and the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file (in the **WebApplication** folder) do not inherit permissions.</span></span> <span data-ttu-id="a4163-126">Le autorizzazioni di cui dispongono sono impostate in modo esplicito quando si installa [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], indipendentemente dal percorso di installazione scelto.</span><span class="sxs-lookup"><span data-stu-id="a4163-126">They have permissions that are set explicitly when you install [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], regardless of the installation path you choose.</span></span> <span data-ttu-id="a4163-127">Non modificare queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="a4163-127">Do not modify these permissions.</span></span>  
  
###### <a name="mdstempdir-permissions"></a><span data-ttu-id="a4163-128">Autorizzazioni di MDSTempDir</span><span class="sxs-lookup"><span data-stu-id="a4163-128">MDSTempDir Permissions</span></span>  
  
|<span data-ttu-id="a4163-129">Nome di gruppo o di account</span><span class="sxs-lookup"><span data-stu-id="a4163-129">Group or account name</span></span>|<span data-ttu-id="a4163-130">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a4163-130">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="a4163-131">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="a4163-131">SYSTEM</span></span>|<span data-ttu-id="a4163-132">Modifica, Lettura ed esecuzione, Visualizzazione contenuto cartella, Lettura, Scrittura</span><span class="sxs-lookup"><span data-stu-id="a4163-132">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="a4163-133">Amministratori</span><span class="sxs-lookup"><span data-stu-id="a4163-133">Administrators</span></span>|<span data-ttu-id="a4163-134">Modifica, Lettura ed esecuzione, Visualizzazione contenuto cartella, Lettura, Scrittura</span><span class="sxs-lookup"><span data-stu-id="a4163-134">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
|<span data-ttu-id="a4163-135">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="a4163-135">MDS_ServiceAccounts</span></span>|<span data-ttu-id="a4163-136">Modifica, Lettura ed esecuzione, Visualizzazione contenuto cartella, Lettura, Scrittura</span><span class="sxs-lookup"><span data-stu-id="a4163-136">Modify, Read & execute, List folder contents, Read, Write</span></span>|  
  
###### <a name="webconfig-permissions"></a><span data-ttu-id="a4163-137">Autorizzazioni di Web.config</span><span class="sxs-lookup"><span data-stu-id="a4163-137">Web.config Permissions</span></span>  
  
|<span data-ttu-id="a4163-138">Nome di gruppo o di account</span><span class="sxs-lookup"><span data-stu-id="a4163-138">Group or account name</span></span>|<span data-ttu-id="a4163-139">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="a4163-139">Permissions</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="a4163-140">SYSTEM</span><span class="sxs-lookup"><span data-stu-id="a4163-140">SYSTEM</span></span>|<span data-ttu-id="a4163-141">Controllo completo, Modifica, Lettura ed esecuzione, Lettura, Scrittura</span><span class="sxs-lookup"><span data-stu-id="a4163-141">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="a4163-142">Amministratori</span><span class="sxs-lookup"><span data-stu-id="a4163-142">Administrators</span></span>|<span data-ttu-id="a4163-143">Controllo completo, Modifica, Lettura ed esecuzione, Lettura, Scrittura</span><span class="sxs-lookup"><span data-stu-id="a4163-143">Full control, Modify, Read & execute, Read, Write</span></span>|  
|<span data-ttu-id="a4163-144">MDS_ServiceAccounts</span><span class="sxs-lookup"><span data-stu-id="a4163-144">MDS_ServiceAccounts</span></span>|<span data-ttu-id="a4163-145">Lettura ed esecuzione, Lettura</span><span class="sxs-lookup"><span data-stu-id="a4163-145">Read & execute, Read</span></span>|  
  
 <span data-ttu-id="a4163-146">Per altre informazioni sul contenuto del file Web.config di [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vedere [Guida di riferimento alla configurazione Web &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a4163-146">For more information about the contents of the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Web.config file, see [Web Configuration Reference &#40;Master Data Services&#41;](web-configuration-reference-master-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4163-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4163-147">See Also</span></span>  
 [<span data-ttu-id="a4163-148">Installazione di Master Data Services</span><span class="sxs-lookup"><span data-stu-id="a4163-148">Install Master Data Services</span></span>](install-windows/install-master-data-services.md)  
  
  
