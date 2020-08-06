---
title: Riferimento all'interfaccia utente della finestra di dialogo Esporta pacchetto | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtsserver.exportpackage.f1
helpviewer_keywords:
- Export Package dialog box
ms.assetid: 3742fe8a-ef57-444d-b2fb-cb25d16bae97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8aedb771dc61fca737ba3841e65b8cb8655d173e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727079"
---
# <a name="export-package-dialog-box-ui-reference"></a><span data-ttu-id="9d162-102">Riferimento all'interfaccia utente della finestra di dialogo Esporta pacchetto</span><span class="sxs-lookup"><span data-stu-id="9d162-102">Export Package Dialog Box UI Reference</span></span>
  <span data-ttu-id="9d162-103">Usare la finestra di dialogo **Esporta pacchetto** disponibile in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]per esportare un pacchetto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in un percorso diverso ed eventualmente modificare il livello di protezione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9d162-103">Use the **Export Package** dialog box, available in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], to export a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package to a different location and optionally, modify the protection level of the package.</span></span>  
  
## <a name="options"></a><span data-ttu-id="9d162-104">Opzioni</span><span class="sxs-lookup"><span data-stu-id="9d162-104">Options</span></span>  
 <span data-ttu-id="9d162-105">**Posizione pacchetto**</span><span class="sxs-lookup"><span data-stu-id="9d162-105">**Package location**</span></span>  
 <span data-ttu-id="9d162-106">Consente di selezionare il tipo di archiviazione in cui esportare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9d162-106">Select the type of storage to export the package to.</span></span> <span data-ttu-id="9d162-107">Sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d162-107">The following options are available:</span></span>  
  
 <span data-ttu-id="9d162-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="9d162-108">**SQL Server**</span></span>  
  
 <span data-ttu-id="9d162-109">**File system**</span><span class="sxs-lookup"><span data-stu-id="9d162-109">**File System**</span></span>  
  
 <span data-ttu-id="9d162-110">**Archivio pacchetti SSIS**</span><span class="sxs-lookup"><span data-stu-id="9d162-110">**SSIS Package Storage**</span></span>  
  
 <span data-ttu-id="9d162-111">**Server**</span><span class="sxs-lookup"><span data-stu-id="9d162-111">**Server**</span></span>  
 <span data-ttu-id="9d162-112">Consente di digitare il nome del server o di selezionarlo nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9d162-112">Type a server name or select a server from the list.</span></span>  
  
 <span data-ttu-id="9d162-113">**autenticazione**</span><span class="sxs-lookup"><span data-stu-id="9d162-113">**Authentication**</span></span>  
 <span data-ttu-id="9d162-114">Consente di selezionare l'autenticazione di Windows o l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9d162-114">Select Windows Authentication or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="9d162-115">Questa opzione è disponibile solo se è stato selezionato il percorso di archiviazione [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9d162-115">This option is available only if the storage location is [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9d162-116">Se possibile, è consigliabile utilizzare l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="9d162-116">Whenever possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="9d162-117">**Tipo di autenticazione**</span><span class="sxs-lookup"><span data-stu-id="9d162-117">**Authentication type**</span></span>  
 <span data-ttu-id="9d162-118">Consente di selezionare un tipo di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="9d162-118">Select an authentication type.</span></span>  
  
 <span data-ttu-id="9d162-119">**Nome utente**</span><span class="sxs-lookup"><span data-stu-id="9d162-119">**User name**</span></span>  
 <span data-ttu-id="9d162-120">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare un nome utente.</span><span class="sxs-lookup"><span data-stu-id="9d162-120">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name.</span></span>  
  
 <span data-ttu-id="9d162-121">**Password**</span><span class="sxs-lookup"><span data-stu-id="9d162-121">**Password**</span></span>  
 <span data-ttu-id="9d162-122">Se si utilizza l'autenticazione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , specificare una password.</span><span class="sxs-lookup"><span data-stu-id="9d162-122">If using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a password.</span></span>  
  
 <span data-ttu-id="9d162-123">**Percorso pacchetto**</span><span class="sxs-lookup"><span data-stu-id="9d162-123">**Package path**</span></span>  
 <span data-ttu-id="9d162-124">Digitare il percorso del pacchetto oppure fare clic sul pulsante Sfoglia **(...)** e individuare la cartella in cui archiviare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9d162-124">Type the package path, or click the browse button **(...)** and locate the folder in which to store the package.</span></span>  
  
 <span data-ttu-id="9d162-125">**Livello di protezione**</span><span class="sxs-lookup"><span data-stu-id="9d162-125">**Protection level**</span></span>  
 <span data-ttu-id="9d162-126">Fare clic sul pulsante Sfoglia **(...)** e aggiornare il livello di protezione nella finestra di dialogo **Livello di protezione pacchetto**.</span><span class="sxs-lookup"><span data-stu-id="9d162-126">Click the browse button **(...)** and update the protection level in the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="9d162-127">Per altre informazioni, vedere [Finestra di dialogo Livello di protezione pacchetto e Livello di protezione del progetto](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="9d162-127">For more information, see [Package and Project Protection Level Dialog Box](../../2014/integration-services/package-and-project-protection-level-dialog-box.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d162-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d162-128">See Also</span></span>  
 <span data-ttu-id="9d162-129">[Salva copia del pacchetto](../../2014/integration-services/save-copy-of-package.md) </span><span class="sxs-lookup"><span data-stu-id="9d162-129">[Save Copy of Package](../../2014/integration-services/save-copy-of-package.md) </span></span>  
 <span data-ttu-id="9d162-130">[Riferimento all'interfaccia utente della finestra di dialogo Importa pacchetto](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span><span class="sxs-lookup"><span data-stu-id="9d162-130">[Import Package Dialog Box UI Reference](../../2014/integration-services/import-package-dialog-box-ui-reference.md) </span></span>  
 <span data-ttu-id="9d162-131">[Salva pacchetti](save-packages.md) </span><span class="sxs-lookup"><span data-stu-id="9d162-131">[Save Packages](save-packages.md) </span></span>  
 [<span data-ttu-id="9d162-132">Importare ed esportare pacchetti &#40;servizio SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="9d162-132">Import and Export Packages &#40;SSIS Service&#41;</span></span>](../../2014/integration-services/import-and-export-packages-ssis-service.md)  
  
  
