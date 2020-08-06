---
title: Opzione Annulla (strumento di amministrazione Riesecuzione distribuita) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: fea376de-307a-4b45-b7e2-37df88f3681a
author: stevestein
ms.author: sstein
ms.openlocfilehash: d132fbf5ce541a2bdab82e44dc55e6fc92df536d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629663"
---
# <a name="cancel-option-distributed-replay-administration-tool"></a><span data-ttu-id="fac47-102">Opzione cancel (strumento di amministrazione Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="fac47-102">Cancel Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="fac47-103">Lo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] strumento di amministrazione riesecuzione distribuita, `DReplay.exe` , è uno strumento da riga di comando che è possibile utilizzare per comunicare con il controller di riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="fac47-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="fac47-104">Questo argomento descrive l'opzione della riga di comando **cancel** e la sintassi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="fac47-104">This topic describes the **cancel** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="fac47-105">L'opzione **cancel** annulla l'operazione corrente in esecuzione nel controller.</span><span class="sxs-lookup"><span data-stu-id="fac47-105">The **cancel** option cancels the current operation that is running on the controller.</span></span>

 <span data-ttu-id="fac47-106">![Icona di collegamento all'argomento](../../database-engine/media/topic-link.gif "Icona di collegamento a un argomento") Per altre informazioni sulle convenzioni relative alla sintassi dello strumento di amministrazione, vedere [Convenzioni della sintassi Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="fac47-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="fac47-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fac47-107">Syntax</span></span>

```

dreplay cancel [-mcontroller] [-q] 
```

#### <a name="parameters"></a><span data-ttu-id="fac47-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="fac47-108">Parameters</span></span>
 <span data-ttu-id="fac47-109">**-m** *controller* nome computer del controller.</span><span class="sxs-lookup"><span data-stu-id="fac47-109">**-m** *controller* The computer name of the controller.</span></span> <span data-ttu-id="fac47-110">È possibile utilizzare "`localhost`" o "`.`" per fare riferimento al computer locale.</span><span class="sxs-lookup"><span data-stu-id="fac47-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="fac47-111">Se il parametro **-m** non è specificato, viene usato il computer locale.</span><span class="sxs-lookup"><span data-stu-id="fac47-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="fac47-112">**-q** Modalità non interattiva.</span><span class="sxs-lookup"><span data-stu-id="fac47-112">**-q** Quiet mode.</span></span> <span data-ttu-id="fac47-113">Non viene richiesta alcuna conferma da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fac47-113">Does not prompt for confirmation.</span></span>

 <span data-ttu-id="fac47-114">Il parametro **-q** è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fac47-114">The **-q** parameter is optional.</span></span>

## <a name="examples"></a><span data-ttu-id="fac47-115">Esempi</span><span class="sxs-lookup"><span data-stu-id="fac47-115">Examples</span></span>
 <span data-ttu-id="fac47-116">Nell'esempio seguente viene inviata una richiesta di annullamento in modalità non interattiva.</span><span class="sxs-lookup"><span data-stu-id="fac47-116">In the following example, a cancel request is submitted in quiet mode.</span></span> <span data-ttu-id="fac47-117">Il valore `localhost` indica che il servizio controller viene eseguito nello stesso computer dello strumento di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fac47-117">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay cancel -m localhost -q
```

## <a name="permissions"></a><span data-ttu-id="fac47-118">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="fac47-118">Permissions</span></span>
 <span data-ttu-id="fac47-119">È necessario eseguire lo strumento di amministrazione come utente interattivo, scegliendo tra utente locale e account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="fac47-119">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="fac47-120">Per utilizzare un account utente locale, lo strumento di amministrazione e il controller devono essere eseguiti nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="fac47-120">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="fac47-121">Per altre informazioni, vedere [Sicurezza di Distributed Replay](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="fac47-121">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fac47-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fac47-122">See Also</span></span>
 [<span data-ttu-id="fac47-123">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="fac47-123">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)


