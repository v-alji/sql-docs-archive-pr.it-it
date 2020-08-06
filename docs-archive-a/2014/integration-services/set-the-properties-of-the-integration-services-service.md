---
title: Impostare le proprietà del servizio Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- Integration Services service, properties
ms.assetid: 3a8ad546-0f58-4b31-ab56-58d6313b1098
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 055eadd9a1d59c59dd40675b142eae480763f6f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726044"
---
# <a name="set-the-properties-of-the-integration-services-service"></a><span data-ttu-id="0cb2e-102">Impostare le proprietà del servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="0cb2e-102">Set the Properties of the Integration Services Service</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="0cb2e-103">In questo argomento viene illustrato il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un servizio Windows per la gestione dei pacchetti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cb2e-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="0cb2e-104">supporta il servizio per la compatibilità con le versioni precedenti di [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cb2e-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="0cb2e-105">A partire da [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], è possibile gestire oggetti come i pacchetti del server Integration Services.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="0cb2e-106">Il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] consente di gestire e monitorare i pacchetti in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cb2e-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages and monitors packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0cb2e-107">Quando si installa per la prima volta [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , il [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] servizio viene avviato e il tipo di avvio del servizio è impostato su automatico.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-107">When you first install [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span>  
  
 <span data-ttu-id="0cb2e-108">Dopo l'installazione del servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , è possibile impostare le proprietà del servizio usando Gestione configurazione SQL Server o lo snap-in MMC Servizi.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-108">After the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has been installed, you can set the properties of the service by using either SQL Server Configuration Manager or the Services MMC snap-in.</span></span>  
  
 <span data-ttu-id="0cb2e-109">Per configurare le altre importanti funzionalità del servizio, inclusi i percorsi in cui vengono memorizzati e gestiti i pacchetti, è necessario modificare il file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-109">To configure other important features of the service, including the locations where it stores and manages packages, you must modify the configuration file of the service.</span></span> <span data-ttu-id="0cb2e-110">Per altre informazioni, vedere [Configurazione del servizio Integration Services &#40;servizio SSIS&#41;](service/integration-services-service-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="0cb2e-110">For more information, see [Configuring the Integration Services Service &#40;SSIS Service&#41;](service/integration-services-service-ssis-service.md).</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-sql-server-configuration-manager"></a><span data-ttu-id="0cb2e-111">Per impostare le proprietà del servizio Integration Services tramite Gestione configurazione SQL Server</span><span class="sxs-lookup"><span data-stu-id="0cb2e-111">To set properties of the Integration Services service by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="0cb2e-112">Fare clic sul menu **Start** , scegliere **Tutti i programmi**, **Microsoft SQL Server**, **Strumenti di configurazione**e quindi fare clic su **Gestione configurazione SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-112">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="0cb2e-113">Nello snap-in **Gestione configurazione SQL Server** individuare **SQL Server Integration Services** nell'elenco dei servizi, fare clic con il pulsante destro del mouse su **SQL Server Integration Services**e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-113">In the **SQL Server Configuration Manager** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0cb2e-114">Nella finestra di dialogo **proprietà SQL Server Integration Services** è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cb2e-114">In the **SQL Server Integration Services Properties** dialog box you can do the following:</span></span>  
  
    -   <span data-ttu-id="0cb2e-115">Fare clic sulla scheda **Connessione** per visualizzare le informazioni di accesso, come il nome dell'account.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-115">Click the **Log On** tab to view the logon information such as the account name.</span></span>  
  
    -   <span data-ttu-id="0cb2e-116">Fare clic sulla scheda **Servizio** per visualizzare le informazioni relative al servizio, ad esempio il nome del computer host e per specificare la modalità di avvio del servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cb2e-116">Click the **Service** tab to view information about the service such as the name of the host computer and to specify the start mode of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0cb2e-117">Nella scheda **Avanzate** non sono disponibili informazioni relative al servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0cb2e-117">The **Advanced** tab contains no information for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
4.  <span data-ttu-id="0cb2e-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="0cb2e-119">Scegliere **Esci** dal menu **File** per chiudere lo snap-in **Gestione configurazione SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="0cb2e-119">On the **File** menu, click **Exit** to close the **SQL Server Configuration Manager** snap-in.</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-services"></a><span data-ttu-id="0cb2e-120">Per impostare le proprietà del servizio Integration Services tramite i Servizi</span><span class="sxs-lookup"><span data-stu-id="0cb2e-120">To set properties of the Integration Services service by using Services</span></span>  
  
