---
title: MSSQLSERVER_125 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "125"
helpviewer_keywords:
- 125 (Database Engine error)
ms.assetid: 0f58338d-2ea0-48b8-8a20-c438b0940433
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 59c732d80ccfafc8f242bb1c42fe60e3dea81f19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628751"
---
# <a name="mssqlserver_125"></a><span data-ttu-id="d0eb2-102">MSSQLSERVER_125</span><span class="sxs-lookup"><span data-stu-id="d0eb2-102">MSSQLSERVER_125</span></span>
    
## <a name="details"></a><span data-ttu-id="d0eb2-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="d0eb2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0eb2-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="d0eb2-104">Product Name</span></span>|<span data-ttu-id="d0eb2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0eb2-105">SQL Server</span></span>|  
|<span data-ttu-id="d0eb2-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="d0eb2-106">Event ID</span></span>|<span data-ttu-id="d0eb2-107">125</span><span class="sxs-lookup"><span data-stu-id="d0eb2-107">125</span></span>|  
|<span data-ttu-id="d0eb2-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="d0eb2-108">Event Source</span></span>|<span data-ttu-id="d0eb2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d0eb2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d0eb2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="d0eb2-110">Component</span></span>|<span data-ttu-id="d0eb2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d0eb2-111">SQLEngine</span></span>|  
|<span data-ttu-id="d0eb2-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="d0eb2-112">Symbolic Name</span></span>||  
|<span data-ttu-id="d0eb2-113">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="d0eb2-113">Message Text</span></span>|<span data-ttu-id="d0eb2-114">Per le espressioni Case sono consentiti solo %d livelli di nidificazione.</span><span class="sxs-lookup"><span data-stu-id="d0eb2-114">Case expressions may only be nested to level %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d0eb2-115">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="d0eb2-115">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="d0eb2-116">consente solo 10 livelli di nidificazione nelle espressioni CASE.</span><span class="sxs-lookup"><span data-stu-id="d0eb2-116">allows for only 10 levels of nesting in CASE expressions.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0eb2-117">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="d0eb2-117">User Action</span></span>  
 <span data-ttu-id="d0eb2-118">Ridurre il livello di istruzioni CASE a un massimo di 10.</span><span class="sxs-lookup"><span data-stu-id="d0eb2-118">Reduce the level of CASE statements to 10 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0eb2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0eb2-119">See Also</span></span>  
 [<span data-ttu-id="d0eb2-120">CASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d0eb2-120">CASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/case-transact-sql)  
  
  
