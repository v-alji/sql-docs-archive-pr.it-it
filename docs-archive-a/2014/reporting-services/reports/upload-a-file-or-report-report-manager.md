---
title: Caricare un file o un report (Gestione report) | Microsoft Docs
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
ms.assetid: 79027e11-f4ba-4bfd-bd8c-d334e3da02a1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 119e2b22976dc227e017b81a59b698cf9eb7457f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87625988"
---
# <a name="upload-a-file-or-report-report-manager"></a><span data-ttu-id="30dd5-102">Caricare un file o un report (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="30dd5-102">Upload a File or Report (Report Manager)</span></span>
  <span data-ttu-id="30dd5-103">In Gestione report è disponibile una caratteristica di caricamento che consente di aggiungere report, modelli e altri file a un server di report senza pubblicarli da un'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="30dd5-103">Report Manager provides an upload feature so that you can add reports, models, and other files to a report server without having to publish those items from a client application.</span></span> <span data-ttu-id="30dd5-104">I file caricati da un file system vengono archiviati come elementi in un server di report.</span><span class="sxs-lookup"><span data-stu-id="30dd5-104">Files that you upload from the file system are stored as items on the report server.</span></span> <span data-ttu-id="30dd5-105">Il tipo di file caricato determina le modalità di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="30dd5-105">The type of file you upload determines how it is stored:</span></span>  
  
-   <span data-ttu-id="30dd5-106">I file con estensione rdl vengono archiviati come report.</span><span class="sxs-lookup"><span data-stu-id="30dd5-106">.rdl files are stored as reports.</span></span>  
  
-   <span data-ttu-id="30dd5-107">I file con estensione smdl vengono archiviati come modelli di report.</span><span class="sxs-lookup"><span data-stu-id="30dd5-107">.smdl files are stored as report models.</span></span>  
  
-   <span data-ttu-id="30dd5-108">Tutti gli altri file, ad esempio i file dell'origine dati condivisa (con estensione rds), vengono caricate come risorse.</span><span class="sxs-lookup"><span data-stu-id="30dd5-108">All other files, including shared data source (.rds) files, are uploaded as resources.</span></span> <span data-ttu-id="30dd5-109">Le risorse non vengono elaborate da un server di report, ma possono essere visualizzate in Gestione report se il server di report supporta il tipo MIME del file.</span><span class="sxs-lookup"><span data-stu-id="30dd5-109">Resources are not processed by a report server, but can be viewed in Report Manager if the report server supports the MIME type of the file.</span></span>  
  
### <a name="to-upload-a-file-or-report"></a><span data-ttu-id="30dd5-110">Per caricare un file o un report</span><span class="sxs-lookup"><span data-stu-id="30dd5-110">To upload a file or report</span></span>  
  
1.  <span data-ttu-id="30dd5-111">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="30dd5-111">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="30dd5-112">In Gestione report passare alla pagina **contenuto** .</span><span class="sxs-lookup"><span data-stu-id="30dd5-112">In Report Manager, navigate to the **Contents** page.</span></span> <span data-ttu-id="30dd5-113">quindi passare alla cartella in cui si desidera aggiungere un elemento.</span><span class="sxs-lookup"><span data-stu-id="30dd5-113">Navigate to the folder to which you want to add an item.</span></span>  
  
3.  <span data-ttu-id="30dd5-114">Fare clic su **Carica file**.</span><span class="sxs-lookup"><span data-stu-id="30dd5-114">Click **Upload File**.</span></span>  
  
4.  <span data-ttu-id="30dd5-115">Fare clic su **Sfoglia** per selezionare il file da caricare.</span><span class="sxs-lookup"><span data-stu-id="30dd5-115">Click **Browse** to select a file to upload.</span></span> <span data-ttu-id="30dd5-116">È possibile caricare un file di definizione del report, un'immagine, un documento o qualsiasi altro file che si desidera rendere disponibile nel server di report.</span><span class="sxs-lookup"><span data-stu-id="30dd5-116">You can upload a report definition file, an image, a document, or any file that you want to make available on the report server.</span></span>  
  
5.  <span data-ttu-id="30dd5-117">Digitare un nome per il nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="30dd5-117">Type a name for the new item.</span></span> <span data-ttu-id="30dd5-118">Il nome di un elemento può includere spazi ma non i caratteri riservati, ovvero ; ?</span><span class="sxs-lookup"><span data-stu-id="30dd5-118">An item name can include spaces, but cannot include the reserved characters: ; ?</span></span> <span data-ttu-id="30dd5-119">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="30dd5-119">: \@ & = + , $ / \* \< > |.</span></span>  
  
6.  <span data-ttu-id="30dd5-120">Se si desidera sostituire un elemento esistente con il nuovo elemento, selezionare **Sovrascrivi se esistente**.</span><span class="sxs-lookup"><span data-stu-id="30dd5-120">If you want to replace an existing item with the new item, select **Overwrite item if it exists**.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30dd5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30dd5-121">See Also</span></span>  
 <span data-ttu-id="30dd5-122">[Creare, eliminare o modificare un'origine dati condivisa &#40;Gestione report&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="30dd5-122">[Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) </span></span>  
 <span data-ttu-id="30dd5-123">[Pagina contenuti &#40;Gestione report&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="30dd5-123">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="30dd5-124">[Carica &#40;della pagina file Gestione report&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="30dd5-124">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 [<span data-ttu-id="30dd5-125">Caricare file in una cartella</span><span class="sxs-lookup"><span data-stu-id="30dd5-125">Upload Files to a Folder</span></span>](../report-server/upload-files-to-a-folder.md)  
  
  
