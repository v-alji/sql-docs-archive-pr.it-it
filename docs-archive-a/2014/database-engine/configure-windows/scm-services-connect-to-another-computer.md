---
title: Connettersi a un altro computer (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], other computers
ms.assetid: c4c1e94f-4f5f-431e-8b5b-d5ff97baf723
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3d478cebc1ca36ccb8f87b0355b7c8fe0a928cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87638098"
---
# <a name="connect-to-another-computer-sql-server-configuration-manager"></a><span data-ttu-id="b6b9b-102">Connessione a un altro computer (Gestione configurazione SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b6b9b-102">Connect to Another Computer (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="b6b9b-103">In questo argomento viene illustrato come connettersi a un altro computer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b6b9b-103">This topic describes how to connect to another computer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="b6b9b-104">Attenersi alla prima procedura per aprire Gestione computer di Windows, [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (MMC), connettersi al computer ed espandere l'albero Servizi e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-104">Follow the first procedure to open the Windows Computer Management [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console (mmc), connect to the computer, and expand the Services and Applications tree.</span></span> <span data-ttu-id="b6b9b-105">Seguire la seconda procedura per creare un file con un collegamento a Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un computer remoto.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-105">Follow the second procedure to create a file with a link to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6b9b-106">Alcune azioni non possono essere eseguite da Configuration Manager quando si effettua la connessione in remoto.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-106">Some actions cannot be performed by Configuration Manager when connecting remotely.</span></span>  
  
 <span data-ttu-id="b6b9b-107">Per avviare, arrestare, sospendere o riprendere i servizi in un altro computer, è inoltre possibile connettersi al server tramite [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], fare clic con il pulsante destro del mouse sul server o su [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent e quindi scegliere l'operazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-107">To start, stop, pause, or resume services on another computer, you can also connect to the server with [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click the server or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent and then click the desired action.</span></span>  
  
##  <a name="SSMSProcedure"></a>  
  
#### <a name="to-connect-to-another-computer-with-windows-computer-management"></a><span data-ttu-id="b6b9b-108">Per connettersi a un altro computer utilizzando Gestione computer di Windows</span><span class="sxs-lookup"><span data-stu-id="b6b9b-108">To connect to another computer with Windows Computer Management</span></span>  
  
1.  <span data-ttu-id="b6b9b-109">Nel menu **Start** fare clic con il pulsante destro del mouse su **Risorse del computer**e quindi scegliere **Gestione**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-109">On the **Start** menu, right-click **My Computer**, and then click **Manage.**</span></span>  
  
2.  <span data-ttu-id="b6b9b-110">In **Gestione computer**fare clic con il pulsante destro del mouse su **Gestione computer (locale)** e quindi scegliere **Connetti a un altro computer**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-110">In **Computer Management**, right-click **Computer Management (Local)**, and then click **Connect to another computer**.</span></span>  
  
3.  <span data-ttu-id="b6b9b-111">Nella finestra di dialogo **Seleziona computer** digitare il nome del computer che si vuole gestire nella casella di testo **Altro computer** quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-111">In the **Select Computer** dialog box, in the **Another computer** text box, type the name of the computer you want to manage, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b6b9b-112">Gestione computer visualizza i servizi in esecuzione nel computer remoto.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-112">Computer Management displays the services running on the remote computer.</span></span> <span data-ttu-id="b6b9b-113">Il nodo di primo livello diventa **Gestione computer** \<*remotecomputer*>.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-113">The top-level node changes to **Computer Management** \<*remotecomputer*>.</span></span>  
  
4.  <span data-ttu-id="b6b9b-114">Nell'albero della console espandere **Servizi e applicazioni**e quindi espandere **Gestione configurazione SQL Server** per gestire i servizi del computer remoto.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-114">In the console tree, expand **Services and Applications**, and then expand **SQL Server Configuration Manager** to manage the remote computer's services.</span></span>  
  
#### <a name="to-save-a-link-to-sql-server-configuration-manager-for-another-computer"></a><span data-ttu-id="b6b9b-115">Per salvare un collegamento a Gestione configurazione SQL Server da un altro computer</span><span class="sxs-lookup"><span data-stu-id="b6b9b-115">To save a link to SQL Server Configuration Manager for another computer</span></span>  
  
1.  <span data-ttu-id="b6b9b-116">Fare clic sul menu **Start** e scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-116">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b6b9b-117">Nella casella **Apri** Digitare `mmc -a` per aprire la console di [!INCLUDE[msCoName](../../includes/msconame-md.md)] gestione in modalità autore.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-117">In the **Open** box, type `mmc -a` to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console in author mode.</span></span>  
  
3.  <span data-ttu-id="b6b9b-118">Scegliere **Aggiungi/Rimuovi snap-in** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-118">On the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
4.  <span data-ttu-id="b6b9b-119">Nella finestra **Aggiungi/Rimuovi snap-in** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-119">In the **Add/Remove Snap-in** window, click **Add**.</span></span>  
  
5.  <span data-ttu-id="b6b9b-120">Nella finestra **Aggiungi snap-in autonomo** fare clic su **Gestione computer** e quindi su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-120">In the **Add Standalone Snap-in** window, click **Computer Management** and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="b6b9b-121">Nella finestra **Gestione computer** fare clic su **Altro computer**, digitare il nome del computer remoto da gestire e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-121">In the **Computer Management** window, click **Another computer**, type the name of the remote computer you wish to manage, and then click **Finish**.</span></span>  
  
7.  <span data-ttu-id="b6b9b-122">Nella finestra **Aggiungi snap-in autonomo** fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-122">In the **Add Standalone Snap-in** window, click **Close**.</span></span>  
  
8.  <span data-ttu-id="b6b9b-123">Nella finestra **Aggiungi/Rimuovi snap-in** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-123">In the **Add/Remove Snap-in** window, click **OK**.</span></span>  
  
9. <span data-ttu-id="b6b9b-124">Espandere **Gestione computer ( ***\<computer name>*** )** e **Servizi e applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-124">Expand **Computer Management (***\<computer name>***)**, and **Services and Applications**.</span></span>  
  
10. <span data-ttu-id="b6b9b-125">Fare clic con il pulsante destro del mouse su **Gestione configurazione SQL Server**e quindi scegliere **Nuova finestra da qui**.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-125">Right-click **SQL Server Configuration Manager**, and then click **New Window from here**.</span></span>  
  
11. <span data-ttu-id="b6b9b-126">Scegliere **Radice console** dal menu **Finestra** per tornare alla prima finestra ed eliminare la finestra aperta.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-126">On the **Window** menu, click **Console Root**, to switch back to the first window, and delete the window.</span></span>  
  
12. <span data-ttu-id="b6b9b-127">Scegliere **Salva**con nome dal menu **file** e salvare il file nella cartella desiderata con un nome appropriato con l' `.msc` estensione del file.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-127">On the **File** menu, click **Save As**, and save the file in the desired folder, with an appropriate name with the `.msc` file extension.</span></span> <span data-ttu-id="b6b9b-128">Chiudere [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-128">Close the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span>  
  
13. <span data-ttu-id="b6b9b-129">Per aprire Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nel computer di destinazione, fare doppio clic sul file.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-129">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on the target computer, double-click the file.</span></span> <span data-ttu-id="b6b9b-130">È possibile salvare un collegamento al file sul desktop o nel menu **Start** .</span><span class="sxs-lookup"><span data-stu-id="b6b9b-130">If desired, save a link to the file on the desktop or in the **Start** menu.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="b6b9b-131">Quando si utilizza Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in un computer remoto, il nome del computer non è facilmente individuabile ed è possibile che venga arrestato o configurato il computer errato.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-131">When using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager on a remote computer, the computer name is not obvious and it is possible to mistakenly stop or configure the wrong computer.</span></span> <span data-ttu-id="b6b9b-132">Nella scheda **Servizio** selezionare la casella **Nome host** per verificare il nome del computer prima di modificare un servizio.</span><span class="sxs-lookup"><span data-stu-id="b6b9b-132">On the **Service** tab, check the **Host Name** box to confirm the computer name before modifying a service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b9b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6b9b-133">See Also</span></span>  
 [<span data-ttu-id="b6b9b-134">Configurazione di WMI per mostrare lo stato del server in Strumenti SQL Server</span><span class="sxs-lookup"><span data-stu-id="b6b9b-134">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
