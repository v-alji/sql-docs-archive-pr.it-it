---
title: Specificare la parola chiave WITH quando si usano gli hint di tabella in modalità di compatibilità 90 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- table hints [SQL Server]
ms.assetid: 7636cc85-5155-44db-baf6-df807761adb8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ecd13475395cef4257d97eb7480f32420932e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87628153"
---
# <a name="specify-the-with-keyword-when-using-table-hints-in-90-compatibility-mode"></a><span data-ttu-id="74480-102">Specificare la parola chiave WITH quando si utilizzano hint di tabella in modalità di compatibilità 90</span><span class="sxs-lookup"><span data-stu-id="74480-102">Specify the WITH keyword when using table hints in 90 compatibility mode</span></span>
  <span data-ttu-id="74480-103">Gli hint di tabella sono supportati nella clausola FROM di una query solo se vengono specificati utilizzando la parola chiave WITH, con alcune eccezioni.</span><span class="sxs-lookup"><span data-stu-id="74480-103">With some exceptions, table hints are supported in the FROM clause of a query only when the hints are specified by using the WITH keyword.</span></span> <span data-ttu-id="74480-104">Per ulteriori informazioni, vedere gli argomenti "FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])" e "Hint di tabella ([!INCLUDE[tsql](../../includes/tsql-md.md)])" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74480-104">For more information, see the topics "FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])" and "Table Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="74480-105">Componente</span><span class="sxs-lookup"><span data-stu-id="74480-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="74480-106">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="74480-106">Corrective Action</span></span>  
 <span data-ttu-id="74480-107">Modificare le query che includono hint di tabella nella clausola FROM includendo la parola chiave WITH prima degli hint di tabella.</span><span class="sxs-lookup"><span data-stu-id="74480-107">Modify queries that include table hints in the FROM clause by including the WITH keyword before the table hints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74480-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74480-108">See Also</span></span>  
 <span data-ttu-id="74480-109">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="74480-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="74480-110">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="74480-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
