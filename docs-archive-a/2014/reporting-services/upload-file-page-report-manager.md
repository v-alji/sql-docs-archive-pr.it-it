---
title: Pagina carica file (Gestione report) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7bb3166f-9374-4449-b66a-ffb77298507d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: de03c6c6bd03cbe083d5e1edfd320264d2cc3bde
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719404"
---
# <a name="upload-file-page-report-manager"></a><span data-ttu-id="3a9cc-102">Pagina Carica file (Gestione report)</span><span class="sxs-lookup"><span data-stu-id="3a9cc-102">Upload File Page (Report Manager)</span></span>
  <span data-ttu-id="3a9cc-103">La pagina Carica file consente di pubblicare un file dal file system nel database del server di report.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-103">Use the Upload File page to publish a file from the file system into the report server database.</span></span> <span data-ttu-id="3a9cc-104">I file caricati vengono rappresentati come elementi nella gerarchia di cartelle del server di report.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-104">Uploaded files are represented as items in the report server folder hierarchy.</span></span>  
  
-   <span data-ttu-id="3a9cc-105">I file con estensione rdl caricati vengono pubblicati come report in un server di report.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-105">Uploaded .rdl files are published to a report server as reports.</span></span>  
  
-   <span data-ttu-id="3a9cc-106">I file caricati con estensione smdl vengono pubblicati come modelli di report se includono informazioni sulla vista origine dati.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-106">Uploaded .smdl files are published as report models if they contain data source view information.</span></span> <span data-ttu-id="3a9cc-107">Se tali file non contengono alcun riferimento alla vista origine dati, si verificherà un errore durante il caricamento.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-107">If they are missing a data source view reference, an error occurs during the upload.</span></span> <span data-ttu-id="3a9cc-108">Se si carica un file con estensione smdl da un [!INCLUDE[msCoName](../includes/msconame-md.md)] progetto modello di report, è possibile che le informazioni sulla vista origine dati risultino mancanti [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3a9cc-108">Data source view information might be missing if you upload an .smdl file from a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] report model project.</span></span> <span data-ttu-id="3a9cc-109">Nei progetti modello di report le informazioni relative alla vista origine dati vengono archiviate in un file separato anziché direttamente nel file con estensione smdl.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-109">In report model projects, data source view information is stored in a separate file rather than in the .smdl file itself.</span></span>  
  
     <span data-ttu-id="3a9cc-110">I file modello che contengono informazioni sulla vista origine dati, e che pertanto è possibile caricare, sono i file che sono stati pubblicati in precedenza in un server di report, quindi salvati in un file nel file system.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-110">Model files that do contain data source view information (and can therefore be successfully uploaded) are those that have been previously published to a report server and then saved from the server to a file on the file system.</span></span> <span data-ttu-id="3a9cc-111">Se si apre la pagina delle proprietà Generale di un modello e si fa clic su **Modifica** per aprire il modello, è possibile salvarlo in un file e quindi caricare il file come nuovo modello nel server di report.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-111">If you open the General Properties page of a model and click **Edit** to open the model, you can save it to a file and then upload it as a new model on the report server.</span></span> <span data-ttu-id="3a9cc-112">Nel file con estensione smdl caricato successivamente saranno disponibili tutte le informazioni necessarie per la pubblicazione del modello.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-112">The .smdl file that you subsequently upload will have all of information that is necessary for model publication.</span></span>  
  
-   <span data-ttu-id="3a9cc-113">Tutti gli altri tipi di file caricati vengono archiviati come risorse,</span><span class="sxs-lookup"><span data-stu-id="3a9cc-113">All other file types that you upload are stored as resources.</span></span> <span data-ttu-id="3a9cc-114">inclusi i file con estensione rds che contengono informazioni di connessione all'origine dati del report.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-114">This includes .rds files that contain report data source connection information.</span></span> <span data-ttu-id="3a9cc-115">Il caricamento di un file rds non comporta la creazione di un'origine dei dati condivisa nel server di report.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-115">Uploading an .rds file does not produce a shared data source item on the report server.</span></span>  
  
 <span data-ttu-id="3a9cc-116">Quando si carica un elemento, questo viene inserito nella cartella corrente.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-116">When you upload an item, it is placed in the current folder.</span></span> <span data-ttu-id="3a9cc-117">Dopo il caricamento, l'elemento può essere spostato in percorsi diversi.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-117">After the upload is complete, you can move the item to a different location.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3a9cc-118">Questa funzionalità non è disponibile in ogni edizione di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3a9cc-118">This feature is not available in every edition of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3a9cc-119">Per un elenco delle funzionalità supportate dalle edizioni di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], vedere [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="3a9cc-119">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../2014/getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="3a9cc-120">Spostamento</span><span class="sxs-lookup"><span data-stu-id="3a9cc-120">Navigation</span></span>  
 <span data-ttu-id="3a9cc-121">Utilizzare la procedura riportata di seguito per navigare fino a questo percorso nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-121">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
### <a name="to-open-the-upload-file-page"></a><span data-ttu-id="3a9cc-122">Per aprire la pagina Carica file</span><span class="sxs-lookup"><span data-stu-id="3a9cc-122">To open the Upload File page</span></span>  
  
1.  <span data-ttu-id="3a9cc-123">Aprire Gestione report e navigare fino alla cartella in cui si desidera caricare un file.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-123">Open Report Manager, and navigate to the folder in which you want to upload a file.</span></span>  
  
2.  <span data-ttu-id="3a9cc-124">Nella barra degli strumenti fare clic su **Carica file**.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-124">In the toolbar, click **Upload File**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3a9cc-125">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3a9cc-125">Options</span></span>  
 <span data-ttu-id="3a9cc-126">**File da caricare**</span><span class="sxs-lookup"><span data-stu-id="3a9cc-126">**File to Upload**</span></span>  
 <span data-ttu-id="3a9cc-127">Consente di visualizzare il percorso completo del file copiato dal file system.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-127">Displays the fully qualified path to the file you are copying from the file system.</span></span>  
  
 <span data-ttu-id="3a9cc-128">**Sfoglia**</span><span class="sxs-lookup"><span data-stu-id="3a9cc-128">**Browse**</span></span>  
 <span data-ttu-id="3a9cc-129">Fare clic per selezionare un file nel file system.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-129">Click to choose a file from the file system.</span></span>  
  
 <span data-ttu-id="3a9cc-130">**Nome**</span><span class="sxs-lookup"><span data-stu-id="3a9cc-130">**Name**</span></span>  
 <span data-ttu-id="3a9cc-131">Consente di digitare il nome del file nel modo in cui si desidera venga visualizzato nello spazio dei nomi del server di report.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-131">Type the name of the file, as it will appear in the report server namespace.</span></span> <span data-ttu-id="3a9cc-132">Il nome deve includere almeno un carattere alfanumerico.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-132">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="3a9cc-133">È inoltre possibile utilizzare spazi e alcuni simboli.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-133">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="3a9cc-134">Non utilizzare i caratteri ; ?</span><span class="sxs-lookup"><span data-stu-id="3a9cc-134">Do not use the characters ; ?</span></span> <span data-ttu-id="3a9cc-135">: \@ & = +, $ \* \< > | "o/quando si specifica un nome di elemento.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-135">: \@ & = + , $ \* \< > | " or / when specifying an item name.</span></span>  
  
 <span data-ttu-id="3a9cc-136">**Sovrascrivi se esistente**</span><span class="sxs-lookup"><span data-stu-id="3a9cc-136">**Overwrite item if it exists**</span></span>  
 <span data-ttu-id="3a9cc-137">Selezionare questa casella di controllo se si desidera sostituire un elemento esistente con una versione più recente.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-137">Select this check box if you want to replace an existing item with a newer version.</span></span> <span data-ttu-id="3a9cc-138">Per sovrascrivere la versione esistente è necessario che i nomi del nuovo elemento e dell'elemento esistente siano identici.</span><span class="sxs-lookup"><span data-stu-id="3a9cc-138">To overwrite an existing version, the name of the new item and the existing item must be an exact match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a9cc-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a9cc-139">See Also</span></span>  
 <span data-ttu-id="3a9cc-140">[Gestione report &#40;modalità nativa SSRS&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span><span class="sxs-lookup"><span data-stu-id="3a9cc-140">[Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md) </span></span>  
 <span data-ttu-id="3a9cc-141">[Pagina contenuti &#40;Gestione report&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="3a9cc-141">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="3a9cc-142">[Guida sensibile al contesto Gestione report](../../2014/reporting-services/report-manager-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3a9cc-142">[Report Manager F1 Help](../../2014/reporting-services/report-manager-f1-help.md) </span></span>  
 [<span data-ttu-id="3a9cc-143">Caricare file in una cartella</span><span class="sxs-lookup"><span data-stu-id="3a9cc-143">Upload Files to a Folder</span></span>](report-server/upload-files-to-a-folder.md)  
  
  
