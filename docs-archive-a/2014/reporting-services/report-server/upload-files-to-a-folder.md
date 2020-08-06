---
title: Caricare file in una cartella | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- publishing reports [Reporting Services], uploading files
- reports [Reporting Services], publishing
- uploading reports [Reporting Services]
- uploading files [Reporting Services]
- files [Reporting Services], uploading
- files [Reporting Services]
- folders [Reporting Services], uploading files to
ms.assetid: 2f99a288-d4aa-4c64-b310-e457a2aef2c5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cfb595ed6059436d17cb82262f5d1975a8397dbd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628321"
---
# <a name="upload-files-to-a-folder"></a><span data-ttu-id="39ccf-102">Caricare file in una cartella</span><span class="sxs-lookup"><span data-stu-id="39ccf-102">Upload Files to a Folder</span></span>
  <span data-ttu-id="39ccf-103">È possibile caricare file dal file system e archiviarli come elementi gestiti in un database del server di report.</span><span class="sxs-lookup"><span data-stu-id="39ccf-103">You can upload files from the file system and store them as managed items in a report server database.</span></span> <span data-ttu-id="39ccf-104">La funzionalità di un file caricato dipende dal tipo di file.</span><span class="sxs-lookup"><span data-stu-id="39ccf-104">What happens when you upload a file depends on the file type.</span></span>

-   <span data-ttu-id="39ccf-105">Il caricamento di un file con estensione rdl equivale alla pubblicazione di un report.</span><span class="sxs-lookup"><span data-stu-id="39ccf-105">Uploading an .rdl file is equivalent to publishing a report.</span></span>

-   <span data-ttu-id="39ccf-106">Qualsiasi altro tipo di file caricato viene aggiunto al database del server di report come singolo oggetto binario.</span><span class="sxs-lookup"><span data-stu-id="39ccf-106">Uploading any other file adds it to the report server database as a single binary object.</span></span> <span data-ttu-id="39ccf-107">I file vengono pubblicati in un server di report come risorse</span><span class="sxs-lookup"><span data-stu-id="39ccf-107">These files are published to a report server as a resource.</span></span> <span data-ttu-id="39ccf-108">e possono essere file di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="39ccf-108">Resources can be any file type.</span></span> <span data-ttu-id="39ccf-109">Se l'estensione del file corrisponde a un tipo MIME noto, viene utilizzata un'icona specifica per identificare il tipo di risorsa.</span><span class="sxs-lookup"><span data-stu-id="39ccf-109">If the file extension matches a known MIME type, an icon for that MIME type is used to identify the resource type.</span></span> <span data-ttu-id="39ccf-110">In caso contrario, la risorsa viene indicata da un'icona di file generico.</span><span class="sxs-lookup"><span data-stu-id="39ccf-110">Otherwise, a generic file icon indicates a resource.</span></span>

