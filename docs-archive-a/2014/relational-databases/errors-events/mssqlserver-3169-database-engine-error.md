---
title: MSSQLSERVER_3169 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "3169"
helpviewer_keywords:
- 3169 (Database Engine error)
ms.assetid: 7d4dbed6-bb94-4908-bc03-2040a9cf63bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b13d9c1c17eddb34648bc4a536e2fccf371b99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628728"
---
# <a name="mssqlserver_3169"></a><span data-ttu-id="37aa4-102">MSSQLSERVER_3169</span><span class="sxs-lookup"><span data-stu-id="37aa4-102">MSSQLSERVER_3169</span></span>
    
## <a name="details"></a><span data-ttu-id="37aa4-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="37aa4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="37aa4-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="37aa4-104">Product Name</span></span>|<span data-ttu-id="37aa4-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="37aa4-105">SQL Server</span></span>|  
|<span data-ttu-id="37aa4-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="37aa4-106">Event ID</span></span>|<span data-ttu-id="37aa4-107">3169</span><span class="sxs-lookup"><span data-stu-id="37aa4-107">3169</span></span>|  
|<span data-ttu-id="37aa4-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="37aa4-108">Event Source</span></span>|<span data-ttu-id="37aa4-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="37aa4-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="37aa4-110">Componente</span><span class="sxs-lookup"><span data-stu-id="37aa4-110">Component</span></span>|<span data-ttu-id="37aa4-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="37aa4-111">SQLEngine</span></span>|  
|<span data-ttu-id="37aa4-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="37aa4-112">Symbolic Name</span></span>|<span data-ttu-id="37aa4-113">ND</span><span class="sxs-lookup"><span data-stu-id="37aa4-113">NA</span></span>|  
|<span data-ttu-id="37aa4-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="37aa4-114">Message Text</span></span>|<span data-ttu-id="37aa4-115">Il backup del database è stato eseguito in un server che esegue la versione %ls.</span><span class="sxs-lookup"><span data-stu-id="37aa4-115">The database was backed up on a server running version %ls.</span></span> <span data-ttu-id="37aa4-116">Tale versione è incompatibile con il server, che esegue la versione %ls.</span><span class="sxs-lookup"><span data-stu-id="37aa4-116">That version is incompatible with this server, which is running version %ls.</span></span> <span data-ttu-id="37aa4-117">Ripristinare il database in un server che supporta il backup oppure utilizzare un backup compatibile con questo server.</span><span class="sxs-lookup"><span data-stu-id="37aa4-117">Either restore the database on a server that supports the backup, or use a backup that is compatible with this server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="37aa4-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="37aa4-118">Explanation</span></span>  
 <span data-ttu-id="37aa4-119">Alcune caratteristiche di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] influiscono sulla struttura dei file di database.</span><span class="sxs-lookup"><span data-stu-id="37aa4-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="37aa4-120">Quando si ripristina un database in un'altra istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile che il formato di file non sia compatibile con una versione diversa di [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37aa4-120">When you restore a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="37aa4-121">Ad esempio, questo errore può verificarsi quando si usa il formato vardecimalstorage in una versione più recente di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e successivamente si tenta di ripristinare i file di database in una versione precedente a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="37aa4-121">For example, this error can be caused by using the vardecimalstorage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to restore the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="37aa4-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="37aa4-122">User Action</span></span>  
 <span data-ttu-id="37aa4-123">Verificare quale versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione nel server di origine.</span><span class="sxs-lookup"><span data-stu-id="37aa4-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="37aa4-124">In fare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] clic con il pulsante destro del mouse sul server e quindi scegliere **Proprietà** o digitare `SELECT @@VERSION` in una finestra query.</span><span class="sxs-lookup"><span data-stu-id="37aa4-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="37aa4-125">Aprire il database utilizzando la versione originale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37aa4-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="37aa4-126">Verificare quali caratteristiche sono attivate nel database originale nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37aa4-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="37aa4-127">Modificare tali impostazioni in modo che funzionino con la versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui il database verrà ripristinato.</span><span class="sxs-lookup"><span data-stu-id="37aa4-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be restored.</span></span>  
  
  
