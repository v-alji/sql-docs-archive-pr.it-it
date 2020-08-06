---
title: Modificare le istruzioni UPDATETEXT che leggono e scrivono in oggetti binari di grandi dimensioni (BLOB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- UPDATETEXT statement
- text [SQL Server], UPDATETEXT statements
ms.assetid: b85da6a7-42f6-4707-a25e-3ded8958b94f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 061e7bad0bae5a74d103406265ad79195f79f7db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628176"
---
# <a name="modify-updatetext-statements-that-read-and-write-to-binary-large-objects-blobs"></a><span data-ttu-id="40f2e-102">Modificare le istruzioni UPDATETEXT che eseguono operazioni di lettura e scrittura in oggetti BLOB (Binary Large Object)</span><span class="sxs-lookup"><span data-stu-id="40f2e-102">Modify UPDATETEXT statements that read and write to binary large objects (BLOBs)</span></span>
  <span data-ttu-id="40f2e-103">Sono state rilevate istruzioni UPDATETEXT che eseguono operazioni di lettura e scrittura negli stessi BLOB (Binary Large Object) utilizzando lo stesso puntatore di testo.</span><span class="sxs-lookup"><span data-stu-id="40f2e-103">Upgrade Advisor detected UPDATETEXT statements that read and write to the same binary large objects (BLOB) by using the same text pointer.</span></span> <span data-ttu-id="40f2e-104">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] questo tipo di utilizzo dei puntatori di testo non è supportato.</span><span class="sxs-lookup"><span data-stu-id="40f2e-104">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] does not support the use of text pointers in this manner.</span></span>  
  
## <a name="component"></a><span data-ttu-id="40f2e-105">Componente</span><span class="sxs-lookup"><span data-stu-id="40f2e-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="40f2e-106">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="40f2e-106">Corrective Action</span></span>  
 <span data-ttu-id="40f2e-107">Copiare gli oggetti BLOB in una tabella temporanea o in una variabile di tabella e quindi riassegnare il valore alla colonna originale.</span><span class="sxs-lookup"><span data-stu-id="40f2e-107">Copy the BLOB to a temporary table or to a table variable, and then assign the value back to the original column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f2e-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40f2e-108">See Also</span></span>  
 <span data-ttu-id="40f2e-109">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="40f2e-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="40f2e-110">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="40f2e-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
