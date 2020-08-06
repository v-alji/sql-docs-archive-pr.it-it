---
title: LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: fa082dca-bf88-46e7-b61e-7ac8835a3493
author: stevestein
ms.author: sstein
ms.openlocfilehash: e71f7b443a1999a5edbb17dc11ee4d578834faf4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629832"
---
# <a name="localdb_error_unknown_language_id"></a><span data-ttu-id="25690-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="25690-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>
    
## <a name="details"></a><span data-ttu-id="25690-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="25690-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25690-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="25690-104">Product Name</span></span>|<span data-ttu-id="25690-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25690-105">SQL Server</span></span>|  
|<span data-ttu-id="25690-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="25690-106">Event ID</span></span>|<span data-ttu-id="25690-107">270</span><span class="sxs-lookup"><span data-stu-id="25690-107">270</span></span>|  
|<span data-ttu-id="25690-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="25690-108">Event Source</span></span>|<span data-ttu-id="25690-109">Runtime database locale di SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="25690-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="25690-110">Componente</span><span class="sxs-lookup"><span data-stu-id="25690-110">Component</span></span>|<span data-ttu-id="25690-111">API di Runtime database locale</span><span class="sxs-lookup"><span data-stu-id="25690-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="25690-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="25690-112">Message Text</span></span>|<span data-ttu-id="25690-113">Errore durante il recupero del messaggio di errore localizzato.</span><span class="sxs-lookup"><span data-stu-id="25690-113">Error getting the localized error message.</span></span> <span data-ttu-id="25690-114">Linguaggio specificato dal parametro 'Language ID' sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="25690-114">The language specified by 'Language ID' parameter is unknown.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25690-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="25690-115">Explanation</span></span>  
 <span data-ttu-id="25690-116">La lingua richiesta per il messaggio di errore di run-time database locale è sconosciuta o non supportata.</span><span class="sxs-lookup"><span data-stu-id="25690-116">The requested language for the Local Database Runtime error message is unknown or not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25690-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="25690-117">User Action</span></span>  
 <span data-ttu-id="25690-118">Provare a richiedere una delle lingue supportate per i messaggi di errore di run-time database locale o una lingua predefinita.</span><span class="sxs-lookup"><span data-stu-id="25690-118">Try requesting one of the supported languages for Local Database Runtime error messages, or a default language.</span></span>  
  
  
