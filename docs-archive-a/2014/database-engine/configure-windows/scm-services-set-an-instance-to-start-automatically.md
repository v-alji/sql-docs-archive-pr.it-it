---
title: Impostare un'istanza di SQL Server per l'avvio automatico (Gestione configurazione SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 01/07/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- automatic SQL Server startup
- SQL Server, automatic startup
- starting SQL Server, automatically
ms.assetid: aa2b6bde-e76d-4fea-a560-54a63745d9b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2fc21bd881c1588da47710c6d8437e31d3df2ab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723064"
---
# <a name="set-an-instance-of-sql-server-to-start-automatically-sql-server-configuration-manager"></a><span data-ttu-id="8bda3-102">Impostare un'istanza di SQL Server per l'avvio automatico (Gestione configurazione SQL Server)</span><span class="sxs-lookup"><span data-stu-id="8bda3-102">Set an Instance of SQL Server to Start Automatically (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="8bda3-103">In questo argomento viene illustrato come impostare un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per l'avvio automatico in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] utilizzando Gestione configurazione SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8bda3-103">This topic describes how to set an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to start automatically in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="8bda3-104">Durante l'installazione, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] viene normalmente configurato per l'avvio automatico.</span><span class="sxs-lookup"><span data-stu-id="8bda3-104">During setup, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is normally configured to start automatically.</span></span> <span data-ttu-id="8bda3-105">In caso contrario, è possibile modificare questa impostazione in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="8bda3-105">If this was not done, you can change that setting at any time.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="8bda3-106">Utilizzo di Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bda3-106">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-set-an-instance-of-sql-server-to-start-automatically"></a><span data-ttu-id="8bda3-107">Per impostare un'istanza di SQL Server per l'avvio automatico</span><span class="sxs-lookup"><span data-stu-id="8bda3-107">To set an instance of SQL Server to start automatically</span></span>  
  
1.  <span data-ttu-id="8bda3-108">Fare clic sul menu **Start** , scegliere **Tutti i programmi**, [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Strumenti di configurazione**e quindi **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8bda3-108">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8bda3-109">Poiché Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è uno snap-in per il programma [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console e non un programma autonomo, Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non viene visualizzato come applicazione nelle versioni più recenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="8bda3-109">Because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager is a snap-in for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console program and not a stand-alone program, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager does not appear as an application in newer versions of Windows.</span></span>  
    >   
    >  -   <span data-ttu-id="8bda3-110">**Windows 10**:</span><span class="sxs-lookup"><span data-stu-id="8bda3-110">**Windows 10**:</span></span>  
    >          <span data-ttu-id="8bda3-111">Per aprire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, nella **pagina iniziale**digitare SQLServerManager12. msc (per [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="8bda3-111">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, on the **Start Page**, type SQLServerManager12.msc (for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]).</span></span> <span data-ttu-id="8bda3-112">Per le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sostituire 12 con un numero inferiore.</span><span class="sxs-lookup"><span data-stu-id="8bda3-112">For previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replace 12 with a smaller number.</span></span> <span data-ttu-id="8bda3-113">Se si fa clic su SQLServerManager12.msc, viene aperto Gestione configurazione.</span><span class="sxs-lookup"><span data-stu-id="8bda3-113">Clicking SQLServerManager12.msc opens the Configuration Manager.</span></span> <span data-ttu-id="8bda3-114">Per aggiungere la Configuration Manager alla pagina iniziale o alla barra delle applicazioni, fare clic con il pulsante destro del mouse su SQLServerManager12. msc, quindi scegliere **Apri percorso file**.</span><span class="sxs-lookup"><span data-stu-id="8bda3-114">To pin the Configuration Manager to the Start Page or Task Bar, right-click SQLServerManager12.msc, and then click **Open file location**.</span></span> <span data-ttu-id="8bda3-115">In Esplora file di Windows fare clic con il pulsante destro del mouse su SQLServerManager12. msc, quindi scegliere **Aggiungi a Start** o **Aggiungi alla barra delle applicazioni**.</span><span class="sxs-lookup"><span data-stu-id="8bda3-115">In the Windows File Explorer, right-click SQLServerManager12.msc, and then click **Pin to Start** or **Pin to taskbar**.</span></span>  
    > -   <span data-ttu-id="8bda3-116">**Windows 8**:</span><span class="sxs-lookup"><span data-stu-id="8bda3-116">**Windows 8**:</span></span>  
    >          <span data-ttu-id="8bda3-117">Per aprire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, nell'accesso alla **ricerca** , in **app**digitare **SQLServerManager \<version> . msc** , ad esempio `SQLServerManager12.msc` , quindi premere **invio**.</span><span class="sxs-lookup"><span data-stu-id="8bda3-117">To open [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, in the **Search** charm, under **Apps**, type **SQLServerManager\<version>.msc** such as `SQLServerManager12.msc`, and then press **Enter**.</span></span>  
  
2.  <span data-ttu-id="8bda3-118">In **Gestione configurazione SQL Server**espandere **Servizi**e quindi fare clic su **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="8bda3-118">In **SQL Server Configuration Manager**, expand **Services**, and then click **SQL Server**.</span></span>  
  
3.  <span data-ttu-id="8bda3-119">Nel riquadro dei dettagli fare clic con il pulsante destro del mouse sul nome dell'istanza per la quale impostare l'avvio automatico, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="8bda3-119">In the details pane, right-click the name of the instance you want to start automatically, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="8bda3-120">Nella finestra di dialogo **Proprietà - SQL Server \<***instancename***>** impostare **Modalità di avvio** su **Automatica**.</span><span class="sxs-lookup"><span data-stu-id="8bda3-120">In the **SQL Server \<***instancename***> Properties** dialog box, set **Start Mode** to **Automatic**.</span></span>  
  
5.  <span data-ttu-id="8bda3-121">Fare clic su **OK**e chiudere Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bda3-121">Click **OK**, and then close [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bda3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bda3-122">See Also</span></span>  
 <span data-ttu-id="8bda3-123">[Impedire l'avvio automatico di un'istanza di SQL Server &#40;Gestione configurazione SQL Server&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span><span class="sxs-lookup"><span data-stu-id="8bda3-123">[Prevent Automatic Startup of an Instance of SQL Server &#40;SQL Server Configuration Manager&#41;](scm-services-prevent-automatic-startup-of-an-instance.md) </span></span>  
 <span data-ttu-id="8bda3-124">[Connettersi a un altro computer &#40;Gestione configurazione SQL Server&#41;](scm-services-connect-to-another-computer.md) </span><span class="sxs-lookup"><span data-stu-id="8bda3-124">[Connect to Another Computer &#40;SQL Server Configuration Manager&#41;](scm-services-connect-to-another-computer.md) </span></span>  
 [<span data-ttu-id="8bda3-125">Configurazione di WMI per mostrare lo stato del server in Strumenti SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bda3-125">Configure WMI to Show Server Status in SQL Server Tools</span></span>](../../ssms/configure-wmi-to-show-server-status-in-sql-server-tools.md)  
  
  
