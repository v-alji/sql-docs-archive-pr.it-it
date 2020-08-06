---
title: Finestra di dialogo Aggiungi indirizzo IP (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.availabilitygrouplistener.addipaddress.f1
ms.assetid: 98c9ad3b-ff3c-4c1d-b344-59a72fca137c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5192e6414b34bee6de09d45a7284f25404235dc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624964"
---
# <a name="add-ip-address-dialog-box-sql-server-management-studio"></a><span data-ttu-id="130fb-102">Finestra di dialogo Aggiungi indirizzo IP (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="130fb-102">Add IP Address Dialog Box (SQL Server Management Studio)</span></span>
  <span data-ttu-id="130fb-103"> Questo argomento della Guida sensibile al contesto descrive le opzioni della finestra di dialogo **Aggiungi indirizzo IP**.</span><span class="sxs-lookup"><span data-stu-id="130fb-103">This F1 help topic describes the options of the **Add IP Address** dialog box.</span></span> <span data-ttu-id="130fb-104">Questa finestra di dialogo a cui si accede dalla finestra di dialogo **Nuovo listener gruppo di disponibilità** e dalla scheda **Listener** della pagina **Specifica repliche** della [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] o della [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] di [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="130fb-104">This dialog box accessed from the **New Availability Group Listener** dialog box and the **Listener** tab of the **Specify Replicas** page of the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] or the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="130fb-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="130fb-105">Prerequisites</span></span>  
 <span data-ttu-id="130fb-106">Prima di iniziare ad aggiungere subnet a un listener del gruppo di disponibilità, assicurarsi di conoscere l'indirizzo IP per ogni subnet e, per un indirizzo IPv4, la subnet mask.</span><span class="sxs-lookup"><span data-stu-id="130fb-106">Before you begin to add subnets to an availability group listener, ensure that know the IP address for each subnet and, for an IPv4 address, the subnet mask.</span></span>  
  
##  <a name="add-ip-address-options"></a><a name="PageOptions"></a> <span data-ttu-id="130fb-107">Opzioni di aggiunta dell'indirizzo IP</span><span class="sxs-lookup"><span data-stu-id="130fb-107">Add IP Address Options</span></span>  
 <span data-ttu-id="130fb-108">**Subnet**</span><span class="sxs-lookup"><span data-stu-id="130fb-108">**Subnet**</span></span>  
 <span data-ttu-id="130fb-109">Utilizzare l'elenco a discesa per selezionare un indirizzo per la subnet da aggiungere al listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="130fb-109">Use the drop list to select an address for the subnet that you are adding to the availability group listener.</span></span> <span data-ttu-id="130fb-110">Per impostazione predefinita, una subnet ha sia un indirizzo IPv4 sia un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="130fb-110">By default a subnet possesses both an IPv4 address and an IPv6 address.</span></span> <span data-ttu-id="130fb-111">Al primo utilizzo della finestra di dialogo **Aggiungi indirizzo IP** , nell'elenco a discesa **Subnet** sono visualizzati entrambi gli indirizzi per ogni subnet che ospita una replica per il gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="130fb-111">The first time you use the **Add IP Address** dialog,  the **Subnet** drop list displays both subnet addresses for each subnet that hosts a replica for the availability group.</span></span> <span data-ttu-id="130fb-112">Per aggiungere una determinata subnet al listener, selezionare uno dei relativi indirizzi subnet.</span><span class="sxs-lookup"><span data-stu-id="130fb-112">To add a given subnet to the listener, select one of its subnet addresses.</span></span>  
  
 <span data-ttu-id="130fb-113">Dopo avere completato la finestra di dialogo **Aggiungi indirizzo IP** e scelto **OK** per aggiungere un indirizzo di subnet selezionato al listener, nell'elenco a discesa **Subnet** tale indirizzo di subnet sarà filtrato.</span><span class="sxs-lookup"><span data-stu-id="130fb-113">After you complete the **Add IP Address** dialog box and click **OK** to add a selected subnet address to the listener, the **Subnet** drop list filters out that subnet address.</span></span> <span data-ttu-id="130fb-114">Tutti gli indirizzi della subnet deselezionati rimangono nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="130fb-114">All unselected subnet addresses remain on the drop list.</span></span> <span data-ttu-id="130fb-115">Verificare di aggiungere un solo indirizzo per subnet al listener, in caso contrario la creazione del listener avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="130fb-115">Be sure that you add one and only one subnet address per subnet to the listener, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="130fb-116">**Indirizzi**</span><span class="sxs-lookup"><span data-stu-id="130fb-116">**Addresses**</span></span>  
 <span data-ttu-id="130fb-117">Utilizzare questo campo per immettere un indirizzo IP statico per l'indirizzo di subnet selezionato.</span><span class="sxs-lookup"><span data-stu-id="130fb-117">Use this field to enter a static IP address for the selected subnet address.</span></span> <span data-ttu-id="130fb-118">Contattare l'amministratore della rete per questo indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="130fb-118">Contact your network administrator for this IP address.</span></span> <span data-ttu-id="130fb-119">Assicurarsi di immettere un indirizzo valido per l'indirizzo di subnet selezionato, in caso contrario la creazione del listener avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="130fb-119">Ensure that you enter a valid address for the selected subnet address, or listener creation will fail.</span></span>  
  
 <span data-ttu-id="130fb-120">**Indirizzo IPv4**</span><span class="sxs-lookup"><span data-stu-id="130fb-120">**IPv4 Address**</span></span>  
 <span data-ttu-id="130fb-121">Se è stato selezionato l'indirizzo IPv4 di una subnet, immettere un indirizzo statico IPv4 valido.</span><span class="sxs-lookup"><span data-stu-id="130fb-121">If you selected the IPv4 subnet address of a subnet, enter a valid IPv4 static address here.</span></span>  
  
 <span data-ttu-id="130fb-122">**Subnet mask**</span><span class="sxs-lookup"><span data-stu-id="130fb-122">**Subnet Mask**</span></span>  
 <span data-ttu-id="130fb-123">Per un indirizzo IPv4, in questo campo di sola lettura viene visualizzata la subnet mask della subnet selezionata.</span><span class="sxs-lookup"><span data-stu-id="130fb-123">For an IPv4 address, this read-only field displays the subnet mask of the selected subnet.</span></span>  
  
 <span data-ttu-id="130fb-124">**Indirizzo IPv6**</span><span class="sxs-lookup"><span data-stu-id="130fb-124">**IPv6 Address**</span></span>  
 <span data-ttu-id="130fb-125">Se è stato selezionato l'indirizzo IPv6 di una subnet, immettere un indirizzo statico IPv6 valido.</span><span class="sxs-lookup"><span data-stu-id="130fb-125">If you selected the IPv6 subnet address of a subnet, enter a valid IPv6 static address here.</span></span>  
  
 <span data-ttu-id="130fb-126">**OK**</span><span class="sxs-lookup"><span data-stu-id="130fb-126">**OK**</span></span>  
 <span data-ttu-id="130fb-127">Fare clic per creare o aggiungere la subnet di cui è stato selezionato l'indirizzo con l'indirizzo IP statico specificato.</span><span class="sxs-lookup"><span data-stu-id="130fb-127">Click to create add the subnet whose address you selected, along with the static IP address that you specified.</span></span> <span data-ttu-id="130fb-128">Verrà aggiunta una riga con tali valori nella griglia della subnet della finestra di dialogo **Nuovo listener gruppo di disponibilità** o **Specifica repliche** .</span><span class="sxs-lookup"><span data-stu-id="130fb-128">A row containing these values will be added to the subnet grid of the **New Availability Group Listener** or **Specify Replicas** dialog box.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="130fb-129">L'indirizzo IP non viene verificato nella finestra di dialogo **Aggiungi indirizzo IP** .</span><span class="sxs-lookup"><span data-stu-id="130fb-129">The **Add IP Address** dialog does not verify the IP address.</span></span> <span data-ttu-id="130fb-130">Inoltre, la finestra di dialogo non impedisce che venga aggiunto il secondo indirizzo per una subnet già aggiunta al listener del gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="130fb-130">Also the dialog does not prevent you from adding the second subnet address for a subnet that you have already added to the availability group listener.</span></span>  
  
 <span data-ttu-id="130fb-131">**Annulla**</span><span class="sxs-lookup"><span data-stu-id="130fb-131">**Cancel**</span></span>  
 <span data-ttu-id="130fb-132">Fare clic per annullare le selezioni e tornare alla finestra di dialogo **Nuovo listener gruppo di disponibilità** o alla scheda **Listener** senza aggiungere un indirizzo IP statico per qualsiasi subnet.</span><span class="sxs-lookup"><span data-stu-id="130fb-132">Click to cancel your selections, and return to the **New Availability Group Listener** dialog box or **Listener** tab without adding a static IP address for any subnet.</span></span>  
  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="130fb-133">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="130fb-133">Related Tasks</span></span>  
  
-   [<span data-ttu-id="130fb-134">Creare o configurare un listener del gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="130fb-134">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
-   [<span data-ttu-id="130fb-135">Utilizzare la finestra di dialogo Nuovo gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="130fb-135">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="130fb-136">Usare la procedura guidata Aggiungi replica a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="130fb-136">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
  
## <a name="see-also"></a><span data-ttu-id="130fb-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="130fb-137">See Also</span></span>  
 <span data-ttu-id="130fb-138">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="130fb-138">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="130fb-139">[Listener del gruppo di disponibilità, connettività client e failover dell'applicazione &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span><span class="sxs-lookup"><span data-stu-id="130fb-139">[Availability Group Listeners, Client Connectivity, and Application Failover &#40;SQL Server&#41;](../../listeners-client-connectivity-application-failover.md) </span></span>  
 [<span data-ttu-id="130fb-140">Connettività client AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="130fb-140">AlwaysOn Client Connectivity (SQL Server)</span></span>](always-on-client-connectivity-sql-server.md)  
  
  
