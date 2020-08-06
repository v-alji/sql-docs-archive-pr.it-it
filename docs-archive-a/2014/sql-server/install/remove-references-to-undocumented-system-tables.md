---
title: Rimuovere i riferimenti alle tabelle di sistema non documentate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system tables [SQL Server]
- system tables [SQL Server]
ms.assetid: 010b1236-2219-4bf4-a6db-e3fc3abfa37a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 45c38038ee3d3214e4303c0ddbe0110be926c37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720849"
---
# <a name="remove-references-to-undocumented-system-tables"></a><span data-ttu-id="5ab47-102">Rimuovere i riferimenti alle tabelle di sistema non documentate</span><span class="sxs-lookup"><span data-stu-id="5ab47-102">Remove references to undocumented system tables</span></span>
  <span data-ttu-id="5ab47-103">Molte tabelle di sistema non documentate nelle versioni precedenti sono state modificate o non esistono più. L'utilizzo di tali tabelle potrebbe pertanto provocare errori dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5ab47-103">Many system tables that were undocumented in prior releases have changed or no longer exist; therefore, using these tables may cause errors after upgrading.</span></span> <span data-ttu-id="5ab47-104">Poiché Preparazione aggiornamento cerca i riferimenti ai nomi delle tabella di sistema, segnalerà anche i riferimenti a tutte le tabelle utente che hanno nomi uguali a quelli delle tabelle di sistema.</span><span class="sxs-lookup"><span data-stu-id="5ab47-104">Because Upgrade Advisor looks for references to system table names, it will report references to any user tables that have the same names as system tables.</span></span>  
  
## <a name="component"></a><span data-ttu-id="5ab47-105">Componente</span><span class="sxs-lookup"><span data-stu-id="5ab47-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="5ab47-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5ab47-106">Description</span></span>  
 <span data-ttu-id="5ab47-107">Le seguenti tabelle di sistema non documentate sono state rimosse:</span><span class="sxs-lookup"><span data-stu-id="5ab47-107">The following undocumented system tables are removed:</span></span>  
  
-   <span data-ttu-id="5ab47-108">**spt_datatype_info**</span><span class="sxs-lookup"><span data-stu-id="5ab47-108">**spt_datatype_info**</span></span>  
  
-   <span data-ttu-id="5ab47-109">**spt_datatype_info_ext**</span><span class="sxs-lookup"><span data-stu-id="5ab47-109">**spt_datatype_info_ext**</span></span>  
  
-   <span data-ttu-id="5ab47-110">**spt_provider_types**</span><span class="sxs-lookup"><span data-stu-id="5ab47-110">**spt_provider_types**</span></span>  
  
-   <span data-ttu-id="5ab47-111">**spt_server_info**</span><span class="sxs-lookup"><span data-stu-id="5ab47-111">**spt_server_info**</span></span>  
  
-   <span data-ttu-id="5ab47-112">**spt_values**</span><span class="sxs-lookup"><span data-stu-id="5ab47-112">**spt_values**</span></span>  
  
-   <span data-ttu-id="5ab47-113">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="5ab47-113">**sysfulltextnotify**</span></span>  
  
-   <span data-ttu-id="5ab47-114">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="5ab47-114">**syslocks**</span></span>  
  
-   <span data-ttu-id="5ab47-115">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="5ab47-115">**sysproperties**</span></span>  
  
-   <span data-ttu-id="5ab47-116">**sysprotects_aux**</span><span class="sxs-lookup"><span data-stu-id="5ab47-116">**sysprotects_aux**</span></span>  
  
-   <span data-ttu-id="5ab47-117">**sysprotects_view**</span><span class="sxs-lookup"><span data-stu-id="5ab47-117">**sysprotects_view**</span></span>  
  
-   <span data-ttu-id="5ab47-118">**SYSREMOTE_CATALOGS**</span><span class="sxs-lookup"><span data-stu-id="5ab47-118">**SYSREMOTE_CATALOGS**</span></span>  
  
-   <span data-ttu-id="5ab47-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="5ab47-119">**SYSREMOTE_COLUMN_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="5ab47-120">**SYSREMOTE_COLUMNS**</span><span class="sxs-lookup"><span data-stu-id="5ab47-120">**SYSREMOTE_COLUMNS**</span></span>  
  
-   <span data-ttu-id="5ab47-121">**SYSREMOTE_FOREIGN_KEYS**</span><span class="sxs-lookup"><span data-stu-id="5ab47-121">**SYSREMOTE_FOREIGN_KEYS**</span></span>  
  
-   <span data-ttu-id="5ab47-122">**SYSREMOTE_INDEXES**</span><span class="sxs-lookup"><span data-stu-id="5ab47-122">**SYSREMOTE_INDEXES**</span></span>  
  
