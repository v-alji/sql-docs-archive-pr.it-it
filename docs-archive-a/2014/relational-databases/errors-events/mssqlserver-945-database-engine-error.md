---
title: MSSQLSERVER_945 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 945 (Database Engine error)
ms.assetid: ee501d13-0bd9-4627-896c-ed5b1bdb88b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51284cdcf48f1bf713a853f9c87457cb5291cc4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87627744"
---
# <a name="mssqlserver_945"></a><span data-ttu-id="16c5c-102">MSSQLSERVER_945</span><span class="sxs-lookup"><span data-stu-id="16c5c-102">MSSQLSERVER_945</span></span>
    
## <a name="details"></a><span data-ttu-id="16c5c-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="16c5c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16c5c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="16c5c-104">Product Name</span></span>|<span data-ttu-id="16c5c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="16c5c-105">SQL Server</span></span>|  
|<span data-ttu-id="16c5c-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="16c5c-106">Event ID</span></span>|<span data-ttu-id="16c5c-107">945</span><span class="sxs-lookup"><span data-stu-id="16c5c-107">945</span></span>|  
|<span data-ttu-id="16c5c-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="16c5c-108">Event Source</span></span>|<span data-ttu-id="16c5c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="16c5c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="16c5c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="16c5c-110">Component</span></span>|<span data-ttu-id="16c5c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="16c5c-111">SQLEngine</span></span>|  
|<span data-ttu-id="16c5c-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="16c5c-112">Symbolic Name</span></span>|<span data-ttu-id="16c5c-113">DB_IS_SHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="16c5c-113">DB_IS_SHUTDOWN</span></span>|  
|<span data-ttu-id="16c5c-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="16c5c-114">Message Text</span></span>|<span data-ttu-id="16c5c-115">Impossibile aprire il database '%.\*ls' a causa di file inaccessibili oppure per memoria o spazio su disco insufficiente.</span><span class="sxs-lookup"><span data-stu-id="16c5c-115">Database '%.\*ls' cannot be opened due to inaccessible files or insufficient memory or disk space.</span></span>  <span data-ttu-id="16c5c-116">Per ulteriori informazioni, vedere il log degli errori di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="16c5c-116">See the SQL Server error log for details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="16c5c-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="16c5c-117">Explanation</span></span>  
 <span data-ttu-id="16c5c-118">Non è stato possibile accedere al database perché i file o altre risorse risultano mancanti.</span><span class="sxs-lookup"><span data-stu-id="16c5c-118">The database could not be accessed because files or other resources are missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16c5c-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="16c5c-119">User Action</span></span>  
 <span data-ttu-id="16c5c-120">Verificare se nel log degli errori sono presenti ulteriori informazioni sull'errore relativo alla memoria, allo spazio su disco o alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="16c5c-120">Check the error log for additional information about memory, disk space, or permission failure.</span></span> <span data-ttu-id="16c5c-121">Verificare il percorso dei file con estensione mdf e ndf del database interessato. Verificare inoltre che l'account utilizzato dal [!INCLUDE[ssDE](../../includes/ssde-md.md)] disponga dell'autorizzazione per accedere a tali file.</span><span class="sxs-lookup"><span data-stu-id="16c5c-121">Confirm the location of the .mdf and .ndf files for the affected database and confirm that the account used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] has permission to access those files.</span></span> <span data-ttu-id="16c5c-122">Dopo aver corretto il problema, riavviare il database utilizzando ALTER DATABASE per impostarlo su ONLINE.</span><span class="sxs-lookup"><span data-stu-id="16c5c-122">After correcting the problem, restart the database by using ALTER DATABASE to set it ONLINE.</span></span>  
  
  
