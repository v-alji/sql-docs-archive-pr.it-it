---
title: Attività File system di Azure Data Lake Store | Microsoft Docs
ms.custom: ''
ms.date: 01/09/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSTASK.F1
- SQL11.DTS.DESIGNER.AFPADLSTASK.F1
ms.assetid: 02b9edd7-6ef9-463e-abbf-e1830bcae875
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1bc37e774c5346190635e50259deb47f2f22a054
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630002"
---
# <a name="azure-data-lake-store-file-system-task"></a><span data-ttu-id="84f58-102">Attività File system di Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="84f58-102">Azure Data Lake Store File System Task</span></span>

<span data-ttu-id="84f58-103">L' **attività Azure Data Lake Store file System** consente agli utenti di eseguire varie operazioni di file system su [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span><span class="sxs-lookup"><span data-stu-id="84f58-103">The **Azure Data Lake Store File System Task** enables users to perform various file system operations on [Azure Data Lake Store (ADLS)](https://azure.microsoft.com/services/data-lake-store/).</span></span>

<span data-ttu-id="84f58-104">Per aggiungere un'attività File System di Azure Data Lake Store a un pacchetto, trascinarla dalla casella degli strumenti SSIS ai canvas di progettazione.</span><span class="sxs-lookup"><span data-stu-id="84f58-104">To add an Azure Data Lake Store File System Task to a package, drag it from SSIS Toolbox to the designer canvas.</span></span> <span data-ttu-id="84f58-105">Fare quindi doppio clic sull'attività o fare clic con il pulsante destro del mouse sull'attività e scegliere **modifica**per aprire la finestra di dialogo Editor attività.</span><span class="sxs-lookup"><span data-stu-id="84f58-105">Then double-click the task, or right-click the task and select **Edit**, to open the task editor dialog box.</span></span>

<span data-ttu-id="84f58-106">La proprietà **Operation** specifica l'operazione del file system da eseguire.</span><span class="sxs-lookup"><span data-stu-id="84f58-106">The **Operation** property specifies the file system operation to perform.</span></span> <span data-ttu-id="84f58-107">Le operazioni supportate sono elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="84f58-107">The following operations are supported.</span></span>

* <span data-ttu-id="84f58-108">**CopyToADLS** per caricare file in ADLS.</span><span class="sxs-lookup"><span data-stu-id="84f58-108">**CopyToADLS:** Upload files to ADLS.</span></span>
* <span data-ttu-id="84f58-109">**CopyFromADLS** per scaricare file da ADLS.</span><span class="sxs-lookup"><span data-stu-id="84f58-109">**CopyFromADLS:** Download files from ADLS.</span></span>

<span data-ttu-id="84f58-110">Per qualsiasi operazione è necessario specificare una gestione della connessione di Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="84f58-110">For any operation, you have to specify an Azure Data Lake connection manager.</span></span>

<span data-ttu-id="84f58-111">Di seguito sono riportate le descrizioni delle proprietà specifiche per ogni operazione.</span><span class="sxs-lookup"><span data-stu-id="84f58-111">Here are the descriptions of the properties specific to each operation.</span></span>

## <a name="copytoadls"></a><span data-ttu-id="84f58-112">CopyToADLS</span><span class="sxs-lookup"><span data-stu-id="84f58-112">CopyToADLS</span></span>

* <span data-ttu-id="84f58-113">**LocalDirectory:** Specifica la directory di origine che contiene i file da caricare.</span><span class="sxs-lookup"><span data-stu-id="84f58-113">**LocalDirectory:** Specifies the source directory which contains files to upload.</span></span>
* <span data-ttu-id="84f58-114">**FileNamePattern:** specifica un filtro di nome file per i file di origine.</span><span class="sxs-lookup"><span data-stu-id="84f58-114">**FileNamePattern:** Specifies a file name filter for source files.</span></span> <span data-ttu-id="84f58-115">Verranno caricati solo i file il cui nome corrisponde al modello specificato.</span><span class="sxs-lookup"><span data-stu-id="84f58-115">Only files whose name matches the specified pattern will be uploaded.</span></span> <span data-ttu-id="84f58-116">Sono supportati i caratteri jolly `*` e `?`.</span><span class="sxs-lookup"><span data-stu-id="84f58-116">Wildcards `*` and `?` are supported.</span></span>
* <span data-ttu-id="84f58-117">**SearchRecursively:** specifica se cercare in modo ricorsivo i file da caricare all'interno della directory di origine.</span><span class="sxs-lookup"><span data-stu-id="84f58-117">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to upload.</span></span>
* <span data-ttu-id="84f58-118">**AzureDataLakeDirectory:** specifica la directory di destinazione di ADLS in cui caricare i file.</span><span class="sxs-lookup"><span data-stu-id="84f58-118">**AzureDataLakeDirectory:** Specifies the ADLS destination directory to upload files to.</span></span>
* <span data-ttu-id="84f58-119">**Fileexpire:** Specifica una data e un'ora di scadenza per i file caricati in ADLS o lasciare vuota questa proprietà per indicare che i file non scadono mai.</span><span class="sxs-lookup"><span data-stu-id="84f58-119">**FileExpiry:** Specifies an expiration date and time for the files uploaded to ADLS, or leave this property blank to indicate that the files never expire.</span></span>

## <a name="copyfromadls"></a><span data-ttu-id="84f58-120">CopyFromADLS</span><span class="sxs-lookup"><span data-stu-id="84f58-120">CopyFromADLS</span></span>

* <span data-ttu-id="84f58-121">**AzureDataLakeDirectory:** specifica la directory di origine di ADLS che contiene i file da scaricare.</span><span class="sxs-lookup"><span data-stu-id="84f58-121">**AzureDataLakeDirectory:** Specifies the ADLS source directory which contains the files to download.</span></span>
* <span data-ttu-id="84f58-122">**SearchRecursively:** specifica se cercare in modo ricorsivo i file da scaricare all'interno della directory di origine.</span><span class="sxs-lookup"><span data-stu-id="84f58-122">**SearchRecursively:** Specifies whether to search recursively within the source directory for files to download.</span></span>
* <span data-ttu-id="84f58-123">**LocalDirectory:** specifica la directory di destinazione in cui archiviare i file scaricati.</span><span class="sxs-lookup"><span data-stu-id="84f58-123">**LocalDirectory:** Specifies the destination directory to store downloaded files.</span></span>
