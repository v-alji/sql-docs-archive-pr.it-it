---
title: MSSQLSERVER_2518 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2518 (Database Engine error)
ms.assetid: 54a13abc-4c33-43f0-b55d-e2e74a1381c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5f5517458c1014d7830c4813b95e1120bef452e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626793"
---
# <a name="mssqlserver_2518"></a><span data-ttu-id="8743b-102">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="8743b-102">MSSQLSERVER_2518</span></span>
    
## <a name="details"></a><span data-ttu-id="8743b-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="8743b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8743b-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="8743b-104">Product Name</span></span>|<span data-ttu-id="8743b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8743b-105">SQL Server</span></span>|  
|<span data-ttu-id="8743b-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="8743b-106">Event ID</span></span>|<span data-ttu-id="8743b-107">2518</span><span class="sxs-lookup"><span data-stu-id="8743b-107">2518</span></span>|  
|<span data-ttu-id="8743b-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="8743b-108">Event Source</span></span>|<span data-ttu-id="8743b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8743b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8743b-110">Componente</span><span class="sxs-lookup"><span data-stu-id="8743b-110">Component</span></span>|<span data-ttu-id="8743b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8743b-111">SQLEngine</span></span>|  
|<span data-ttu-id="8743b-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="8743b-112">Symbolic Name</span></span>|<span data-ttu-id="8743b-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span><span class="sxs-lookup"><span data-stu-id="8743b-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span></span>|  
|<span data-ttu-id="8743b-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="8743b-114">Message Text</span></span>|<span data-ttu-id="8743b-115">ID oggetto O_ID (oggetto "O_NAME"): impossibile verificare colonne calcolate e tipi definiti dall'utente per questo oggetto perché Common Language Runtime (CLR) è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="8743b-115">Object ID O_ID (object "O_NAME"): Computed columns and user-defined types cannot be checked for this object because the common language runtime (CLR) is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8743b-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8743b-116">Explanation</span></span>  
 <span data-ttu-id="8743b-117">Questo messaggio informativo indica che Query Processor non è riuscito a fornire a DBCC un oggetto interno per consentire la restituzione delle colonne calcolate e dei tipi CLR (Common Language Runtime) definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="8743b-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for computed columns and common language runtime (CLR) user-defined types to be evaluated.</span></span> <span data-ttu-id="8743b-118">Il problema si verifica perché CLR è incluso in una delle colonne, ma non è attivato.</span><span class="sxs-lookup"><span data-stu-id="8743b-118">This problem occurred because one of the columns involved the CLR, but the CLR is not enabled.</span></span> <span data-ttu-id="8743b-119">L'oggetto interno è incluso in tutte le colonne.</span><span class="sxs-lookup"><span data-stu-id="8743b-119">The internal object covers all columns.</span></span> <span data-ttu-id="8743b-120">Pertanto, l'impossibilità di restituire una singola colonna impedisce la creazione dell'oggetto interno.</span><span class="sxs-lookup"><span data-stu-id="8743b-120">Therefore, the inability to evaluate a single column prevents creating the internal object.</span></span> <span data-ttu-id="8743b-121">Ciò significa che non verrà controllata la correttezza delle colonne calcolate o che quest'ultime non verranno utilizzate durante il controllo DBCC della consistenza tra indici e tabelle di base.</span><span class="sxs-lookup"><span data-stu-id="8743b-121">This means that computed columns will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8743b-122">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="8743b-122">User Action</span></span>  
 <span data-ttu-id="8743b-123">Attivare CLR ed eseguire nuovamente l'istruzione DBCC.</span><span class="sxs-lookup"><span data-stu-id="8743b-123">Enable CLR and rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8743b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8743b-124">See Also</span></span>  
 [<span data-ttu-id="8743b-125">Abilitazione dell'integrazione con CLR</span><span class="sxs-lookup"><span data-stu-id="8743b-125">Enabling CLR Integration</span></span>](../clr-integration/clr-integration-enabling.md)  
  
  
