---
title: Altri problemi di aggiornamento motore di database | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], upgrading
ms.assetid: 78a1d8e8-fa97-476f-8777-84617d145340
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: db496112fc975304bb2d7da9d9ea1c52e6dd8bec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87626473"
---
# <a name="other-database-engine-upgrade-issues"></a><span data-ttu-id="de383-102">Altri problemi di aggiornamento del motore di database</span><span class="sxs-lookup"><span data-stu-id="de383-102">Other Database Engine Upgrade Issues</span></span>
  <span data-ttu-id="de383-103">I problemi di aggiornamento seguenti non possono essere rilevati dalla versione corrente di Preparazione aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="de383-103">The following upgrade issues cannot be detected by the current version of Upgrade Advisor.</span></span> <span data-ttu-id="de383-104">Esaminare i problemi elencati di seguito per valutarne il potenziale impatto sui sistemi.</span><span class="sxs-lookup"><span data-stu-id="de383-104">Review the issues listed below to evaluate their potential impact to your systems.</span></span>  
  
## <a name="multiple-database-engine-deprecated-features"></a><span data-ttu-id="de383-105">Più caratteristiche deprecate del motore di database</span><span class="sxs-lookup"><span data-stu-id="de383-105">Multiple Database Engine Deprecated Features</span></span>  
 <span data-ttu-id="de383-106">Le opzioni o le istruzioni di [!INCLUDE[tsql](../../includes/tsql-md.md)] riportate di seguito sono deprecate:</span><span class="sxs-lookup"><span data-stu-id="de383-106">The following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements or options are deprecated:</span></span>  
  
-   <span data-ttu-id="de383-107">Opzioni NO_LOG e TRUNCATE_ONLY di BACKUP LOG</span><span class="sxs-lookup"><span data-stu-id="de383-107">NO_LOG and TRUNCATE_ONLY options of BACKUP LOG</span></span>  
  
-   <span data-ttu-id="de383-108">BACKUP TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="de383-108">BACKUP TRANSACTION</span></span>  
  
-   <span data-ttu-id="de383-109">RESTORE TRANSACTION</span><span class="sxs-lookup"><span data-stu-id="de383-109">RESTORE TRANSACTION</span></span>  
  
-   <span data-ttu-id="de383-110">DUMP</span><span class="sxs-lookup"><span data-stu-id="de383-110">DUMP</span></span>  
  
-   <span data-ttu-id="de383-111">LOAD</span><span class="sxs-lookup"><span data-stu-id="de383-111">LOAD</span></span>  
  
-   <span data-ttu-id="de383-112">DBCC CONCURRENCYVIOLATION</span><span class="sxs-lookup"><span data-stu-id="de383-112">DBCC CONCURRENCYVIOLATION</span></span>  
  
-   <span data-ttu-id="de383-113">sp_addalias</span><span class="sxs-lookup"><span data-stu-id="de383-113">sp_addalias</span></span>  
  
-   <span data-ttu-id="de383-114">sp_addgroup</span><span class="sxs-lookup"><span data-stu-id="de383-114">sp_addgroup</span></span>  
  
-   <span data-ttu-id="de383-115">sp_changegroup</span><span class="sxs-lookup"><span data-stu-id="de383-115">sp_changegroup</span></span>  
  
-   <span data-ttu-id="de383-116">sp_dropgroup</span><span class="sxs-lookup"><span data-stu-id="de383-116">sp_dropgroup</span></span>  
  
-   <span data-ttu-id="de383-117">sp_helpgroup</span><span class="sxs-lookup"><span data-stu-id="de383-117">sp_helpgroup</span></span>  
  
-   <span data-ttu-id="de383-118">syssegments</span><span class="sxs-lookup"><span data-stu-id="de383-118">syssegments</span></span>  
  
 <span data-ttu-id="de383-119">Utilizzo del protocollo VIA per connettersi al [!INCLUDE[ssDE](../../includes/ssde-md.md)] è deprecato.</span><span class="sxs-lookup"><span data-stu-id="de383-119">Use of the VIA protocol to connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] is deprecated.</span></span>  
  
## <a name="new-data-types"></a><span data-ttu-id="de383-120">Nuovi tipi di dati</span><span class="sxs-lookup"><span data-stu-id="de383-120">New Data Types</span></span>  
 <span data-ttu-id="de383-121">I seguenti tipi di dati sono tipi di sistema riservati.</span><span class="sxs-lookup"><span data-stu-id="de383-121">The following will be reserved system types.</span></span> <span data-ttu-id="de383-122">Rinominare i tipi definiti dall'utente (UDT) in conflitto prima o dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="de383-122">Rename the existing conflicting user defined types either before or after upgrade.</span></span>  
  
-   <span data-ttu-id="de383-123">Area geografica</span><span class="sxs-lookup"><span data-stu-id="de383-123">Geography</span></span>  
  
-   <span data-ttu-id="de383-124">Geometria</span><span class="sxs-lookup"><span data-stu-id="de383-124">Geometry</span></span>  
  
-   <span data-ttu-id="de383-125">Datetime2</span><span class="sxs-lookup"><span data-stu-id="de383-125">Datetime2</span></span>  
  
