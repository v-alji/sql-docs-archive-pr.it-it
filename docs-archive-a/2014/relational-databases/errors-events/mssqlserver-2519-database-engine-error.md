---
title: MSSQLSERVER_2519 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2519 (Database Engine error)
ms.assetid: 8dc6ad98-5db8-4c88-8dea-6d455e63b839
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8577b07586553f4b03714cd31451ac755faf824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624235"
---
# <a name="mssqlserver_2519"></a><span data-ttu-id="3151c-102">MSSQLSERVER_2519</span><span class="sxs-lookup"><span data-stu-id="3151c-102">MSSQLSERVER_2519</span></span>
    
## <a name="details"></a><span data-ttu-id="3151c-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="3151c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3151c-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="3151c-104">Product Name</span></span>|<span data-ttu-id="3151c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="3151c-105">SQL Server</span></span>|  
|<span data-ttu-id="3151c-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="3151c-106">Event ID</span></span>|<span data-ttu-id="3151c-107">2519</span><span class="sxs-lookup"><span data-stu-id="3151c-107">2519</span></span>|  
|<span data-ttu-id="3151c-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="3151c-108">Event Source</span></span>|<span data-ttu-id="3151c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="3151c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="3151c-110">Componente</span><span class="sxs-lookup"><span data-stu-id="3151c-110">Component</span></span>|<span data-ttu-id="3151c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="3151c-111">SQLEngine</span></span>|  
|<span data-ttu-id="3151c-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="3151c-112">Symbolic Name</span></span>|<span data-ttu-id="3151c-113">DBCC_NO_EXPRESSION_EVALUATOR</span><span class="sxs-lookup"><span data-stu-id="3151c-113">DBCC_NO_EXPRESSION_EVALUATOR</span></span>|  
|<span data-ttu-id="3151c-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="3151c-114">Message Text</span></span>|<span data-ttu-id="3151c-115">Impossibile controllare le colonne calcolate e i tipi definiti dall'utente per l'ID di oggetto ID_O (oggetto "NOME_O") perché non è stato possibile inizializzare l'analizzatore di espressioni interno.</span><span class="sxs-lookup"><span data-stu-id="3151c-115">Computed columns and user-defined types cannot be checked for object ID O_ID (object "O_NAME") because the internal expression evaluator could not be initialized.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3151c-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="3151c-116">Explanation</span></span>  
 <span data-ttu-id="3151c-117">Questo messaggio informativo indica che Query Processor non è riuscito a fornire a DBCC un oggetto interno per consentire la restituzione delle colonne calcolate e dei tipi CLR (Common Language Runtime) definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="3151c-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for the evaluation of computed columns and common language runtime (CLR) user-defined types.</span></span> <span data-ttu-id="3151c-118">Ciò significa che non verrà controllata la correttezza delle colonne calcolate e dei tipi CLR definiti dall'utente o che questi non verranno utilizzati durante il controllo DBCC della consistenza tra indici e tabelle di base.</span><span class="sxs-lookup"><span data-stu-id="3151c-118">This means that computed columns and CLR user-defined types will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3151c-119">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="3151c-119">User Action</span></span>  
 <span data-ttu-id="3151c-120">nessuno</span><span class="sxs-lookup"><span data-stu-id="3151c-120">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3151c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3151c-121">See Also</span></span>  
 [<span data-ttu-id="3151c-122">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="3151c-122">MSSQLSERVER_2518</span></span>](mssqlserver-2518-database-engine-error.md)  
  
  
