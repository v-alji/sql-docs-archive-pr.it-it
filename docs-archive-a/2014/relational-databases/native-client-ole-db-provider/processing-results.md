---
title: Elaborazione dei risultati | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, results processing
- OLE DB, processing results
- rowsets [SQL Server], results processing
- results [SQL Server Native Client]
ms.assetid: 20887ac4-f649-4e7f-92e6-f929e2e70952
author: rothja
ms.author: jroth
ms.openlocfilehash: b9e5bf00b4d2e554536c9f2ba1a328390b93a8a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636041"
---
# <a name="processing-results"></a><span data-ttu-id="adcf5-102">Risultati dell'elaborazione</span><span class="sxs-lookup"><span data-stu-id="adcf5-102">Processing Results</span></span>
  <span data-ttu-id="adcf5-103">Se un oggetto set di righe viene prodotto dall'esecuzione di un comando o dalla generazione di un oggetto set di righe direttamente dal provider, il consumer deve recuperare e accedere ai dati nel set di righe.</span><span class="sxs-lookup"><span data-stu-id="adcf5-103">If a rowset object is produced by either the execution of a command or the generation of a rowset object directly from the provider, the consumer needs to retrieve and access data in the rowset.</span></span>  
  
 <span data-ttu-id="adcf5-104">I set di righe sono gli oggetti centrali che consentono al provider OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client di esporre dati in formato tabulare.</span><span class="sxs-lookup"><span data-stu-id="adcf5-104">Rowsets are the central objects that enable the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider to expose data in tabular form.</span></span> <span data-ttu-id="adcf5-105">Concettualmente, un set di righe è un set in cui ogni riga include dati di colonne</span><span class="sxs-lookup"><span data-stu-id="adcf5-105">Conceptually, a rowset is a set of rows in which each row has column data.</span></span> <span data-ttu-id="adcf5-106">Un oggetto set di righe espone interfacce come **IRowset**, che contiene metodi per il recupero di righe in sequenza dal set di righe, **IAccessor**, che permette la definizione di un gruppo di associazioni di colonna che descrivono la modalità di associazione dei dati tabulari alle variabili del programma di tipo consumer, **IColumnsInfo**, che fornisce informazioni sulle colonne nel set di righe, e **IRowsetInfo**, che fornisce informazioni sul set di righe.</span><span class="sxs-lookup"><span data-stu-id="adcf5-106">A rowset object exposes interfaces such as **IRowset** (contains methods for fetching rows from the rowset sequentially), **IAccessor** (permits the definition of a group of column bindings describing the way tabular data is bound to consumer program variables), **IColumnsInfo** (provides information about columns in the rowset), and **IRowsetInfo** (provides information about rowset).</span></span>  
  
 <span data-ttu-id="adcf5-107">Un utente può chiamare il metodo **IRowset::GetData** per recuperare una riga di dati dal set di righe in un buffer.</span><span class="sxs-lookup"><span data-stu-id="adcf5-107">A consumer can call the **IRowset::GetData** method to retrieve a row of data from the rowset into a buffer.</span></span> <span data-ttu-id="adcf5-108">Prima che venga chiamato **GetData**, il consumer descrive il buffer mediante un set di strutture DBBINDING.</span><span class="sxs-lookup"><span data-stu-id="adcf5-108">Before **GetData** is called, the consumer describes the buffer using a set of DBBINDING structures.</span></span> <span data-ttu-id="adcf5-109">Ogni associazione descrive la modalità di archiviazione di una colonna in un set di righe in un buffer del consumer e contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="adcf5-109">Each binding describes how a column in a rowset is stored in a consumer buffer and contains the following:</span></span>  
  
-   <span data-ttu-id="adcf5-110">Ordinale della colonna, o parametro, a cui si applica l'associazione.</span><span class="sxs-lookup"><span data-stu-id="adcf5-110">Ordinal of the column (or parameter) to which the binding applies.</span></span>  
  
-   <span data-ttu-id="adcf5-111">Informazioni sugli elementi associati, ad esempio, valore dei dati, lunghezza dei dati e relativo stato dell'associazione.</span><span class="sxs-lookup"><span data-stu-id="adcf5-111">Information about what is bound (for example, data value, length of the data, and its binding status).</span></span>  
  
-   <span data-ttu-id="adcf5-112">Informazioni sugli offset presenti nel buffer per ciascuna di queste parti.</span><span class="sxs-lookup"><span data-stu-id="adcf5-112">Information about what is offset in the buffer to each of these parts.</span></span>  
  
-   <span data-ttu-id="adcf5-113">Lunghezza e tipo dei valori dei dati inclusi nel buffer del consumer.</span><span class="sxs-lookup"><span data-stu-id="adcf5-113">Length and type of the data values as they exist in the consumer buffer.</span></span>  
  
 <span data-ttu-id="adcf5-114">Quando si recuperano i dati, il provider utilizza le informazioni presenti in ogni associazione per determinare dove e come recuperare i dati dal buffer del consumer.</span><span class="sxs-lookup"><span data-stu-id="adcf5-114">When getting the data, the provider uses information in each binding to determine where and how to retrieve data from the consumer buffer.</span></span> <span data-ttu-id="adcf5-115">Durante l'impostazione dei dati nel buffer del consumer, il provider utilizza le informazioni presenti in ogni associazione per determinare dove e come restituire i dati all'interno del buffer.</span><span class="sxs-lookup"><span data-stu-id="adcf5-115">When setting data in the consumer buffer, the provider uses information in each binding to determine where and how to return data in the consumer's buffer.</span></span>  
  
 <span data-ttu-id="adcf5-116">Dopo aver specificato le strutture DBBINDING, viene creata una funzione di accesso (**IAccessor::CreateAccessor**).</span><span class="sxs-lookup"><span data-stu-id="adcf5-116">After the DBBINDING structures are specified, an accessor is created (**IAccessor::CreateAccessor**).</span></span> <span data-ttu-id="adcf5-117">Una funzione di accesso è una raccolta di associazioni e viene utilizzata per ottenere o impostare i dati nel buffer del consumer.</span><span class="sxs-lookup"><span data-stu-id="adcf5-117">An accessor is a collection of bindings and is used to get or set the data in the consumer buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adcf5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adcf5-118">See Also</span></span>  
 <span data-ttu-id="adcf5-119">[Creazione di un'applicazione provider OLE DB SQL Server Native Client](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="adcf5-119">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="adcf5-120">Procedure relative a OLE DB</span><span class="sxs-lookup"><span data-stu-id="adcf5-120">OLE DB How-to Topics</span></span>](../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
