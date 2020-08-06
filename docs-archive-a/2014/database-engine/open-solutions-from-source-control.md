---
title: Aprire soluzioni dal controllo del codice sorgente | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- opening solutions
- solutions [SQL Server Management Studio], opening
ms.assetid: a96a1f0d-0183-4587-a3b0-4598309cbdd2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 808a4851bcc1f51690b2ba924a859bcccf9a6adb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636860"
---
# <a name="open-solutions-from-source-control"></a><span data-ttu-id="5c5b7-102">Aprire Soluzioni dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="5c5b7-102">Open Solutions from Source Control</span></span>
  <span data-ttu-id="5c5b7-103">Per aprire soluzioni direttamente dal controllo del codice sorgente, è possibile utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5c5b7-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to open solutions directly from source control.</span></span> <span data-ttu-id="5c5b7-104">Quando si esegue questa operazione, viene creata automaticamente una copia della versione più recente dei file della soluzione nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-104">When you do this, the Studio environment creates a copy of the latest version of the solution files at the location you specify.</span></span>  
  
 <span data-ttu-id="5c5b7-105">Se sul disco locale non è presente una copia locale della soluzione, prima di utilizzare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] per estrarre la soluzione o recuperare i file della soluzione sarà necessario aprire il progetto dal controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-105">If a local copy of the solution does not exist on your local disk, you must open the project from source control before you can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to check out the solution or retrieve solution files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5c5b7-106">Se è già disponibile una copia locale della soluzione che si desidera aprire dal controllo del codice sorgente, verrà chiesto di sovrascrivere la copia locale.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-106">If you already have a local copy of the solution you are opening from source control, you are prompted to overwrite the local copy.</span></span>  
  
### <a name="to-open-a-solution-from-source-control"></a><span data-ttu-id="5c5b7-107">Per aprire una soluzione dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="5c5b7-107">To open a solution from source control</span></span>  
  
1.  <span data-ttu-id="5c5b7-108">Scegliere **controllo del codice sorgente**dal menu **file** e fare clic su **Apri dal controllo del codice sorgente**.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-108">On the **File** menu, point to **Source Control**, and click **Open From Source Control**.</span></span>  
  
2.  <span data-ttu-id="5c5b7-109">Se richiesto, accedere a [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-109">If prompted, log on to [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe.</span></span>  
  
3.  <span data-ttu-id="5c5b7-110">Nella finestra di dialogo **Crea progetto locale da SourceSafe** selezionare la cartella che contiene la soluzione che si desidera aprire e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-110">In the **Create local project from SourceSafe** dialog box, select the folder that contains the solution you want to open, and click **OK**.</span></span>  
  
4.  <span data-ttu-id="5c5b7-111">Se una cartella di lavoro per la soluzione esiste già nell'unità disco locale, la casella **Crea un nuovo progetto nella cartella** cambia per identificare la directory locale.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-111">If a working folder for the solution already exists on your local disk drive, the **Create a new project in the folder** box changes to identify the local directory.</span></span> <span data-ttu-id="5c5b7-112">Se non esiste una cartella di lavoro per la soluzione, è possibile digitare o cercare la directory locale nella quale dovrebbe essere aperta la soluzione.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-112">If no working folder for the solution exists, you can type or browse to the local directory in which the solution should be opened.</span></span>  
  
5.  <span data-ttu-id="5c5b7-113">Nella finestra di dialogo **Apri soluzione** selezionare il file della soluzione e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c5b7-113">In the **Open Solution** dialog box, select the solution file, and click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5b7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c5b7-114">See Also</span></span>  
 [<span data-ttu-id="5c5b7-115">Apertura di progetti dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="5c5b7-115">Open Projects from Source Control</span></span>](../../2014/database-engine/open-projects-from-source-control.md)  
  
  
