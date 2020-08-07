---
title: Proprietà SQL Server (scheda disponibilità elevata AlwaysOn) | Microsoft Docs
description: Informazioni su come attivare o disattivare la funzionalità Gruppi di disponibilità AlwaysOn in SQL Server 2014. Visualizzare i prerequisiti che l'istanza del server deve soddisfare per questa funzionalità.
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: d8630923-a600-4f1c-aca1-027453a3ec82
author: mikeraymsft
ms.author: mikeray
ms.openlocfilehash: 3939b40a334746e9ee96441338e2e50791987103
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719277"
---
# <a name="sql-server-properties-alwayson-high-availability-tab"></a><span data-ttu-id="19e90-104">Proprietà SQL Server (scheda Disponibilità elevata AlwaysOn)</span><span class="sxs-lookup"><span data-stu-id="19e90-104">SQL Server Properties (AlwaysOn High Availability Tab)</span></span>
  <span data-ttu-id="19e90-105">Utilizzare la scheda **Disponibilità elevata AlwaysOn** della finestra di dialogo **Proprietà SQL Server** in Gestione configurazione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per abilitare o disabilitare la caratteristica dei gruppi di disponibilità AlwaysOn in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19e90-105">Use the **AlwaysOn High Availability** tab of the **SQL Server Properties** dialog box in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to enable or disable the AlwaysOn Availability Groups feature in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="19e90-106">L'abilitazione dei gruppi di disponibilità AlwaysOn rappresenta un prerequisito per consentire a un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] di utilizzare i gruppi di disponibilità come soluzione a disponibilità elevata e di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="19e90-106">Enabling AlwaysOn Availability Groups is a prerequisite for an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to use availability groups as a high availability and disaster recovery solution.</span></span>  
  
##  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="19e90-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="19e90-107">Prerequisites</span></span>  
 <span data-ttu-id="19e90-108">Per poter essere abilitato per i gruppi di disponibilità AlwaysOn, un'istanza di server deve soddisfare i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="19e90-108">To be enabled for AlwaysOn Availability Groups, a server instance must meet the following prerequisites:</span></span>  
  
-   <span data-ttu-id="19e90-109">L'istanza del server deve trovarsi in un nodo WSFC (Windows Server Failover Clustering).</span><span class="sxs-lookup"><span data-stu-id="19e90-109">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="19e90-110">Per trovarsi nello stesso gruppo di disponibilità, tutte le istanze del server devono trovarsi nello stesso cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="19e90-110">To be in the same availability group, instances must be in the same WSFC cluster.</span></span> <span data-ttu-id="19e90-111">Un gruppo di disponibilità non può essere esteso ai cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="19e90-111">An availability group cannot span WSFC clusters.</span></span>  
  
-   <span data-ttu-id="19e90-112">L'istanza del server deve eseguire un'edizione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui è supportato [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19e90-112">The server instance must be running an edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that supports [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span></span>  
  
-   <span data-ttu-id="19e90-113">Abilitare i gruppi di disponibilità AlwaysOn per una sola istanza di server per volta.</span><span class="sxs-lookup"><span data-stu-id="19e90-113">Enable AlwaysOn Availability Groups for only one server instance at a time.</span></span> <span data-ttu-id="19e90-114">Dopo aver abilitato i gruppi di disponibilità AlwaysOn, attendere il riavvio del servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prima di abilitare la successiva istanza di server.</span><span class="sxs-lookup"><span data-stu-id="19e90-114">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service has restarted before you enable the next server instance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19e90-115">Per informazioni sul supporto delle caratteristiche e su altri prerequisiti, restrizioni e consigli per [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], vedere la documentazione online di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19e90-115">For information about feature support and for information about additional prerequisites, restrictions, and recommendations for [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
## <a name="dialog-options"></a><span data-ttu-id="19e90-116">Opzioni della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="19e90-116">Dialog Options</span></span>  
 <span data-ttu-id="19e90-117">**Nome cluster di failover Windows**</span><span class="sxs-lookup"><span data-stu-id="19e90-117">**Windows failover cluster name**</span></span>  
 <span data-ttu-id="19e90-118">Consente di visualizzare il nome del cluster WSFC in cui il computer locale è un nodo.</span><span class="sxs-lookup"><span data-stu-id="19e90-118">Displays the name of the WSFC cluster in which the local computer is a node.</span></span>  
  
 <span data-ttu-id="19e90-119">**Abilita Gruppi di disponibilità AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="19e90-119">**Enable AlwaysOn Availability Groups**</span></span>  
 <span data-ttu-id="19e90-120">Utilizzare questa casella di controllo per abilitare o disabilitare i gruppi di disponibilità AlwaysOn in questa istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="19e90-120">Use this check box to enable or disable AlwaysOn Availability Groups on this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], as follows:</span></span>  
  
-   <span data-ttu-id="19e90-121">Se la casella è deselezionata, i gruppi di disponibilità AlwaysOn sono attualmente disabilitati.</span><span class="sxs-lookup"><span data-stu-id="19e90-121">If this check box is empty, AlwaysOn Availability Groups is currently disabled.</span></span> <span data-ttu-id="19e90-122">Per abilitarli, selezionare la casella di controllo, fare clic su **OK**e riavviare manualmente il servizio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="19e90-122">To enable AlwaysOn Availability Groups, select this check box, click **OK**, and manually restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
-   <span data-ttu-id="19e90-123">Se la casella è già selezionata, i gruppi di disponibilità AlwaysOn sono attualmente abilitati.</span><span class="sxs-lookup"><span data-stu-id="19e90-123">If this check box is already selected, AlwaysOn Availability Groups is currently enabled.</span></span> <span data-ttu-id="19e90-124">Per disabilitarli, deselezionare la casella di controllo e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="19e90-124">To disable AlwaysOn Availability Groups, uncheck the check box and click **OK**.</span></span> <span data-ttu-id="19e90-125">L'istanza del server verrà riavviata.</span><span class="sxs-lookup"><span data-stu-id="19e90-125">This causes the server instance to restart.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="19e90-126">Dopo aver disabilitato i gruppi di disponibilità AlwaysOn, è opportuno rimuovere eventuali repliche di disponibilità dall'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="19e90-126">After disabling AlwaysOn Availability Groups, you should remove any local availability replicas from the server instance.</span></span> <span data-ttu-id="19e90-127">Se si rimuove l'ultima replica di un determinato gruppo di disponibilità, è opportuno rimuovere anche il gruppo.</span><span class="sxs-lookup"><span data-stu-id="19e90-127">If you remove the last replica of a given availability group, you should also remove the group.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="19e90-128">Elenco di elementi dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="19e90-128">UI element list</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="19e90-129">Per ulteriori informazioni su come procedere dopo aver disabilitato i gruppi di disponibilità AlwaysOn e su come creare e configurare gruppi di disponibilità, vedere la documentazione online di [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19e90-129">For more information about follow up after you disable AlwaysOn Availability Groups and for information about how to create and configure availability groups, see [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Books Online.</span></span>  
  
  
