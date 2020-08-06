---
title: Controllare il comportamento di trigger e vincoli durante la sincronizzazione (programmazione Transact-SQL della replica) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- identities [SQL Server replication]
- constraints [SQL Server], replication
- triggers [SQL Server], replication
- triggers [SQL Server replication]
- constraints [SQL Server replication]
- NOT FOR REPLICATION option
- NFR option
ms.assetid: 7c4e0f0e-cadc-4c99-98f4-69799b9b356b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 88176f43295fe2ab1f5f5643a46db1ce6132c5f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87624077"
---
# <a name="control-the-behavior-of-triggers-and-constraints-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="043cb-102">Controllo del comportamento di trigger e vincoli durante la sincronizzazione (programmazione Transact-SQL della replica)</span><span class="sxs-lookup"><span data-stu-id="043cb-102">Control the Behavior of Triggers and Constraints During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="043cb-103">Durante la sincronizzazione gli agenti di replica eseguono istruzioni [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql) e [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) in tabelle replicate che possono causare l'esecuzione di trigger DML (Data Manipulation Language) in tali tabelle.</span><span class="sxs-lookup"><span data-stu-id="043cb-103">During synchronization, replication agents execute [INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/insert-transact-sql), [UPDATE &#40;Transact-SQL&#41;](/sql/t-sql/queries/update-transact-sql), and [DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) statements on replicated tables, which can cause data manipulation language (DML) triggers on these tables to be executed.</span></span> <span data-ttu-id="043cb-104">In alcuni casi è necessario impedire l'attivazione di questi trigger o l'applicazione di vincoli durante la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="043cb-104">There are cases when you may need to prevent these triggers from firing or constraints from being enforced during synchronization.</span></span> <span data-ttu-id="043cb-105">Questo comportamento dipende dalla modalità di creazione del trigger o del vincolo.</span><span class="sxs-lookup"><span data-stu-id="043cb-105">This behavior depends on how the trigger or constraint is created.</span></span>  
  
### <a name="to-prevent-triggers-from-executing-during-synchronization"></a><span data-ttu-id="043cb-106">Per impedire l'esecuzione di trigger durante la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="043cb-106">To prevent triggers from executing during synchronization</span></span>  
  
1.  <span data-ttu-id="043cb-107">Quando si crea un nuovo trigger, specificare l'opzione NOT FOR REPLICATION di [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="043cb-107">When creating a new trigger, specify the NOT FOR REPLICATION option of [CREATE TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-trigger-transact-sql).</span></span>  
  
2.  <span data-ttu-id="043cb-108">Per un trigger esistente specificare l'opzione NOT FOR REPLICATION di [ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="043cb-108">For an existing trigger, specify the NOT FOR REPLICATION option of [ALTER TRIGGER &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-trigger-transact-sql).</span></span>  
  
### <a name="to-prevent-constraints-from-being-enforced-during-synchronization"></a><span data-ttu-id="043cb-109">Per impedire l'applicazione di vincoli durante la sincronizzazione</span><span class="sxs-lookup"><span data-stu-id="043cb-109">To prevent constraints from being enforced during synchronization</span></span>  
  
1.  <span data-ttu-id="043cb-110">Quando si crea un nuovo vincolo CHECK o FOREIGN KEY, specificare l'opzione CHECK NOT FOR REPLICATION nella definizione del vincolo di [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="043cb-110">When creating a new CHECK or FOREIGN KEY constraint, specify CHECK NOT FOR REPLICATION option in the constraint definition of [CREATE TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-table-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="043cb-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="043cb-111">See Also</span></span>  
 [<span data-ttu-id="043cb-112">Creare tabelle &#40;motore di database&#41;</span><span class="sxs-lookup"><span data-stu-id="043cb-112">Create Tables &#40;Database Engine&#41;</span></span>](../tables/create-tables-database-engine.md)  
  
  
