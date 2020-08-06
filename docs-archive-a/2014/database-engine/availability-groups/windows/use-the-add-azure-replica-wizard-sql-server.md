---
title: Usare la procedura guidata Aggiungi replica Azure (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.azurereplica.f1
ms.assetid: b89cc41b-07b4-49f3-82cc-bc42b2e793ae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8f7ee9e80f0511fe23aebb887b15b5e8b7e9cabf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712380"
---
# <a name="use-the-add-azure-replica-wizard-sql-server"></a><span data-ttu-id="0572f-102">Utilizzare la procedura guidata Aggiungi replica Azure (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0572f-102">Use the Add Azure Replica Wizard (SQL Server)</span></span>
  <span data-ttu-id="0572f-103">Usare la procedura guidata Aggiungi replica Azure per creare una nuova macchina virtuale di Azure in un ambiente IT ibrido e configurarla come replica secondaria per un gruppo di disponibilità AlwaysOn nuovo o esistente.</span><span class="sxs-lookup"><span data-stu-id="0572f-103">Use the Add Azure Replica Wizard to help you create a new Azure VM in hybrid IT and configure it as a secondary replica for a new or existing AlwaysOn availability group.</span></span>  
  
-   <span data-ttu-id="0572f-104">**Prima di iniziare:**</span><span class="sxs-lookup"><span data-stu-id="0572f-104">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0572f-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0572f-105">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="0572f-106">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0572f-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0572f-107">**Per aggiungere una replica mediante:**  [Procedura guidata Aggiungi replica Azure (SQL Server Management Studio)](#SSMSProcedure)</span><span class="sxs-lookup"><span data-stu-id="0572f-107">**To add a replica, using:**  [Add Azure Replica Wizard (SQL Server Management Studio)](#SSMSProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0572f-108">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0572f-108">Before You Begin</span></span>  
 <span data-ttu-id="0572f-109">Se non è mai stata aggiunta una replica di disponibilità a un gruppo di disponibilità, vedere le sezioni "istanze del server" e "repliche e gruppi di disponibilità" in [prerequisiti, restrizioni e consigli per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="0572f-109">If you have never added any availability replica to an availability group, see the "Server instances" and "Availability groups and replicas" sections in [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="0572f-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0572f-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="0572f-111">È necessario essere connessi all'istanza del server che ospita la replica primaria corrente.</span><span class="sxs-lookup"><span data-stu-id="0572f-111">You must be connected to the server instance that hosts the current primary replica.</span></span>  
  
-   <span data-ttu-id="0572f-112">È necessario usare un ambiente IT ibrido in cui nella subnet locale sia presente una VPN da sito a sito con Azure.</span><span class="sxs-lookup"><span data-stu-id="0572f-112">You must have a hybrid-IT environment where your on-premise subnet has a site-to-site VPN with Azure.</span></span> <span data-ttu-id="0572f-113">Per altre informazioni, vedere [Creare una rete virtuale con una connessione VPN da sito a sito usando il portale di Azure classico](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span><span class="sxs-lookup"><span data-stu-id="0572f-113">For more information, see [Configure a Site-to-Site VPN in the Management Portal](https://azure.microsoft.com/documentation/articles/vpn-gateway-site-to-site-create).</span></span>  
  
-   <span data-ttu-id="0572f-114">Il gruppo di disponibilità deve contenere le repliche di disponibilità locali.</span><span class="sxs-lookup"><span data-stu-id="0572f-114">Your availability group must contain on-premise availability replicas.</span></span>  
  
-   <span data-ttu-id="0572f-115">I client nel listener del gruppo di disponibilità devono avere la connettività a Internet se vogliono mantenere la connettività con il listener quando viene eseguito il failover del gruppo di disponibilità in una replica di Azure.</span><span class="sxs-lookup"><span data-stu-id="0572f-115">Clients to the availability group listener must have connectivity to the Internet if they want to maintain connectivity with the listener when the availability group is failed over to an Azure replica.</span></span>  
  
-   <span data-ttu-id="0572f-116">**Prerequisiti per l'utilizzo della sincronizzazione dei dati iniziale completa** È necessario specificare una condivisione di rete affinché la procedura guidata possa creare e accedere ai backup.</span><span class="sxs-lookup"><span data-stu-id="0572f-116">**Prerequisites for using full initial data synchronization** You will need to specify a network share in order for the wizard to create and access backups.</span></span> <span data-ttu-id="0572f-117">Per la replica primaria, all'account usato per avviare il [!INCLUDE[ssDE](../../../includes/ssde-md.md)] devono essere associate le autorizzazioni del file system in lettura e scrittura per una condivisione di rete.</span><span class="sxs-lookup"><span data-stu-id="0572f-117">For the primary replica, the account used to start the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must have read and write file-system permissions on a network share.</span></span> <span data-ttu-id="0572f-118">Per le repliche secondarie, all'account deve essere associata l'autorizzazione di lettura per la condivisione di rete.</span><span class="sxs-lookup"><span data-stu-id="0572f-118">For secondary replicas, the account must have read permission on the network share.</span></span>  
  
     <span data-ttu-id="0572f-119">Se non è possibile usare la procedura guidata per eseguire la sincronizzazione dei dati iniziale completa, sarà necessario preparare i database secondari manualmente.</span><span class="sxs-lookup"><span data-stu-id="0572f-119">If you are unable to use the wizard to perform full initial data synchronization, you need to prepare your secondary databases manually.</span></span> <span data-ttu-id="0572f-120">Tale operazione può essere eseguita prima o dopo l'esecuzione della procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="0572f-120">You can do this before or after running the wizard.</span></span> <span data-ttu-id="0572f-121">Per altre informazioni, vedere [Preparare manualmente un database secondario per un gruppo di disponibilità &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0572f-121">For more information, see [Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0572f-122">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0572f-122">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0572f-123">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="0572f-123">Permissions</span></span>  
 <span data-ttu-id="0572f-124">Vedere [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span><span class="sxs-lookup"><span data-stu-id="0572f-124">See [Security](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md#Security)</span></span>  
  
##  <a name="using-the-add-azure-replica-wizard-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0572f-125">Utilizzo della procedura guidata Aggiungi replica Azure (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="0572f-125">Using the Add Azure Replica Wizard (SQL Server Management Studio)</span></span>  
 <span data-ttu-id="0572f-126">La procedura guidata Aggiungi replica Azure può essere avviata dalla [Pagina Specifica repliche](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0572f-126">The Add Azure Replica Wizard can be launched from the [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md).</span></span> <span data-ttu-id="0572f-127">Questa pagina può essere visualizzata in due modi:</span><span class="sxs-lookup"><span data-stu-id="0572f-127">There are two ways to reach this page:</span></span>  
  
-   [<span data-ttu-id="0572f-128">Usare la Creazione guidata Gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0572f-128">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="0572f-129">Usare la procedura guidata Aggiungi replica a gruppo di disponibilità &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="0572f-129">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
 <span data-ttu-id="0572f-130">Dopo aver avviato la procedura guidata Aggiungi replica Azure effettuare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0572f-130">Once you have launched the Add Azure Replica Wizard, follow the steps below:</span></span>  
  
1.  <span data-ttu-id="0572f-131">Scaricare prima un certificato di gestione per la sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="0572f-131">First, download a management certificate for your Azure subscription.</span></span> <span data-ttu-id="0572f-132">Fare clic su **Download** per aprire la pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="0572f-132">Click **Download** to open the sign-in page.</span></span>  
  
2.  <span data-ttu-id="0572f-133">Nella pagina di accesso accedere alla sottoscrizione di Azure.</span><span class="sxs-lookup"><span data-stu-id="0572f-133">In the sign-in page, sign in to your Azure subscription.</span></span> <span data-ttu-id="0572f-134">Una volta eseguito l'accesso la procedura guidata installa un certificato di gestione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="0572f-134">Once you are signed in, the wizard installs a management certificate onto your local machine.</span></span> <span data-ttu-id="0572f-135">Il certificato di gestione viene caricato automaticamente quando si utilizza di nuovo questa procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="0572f-135">This management certificate is automatically loaded when you use this wizard again.</span></span> <span data-ttu-id="0572f-136">Se sono stati scaricati più certificati di gestione, è possibile fare clic sul pulsante **...** per selezionare il certificato che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="0572f-136">If you have downloaded multiple management certificates, you can click the **...** button to select the one you want to use.</span></span>  
  
3.  <span data-ttu-id="0572f-137">Connettersi quindi alla sottoscrizione facendo clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="0572f-137">Next, connect to your subscription by clicking **Connect**.</span></span> <span data-ttu-id="0572f-138">Dopo aver eseguito la connessione, gli elenchi a discesa vengono popolati con i parametri di Azure, ad esempio **Rete virtuale** e **Subnet rete virtuale**.</span><span class="sxs-lookup"><span data-stu-id="0572f-138">Once you are connected, the drop-down lists are populated with your Azure parameters, such as **Virtual Network** and **Virtual Network Subnet**.</span></span>  
  
4.  <span data-ttu-id="0572f-139">Specificare le impostazioni per la macchina virtuale di Azure che ospiterà la nuova replica secondaria:</span><span class="sxs-lookup"><span data-stu-id="0572f-139">Specify the settings for the Azure VM that will host the new secondary replica:</span></span>  
  
     <span data-ttu-id="0572f-140">Immagine</span><span class="sxs-lookup"><span data-stu-id="0572f-140">Image</span></span>  
     <span data-ttu-id="0572f-141">Nome dell'immagine di SQL Server da usare per la macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="0572f-141">The name of the SQL Server image to use for the Azure VM</span></span>  
  
     <span data-ttu-id="0572f-142">Dimensioni macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="0572f-142">VM Size</span></span>  
     <span data-ttu-id="0572f-143">Dimensioni della macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="0572f-143">The size of the Azure VM</span></span>  
  
     <span data-ttu-id="0572f-144">Nome macchina virtuale</span><span class="sxs-lookup"><span data-stu-id="0572f-144">VM Name</span></span>  
     <span data-ttu-id="0572f-145">Nome DNS della macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="0572f-145">The DNS name of the Azure VM</span></span>  
  
     <span data-ttu-id="0572f-146">Nome utente VM</span><span class="sxs-lookup"><span data-stu-id="0572f-146">VM Username</span></span>  
     <span data-ttu-id="0572f-147">Nome utente dell'amministratore predefinito della macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="0572f-147">The username of the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="0572f-148">Password amministratore VM (e Conferma password)</span><span class="sxs-lookup"><span data-stu-id="0572f-148">VM Administrator Password (and Confirm Password)</span></span>  
     <span data-ttu-id="0572f-149">Password dell'amministratore predefinito della macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="0572f-149">The password for the default administrator for the Azure VM</span></span>  
  
     <span data-ttu-id="0572f-150">Rete virtuale</span><span class="sxs-lookup"><span data-stu-id="0572f-150">Virtual Network</span></span>  
     <span data-ttu-id="0572f-151">Rete virtuale in cui posizionare la macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="0572f-151">The virtual network in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="0572f-152">Subnet rete virtuale</span><span class="sxs-lookup"><span data-stu-id="0572f-152">Virtual Network Subnet</span></span>  
     <span data-ttu-id="0572f-153">Subnet della rete virtuale in cui posizionare la macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="0572f-153">The virtual network subnet in which to place the Azure VM</span></span>  
  
     <span data-ttu-id="0572f-154">Dominio</span><span class="sxs-lookup"><span data-stu-id="0572f-154">Domain</span></span>  
     <span data-ttu-id="0572f-155">Dominio Active Directory (AD) a cui aggiungere la macchina virtuale di Azure</span><span class="sxs-lookup"><span data-stu-id="0572f-155">The Active Directory (AD) domain to join the Azure VM</span></span>  
  
     <span data-ttu-id="0572f-156">Nome utente di dominio</span><span class="sxs-lookup"><span data-stu-id="0572f-156">Domain Username</span></span>  
     <span data-ttu-id="0572f-157">Nome utente di Active Directory usato per aggiungere la macchina virtuale di Azure al dominio</span><span class="sxs-lookup"><span data-stu-id="0572f-157">The AD username used to join the Azure VM to the domain</span></span>  
  
     <span data-ttu-id="0572f-158">Password</span><span class="sxs-lookup"><span data-stu-id="0572f-158">Password</span></span>  
     <span data-ttu-id="0572f-159">Password usata per aggiungere la macchina virtuale di Azure al dominio</span><span class="sxs-lookup"><span data-stu-id="0572f-159">The password used to join the Azure VM to the domain</span></span>  
  
5.  <span data-ttu-id="0572f-160">Fare clic su **OK** per eseguire il commit delle impostazioni e chiudere la procedura guidata Aggiungi replica Azure.</span><span class="sxs-lookup"><span data-stu-id="0572f-160">Click **OK** to commit your settings and exit the Add Azure Replica Wizard.</span></span>  
  
6.  <span data-ttu-id="0572f-161">Continuare con il resto dei passaggi di configurazione della [Pagina Specifica repliche](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) come per qualsiasi nuova replica.</span><span class="sxs-lookup"><span data-stu-id="0572f-161">Continue with the rest of the configuration steps for [Specify Replicas Page](specify-replicas-page-new-availability-group-wizard-add-replica-wizard.md) as you do for any new replica.</span></span>  
  
     <span data-ttu-id="0572f-162">Al termine della creazione guidata gruppo di disponibilità o della procedura guidata Aggiungi replica a gruppo di disponibilità, il processo di configurazione esegue tutte le operazioni in Azure per creare la nuova macchina virtuale, aggiungerla al dominio AD, aggiungerla al cluster di Windows, abilitare la disponibilità elevata AlwaysOn e aggiungere la nuova replica al gruppo di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="0572f-162">Once you are finished with the Availability Group Wizard or the Add Replica to Availability Group Wizard, the configuration process performs all operations in Azure to create the new VM, join it to the AD domain, add it to the Windows cluster, enable AlwaysOn High Availability, and add the new replica to the availability group.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="0572f-163">Attività correlate</span><span class="sxs-lookup"><span data-stu-id="0572f-163">Related Tasks</span></span>  
  
-   [<span data-ttu-id="0572f-164">Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0572f-164">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="0572f-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0572f-165">See Also</span></span>  
 <span data-ttu-id="0572f-166">[Panoramica di Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="0572f-166">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="0572f-167">[Prerequisiti, restrizioni e consigli per Gruppi di disponibilità AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="0572f-167">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 [<span data-ttu-id="0572f-168">Aggiungere una replica secondaria a un gruppo di disponibilità &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0572f-168">Add a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](add-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
  
