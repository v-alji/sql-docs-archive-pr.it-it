---
title: LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c1595263-6264-4a43-9535-5eb76ece3a57
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0896f3e70e6c65a1fcd0de4169249fb622e6b5f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624180"
---
# <a name="localdb_error_too_many_shared_instances"></a><span data-ttu-id="feaaa-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span><span class="sxs-lookup"><span data-stu-id="feaaa-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span></span>
    
## <a name="details"></a><span data-ttu-id="feaaa-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="feaaa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="feaaa-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="feaaa-104">Product Name</span></span>|<span data-ttu-id="feaaa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="feaaa-105">SQL Server</span></span>|  
|<span data-ttu-id="feaaa-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="feaaa-106">Event ID</span></span>|<span data-ttu-id="feaaa-107">287</span><span class="sxs-lookup"><span data-stu-id="feaaa-107">287</span></span>|  
|<span data-ttu-id="feaaa-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="feaaa-108">Event Source</span></span>|<span data-ttu-id="feaaa-109">Runtime database locale di SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="feaaa-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="feaaa-110">Componente</span><span class="sxs-lookup"><span data-stu-id="feaaa-110">Component</span></span>|<span data-ttu-id="feaaa-111">API di Runtime database locale</span><span class="sxs-lookup"><span data-stu-id="feaaa-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="feaaa-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="feaaa-112">Message Text</span></span>|<span data-ttu-id="feaaa-113">Impossibile generare un nome univoco per l'istanza utente.</span><span class="sxs-lookup"><span data-stu-id="feaaa-113">There are too many shared instance and we cannot generate unique User Instance Name.</span></span> <span data-ttu-id="feaaa-114">Annullare la condivisione di alcune delle istanze condivise esistenti.</span><span class="sxs-lookup"><span data-stu-id="feaaa-114">Unshare some of the existing shared instances.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="feaaa-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="feaaa-115">Explanation</span></span>  
 <span data-ttu-id="feaaa-116">Impossibile generare un nome univoco per l'istanza utente.</span><span class="sxs-lookup"><span data-stu-id="feaaa-116">There are too many shared instance and we cannot generate unique User Instance Name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="feaaa-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="feaaa-117">User Action</span></span>  
 <span data-ttu-id="feaaa-118">Annullare la condivisione di una o più istanze di Runtime database locale condivise e riprovare.</span><span class="sxs-lookup"><span data-stu-id="feaaa-118">Unshare one or more of the shared Local Database Runtime instances and try again.</span></span>  
  
  
