---
title: Editor attività Inserimento bulk (pagina Opzioni) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.options.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: b3702811-3eb8-4b28-9190-5ae7a1a7bb6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1751d1e0ac01d5459a8c76e6a48626c2ad6deafd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722991"
---
# <a name="bulk-insert-task-editor-options-page"></a><span data-ttu-id="07f0d-102">Editor attività Inserimento bulk (pagina Opzioni)</span><span class="sxs-lookup"><span data-stu-id="07f0d-102">Bulk Insert Task Editor (Options Page)</span></span>
  <span data-ttu-id="07f0d-103">Utilizzare la pagina **Opzioni** della finestra di dialogo **Editor attività Inserimento bulk** per impostare le proprietà relative all'operazione di inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="07f0d-103">Use the **Options** page of the **Bulk Insert Task Editor** dialog box to set properties for the bulk insert operation.</span></span> <span data-ttu-id="07f0d-104">L'attività Inserimento bulk consente di copiare grandi quantità di dati all'interno di una vista o tabella di [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="07f0d-104">The Bulk Insert task copies large amounts of data into a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table or view.</span></span>  
  
 <span data-ttu-id="07f0d-105">Per altre informazioni sull'uso degli inserimenti di massa, vedere [Attività Inserimento bulk](control-flow/bulk-insert-task.md) e [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="07f0d-105">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="07f0d-106">Opzioni</span><span class="sxs-lookup"><span data-stu-id="07f0d-106">Options</span></span>  
 <span data-ttu-id="07f0d-107">**CodePage**</span><span class="sxs-lookup"><span data-stu-id="07f0d-107">**CodePage**</span></span>  
 <span data-ttu-id="07f0d-108">Consente di specificare la tabella codici dei dati contenuti nel file.</span><span class="sxs-lookup"><span data-stu-id="07f0d-108">Specify the code page of the data in the data file.</span></span>  
  
 <span data-ttu-id="07f0d-109">**DataFileType**</span><span class="sxs-lookup"><span data-stu-id="07f0d-109">**DataFileType**</span></span>  
 <span data-ttu-id="07f0d-110">Consente di specificare il valore di tipo di dati da utilizzare nell'operazione di caricamento.</span><span class="sxs-lookup"><span data-stu-id="07f0d-110">Specify the data-type value to use in the load operation.</span></span>  
  
 <span data-ttu-id="07f0d-111">**BatchSize**</span><span class="sxs-lookup"><span data-stu-id="07f0d-111">**BatchSize**</span></span>  
 <span data-ttu-id="07f0d-112">Consente di specificare il numero di righe di un batch.</span><span class="sxs-lookup"><span data-stu-id="07f0d-112">Specify the number of rows in a batch.</span></span> <span data-ttu-id="07f0d-113">Il valore predefinito è l'intero file di dati.</span><span class="sxs-lookup"><span data-stu-id="07f0d-113">The default is the entire data file.</span></span> <span data-ttu-id="07f0d-114">Se si imposta **BatchSize** su zero, i dati vengono caricati in un singolo batch.</span><span class="sxs-lookup"><span data-stu-id="07f0d-114">If you set **BatchSize** to zero, the data is loaded in a single batch.</span></span>  
  
 <span data-ttu-id="07f0d-115">**LastRow**</span><span class="sxs-lookup"><span data-stu-id="07f0d-115">**LastRow**</span></span>  
 <span data-ttu-id="07f0d-116">Consente di specificare l'ultima riga da copiare.</span><span class="sxs-lookup"><span data-stu-id="07f0d-116">Specify the last row to copy.</span></span>  
  
 <span data-ttu-id="07f0d-117">**FirstRow**</span><span class="sxs-lookup"><span data-stu-id="07f0d-117">**FirstRow**</span></span>  
 <span data-ttu-id="07f0d-118">Consente di specificare la riga dalla quale iniziare la copia.</span><span class="sxs-lookup"><span data-stu-id="07f0d-118">Specify the first row from which to start copying.</span></span>  
  
 <span data-ttu-id="07f0d-119">**Opzioni**</span><span class="sxs-lookup"><span data-stu-id="07f0d-119">**Options**</span></span>  
 |<span data-ttu-id="07f0d-120">Termine</span><span class="sxs-lookup"><span data-stu-id="07f0d-120">Term</span></span>|<span data-ttu-id="07f0d-121">Definizione</span><span class="sxs-lookup"><span data-stu-id="07f0d-121">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="07f0d-122">**Vincoli CHECK**</span><span class="sxs-lookup"><span data-stu-id="07f0d-122">**Check constraints**</span></span>|<span data-ttu-id="07f0d-123">Selezionare questa opzione per verificare i vincoli di colonna e tabella.</span><span class="sxs-lookup"><span data-stu-id="07f0d-123">Select to check the table and column constraints.</span></span>|  
