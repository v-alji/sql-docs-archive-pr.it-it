---
title: MSSQLSERVER_5237 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5237 (Database Engine error)
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 224317e290ce15aaed979129733b6273b3b663df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636097"
---
# <a name="mssqlserver_5237"></a><span data-ttu-id="a12e8-102">MSSQLSERVER_5237</span><span class="sxs-lookup"><span data-stu-id="a12e8-102">MSSQLSERVER_5237</span></span>
    
## <a name="details"></a><span data-ttu-id="a12e8-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="a12e8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a12e8-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="a12e8-104">Product Name</span></span>|<span data-ttu-id="a12e8-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a12e8-105">SQL Server</span></span>|  
|<span data-ttu-id="a12e8-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="a12e8-106">Event ID</span></span>|<span data-ttu-id="a12e8-107">5237</span><span class="sxs-lookup"><span data-stu-id="a12e8-107">5237</span></span>|  
|<span data-ttu-id="a12e8-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="a12e8-108">Event Source</span></span>|<span data-ttu-id="a12e8-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a12e8-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a12e8-110">Componente</span><span class="sxs-lookup"><span data-stu-id="a12e8-110">Component</span></span>|<span data-ttu-id="a12e8-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a12e8-111">SQLEngine</span></span>|  
|<span data-ttu-id="a12e8-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="a12e8-112">Symbolic Name</span></span>|<span data-ttu-id="a12e8-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span><span class="sxs-lookup"><span data-stu-id="a12e8-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span></span>|  
|<span data-ttu-id="a12e8-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="a12e8-114">Message Text</span></span>|<span data-ttu-id="a12e8-115">Controllo DBCC per il set di righe non riuscito per l'oggetto 'NAME' (ID di oggetto O_ID) a causa di un errore interno della query.</span><span class="sxs-lookup"><span data-stu-id="a12e8-115">DBCC cross-rowset check failed for object 'NAME' (object ID O_ID) due to an internal query error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a12e8-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="a12e8-116">Explanation</span></span>  
 <span data-ttu-id="a12e8-117">Si è verificato un errore interno poiché DBCC non è in grado di eseguire la query per controllare viste indicizzate.</span><span class="sxs-lookup"><span data-stu-id="a12e8-117">An internal error resulted in DBCC not being able to execute the query to check indexed views.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a12e8-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="a12e8-118">User Action</span></span>  
 <span data-ttu-id="a12e8-119">Eseguire di nuovo il comando DBCC.</span><span class="sxs-lookup"><span data-stu-id="a12e8-119">Rerun the DBCC command.</span></span>  
  
  
