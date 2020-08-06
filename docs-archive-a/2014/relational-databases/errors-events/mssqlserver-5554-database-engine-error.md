---
title: MSSQLSERVER_5554 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5554 (Database Engine error)
ms.assetid: 7134bbe5-d240-4a98-85ce-b13cc8ae9b0e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5095a50f257abafb6ebde97bb32c57bc71fc4e09
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629425"
---
# <a name="mssqlserver_5554"></a><span data-ttu-id="b00fe-102">MSSQLSERVER_5554</span><span class="sxs-lookup"><span data-stu-id="b00fe-102">MSSQLSERVER_5554</span></span>
    
## <a name="details"></a><span data-ttu-id="b00fe-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="b00fe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b00fe-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="b00fe-104">Product Name</span></span>|<span data-ttu-id="b00fe-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b00fe-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b00fe-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="b00fe-106">Event ID</span></span>|<span data-ttu-id="b00fe-107">5554</span><span class="sxs-lookup"><span data-stu-id="b00fe-107">5554</span></span>|  
|<span data-ttu-id="b00fe-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="b00fe-108">Event Source</span></span>|<span data-ttu-id="b00fe-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b00fe-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b00fe-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b00fe-110">Component</span></span>|<span data-ttu-id="b00fe-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b00fe-111">SQLEngine</span></span>|  
|<span data-ttu-id="b00fe-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="b00fe-112">Symbolic Name</span></span>|<span data-ttu-id="b00fe-113">FS_MINIVER_OVERFLOW</span><span class="sxs-lookup"><span data-stu-id="b00fe-113">FS_MINIVER_OVERFLOW</span></span>|  
|<span data-ttu-id="b00fe-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="b00fe-114">Message Text</span></span>|<span data-ttu-id="b00fe-115">È stato raggiunto il limite massimo di versioni totali per un singolo supportato dal file system.</span><span class="sxs-lookup"><span data-stu-id="b00fe-115">The total number of versions for a single file has reached the maximum limit set by the file system.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b00fe-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="b00fe-116">Explanation</span></span>  
 <span data-ttu-id="b00fe-117">In scenari MARS (Multiple Active Result Set) o con presenza di trigger, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa la miniversione specificata dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b00fe-117">In multiple active result sets (MARS) or trigger scenarios, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] uses the miniversion specified by the operating system.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b00fe-118">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="b00fe-118">User Action</span></span>  
 <span data-ttu-id="b00fe-119">Tentare di evitare aggiornamenti ripetuti ai dati nella stessa transazione.</span><span class="sxs-lookup"><span data-stu-id="b00fe-119">Try to avoid repeated updates to the data in the same transaction.</span></span>  
  
  
