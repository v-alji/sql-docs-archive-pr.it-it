---
title: Esecuzione di un aggiornamento fittizio per un articolo di merge (programmazione Transact-SQL della replica) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- sp_mergedummyupdate
- dummy updates [SQL Server replication]
ms.assetid: 2f339210-4d85-4843-bd94-e86f7100d3ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 07fa0f868b2c3f98496046b138424d7d3a2fa2fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721411"
---
# <a name="perform-a-dummy-update-for-a-merge-article-replication-transact-sql-programming"></a><span data-ttu-id="d9864-102">Esecuzione di un aggiornamento fittizio per un articolo di merge (programmazione Transact-SQL della replica)</span><span class="sxs-lookup"><span data-stu-id="d9864-102">Perform a Dummy Update for a Merge Article (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="d9864-103">La replica di tipo merge utilizza i trigger come parte del processo di replica; in caso di aggiornamento di una tabella pubblicata, viene attivato un trigger di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="d9864-103">Merge replication uses triggers as part of the replication process; when an update is made to published table, an update trigger fires.</span></span> <span data-ttu-id="d9864-104">In alcuni casi, i dati possono essere aggiornati senza l'attivazione del trigger, ad esempio durante le operazioni WRITETEXT e UPDATETEXT.</span><span class="sxs-lookup"><span data-stu-id="d9864-104">In some cases, data can be updated without the trigger firing, such as during the WRITETEXT and UPDATETEXT operations.</span></span> <span data-ttu-id="d9864-105">In questi casi, è necessario aggiungere in modo esplicito un'istruzione UPDATE fittizia per replicare la modifica.</span><span class="sxs-lookup"><span data-stu-id="d9864-105">In these cases, you need to add a dummy UPDATE statement explicitly to replicate the change.</span></span> <span data-ttu-id="d9864-106">È possibile aggiungere un'istruzione UPDATE fittizia utilizzando le stored procedure di replica.</span><span class="sxs-lookup"><span data-stu-id="d9864-106">You can add a dummy UPDATE statement using replication stored procedures.</span></span>  
  
### <a name="to-add-a-dummy-update-statement"></a><span data-ttu-id="d9864-107">Per aggiungere un'istruzione UPDATE fittizia</span><span class="sxs-lookup"><span data-stu-id="d9864-107">To add a dummy UPDATE statement</span></span>  
  
1.  <span data-ttu-id="d9864-108">Eseguire l'operazione, ad esempio UPDATETEXT, su una riga in una tabella pubblicata di merge che richiede un aggiornamento fittizio.</span><span class="sxs-lookup"><span data-stu-id="d9864-108">Execute the operation (for example, UPDATETEXT) on a row in a merge published table  that requires a dummy update.</span></span>  
  
2.  <span data-ttu-id="d9864-109">Nel database del server di pubblicazione o del Sottoscrittore nel quale è stata apportata la modifica, eseguire [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d9864-109">At the server (Publisher or Subscriber) on the database where the change was made, execute [sp_mergedummyupdate &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-mergedummyupdate-transact-sql).</span></span> <span data-ttu-id="d9864-110">Specificare la tabella per la quale è stata apportata la modifica **@source_object** e l'identificatore univoco della riga modificata per **@rowguid** .</span><span class="sxs-lookup"><span data-stu-id="d9864-110">Specify the table on which the change was made for **@source_object**, and the unique identifier of the changed row for **@rowguid**.</span></span>  
  
3.  <span data-ttu-id="d9864-111">Sincronizzare la sottoscrizione per replicare la riga modificata.</span><span class="sxs-lookup"><span data-stu-id="d9864-111">Synchronize the subscription to replicate the changed row.</span></span>  
  
  
