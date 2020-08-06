---
title: Errori | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- OLE/COM errors
- errors [OLE DB]
- OLE DB error handling, about error handling
- OLE DB error handling
ms.assetid: bd0612f4-96ef-4919-b0f9-b5447210fe93
author: rothja
ms.author: jroth
ms.openlocfilehash: 0560a31b60a10e278f621aa53f1c7fa038fe8039
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636058"
---
# <a name="errors"></a><span data-ttu-id="8b0c3-102">Errors</span><span class="sxs-lookup"><span data-stu-id="8b0c3-102">Errors</span></span>
  <span data-ttu-id="8b0c3-103">Gli oggetti OLE/COM segnalano gli errori tramite il codice restituito HRESULT delle funzioni membro oggetto.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-103">OLE/COM objects report errors through the HRESULT return code of object member functions.</span></span> <span data-ttu-id="8b0c3-104">Un HRESULT OLE/COM è una struttura costituita da pacchetti di byte.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-104">An OLE/COM HRESULT is a bit-packed structure.</span></span> <span data-ttu-id="8b0c3-105">OLE fornisce macro che risolvono i riferimenti dei membri di struttura.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-105">OLE provides macros that dereference structure members.</span></span>  
  
 <span data-ttu-id="8b0c3-106">OLE/COM specifica l'interfaccia **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-106">OLE/COM specifies the **IErrorInfo** interface.</span></span> <span data-ttu-id="8b0c3-107">L'interfaccia espone metodi come **GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-107">The interface exposes methods such as **GetDescription**.</span></span> <span data-ttu-id="8b0c3-108">In questo modo, i client possono estrarre i dettagli relativi agli errori dai server OLE/COM.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-108">This allows clients to extract error details from OLE/COM servers.</span></span> <span data-ttu-id="8b0c3-109">OLE DB estende **IErrorInfo** per supportare la restituzione di più pacchetti di informazioni sugli errori nell'esecuzione di una funzione con singolo membro.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-109">OLE DB extends **IErrorInfo** to support the return of multiple error information packets on a single-member function execution.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8b0c3-110">può restituire più errori.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-110">can return multiple errors.</span></span> <span data-ttu-id="8b0c3-111">Un'applicazione può recuperare gli errori del server uno alla volta chiamando [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) insieme a ISQLErrorInfo e IErrorRecords.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-111">An application can retrieve server errors one at a time by calling [IMultipleResults::GetResult](https://go.microsoft.com/fwlink/?LinkId=129630) combined with ISQLErrorInfo and IErrorRecords.</span></span>  
  
 <span data-ttu-id="8b0c3-112">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client espone l'OLE DB **IErrorInfo**con miglioramento dei record, l' `ISQLErrorInfo` oggetto personalizzato e le interfacce dell'oggetto errore [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) specifiche del provider.</span><span class="sxs-lookup"><span data-stu-id="8b0c3-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the OLE DB record-enhanced **IErrorInfo**, the custom `ISQLErrorInfo`, and the provider-specific [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) error object interfaces.</span></span>  
  
 <span data-ttu-id="8b0c3-113">Per informazioni sulla traccia degli errori, vedere [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805) (Traccia di accesso ai dati).</span><span class="sxs-lookup"><span data-stu-id="8b0c3-113">For information about tracing errors, see [Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805).</span></span> <span data-ttu-id="8b0c3-114">Per informazioni sui miglioramenti apportati alla traccia degli errori aggiunta in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], vedere [Accesso alle informazioni di diagnostica nel log degli eventi estesi](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="8b0c3-114">For information about enhancements to error tracing added in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b0c3-115">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8b0c3-115">In This Section</span></span>  
  
-   [<span data-ttu-id="8b0c3-116">Codici restituiti</span><span class="sxs-lookup"><span data-stu-id="8b0c3-116">Return Codes</span></span>](return-codes.md)  
  
-   [<span data-ttu-id="8b0c3-117">Informazioni nelle interfacce di errore</span><span class="sxs-lookup"><span data-stu-id="8b0c3-117">Information in Error Interfaces</span></span>](information-in-error-interfaces.md)  
  
-   [<span data-ttu-id="8b0c3-118">Dettagli relativi agli errori di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b0c3-118">SQL Server Error Detail</span></span>](sql-server-error-detail.md)  
  
-   [<span data-ttu-id="8b0c3-119">Recupero delle informazioni sugli errori</span><span class="sxs-lookup"><span data-stu-id="8b0c3-119">Retrieving Error Information</span></span>](retrieving-error-information.md)  
  
-   [<span data-ttu-id="8b0c3-120">Risultati dei messaggi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="8b0c3-120">SQL Server Message Results</span></span>](sql-server-message-results.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b0c3-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b0c3-121">See Also</span></span>  
 [<span data-ttu-id="8b0c3-122">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8b0c3-122">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
