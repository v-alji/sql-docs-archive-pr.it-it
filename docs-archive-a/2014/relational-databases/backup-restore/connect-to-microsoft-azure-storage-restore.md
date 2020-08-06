---
title: Connettersi ad archiviazione di Azure (ripristino) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restore.connectstorage.f1
ms.assetid: c0b7d7c8-b878-4b7f-8120-d0c6917b583f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dff9730d6592381b1c8e8a1cf7ee45ad7532a440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637924"
---
# <a name="connect-to-azure-storage-restore"></a><span data-ttu-id="36689-102">Connettersi ad Archiviazione di Azure (ripristino)</span><span class="sxs-lookup"><span data-stu-id="36689-102">Connect to Azure Storage (Restore)</span></span>
  <span data-ttu-id="36689-103">La finestra di dialogo consente di specificare la connessione alle informazioni sull'account di archiviazione di Azure per recuperare l'archivio di file nell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="36689-103">The dialog box allows you to specify the connection to Azure storage account information in order to retrieve the files storage in the Azure storage account.</span></span> <span data-ttu-id="36689-104">Dopo avere specificato le informazioni necessarie, fare clic su **Connetti** per stabilire la connessione all'archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="36689-104">After specifying the required information, click **Connect** to establish the connection to Azure storage.</span></span>  
  
## <a name="azure-storage-account"></a><span data-ttu-id="36689-105">Account di archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="36689-105">Azure Storage Account</span></span>  
 <span data-ttu-id="36689-106">**Account di archiviazione**</span><span class="sxs-lookup"><span data-stu-id="36689-106">**Storage account**</span></span>  
 <span data-ttu-id="36689-107">Selezionare, digitare o incollare il nome dell'account di archiviazione di Azure da usare.</span><span class="sxs-lookup"><span data-stu-id="36689-107">Select, type or paste the name of the Azure storage account you want to use.</span></span> <span data-ttu-id="36689-108">Nella casella di riepilogo sono elencati gli account utilizzati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="36689-108">The drop down box lists the accounts previously used.</span></span>  
  
 <span data-ttu-id="36689-109">**Chiave dell'account**</span><span class="sxs-lookup"><span data-stu-id="36689-109">**Account key**</span></span>  
 <span data-ttu-id="36689-110">Specificare la chiave di accesso dell'account di archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="36689-110">Specify the Azure storage account access key.</span></span>  
  
 <span data-ttu-id="36689-111">Casella di controllo**Usa endpoint sicuri (HTTPS)**</span><span class="sxs-lookup"><span data-stu-id="36689-111">**Use secure endpoints (HTTPS)** check box</span></span>  
 <span data-ttu-id="36689-112">Selezionare questa opzione per stabilire una connessione sicura all'archiviazione di Azure (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="36689-112">Select this option to make a secure connection to Azure storage - recommended.</span></span>  
  
 <span data-ttu-id="36689-113">Casella di controllo**Salva chiave account**</span><span class="sxs-lookup"><span data-stu-id="36689-113">**Save account key** check box</span></span>  
 <span data-ttu-id="36689-114">Selezionare questa casella di controllo se si desidera memorizzare in SQL Server la chiave di accesso per l'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="36689-114">Select this check box if you want SQL Server to remember the access key for this storage account.</span></span>  
  
### <a name="sql-credential"></a><span data-ttu-id="36689-115">Credenziali SQL</span><span class="sxs-lookup"><span data-stu-id="36689-115">SQL Credential</span></span>  
 <span data-ttu-id="36689-116">**Selezionare credenziali esistenti**</span><span class="sxs-lookup"><span data-stu-id="36689-116">**Select an existing credential**</span></span>  
 <span data-ttu-id="36689-117">Selezionare le credenziali SQL esistenti corrispondenti alle informazioni sulla chiave account e sull'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="36689-117">Select an existing SQL Credential that matches the storage account and account key information.</span></span>  
  
 <span data-ttu-id="36689-118">**Crea nuove credenziali**</span><span class="sxs-lookup"><span data-stu-id="36689-118">**Create a new Credential**</span></span>  
 <span data-ttu-id="36689-119">Selezionare questa opzione per creare nuove credenziali utilizzando le informazioni sulla chiave account e sull'account di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="36689-119">Select this option to create a new credential using the storage account and account key information.</span></span> <span data-ttu-id="36689-120">Specificare il nome delle nuove credenziali nel campo **Nome credenziali** .</span><span class="sxs-lookup"><span data-stu-id="36689-120">Specify the name of the new credential in the **Credential Name** field.</span></span>  
  
  
