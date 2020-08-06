---
title: Salva copia del pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.savecopyas.f1
helpviewer_keywords:
- Save Copy of Package dialog box
ms.assetid: 7b44c0d7-d8fa-4491-8836-0899f621d3a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f0a685d8b38299e1ba1d03c4ec8c1052cc957dbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722907"
---
# <a name="save-copy-of-package"></a><span data-ttu-id="37124-102">Salva copia del pacchetto</span><span class="sxs-lookup"><span data-stu-id="37124-102">Save Copy of Package</span></span>
  <span data-ttu-id="37124-103">Usare la finestra di dialogo **Salva copia del pacchetto** , disponibile in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], per salvare una copia di un pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] da [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] in un percorso diverso ed eventualmente modificarne il livello di protezione.</span><span class="sxs-lookup"><span data-stu-id="37124-103">Use the **Save Copy of Package** dialog box, available in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], to save a copy of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to a different location and, optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="37124-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="37124-104">Options</span></span>  
 <span data-ttu-id="37124-105">**Posizione pacchetto**</span><span class="sxs-lookup"><span data-stu-id="37124-105">**Package location**</span></span>  
 <span data-ttu-id="37124-106">Consente di selezionare il tipo di percorso di archiviazione in cui salvare la copia del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="37124-106">Select the type of storage location in which to save the package copy.</span></span> <span data-ttu-id="37124-107">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="37124-107">The following options are available:</span></span>  
  
 <span data-ttu-id="37124-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="37124-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="37124-109">**File system**</span><span class="sxs-lookup"><span data-stu-id="37124-109">**File System**</span></span>  
  
 <span data-ttu-id="37124-110">**Archivio pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="37124-110">**SSIS Package Store**</span></span>  
  
 <span data-ttu-id="37124-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="37124-111">**Server**</span></span>  
 <span data-ttu-id="37124-112">Consente di digitare il nome del server o di selezionarlo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="37124-112">Type a server name or select a server from the list.</span></span> <span data-ttu-id="37124-113">Questa opzione è disponibile solo se il percorso di archiviazione è **SQL Server** o **Archivio pacchetti SSIS**.</span><span class="sxs-lookup"><span data-stu-id="37124-113">This option is available only if the storage location is **SQL Server** or **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="37124-114">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="37124-114">**Authentication**</span></span>  
 <span data-ttu-id="37124-115">Consente di selezionare l'autenticazione di Windows o l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="37124-115">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="37124-116">Questa opzione è disponibile solo se è stato selezionato il percorso di archiviazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37124-116">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="37124-117">Se possibile, utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="37124-117">Whenever possible use Windows Authentication.</span></span>  
  
 <span data-ttu-id="37124-118">**Tipo di autenticazione**</span><span class="sxs-lookup"><span data-stu-id="37124-118">**Authentication type**</span></span>  
 <span data-ttu-id="37124-119">Consente di selezionare un tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="37124-119">Select an authentication type.</span></span>  
  
 <span data-ttu-id="37124-120">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="37124-120">**User name**</span></span>  
 <span data-ttu-id="37124-121">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare un nome utente.</span><span class="sxs-lookup"><span data-stu-id="37124-121">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="37124-122">**Password**</span><span class="sxs-lookup"><span data-stu-id="37124-122">**Password**</span></span>  
 <span data-ttu-id="37124-123">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare una password.</span><span class="sxs-lookup"><span data-stu-id="37124-123">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="37124-124">**Percorso pacchetto**</span><span class="sxs-lookup"><span data-stu-id="37124-124">**Package path**</span></span>  
 <span data-ttu-id="37124-125">Digitare il percorso del pacchetto oppure fare clic sul pulsante Sfoglia **(...)** per individuare la cartella in cui archiviare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="37124-125">Type the package path, or click the browse **(...)** button and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="37124-126">**Livello di protezione**</span><span class="sxs-lookup"><span data-stu-id="37124-126">**Protection level**</span></span>  
 <span data-ttu-id="37124-127">Fare clic sul pulsante Sfoglia **(...)** e aggiornare il livello di protezione nella finestra di dialogo **livello di protezione pacchetto** .</span><span class="sxs-lookup"><span data-stu-id="37124-127">Click the browse **(...)** button and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="37124-128">Per altre informazioni, vedere [Finestra di dialogo Livello di protezione pacchetto e Livello di protezione del progetto](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="37124-128">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37124-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37124-129">See Also</span></span>  
 <span data-ttu-id="37124-130">[Riferimento all'interfaccia utente della finestra di dialogo Importa pacchetto](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="37124-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="37124-131">[Riferimento all'interfaccia utente della finestra di dialogo Esporta pacchetto](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="37124-131">[Export Package Dialog Box UI Reference](../../2014/integration-services/export-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="37124-132">[Salva pacchetti](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="37124-132">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="37124-133">Importare ed esportare pacchetti &#40;servizio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="37124-133">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
