---
title: Recuperare i file | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- version control services [SQL Server], file retrieval
- file retrieval [SQL Server]
- retrieving files
ms.assetid: 37b74426-e262-43b2-a81f-79b1fd1a36ec
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ebced9ea69f304344893289140687cd6d511e923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636368"
---
# <a name="retrieve-files"></a><span data-ttu-id="73143-102">Recupero di file</span><span class="sxs-lookup"><span data-stu-id="73143-102">Retrieve Files</span></span>
  <span data-ttu-id="73143-103">Dopo aver aperto un progetto incluso nel controllo del codice sorgente, è possibile utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per recuperare le copie locali dei file di progetto dall'archivio del controllo del codice sorgente e salvarle nella directory locale in cui si trova il progetto.</span><span class="sxs-lookup"><span data-stu-id="73143-103">After you have opened a source-controlled project, you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to retrieve local copies of project files from the source control store to the local directory in which the project resides.</span></span>  
  
 <span data-ttu-id="73143-104">È possibile utilizzare il controllo del codice sorgente integrato per recuperare i file nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="73143-104">You can use integrated source control to retrieve files in the following ways:</span></span>  
  
-   <span data-ttu-id="73143-105">Comando per **ottenere la versione più recente (ricorsivo)**</span><span class="sxs-lookup"><span data-stu-id="73143-105">**Get Latest Version (Recursive)** command</span></span>  
  
     <span data-ttu-id="73143-106">Consente di recuperare l'ultima versione archiviata dei file selezionati.</span><span class="sxs-lookup"><span data-stu-id="73143-106">Retrieves the latest checked in version of the selected files.</span></span> <span data-ttu-id="73143-107">Se viene selezionata una soluzione o un progetto, questo comando consente di recuperare l'ultima versione di tutti i file della soluzione o del progetto.</span><span class="sxs-lookup"><span data-stu-id="73143-107">If a solution or project is selected, this command retrieves the latest version of all solution and project files.</span></span>  
  
-   <span data-ttu-id="73143-108">Comando **Get**</span><span class="sxs-lookup"><span data-stu-id="73143-108">**Get** command</span></span>  
  
     <span data-ttu-id="73143-109">Consente di visualizzare la finestra di dialogo **Ottieni** , che consente di recuperare la versione più recente di un file selezionato oppure di recuperare un subset dei file della soluzione o del progetto selezionato.</span><span class="sxs-lookup"><span data-stu-id="73143-109">Displays the **Get** dialog box, which you can use to retrieve the latest version of a selected file, or to retrieve a subset of the files in the selected solution or project.</span></span>  
  
### <a name="to-retrieve-the-latest-version-of-all-the-files-in-a-project"></a><span data-ttu-id="73143-110">Per recuperare l'ultima versione di tutti i file in un progetto</span><span class="sxs-lookup"><span data-stu-id="73143-110">To retrieve the latest version of all the files in a project</span></span>  
  
1.  <span data-ttu-id="73143-111">In Esplora soluzioni selezionare il progetto.</span><span class="sxs-lookup"><span data-stu-id="73143-111">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="73143-112">Scegliere **controllo del codice sorgente**dal menu **file** e quindi fare clic su **Ottieni ultima versione (ricorsivo)**.</span><span class="sxs-lookup"><span data-stu-id="73143-112">On the **File** menu, point to **Source Control**, and then click **Get Latest Version (Recursive)**.</span></span>  
  
 <span data-ttu-id="73143-113">Le versioni più recenti dei file nel progetto verranno recuperate nel percorso del progetto sul disco locale.</span><span class="sxs-lookup"><span data-stu-id="73143-113">The most recent versions of the files in the project are retrieved to the project location on your local disk.</span></span>  
  
#### <a name="to-retrieve-only-certain-files-in-a-project"></a><span data-ttu-id="73143-114">Per recuperare solo alcuni file in un progetto</span><span class="sxs-lookup"><span data-stu-id="73143-114">To retrieve only certain files in a project</span></span>  
  
1.  <span data-ttu-id="73143-115">In Esplora soluzioni selezionare l'elemento che si desidera recuperare.</span><span class="sxs-lookup"><span data-stu-id="73143-115">In Solution Explorer, select the item you want to retrieve.</span></span>  
  
2.  <span data-ttu-id="73143-116">Scegliere **controllo del codice sorgente**dal menu **file** e quindi fare clic su **Ottieni**.</span><span class="sxs-lookup"><span data-stu-id="73143-116">On the **File** menu, point to **Source Control**, and then click **Get**.</span></span>  
  
3.  <span data-ttu-id="73143-117">Nella finestra di dialogo **Ottieni** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="73143-117">In the **Get** dialog box, click **OK**.</span></span> <span data-ttu-id="73143-118">In alternativa, se in Esplora soluzioni è stato selezionato un progetto o una soluzione, deselezionare le caselle di controllo accanto agli elementi che non si desidera recuperare.</span><span class="sxs-lookup"><span data-stu-id="73143-118">Alternatively, if you selected a solution or project in Solution Explorer, clear the check boxes that appear next to the items you do not want to retrieve.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73143-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73143-119">See Also</span></span>  
 <span data-ttu-id="73143-120">[Finestra di dialogo Get &#40;controllo del codice sorgente&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="73143-120">[Get Dialog Box &#40;Source Control&#41;](../../2014/database-engine/get-dialog-box-source-control.md) </span></span>  
 <span data-ttu-id="73143-121">[Impostare e recuperare le informazioni sulla versione](../../2014/database-engine/set-and-retrieve-version-information.md) </span><span class="sxs-lookup"><span data-stu-id="73143-121">[Set and Retrieve Version Information](../../2014/database-engine/set-and-retrieve-version-information.md) </span></span>  
 <span data-ttu-id="73143-122">[Visualizza cronologia progetto](../../2014/database-engine/view-project-history.md) </span><span class="sxs-lookup"><span data-stu-id="73143-122">[View Project History](../../2014/database-engine/view-project-history.md) </span></span>  
 [<span data-ttu-id="73143-123">Visualizzazione dello stato dei file</span><span class="sxs-lookup"><span data-stu-id="73143-123">View File Status</span></span>](../../2014/database-engine/view-file-status.md)  
  
  
