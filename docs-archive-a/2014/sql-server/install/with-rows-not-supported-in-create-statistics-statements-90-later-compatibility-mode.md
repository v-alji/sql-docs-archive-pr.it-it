---
title: WITH ROWS non è supportata nelle istruzioni CREATE STATISTICs in modalità di compatibilità 90 o successiva | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH ROWS in CREATE STATISTICS statement
ms.assetid: 197b2ecf-a1a3-4a3a-a523-a0ee919c1dde
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d28a05e7cd025e213e2cebdce9d582a9df446fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628089"
---
# <a name="with-rows-is-not-supported-in-create-statistics-statements-in-the-compatibility-mode-of-90-or-later"></a><span data-ttu-id="e4d1b-102">Quando è attiva la modalità di compatibilità 90 o successiva la clausola WITH ROWS non è supportata nelle istruzioni CREATE STATISTICS</span><span class="sxs-lookup"><span data-stu-id="e4d1b-102">WITH ROWS is not supported in CREATE STATISTICS statements in the compatibility mode of 90 or later</span></span>
  <span data-ttu-id="e4d1b-103">Se si esegue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con modalità di compatibilità 90 o successiva, l'utilizzo di WITH ROWS nelle istruzioni CREATE STATISTICS non è supportato.</span><span class="sxs-lookup"><span data-stu-id="e4d1b-103">Specifying WITH ROWS in CREATE STATISTICS statements is not supported when you run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set to the compatibility mode of 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="e4d1b-104">Componente</span><span class="sxs-lookup"><span data-stu-id="e4d1b-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="e4d1b-105">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="e4d1b-105">Corrective Action</span></span>  
 <span data-ttu-id="e4d1b-106">Modificare le istruzioni CREATE STATISTICs incluse con le righe specificando con *numero* di righe di esempio o specificando altre opzioni conformi alla sintassi documentata.</span><span class="sxs-lookup"><span data-stu-id="e4d1b-106">Modify CREATE STATISTICS statements that include WITH ROWS by specifying WITH SAMPLE *number* ROWS, or by specifying other options that comply with the documented syntax.</span></span> <span data-ttu-id="e4d1b-107">Per ulteriori informazioni, vedere l'argomento "CREATE STATISTICS (Transact-SQL) nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e4d1b-107">For more information, see the topic "CREATE STATISTICS (Transact-SQL) in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d1b-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4d1b-108">See Also</span></span>  
 <span data-ttu-id="e4d1b-109">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="e4d1b-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="e4d1b-110">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="e4d1b-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