|<span data-ttu-id="07f0d-124">**Mantieni valori Null**</span><span class="sxs-lookup"><span data-stu-id="07f0d-124">**Keep nulls**</span></span>|<span data-ttu-id="07f0d-125">Selezionare questa opzione per mantenere i valori Null durante l'operazione di inserimento bulk anziché inserire tutti i valori predefiniti per le colonne vuote.</span><span class="sxs-lookup"><span data-stu-id="07f0d-125">Select to retain null values during the bulk insert operation, instead of inserting any default values for empty columns.</span></span>|  
|<span data-ttu-id="07f0d-126">**Consenti IDENTITY_INSERT**</span><span class="sxs-lookup"><span data-stu-id="07f0d-126">**Enable identity insert**</span></span>|<span data-ttu-id="07f0d-127">Selezionare questa opzione per inserire valori esistenti in una colonna Identity.</span><span class="sxs-lookup"><span data-stu-id="07f0d-127">Select to insert existing values into an identity column.</span></span>|  
|<span data-ttu-id="07f0d-128">**Blocco a livello di tabella**</span><span class="sxs-lookup"><span data-stu-id="07f0d-128">**Table lock**</span></span>|<span data-ttu-id="07f0d-129">Selezionare questa opzione per bloccare la tabella durante l'inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="07f0d-129">Select to lock the table during the bulk insert.</span></span>|  
|<span data-ttu-id="07f0d-130">**Attive trigger**</span><span class="sxs-lookup"><span data-stu-id="07f0d-130">**Fire triggers**</span></span>|<span data-ttu-id="07f0d-131">Selezionare questa opzione per attivare tutti i trigger di eliminazione, aggiornamento o inserimento nella tabella.</span><span class="sxs-lookup"><span data-stu-id="07f0d-131">Select to fire any insert, update, or delete triggers on the table.</span></span>|  
  
 <span data-ttu-id="07f0d-132">**SortedData**</span><span class="sxs-lookup"><span data-stu-id="07f0d-132">**SortedData**</span></span>  
 <span data-ttu-id="07f0d-133">Consente di specificare la clausola ORDER BY nell'istruzione di inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="07f0d-133">Specify the ORDER BY clause in the bulk insert statement.</span></span> <span data-ttu-id="07f0d-134">Il nome della colonna deve corrispondere a una colonna valida della tabella di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07f0d-134">The column name that you supply must be a valid column in the destination table.</span></span> <span data-ttu-id="07f0d-135">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="07f0d-135">The default is `false`.</span></span> <span data-ttu-id="07f0d-136">Questo valore implica che i dati non vengono ordinati da una clausola ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="07f0d-136">This means that the data is not sorted by an ORDER BY clause.</span></span>  
  
 <span data-ttu-id="07f0d-137">**MaxErrors**</span><span class="sxs-lookup"><span data-stu-id="07f0d-137">**MaxErrors**</span></span>  
 <span data-ttu-id="07f0d-138">Consente di specificare il numero massimo di errori che possono verificarsi prima dell'annullamento dell'operazione di inserimento bulk.</span><span class="sxs-lookup"><span data-stu-id="07f0d-138">Specify the maximum number of errors that can occur before the bulk insert operation is canceled.</span></span> <span data-ttu-id="07f0d-139">Un valore pari a 0 indica che è consentito un numero infinito di errori.</span><span class="sxs-lookup"><span data-stu-id="07f0d-139">A value of 0 indicates that an infinite number of errors are allowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="07f0d-140">Ogni riga che non è possibile importare tramite l'operazione di caricamento bulk viene considerata un errore.</span><span class="sxs-lookup"><span data-stu-id="07f0d-140">Each row that cannot be imported by the bulk load operation is counted as one error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f0d-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07f0d-141">See Also</span></span>  
 <span data-ttu-id="07f0d-142">[Guida di riferimento ai messaggi e agli errori di Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="07f0d-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="07f0d-143">[Editor attività Inserimento bulk &#40;pagina generale&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="07f0d-143">[Bulk Insert Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="07f0d-144">[Editor attività Inserimento bulk &#40;pagina connessione&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="07f0d-144">[Bulk Insert Task Editor &#40;Connection Page&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span></span>  
 <span data-ttu-id="07f0d-145">[Pagina Espressioni](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="07f0d-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="07f0d-146">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="07f0d-146">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
