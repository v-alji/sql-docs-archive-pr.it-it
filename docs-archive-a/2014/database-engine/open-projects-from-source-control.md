---
title: Apri progetti dal controllo del codice sorgente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- projects [SQL Server Management Studio], opening
- opening projects
ms.assetid: 942f93a3-e264-4ec4-ba72-a28e0509a527
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 944b121516e3782e35e213e165405b0ecceb7456
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636862"
---
# <a name="open-projects-from-source-control"></a><span data-ttu-id="4554f-102">Apertura di progetti dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="4554f-102">Open Projects from Source Control</span></span>
  <span data-ttu-id="4554f-103">È possibile utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per aprire i progetti direttamente dal controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="4554f-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open projects directly from source control.</span></span> <span data-ttu-id="4554f-104">Quando si esegue questa operazione, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Recupera la versione più recente del progetto e la copia nel disco locale.</span><span class="sxs-lookup"><span data-stu-id="4554f-104">When you do this, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] retrieves the latest version of the project and copies it to your local disk.</span></span> <span data-ttu-id="4554f-105">Nell'ambiente [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] viene inoltre creata automaticamente una soluzione per il progetto.</span><span class="sxs-lookup"><span data-stu-id="4554f-105">The [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] environment also creates a solution for the project automatically.</span></span>  
  
 <span data-ttu-id="4554f-106">Dopo aver aperto un progetto dal controllo del codice sorgente, è possibile estrarre e modificare i file di progetto.</span><span class="sxs-lookup"><span data-stu-id="4554f-106">After you have opened a project from source control, you can check out and modify the project files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4554f-107">Utilizzare la procedura seguente una sola volta.</span><span class="sxs-lookup"><span data-stu-id="4554f-107">The following procedure should only be used once.</span></span> <span data-ttu-id="4554f-108">Successivamente, è necessario aprire il progetto come qualsiasi altro progetto (scegliendo **file**, **Apri**, quindi **progetto**).</span><span class="sxs-lookup"><span data-stu-id="4554f-108">Thereafter, you should open the project like any other project (by clicking **File**, **Open**, and then **Project**).</span></span>  
  
### <a name="to-open-a-project-from-source-control"></a><span data-ttu-id="4554f-109">Per aprire un progetto dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="4554f-109">To open a project from source control</span></span>  
  
1.  <span data-ttu-id="4554f-110">Scegliere **controllo del codice sorgente**dal menu **file** e fare clic su **Apri dal controllo del codice sorgente**.</span><span class="sxs-lookup"><span data-stu-id="4554f-110">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="4554f-111">Se richiesto, accedere a [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="4554f-111">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="4554f-112">Nella finestra di dialogo **Crea progetto locale da SourceSafe** aprire la cartella che contiene il progetto da aprire.</span><span class="sxs-lookup"><span data-stu-id="4554f-112">In the **Create local project from SourceSafe** dialog box, open the folder that contains the project to open.</span></span>  
  
4.  <span data-ttu-id="4554f-113">La casella **Crea un nuovo progetto nella cartella** cambia per identificare la directory locale in cui verrà creato il progetto.</span><span class="sxs-lookup"><span data-stu-id="4554f-113">The **Create a new project in the folder** box changes to identify the local directory in which the project will be created.</span></span> <span data-ttu-id="4554f-114">Se si vuole inserire il progetto in una directory diversa, digitare il percorso della directory o usare il pulsante **Sfoglia** per individuare la directory nel disco locale.</span><span class="sxs-lookup"><span data-stu-id="4554f-114">If you want to place the project in a different directory, type the path to the directory or use the **Browse** button to locate the directory on your local disk.</span></span>  
  
5.  <span data-ttu-id="4554f-115">Nella **casella Crea un nuovo progetto nella cartella**verificare che sia visualizzata la cartella corretta, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4554f-115">In the **Create a new project in the folder box**, verify that the correct folder is displayed, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="4554f-116">Nella finestra di dialogo **Apri soluzione** selezionare il progetto che si desidera aprire e fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="4554f-116">In the **Open Solution** dialog box, select the project you want to open, and click **Open**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4554f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4554f-117">See Also</span></span>  
 <span data-ttu-id="4554f-118">[Apri soluzioni e progetti dal controllo del codice sorgente](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span><span class="sxs-lookup"><span data-stu-id="4554f-118">[Open Solutions and Projects from Source Control](../../2014/database-engine/open-solutions-and-projects-from-source-control.md) </span></span>  
 [<span data-ttu-id="4554f-119">Aprire Soluzioni dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="4554f-119">Open Solutions from Source Control</span></span>](../../2014/database-engine/open-solutions-from-source-control.md)  
  
  
