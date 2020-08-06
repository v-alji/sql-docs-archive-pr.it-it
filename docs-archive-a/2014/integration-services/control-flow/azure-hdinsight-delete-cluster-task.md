---
title: Attività di eliminazione cluster di Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpdelcltask.f1
- sql11.dts.designer.afpdelcltask.f1
ms.assetid: e298776e-d18a-4393-a8e6-65ee3d555749
author: chugugrace
ms.author: chugu
ms.openlocfilehash: db0a15aaea37c6d18c1d3c2136e0fd0c94eb7506
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636344"
---
# <a name="azure-hdinsight-delete-cluster-task"></a><span data-ttu-id="60f67-102">Attività di eliminazione cluster di Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="60f67-102">Azure HDInsight Delete Cluster Task</span></span>
<span data-ttu-id="60f67-103">L'**attività di eliminazione cluster di Azure HDInsight** consente a un pacchetto di SSIS di eliminare un cluster Azure HDInsight nel gruppo di risorse e nella sottoscrizione di Azure specificati.</span><span class="sxs-lookup"><span data-stu-id="60f67-103">The **Azure HDInsight Delete Cluster Task** enables an SSIS package to delete an Azure HDInsight cluster in the specified Azure subscription and resource group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="60f67-104">L'eliminazione di un cluster HDInsight può richiedere da 10 a 20 minuti circa.</span><span class="sxs-lookup"><span data-stu-id="60f67-104">Deleting an HDInsight cluster may take 10~20 minutes.</span></span>  
  
<span data-ttu-id="60f67-105">Per aggiungere un' **attività di eliminazione cluster di Azure HDInsight**, trascinare l'attività in Progettazione SSIS e farvi doppio clic oppure clic con il pulsante destro del mouse, quindi scegliere **Modifica** per visualizzare la finestra di dialogo seguente relativa all' **editor dell'attività di eliminazione cluster di Azure HDInsight** .</span><span class="sxs-lookup"><span data-stu-id="60f67-105">To add an **Azure HDInsight Delete Cluster Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Delete Cluster Task Editor** dialog box.</span></span>  
  
<span data-ttu-id="60f67-106">La tabella seguente fornisce una descrizione dei campi della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="60f67-106">The following table provides a description for the fields in the dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60f67-107">**Campo**</span><span class="sxs-lookup"><span data-stu-id="60f67-107">**Field**</span></span>|<span data-ttu-id="60f67-108">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="60f67-108">**Description**</span></span>|  
|<span data-ttu-id="60f67-109">AzureResourceManagerConnection</span><span class="sxs-lookup"><span data-stu-id="60f67-109">AzureResourceManagerConnection</span></span>|<span data-ttu-id="60f67-110">Selezionare un'istanza di Gestione connessioni esistente per Azure Resource Manager oppure creare una nuova istanza che verrà usata per eliminare il cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="60f67-110">Select an existing Azure Resource Manager Connection Manager or create a new one that will be used to delete the HDInsight cluster.</span></span>|
|<span data-ttu-id="60f67-111">SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="60f67-111">SubscriptionId</span></span>|<span data-ttu-id="60f67-112">Specificare l'ID della sottoscrizione del cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="60f67-112">Specify the ID of the subscription the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="60f67-113">ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="60f67-113">ResourceGroup</span></span>|<span data-ttu-id="60f67-114">Specificare il gruppo di risorse di Azure in cui si trova il cluster HDInsight.</span><span class="sxs-lookup"><span data-stu-id="60f67-114">Specify the Azure resource group the HDInsight cluster is in.</span></span>|
|<span data-ttu-id="60f67-115">ClusterName</span><span class="sxs-lookup"><span data-stu-id="60f67-115">ClusterName</span></span>|<span data-ttu-id="60f67-116">Consente di specificare il nome del cluster da eliminare.</span><span class="sxs-lookup"><span data-stu-id="60f67-116">Specify the name of the cluster to be deleted.</span></span>|  
|<span data-ttu-id="60f67-117">FailIfNotExists</span><span class="sxs-lookup"><span data-stu-id="60f67-117">FailIfNotExists</span></span>|<span data-ttu-id="60f67-118">Consente di indicare se l'attività deve avere esito negativo se il cluster non esiste.</span><span class="sxs-lookup"><span data-stu-id="60f67-118">Specify whether the task should fail if the cluster does not exist.</span></span>|
