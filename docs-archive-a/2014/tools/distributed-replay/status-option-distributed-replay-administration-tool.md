---
title: Opzione Stato (strumento di amministrazione Riesecuzione distribuita) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: ea89386e-1598-4412-8b37-680d14b2a5b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ce3d07bc357c5f3788fb6f995a43399021b3553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87711360"
---
# <a name="status-option-distributed-replay-administration-tool"></a><span data-ttu-id="5aa8f-102">Opzione status (strumento di amministrazione Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="5aa8f-102">Status Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="5aa8f-103">Lo [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] strumento di amministrazione riesecuzione distribuita, `DReplay.exe` , è uno strumento da riga di comando che è possibile utilizzare per comunicare con il controller di riesecuzione distribuita.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="5aa8f-104">Questo argomento descrive l'opzione della riga di comando **status** e la sintassi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-104">This topic describes the **status** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="5aa8f-105">L'opzione **status** esegue query sul controller e visualizza lo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-105">The **status** option queries the controller and displays the current status.</span></span>

 <span data-ttu-id="5aa8f-106">![Icona di collegamento all'argomento](../../database-engine/media/topic-link.gif "Icona di collegamento a un argomento") Per altre informazioni sulle convenzioni relative alla sintassi dello strumento di amministrazione, vedere [Convenzioni della sintassi Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5aa8f-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="5aa8f-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5aa8f-107">Syntax</span></span>

```

dreplay status [-mcontroller] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="5aa8f-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="5aa8f-108">Parameters</span></span>
 <span data-ttu-id="5aa8f-109">**-m** *controller* specifica il nome computer del controller.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-109">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="5aa8f-110">È possibile utilizzare "`localhost`" o "`.`" per fare riferimento al computer locale.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="5aa8f-111">Se il parametro **-m** non è specificato, viene usato il computer locale.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="5aa8f-112">**-f** *status_interval* specifica la frequenza (in secondi) in cui visualizzare lo stato.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-112">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="5aa8f-113">Se il parametro **-f** non è specificato, l'intervallo predefinito è 30 secondi.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-113">If the **-f** parameter is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="5aa8f-114">Esempi</span><span class="sxs-lookup"><span data-stu-id="5aa8f-114">Examples</span></span>
 <span data-ttu-id="5aa8f-115">Nell'esempio seguente lo stato corrente viene visualizzato ogni 60 secondi.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-115">In the following example, the current status is displayed every 60 seconds.</span></span> <span data-ttu-id="5aa8f-116">Il valore `localhost` indica che il servizio controller viene eseguito nello stesso computer dello strumento di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-116">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay status -m localhost -f 60
```

## <a name="permissions"></a><span data-ttu-id="5aa8f-117">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="5aa8f-117">Permissions</span></span>
 <span data-ttu-id="5aa8f-118">È necessario eseguire lo strumento di amministrazione come utente interattivo, scegliendo tra utente locale e account utente di dominio.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-118">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="5aa8f-119">Per utilizzare un account utente locale, lo strumento di amministrazione e il controller devono essere eseguiti nello stesso computer.</span><span class="sxs-lookup"><span data-stu-id="5aa8f-119">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="5aa8f-120">Per altre informazioni, vedere [Sicurezza di Distributed Replay](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="5aa8f-120">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5aa8f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5aa8f-121">See Also</span></span>
 <span data-ttu-id="5aa8f-122">[SQL Server riesecuzione distribuita](sql-server-distributed-replay.md) [debugger Transact-SQL](../../relational-databases/scripting/transact-sql-debugger.md)</span><span class="sxs-lookup"><span data-stu-id="5aa8f-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [Transact-SQL Debugger](../../relational-databases/scripting/transact-sql-debugger.md)</span></span>


