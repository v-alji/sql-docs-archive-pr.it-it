---
title: Rimuovere i due punti seguenti parola chiave riservata | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- reserved keywords
ms.assetid: 4f23f7e4-7b4d-4e19-86c9-7527bb8b107d
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fc6882439338509a3c716129d9504f209ab1e555
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726492"
---
# <a name="remove-colon-following-reserved-keyword"></a><span data-ttu-id="c0f31-102">Rimuovere i due punti (:) dopo le parole chiave riservate</span><span class="sxs-lookup"><span data-stu-id="c0f31-102">Remove colon following reserved keyword</span></span>
  <span data-ttu-id="c0f31-103">È stato rilevato uno script che contiene una parola chiave riservata seguita da due punti (:).</span><span class="sxs-lookup"><span data-stu-id="c0f31-103">The Upgrade Advisor detected a script that contains a colon (:) following a reserved keyword.</span></span> <span data-ttu-id="c0f31-104">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tale sintassi viene ignorata e le istruzioni vengono eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="c0f31-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this syntax is ignored and the statements execute successfully.</span></span> <span data-ttu-id="c0f31-105">Ora tale sintassi impedisce l'esecuzione dell'istruzione in modalità di compatibilità del database 100 o successiva.</span><span class="sxs-lookup"><span data-stu-id="c0f31-105">Now, this syntax causes the statement to fail when the database compatibility mode is set to 100 or later.</span></span>  
  
 <span data-ttu-id="c0f31-106">La modalità di compatibilità dei database utente non cambia.</span><span class="sxs-lookup"><span data-stu-id="c0f31-106">User databases maintain their compatibility mode.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c0f31-107">Componente</span><span class="sxs-lookup"><span data-stu-id="c0f31-107">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="c0f31-108">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="c0f31-108">Corrective Action</span></span>  
 <span data-ttu-id="c0f31-109">Prima di impostare la modalità di compatibilità del database su 100 o successiva, modificare gli script rimuovendo i due punti (:) dopo le parole chiave riservate.</span><span class="sxs-lookup"><span data-stu-id="c0f31-109">Before you change the database compatibility mode to 100 or later, modify your scripts by removing colons that follow reserved keywords.</span></span> <span data-ttu-id="c0f31-110">Per ulteriori informazioni, vedere "sp_dbcmptlevel" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c0f31-110">For more information, see "sp_dbcmptlevel" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f31-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0f31-111">See Also</span></span>  
 <span data-ttu-id="c0f31-112">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c0f31-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c0f31-113">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="c0f31-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
