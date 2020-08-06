---
title: MSSQLSERVER_1461 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1461 (Database Engine error)
ms.assetid: fce10907-4753-441b-b624-f28e00ed7520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6667728b2cc134632ddc538b662d73533ee4d6ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636161"
---
# <a name="mssqlserver_1461"></a><span data-ttu-id="f1559-102">MSSQLSERVER_1461</span><span class="sxs-lookup"><span data-stu-id="f1559-102">MSSQLSERVER_1461</span></span>
    
## <a name="details"></a><span data-ttu-id="f1559-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f1559-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1559-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="f1559-104">Product Name</span></span>|<span data-ttu-id="f1559-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1559-105">SQL Server</span></span>|  
|<span data-ttu-id="f1559-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="f1559-106">Event ID</span></span>|<span data-ttu-id="f1559-107">1461</span><span class="sxs-lookup"><span data-stu-id="f1559-107">1461</span></span>|  
|<span data-ttu-id="f1559-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="f1559-108">Event Source</span></span>|<span data-ttu-id="f1559-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f1559-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f1559-110">Componente</span><span class="sxs-lookup"><span data-stu-id="f1559-110">Component</span></span>|<span data-ttu-id="f1559-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f1559-111">SQLEngine</span></span>|  
|<span data-ttu-id="f1559-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="f1559-112">Symbolic Name</span></span>|<span data-ttu-id="f1559-113">DBM_SAFETY_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="f1559-113">DBM_SAFETY_MISMATCH</span></span>|  
|<span data-ttu-id="f1559-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="f1559-114">Message Text</span></span>|<span data-ttu-id="f1559-115">Rilevati livelli di protezione del mirroring del database diversi tra i server per il database "%.\*ls".</span><span class="sxs-lookup"><span data-stu-id="f1559-115">Different database mirroring safety levels among servers were detected for database "%.\*ls".</span></span> <span data-ttu-id="f1559-116">Verrà utilizzato il livello di protezione FULL.</span><span class="sxs-lookup"><span data-stu-id="f1559-116">The FULL safety level will be used.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f1559-117">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="f1559-117">Explanation</span></span>  
 <span data-ttu-id="f1559-118">Le connessioni per il mirroring sono state interrotte quando il livello di protezione delle transazioni è stato modificato a causa dell'inconsistenza delle impostazioni di protezione delle transazioni nei database principale e mirror.</span><span class="sxs-lookup"><span data-stu-id="f1559-118">Mirroring connections were broken when the transaction safety level was modified because the transaction safety settings were inconsistent on the principal and mirror databases.</span></span> <span data-ttu-id="f1559-119">Verrà utilizzata l'impostazione predefinita del livello di protezione FULL delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="f1559-119">The default safety setting of full-transaction safety will be used.</span></span> <span data-ttu-id="f1559-120">La sessione verrà eseguita in modalità a protezione elevata.</span><span class="sxs-lookup"><span data-stu-id="f1559-120">The session will run in high-safety mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f1559-121">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="f1559-121">User Action</span></span>  
 <span data-ttu-id="f1559-122">Per disattivare la protezione delle transazioni, eseguire nuovamente l'istruzione ALTER DATABASE *nome_database* SET PARTNER SAFETY OFF nel database principale.</span><span class="sxs-lookup"><span data-stu-id="f1559-122">To set transaction safety off, rerun the ALTER DATABASE *database_name* SET PARTNER SAFETY OFF statement on the principal database.</span></span>  
  
  
