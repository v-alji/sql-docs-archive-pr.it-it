---
title: Importare i criteri in un'istanza singola | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: bc5bcd87-663f-41d9-bb7b-b3e083cd63df
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0464bc6f4dcd6326a4b8f222cb4b3128f21561ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724300"
---
# <a name="import-the-policies-to-a-single-instance"></a><span data-ttu-id="e1297-102">Importazione dei criteri in un'istanza singola</span><span class="sxs-lookup"><span data-stu-id="e1297-102">Import the Policies to a Single Instance</span></span>
  <span data-ttu-id="e1297-103">In questa attività verrà eseguita l'importazione dei criteri per procedure consigliate che si desidera pianificare nella gestione basata su criteri in una singola istanza di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1297-103">In this task, you will import the best practices policies that you want to schedule into Policy-Based Management on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e1297-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e1297-104">Prerequisites</span></span>  
 <span data-ttu-id="e1297-105">È necessario eseguire questa procedura in un server che esegue [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] o una versione successiva.</span><span class="sxs-lookup"><span data-stu-id="e1297-105">You must perform this procedure on a server that is running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span>  
  
### <a name="import-the-best-practices-policies-for-the-database-engine"></a><span data-ttu-id="e1297-106">Importazione dei criteri per procedure consigliate per il Motore di database</span><span class="sxs-lookup"><span data-stu-id="e1297-106">Import the best practices policies for the Database Engine</span></span>  
  
1.  <span data-ttu-id="e1297-107">Avviare [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], quindi connettersi al [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1297-107">Start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="e1297-108">In Esplora oggetti espandere **gestione**, quindi **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="e1297-108">In Object Explorer, expand **Management**, and then expand **Policy Management**.</span></span>  
  
3.  <span data-ttu-id="e1297-109">Fare clic con il pulsante destro del mouse su **criteri**, quindi scegliere **Importa criterio**.</span><span class="sxs-lookup"><span data-stu-id="e1297-109">Right-click **Policies**, and then click **Import Policy**.</span></span>  
  
4.  <span data-ttu-id="e1297-110">Nella finestra di dialogo **Importa** fare clic sul pulsante con i puntini di sospensione (**..**.) accanto alla casella **file da importare** .</span><span class="sxs-lookup"><span data-stu-id="e1297-110">In the **Import** dialog box, next to the **Files to import** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="e1297-111">Nell'elenco **Cerca in** passare alla cartella seguente, che contiene i criteri per procedure consigliate:</span><span class="sxs-lookup"><span data-stu-id="e1297-111">In the **Look in** list, browse to the following folder, which contains the best practices policies:</span></span>  
  
     <span data-ttu-id="e1297-112">**C:\Programmi (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="e1297-112">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e1297-113">Il percorso del file può variare in base alla posizione in cui sono stati installati i file di programma di [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], all'esecuzione di un sistema operativo a 32 o a 64 bit e all'identificatore di lingua.</span><span class="sxs-lookup"><span data-stu-id="e1297-113">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
6.  <span data-ttu-id="e1297-114">Nella finestra di dialogo **Seleziona criterio** selezionare uno o più file di criteri.</span><span class="sxs-lookup"><span data-stu-id="e1297-114">In the **Select Policy** dialog box, select one or more policy files.</span></span>  
  
     <span data-ttu-id="e1297-115">Per selezionare file non adiacenti, fare clic su un file, tenere premuto il tasto CTRL, quindi fare clic su ogni file aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="e1297-115">To select nonadjacent files, click one file, hold down the CTRL key, and then click each additional file.</span></span> <span data-ttu-id="e1297-116">Per selezionare file adiacenti, fare clic sul primo file nella sequenza, tenere premuto il tasto MAIUSC, quindi fare clic sull'ultimo file.</span><span class="sxs-lookup"><span data-stu-id="e1297-116">To select adjacent files, click the first file in the sequence, hold down the SHIFT key, and then click the last file.</span></span>  
  
7.  <span data-ttu-id="e1297-117">Al termine della selezione dei file, fare clic su **Apri**.</span><span class="sxs-lookup"><span data-stu-id="e1297-117">When you are finished selecting files, click **Open**.</span></span>  
  
8.  <span data-ttu-id="e1297-118">Nella finestra di dialogo **Importa** verificare che l'elenco **stato criteri** sia impostato **su Mantieni lo stato dei criteri durante l'importazione** (impostazione predefinita), quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1297-118">In the **Import** dialog box, make sure that the **Policy state** list is set to **Preserve policy state on import** (the default), and then click **OK**.</span></span>  
  
     <span data-ttu-id="e1297-119">I criteri vengono importati nel nodo **criteri** in **Gestione criteri**.</span><span class="sxs-lookup"><span data-stu-id="e1297-119">The policies are imported into the **Policies** node under **Policy Management**.</span></span> <span data-ttu-id="e1297-120">Per impostazione predefinita, i criteri importati sono impostati sulla modalità di valutazione "Su richiesta".</span><span class="sxs-lookup"><span data-stu-id="e1297-120">By default, the imported policies are set to "On demand" evaluation mode.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e1297-121">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e1297-121">Next Steps</span></span>  
 [<span data-ttu-id="e1297-122">Pianificazione criteri</span><span class="sxs-lookup"><span data-stu-id="e1297-122">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
  