> [!NOTE]
>  <span data-ttu-id="39ccf-111">Non è possibile caricare un file di origine dei dati del report con estensione rds per creare un'origine dei dati condivisa.</span><span class="sxs-lookup"><span data-stu-id="39ccf-111">You cannot upload a report data source (.rds) file to create a shared data source.</span></span> <span data-ttu-id="39ccf-112">Un file con estensione rds viene utilizzato solo in Progettazione report.</span><span class="sxs-lookup"><span data-stu-id="39ccf-112">An .rds file is used only in Report Designer.</span></span> <span data-ttu-id="39ccf-113">Tale file non fornisce il contenuto per un elemento dell'origine dati condivisa definito e gestito tramite Gestione report.</span><span class="sxs-lookup"><span data-stu-id="39ccf-113">It cannot provide the content for a shared data source item that you define and manage through Report Manager.</span></span> <span data-ttu-id="39ccf-114">In alternativa al caricamento è possibile creare uno script per la creazione di un'origine dei dati condivisa in base a un file con estensione rds.</span><span class="sxs-lookup"><span data-stu-id="39ccf-114">As an alternative to uploading, you can write a script that creates a shared data source based on a .rds file.</span></span>

 <span data-ttu-id="39ccf-115">La dimensione massima del file per gli elementi caricati è stabilita da [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39ccf-115">The maximum file size for uploaded items is determined by [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)].</span></span> <span data-ttu-id="39ccf-116">Per impostazione predefinita, il valore per la dimensione massima è pari a 4 MB.</span><span class="sxs-lookup"><span data-stu-id="39ccf-116">By default, the maximum size is 4 megabytes (MB).</span></span>

 <span data-ttu-id="39ccf-117">I file caricati in un database del server di report sono visualizzati nella gerarchia di cartelle con le icone seguenti.</span><span class="sxs-lookup"><span data-stu-id="39ccf-117">Visually, files that you upload to a report server database are represented in the folder hierarchy with the following icons.</span></span>

 <span data-ttu-id="39ccf-118">Icona del report ![icona](../media/hlp-16doc.gif "Icona del report") del report</span><span class="sxs-lookup"><span data-stu-id="39ccf-118">![Report icon](../media/hlp-16doc.gif "Report icon") report icon</span></span>

 <span data-ttu-id="39ccf-119">Icona modello di report ![icona](../media/model-icon.gif "Icona di modello") modello</span><span class="sxs-lookup"><span data-stu-id="39ccf-119">![Model icon](../media/model-icon.gif "Model icon") report model icon</span></span>

 <span data-ttu-id="39ccf-120">icona di risorsa generica icona di ![risorsa generica](../media/hlp-16file.gif "Icona di risorsa generica")</span><span class="sxs-lookup"><span data-stu-id="39ccf-120">![generic resource icon](../media/hlp-16file.gif "generic resource icon") generic resource icon</span></span>

 <span data-ttu-id="39ccf-121">I file caricati vengono inseriti automaticamente nella cartella selezionata.</span><span class="sxs-lookup"><span data-stu-id="39ccf-121">When you upload a file, it is always placed in the folder that is currently selected.</span></span> <span data-ttu-id="39ccf-122">È pertanto possibile passare alla cartella desiderata prima di caricare il file oppure spostare il file nella cartella desiderata dopo averlo caricato.</span><span class="sxs-lookup"><span data-stu-id="39ccf-122">You can navigate to the folder that you want to contain the item first, or you can upload a file and then move it to a final location later.</span></span>

 <span data-ttu-id="39ccf-123">Per caricare un file, utilizzare Gestione report</span><span class="sxs-lookup"><span data-stu-id="39ccf-123">To upload a file, use Report Manager.</span></span> <span data-ttu-id="39ccf-124">La possibilità o meno di caricare file in un server di report dipende dalle attività incluse nell'assegnazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="39ccf-124">Whether you can upload files to a report server depends on tasks that are part of your role assignment.</span></span> <span data-ttu-id="39ccf-125">Se vengono utilizzate le impostazioni di sicurezza predefinite, gli amministratori locali possono aggiungere elementi a un server di report.</span><span class="sxs-lookup"><span data-stu-id="39ccf-125">If you are using default security, local administrators can add items to a report server.</span></span> <span data-ttu-id="39ccf-126">Se è attivata la funzionalità Report personali, qualsiasi utente con una cartella Report personali disporrà dell'autorizzazione per caricare elementi in quella cartella.</span><span class="sxs-lookup"><span data-stu-id="39ccf-126">If My Reports is enabled, any user who has a My Reports folder has permission to upload items to that folder.</span></span> <span data-ttu-id="39ccf-127">Se si utilizzano assegnazioni di ruolo personalizzate, tali assegnazioni devono includere attività che supportano la gestione delle cartelle.</span><span class="sxs-lookup"><span data-stu-id="39ccf-127">If you use custom role assignments, the role assignment must include tasks that support folder management.</span></span>

|<span data-ttu-id="39ccf-128">Per</span><span class="sxs-lookup"><span data-stu-id="39ccf-128">To do this</span></span>|<span data-ttu-id="39ccf-129">Includere queste attività</span><span class="sxs-lookup"><span data-stu-id="39ccf-129">Include these tasks</span></span>|
|----------------|-------------------------|
|<span data-ttu-id="39ccf-130">Caricamento di un file con estensione rdl in una cartella</span><span class="sxs-lookup"><span data-stu-id="39ccf-130">Upload an .rdl file to a folder</span></span>|<span data-ttu-id="39ccf-131">Gestione di report</span><span class="sxs-lookup"><span data-stu-id="39ccf-131">Manage reports</span></span>|
|<span data-ttu-id="39ccf-132">Caricamento di qualsiasi file come oggetto binario</span><span class="sxs-lookup"><span data-stu-id="39ccf-132">Upload any file as a binary object</span></span>|<span data-ttu-id="39ccf-133">Gestione di risorse</span><span class="sxs-lookup"><span data-stu-id="39ccf-133">Manage resources</span></span>|
|<span data-ttu-id="39ccf-134">Visualizzazione del contenuto di una cartella</span><span class="sxs-lookup"><span data-stu-id="39ccf-134">View the contents of a folder</span></span>|<span data-ttu-id="39ccf-135">Visualizzazione di risorse, Visualizzazione di report</span><span class="sxs-lookup"><span data-stu-id="39ccf-135">View resources, View reports</span></span>|

## <a name="see-also"></a><span data-ttu-id="39ccf-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39ccf-136">See Also</span></span>
 <span data-ttu-id="39ccf-137">[Gestione report &#40;modalità nativa SSRS&#41;]. /report-manager-ssrs-native-mode.md) [concessione di autorizzazioni per le attività del server di report in modalità nativa](../security/granting-permissions-on-a-native-mode-report-server.md) [e autorizzazioni](../security/tasks-and-permissions.md) per il [caricamento di un File o di un report &#40;Gestione report&#41;](../reports/upload-a-file-or-report-report-manager.md)</span><span class="sxs-lookup"><span data-stu-id="39ccf-137">[Report Manager  &#40;SSRS Native Mode&#41;]../report-manager-ssrs-native-mode.md) [Granting Permissions on a Native Mode Report Server](../security/granting-permissions-on-a-native-mode-report-server.md) [Tasks and Permissions](../security/tasks-and-permissions.md) [Upload a File or Report &#40;Report Manager&#41;](../reports/upload-a-file-or-report-report-manager.md)</span></span>


