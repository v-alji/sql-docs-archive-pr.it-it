---
title: Feature Pack di Azure | Microsoft Docs
ms.custom: ''
ms.date: 08/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL11.SSIS.AZURE.F1
- SQL12.SSIS.AZURE.F1
ms.assetid: 31de555f-ae62-4f2f-a6a6-77fea1fa8189
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8bca2b4d3ce91f6010fbe01da836efd8a67ca6bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87712335"
---
# <a name="azure-feature-pack"></a><span data-ttu-id="8b81b-102">Azure Feature Pack</span><span class="sxs-lookup"><span data-stu-id="8b81b-102">Azure Feature Pack</span></span>
<span data-ttu-id="8b81b-103">Il Feature Pack di SQL Server Integration Services (SSIS) per Azure è un'estensione che fornisce i componenti elencati in questa pagina per consentire a SSIS di connettersi ai servizi Azure, trasferire i dati tra Azure e le origini dati locali ed elaborare i dati archiviati in Azure.</span><span class="sxs-lookup"><span data-stu-id="8b81b-103">SQL Server Integration Services (SSIS) Feature Pack for Azure is an extension that provides the components listed on this page for SSIS to connect to Azure services, transfer data between Azure and on-premises data sources, and process data stored in Azure.</span></span>

## <a name="components-in-the-feature-pack"></a><span data-ttu-id="8b81b-104">Componenti del Feature Pack</span><span class="sxs-lookup"><span data-stu-id="8b81b-104">Components in the Feature Pack</span></span>
  
