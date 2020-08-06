---
title: Attività di creazione cluster di Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpcreatecltask.f1
- sql11.dts.designer.afpcreatecltask.f1
ms.assetid: a8ec413a-38d3-45df-887e-6f5f4d9f8465
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e4029e3a01cbcfe04be5f2879a9b60866bfc867a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713391"
---
# <a name="azure-hdinsight-create-cluster-task"></a><span data-ttu-id="d7d9b-102">Attività di creazione cluster di Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="d7d9b-102">Azure HDInsight Create Cluster Task</span></span>
<span data-ttu-id="d7d9b-103">L' **attività di creazione cluster di Azure HDInsight** consente a un pacchetto di SSIS di creare un cluster Azure HDInsight nella sottoscrizione e nel gruppo di risorse di Azure specificati.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-103">The **Azure HDInsight Create Cluster Task** enables an SSIS package to create an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]  
> - <span data-ttu-id="d7d9b-104">La creazione di un nuovo cluster HDInsight può richiedere da 10 a 20 minuti circa.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-104">Creating a new HDInsight cluster may take 10~20 minutes.</span></span>  
> - <span data-ttu-id="d7d9b-105">Alla creazione ed esecuzione di un cluster HDInsight di Azure è associato un costo.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-105">There is a cost associated with creating and running an Azure HDInsight cluster.</span></span> <span data-ttu-id="d7d9b-106">Per altre informazioni, vedere [Prezzi di HDInsight](https://azure.microsoft.com/pricing/details/hdinsight/).</span><span class="sxs-lookup"><span data-stu-id="d7d9b-106">See [HDInsight Pricing](https://azure.microsoft.com/pricing/details/hdinsight/) for details.</span></span>  
  
<span data-ttu-id="d7d9b-107">Per aggiungere un' **attività di creazione cluster di Azure HDInsight**, trascinare l'attività in Progettazione SSIS e farvi doppio clic oppure clic con il pulsante destro del mouse, quindi scegliere **Modifica** per visualizzare la finestra di dialogo seguente relativa all' **editor dell'attività di creazione cluster di Azure HDInsight** .</span><span class="sxs-lookup"><span data-stu-id="d7d9b-107">To add an **Azure HDInsight Create Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Create Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="d7d9b-108">La tabella seguente offre una descrizione dei campi della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-108">The following table provides a description of the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7d9b-109">**Campo**</span><span class="sxs-lookup"><span data-stu-id="d7d9b-109">**Field**</span></span>|<span data-ttu-id="d7d9b-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="d7d9b-110">**Description**</span></span>|  
|<span data-ttu-id="d7d9b-111">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="d7d9b-111">AzureResourceManagerConnection</span></span>|<span data-ttu-id="d7d9b-112">Selezionare un'istanza di Gestione connessioni esistente per Azure Resource Manager oppure creare una nuova istanza che verrà usata per creare il cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-112">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to create the HDInsight cluster.</span></span>|  
|<span data-ttu-id="d7d9b-113">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="d7d9b-113">AzureStorageConnection</span></span>|<span data-ttu-id="d7d9b-114">Selezionare una gestione connessione di archiviazione di Azure esistente o crearne una nuova che si riferisca a un Account di archiviazione Azure che sarà associato al cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-114">Select an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account that will be associated with the HDInsight cluster.</span></span>|
|<span data-ttu-id="d7d9b-115">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="d7d9b-115">SubscriptionId</span></span>|<span data-ttu-id="d7d9b-116">Specificare l'ID della sottoscrizione in cui verrà creato il cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-116">Specify the ID of the subscription the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="d7d9b-117">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="d7d9b-117">ResourceGroup</span></span>|<span data-ttu-id="d7d9b-118">Specificare il gruppo di risorse di Azure in cui verrà creato il cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-118">Specify the Azure resource group the HDInsight cluster will be created in.</span></span>|
|<span data-ttu-id="d7d9b-119">Location</span><span class="sxs-lookup"><span data-stu-id="d7d9b-119">Location</span></span>|<span data-ttu-id="d7d9b-120">Specificare il percorso del cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-120">Specify the location of the HDInsight cluster.</span></span> <span data-ttu-id="d7d9b-121">Il cluster deve essere creato nella stessa posizione specificata nell'account di Archiviazione di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-121">The cluster must be created in the same location as the Azure Storage Account specified.</span></span>|  
|<span data-ttu-id="d7d9b-122">ClusterName</span><span class="sxs-lookup"><span data-stu-id="d7d9b-122">ClusterName</span></span>|<span data-ttu-id="d7d9b-123">Specificare un nome per il cluster HDInsight da creare.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-123">Specify a name for the HDInsight cluster to be created.</span></span>|  
|<span data-ttu-id="d7d9b-124">clusterSize</span><span class="sxs-lookup"><span data-stu-id="d7d9b-124">ClusterSize</span></span>|<span data-ttu-id="d7d9b-125">Specificare il numero di nodi da creare nel cluster.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-125">Specify the number of nodes to create in the cluster.</span></span>|  
|<span data-ttu-id="d7d9b-126">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="d7d9b-126">BlobContainer</span></span>|<span data-ttu-id="d7d9b-127">Specificare il nome del contenitore di archiviazione predefinito da associare al cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-127">Specify the name of the default storage container to be associated with the HDInsight cluster.</span></span>|  
|<span data-ttu-id="d7d9b-128">UserName</span><span class="sxs-lookup"><span data-stu-id="d7d9b-128">UserName</span></span>|<span data-ttu-id="d7d9b-129">Specificare il nome utente da usare per la connessione al cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-129">Specify the user name to be used for connecting to the HDInsight cluster.</span></span>|  
|<span data-ttu-id="d7d9b-130">Password</span><span class="sxs-lookup"><span data-stu-id="d7d9b-130">Password</span></span>|<span data-ttu-id="d7d9b-131">Specificare la password da usare per la connessione al cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-131">Specify the password to be used for connecting to the HDInsight cluster.</span></span>|
|<span data-ttu-id="d7d9b-132">SshUserName</span><span class="sxs-lookup"><span data-stu-id="d7d9b-132">SshUserName</span></span>|<span data-ttu-id="d7d9b-133">Specificare il nome utente usato per accedere in remoto al cluster HDInsight con SSH.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-133">Specify the user name used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="d7d9b-134">SshPassword</span><span class="sxs-lookup"><span data-stu-id="d7d9b-134">SshPassword</span></span>|<span data-ttu-id="d7d9b-135">Specificare la password usata per accedere in remoto al cluster HDInsight con SSH.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-135">Specify the password used to remotely access the HDInsight cluster using SSH.</span></span>|
|<span data-ttu-id="d7d9b-136">FailIfExists</span><span class="sxs-lookup"><span data-stu-id="d7d9b-136">FailIfExists</span></span>|<span data-ttu-id="d7d9b-137">Specificare se l'attività non dovrà riuscire se il cluster esiste già.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-137">Specify whether the task should fail if the cluster already exists.</span></span>|  
  
> [!NOTE]  
> <span data-ttu-id="d7d9b-138">Il percorso del cluster HDInsight e dell'account di archiviazione di Azure deve essere lo stesso.</span><span class="sxs-lookup"><span data-stu-id="d7d9b-138">The locations of the HDInsight cluster and the Azure Storage Account must be the same.</span></span>
