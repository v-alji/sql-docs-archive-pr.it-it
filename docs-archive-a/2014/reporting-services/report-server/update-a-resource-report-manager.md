---
title: Aggiornare una risorsa (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- updating resources
- resources [Reporting Services], updating
ms.assetid: d21f7493-bcf7-4e9e-9886-55ebdc1f1037
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a0fca59e476c2820b715ff46729784edc562f74d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628322"
---
# <a name="update-a-resource-report-manager"></a><span data-ttu-id="86ae3-102">Aggiornare una risorsa (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="86ae3-102">Update a Resource (Report Manager)</span></span>
  <span data-ttu-id="86ae3-103">L'aggiornamento di una risorsa viene eseguito mediante la sostituzione con una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="86ae3-103">You can update a resource by replacing it with a newer version.</span></span> <span data-ttu-id="86ae3-104">Le risorse sono elementi archiviati in un server di report che includono contenuto da un file caricato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="86ae3-104">Resources are items stored on a report server that contain content from a file that you upload.</span></span> <span data-ttu-id="86ae3-105">È possibile sostituire una risorsa esistente mediante l'importazione di contenuto di file diverso o nuovo nella risorsa esistente.</span><span class="sxs-lookup"><span data-stu-id="86ae3-105">You can replace an existing resource by importing new or different file content into the existing resource.</span></span> <span data-ttu-id="86ae3-106">Con l'aggiornamento di una risorsa è possibile aggiornare contenuto mantenendo le proprietà e le impostazioni di sicurezza esistenti nella risorsa.</span><span class="sxs-lookup"><span data-stu-id="86ae3-106">Updating a resource provides a way to update content while preserving existing properties and security settings on the resource.</span></span>  
  
### <a name="to-update-a-resource"></a><span data-ttu-id="86ae3-107">Per aggiornare una risorsa</span><span class="sxs-lookup"><span data-stu-id="86ae3-107">To update a resource</span></span>  
  
1.  <span data-ttu-id="86ae3-108">Avviare [Gestione report &#40;modalità nativa SSRS&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="86ae3-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="86ae3-109">In Gestione report passare alla risorsa che si desidera aggiornare oppure eseguirne la ricerca.</span><span class="sxs-lookup"><span data-stu-id="86ae3-109">In Report Manager, navigate to or search for the resource you want to update.</span></span>  
  
3.  <span data-ttu-id="86ae3-110">Fare clic sulla risorsa per aprirla nella pagina **Visualizza** .</span><span class="sxs-lookup"><span data-stu-id="86ae3-110">Click the resource to open it in the **View** page.</span></span>  
  
4.  <span data-ttu-id="86ae3-111">Fare clic su **Proprietà** per aprire la pagina delle proprietà **Generale** .</span><span class="sxs-lookup"><span data-stu-id="86ae3-111">Click **Properties** to open the **General** properties page.</span></span>  
  
5.  <span data-ttu-id="86ae3-112">Fare clic su **Sostituisci** per aprire la pagina **Importa risorsa** .</span><span class="sxs-lookup"><span data-stu-id="86ae3-112">Click **Replace** to open the **Import Resource** page.</span></span>  
  
6.  <span data-ttu-id="86ae3-113">Fare clic su **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="86ae3-113">Click **Browse**.</span></span>  
  
7.  <span data-ttu-id="86ae3-114">Selezionare il file che si desidera utilizzare per sostituire la ricorsa corrente.</span><span class="sxs-lookup"><span data-stu-id="86ae3-114">Select the file that you want to use to replace the current resource.</span></span> <span data-ttu-id="86ae3-115">È possibile utilizzare una risorsa aggiornata del file di risorse oppure specificare un file con un nome o un tipo di file diverso.</span><span class="sxs-lookup"><span data-stu-id="86ae3-115">You can use an updated version of the resource file, or specify a file with a different name or file type.</span></span>  
  
8.  <span data-ttu-id="86ae3-116">Fare clic su **OK** per caricare il file di risorse, chiudere la pagina **Importa risorsa** e quindi salvare le modifiche apportate al server di report.</span><span class="sxs-lookup"><span data-stu-id="86ae3-116">Click **OK** to upload the resource file, close the **Import Resource** page, and save your changes to the report server.</span></span>  
  
 <span data-ttu-id="86ae3-117">Se la risorsa in corso di aggiornamento contiene un'immagine utilizzata nel report, per visualizzare l'immagine aggiornata sarà necessario aggiornare il report.</span><span class="sxs-lookup"><span data-stu-id="86ae3-117">If the resource you are updating contains an image that is used in a report, you need to refresh the report to see the updated image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86ae3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86ae3-118">See Also</span></span>  
 <span data-ttu-id="86ae3-119">[Pagina contenuti &#40;Gestione report&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="86ae3-119">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="86ae3-120">[Carica &#40;della pagina file Gestione report&#41;](../upload-file-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="86ae3-120">[Upload File Page &#40;Report Manager&#41;](../upload-file-page-report-manager.md) </span></span>  
 <span data-ttu-id="86ae3-121">[Caricare file in una cartella](upload-files-to-a-folder.md) </span><span class="sxs-lookup"><span data-stu-id="86ae3-121">[Upload Files to a Folder](upload-files-to-a-folder.md) </span></span>  
 [<span data-ttu-id="86ae3-122">Guida sensibile al contesto di Gestione report</span><span class="sxs-lookup"><span data-stu-id="86ae3-122">Report Manager F1 Help</span></span>](../report-manager-f1-help.md)  
  
  
