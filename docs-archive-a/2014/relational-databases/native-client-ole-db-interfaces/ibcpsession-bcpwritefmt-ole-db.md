---
title: IBCPSession::BCPWriteFmt (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPWriteFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPWriteFmt method
ms.assetid: add50425-2ed6-411a-a391-4ce63c364892
author: rothja
ms.author: jroth
ms.openlocfilehash: ee4dcb5809c0f0fbb6d3f7aba6f4af5f6991e0e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636710"
---
# <a name="ibcpsessionbcpwritefmt-ole-db"></a><span data-ttu-id="8ce62-102">IBCPSession::BCPWriteFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="8ce62-102">IBCPSession::BCPWriteFmt (OLE DB)</span></span>
  <span data-ttu-id="8ce62-103">Scrive informazioni sul formato per ogni colonna nel file di formato.</span><span class="sxs-lookup"><span data-stu-id="8ce62-103">Writes format information for each column to the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ce62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ce62-104">Syntax</span></span>  
  
```  
  
HRESULT BCPWriteFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ce62-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8ce62-105">Remarks</span></span>  
 <span data-ttu-id="8ce62-106">Il file di formato specifica il formato dei dati di un file di dati creato dalla copia bulk.</span><span class="sxs-lookup"><span data-stu-id="8ce62-106">The format file specifies the data format of a data file created by bulk copy.</span></span> <span data-ttu-id="8ce62-107">Le chiamate ai metodi [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) definiscono il formato del file di dati.</span><span class="sxs-lookup"><span data-stu-id="8ce62-107">Calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods define the format of the data file.</span></span> <span data-ttu-id="8ce62-108">Il metodo **BCPWriteFmt** salva questa definizione nel file a cui fa riferimento l'argomento pwszFormatFile.</span><span class="sxs-lookup"><span data-stu-id="8ce62-108">The **BCPWriteFmt** method saves this definition in the file referenced by the pwszFormatFile argument.</span></span>  
  
 <span data-ttu-id="8ce62-109">Il metodo **BCPWriteFmt** può salvare i file di formato in formato XML o testo.</span><span class="sxs-lookup"><span data-stu-id="8ce62-109">The **BCPWriteFmt** method can save the format files in either xml or text format.</span></span> <span data-ttu-id="8ce62-110">Il formato deve essere indicato utilizzando l'opzione di controllo BCP_OPTION_XML con il metodo [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="8ce62-110">This must be indicated by using the BCP_OPTION_XML control option with the [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="8ce62-111">Per caricare un file di formato salvato, utilizzare il metodo [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="8ce62-111">To load a saved format file, use the [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md) method.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="8ce62-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8ce62-112">Arguments</span></span>  
 <span data-ttu-id="8ce62-113">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="8ce62-113">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="8ce62-114">Percorso e nome del file contenente i valori di formato per il file di dati.</span><span class="sxs-lookup"><span data-stu-id="8ce62-114">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="8ce62-115">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="8ce62-115">Return Code Values</span></span>  
 <span data-ttu-id="8ce62-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ce62-116">S_OK</span></span>  
 <span data-ttu-id="8ce62-117">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="8ce62-117">The method succeeded.</span></span>  
  
 <span data-ttu-id="8ce62-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ce62-118">E_FAIL</span></span>  
 <span data-ttu-id="8ce62-119">Si è verificato un errore specifico del provider. per informazioni dettagliate, usare l'interfaccia [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="8ce62-119">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="8ce62-120">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8ce62-120">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="8ce62-121">Errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="8ce62-121">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="8ce62-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="8ce62-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="8ce62-123">La chiamata al metodo non era prevista.</span><span class="sxs-lookup"><span data-stu-id="8ce62-123">The call to the method was unexpected.</span></span> <span data-ttu-id="8ce62-124">Non è stato ad esempio chiamato il metodo [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) prima della chiamata a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8ce62-124">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ce62-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ce62-125">See Also</span></span>  
 <span data-ttu-id="8ce62-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="8ce62-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="8ce62-127">Esecuzione di operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="8ce62-127">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