-   <span data-ttu-id="5ab47-123">**SYSREMOTE_PRIMARY_KEYS**</span><span class="sxs-lookup"><span data-stu-id="5ab47-123">**SYSREMOTE_PRIMARY_KEYS**</span></span>  
  
-   <span data-ttu-id="5ab47-124">**SYSREMOTE_PROVIDER_TYPES**</span><span class="sxs-lookup"><span data-stu-id="5ab47-124">**SYSREMOTE_PROVIDER_TYPES**</span></span>  
  
-   <span data-ttu-id="5ab47-125">**SYSREMOTE_SCHEMATA**</span><span class="sxs-lookup"><span data-stu-id="5ab47-125">**SYSREMOTE_SCHEMATA**</span></span>  
  
-   <span data-ttu-id="5ab47-126">**SYSREMOTE_STATISTICS**</span><span class="sxs-lookup"><span data-stu-id="5ab47-126">**SYSREMOTE_STATISTICS**</span></span>  
  
-   <span data-ttu-id="5ab47-127">**SYSREMOTE_TABLE_PRIVILEGES**</span><span class="sxs-lookup"><span data-stu-id="5ab47-127">**SYSREMOTE_TABLE_PRIVILEGES**</span></span>  
  
-   <span data-ttu-id="5ab47-128">**SYSREMOTE_TABLES**</span><span class="sxs-lookup"><span data-stu-id="5ab47-128">**SYSREMOTE_TABLES**</span></span>  
  
-   <span data-ttu-id="5ab47-129">**SYSREMOTE_VIEWS**</span><span class="sxs-lookup"><span data-stu-id="5ab47-129">**SYSREMOTE_VIEWS**</span></span>  
  
-   <span data-ttu-id="5ab47-130">**syssegments**</span><span class="sxs-lookup"><span data-stu-id="5ab47-130">**syssegments**</span></span>  
  
-   <span data-ttu-id="5ab47-131">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="5ab47-131">**sysxlogins**</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="5ab47-132">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="5ab47-132">Corrective Action</span></span>  
 <span data-ttu-id="5ab47-133">Modificare le applicazioni in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5ab47-133">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="5ab47-134">Anziché</span><span class="sxs-lookup"><span data-stu-id="5ab47-134">Instead of</span></span>|<span data-ttu-id="5ab47-135">Uso</span><span class="sxs-lookup"><span data-stu-id="5ab47-135">Use</span></span>|  
|----------------|---------|  
|<span data-ttu-id="5ab47-136">**sysfulltextnotify**</span><span class="sxs-lookup"><span data-stu-id="5ab47-136">**sysfulltextnotify**</span></span>|<span data-ttu-id="5ab47-137">Proprietà **TableFulltextPendingChanges** della funzione OBJECTPROPERTYEX.</span><span class="sxs-lookup"><span data-stu-id="5ab47-137">**TableFulltextPendingChanges** property of the OBJECTPROPERTYEX function.</span></span>|  
|<span data-ttu-id="5ab47-138">**syslocks**</span><span class="sxs-lookup"><span data-stu-id="5ab47-138">**syslocks**</span></span>|<span data-ttu-id="5ab47-139">**sys. dm_tran_locks** vista a gestione dinamica o sp_lock o la vista di compatibilità **sys.sysLockInfo** .</span><span class="sxs-lookup"><span data-stu-id="5ab47-139">**sys.dm_tran_locks** dynamic management view, or sp_lock, or the **sys.syslockinfo** compatibility view.</span></span>|  
|<span data-ttu-id="5ab47-140">**sysproperties**</span><span class="sxs-lookup"><span data-stu-id="5ab47-140">**sysproperties**</span></span>|<span data-ttu-id="5ab47-141">**sys. extended_properties** vista del catalogo o funzione **fn_listextendedproperty**</span><span class="sxs-lookup"><span data-stu-id="5ab47-141">**sys.extended_properties** catalog view or the **fn_listextendedproperty** function</span></span>|  
|<span data-ttu-id="5ab47-142">**sysxlogins**</span><span class="sxs-lookup"><span data-stu-id="5ab47-142">**sysxlogins**</span></span>|<span data-ttu-id="5ab47-143">**sys. server_principals** vista del catalogo o vista di compatibilità **syslogins** .</span><span class="sxs-lookup"><span data-stu-id="5ab47-143">**sys.server_principals** catalog view or **syslogins** compatibility view.</span></span>|  
|<span data-ttu-id="5ab47-144">tutte le tabelle **spt_**</span><span class="sxs-lookup"><span data-stu-id="5ab47-144">all **spt_** tables</span></span>|<span data-ttu-id="5ab47-145">Nessuna sostituzione disponibile</span><span class="sxs-lookup"><span data-stu-id="5ab47-145">No replacement available</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ab47-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5ab47-146">See Also</span></span>  
 <span data-ttu-id="5ab47-147">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="5ab47-147">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="5ab47-148">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="5ab47-148">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