-   <span data-ttu-id="8b81b-105">Gestioni connessioni</span><span class="sxs-lookup"><span data-stu-id="8b81b-105">Connection Managers</span></span>  
  
    -   [<span data-ttu-id="8b81b-106">Gestione connessione dell'archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="8b81b-106">Azure Storage Connection Manager</span></span>](connection-manager/azure-storage-connection-manager.md)  
  
    -   [<span data-ttu-id="8b81b-107">Gestione connessione della sottoscrizione di Azure</span><span class="sxs-lookup"><span data-stu-id="8b81b-107">Azure Subscription Connection Manager</span></span>](connection-manager/azure-subscription-connection-manager.md)  
    
    -   [<span data-ttu-id="8b81b-108">Gestione connessioni di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="8b81b-108">Azure Data Lake Store Connection Manager</span></span>](../../2014/integration-services/azure-data-lake-store-connection-manager.md)
    
    -   [<span data-ttu-id="8b81b-109">Gestione connessione Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="8b81b-109">Azure Resource Manager Connection Manager</span></span>](../../2014/integration-services/azure-resource-manager-connection-manager.md)
    
    -   [<span data-ttu-id="8b81b-110">Gestione connessione Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="8b81b-110">Azure HDInsight Connection Manager</span></span>](../../2014/integration-services/azure-hdinsight-connection-manager.md)
  
-   <span data-ttu-id="8b81b-111">Attività</span><span class="sxs-lookup"><span data-stu-id="8b81b-111">Tasks</span></span>  
  
    -   [<span data-ttu-id="8b81b-112">Attività di caricamento BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="8b81b-112">Azure Blob Upload Task</span></span>](control-flow/azure-blob-upload-task.md)  
  
    -   [<span data-ttu-id="8b81b-113">Attività di download BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="8b81b-113">Azure Blob Download Task</span></span>](control-flow/azure-blob-download-task.md)  
  
    -   [<span data-ttu-id="8b81b-114">Attività Hive di Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="8b81b-114">Azure HDInsight Hive Task</span></span>](control-flow/azure-hdinsight-hive-task.md)  
  
    -   <span data-ttu-id="8b81b-115">[Attività Pig di Azure HDInsight](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="8b81b-115">[Azure HDInsight Pig Task](https://msdn.microsoft.com/library/mt146781(v=sql.120).aspx)</span></span>
  
    -   [<span data-ttu-id="8b81b-116">Attività di creazione cluster di Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="8b81b-116">Azure HDInsight Create Cluster Task</span></span>](control-flow/azure-hdinsight-create-cluster-task.md)  
  
    -   [<span data-ttu-id="8b81b-117">Attività di eliminazione cluster di Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="8b81b-117">Azure HDInsight Delete Cluster Task</span></span>](control-flow/azure-hdinsight-delete-cluster-task.md)
    
    -   [<span data-ttu-id="8b81b-118">Attività di caricamento di Azure SQL DW</span><span class="sxs-lookup"><span data-stu-id="8b81b-118">Azure SQL DW Upload Task</span></span>](../../2014/integration-services/azure-sql-dw-upload-task.md)    
    
    -   [<span data-ttu-id="8b81b-119">Attività File system di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="8b81b-119">Azure Data Lake Store File System Task</span></span>](control-flow/file-system-task.md)    
  
-   <span data-ttu-id="8b81b-120">Componenti del flusso di dati</span><span class="sxs-lookup"><span data-stu-id="8b81b-120">Data Flow Components</span></span>  
  
    -   <span data-ttu-id="8b81b-121">[Origine BLOB di Azure](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span><span class="sxs-lookup"><span data-stu-id="8b81b-121">[Azure Blob Source](https://msdn.microsoft.com/library/mt146775(v=sql.120).aspx)</span></span>  
  
    -   [<span data-ttu-id="8b81b-122">Destinazione BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="8b81b-122">Azure Blob Destination</span></span>](data-flow/azure-blob-destination.md)  
    
    -   [<span data-ttu-id="8b81b-123">Origine di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="8b81b-123">Azure Data Lake Store Source</span></span>](../../2014/integration-services/azure-data-lake-store-source.md)
    
    -   [<span data-ttu-id="8b81b-124">Destinazione di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="8b81b-124">Azure Data Lake Store Destination</span></span>](../../2014/integration-services/azure-data-lake-store-destination.md)
  
-   <span data-ttu-id="8b81b-125">Enumeratore BLOB di Azure & enumeratore del file ADLS.</span><span class="sxs-lookup"><span data-stu-id="8b81b-125">Azure Blob Enumerator & ADLS File Enumerator.</span></span> <span data-ttu-id="8b81b-126">Vedere [contenitore ciclo foreach](control-flow/foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="8b81b-126">See [Foreach Loop Container](control-flow/foreach-loop-container.md).</span></span>  
  
 
## <a name="download-the-feature-pack"></a><span data-ttu-id="8b81b-127">Scaricare il Feature Pack</span><span class="sxs-lookup"><span data-stu-id="8b81b-127">Download the Feature Pack</span></span>  
<span data-ttu-id="8b81b-128">Scaricare il Feature Pack di SQL Server Integration Services (SSIS) per Azure.</span><span class="sxs-lookup"><span data-stu-id="8b81b-128">Download the SQL Server Integration Services (SSIS) Feature Pack for Azure.</span></span>  
  
-   [<span data-ttu-id="8b81b-129">Microsoft SQL Server 2014 Integration Services Feature Pack per Azure</span><span class="sxs-lookup"><span data-stu-id="8b81b-129">Microsoft SQL Server 2014 Integration Services Feature Pack for Azure</span></span>](https://www.microsoft.com/download/details.aspx?id=47366)  

## <a name="prerequisites"></a><span data-ttu-id="8b81b-130">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="8b81b-130">Prerequisites</span></span>  
<span data-ttu-id="8b81b-131">Prima di installare questo Feature Pack, è necessario installare i prerequisiti seguenti.</span><span class="sxs-lookup"><span data-stu-id="8b81b-131">You must install the following prerequisites before installing this feature pack.</span></span>  
  
-   <span data-ttu-id="8b81b-132">SQL Server Integration Services</span><span class="sxs-lookup"><span data-stu-id="8b81b-132">SQL Server Integration Services</span></span>  
-   <span data-ttu-id="8b81b-133">.Net Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8b81b-133">.Net Framework 4.5</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="8b81b-134">Scenari</span><span class="sxs-lookup"><span data-stu-id="8b81b-134">Scenarios</span></span>  
  
### <a name="big-data-processing"></a><span data-ttu-id="8b81b-135">Elaborazione di Big Data</span><span class="sxs-lookup"><span data-stu-id="8b81b-135">Big Data Processing</span></span>  
 <span data-ttu-id="8b81b-136">Usare il connettore di Azure per completare l'elaborazione di Big Data:</span><span class="sxs-lookup"><span data-stu-id="8b81b-136">Use Azure Connector to complete following big data processing work:</span></span>  
  
1.  <span data-ttu-id="8b81b-137">Usare l'attività di caricamento BLOB di Azure per caricare i dati di input nell'archivio BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="8b81b-137">Use the Azure Blob Upload Task to upload input data to Azure Blob Storage.</span></span>  
  
2.  <span data-ttu-id="8b81b-138">Usare l'attività di creazione cluster di Azure HDInsight per creare un cluster di Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="8b81b-138">Use the Azure HDInsight Create Cluster Task to create an Azure HDInsight cluster.</span></span> <span data-ttu-id="8b81b-139">Questo passaggio è facoltativo se si vuole usare un cluster personale.</span><span class="sxs-lookup"><span data-stu-id="8b81b-139">This step is optional if you want to use your own cluster.</span></span>  
  
3.  <span data-ttu-id="8b81b-140">Usare l'attività Hive o Pig di Azure HDInsight per richiamare un processo Pig o Hive nel cluster di Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="8b81b-140">Use the Azure HDInsight Hive Task or Azure HDInsight Pig Task to invoke a Pig or Hive job on the Azure HDInsight cluster.</span></span>  
  
4.  <span data-ttu-id="8b81b-141">Usare l'attività di eliminazione cluster di Azure HDInsight per eliminare il cluster di HDInsight dopo l'uso se è stato creato un cluster di HDInsight su richiesta nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="8b81b-141">Use the Azure HDInsight Delete Cluster Task to delete the HDInsight Cluster after use if you have created an on-demand HDInsight cluster in step #2.</span></span>  
  
5.  <span data-ttu-id="8b81b-142">Usare l'attività di download BLOB di Azure HDInsight per scaricare i dati di output Pig/Hive dall'archivio BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="8b81b-142">Use the Azure HDInsight Blob Download Task to download the Pig/Hive output data from the Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="8b81b-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span><span class="sxs-lookup"><span data-stu-id="8b81b-143">![SSIS-AzureConnector-BigDataScenario](media/ssis-azureconnector-bigdatascenario.png "SSIS-AzureConnector-BigDataScenario")</span></span>  
  
### <a name="cloud-data-archiving"></a><span data-ttu-id="8b81b-144">Archiviazione dei dati cloud</span><span class="sxs-lookup"><span data-stu-id="8b81b-144">Cloud Data Archiving</span></span>  
 <span data-ttu-id="8b81b-145">Usare la destinazione BLOB di Azure in un pacchetto SSIS per scrivere i dati di output in un archivio BLOB di Azure oppure usare l'origine BLOB di Azure per leggere i dati da un archivio BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="8b81b-145">Use the Azure Blob Destination in an SSIS package to write output data to an Azure Blob Storage, or use the Azure Blob Source to read data from an Azure Blob Storage.</span></span>  
  
 <span data-ttu-id="8b81b-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span><span class="sxs-lookup"><span data-stu-id="8b81b-146">![SSIS-AzureConnector-CloudArchive-1](media/ssis-azureconnector-cloudarchive-1.png "SSIS-AzureConnector-CloudArchive-1")</span></span>  
  
 <span data-ttu-id="8b81b-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span><span class="sxs-lookup"><span data-stu-id="8b81b-147">![SSIS-AzureConnector-CloudArchive-2](media/ssis-azureconnector-cloudarchive-2.png "SSIS-AzureConnector-CloudArchive-2")</span></span>  
  
 <span data-ttu-id="8b81b-148">Inoltre, usare il contenitore Ciclo Foreach con l'enumeratore BLOB di Azure per elaborare i dati in più file BLOB.</span><span class="sxs-lookup"><span data-stu-id="8b81b-148">And use the Foreach Loop Container with Azure Blob Enumerator to process data in multiple bob files.</span></span>  
  
 <span data-ttu-id="8b81b-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span><span class="sxs-lookup"><span data-stu-id="8b81b-149">![SSIS-AzureConnector-CloudArchive-3](media/ssis-azureconnector-cloudarchive-3.png "SSIS-AzureConnector-CloudArchive-3")</span></span>  
  
  
