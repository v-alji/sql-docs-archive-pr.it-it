---
title: Aggiungere o sostituire un server di controllo del mirroring del database (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- database mirroring [SQL Server], witness
ms.assetid: 4b5ecffd-f025-4ab7-b69d-8958c6477127
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dd14ace23956ceef114f1f032b5d4db5febcec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626292"
---
# <a name="add-or-replace-a-database-mirroring-witness-sql-server-management-studio"></a><span data-ttu-id="89400-102">Aggiunta o sostituzione di un server di controllo del mirroring del database (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="89400-102">Add or Replace a Database Mirroring Witness (SQL Server Management Studio)</span></span>
  <span data-ttu-id="89400-103">Se gli endpoint del mirroring del database utilizzano l'autenticazione di Windows, è possibile utilizzare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] per aggiungere o sostituire un server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="89400-103">If the database mirroring endpoints use Windows Authentication,, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add or replace a witness.</span></span> <span data-ttu-id="89400-104">L'aggiunta di un server di controllo del mirroring in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] comporta l'attivazione della modalità a sicurezza elevata con failover automatico.</span><span class="sxs-lookup"><span data-stu-id="89400-104">Adding a witness in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] also changes the operating mode to high-safety mode with automatic failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="89400-105">È consigliabile che il server di controllo del mirroring si trovi in un computer separato dagli altri due partner.</span><span class="sxs-lookup"><span data-stu-id="89400-105">We strongly recommend that the witness reside on a separate computer from either of the partners.</span></span> <span data-ttu-id="89400-106">L'account di servizio utilizzato dal server di controllo del mirroring deve trovarsi nello stesso dominio degli account di servizio utilizzati dalle istanze del server principale e del server mirror oppure in un dominio trusted.</span><span class="sxs-lookup"><span data-stu-id="89400-106">The service account used by the witness must be in the same domain as the service accounts used by the principal and mirror server instances, or it must be in a trusted domain.</span></span>  
  
### <a name="to-add-or-replace-a-witness"></a><span data-ttu-id="89400-107">Per aggiungere o sostituire un server di controllo del mirroring</span><span class="sxs-lookup"><span data-stu-id="89400-107">To Add or Replace a Witness</span></span>  
  
1.  <span data-ttu-id="89400-108">Dopo aver attivato la connessione all'istanza del server principale, in Esplora oggetti fare clic sul nome del server per espandere l'albero.</span><span class="sxs-lookup"><span data-stu-id="89400-108">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="89400-109">Espandere **Database**e selezionare il database principale della sessione in cui si intende aggiungere o sostituire un server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="89400-109">Expand **Databases**, and select the principal database of the session to which you are adding or replacing a witness.</span></span>  
  
3.  <span data-ttu-id="89400-110">Fare clic con il pulsante destro del mouse sul database, scegliere **Attività**e quindi fare clic su **Server mirror**.</span><span class="sxs-lookup"><span data-stu-id="89400-110">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="89400-111">Viene visualizzata la pagina **Mirroring** della finestra di dialogo **Proprietà database** .</span><span class="sxs-lookup"><span data-stu-id="89400-111">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="89400-112">Fare clic su **Configura sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="89400-112">Click **Configure Security**.</span></span>  
  
5.  <span data-ttu-id="89400-113">Se viene visualizzata la schermata iniziale di **Configurazione guidata sicurezza mirroring del database** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="89400-113">If the **Configure Database Mirroring Security Wizard** welcome screen appears, click **Next**.</span></span>  
  
6.  <span data-ttu-id="89400-114">Nella finestra di dialogo **Aggiunta server di controllo del mirroring** fare clic su **Sì**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="89400-114">In the **Include Witness Server** dialog box, click **Yes**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="89400-115">Nella finestra di dialogo **Selezione dei server da configurare** viene automaticamente selezionata la casella di controllo **Istanza server di controllo del mirroring** .</span><span class="sxs-lookup"><span data-stu-id="89400-115">In the **Choose Servers to Configure** dialog box, the **Witness server instance** check box is automatically checked.</span></span> <span data-ttu-id="89400-116">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="89400-116">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="89400-117">Nella finestra di dialogo **Istanza server principale** mantenere la porta e l'endpoint esistenti.</span><span class="sxs-lookup"><span data-stu-id="89400-117">On the **Principal Server Instance** dialog box, keep the existing port and endpoint.</span></span> <span data-ttu-id="89400-118">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="89400-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="89400-119">Nella finestra di dialogo **Istanza server di controllo del mirroring** fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="89400-119">On the **Witness Server Instance** dialog box, click **Connect**.</span></span>  
  
