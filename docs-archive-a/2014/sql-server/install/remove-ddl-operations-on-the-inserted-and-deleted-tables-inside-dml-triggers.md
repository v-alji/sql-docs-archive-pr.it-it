---
title: Rimuovere le operazioni DDL sulle tabelle inserite ed eliminate all'interno di trigger DML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- data definition language [SQL Server]
- DDL statements [SQL Server]
- DML triggers, removing DDL operations
ms.assetid: e49ba7d5-787f-4052-b985-b699195d982b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 61f7ab78b5ab6251b7f27401d36423ec27141c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720904"
---
# <a name="remove-ddl-operations-on-the-inserted-and-deleted-tables-inside-dml-triggers"></a><span data-ttu-id="25095-102">Rimuovere le istruzioni DDL eseguite su tabelle inserite ed eliminate all'interno di trigger DML</span><span class="sxs-lookup"><span data-stu-id="25095-102">Remove DDL operations on the inserted and deleted tables inside DML triggers</span></span>
  <span data-ttu-id="25095-103">Non è possibile eseguire istruzioni DDL (Data Definition Language), ad esempio CREATE INDEX, su tabelle inserite ed eliminate all'interno di trigger DML.</span><span class="sxs-lookup"><span data-stu-id="25095-103">Data definition language (DDL) statements, such as CREATE INDEX, cannot be performed on the inserted and deleted tables inside DML triggers.</span></span> <span data-ttu-id="25095-104">Alcune istruzioni DDL sulle tabelle inserite ed eliminate sono consentite nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25095-104">Some DDL statements on the inserted and deleted tables are permitted in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="25095-105">Per ulteriori informazioni, vedere "Utilizzo delle tabelle inserted e deleted" nella documentazione online di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25095-105">For more information, see "Using the inserted and deleted Tables" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="25095-106">Componente</span><span class="sxs-lookup"><span data-stu-id="25095-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="25095-107">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="25095-107">Corrective Action</span></span>  
 <span data-ttu-id="25095-108">Rimuovere le istruzioni DLL eseguite nelle tabelle inserite ed eliminate all'interno di trigger DML.</span><span class="sxs-lookup"><span data-stu-id="25095-108">Remove any DDL operations that are performed on the inserted and deleted tables inside DML triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25095-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25095-109">See Also</span></span>  
 <span data-ttu-id="25095-110">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="25095-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="25095-111">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="25095-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
