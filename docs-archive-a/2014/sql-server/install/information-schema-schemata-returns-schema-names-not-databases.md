---
title: INFORMATION_SCHEMA. SCHEMI restituisce i nomi di schema in un database, non i database in un'istanza | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- INFORMATION_SCHEMA.SCHEMATA view
ms.assetid: 4337b643-910d-47d7-bea8-f4052066b9a2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cb2a34a59bf6257c188210fc7bf2aeacb70f6b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637039"
---
# <a name="information_schemaschemata-returns-schema-names-in-a-database-not-databases-in-an-instance"></a><span data-ttu-id="b8ed9-102">INFORMATION_SCHEMA.SCHEMATA restituisce i nomi degli schemi di un database, non i database di un'istanza</span><span class="sxs-lookup"><span data-stu-id="b8ed9-102">INFORMATION_SCHEMA.SCHEMATA returns schema names in a database, not databases in an instance</span></span>
  <span data-ttu-id="b8ed9-103">Sono state rilevate istruzioni che fanno riferimento alla vista INFORMATION_SCHEMA.SCHEMATA.</span><span class="sxs-lookup"><span data-stu-id="b8ed9-103">Upgrade Advisor detected statements that reference the INFORMATION_SCHEMA.SCHEMATA view.</span></span> <span data-ttu-id="b8ed9-104">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la vista restituisce tutti i database inclusi in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="b8ed9-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b8ed9-105">mentre in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] e versioni successive restituisce tutti gli schemi di un database.</span><span class="sxs-lookup"><span data-stu-id="b8ed9-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, the view returns all schemas in a database.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b8ed9-106">Componente</span><span class="sxs-lookup"><span data-stu-id="b8ed9-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="b8ed9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8ed9-107">Description</span></span>  
 <span data-ttu-id="b8ed9-108">Nelle versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la vista INFORMATION_SCHEMA.SCHEMATA restituisce tutti i database inclusi in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)],</span><span class="sxs-lookup"><span data-stu-id="b8ed9-108">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the INFORMATION_SCHEMA.SCHEMATA view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b8ed9-109">mentre ora restituisce tutti gli schemi di un database, in modo conforme allo standard SQL.</span><span class="sxs-lookup"><span data-stu-id="b8ed9-109">Now, the view returns all schemas in a database, which complies with the SQL Standard.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="b8ed9-110">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="b8ed9-110">Corrective Action</span></span>  
 <span data-ttu-id="b8ed9-111">Modificare l'applicazione in modo che faccia riferimento alla vista del catalogo **sys. databases** per restituire tutti i database in un'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b8ed9-111">Modify your application to reference the **sys.databases** catalog view to return all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ed9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8ed9-112">See Also</span></span>  
 <span data-ttu-id="b8ed9-113">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b8ed9-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b8ed9-114">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="b8ed9-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
