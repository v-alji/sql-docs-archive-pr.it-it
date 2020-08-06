---
title: Oggetti supportati dalla procedura guidata di generazione script
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 071eb2cb-f073-41ca-9f4d-11d3b8803495
author: rothja
ms.author: jroth
ms.openlocfilehash: 5ddc1da0d2f87fc12dfbe034a683802f54b7d34f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636672"
---
# <a name="objects-supported-by-the-generate-scripts-wizard"></a><span data-ttu-id="2358a-102">Oggetti supportati dalla procedura guidata di generazione script</span><span class="sxs-lookup"><span data-stu-id="2358a-102">Objects Supported by the Generate Scripts Wizard</span></span>
  <span data-ttu-id="2358a-103">La procedura guidata Genera e pubblica script supporta un subset degli oggetti supportati da [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2358a-103">The Generate and Publish Scripts wizard supports a subset of the objects supported by the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
## <a name="supported-objects"></a><span data-ttu-id="2358a-104">Oggetti supportati</span><span class="sxs-lookup"><span data-stu-id="2358a-104">Supported Objects</span></span>  
 <span data-ttu-id="2358a-105">Nella tabella seguente vengono elencati gli oggetti pubblicabili supportati dalla procedura guidata Genera e pubblica script.</span><span class="sxs-lookup"><span data-stu-id="2358a-105">The following table lists the objects that can be published supported by the Generate and Publish Scripts Wizard.</span></span>  
  
||||||  
|-|-|-|-|-|  
|<span data-ttu-id="2358a-106">Ruolo applicazione</span><span class="sxs-lookup"><span data-stu-id="2358a-106">Application role</span></span>|<span data-ttu-id="2358a-107">Ruolo del database</span><span class="sxs-lookup"><span data-stu-id="2358a-107">Database role</span></span>|<span data-ttu-id="2358a-108">SCHEMA</span><span class="sxs-lookup"><span data-stu-id="2358a-108">Schema</span></span>|<span data-ttu-id="2358a-109">Aggregazione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="2358a-109">User-defined aggregate</span></span>|<span data-ttu-id="2358a-110">Visualizzazione<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2358a-110">View<sup>1</sup></span></span>|  
|<span data-ttu-id="2358a-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="2358a-111">Assembly</span></span>|<span data-ttu-id="2358a-112">Vincolo DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2358a-112">DEFAULT constraint</span></span>|<span data-ttu-id="2358a-113">Stored procedure<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2358a-113">Stored procedure<sup>1</sup></span></span>|<span data-ttu-id="2358a-114">Tipo di dati definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="2358a-114">User-defined data type</span></span>|<span data-ttu-id="2358a-115">Raccolta di XML Schema</span><span class="sxs-lookup"><span data-stu-id="2358a-115">XML schema collection</span></span>|  
|<span data-ttu-id="2358a-116">Vincolo CHECK</span><span class="sxs-lookup"><span data-stu-id="2358a-116">CHECK constraint</span></span>|<span data-ttu-id="2358a-117">Catalogo full-text</span><span class="sxs-lookup"><span data-stu-id="2358a-117">Full-text catalog</span></span>|<span data-ttu-id="2358a-118">Sinonimo</span><span class="sxs-lookup"><span data-stu-id="2358a-118">Synonym</span></span>|<span data-ttu-id="2358a-119">Funzione definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="2358a-119">User-defined function</span></span>||  
|<span data-ttu-id="2358a-120">CLR (Common Language Runtime) stored procedure<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="2358a-120">CLR (common language runtime) stored procedure<sup>1</sup></span></span>|<span data-ttu-id="2358a-121">Indice</span><span class="sxs-lookup"><span data-stu-id="2358a-121">Index</span></span>|<span data-ttu-id="2358a-122">Tabella</span><span class="sxs-lookup"><span data-stu-id="2358a-122">Table</span></span>|<span data-ttu-id="2358a-123">Tabella definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="2358a-123">User-defined table</span></span>||  
|<span data-ttu-id="2358a-124">Funzione CLR definita dall'utente</span><span class="sxs-lookup"><span data-stu-id="2358a-124">CLR user-defined function</span></span>|<span data-ttu-id="2358a-125">Regola</span><span class="sxs-lookup"><span data-stu-id="2358a-125">Rule</span></span>|<span data-ttu-id="2358a-126">Utente<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="2358a-126">User<sup>2</sup></span></span>|<span data-ttu-id="2358a-127">Tipo definito dall'utente</span><span class="sxs-lookup"><span data-stu-id="2358a-127">User-defined type</span></span>||  
  
 <span data-ttu-id="2358a-128"><sup>1</sup> pubblicato senza crittografia.</span><span class="sxs-lookup"><span data-stu-id="2358a-128"><sup>1</sup> Published without encryption.</span></span>  
  
 <span data-ttu-id="2358a-129"><sup>2</sup> qualsiasi utente non di sistema esistente nel database viene pubblicato come ruolo.</span><span class="sxs-lookup"><span data-stu-id="2358a-129"><sup>2</sup> Any non-system users that exist in the database are published as Roles.</span></span>  
  
  
