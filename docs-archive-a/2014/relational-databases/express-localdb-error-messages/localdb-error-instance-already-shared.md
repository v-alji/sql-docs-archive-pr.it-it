---
title: LOCALDB_ERROR_INSTANCE_ALREADY_SHARED | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: 35b4d6fa-ebb9-49d3-aaab-d4e37b6f3760
author: stevestein
ms.author: sstein
ms.openlocfilehash: 300f9753b721bc3e0a821a6b77929a9bec09312b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624186"
---
# <a name="localdb_error_instance_already_shared"></a><span data-ttu-id="8ca64-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span><span class="sxs-lookup"><span data-stu-id="8ca64-102">LOCALDB_ERROR_INSTANCE_ALREADY_SHARED</span></span>
    
## <a name="details"></a><span data-ttu-id="8ca64-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8ca64-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ca64-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8ca64-104">Product Name</span></span>|<span data-ttu-id="8ca64-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ca64-105">SQL Server</span></span>|  
|<span data-ttu-id="8ca64-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8ca64-106">Event ID</span></span>|<span data-ttu-id="8ca64-107">284</span><span class="sxs-lookup"><span data-stu-id="8ca64-107">284</span></span>|  
|<span data-ttu-id="8ca64-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8ca64-108">Event Source</span></span>|<span data-ttu-id="8ca64-109">Runtime database locale di SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="8ca64-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="8ca64-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8ca64-110">Component</span></span>|<span data-ttu-id="8ca64-111">API di Runtime database locale</span><span class="sxs-lookup"><span data-stu-id="8ca64-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="8ca64-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8ca64-112">Message Text</span></span>|<span data-ttu-id="8ca64-113">L'istanza del database locale specificata è già condivisa.</span><span class="sxs-lookup"><span data-stu-id="8ca64-113">The specified Local Database Instance is already shared.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8ca64-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8ca64-114">Explanation</span></span>  
 <span data-ttu-id="8ca64-115">L'istanza del database locale specificata è già condivisa con un nome condivisione diverso.</span><span class="sxs-lookup"><span data-stu-id="8ca64-115">The specified Local Database Instance is already shared with a different shared name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8ca64-116">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8ca64-116">User Action</span></span>  
 <span data-ttu-id="8ca64-117">Annullare la condivisione dell'istanza condivisa prima di condividerla di nuovo con un nome condiviso diverso.</span><span class="sxs-lookup"><span data-stu-id="8ca64-117">Unshare the shared instance before sharing it again with a different shared name.</span></span>  
  
  
