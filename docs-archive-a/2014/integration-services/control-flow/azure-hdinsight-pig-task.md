---
title: Attività Pig di Azure HDInsight | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afppigtask.f1
- sql11.dts.designer.afppigtask.f1
ms.assetid: 26f34f64-f344-486e-9190-acf71aef29a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 214db5e83272b1fa70c9e70eef8f8b9a43bac095
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626204"
---
# <a name="azure-hdinsight-pig-task"></a><span data-ttu-id="4de45-102">Attività Pig di Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="4de45-102">Azure HDInsight Pig Task</span></span>
<span data-ttu-id="4de45-103">Usare l' **attività Pig di Azure HDInsight** per eseguire uno script Pig in un cluster di Azure HDInsight.</span><span class="sxs-lookup"><span data-stu-id="4de45-103">Use the **Azure HDInsight Pig Task** to run Pig script on an Azure HDInsight cluster.</span></span>
     
<span data-ttu-id="4de45-104">Per aggiungere un' **attività Pig di Azure HDInsight**, trascinare l'attività in Progettazione SSIS e farvi doppio clic oppure clic con il pulsante destro del mouse, quindi scegliere **Modifica** per visualizzare la finestra di dialogo seguente relativa all' **editor dell'attività Pig di Azure HDInsight** .</span><span class="sxs-lookup"><span data-stu-id="4de45-104">To add an **Azure HDInsight Pig Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure HDInsight Pig Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="4de45-105">L'elenco seguente contiene i campi di questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="4de45-105">The following list describes fields in this dialog box.</span></span>  
  
1.  <span data-ttu-id="4de45-106">Per il campo **HDInsightConnection** selezionare un'istanza di Gestione connessione Azure HDInsight esistente oppure creare una nuova istanza che faccia riferimento al cluster HDInsight di Azure usato per eseguire lo script.</span><span class="sxs-lookup"><span data-stu-id="4de45-106">For the **HDInsightConnection** field, select an existing Azure HDInsight Connection Manager or create a new one that refers to the Azure HDInsight cluster used to execute the script.</span></span>
  
2.  <span data-ttu-id="4de45-107">Per il campo **AzureStorageConnection** selezionare un'istanza di Gestione connessione Archiviazione di Azure esistente oppure creare una nuova istanza che faccia riferimento all'account di archiviazione di Azure associato al cluster.</span><span class="sxs-lookup"><span data-stu-id="4de45-107">For the **AzureStorageConnection** field, select an existing Azure Storage Connection Manager or create a new one that refers to the Azure Storage Account associated with the cluster.</span></span> <span data-ttu-id="4de45-108">Questa operazione è necessaria solo se si vuole scaricare l'output dell'esecuzione dello script e i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="4de45-108">This is only necessary if you want to download the script execution output and error logs.</span></span>
 
3.  <span data-ttu-id="4de45-109">Per il campo **BlobContainer** specificare il nome del contenitore di archiviazione associato al cluster.</span><span class="sxs-lookup"><span data-stu-id="4de45-109">For the **BlobContainer** field, specify the storage container name associated with the cluster.</span></span> <span data-ttu-id="4de45-110">Questa operazione è necessaria solo se si vuole scaricare l'output dell'esecuzione dello script e i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="4de45-110">This is only necessary if you want to download the script execution output and error logs.</span></span>
  
4.  <span data-ttu-id="4de45-111">Per il campo **LocalLogFolder** specificare la cartella in cui verranno scaricati l'output dell'esecuzione dello script e i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="4de45-111">For the **LocalLogFolder** field, specify the folder to which the script execution output and error logs will be downloaded to.</span></span> <span data-ttu-id="4de45-112">Questa operazione è necessaria solo se si vuole scaricare l'output dell'esecuzione dello script e i log degli errori.</span><span class="sxs-lookup"><span data-stu-id="4de45-112">This is only necessary if you want to download the script execution output and error logs.</span></span>   
  
5.  <span data-ttu-id="4de45-113">È possibile specificare due modalità di esecuzione dello script Pig:</span><span class="sxs-lookup"><span data-stu-id="4de45-113">There are two ways to specify the Pig script to execute:</span></span>
  
    1.  <span data-ttu-id="4de45-114">**Script inline**: specificare il campo **Script** digitando lo script inline da eseguire nella finestra di dialogo **Immetti script**.</span><span class="sxs-lookup"><span data-stu-id="4de45-114">**In-line script**: Specify the **Script** field by typing in-line the script to execute in the **Enter Script** dialog box.</span></span>
  
    2.  <span data-ttu-id="4de45-115">**File script**: caricare il file script in Archiviazione BLOB di Azure e specificare il campo **BlobName**.</span><span class="sxs-lookup"><span data-stu-id="4de45-115">**Script file**: Upload the script file to Azure Blob Storage and specify the **BlobName** field.</span></span> <span data-ttu-id="4de45-116">Se il BLOB non è presente nell'account di archiviazione o nel contenitore predefinito associato al cluster HDInsight, è necessario specificare i campi **ExternalStorageAccountName** e **ExternalBlobContainer**.</span><span class="sxs-lookup"><span data-stu-id="4de45-116">If the blob is not in the default storage account or container associated with the HDInsight cluster, the **ExternalStorageAccountName** and **ExternalBlobContainer** fields must be specified.</span></span> <span data-ttu-id="4de45-117">Per un BLOB esterno, assicurarsi che sia configurato come accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="4de45-117">For an external blob, make sure that it is configured as publicly accessible.</span></span>  
  
     <span data-ttu-id="4de45-118">Se vengono specificati entrambi, verrà usato il file script e lo script inline verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="4de45-118">If both are specified, script file will be used and the in-line script will be ignored.</span></span>
