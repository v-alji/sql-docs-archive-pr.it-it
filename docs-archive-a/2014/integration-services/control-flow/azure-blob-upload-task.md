---
title: Attività di caricamento BLOB di Azure | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobuptask.f1
- sql11.dts.designer.afpblobuptask.f1
ms.assetid: 6ea068b0-4cd8-45b5-b89d-09b8f25040c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ca15c5a77a2694293981121f4e5927be8ec0e1c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713392"
---
# <a name="azure-blob-upload-task"></a><span data-ttu-id="0b66d-102">Attività di caricamento BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="0b66d-102">Azure Blob Upload Task</span></span>
  <span data-ttu-id="0b66d-103">L'attività di caricamento BLOB di Azure consente a un pacchetto di SSIS di caricare file in un archivio BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="0b66d-103">The Azure Blob Upload Task enables an SSIS package to upload files to an Azure blob storage.</span></span>   
<span data-ttu-id="0b66d-104">Per aggiungere un' **attività di caricamento BLOB di Azure**, trascinare l'attività in Progettazione SSIS e fare doppio clic oppure clic con il pulsante destro del mouse e quindi scegliere **Modifica** per visualizzare la finestra di dialogo seguente relativa all' **editor dell'attività di caricamento BLOB di Azure** .</span><span class="sxs-lookup"><span data-stu-id="0b66d-104">To add an **Azure Blob Upload Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Upload Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="0b66d-105">La tabella seguente fornisce le descrizioni dei campi della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0b66d-105">The following table provides descriptions for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b66d-106">**Campo**</span><span class="sxs-lookup"><span data-stu-id="0b66d-106">**Field**</span></span>|<span data-ttu-id="0b66d-107">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0b66d-107">**Description**</span></span>|  
|<span data-ttu-id="0b66d-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="0b66d-108">AzureStorageConnection</span></span>|<span data-ttu-id="0b66d-109">Consente di specificare un'istanza esistente di Gestione connessioni dell'archiviazione di Azure o di creare una nuova istanza che fa riferimento a un account di archiviazione di Azure che indica la posizione in cui sono ospitati i file BLOB.</span><span class="sxs-lookup"><span data-stu-id="0b66d-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="0b66d-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="0b66d-110">BlobContainer</span></span>|<span data-ttu-id="0b66d-111">Specifica il nome del contenitore BLOB che conterrà i file caricati come BLOB.</span><span class="sxs-lookup"><span data-stu-id="0b66d-111">Specifies the name of the blob container that will hold the uploaded files as blobs.</span></span>|  
|<span data-ttu-id="0b66d-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="0b66d-112">BlobDirectory</span></span>|<span data-ttu-id="0b66d-113">Specifica la directory BLOB in cui verrà archiviato il file caricato come BLOB in blocchi.</span><span class="sxs-lookup"><span data-stu-id="0b66d-113">Specifies the blob directory where the uploaded file will be stored as a block blob.</span></span> <span data-ttu-id="0b66d-114">La directory BLOB è una struttura gerarchica virtuale.</span><span class="sxs-lookup"><span data-stu-id="0b66d-114">The blob directory is a virtual hierarchical structure.</span></span> <span data-ttu-id="0b66d-115">Se il BLOB esiste già, verrà sostituito.</span><span class="sxs-lookup"><span data-stu-id="0b66d-115">If the blob already exists, it will be replaced.</span></span>|  
|<span data-ttu-id="0b66d-116">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="0b66d-116">LocalDirectory</span></span>|<span data-ttu-id="0b66d-117">Specifica il nome della directory locale che contiene i file da caricare.</span><span class="sxs-lookup"><span data-stu-id="0b66d-117">Specify the local directory that contains the files to be uploaded.</span></span>|  
|<span data-ttu-id="0b66d-118">FileName</span><span class="sxs-lookup"><span data-stu-id="0b66d-118">FileName</span></span>|<span data-ttu-id="0b66d-119">Specifica un filtro per i nomi per la selezione di file con il modello di nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="0b66d-119">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="0b66d-120">ad esempio</span><span class="sxs-lookup"><span data-stu-id="0b66d-120">E.g.</span></span> <span data-ttu-id="0b66d-121">MySheet\*.xls\* include file quali MySheet001.xls e MySheetABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="0b66d-121">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="0b66d-122">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="0b66d-122">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="0b66d-123">Specifica un filtro basato su un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="0b66d-123">Specifies a time range filter.</span></span> <span data-ttu-id="0b66d-124">Saranno inclusi i file modificati dopo **TimeRangeFrom** e prima di **TimeRangeTo** .</span><span class="sxs-lookup"><span data-stu-id="0b66d-124">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
