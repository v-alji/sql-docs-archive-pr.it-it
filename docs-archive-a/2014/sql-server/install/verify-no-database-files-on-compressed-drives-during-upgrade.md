---
title: Verificare che durante il processo di aggiornamento non siano presenti file di database su unità compresse | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- compressed drives [SQL Server]
ms.assetid: 63be6853-c54a-42b2-ae1a-db2175f1d28e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9c04f7890ba8d8efe64afaf11b922af156c5de46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624523"
---
# <a name="verify-that-no-database-files-are-on-compressed-drives-during-the-upgrade-process"></a><span data-ttu-id="fe027-102">Verificare che durante il processo di aggiornamento non siano presenti file di database su unità compresse</span><span class="sxs-lookup"><span data-stu-id="fe027-102">Verify that no database files are on compressed drives during the upgrade process</span></span>
  <span data-ttu-id="fe027-103">Sono presenti file di database in un'unità compressa.</span><span class="sxs-lookup"><span data-stu-id="fe027-103">Upgrade Advisor detected database files on a compressed drive.</span></span> <span data-ttu-id="fe027-104">Con [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] non è possibile creare o aggiornare database in unità compresse.</span><span class="sxs-lookup"><span data-stu-id="fe027-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot create or upgrade databases on compressed drives.</span></span>  
  
## <a name="component"></a><span data-ttu-id="fe027-105">Componente</span><span class="sxs-lookup"><span data-stu-id="fe027-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="fe027-106">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="fe027-106">Corrective Action</span></span>  
 <span data-ttu-id="fe027-107">Durante l'installazione di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] selezionare un'unità non compressa per i database di sistema e verificare che questi vengano aggiornati su unità non compresse.</span><span class="sxs-lookup"><span data-stu-id="fe027-107">When you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], select an uncompressed drive for system databases and verify that databases to be upgraded are not on compressed drives.</span></span> <span data-ttu-id="fe027-108">Tenere tuttavia presente che, dopo l'aggiornamento del database, è possibile copiare database e filegroup secondari di sola lettura in un file system compresso NTFS.</span><span class="sxs-lookup"><span data-stu-id="fe027-108">However, note that after the database has been upgraded, you can put read-only databases and read-only secondary filegroups on an NTFS compressed file system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe027-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe027-109">See Also</span></span>  
 <span data-ttu-id="fe027-110">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="fe027-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="fe027-111">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="fe027-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
