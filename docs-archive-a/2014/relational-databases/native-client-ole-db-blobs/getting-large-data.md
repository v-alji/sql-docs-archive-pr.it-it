---
title: Recupero di dati di grandi dimensioni | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BLOBs, OLE objects
- DBPROP_ACCESSORDER property
- SQL Server Native Client OLE DB provider, BLOBs
- large data, OLE objects
ms.assetid: a31c5632-96aa-483f-a307-004c5149fbc0
author: rothja
ms.author: jroth
ms.openlocfilehash: 38602df026d2e752a758672dde23a59a26ad4917
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725607"
---
# <a name="getting-large-data"></a><span data-ttu-id="a2fa8-102">Recupero di dati di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="a2fa8-102">Getting Large Data</span></span>
  <span data-ttu-id="a2fa8-103">In generale, i consumer devono isolare il codice che crea un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oggetto di archiviazione del provider OLE DB di Native Client da altro codice che gestisce i dati a cui non viene fatto riferimento tramite un puntatore a interfaccia **ISequentialStream** .</span><span class="sxs-lookup"><span data-stu-id="a2fa8-103">In general, consumers should isolate code that creates a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider storage object from other code that handles data not referenced through an **ISequentialStream** interface pointer.</span></span>  
  
 <span data-ttu-id="a2fa8-104">In questo argomento vengono descritte le funzionalità disponibili con le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2fa8-104">This topic refers to functionality available with the following functions:</span></span>  
  
-   <span data-ttu-id="a2fa8-105">IRowset:GetData</span><span class="sxs-lookup"><span data-stu-id="a2fa8-105">IRowset:GetData</span></span>  
  
-   <span data-ttu-id="a2fa8-106">IRow::GetColumns</span><span class="sxs-lookup"><span data-stu-id="a2fa8-106">IRow::GetColumns</span></span>  
  
