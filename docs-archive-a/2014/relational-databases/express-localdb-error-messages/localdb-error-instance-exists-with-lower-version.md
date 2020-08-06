---
title: LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: a7c5ce08-8841-49a3-b252-116807ba469a
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa6db2af138bb2aeefb1a922e55db56c4ea821f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726968"
---
# <a name="localdb_error_instance_exists_with_lower_version"></a><span data-ttu-id="b96b6-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="b96b6-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>
    
## <a name="details"></a><span data-ttu-id="b96b6-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b96b6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b96b6-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b96b6-104">Product Name</span></span>|<span data-ttu-id="b96b6-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b96b6-105">SQL Server</span></span>|  
|<span data-ttu-id="b96b6-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b96b6-106">Event ID</span></span>|<span data-ttu-id="b96b6-107">258</span><span class="sxs-lookup"><span data-stu-id="b96b6-107">258</span></span>|  
|<span data-ttu-id="b96b6-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b96b6-108">Event Source</span></span>|<span data-ttu-id="b96b6-109">Runtime database locale di SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="b96b6-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="b96b6-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b96b6-110">Component</span></span>|<span data-ttu-id="b96b6-111">API di Runtime database locale</span><span class="sxs-lookup"><span data-stu-id="b96b6-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="b96b6-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b96b6-112">Message Text</span></span>|<span data-ttu-id="b96b6-113">Impossibile creare l'istanza del database locale con la versione specificata.</span><span class="sxs-lookup"><span data-stu-id="b96b6-113">Unable to create the Local Database instance with specified version.</span></span> <span data-ttu-id="b96b6-114">Istanza con lo stesso nome già esistente, ma con una versione inferiore rispetto alla versione specificata.</span><span class="sxs-lookup"><span data-stu-id="b96b6-114">An instance with the same name already exists, but it has lower version than the specified version.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b96b6-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b96b6-115">Explanation</span></span>  
 <span data-ttu-id="b96b6-116">Istanza specificata già esistente ma con relativa versione meno recente di quella richiesta.</span><span class="sxs-lookup"><span data-stu-id="b96b6-116">The specified instance already exists but its version is lower than requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b96b6-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b96b6-117">User Action</span></span>  
 <span data-ttu-id="b96b6-118">Eliminare l'istanza esistente e ritentare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="b96b6-118">Delete the existing instance and retry the operation.</span></span>  
  
  