-   <span data-ttu-id="de383-126">HierarchyID</span><span class="sxs-lookup"><span data-stu-id="de383-126">HierarchyID</span></span>  
  
## <a name="target-table-of-the-output-into-clause-cannot-have-any-defined-triggers"></a><span data-ttu-id="de383-127">La tabella di destinazione della clausola OUTPUT INTO non può contenere trigger definiti</span><span class="sxs-lookup"><span data-stu-id="de383-127">Target Table of the OUTPUT INTO Clause Cannot Have Any Defined Triggers</span></span>  
 <span data-ttu-id="de383-128">L'OUTPUT in una tabella di destinazione quando la tabella contiene trigger abilitati non è supportato.</span><span class="sxs-lookup"><span data-stu-id="de383-128">OUTPUT INTO a target table when the table has any enabled triggers is not supported.</span></span>  
  
## <a name="compile-time-error-for-udfs-when-the-target-of-an-output-into-clause-is-a-table"></a><span data-ttu-id="de383-129">Errore in fase di compilazione per le funzioni definite dall'utente quando la destinazione di una clausola OUTPUT INTO è una tabella</span><span class="sxs-lookup"><span data-stu-id="de383-129">Compile Time Error for UDFs When the Target of an OUTPUT INTO Clause is a Table</span></span>  
 <span data-ttu-id="de383-130">Non è possibile utilizzare funzioni definite dall'utente per eseguire azioni che modificano lo stato del database.</span><span class="sxs-lookup"><span data-stu-id="de383-130">User-defined functions (UDF) cannot be used to perform actions that modify the database state.</span></span> <span data-ttu-id="de383-131">Ad esempio, una funzione definita dall'utente non può eseguire azioni DDL (CREATE/ALTER/DROP) o DML (INSERT/UPDATE/DELETE) su qualsiasi oggetto, ad eccezione delle variabili di tabella.</span><span class="sxs-lookup"><span data-stu-id="de383-131">For example, a UDF cannot perform any DDL (CREATE/ALTER/DROP) or DML (INSERT/UPDATE/DELETE) actions on any objects, except for table variables.</span></span>  
  
## <a name="merge-is-a-reserved-keyword"></a><span data-ttu-id="de383-132">MERGE è una parola chiave riservata</span><span class="sxs-lookup"><span data-stu-id="de383-132">MERGE is a Reserved Keyword</span></span>  
 <span data-ttu-id="de383-133">MERGE è ora una parola chiave completamente riservata.</span><span class="sxs-lookup"><span data-stu-id="de383-133">MERGE is now a fully-reserved keyword.</span></span> <span data-ttu-id="de383-134">Non è più possibile includere oggetti (tabella, colonna e così via) denominati MERGE nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="de383-134">Applications can no longer have objects (table, column, etc.) called MERGE.</span></span>  
  
## <a name="rename-cdc-schema"></a><span data-ttu-id="de383-135">Rinominare lo schema CDC</span><span class="sxs-lookup"><span data-stu-id="de383-135">Rename CDC Schema</span></span>  
 <span data-ttu-id="de383-136">È disponibile un nome di schema denominato CDC</span><span class="sxs-lookup"><span data-stu-id="de383-136">There is a schema name called CDC.</span></span> <span data-ttu-id="de383-137">Il nome dello schema non può essere utilizzato se **Change Data Capture** è abilitato per il database.</span><span class="sxs-lookup"><span data-stu-id="de383-137">This schema name cannot be in used if **Change Data Capture** is enabled for the database.</span></span>  
  
 <span data-ttu-id="de383-138">Prima di abilitare **Change Data Capture** per il database, è necessario eliminare lo schema cdc.</span><span class="sxs-lookup"><span data-stu-id="de383-138">You must drop the CDC schema before you enable **Change Data Capture** for the database.</span></span> <span data-ttu-id="de383-139">Questo passaggio può essere completato prima o dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="de383-139">This step can be done before or after the upgrade.</span></span> <span data-ttu-id="de383-140">Per eliminare lo schema, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="de383-140">To drop the schema, use the following steps:</span></span>  
  
1.  <span data-ttu-id="de383-141">Trasferire gli oggetti dallo schema CDC in un nuovo schema utilizzando ALTER SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="de383-141">Transfer the objects from CDC schema to a new schema name using ALTER SCHEMA.</span></span>  
  
2.  <span data-ttu-id="de383-142">Verificare le autorizzazioni per gli oggetti nel nuovo schema.</span><span class="sxs-lookup"><span data-stu-id="de383-142">Verify permissions for the objects in the new schema.</span></span>  
  
3.  <span data-ttu-id="de383-143">Apportare le modifiche necessarie all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="de383-143">Make necessary modifications to the application.</span></span>  
  
4.  <span data-ttu-id="de383-144">Eliminare lo schema CDC utilizzando DROP SCHEMA.</span><span class="sxs-lookup"><span data-stu-id="de383-144">Drop the CDC schema using DROP SCHEMA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de383-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de383-145">See Also</span></span>  
 [<span data-ttu-id="de383-146">Problemi di aggiornamento del motore di database</span><span class="sxs-lookup"><span data-stu-id="de383-146">Database Engine Upgrade Issues</span></span>](../../../2014/sql-server/install/database-engine-upgrade-issues.md)  
  
  
