---
title: IBCPSession::BCPColumns (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPColumns (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPColumns method
ms.assetid: c338abe8-9e30-4853-a7c6-b1a6c00095e1
author: rothja
ms.author: jroth
ms.openlocfilehash: c842b2a815074c0db7e6ab21e0a85eac68a986a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723776"
---
# <a name="ibcpsessionbcpcolumns-ole-db"></a><span data-ttu-id="3179f-102">IBCPSession::BCPColumns (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="3179f-102">IBCPSession::BCPColumns (OLE DB)</span></span>
  <span data-ttu-id="3179f-103">Imposta il numero di campi da associare alle colonne di una tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3179f-103">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3179f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3179f-104">Syntax</span></span>  
  
```  
  
HRESULT BCPColumns(   
DBCOUNTITEMnColumns);  
```  
  
## <a name="remarks"></a><span data-ttu-id="3179f-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3179f-105">Remarks</span></span>  
 <span data-ttu-id="3179f-106">Chiama internamente [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) per impostare i valori predefiniti per i dati dei campi.</span><span class="sxs-lookup"><span data-stu-id="3179f-106">Internally it calls [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) to set the default values for field data.</span></span> <span data-ttu-id="3179f-107">Questi valori predefiniti vengono ottenuti dalle informazioni sulle colonne di SQL Server recuperate internamente dal provider quando si specifica il nome di tabella tramite [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="3179f-107">These default values are obtained from the SQL Server column information that the provider internally retrieves when the table name is specified through [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3179f-108">È possibile chiamare questo metodo solo dopo avere chiamato **BCPInit** con un nome di file valido.</span><span class="sxs-lookup"><span data-stu-id="3179f-108">This method can be called only after **BCPInit** has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="3179f-109">È consigliabile chiamare questo metodo solo se si intende utilizzare un formato di file utente diverso da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="3179f-109">You should call this method only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="3179f-110">Per ulteriori informazioni su una descrizione del formato di file utente predefinito, vedere il metodo **BCPInit**.</span><span class="sxs-lookup"><span data-stu-id="3179f-110">For more information about a description of the default user-file format, see the **BCPInit** method.</span></span>  
  
 <span data-ttu-id="3179f-111">Dopo avere chiamato il metodo **BCPColumns**, è necessario chiamare il metodo **BCPColFmt** per ogni colonna del file utente per definire in modo completo un formato di file personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3179f-111">After calling the **BCPColumns** method, you must call the **BCPColFmt** method for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="3179f-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3179f-112">Arguments</span></span>  
 <span data-ttu-id="3179f-113">*nColumns*[in]</span><span class="sxs-lookup"><span data-stu-id="3179f-113">*nColumns*[in]</span></span>  
 <span data-ttu-id="3179f-114">Numero totale di campi nel file utente.</span><span class="sxs-lookup"><span data-stu-id="3179f-114">The total number of fields in the user file.</span></span> <span data-ttu-id="3179f-115">Anche se si prepara la copia bulk dei dati dal file utente in una tabella di SQL Server e non si prevede di copiare tutti i campi del file utente, è comunque necessario impostare l'argomento *nColumns* sul numero totale di campi del file utente.</span><span class="sxs-lookup"><span data-stu-id="3179f-115">Even if you are preparing to bulk copy data from the user file to a SQL Server table and do not intend to copy all fields in the user file, you must still set the *nColumns* argument to the total number of user-file fields.</span></span> <span data-ttu-id="3179f-116">I campi ignorati possono quindi essere specificati tramite **BCPColFmt**.</span><span class="sxs-lookup"><span data-stu-id="3179f-116">The skipped fields can then be specified through **BCPColFmt**.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="3179f-117">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="3179f-117">Return Code Values</span></span>  
 <span data-ttu-id="3179f-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="3179f-118">S_OK</span></span>  
 <span data-ttu-id="3179f-119">Il metodo è riuscito.</span><span class="sxs-lookup"><span data-stu-id="3179f-119">The method succeeded.</span></span>  
  
 <span data-ttu-id="3179f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3179f-120">E_FAIL</span></span>  
 <span data-ttu-id="3179f-121">Si è verificato un errore specifico del provider. per informazioni dettagliate, usare l'interfaccia [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) .</span><span class="sxs-lookup"><span data-stu-id="3179f-121">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="3179f-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="3179f-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="3179f-123">La chiamata al metodo non era prevista.</span><span class="sxs-lookup"><span data-stu-id="3179f-123">The call to the method was unexpected.</span></span> <span data-ttu-id="3179f-124">Non è stato ad esempio chiamato il metodo **BCPInit** prima della chiamata a questo metodo.</span><span class="sxs-lookup"><span data-stu-id="3179f-124">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="3179f-125">Si verifica inoltre quando questo metodo viene chiamato più volte per un'operazione di copia bulk.</span><span class="sxs-lookup"><span data-stu-id="3179f-125">Also occurs when this method is called more than once for a bulk copy operation.</span></span>  
  
 <span data-ttu-id="3179f-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3179f-126">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="3179f-127">Errore di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="3179f-127">Out-of-memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3179f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3179f-128">See Also</span></span>  
 <span data-ttu-id="3179f-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="3179f-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="3179f-130">Esecuzione di operazioni di copia bulk</span><span class="sxs-lookup"><span data-stu-id="3179f-130">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