-   <span data-ttu-id="a2fa8-107">ICommand::Execute</span><span class="sxs-lookup"><span data-stu-id="a2fa8-107">ICommand::Execute</span></span>  
  
 <span data-ttu-id="a2fa8-108">Se la proprietà DBPROP_ACCESSORDER (nel gruppo di proprietà del set di righe) è impostata su uno dei valori DBPROPVAL_AO_SEQUENTIAL o DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS, il consumer deve recuperare solo una singola riga di dati in una chiamata al metodo **GetNextRows** perché i dati BLOB non vengono memorizzati nel buffer.</span><span class="sxs-lookup"><span data-stu-id="a2fa8-108">If the DBPROP_ACCESSORDER property (in the rowset property group) is set to either of the values DBPROPVAL_AO_SEQUENTIAL or DBPROPVAL_AO_SEQUENTIALSTORAGEOBJECTS, the consumer should fetch only a single row of data in a call to the **GetNextRows** method because BLOB data is not buffered.</span></span> <span data-ttu-id="a2fa8-109">Se il valore di DBPROP_ACCESSORDER è impostato su DBPROPVAL_AO_RANDOM, il consumer può recuperare più righe di dati in **GetNextRows**.</span><span class="sxs-lookup"><span data-stu-id="a2fa8-109">If the value of DBPROP_ACCESSORDER is set to DBPROPVAL_AO_RANDOM, the consumer can fetch multiple rows of data in **GetNextRows**.</span></span>  
  
 <span data-ttu-id="a2fa8-110">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non recupera dati di grandi dimensioni da [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fino a quando non viene richiesto dal consumer.</span><span class="sxs-lookup"><span data-stu-id="a2fa8-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not retrieve large data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until requested to do so by the consumer.</span></span> <span data-ttu-id="a2fa8-111">Il consumer deve associare tutti i dati di tipo short in una funzione di accesso e quindi utilizzare una o più funzioni di accesso temporanee per recuperare valori di dati di grandi dimensioni come richiesto.</span><span class="sxs-lookup"><span data-stu-id="a2fa8-111">The consumer should bind all short data in one accessor, and then use one or more temporary accessors to retrieve large data values as required.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2fa8-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2fa8-112">Example</span></span>  
 <span data-ttu-id="a2fa8-113">In questo esempio viene recuperato un valore di dati di grandi dimensioni da una singola colonna:</span><span class="sxs-lookup"><span data-stu-id="a2fa8-113">This example retrieves a large data value from a single column:</span></span>  
  
```  
HRESULT GetUnboundData  
    (  
    IRowset* pIRowset,  
    HROW hRow,  
    ULONG nCol,   
    BYTE* pUnboundData  
    )  
    {  
    UINT                cbRow = sizeof(IUnknown*) + sizeof(ULONG);  
    BYTE*               pRow = new BYTE[cbRow];  
  
    DBOBJECT            dbobject;  
  
    IAccessor*          pIAccessor = NULL;  
    HACCESSOR           haccessor;  
  
    DBBINDING           dbbinding;  
    ULONG               ulbindstatus;  
  
    ULONG               dwStatus;  
    ISequentialStream*  pISequentialStream;  
    ULONG               cbRead;  
  
    HRESULT             hr;  
  
    // Set up the DBOBJECT structure.  
    dbobject.dwFlags = STGM_READ;  
    dbobject.iid = IID_ISequentialStream;  
  
    // Create the DBBINDING, requesting a storage-object pointer from  
    // The SQL Server Native Client OLE DB provider.  
    dbbinding.iOrdinal = nCol;  
    dbbinding.obValue = 0;  
    dbbinding.obStatus = sizeof(IUnknown*);  
    dbbinding.obLength = 0;  
    dbbinding.pTypeInfo = NULL;  
    dbbinding.pObject = &dbobject;  
    dbbinding.pBindExt = NULL;  
    dbbinding.dwPart = DBPART_VALUE | DBPART_STATUS;  
    dbbinding.dwMemOwner = DBMEMOWNER_CLIENTOWNED;  
    dbbinding.eParamIO = DBPARAMIO_NOTPARAM;  
    dbbinding.cbMaxLen = 0;  
    dbbinding.dwFlags = 0;  
    dbbinding.wType = DBTYPE_IUNKNOWN;  
    dbbinding.bPrecision = 0;  
    dbbinding.bScale = 0;  
  
    if (FAILED(hr = pIRowset->  
        QueryInterface(IID_IAccessor, (void**) &pIAccessor)))  
        {  
        // Process QueryInterface failure.  
        return (hr);  
        }  
  
    // Create the accessor.  
    if (FAILED(hr = pIAccessor->CreateAccessor(DBACCESSOR_ROWDATA, 1,  
        &dbbinding, 0, &haccessor, &ulbindstatus)))  
        {  
        // Process error from CreateAccessor.  
        pIAccessor->Release();  
        return (hr);  
        }  
  
    // Read and process BLOCK_SIZE bytes at a time.  
    if (SUCCEEDED(hr = pIRowset->GetData(hRow, haccessor, pRow)))  
        {  
        dwStatus = *((ULONG*) (pRow + dbbinding.obStatus));  
  
        if (dwStatus == DBSTATUS_S_ISNULL)  
            {  
            // Process NULL data  
            }  
        else if (dwStatus == DBSTATUS_S_OK)  
            {  
            pISequentialStream = *((ISequentialStream**)   
                (pRow + dbbinding.obValue));  
  
            do  
                {  
                if (SUCCEEDED(hr =  
                    pISequentialStream->Read(pUnboundData,  
                    BLOCK_SIZE, &cbRead)))  
                    {  
                    pUnboundData += cbRead;  
                    }  
                }  
            while (SUCCEEDED(hr) && cbRead >= BLOCK_SIZE);  
  
            pISequentialStream->Release();  
            }  
        }  
    else  
        {  
        // Process error from GetData.  
        }  
  
    pIAccessor->ReleaseAccessor(haccessor, NULL);  
    pIAccessor->Release();  
    delete [] pRow;  
  
    return (hr);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2fa8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2fa8-114">See Also</span></span>  
 <span data-ttu-id="a2fa8-115">[Oggetti BLOB e OLE](blobs-and-ole-objects.md) </span><span class="sxs-lookup"><span data-stu-id="a2fa8-115">[BLOBs and OLE Objects](blobs-and-ole-objects.md) </span></span>  
 [<span data-ttu-id="a2fa8-116">Utilizzo di tipi di dati per valori di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="a2fa8-116">Using Large Value Types</span></span>](../native-client/features/using-large-value-types.md)  
  
  
