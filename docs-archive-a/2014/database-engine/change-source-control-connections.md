---
title: Modificare le connessioni del controllo del codice sorgente | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server Management Studio], source controls
- source controls [SQL Server Management Studio], connections
ms.assetid: 538e3beb-f99c-4095-bd65-6413e872d26e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 077a09cdca0c0aff777184f04467ca39592690aa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630074"
---
# <a name="change-source-control-connections"></a><span data-ttu-id="4b4c3-102">Modifica delle connessioni del controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="4b4c3-102">Change Source Control Connections</span></span>
  <span data-ttu-id="4b4c3-103">La prima volta che viene aggiunta o aperta una soluzione dal controllo del codice sorgente, il provider del controllo crea un'associazione tra la cartella radice della directory della soluzione locale e la cartella corrispondente del server.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-103">The first time you add or open a solution from source control, your source control provider creates an association between the root folder of the local solution directory and its corresponding server folder.</span></span>  
  
 <span data-ttu-id="4b4c3-104">La cartella radice, chiamata anche radice unificata, risiede nel client.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-104">The root folder (also called unified root) resides on the client.</span></span> <span data-ttu-id="4b4c3-105">Sotto di essa si trovano tutti i file a cui fa riferimento una soluzione o un progetto.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-105">It is the folder beneath which all the files referenced by a solution or project can be found.</span></span> <span data-ttu-id="4b4c3-106">Per trovare l'ultima versione di una soluzione, la cronologia e le informazioni sullo stato, individuare la cartella che si trova nel server del controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-106">To find the latest version of a solution, its history, and its status information, locate the server folder, which resides on the source control server.</span></span> <span data-ttu-id="4b4c3-107">In [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, le cartelle del server sono denominate progetti.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-107">In [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual SourceSafe, server folders are called projects.</span></span>  
  
 <span data-ttu-id="4b4c3-108">In molti casi è necessario disassociare o disconnettere una soluzione dalla sua cartella del server.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-108">In many situations, you need to unbind or disconnect a solution from its server folder.</span></span> <span data-ttu-id="4b4c3-109">Se, ad esempio, il computer in cui si trova il provider del controllo del codice sorgente non è disponibile, è possibile connettersi a un computer di backup, riassociare la soluzione a una cartella del server sottoposta a backup e riprendere a lavorare normalmente.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-109">For example, if the computer on which your source control provider resides is unavailable, you can connect to a backup computer, rebind your solution to a backed-up server folder, and resume working normally.</span></span> <span data-ttu-id="4b4c3-110">Se un progetto di controllo del codice sorgente è inoltre duplicato, potrebbe essere necessario associare la soluzione alla cartella del server in cui si trova la nuova versione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-110">Also, if a source control project is forked, you may have to bind your solution to the server folder where the new project version resides.</span></span>  
  
 <span data-ttu-id="4b4c3-111">Utilizzare l'interfaccia utente del provider del controllo del codice sorgente per cambiare la cartella del server alla quale è associata una soluzione.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-111">Use the user interface of the source control provider to change the server folder that a solution is bound to.</span></span> <span data-ttu-id="4b4c3-112">È possibile aprire l'interfaccia utente del controllo del codice sorgente dall'ambiente [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4b4c3-112">You can open the source control user interface from within the [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span>  
  
#### <a name="to-open-the-source-control-user-interface-from-the-studio-environment"></a><span data-ttu-id="4b4c3-113">Per aprire l'interfaccia utente del controllo del codice sorgente dall'ambiente Studio</span><span class="sxs-lookup"><span data-stu-id="4b4c3-113">To open the source control user interface from the Studio environment</span></span>  
  
1.  <span data-ttu-id="4b4c3-114">Scegliere **controllo del codice sorgente**dal menu **file** e quindi fare clic su **avvia Microsoft Visual SourceSafe**.</span><span class="sxs-lookup"><span data-stu-id="4b4c3-114">On the **File** menu, point to **Source Control**, and then click **Launch Microsoft Visual SourceSafe**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b4c3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b4c3-115">See Also</span></span>  
 <span data-ttu-id="4b4c3-116">[Nozioni fondamentali sul controllo del codice sorgente](../../2014/database-engine/source-control-basics.md) </span><span class="sxs-lookup"><span data-stu-id="4b4c3-116">[Source Control Basics](../../2014/database-engine/source-control-basics.md) </span></span>  
 <span data-ttu-id="4b4c3-117">[Impostare le opzioni di controllo del codice sorgente](../../2014/database-engine/set-source-control-options.md) </span><span class="sxs-lookup"><span data-stu-id="4b4c3-117">[Set Source Control Options](../../2014/database-engine/set-source-control-options.md) </span></span>  
 [<span data-ttu-id="4b4c3-118">Esclusione di file dal controllo del codice sorgente</span><span class="sxs-lookup"><span data-stu-id="4b4c3-118">Exclude Files from Source Control</span></span>](../../2014/database-engine/exclude-files-from-source-control.md)  
  
  
