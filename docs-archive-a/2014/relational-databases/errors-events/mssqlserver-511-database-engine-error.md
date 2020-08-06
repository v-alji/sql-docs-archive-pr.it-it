---
title: MSSQLSERVER_511 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 511 (Database Engine error)
ms.assetid: 0c85686a-53c1-4180-ba8c-2000e68a0d63
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5b69d2c043997e2947563de119bc4ee89fdf4e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87714380"
---
# <a name="mssqlserver_511"></a><span data-ttu-id="21d68-102">MSSQLSERVER_511</span><span class="sxs-lookup"><span data-stu-id="21d68-102">MSSQLSERVER_511</span></span>
    
## <a name="details"></a><span data-ttu-id="21d68-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="21d68-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="21d68-104">Nome prodotto</span><span class="sxs-lookup"><span data-stu-id="21d68-104">Product Name</span></span>|<span data-ttu-id="21d68-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="21d68-105">SQL Server</span></span>|  
|<span data-ttu-id="21d68-106">ID evento</span><span class="sxs-lookup"><span data-stu-id="21d68-106">Event ID</span></span>|<span data-ttu-id="21d68-107">511</span><span class="sxs-lookup"><span data-stu-id="21d68-107">511</span></span>|  
|<span data-ttu-id="21d68-108">Origine evento</span><span class="sxs-lookup"><span data-stu-id="21d68-108">Event Source</span></span>|<span data-ttu-id="21d68-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="21d68-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="21d68-110">Componente</span><span class="sxs-lookup"><span data-stu-id="21d68-110">Component</span></span>|<span data-ttu-id="21d68-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="21d68-111">SQLEngine</span></span>|  
|<span data-ttu-id="21d68-112">Nome simbolico</span><span class="sxs-lookup"><span data-stu-id="21d68-112">Symbolic Name</span></span>|<span data-ttu-id="21d68-113">ROW_TOOBIG</span><span class="sxs-lookup"><span data-stu-id="21d68-113">ROW_TOOBIG</span></span>|  
|<span data-ttu-id="21d68-114">Testo del messaggio</span><span class="sxs-lookup"><span data-stu-id="21d68-114">Message Text</span></span>|<span data-ttu-id="21d68-115">Impossibile creare una riga con dimensioni %d, perché tale valore è maggiore delle dimensioni massime consentite %d.</span><span class="sxs-lookup"><span data-stu-id="21d68-115">Cannot create a row of size %d which is greater than the allowable maximum of %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="21d68-116">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="21d68-116">Explanation</span></span>  
 <span data-ttu-id="21d68-117">L'operazione tentata ha provocato il superamento delle dimensioni massime di una riga.</span><span class="sxs-lookup"><span data-stu-id="21d68-117">The operation you have tried has exceeded the maximum size of a row.</span></span> <span data-ttu-id="21d68-118">rappresentate in genere dal valore 8.060 byte.</span><span class="sxs-lookup"><span data-stu-id="21d68-118">Usually, the maximum size of a row is 8,060 bytes.</span></span> <span data-ttu-id="21d68-119">Alcuni formati di archiviazione contengono overhead che può ridurre le dimensioni della riga disponibili per i dati.</span><span class="sxs-lookup"><span data-stu-id="21d68-119">Some storage formats contain overhead that can reduce the row size that is available for data.</span></span> <span data-ttu-id="21d68-120">Se si utilizzano colonne di tipo sparse, ad esempio, il valore delle dimensioni massime di una riga è di 8.018 byte.</span><span class="sxs-lookup"><span data-stu-id="21d68-120">For example, when you use sparse columns, the maximum size of a row is 8,018 bytes.</span></span> <span data-ttu-id="21d68-121">Per alcune operazioni che aggiungono o rimuovono righe e per altre che modificano il tipo di dati di una colonna è necessario riscrivere la riga nella pagina di dati, quindi rimuovere riga originale.</span><span class="sxs-lookup"><span data-stu-id="21d68-121">Some operations that add or remove rows and some operations that change the data type of a column require the row to be rewritten on the data page, and then the original row is removed.</span></span> <span data-ttu-id="21d68-122">Per queste operazioni, il limite effettivo alla dimensioni della riga è la metà di quello massimo consentito,</span><span class="sxs-lookup"><span data-stu-id="21d68-122">In these operations, the effective limit to the size of the row is half the maximum limit.</span></span> <span data-ttu-id="21d68-123">poiché la riga originale e quella modificata devono essere contenute entrambe nella pagina di dati per un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="21d68-123">This is because the original row and the modified row must both be contained on the data page for a short period.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="21d68-124">Ogni colonna non null **varchar (max)** o **nvarchar (max)** richiede 24 byte di allocazione fissa aggiuntiva che viene conteggiata rispetto al limite di righe di 8.060 byte durante un'operazione di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="21d68-124">Each non-null  **varchar(max)** or **nvarchar(max)** column requires 24 bytes of additional fixed allocation which counts against the 8,060 byte row limit during a sort operation.</span></span> <span data-ttu-id="21d68-125">Questo può creare un limite implicito al numero di colonne non null **varchar (max)** o **nvarchar (max)** che è possibile creare in una tabella.</span><span class="sxs-lookup"><span data-stu-id="21d68-125">This can create an implicit limit to the number of non-null **varchar(max)** or **nvarchar(max)** columns that can be created in a table.</span></span> <span data-ttu-id="21d68-126">Non vengono segnalati errori particolari (oltre il normale avviso che indica che le dimensioni massime per le righe superano il valore massimo consentito di 8060 byte) durante la creazione della tabella o l'inserimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="21d68-126">No special error is provided when the table is created (beyond the usual warning that the maximum row size exceeds the allowed maximum of 8060 bytes) or at the time of data insertion.</span></span> <span data-ttu-id="21d68-127">Queste dimensioni delle righe eccessive possono causare errori (ad esempio, l'errore 512) durante le normali operazioni, ad esempio un aggiornamento della chiave dell'indice cluster o l'ordinamento del set di colonne completo, che gli utenti non possono prevedere finché non eseguono un'operazione.</span><span class="sxs-lookup"><span data-stu-id="21d68-127">This large row size can cause errors (such as error 512) during some normal operations, such as a clustered index key update, or sorts of the full column set, which users cannot anticipate until performing an operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21d68-128">Azione dell'utente</span><span class="sxs-lookup"><span data-stu-id="21d68-128">User Action</span></span>  
 <span data-ttu-id="21d68-129">Se possibile, ridurre le dimensioni della riga.</span><span class="sxs-lookup"><span data-stu-id="21d68-129">If it is possible, reduce the size of the row.</span></span>  
  
 <span data-ttu-id="21d68-130">Se si ritiene che il problema sia causato da un aggiornamento sul posto della riga, è necessario modificare la tabella in più passaggi.</span><span class="sxs-lookup"><span data-stu-id="21d68-130">If you think the problem is caused by an in-place update of the row, you must change the table in multiple steps.</span></span> <span data-ttu-id="21d68-131">Creare una nuova tabella e trasferirvi i dati.</span><span class="sxs-lookup"><span data-stu-id="21d68-131">Create a new table, and transfer the data into the new table.</span></span> <span data-ttu-id="21d68-132">Successivamente eliminare la tabella originale e rinominare la nuova tabella oppure troncare la tabella originale, modificarne le righe, quindi spostarvi nuovamente i dati.</span><span class="sxs-lookup"><span data-stu-id="21d68-132">Then, either delete the original table and rename the new table, or truncate the original table, modify the rows in the original table, and then move the data back into it.</span></span>  
  
  
