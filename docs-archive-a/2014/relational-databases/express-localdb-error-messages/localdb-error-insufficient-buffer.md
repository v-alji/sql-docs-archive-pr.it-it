---
title: LOCALDB_ERROR_INSUFFICIENT_BUFFER | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: ff67bda8-7e5c-4b06-8d7b-9985b6059a98
author: stevestein
ms.author: sstein
ms.openlocfilehash: 934683cfca1a9a9c0596071824c21a0045e6ebab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637340"
---
# <a name="localdb_error_insufficient_buffer"></a><span data-ttu-id="f68b5-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f68b5-102">LOCALDB_ERROR_INSUFFICIENT_BUFFER</span></span>
    
## <a name="details"></a><span data-ttu-id="f68b5-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f68b5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f68b5-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f68b5-104">Product Name</span></span>|<span data-ttu-id="f68b5-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f68b5-105">SQL Server</span></span>|  
|<span data-ttu-id="f68b5-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f68b5-106">Event ID</span></span>|<span data-ttu-id="f68b5-107">276</span><span class="sxs-lookup"><span data-stu-id="f68b5-107">276</span></span>|  
|<span data-ttu-id="f68b5-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f68b5-108">Event Source</span></span>|<span data-ttu-id="f68b5-109">Runtime database locale di SQL Server 12.0</span><span class="sxs-lookup"><span data-stu-id="f68b5-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="f68b5-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f68b5-110">Component</span></span>|<span data-ttu-id="f68b5-111">API di Runtime database locale</span><span class="sxs-lookup"><span data-stu-id="f68b5-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="f68b5-112">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f68b5-112">Message Text</span></span>|<span data-ttu-id="f68b5-113">Dimensioni del buffer passato al metodo API dell'istanza del database locale non sufficienti.</span><span class="sxs-lookup"><span data-stu-id="f68b5-113">The buffer passed to the Local Database instance API method has insufficient size.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f68b5-114">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f68b5-114">Explanation</span></span>  
 <span data-ttu-id="f68b5-115">Buffer di input troppo corto. Troncamento non necessario.</span><span class="sxs-lookup"><span data-stu-id="f68b5-115">The input buffer is too short, and truncation was not requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f68b5-116">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f68b5-116">User Action</span></span>  
 <span data-ttu-id="f68b5-117">Fornire un buffer con la dimensione specificata.</span><span class="sxs-lookup"><span data-stu-id="f68b5-117">Provide a buffer of the specified size.</span></span>  
  
  