10. <span data-ttu-id="89400-120">Nella finestra di dialogo **Connetti al server** specificare l'istanza del server di controllo del mirroring nel campo **Nome server** e usare l'autenticazione di Windows (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="89400-120">In the **Connect to Server** dialog box, specify the witness server instance in the **Server name** field, and use Windows Authentication (the default).</span></span> <span data-ttu-id="89400-121">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="89400-121">Click **Connect**.</span></span>  
  
11. <span data-ttu-id="89400-122">Dopo avere stabilito la connessione, nella finestra di dialogo **Istanza server di controllo del mirroring** vengono visualizzati la porta di attesa e l'endpoint del mirroring del database dell'istanza del server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="89400-122">Once a connection is established, the listener port and database mirroring endpoint of the witness server instance are displayed on the **Witness Server Instance** dialog box.</span></span> <span data-ttu-id="89400-123">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="89400-123">Click **Next**.</span></span>  
  
12. <span data-ttu-id="89400-124">Nella finestra di dialogo **Account di servizio** sono contenuti i campi per gli account di servizio del dominio delle istanze dei server principale, mirror e di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="89400-124">The **Service Accounts** dialog box contains fields for the domain service accounts of the principal, mirror, and witness server instances.</span></span>  
  
    -   <span data-ttu-id="89400-125">Se le istanze del server utilizzano tutte lo stesso account di servizio, lasciare i campi vuoti.</span><span class="sxs-lookup"><span data-stu-id="89400-125">If the server instances all use the same service account, leave the fields blank.</span></span>  
  
    -   <span data-ttu-id="89400-126">Se l'istanza del server di controllo del mirroring usa un account di servizio diverso da uno degli altri partner, immettere il nome dell'account nei campi **Server principale**, **Server mirror**e **Server di controllo del mirroring** :</span><span class="sxs-lookup"><span data-stu-id="89400-126">If the witness server instance uses a different service account from either of the partners, fill in the **Principal**, **Mirror**, and **Witness** fields with the account name:</span></span>  
  
         <span data-ttu-id="89400-127">*NOMEDOMINIO* **\\** *nomeutente*</span><span class="sxs-lookup"><span data-stu-id="89400-127">*DOMAINNAME* **\\** *username*</span></span>  
  
         <span data-ttu-id="89400-128">Il nome del dominio deve essere scritto in lettere maiuscole.</span><span class="sxs-lookup"><span data-stu-id="89400-128">The domain name must be in upper case.</span></span>  
  
     <span data-ttu-id="89400-129">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="89400-129">Click **Next**.</span></span>  
  
13. <span data-ttu-id="89400-130">Nella schermata di riepilogo **Completare la procedura guidata** verificare, facoltativamente, la configurazione del server di controllo del mirroring e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="89400-130">On the **Complete the Wizard** summary screen, optionally, verify the witness configuration, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="89400-131">Al termine, verrà nuovamente visualizzata la finestra di dialogo **Proprietà database** nel cui campo **Server di controllo del mirroring** verrà visualizzato l'indirizzo di rete del server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="89400-131">On finishing, the wizard returns you to the **Database Properties** dialog box where the server network address of the witness now appears in **Witness** field.</span></span> <span data-ttu-id="89400-132">Viene inoltre selezionata automaticamente l'opzione **Protezione elevata con failover automatico (sincrona)** necessaria con un server di controllo del mirroring.</span><span class="sxs-lookup"><span data-stu-id="89400-132">Also, **High-safety mode with automatic failover (synchronous)**, which is required with a witness, is automatically selected.</span></span>  
  
     <span data-ttu-id="89400-133">Per abilitare il server di controllo del mirroring e impostare la sessione sulla modalità di protezione elevata con failover automatico, fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="89400-133">To enable the witness and change the session to high-safety mode with automatic failover, Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89400-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89400-134">See Also</span></span>  
 <span data-ttu-id="89400-135">[Server di controllo del mirroring del database](database-mirroring-witness.md) </span><span class="sxs-lookup"><span data-stu-id="89400-135">[Database Mirroring Witness](database-mirroring-witness.md) </span></span>  
 <span data-ttu-id="89400-136">[Mirroring del database &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="89400-136">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="89400-137">[Proprietà del database &#40;Pagina Mirroring&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="89400-137">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="89400-138">[Stabilire una sessione di mirroring del database tramite autenticazione di Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="89400-138">[Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span></span>  
 [<span data-ttu-id="89400-139">Server di controllo del mirroring del database</span><span class="sxs-lookup"><span data-stu-id="89400-139">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
