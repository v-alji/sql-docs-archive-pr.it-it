---
title: IRowsetFastLoad::InsertRow (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::InsertRow (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- InsertRow method
ms.assetid: 594d3461-34d2-41e7-8ad4-bd2753601ab6
author: rothja
ms.author: jroth
ms.openlocfilehash: 4e9ea952f27574270ee333919f778814ff3de462
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636694"
---
# <a name="irowsetfastloadinsertrow-ole-db"></a><span data-ttu-id="d15ba-102">IRowsetFastLoad::InsertRow (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="d15ba-102">IRowsetFastLoad::InsertRow (OLE DB)</span></span>
  <span data-ttu-id="d15ba-103">Aggiunge una riga al set di righe della copia bulk.</span><span class="sxs-lookup"><span data-stu-id="d15ba-103">Adds a row to the bulk copy rowset.</span></span> <span data-ttu-id="d15ba-104">Per gli esempi, vedere [Eseguire una copia bulk dei dati usando IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) e [Inviare dati BLOB a SQL Server usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="d15ba-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](../native-client-ole-db-how-to/bulk-copy-data-using-irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d15ba-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d15ba-105">Syntax</span></span>  
  
```  
  
HRESULT InsertRow(  
HACCESSOR  
hAccessor  
,  
void*  
pData  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="d15ba-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d15ba-106">Arguments</span></span>  
 <span data-ttu-id="d15ba-107">*hAccessor*[in]</span><span class="sxs-lookup"><span data-stu-id="d15ba-107">*hAccessor*[in]</span></span>  
 <span data-ttu-id="d15ba-108">Handle della funzione di accesso che definisce i dati delle righe per la copia bulk.</span><span class="sxs-lookup"><span data-stu-id="d15ba-108">The handle of the accessor defining the row data for bulk copy.</span></span> <span data-ttu-id="d15ba-109">La funzione di accesso a cui viene fatto riferimento è una funzione di accesso di riga, che specifica l'associazione alla memoria del consumer contenente valori di dati.</span><span class="sxs-lookup"><span data-stu-id="d15ba-109">The accessor referenced is a row accessor, binding consumer-owned memory containing data values.</span></span>  
  
 <span data-ttu-id="d15ba-110">*pData*[in]</span><span class="sxs-lookup"><span data-stu-id="d15ba-110">*pData*[in]</span></span>  
 <span data-ttu-id="d15ba-111">Puntatore alla memoria del consumer contenente valori di dati.</span><span class="sxs-lookup"><span data-stu-id="d15ba-111">A pointer to the consumer-owned memory containing data values.</span></span> <span data-ttu-id="d15ba-112">Per altre informazioni, vedere le [strutture DBBINDING](https://go.microsoft.com/fwlink/?LinkId=65955).</span><span class="sxs-lookup"><span data-stu-id="d15ba-112">For more information, see [DBBINDING Structures](https://go.microsoft.com/fwlink/?LinkId=65955).</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="d15ba-113">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="d15ba-113">Return Code Values</span></span>  
 <span data-ttu-id="d15ba-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d15ba-114">S_OK</span></span>  
 <span data-ttu-id="d15ba-115">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="d15ba-115">The method succeeded.</span></span> <span data-ttu-id="d15ba-116">I valori di stato associati per tutte le colonne hanno il valore DBSTATUS_S_OK o DBSTATUS_S_NULL.</span><span class="sxs-lookup"><span data-stu-id="d15ba-116">Any bound status values for all columns have value DBSTATUS_S_OK or DBSTATUS_S_NULL.</span></span>  
  
 <span data-ttu-id="d15ba-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d15ba-117">E_FAIL</span></span>  
 <span data-ttu-id="d15ba-118">Si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="d15ba-118">An error occurred.</span></span> <span data-ttu-id="d15ba-119">Le informazioni sull'errore sono disponibili nelle interfacce degli errori del set di righe.</span><span class="sxs-lookup"><span data-stu-id="d15ba-119">Error information is available from the rowset's error interfaces.</span></span>  
  
 <span data-ttu-id="d15ba-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d15ba-120">E_INVALIDARG</span></span>  
 <span data-ttu-id="d15ba-121">L'argomento *pData* è stato impostato su un puntatore NULL.</span><span class="sxs-lookup"><span data-stu-id="d15ba-121">The *pData* argument was set to a NULL pointer.</span></span>  
  
 <span data-ttu-id="d15ba-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d15ba-122">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="d15ba-123">SQLNCLI11 non è stato in grado di allocare memoria sufficiente per completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="d15ba-123">SQLNCLI11 was unable to allocate sufficient memory to complete the request.</span></span>  
  
 <span data-ttu-id="d15ba-124">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="d15ba-124">E_UNEXPECTED</span></span>  
 <span data-ttu-id="d15ba-125">Il metodo è stato chiamato su un set di righe della copia bulk precedentemente invalidato dal metodo [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="d15ba-125">The method was called on a bulk copy rowset previously invalidated by the [IRowsetFastLoad::Commit](irowsetfastload-commit-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="d15ba-126">DB_E_BADACCESSORHANDLE</span><span class="sxs-lookup"><span data-stu-id="d15ba-126">DB_E_BADACCESSORHANDLE</span></span>  
 <span data-ttu-id="d15ba-127">L'argomento *hAccessor* specificato dal consumer non è valido.</span><span class="sxs-lookup"><span data-stu-id="d15ba-127">The *hAccessor* argument provided by the consumer was invalid.</span></span>  
  
 <span data-ttu-id="d15ba-128">DB_E_BADACCESSORTYPE</span><span class="sxs-lookup"><span data-stu-id="d15ba-128">DB_E_BADACCESSORTYPE</span></span>  
 <span data-ttu-id="d15ba-129">La funzione di accesso specificata non è una funzione di accesso di riga o non specifica la memoria del consumer.</span><span class="sxs-lookup"><span data-stu-id="d15ba-129">The specified accessor was not a row accessor or did not specify consumer-owned memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d15ba-130">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d15ba-130">Remarks</span></span>  
 <span data-ttu-id="d15ba-131">Un errore di conversione dei dati del consumer nel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipo di dati di una colonna causa la restituzione di un E_FAIL dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="d15ba-131">An error converting consumer data to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type for a column causes an E_FAIL return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span> <span data-ttu-id="d15ba-132">I dati possono essere trasmessi a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con qualsiasi metodo **InsertRow** o solo con il metodo **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d15ba-132">Data can be transmitted to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on any **InsertRow** method or only on **Commit** method.</span></span> <span data-ttu-id="d15ba-133">L'applicazione consumer può chiamare il metodo **InsertRow** diverse volte usando i dati errati prima di ricevere un avviso relativo all'errore di conversione del tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="d15ba-133">The consumer application can call the **InsertRow** method many times with erroneous data before it receives notice that a data type conversion error exists.</span></span> <span data-ttu-id="d15ba-134">Poiché il metodo **Commit** verifica che tutti i dati vengano specificati correttamente dal consumer, se necessario, il consumer può usare **Commit** in modo appropriato per convalidare i dati.</span><span class="sxs-lookup"><span data-stu-id="d15ba-134">Because the **Commit** method ensures that all data is correctly specified by the consumer, the consumer can use the **Commit** method appropriately to validate data as necessary.</span></span>  
  
 <span data-ttu-id="d15ba-135">I [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set di righe della copia bulk del provider OLE DB di Native Client sono di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="d15ba-135">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowsets are write-only.</span></span> <span data-ttu-id="d15ba-136">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non espone metodi che consentono di eseguire query sul set di righe.</span><span class="sxs-lookup"><span data-stu-id="d15ba-136">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes no methods allowing consumer query of the rowset.</span></span> <span data-ttu-id="d15ba-137">Per terminare l'elaborazione, il consumer può rilasciare il riferimento all'interfaccia [IRowsetFastLoad](irowsetfastload-ole-db.md) senza chiamare il metodo **Commit**.</span><span class="sxs-lookup"><span data-stu-id="d15ba-137">To terminate processing, the consumer can release its reference on the [IRowsetFastLoad](irowsetfastload-ole-db.md) interface without calling the **Commit** method.</span></span> <span data-ttu-id="d15ba-138">Non sono disponibili funzioni per accedere alle righe inserite dal consumer nel set di righe e modificarne i valori o per rimuoverle singolarmente dal set di righe.</span><span class="sxs-lookup"><span data-stu-id="d15ba-138">There are no facilities for accessing a consumer-inserted row in the rowset and changing its values, or removing it individually from the rowset.</span></span>  
  
 <span data-ttu-id="d15ba-139">Le righe oggetto di copia bulk vengono formattate sul server per [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d15ba-139">Bulk copied rows are formatted on the server for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d15ba-140">Le opzioni eventualmente impostate per la connessione o per la sessione, ad esempio ANSI_PADDING, influiscono sul formato di riga.</span><span class="sxs-lookup"><span data-stu-id="d15ba-140">The row format is affected by any options that may have been set for the connection or session such as ANSI_PADDING.</span></span> <span data-ttu-id="d15ba-141">Per impostazione predefinita, questa opzione è impostata su per tutte le connessioni effettuate tramite il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="d15ba-141">This option is set on by default for any connection made through the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15ba-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d15ba-142">See Also</span></span>  
 [<span data-ttu-id="d15ba-143">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d15ba-143">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
