---
title: MSSQLSERVER_948 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "948"
helpviewer_keywords:
- 948 (Database Engine error)
ms.assetid: 95c4ad45-a518-4165-a5c4-6e6b932b0570
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8461069a3fceb7bdca318b82a522f7f51af83d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627742"
---
# <a name="mssqlserver_948"></a><span data-ttu-id="5b266-102">MSSQLSERVER_948</span><span class="sxs-lookup"><span data-stu-id="5b266-102">MSSQLSERVER_948</span></span>
    
## <a name="details"></a><span data-ttu-id="5b266-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5b266-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b266-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="5b266-104">Product Name</span></span>|<span data-ttu-id="5b266-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b266-105">SQL Server</span></span>|  
|<span data-ttu-id="5b266-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="5b266-106">Event ID</span></span>|<span data-ttu-id="5b266-107">948</span><span class="sxs-lookup"><span data-stu-id="5b266-107">948</span></span>|  
|<span data-ttu-id="5b266-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="5b266-108">Event Source</span></span>|<span data-ttu-id="5b266-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5b266-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5b266-110">Componente</span><span class="sxs-lookup"><span data-stu-id="5b266-110">Component</span></span>|<span data-ttu-id="5b266-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5b266-111">SQLEngine</span></span>|  
|<span data-ttu-id="5b266-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="5b266-112">Symbolic Name</span></span>|<span data-ttu-id="5b266-113">ND</span><span class="sxs-lookup"><span data-stu-id="5b266-113">NA</span></span>|  
|<span data-ttu-id="5b266-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="5b266-114">Message Text</span></span>|<span data-ttu-id="5b266-115">Impossibile aprire il database '%.\*ls' perché la versione è %d.</span><span class="sxs-lookup"><span data-stu-id="5b266-115">The database '%.\*ls' cannot be opened because it is version %d.</span></span> <span data-ttu-id="5b266-116">Il server supporta la versione %d e precedenti.</span><span class="sxs-lookup"><span data-stu-id="5b266-116">This server supports version %d and earlier.</span></span> <span data-ttu-id="5b266-117">Il downgrade non è supportato.</span><span class="sxs-lookup"><span data-stu-id="5b266-117">A downgrade path is not supported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5b266-118">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5b266-118">Explanation</span></span>  
 <span data-ttu-id="5b266-119">Alcune caratteristiche di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] influiscono sulla struttura dei file di database.</span><span class="sxs-lookup"><span data-stu-id="5b266-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="5b266-120">Quando si collega un database a un'altra istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], è possibile che il formato di file non sia compatibile con una versione diversa di [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b266-120">When you attach a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="5b266-121">Ad esempio, questo errore può verificarsi quando si utilizza il formato di archiviazione vardecimal in una versione successiva di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e quindi si tenta di collegare i file del database in una versione precedente a [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="5b266-121">For example, this error can be caused by using the vardecimal storage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to attach the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5b266-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="5b266-122">User Action</span></span>  
 <span data-ttu-id="5b266-123">Verificare quale versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] è in esecuzione nel server di origine.</span><span class="sxs-lookup"><span data-stu-id="5b266-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="5b266-124">In fare [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] clic con il pulsante destro del mouse sul server e quindi scegliere **Proprietà** o digitare `SELECT @@VERSION` in una finestra query.</span><span class="sxs-lookup"><span data-stu-id="5b266-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="5b266-125">Aprire il database utilizzando la versione originale di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b266-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5b266-126">Verificare quali caratteristiche sono attivate nel database originale nell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b266-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5b266-127">Modificare queste impostazioni in modo che venga utilizzata la versione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in cui il database verrà collegato.</span><span class="sxs-lookup"><span data-stu-id="5b266-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be attached.</span></span>  
  
  
