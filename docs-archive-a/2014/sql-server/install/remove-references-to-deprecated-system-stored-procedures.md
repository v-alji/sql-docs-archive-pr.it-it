---
title: Rimuovere i riferimenti alle stored procedure di sistema deprecate | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- undocumented system stored procedures [SQL Server]
- system stored procedures [SQL Server]
ms.assetid: 487d24fc-41d5-495e-843c-0ac974ec472f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 65e7da666beaf84050dd8d60caf4cac5bfc013c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720844"
---
# <a name="remove-references-to-deprecated-system-stored-procedures"></a><span data-ttu-id="f36c7-102">Rimuovere i riferimenti alle stored procedure di sistema deprecate</span><span class="sxs-lookup"><span data-stu-id="f36c7-102">Remove references to deprecated system stored procedures</span></span>
  <span data-ttu-id="f36c7-103">Sono state rilevate istruzioni che fanno riferimento a stored procedure di sistema e stored procedure estese non documentate che non sono più disponibili in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36c7-103">Upgrade Advisor detected statements that reference undocumented system stored procedures and extended stored procedures that are no longer available in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f36c7-104">Le istruzioni che fanno riferimento a tali oggetti non verranno eseguite.</span><span class="sxs-lookup"><span data-stu-id="f36c7-104">Statements that reference these objects will fail.</span></span> <span data-ttu-id="f36c7-105">Evitare di utilizzare oggetti di sistema o API non documentati, perché la funzionalità potrebbe cambiare oppure potrebbero venire rimossi senza comunicazione in una versione futura.</span><span class="sxs-lookup"><span data-stu-id="f36c7-105">Do not use undocumented system objects or APIs as the functionality might change or be removed without notification in a future release.</span></span>  
  
## <a name="component"></a><span data-ttu-id="f36c7-106">Componente</span><span class="sxs-lookup"><span data-stu-id="f36c7-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="f36c7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f36c7-107">Description</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="f36c7-108">Stored procedure di sistema documentate</span><span class="sxs-lookup"><span data-stu-id="f36c7-108">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="f36c7-109">Le seguenti stored procedure di sistema documentate sono state rimosse:</span><span class="sxs-lookup"><span data-stu-id="f36c7-109">The following documented system stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="f36c7-110">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="f36c7-110">sp_addalias</span></span>  
  
-   <span data-ttu-id="f36c7-111">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="f36c7-111">sp_addgroup</span></span>  
  
-   <span data-ttu-id="f36c7-112">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="f36c7-112">sp_changegroup</span></span>  
  
-   <span data-ttu-id="f36c7-113">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="f36c7-113">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="f36c7-114">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="f36c7-114">sp_helpgroup</span></span>  
  
### <a name="undocumented-system-stored-procedures"></a><span data-ttu-id="f36c7-115">Stored procedure di sistema non documentate</span><span class="sxs-lookup"><span data-stu-id="f36c7-115">Undocumented System Stored Procedures</span></span>  
 <span data-ttu-id="f36c7-116">Le seguenti stored procedure di sistema e stored procedure estese non documentate sono state rimosse:</span><span class="sxs-lookup"><span data-stu-id="f36c7-116">The following undocumented system stored procedures and extended stored procedures have been removed:</span></span>  
  
-   <span data-ttu-id="f36c7-117">sp_articlesynctranprocs</span><span class="sxs-lookup"><span data-stu-id="f36c7-117">sp_articlesynctranprocs</span></span>  
  
-   <span data-ttu-id="f36c7-118">sp_diskdefault</span><span class="sxs-lookup"><span data-stu-id="f36c7-118">sp_diskdefault</span></span>  
  
-   <span data-ttu-id="f36c7-119">sp_EventLog</span><span class="sxs-lookup"><span data-stu-id="f36c7-119">sp_EventLog</span></span>  
  
-   <span data-ttu-id="f36c7-120">sp_GetMBCSCharLen</span><span class="sxs-lookup"><span data-stu-id="f36c7-120">sp_GetMBCSCharLen</span></span>  
  
-   <span data-ttu-id="f36c7-121">sp_helplog</span><span class="sxs-lookup"><span data-stu-id="f36c7-121">sp_helplog</span></span>  
  
-   <span data-ttu-id="f36c7-122">sp_helpsql</span><span class="sxs-lookup"><span data-stu-id="f36c7-122">sp_helpsql</span></span>  
  
-   <span data-ttu-id="f36c7-123">sp_IsMBCSLeadByte</span><span class="sxs-lookup"><span data-stu-id="f36c7-123">sp_IsMBCSLeadByte</span></span>  
  
-   <span data-ttu-id="f36c7-124">sp_lock2</span><span class="sxs-lookup"><span data-stu-id="f36c7-124">sp_lock2</span></span>  
  
-   <span data-ttu-id="f36c7-125">sp_MSget_current_activity</span><span class="sxs-lookup"><span data-stu-id="f36c7-125">sp_MSget_current_activity</span></span>  
  
-   <span data-ttu-id="f36c7-126">sp_MSset_current_activity</span><span class="sxs-lookup"><span data-stu-id="f36c7-126">sp_MSset_current_activity</span></span>  
  
-   <span data-ttu-id="f36c7-127">sp_MSobjessearch</span><span class="sxs-lookup"><span data-stu-id="f36c7-127">sp_MSobjessearch</span></span>  
  
-   <span data-ttu-id="f36c7-128">xp_enum_ActiveScriptEngines</span><span class="sxs-lookup"><span data-stu-id="f36c7-128">xp_enum_ActiveScriptEngines</span></span>  
  
-   <span data-ttu-id="f36c7-129">xp_eventlog</span><span class="sxs-lookup"><span data-stu-id="f36c7-129">xp_eventlog</span></span>  
  