1.  <span data-ttu-id="0cb2e-121">Nel **Pannello di controllo**fare clic su **Strumenti di amministrazione**nella visualizzazione classica oppure su **Prestazioni e manutenzione** e quindi su **Strumenti di amministrazione**nella visualizzazione per categorie.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-121">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="0cb2e-122">Fare clic su **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-122">Click **Services**.</span></span>  
  
3.  <span data-ttu-id="0cb2e-123">Nello snap-in **Servizi** individuare **SQL Server Integration Services** nell'elenco dei servizi, fare clic con il pulsante destro del mouse su **SQL Server Integration Services**e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-123">In the **Services** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="0cb2e-124">Nella finestra di dialogo **Proprietà di SQL Server Integration Services** è possibile eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0cb2e-124">In the **SQL Server Integration Services Properties** dialog box, you can do the following:</span></span>  
  
    -   <span data-ttu-id="0cb2e-125">Fare clic sulla scheda **generale** . Per abilitare il servizio, selezionare il tipo di avvio manuale o automatico.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-125">Click the **General** tab. To enable the service, select either the manual or automatic startup type.</span></span> <span data-ttu-id="0cb2e-126">Per disabilitarlo, nella casella **Tipo di avvio** selezionare Disabilita.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-126">To disable the service, select Disable in the **Startup type** box.</span></span> <span data-ttu-id="0cb2e-127">Quando si seleziona Disabilita, il servizio non viene arrestato se è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-127">Selecting Disable does not stop the service if it is currently running.</span></span>  
  
         <span data-ttu-id="0cb2e-128">Se il servizio è già abilitato, è possibile fare clic su **Arresta** per arrestarlo oppure su **Avvia** per avviarlo.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-128">If the service is already enabled, you can click **Stop** to stop the service, or click **Start** to start the service.</span></span>  
  
    -   <span data-ttu-id="0cb2e-129">Fare clic sulla scheda **Accedi** per visualizzare o modificare le informazioni relative all'accesso.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-129">Click the **Log On** tab to view or edit the logon information.</span></span>  
  
    -   <span data-ttu-id="0cb2e-130">Fare clic sulla scheda **Recupero** per visualizzare le risposte predefinite del computer agli errori del servizio.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-130">Click the **Recovery** tab to view the default computer responses to service failure.</span></span> <span data-ttu-id="0cb2e-131">È possibile modificare queste opzioni in base all'ambiente specifico.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-131">You can modify these options to suit your environment.</span></span>  
  
    -   <span data-ttu-id="0cb2e-132">Fare clic sulla scheda **Dipendenze** per visualizzare un elenco dei servizi dipendenti.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-132">Click the **Dependencies** tab to view a list of dependent services.</span></span> <span data-ttu-id="0cb2e-133">Il servizio [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] non ha alcuna dipendenza.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-133">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has no dependencies.</span></span>  
  
5.  <span data-ttu-id="0cb2e-134">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-134">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="0cb2e-135">Facoltativamente, se è stato impostato il tipo di avvio manuale o automatico, è possibile fare clic con il pulsante destro del mouse su **SQL Server Integration Services** e quindi scegliere **Avvia, Arresta o Riavvia**.</span><span class="sxs-lookup"><span data-stu-id="0cb2e-135">Optionally, if the startup type is Manual or Automatic, you can right-click **SQL Server Integration Services** and click **Start, Stop, or Restart**.</span></span>  
  
7.  <span data-ttu-id="0cb2e-136">Scegliere **Esci** dal menu **File** per chiudere lo snap-in **Servizi** .</span><span class="sxs-lookup"><span data-stu-id="0cb2e-136">On the **File** menu, click **Exit** to close the **Services** snap-in.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cb2e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cb2e-137">See Also</span></span>  
 [<span data-ttu-id="0cb2e-138">Gestione del servizio Integration Services</span><span class="sxs-lookup"><span data-stu-id="0cb2e-138">Manage the Integration Services Service</span></span>](../../2014/integration-services/manage-the-integration-services-service.md)  
  
  
