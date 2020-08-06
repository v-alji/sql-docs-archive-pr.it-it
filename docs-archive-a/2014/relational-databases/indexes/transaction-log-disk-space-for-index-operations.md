---
title: Spazio su disco per il log delle transazioni per operazioni sugli indici | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- index disk space [SQL Server]
- space [SQL Server], indexes
- transaction logs [SQL Server], disk space
- disk space [SQL Server], transaction logs
- space [SQL Server], transaction logs
ms.assetid: 4f8a4922-4507-4072-be67-c690528d5c3b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c34c9ff7a9494496d6c60d5920184c0ce86131d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723839"
---
# <a name="transaction-log-disk-space-for-index-operations"></a><span data-ttu-id="ec3c2-102">Spazio su disco per il log delle transazioni per operazioni sugli indici</span><span class="sxs-lookup"><span data-stu-id="ec3c2-102">Transaction Log Disk Space for Index Operations</span></span>
  <span data-ttu-id="ec3c2-103">Le operazioni sugli indici su larga scala possono generare carichi di dati di grandi dimensioni che possono causare un rapido riempimento del log delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-103">Large-scale index operations can generate large data loads that can cause the transaction log to fill quickly.</span></span> <span data-ttu-id="ec3c2-104">Per garantire la possibilità di esecuzione del rollback dell'operazione sull'indice, non è possibile troncare il log delle transazioni fino al completamento dell'operazione sull'indice. Durante tale operazione è tuttavia possibile eseguire il backup del log.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-104">To make sure that the index operation can be rolled back, the transaction log cannot be truncated until the index operation has completed; however, the log can be backed up during the index operation.</span></span> <span data-ttu-id="ec3c2-105">Nel log delle transazioni deve pertanto esserci spazio sufficiente per archiviare sia le transazioni dell'operazione sull'indice che eventuali transazioni utente simultanee per la durata dell'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-105">Therefore, the transaction log must have sufficient room to store both the index operation transactions and any concurrent user transactions for the duration of the index operation.</span></span> <span data-ttu-id="ec3c2-106">Questo è valido sia per le operazioni sugli indici online che non offline.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-106">This is true for both offline and online index operations.</span></span> <span data-ttu-id="ec3c2-107">Poiché durante un'operazione sull'indice offline non è possibile accedere alle tabelle sottostanti, il numero di transazioni utente potrebbe essere basso e il log potrebbe non aumentare in modo eccessivamente rapido.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-107">Because the underlying tables cannot be accessed during an offline index operation, there may be few user transactions and the log may not grow as quickly.</span></span> <span data-ttu-id="ec3c2-108">Le operazioni sugli indici online non impediscono attività utente simultanee e pertanto le operazioni sugli indici su larga scala in combinazione con transazioni utente simultanee significative possono causare un aumento continuo del log delle transazioni senza che sia possibile troncarlo.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-108">Online index operations do not prevent concurrent user activity, therefore, large-scale online index operations combined with significant concurrent user transactions can cause continuous growth of the transaction log without an option to truncate the log.</span></span>  
  
## <a name="recommendations"></a><span data-ttu-id="ec3c2-109">Consigli</span><span class="sxs-lookup"><span data-stu-id="ec3c2-109">Recommendations</span></span>  
 <span data-ttu-id="ec3c2-110">Quando si eseguono operazioni sugli indici su larga scala, considerare i consigli seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec3c2-110">When you run large-scale index operations, consider the following recommendations:</span></span>  
  
1.  <span data-ttu-id="ec3c2-111">Verificare di avere eseguito il backup del log delle transazioni e di averlo troncato prima di eseguire operazioni sugli indici online su larga scala e verificare che nel log vi sia spazio sufficiente per archiviare le transazioni utente e di indice previste.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-111">Make sure the transaction log has been backed up and truncated before running large-scale index operations online, and that the log has sufficient space to store the projected index and user transactions.</span></span>  
  
2.  <span data-ttu-id="ec3c2-112">Valutare l'opportunità di impostare l'opzione SORT_IN_TEMPDB su ON per l'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-112">Consider setting the SORT_IN_TEMPDB option to ON for the index operation.</span></span> <span data-ttu-id="ec3c2-113">In questo modo, è possibile separare le transazioni di indice dalle transazioni utente simultanee.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-113">This separates the index transactions from the concurrent user transactions.</span></span> <span data-ttu-id="ec3c2-114">Le transazioni di indice verranno archiviate nel log delle transazioni di **tempdb** e le transazioni utente simultanee verranno archiviate nel log delle transazioni del database utente.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-114">The index transactions will be stored in the **tempdb** transaction log, and the concurrent user transactions will be stored in the transaction log of the user database.</span></span> <span data-ttu-id="ec3c2-115">In questo modo, il log delle transazioni del database utente può essere troncato durante l'operazione sull'indice, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-115">This allows for the transaction log of the user database to be truncated during the index operation if it is required.</span></span> <span data-ttu-id="ec3c2-116">Se, inoltre, il log del database **tempdb** non si trova nello stesso disco del log del database utente, i due log non useranno lo stesso spazio su disco.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-116">Additionally, if the **tempdb** log is not on the same disk as the user database log, the two logs are not competing for the same disk space.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ec3c2-117">Verificare che nel database **tempdb** e nel log delle transazioni vi sia spazio su disco sufficiente per gestire l'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-117">Verify that the **tempdb** database and transaction log have sufficient disk space to handle the index operation.</span></span> <span data-ttu-id="ec3c2-118">Il log delle transazioni di **tempdb** non può essere troncato prima del termine dell'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-118">The **tempdb** transaction log cannot be truncated until the index operation is completed.</span></span>  
  
3.  <span data-ttu-id="ec3c2-119">Utilizzare un modello di recupero del database che consenta la registrazione minima dell'operazione sull'indice.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-119">Use a database recovery model that allows for minimal logging of the index operation.</span></span> <span data-ttu-id="ec3c2-120">In questo modo, sarà possibile ridurre la dimensione del log e impedire che il relativo spazio venga riempito.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-120">This may reduce the size of the log and prevent the log from filling the log space.</span></span>  
  
4.  <span data-ttu-id="ec3c2-121">Non eseguire l'operazione sull'indice online in una transazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-121">Do not run the online index operation in an explicit transaction.</span></span> <span data-ttu-id="ec3c2-122">Il log non verrà troncato fino al termine della transazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="ec3c2-122">The log will not be truncated until the explicit transaction ends.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="ec3c2-123">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="ec3c2-123">Related Content</span></span>  
 [<span data-ttu-id="ec3c2-124">Disk Space Requirements for Index DDL Operations</span><span class="sxs-lookup"><span data-stu-id="ec3c2-124">Disk Space Requirements for Index DDL Operations</span></span>](disk-space-requirements-for-index-ddl-operations.md)  
  
 [<span data-ttu-id="ec3c2-125">Esempio di spazio su disco per gli indici</span><span class="sxs-lookup"><span data-stu-id="ec3c2-125">Index Disk Space Example</span></span>](index-disk-space-example.md)  
  
  
