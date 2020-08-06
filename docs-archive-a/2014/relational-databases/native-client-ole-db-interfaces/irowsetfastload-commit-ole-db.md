---
title: IRowsetFastLoad::Commit (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IRowsetFastLoad::Commit (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- Commit method
ms.assetid: 19de9128-b91a-4626-847f-af721edaa24e
author: rothja
ms.author: jroth
ms.openlocfilehash: cfdf355919f65fd2cedacd09249e2aae59321390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636698"
---
# <a name="irowsetfastloadcommit-ole-db"></a><span data-ttu-id="6cad7-102">IRowsetFastLoad::Commit (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="6cad7-102">IRowsetFastLoad::Commit (OLE DB)</span></span>
  <span data-ttu-id="6cad7-103">Contrassegna la fine di un batch di righe inserite e scrive le righe nella tabella di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cad7-103">Marks the end of a batch of inserted rows and writes the rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="6cad7-104">Per gli esempi, vedere [Eseguire una copia bulk dei dati usando IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) e [Inviare dati BLOB a SQL Server usando IROWSETFASTLOAD e ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="6cad7-104">For samples, see [Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;](irowsetfastload-ole-db.md) and [Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;](../native-client-ole-db-how-to/send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cad7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6cad7-105">Syntax</span></span>  
  
```  
  
HRESULT Commit(  
BOOL   
fDone  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="6cad7-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6cad7-106">Arguments</span></span>  
 <span data-ttu-id="6cad7-107">*fDone*[in]</span><span class="sxs-lookup"><span data-stu-id="6cad7-107">*fDone*[in]</span></span>  
 <span data-ttu-id="6cad7-108">Se impostato su FALSE, il set di righe resta valido e può essere utilizzato dal consumer per l'inserimento di altre righe.</span><span class="sxs-lookup"><span data-stu-id="6cad7-108">If FALSE, the rowset maintains validity and can be used by the consumer for additional row insertion.</span></span> <span data-ttu-id="6cad7-109">Se impostato su TRUE, il set di righe non è più valido e il consumer non può inserire altre righe.</span><span class="sxs-lookup"><span data-stu-id="6cad7-109">If TRUE, the rowset loses validity and no further insertion can be done by the consumer.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="6cad7-110">Valori del codice restituito</span><span class="sxs-lookup"><span data-stu-id="6cad7-110">Return Code Values</span></span>  
 <span data-ttu-id="6cad7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6cad7-111">S_OK</span></span>  
 <span data-ttu-id="6cad7-112">Il metodo è riuscito e tutti i dati inseriti sono stati scritti nella tabella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6cad7-112">The method succeeded and all inserted data has been written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="6cad7-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6cad7-113">E_FAIL</span></span>  
 <span data-ttu-id="6cad7-114">Si è verificato un errore specifico del provider.</span><span class="sxs-lookup"><span data-stu-id="6cad7-114">A provider-specific error occurred.</span></span> <span data-ttu-id="6cad7-115">Recuperare informazioni relative al testo dell'errore specifico dal provider.</span><span class="sxs-lookup"><span data-stu-id="6cad7-115">Retrieve error information for the specific error text from the provider.</span></span>  
  
 <span data-ttu-id="6cad7-116">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="6cad7-116">E_UNEXPECTED</span></span>  
 <span data-ttu-id="6cad7-117">Il metodo è stato chiamato su un set di righe della copia bulk precedentemente invalidato dal metodo **IRowsetFastLoad::Commit**.</span><span class="sxs-lookup"><span data-stu-id="6cad7-117">The method was called on a bulk copy rowset previously invalidated by the **IRowsetFastLoad::Commit** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cad7-118">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6cad7-118">Remarks</span></span>  
 <span data-ttu-id="6cad7-119">Un set di righe della [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] copia bulk del provider OLE DB di Native client si comporta come un set di righe in modalità di aggiornamento ritardato.</span><span class="sxs-lookup"><span data-stu-id="6cad7-119">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider bulk copy rowset behaves as a delayed-update mode rowset.</span></span> <span data-ttu-id="6cad7-120">Quando l'utente inserisce dati di riga nel set di righe, le righe inserite vengono gestite analogamente agli inserimenti in sospeso di un set di righe che supporta **IRowsetUpdate**.</span><span class="sxs-lookup"><span data-stu-id="6cad7-120">As the user inserts row data through the rowset, inserted rows are treated in the same fashion as pending inserts on a rowset supporting **IRowsetUpdate**.</span></span>  
  
 <span data-ttu-id="6cad7-121">Il consumer deve chiamare il metodo **Commit** sul set di righe della copia bulk per scrivere le righe inserite nella tabella [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esattamente come quando si usa il metodo **IRowsetUpdate::Update** per inviare le righe in sospeso a un'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6cad7-121">The consumer must call the **Commit** method on the bulk copy rowset to write inserted rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table in the same way as the **IRowsetUpdate::Update** method is used to submit pending rows to an instance of SQL Server.</span></span>  
  
 <span data-ttu-id="6cad7-122">Se il consumer rilascia il riferimento al set di righe della copia bulk senza chiamare il metodo **Commit**, tutte le righe inserite e non scritte in precedenza andranno perse.</span><span class="sxs-lookup"><span data-stu-id="6cad7-122">If the consumer releases its reference on the bulk copy rowset without calling the **Commit** method, all inserted rows not previously written are lost.</span></span>  
  
 <span data-ttu-id="6cad7-123">Il consumer può raggruppare le righe inserite chiamando il metodo **Commit** con l'argomento *fDone* impostato su FALSE.</span><span class="sxs-lookup"><span data-stu-id="6cad7-123">The consumer can batch inserted rows by calling the **Commit** method with the *fDone* argument set to FALSE.</span></span> <span data-ttu-id="6cad7-124">Quando *fDone* è impostato su TRUE, il set di righe non è più valido.</span><span class="sxs-lookup"><span data-stu-id="6cad7-124">When *fDone*is set to TRUE, the rowset becomes invalid.</span></span> <span data-ttu-id="6cad7-125">Un set di righe della copia bulk non valido supporta solo l'interfaccia **ISupportErrorInfo** e il metodo **IRowsetFastLoad::Release**.</span><span class="sxs-lookup"><span data-stu-id="6cad7-125">An invalid bulk copy rowset supports only the **ISupportErrorInfo** interface and **IRowsetFastLoad::Release** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cad7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cad7-126">See Also</span></span>  
 [<span data-ttu-id="6cad7-127">IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="6cad7-127">IRowsetFastLoad &#40;OLE DB&#41;</span></span>](irowsetfastload-ole-db.md)  
  
  
