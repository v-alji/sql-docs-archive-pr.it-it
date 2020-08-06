---
title: IBCPSession::BCPReadFmt (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPReadFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPReadFmt method
ms.assetid: e2a12050-94e4-48a3-8a48-b780d646f116
author: rothja
ms.author: jroth
ms.openlocfilehash: ca811dceb8ab6771e3bdd6689a8e11eca6a0e3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723767"
---
# <a name="ibcpsessionbcpreadfmt-ole-db"></a><span data-ttu-id="056ee-102">IBCPSession::BCPReadFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="056ee-102">IBCPSession::BCPReadFmt (OLE DB)</span></span>
  <span data-ttu-id="056ee-103">Legge le informazioni sul formato per ogni colonna dal file di formato.</span><span class="sxs-lookup"><span data-stu-id="056ee-103">Reads format information for each column from the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="056ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="056ee-104">Syntax</span></span>  
  
```  
  
HRESULT BCPReadFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="056ee-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="056ee-105">Remarks</span></span>  
 <span data-ttu-id="056ee-106">Il metodo **BCPReadFmt** viene usato per la lettura di dati da un file di formato che specifica il formato dei dati nel file di dati.</span><span class="sxs-lookup"><span data-stu-id="056ee-106">The **BCPReadFmt** method is used for reading data from a format file that specifies the format of data in the data file.</span></span> <span data-ttu-id="056ee-107">Questo metodo è in grado di rilevare la versione corretta del file di formato.</span><span class="sxs-lookup"><span data-stu-id="056ee-107">This method is capable of detecting the correct version of the format file.</span></span> <span data-ttu-id="056ee-108">Può rilevare automaticamente se il file è in formato xml o testo stile antico e comportarsi di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="056ee-108">It can automatically detect whether the format file is in xml or old style text format and behaves accordingly.</span></span> <span data-ttu-id="056ee-109">Le versioni dei file di formato supportate dall' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilità bcp del provider di OLE DB di Native Client sono la versione 6,0 o successive.</span><span class="sxs-lookup"><span data-stu-id="056ee-109">The format file versions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider BCP are version 6.0 or newer.</span></span>  
  
 <span data-ttu-id="056ee-110">Dopo la lettura dei valori del formato, il metodo **BCPReadFmt** effettua le chiamate appropriate ai metodi [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) e [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="056ee-110">After the **BCPReadFmt** method reads the format values, it makes the appropriate calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span> <span data-ttu-id="056ee-111">L'utente può evitare di analizzare un file di formato ed effettuare queste chiamate.</span><span class="sxs-lookup"><span data-stu-id="056ee-111">There is no need for the user to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="056ee-112">Per salvare un file di formato, chiamare il metodo [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="056ee-112">To save a format file, call the [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md) method.</span></span> <span data-ttu-id="056ee-113">Le chiamate al metodo **BCPReadFmt** possono fare riferimento ai formati salvati.</span><span class="sxs-lookup"><span data-stu-id="056ee-113">Calls to the **BCPReadFmt** method can reference saved formats.</span></span> <span data-ttu-id="056ee-114">In alternativa, l'utilità per la copia bulk (**bcp**) può salvare i formati di dati definiti dall'utente in file ai quali può fare riferimento il metodo **BCPReadFmt**.</span><span class="sxs-lookup"><span data-stu-id="056ee-114">Alternatively, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by the **BCPReadFmt** method.</span></span>  
  
 <span data-ttu-id="056ee-115">Il `BCP_OPTION_DELAYREADFMT` valore del parametro *EOption* di [IBCPSession:: BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifica il comportamento di IBCPSession:: BCPReadFmt.</span><span class="sxs-lookup"><span data-stu-id="056ee-115">The `BCP_OPTION_DELAYREADFMT` value of the *eOption* parameter of [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifies the behavior of IBCPSession::BCPReadFmt.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="056ee-116">Argomenti</span><span class="sxs-lookup"><span data-stu-id="056ee-116">Arguments</span></span>  
 <span data-ttu-id="056ee-117">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="056ee-117">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="056ee-118">Percorso e nome del file contenente i valori di formato per il file di dati.</span><span class="sxs-lookup"><span data-stu-id="056ee-118">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="056ee-119">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="056ee-119">Return Code Values</span></span>  
 <span data-ttu-id="056ee-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="056ee-120">S_OK</span></span>  
 <span data-ttu-id="056ee-121">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="056ee-121">The method succeeded.</span></span>  
  
 <span data-ttu-id="056ee-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="056ee-122">E_FAIL</span></span>  
 <span data-ttu-id="056ee-123">Si è verificato un errore specifico del provider. Per informazioni dettagliate, usare l'interfaccia [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="056ee-123">A provider-specific error occurred, for detailed information use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="056ee-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="056ee-124">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="056ee-125">Errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="056ee-125">Out of memory error.</span></span>  
  
 <span data-ttu-id="056ee-126">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="056ee-126">E_UNEXPECTED</span></span>  
 <span data-ttu-id="056ee-127">La chiamata al metodo non era prevista.</span><span class="sxs-lookup"><span data-stu-id="056ee-127">The call to the method was unexpected.</span></span> <span data-ttu-id="056ee-128">Non è stato ad esempio chiamato il metodo [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) prima della chiamata a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="056ee-128">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="056ee-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="056ee-129">See Also</span></span>  
 <span data-ttu-id="056ee-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="056ee-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="056ee-131">Esecuzione di operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="056ee-131">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
