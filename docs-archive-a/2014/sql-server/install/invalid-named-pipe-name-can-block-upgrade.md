---
title: Il nome del named pipe non valido può bloccare l'aggiornamento | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- invalid named pipes [SQL Server]
- named pipes
ms.assetid: 58c2199c-4fdf-4d43-ac1c-842703344b75
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bacfd3d097d7cccb0a5780328c4db95dc5afc733
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724391"
---
# <a name="invalid-named-pipe-name-can-block-upgrade"></a><span data-ttu-id="3666a-102">Un nome di named pipe non valido può bloccare l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="3666a-102">Invalid named pipe name can block upgrade</span></span>
  <span data-ttu-id="3666a-103">L'aggiornamento non riesce se il protocollo Named Pipes non è configurato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3666a-103">Upgrade fails if the named pipes protocol is incorrectly configured.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3666a-104">Componente</span><span class="sxs-lookup"><span data-stu-id="3666a-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="3666a-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3666a-105">Description</span></span>  
 <span data-ttu-id="3666a-106">Durante l'aggiornamento, il programma di installazione avvia l' [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] istanza di con supporto Shared Memory, un named pipe che accetta solo connessioni locali.</span><span class="sxs-lookup"><span data-stu-id="3666a-106">During upgrade, the Setup program starts the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][!INCLUDE[ssDE](../../includes/ssde-md.md)] instance with shared memory support, a named pipe that only accepts local connections.</span></span> <span data-ttu-id="3666a-107">Se il nome della pipe specificato nel server non è vuoto, deve iniziare con la stringa " \\ \\ .\pipe \\ " per essere valido.</span><span class="sxs-lookup"><span data-stu-id="3666a-107">If the pipe name specified on the server is not blank, it must begin with the string "\\\\.\pipe\\" to be valid.</span></span> <span data-ttu-id="3666a-108">Se il nome non è valido, il [!INCLUDE[ssDE](../../includes/ssde-md.md)] non verrà avviato e l'installazione non verrà completata.</span><span class="sxs-lookup"><span data-stu-id="3666a-108">If the pipe name is not valid, the [!INCLUDE[ssDE](../../includes/ssde-md.md)] will not start, and setup will fail.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="3666a-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="3666a-109">Corrective Action</span></span>  
 <span data-ttu-id="3666a-110">Utilizzare l' \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilità di rete\*\* per specificare un nome di pipe valido, quindi eseguire il programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="3666a-110">Use the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Network Utility** to supply a valid pipe name, and then run Setup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3666a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3666a-111">See Also</span></span>  
 <span data-ttu-id="3666a-112">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3666a-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3666a-113">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="3666a-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
