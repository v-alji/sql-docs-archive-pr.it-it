---
title: IBCPSession (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- IBCPSession interface
ms.assetid: 00d0311f-8b71-4ad6-824d-0e89119347a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d32da9c06a200d5924dbae18d6b7513f46c88ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723768"
---
# <a name="ibcpsession-ole-db"></a><span data-ttu-id="b4c55-102">IBCPSession (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="b4c55-102">IBCPSession (OLE DB)</span></span>
  <span data-ttu-id="b4c55-103">L'interfaccia **IBCPSession** espone il supporto per le operazioni di copia bulk basate su file [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4c55-103">The **IBCPSession** interface exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] file-based bulk copy operations.</span></span> <span data-ttu-id="b4c55-104">L'interfaccia **IBCPSession** viene esposta nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native client nello stesso livello delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="b4c55-104">The **IBCPSession** interface is exposed in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider under the same level as Sessions.</span></span> <span data-ttu-id="b4c55-105">Nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client gli oggetti origine dati sono Factory per gli oggetti sessione e le operazioni di copia bulk vengono specificate nella proprietà di connessione SSPROP_ENABLEBULKCOPY.</span><span class="sxs-lookup"><span data-stu-id="b4c55-105">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, data source objects are factories for Session objects, and bulk copy operations are specified in the connection property SSPROP_ENABLEBULKCOPY.</span></span> <span data-ttu-id="b4c55-106">Inoltre, la proprietà SSPROP_ENABLEFASTLOAD deve essere impostata su True.</span><span class="sxs-lookup"><span data-stu-id="b4c55-106">In addition, the SSPROP_ENABLEFASTLOAD property should be set to true.</span></span>  
  
 <span data-ttu-id="b4c55-107">La chiamata al metodo **IDBCreateSession::CreateSession** comporterà quindi la creazione di un oggetto **BulkCopySession**.</span><span class="sxs-lookup"><span data-stu-id="b4c55-107">Calling the **IDBCreateSession::CreateSession** method will then result in the creation of a **BulkCopySession** object.</span></span> <span data-ttu-id="b4c55-108">Tutti i metodi di copia bulk basati su file esposti tramite l'oggetto **IBCPSession** possono essere quindi chiamati con firme molto simili sull'interfaccia **IBCPSession** di questo oggetto **IBCPSession**.</span><span class="sxs-lookup"><span data-stu-id="b4c55-108">All the file-based bulk copy methods exposed through the **IBCPSession** object are then callable with nearly similar signatures on this **IBCPSession** object's **IBCPSession** interface.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b4c55-109">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta operazioni di copia bulk basate sulla memoria tramite l'interfaccia [IRowsetFastLoad](irowsetfastload-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="b4c55-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports memory-based bulk copy operations through the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="b4c55-110">Per ulteriori informazioni sull'utilizzo del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client per le operazioni di copia bulk, vedere [esecuzione di operazioni di copia bulk](../native-client/features/performing-bulk-copy-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b4c55-110">For more information about using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider for bulk copy operations, see [Performing Bulk Copy Operations](../native-client/features/performing-bulk-copy-operations.md).</span></span>  
  
 <span data-ttu-id="b4c55-111">Per un esempio che illustra come usare l'interfaccia **IBCPSession**, vedere [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="b4c55-111">For a sample showing how to use the **IBCPSession** interface, see [IBCPSession::BCPDone &#40;OLE DB&#41;](ibcpsession-bcpdone-ole-db.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4c55-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b4c55-112">In This Section</span></span>  
  
|<span data-ttu-id="b4c55-113">Metodo</span><span class="sxs-lookup"><span data-stu-id="b4c55-113">Method</span></span>|<span data-ttu-id="b4c55-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4c55-114">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4c55-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-115">IBCPSession::BCPColFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolfmt-ole-db.md)|<span data-ttu-id="b4c55-116">Crea un'associazione tra variabili di programma e colonne di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4c55-116">Creates a binding between program variables and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] columns.</span></span>|  
|[<span data-ttu-id="b4c55-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-117">IBCPSession::BCPColumns &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcolumns-ole-db.md)|<span data-ttu-id="b4c55-118">Imposta il numero di campi da associare alle colonne di una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4c55-118">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|[<span data-ttu-id="b4c55-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-119">IBCPSession::BCPControl &#40;OLE DB&#41;</span></span>](ibcpsession-bcpcontrol-ole-db.md)|<span data-ttu-id="b4c55-120">Imposta le opzioni per un'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="b4c55-120">Sets the options for a bulk copy operation.</span></span>|  
|[<span data-ttu-id="b4c55-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-121">IBCPSession::BCPDone &#40;OLE DB&#41;</span></span>](ibcpsession-bcpdone-ole-db.md)|<span data-ttu-id="b4c55-122">Esegue il commit delle righe restanti da inviare a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b4c55-122">Commits the remaining rows to be sent to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="b4c55-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-123">IBCPSession::BCPExec &#40;OLE DB&#41;</span></span>](ibcpsession-bcpexec-ole-db.md)|<span data-ttu-id="b4c55-124">Esegue l'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="b4c55-124">Performs the bulk copy operation.</span></span>|  
|[<span data-ttu-id="b4c55-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-125">IBCPSession::BCPInit &#40;OLE DB&#41;</span></span>](ibcpsession-bcpinit-ole-db.md)|<span data-ttu-id="b4c55-126">Inizializza la struttura della copia bulk, esegue alcune operazioni di controllo degli errori, verifica che i dati e i nomi dei file di formato siano corretti, quindi li apre.</span><span class="sxs-lookup"><span data-stu-id="b4c55-126">Initializes the bulk copy structure, performs some error checking, verifies that the data and format file names are correct, and then opens them.</span></span>|  
|[<span data-ttu-id="b4c55-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-127">IBCPSession::BCPReadFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpreadfmt-ole-db.md)|<span data-ttu-id="b4c55-128">Legge le informazioni sul formato per ogni colonna dal file di formato.</span><span class="sxs-lookup"><span data-stu-id="b4c55-128">Reads format information for each column from the format file.</span></span>|  
|[<span data-ttu-id="b4c55-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-129">IBCPSession::BCPWriteFmt &#40;OLE DB&#41;</span></span>](ibcpsession-bcpwritefmt-ole-db.md)|<span data-ttu-id="b4c55-130">Scrive informazioni sul formato per ogni colonna nel file di formato.</span><span class="sxs-lookup"><span data-stu-id="b4c55-130">Writes format information for each column to the format file.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4c55-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4c55-131">See Also</span></span>  
 [<span data-ttu-id="b4c55-132">Interfacce &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b4c55-132">Interfaces &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/interfaces-ole-db.md)  
  
  
