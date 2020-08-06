---
title: Failover manuale di una sessione di mirroring del database (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- failover [SQL Server], database mirroring
- manual failover [SQL Server]
- database mirroring [SQL Server], failover
ms.assetid: 4ecf9c63-b3a4-4c54-b553-5bc37973232b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7f7f4547058b2dfd4229142dca73a7d9b4bdb239
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726236"
---
# <a name="manually-fail-over-a-database-mirroring-session-sql-server-management-studio"></a><span data-ttu-id="7f55e-102">Failover manuale di una sessione di mirroring del database (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7f55e-102">Manually Fail Over a Database Mirroring Session (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7f55e-103">Quando il database con mirroring è sincronizzato, ovvero è in stato SYNCHRONIZED, il proprietario del database può iniziare il failover manuale al server mirror.</span><span class="sxs-lookup"><span data-stu-id="7f55e-103">When the mirrored database is synchronized (that is, when the database is in the SYNCHRONIZED state), the database owner can initiate manual failover to the mirror server.</span></span>  
  
 <span data-ttu-id="7f55e-104">Durante un failover manuale, il ruolo del server principale e quello del server mirror vengono scambiati per il database in cui si verifica il failover.</span><span class="sxs-lookup"><span data-stu-id="7f55e-104">During a manual failover, the principal and mirror server roles are swapped for the database on which the failover occurs.</span></span> <span data-ttu-id="7f55e-105">Il database mirror diventa il database principale e viceversa.</span><span class="sxs-lookup"><span data-stu-id="7f55e-105">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span> <span data-ttu-id="7f55e-106">Ad esempio, nella tabella seguente viene illustrato lo scambio dei ruoli di due partner di mirroring tramite un failover manuale: `SQLDBENGINE0_1` e `SQLDBENGINE0_2`.</span><span class="sxs-lookup"><span data-stu-id="7f55e-106">For example, the following table shows the how a manual failover swaps the roles of two mirroring partners: `SQLDBENGINE0_1` and `SQLDBENGINE0_2`.</span></span>  
  
|<span data-ttu-id="7f55e-107">Server</span><span class="sxs-lookup"><span data-stu-id="7f55e-107">Server</span></span>|<span data-ttu-id="7f55e-108">Prima del failover</span><span class="sxs-lookup"><span data-stu-id="7f55e-108">Before failover</span></span>|<span data-ttu-id="7f55e-109">Dopo il failover</span><span class="sxs-lookup"><span data-stu-id="7f55e-109">After failover</span></span>|  
|------------|---------------------|--------------------|  
|`SQLDBENGINE0_1`|<span data-ttu-id="7f55e-110">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="7f55e-110">PRINCIPAL</span></span>|<span data-ttu-id="7f55e-111">MIRROR</span><span class="sxs-lookup"><span data-stu-id="7f55e-111">MIRROR</span></span>|  
|`SQLDBENGINE0_2`|<span data-ttu-id="7f55e-112">MIRROR</span><span class="sxs-lookup"><span data-stu-id="7f55e-112">MIRROR</span></span>|<span data-ttu-id="7f55e-113">PRINCIPAL</span><span class="sxs-lookup"><span data-stu-id="7f55e-113">PRINCIPAL</span></span>|  
  
 <span data-ttu-id="7f55e-114">Si noti che questa operazione non influisce sui ruoli del server per le altre sessioni di mirroring del database.</span><span class="sxs-lookup"><span data-stu-id="7f55e-114">Note that the server roles for other database mirroring sessions are not affected.</span></span> <span data-ttu-id="7f55e-115">Per altre informazioni, vedere [Cambio di ruolo durante una sessione di mirroring del database &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md)(Mirroring del database e log shipping).</span><span class="sxs-lookup"><span data-stu-id="7f55e-115">For more information, see [Role Switching During a Database Mirroring Session &#40;SQL Server&#41;](role-switching-during-a-database-mirroring-session-sql-server.md).</span></span>  
  
### <a name="to-manually-fail-over-database-mirroring"></a><span data-ttu-id="7f55e-116">Per eseguire il failover manuale del mirroring del database</span><span class="sxs-lookup"><span data-stu-id="7f55e-116">To manually fail over database mirroring</span></span>  
  
1.  <span data-ttu-id="7f55e-117">Connettersi all'istanza del server principale e fare clic sul nome del server per espandere l'albero di server nel riquadro **Esplora oggetti** .</span><span class="sxs-lookup"><span data-stu-id="7f55e-117">Connect to the principal server instance and, in the **Object Explorer** pane, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="7f55e-118">Espandere **Database**e selezionare il database di cui eseguire il failover.</span><span class="sxs-lookup"><span data-stu-id="7f55e-118">Expand **Databases**, and select the database to be failed over.</span></span>  
  
3.  <span data-ttu-id="7f55e-119">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="7f55e-119">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="7f55e-120">Viene visualizzata la pagina **Mirroring** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="7f55e-120">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="7f55e-121">Fare clic su **Failover**.</span><span class="sxs-lookup"><span data-stu-id="7f55e-121">Click **Failover**.</span></span>  
  
     <span data-ttu-id="7f55e-122">Verrà visualizzata una finestra contenente una richiesta di conferma.</span><span class="sxs-lookup"><span data-stu-id="7f55e-122">A confirmation box appears.</span></span>  <span data-ttu-id="7f55e-123">Il server principale prova a connettersi al server mirror utilizzando l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="7f55e-123">The principal server begins by trying to connect to the mirror server by using Windows Authentication.</span></span> <span data-ttu-id="7f55e-124">Se l'autenticazione di Windows non funziona, sul server principale viene visualizzata la finestra di dialogo **Connetti al server** .</span><span class="sxs-lookup"><span data-stu-id="7f55e-124">If Windows Authentication does not work, the principal server displays the **Connect to Server** dialog box.</span></span> <span data-ttu-id="7f55e-125">Se il server mirror usa l'autenticazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , selezionare **Autenticazione di SQL Server** nella casella **Autenticazione** .</span><span class="sxs-lookup"><span data-stu-id="7f55e-125">If the mirror server uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, select **SQL Server Authentication** in the **Authentication** box.</span></span> <span data-ttu-id="7f55e-126">Nella casella di testo **Account di accesso** specificare l'account di accesso con cui connettersi al server mirror e nella casella di testo **Password** specificare la password per tale account.</span><span class="sxs-lookup"><span data-stu-id="7f55e-126">In the **Login** text box, specify the login account to connect with on the mirror server, and in the **Password** text box, specify the password for that account.</span></span>  
  
     <span data-ttu-id="7f55e-127">Se il failover ha esito positivo, la finestra di dialogo **Proprietà database** viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="7f55e-127">If failover succeeds, the **Database Properties** dialog box closes.</span></span> <span data-ttu-id="7f55e-128">Il database mirror diventa il database principale e viceversa.</span><span class="sxs-lookup"><span data-stu-id="7f55e-128">The mirror database becomes the principal database and the principal database becomes the mirror.</span></span>  
  
     <span data-ttu-id="7f55e-129">Se il failover non riesce, viene visualizzato un messaggio di errore e la finestra di dialogo rimane aperta.</span><span class="sxs-lookup"><span data-stu-id="7f55e-129">If failover fails, an error message is displayed and the dialog box remains open.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7f55e-130">Se una o più proprietà sono state modificate dopo l'apertura della pagina **Mirroring** , tali modifiche non verranno salvate.</span><span class="sxs-lookup"><span data-stu-id="7f55e-130">If you have modified any properties since opening the **Mirroring** page, those changes will not be saved.</span></span>  
  
     <span data-ttu-id="7f55e-131">La finestra di dialogo verrà chiusa automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f55e-131">The dialog box closes automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f55e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f55e-132">See Also</span></span>  
 <span data-ttu-id="7f55e-133">[Proprietà del database &#40;Pagina Mirroring&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="7f55e-133">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="7f55e-134">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7f55e-134">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="7f55e-135">[Eseguire il failover manuale di una sessione di mirroring del database &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="7f55e-135">[Manually Fail Over a Database Mirroring Session &#40;Transact-SQL&#41;](manually-fail-over-a-database-mirroring-session-transact-sql.md) </span></span>  
 <span data-ttu-id="7f55e-136">[Sospendere o riprendere una sessione di mirroring del database &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7f55e-136">[Pause or Resume a Database Mirroring Session &#40;SQL Server&#41;](pause-or-resume-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="7f55e-137">Rimuovere il mirroring del database &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f55e-137">Remove Database Mirroring &#40;SQL Server&#41;</span></span>](remove-database-mirroring-sql-server.md)  
  
  
