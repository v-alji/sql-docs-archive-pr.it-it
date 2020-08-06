---
title: Riferimento all'interfaccia utente della finestra di dialogo Importa pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.importpackage.f1
helpviewer_keywords:
- Import Package dialog box
ms.assetid: 0e5fb127-c7ff-4dfa-b90e-d9bcf0ce763b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ff20bf8eb221778465a26944280d53b6aab07601
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628900"
---
# <a name="import-package-dialog-box-ui-reference"></a><span data-ttu-id="aa0a3-102">Riferimento all'interfaccia utente della finestra di dialogo Importa pacchetto</span><span class="sxs-lookup"><span data-stu-id="aa0a3-102">Import Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="aa0a3-103">Usare la finestra di dialogo **Importa pacchetto** disponibile in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]per importare un pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e impostare o modificare il livello di protezione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-103">Use the **Import Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to import a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and to set or modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="aa0a3-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="aa0a3-104">Options</span></span>  
 <span data-ttu-id="aa0a3-105">**Posizione pacchetto**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-105">**Package location**</span></span>  
 <span data-ttu-id="aa0a3-106">Selezionare il tipo di percorso di archiviazione da cui importare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-106">Select the type of storage location to import the package to.</span></span> <span data-ttu-id="aa0a3-107">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa0a3-107">The following options are available:</span></span>  
  
 <span data-ttu-id="aa0a3-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="aa0a3-109">**File system**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-109">**File System**</span></span>  
  
 <span data-ttu-id="aa0a3-110">**Archivio pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="aa0a3-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-111">**Server**</span></span>  
 <span data-ttu-id="aa0a3-112">Consente di digitare il nome del server o di selezionarlo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="aa0a3-113">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-113">**Authentication**</span></span>  
 <span data-ttu-id="aa0a3-114">Consente di selezionare l'autenticazione di Windows o l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="aa0a3-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="aa0a3-115">Questa opzione è disponibile solo se è stato selezionato il percorso di archiviazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa0a3-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="aa0a3-116">Se possibile, è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="aa0a3-117">**Tipo di autenticazione**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-117">**Authentication type**</span></span>  
 <span data-ttu-id="aa0a3-118">Consente di selezionare un tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="aa0a3-119">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-119">**User name**</span></span>  
 <span data-ttu-id="aa0a3-120">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare un nome utente.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="aa0a3-121">**Password**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-121">**Password**</span></span>  
 <span data-ttu-id="aa0a3-122">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare una password.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="aa0a3-123">**Percorso pacchetto**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-123">**Package path**</span></span>  
 <span data-ttu-id="aa0a3-124">Digitare il percorso del pacchetto oppure fare clic sul pulsante Sfoglia **(...)** per individuare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-124">Type the package path, or click the browse button **(...)** and locate the package.</span></span>  
  
 <span data-ttu-id="aa0a3-125">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-125">**Package name**</span></span>  
 <span data-ttu-id="aa0a3-126">Se lo si desidera, rinominare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-126">Optionally, rename the package.</span></span> <span data-ttu-id="aa0a3-127">Il nome predefinito è il nome del pacchetto da importare.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-127">The default name is the name of the package to import.</span></span>  
  
 <span data-ttu-id="aa0a3-128">**Livello di protezione**</span><span class="sxs-lookup"><span data-stu-id="aa0a3-128">**Protection level**</span></span>  
 <span data-ttu-id="aa0a3-129">Fare clic sul pulsante Sfoglia **(...)** e aggiornare il livello di protezione nella finestra di dialogo **Livello di protezione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="aa0a3-129">Click the browse button **(...)** and, in the **Package Protection Level** dialog box, update the protection level.</span></span> <span data-ttu-id="aa0a3-130">Per altre informazioni, vedere [Finestra di dialogo Livello di protezione pacchetto e Livello di protezione del progetto](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="aa0a3-130">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0a3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa0a3-131">See Also</span></span>  
 <span data-ttu-id="aa0a3-132">[Salva copia del pacchetto](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="aa0a3-132">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="aa0a3-133">[Riferimento all'interfaccia utente della finestra di dialogo Esporta pacchetto](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="aa0a3-133">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="aa0a3-134">[Salva pacchetti](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="aa0a3-134">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="aa0a3-135">Importare ed esportare pacchetti &#40;servizio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="aa0a3-135">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
