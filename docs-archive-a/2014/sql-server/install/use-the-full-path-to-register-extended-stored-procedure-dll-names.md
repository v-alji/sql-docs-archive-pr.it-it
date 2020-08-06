---
title: Usare il percorso completo per registrare i nomi delle DLL di stored procedure estese | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- registering DLL names
- extended stored procedures [SQL Server], registering
- DLL names [SQL Server]
- full path DLL name registration [SQL Server]
ms.assetid: f648d57c-af32-4c71-9882-47b6766f3c2b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 5ec4ef3fc2e0f2c4834ffa7479a00562ae15d07f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87715943"
---
# <a name="use-the-full-path-to-register-extended-stored-procedure-dll-names"></a><span data-ttu-id="0817e-102">Utilizzare il percorso completo per registrare i nomi delle DLL delle stored procedure estese</span><span class="sxs-lookup"><span data-stu-id="0817e-102">Use the full path to register extended stored procedure DLL names</span></span>
  <span data-ttu-id="0817e-103">Le stored procedure estese registrate precedentemente senza il percorso completo per il nome DLL possono non funzionare dopo l'aggiornamento a [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0817e-103">Extended stored procedures that were previously registered without the full path for the DLL name may not work in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
## <a name="component"></a><span data-ttu-id="0817e-104">Componente</span><span class="sxs-lookup"><span data-stu-id="0817e-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="0817e-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0817e-105">Description</span></span>  
 <span data-ttu-id="0817e-106">Le stored procedure estese registrate precedentemente senza il percorso completo per il nome DLL possono non funzionare dopo l'aggiornamento,</span><span class="sxs-lookup"><span data-stu-id="0817e-106">Extended stored procedures that were previously registered without the full path for the DLL name may not work after you upgrade.</span></span> <span data-ttu-id="0817e-107">poiché la vecchia directory BINN non viene aggiunta al nuovo percorso durante il processo di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0817e-107">This is because the old BINN directory is not added to the new path during the upgrade process.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0817e-108">può non essere in grado di trovare le stored procedure estese.</span><span class="sxs-lookup"><span data-stu-id="0817e-108">may not be able to locate the extended stored procedures.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="0817e-109">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="0817e-109">Corrective Action</span></span>  
 <span data-ttu-id="0817e-110">Prima di eseguire l'aggiornamento, attenersi alla procedura seguente per ogni stored procedure estesa non registrata utilizzando un percorso completo:</span><span class="sxs-lookup"><span data-stu-id="0817e-110">Before you upgrade, follow these steps for each extended stored procedure that was not registered with a full path name:</span></span>  
  
1.  <span data-ttu-id="0817e-111">Per eliminare la stored procedure estesa eseguire sp_dropextendedproc.</span><span class="sxs-lookup"><span data-stu-id="0817e-111">Run sp_dropextendedproc to remove the extended stored procedure.</span></span>  
  
2.  <span data-ttu-id="0817e-112">Per registrare la stored procedure estesa con il percorso completo eseguire sp_addextendedproc.</span><span class="sxs-lookup"><span data-stu-id="0817e-112">Run sp_addextendedproc to register the extended stored procedure with the full path name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0817e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0817e-113">See Also</span></span>  
 <span data-ttu-id="0817e-114">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="0817e-114">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="0817e-115">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="0817e-115">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
