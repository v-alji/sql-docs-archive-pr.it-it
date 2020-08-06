---
title: Attività di download di BLOB di Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.afpblobdltask.f1
- sql11.dts.designer.afpblobdltask.f1
ms.assetid: 8a63bf44-71be-456d-9a5c-be7c31aff065
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e2f61260b1fceaad3c27a0ce6ab6af28b15582bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87713395"
---
# <a name="azure-blob-download-task"></a><span data-ttu-id="2d611-102">Attività di download di BLOB di Azure</span><span class="sxs-lookup"><span data-stu-id="2d611-102">Azure Blob Download Task</span></span>
  <span data-ttu-id="2d611-103">L'attività di download di BLOB di Azure consente a un pacchetto di SSIS di scaricare file da un archivio BLOB di Azure.</span><span class="sxs-lookup"><span data-stu-id="2d611-103">The Azure Blob Download Task enables an SSIS package to download files from an Azure blob storage.</span></span>   
<span data-ttu-id="2d611-104">Per aggiungere un' **attività di download di BLOB di Azure**, trascinare l'attività in Progettazione SSIS e farvi doppio clic oppure clic con il pulsante destro del mouse, quindi scegliere **Modifica** per visualizzare la finestra di dialogo seguente relativa all' **editor dell'attività di download di BLOB di Azure** .</span><span class="sxs-lookup"><span data-stu-id="2d611-104">To add an **Azure Blob Download Task**, drag-drop it to the SSIS Designer, and double-click or right-click and click **Edit** to see the following **Azure Blob Download Task Editor** dialog box.</span></span>  
  
 <span data-ttu-id="2d611-105">La tabella seguente fornisce una descrizione dei campi della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2d611-105">The following table provides description for the fields in this dialog box.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d611-106">**Campo**</span><span class="sxs-lookup"><span data-stu-id="2d611-106">**Field**</span></span>|<span data-ttu-id="2d611-107">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="2d611-107">**Description**</span></span>|  
|<span data-ttu-id="2d611-108">AzureStorageConnection</span><span class="sxs-lookup"><span data-stu-id="2d611-108">AzureStorageConnection</span></span>|<span data-ttu-id="2d611-109">Consente di specificare un'istanza esistente di Gestione connessioni dell'archiviazione di Azure o di creare una nuova istanza che fa riferimento a un account di archiviazione di Azure che indica la posizione in cui sono ospitati i file BLOB.</span><span class="sxs-lookup"><span data-stu-id="2d611-109">Specify an existing Azure Storage Connection Manager or create a new one that refers to an Azure Storage Account, which points to where the blob files are hosted.</span></span>|  
|<span data-ttu-id="2d611-110">BlobContainer</span><span class="sxs-lookup"><span data-stu-id="2d611-110">BlobContainer</span></span>|<span data-ttu-id="2d611-111">Consente di specificare il nome del contenitore BLOB che include i file BLOB da scaricare.</span><span class="sxs-lookup"><span data-stu-id="2d611-111">Specifies the name of the blob container that contains the blob files to be downloaded.</span></span>|  
|<span data-ttu-id="2d611-112">BlobDirectory</span><span class="sxs-lookup"><span data-stu-id="2d611-112">BlobDirectory</span></span>|<span data-ttu-id="2d611-113">Consente di specificare il nome della directory BLOB che include i file BLOB da scaricare.</span><span class="sxs-lookup"><span data-stu-id="2d611-113">Specifies the blob directory that contains the blob files to be downloaded.</span></span> <span data-ttu-id="2d611-114">La directory BLOB è una struttura gerarchica virtuale.</span><span class="sxs-lookup"><span data-stu-id="2d611-114">The blob directory is a virtual hierarchical structure.</span></span>|  
|<span data-ttu-id="2d611-115">LocalDirectory</span><span class="sxs-lookup"><span data-stu-id="2d611-115">LocalDirectory</span></span>|<span data-ttu-id="2d611-116">Consente di specificare la directory locale in cui verranno archiviati i file BLOB.</span><span class="sxs-lookup"><span data-stu-id="2d611-116">Specifies the local directory where the downloaded blob files will be stored.</span></span>|  
|<span data-ttu-id="2d611-117">FileName</span><span class="sxs-lookup"><span data-stu-id="2d611-117">FileName</span></span>|<span data-ttu-id="2d611-118">Specifica un filtro per i nomi per la selezione di file con il modello di nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="2d611-118">Specifies a name filter to select files with the specified name pattern.</span></span> <span data-ttu-id="2d611-119">ad esempio</span><span class="sxs-lookup"><span data-stu-id="2d611-119">E.g.</span></span> <span data-ttu-id="2d611-120">MySheet\*.xls\* include file quali MySheet001.xls e MySheetABC.xlsx.</span><span class="sxs-lookup"><span data-stu-id="2d611-120">MySheet\*.xls\* includes files such as MySheet001.xls and MySheetABC.xlsx.</span></span>|  
|<span data-ttu-id="2d611-121">TimeRangeFrom/TimeRangeTo</span><span class="sxs-lookup"><span data-stu-id="2d611-121">TimeRangeFrom/TimeRangeTo</span></span>|<span data-ttu-id="2d611-122">Specifica un filtro basato su un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="2d611-122">Specifies a time range filter.</span></span> <span data-ttu-id="2d611-123">Saranno inclusi i file modificati dopo **TimeRangeFrom** e prima di **TimeRangeTo** .</span><span class="sxs-lookup"><span data-stu-id="2d611-123">Files modified after **TimeRangeFrom** and before **TimeRangeTo** will be included.</span></span>|  
  
  