-   <span data-ttu-id="f36c7-130">xp_GetAdminGroupName</span><span class="sxs-lookup"><span data-stu-id="f36c7-130">xp_GetAdminGroupName</span></span>  
  
-   <span data-ttu-id="f36c7-131">xp_GetFileDetails</span><span class="sxs-lookup"><span data-stu-id="f36c7-131">xp_GetFileDetails</span></span>  
  
-   <span data-ttu-id="f36c7-132">xp_GetLocalSystemAccountName</span><span class="sxs-lookup"><span data-stu-id="f36c7-132">xp_GetLocalSystemAccountName</span></span>  
  
-   <span data-ttu-id="f36c7-133">xp_IsNTAdmin</span><span class="sxs-lookup"><span data-stu-id="f36c7-133">xp_IsNTAdmin</span></span>  
  
-   <span data-ttu-id="f36c7-134">xp_MSLocalSystem</span><span class="sxs-lookup"><span data-stu-id="f36c7-134">xp_MSLocalSystem</span></span>  
  
-   <span data-ttu-id="f36c7-135">xp_MSnt2000</span><span class="sxs-lookup"><span data-stu-id="f36c7-135">xp_MSnt2000</span></span>  
  
-   <span data-ttu-id="f36c7-136">xp_MSplatform</span><span class="sxs-lookup"><span data-stu-id="f36c7-136">xp_MSplatform</span></span>  
  
-   <span data-ttu-id="f36c7-137">xp_SetSecurity</span><span class="sxs-lookup"><span data-stu-id="f36c7-137">xp_SetSecurity</span></span>  
  
-   <span data-ttu-id="f36c7-138">xp_varbintohexstr</span><span class="sxs-lookup"><span data-stu-id="f36c7-138">xp_varbintohexstr</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="f36c7-139">Azione correttiva</span><span class="sxs-lookup"><span data-stu-id="f36c7-139">Corrective Action</span></span>  
  
### <a name="documented-system-stored-procedures"></a><span data-ttu-id="f36c7-140">Stored procedure di sistema documentate</span><span class="sxs-lookup"><span data-stu-id="f36c7-140">Documented System Stored Procedures</span></span>  
 <span data-ttu-id="f36c7-141">Modificare le applicazioni in base alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f36c7-141">Modify your applications according to the following table.</span></span>  
  
|<span data-ttu-id="f36c7-142">Anziché</span><span class="sxs-lookup"><span data-stu-id="f36c7-142">Instead of</span></span>|<span data-ttu-id="f36c7-143">Procedere nel modo seguente</span><span class="sxs-lookup"><span data-stu-id="f36c7-143">Do this</span></span>|  
|----------------|-------------|  
|<span data-ttu-id="f36c7-144">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="f36c7-144">sp_addalias</span></span>|<span data-ttu-id="f36c7-145">Sostituire gli alias con una combinazione di account utente e ruoli del database.</span><span class="sxs-lookup"><span data-stu-id="f36c7-145">Replace aliases with a combination of user accounts and database roles.</span></span> <span data-ttu-id="f36c7-146">Per ulteriori informazioni, vedere gli argomenti "CREATE USER (Transact-SQL)" e "CREATE ROLE (Transact-SQL)" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f36c7-146">For more information, see "CREATE USER (Transact-SQL)" and "CREATE ROLE (Transact-SQL)" in SQL Server Books Online.</span></span> <span data-ttu-id="f36c7-147">Rimuovere gli alias nei database aggiornati utilizzando sp_dropalias.</span><span class="sxs-lookup"><span data-stu-id="f36c7-147">Remove aliases in upgraded databases by using sp_dropalias.</span></span>|  
|<span data-ttu-id="f36c7-148">sp_addgroupsp_changegroup</span><span class="sxs-lookup"><span data-stu-id="f36c7-148">sp_addgroupsp_changegroup</span></span><br /><br /> <span data-ttu-id="f36c7-149">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="f36c7-149">sp_dropgroup</span></span><br /><br /> <span data-ttu-id="f36c7-150">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="f36c7-150">sp_helpgroup</span></span>|<span data-ttu-id="f36c7-151">Utilizzare i ruoli.</span><span class="sxs-lookup"><span data-stu-id="f36c7-151">Use roles.</span></span> <span data-ttu-id="f36c7-152">Per ulteriori informazioni, vedere gli argomenti relativi ai ruoli a livello di server e ai ruoli a livello di database nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f36c7-152">For more information, see "Server-Level Roles" and "Database-Level Roles" in SQL Server Books Online.</span></span>|  
  
### <a name="undocmented-system-stored-procedures"></a><span data-ttu-id="f36c7-153">Stored procedure di sistema non documentate</span><span class="sxs-lookup"><span data-stu-id="f36c7-153">Undocmented System Stored Procedures</span></span>  
 <span data-ttu-id="f36c7-154">È possibile creare stored procedure CLR con funzionalità equivalente per sostituire le stored procedure di sistema non documentate.</span><span class="sxs-lookup"><span data-stu-id="f36c7-154">You can create CLR stored procedures with equivalent functionality to replace the undocumented system stored procedures.</span></span> <span data-ttu-id="f36c7-155">Per ulteriori informazioni, vedere l'argomento "Stored procedure CLR" nella documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f36c7-155">For more information, see the topic "CLR Stored Procedures" in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f36c7-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f36c7-156">See Also</span></span>  
 <span data-ttu-id="f36c7-157">[Problemi di aggiornamento motore di database](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="f36c7-157">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="f36c7-158">SQL Server 2014 preparazione aggiornamento &#91;nuova&#93;</span><span class="sxs-lookup"><span data-stu-id="f36c7-158">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
