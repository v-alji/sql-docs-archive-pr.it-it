---
title: Dettagli relativi agli errori di SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- errors [OLE DB], error details
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error details
- ISQLServerErrorInfo interface
ms.assetid: 51500ee3-3d78-47ec-b90f-ebfc55642e06
author: rothja
ms.author: jroth
ms.openlocfilehash: 4c03cf62dd274f9bcca213d33fb8969b26c9d980
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636049"
---
# <a name="sql-server-error-detail"></a><span data-ttu-id="72e34-102">Dettagli relativi agli errori SQL Server</span><span class="sxs-lookup"><span data-stu-id="72e34-102">SQL Server Error Detail</span></span>
  <span data-ttu-id="72e34-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client definisce l'interfaccia di errore specifica del provider [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="72e34-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the provider-specific error interface [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span> <span data-ttu-id="72e34-104">L'interfaccia restituisce maggiori dettagli relativi agli errori [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e risulta molto utile quando operazioni di esecuzione di comandi o del set di righe non riescono.</span><span class="sxs-lookup"><span data-stu-id="72e34-104">The interface returns more detail about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error and is valuable when command execution or rowset operations fail.</span></span>  
  
 <span data-ttu-id="72e34-105">È possibile accedere all'interfaccia **ISQLServerErrorInfo** in due modi.</span><span class="sxs-lookup"><span data-stu-id="72e34-105">There are two ways to obtain access to **ISQLServerErrorInfo** interface.</span></span>  
  
 <span data-ttu-id="72e34-106">Il consumer può chiamare **IErrorRecords::GetCustomerErrorObject** per ottenere un puntatore **ISQLServerErrorInfo**, come indicato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="72e34-106">The consumer may call **IErrorRecords::GetCustomerErrorObject** to obtain an **ISQLServerErrorInfo** pointer, as shown in the following code sample.</span></span> <span data-ttu-id="72e34-107">Non è necessario ottenere **ISQLErrorInfo.** Sia **ISQLErrorInfo** sia **ISQLServerErrorInfo** sono oggetti errore OLE DB personalizzati, in cui **ISQLServerErrorInfo** rappresenta l'interfaccia da usare per ottenere informazioni sugli errori del server, inclusi dettagli quali i numeri di riga e il nome di procedura.</span><span class="sxs-lookup"><span data-stu-id="72e34-107">(There is no need to obtain **ISQLErrorInfo.**) Both **ISQLErrorInfo** and **ISQLServerErrorInfo** are custom OLE DB error objects, with **ISQLServerErrorInfo** being the interface to use to obtain information of server errors, including such details as procedure name and line numbers.</span></span>  
  
```  
// Get the SQL Server custom error object.  
if(FAILED(hr=pIErrorRecords->GetCustomErrorObject(  
   nRec, IID_ISQLServerErrorInfo,  
   (IUnknown**)&pISQLServerErrorErrorInfo)))  
```  
  
 <span data-ttu-id="72e34-108">Un altro modo per ottenere un puntatore **ISQLServerErrorInfo** consiste nel chiamare il metodo **QueryInterface** su un puntatore **ISQLErrorInfo** già ottenuto.</span><span class="sxs-lookup"><span data-stu-id="72e34-108">Another way to get an **ISQLServerErrorInfo** pointer is to call the **QueryInterface** method on an already-obtained **ISQLErrorInfo** pointer.</span></span> <span data-ttu-id="72e34-109">Dal momento che **ISQLServerErrorInfo** contiene un superset delle informazioni disponibili in **ISQLErrorInfo**, è consigliabile accedere direttamente a **ISQLServerErrorInfo** mediante **GetCustomerErrorObject**.</span><span class="sxs-lookup"><span data-stu-id="72e34-109">Note that because **ISQLServerErrorInfo** contains a superset of the information available from **ISQLErrorInfo**, it makes sense to go directly to **ISQLServerErrorInfo** through **GetCustomerErrorObject**.</span></span>  
  
 <span data-ttu-id="72e34-110">L'interfaccia **ISQLServerErrorInfo** espone una funzione membro, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="72e34-110">The **ISQLServerErrorInfo** interface exposes one member function, [ISQLServerErrorInfo::GetErrorInfo](../native-client-ole-db-interfaces/isqlservererrorinfo-geterrorinfo-ole-db.md).</span></span> <span data-ttu-id="72e34-111">La funzione restituisce un puntatore a una struttura SSERRORINFO e un puntatore a un buffer di stringhe.</span><span class="sxs-lookup"><span data-stu-id="72e34-111">The function returns a pointer to an SSERRORINFO structure and a pointer to a string buffer.</span></span> <span data-ttu-id="72e34-112">Entrambi i puntatori fanno riferimento a una memoria che il consumer deve deallocare usando il metodo **IMalloc::Free**.</span><span class="sxs-lookup"><span data-stu-id="72e34-112">Both pointers reference memory the consumer must deallocate by using the **IMalloc::Free** method.</span></span>  
  
 <span data-ttu-id="72e34-113">I membri di struttura SSERRORINFO vengono interpretati dal consumer come segue.</span><span class="sxs-lookup"><span data-stu-id="72e34-113">SSERRORINFO structure members are interpreted by the consumer as follows.</span></span>  
  
|<span data-ttu-id="72e34-114">Membro</span><span class="sxs-lookup"><span data-stu-id="72e34-114">Member</span></span>|<span data-ttu-id="72e34-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72e34-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="72e34-116">*pwszMessage*</span><span class="sxs-lookup"><span data-stu-id="72e34-116">*pwszMessage*</span></span>|<span data-ttu-id="72e34-117">Messaggio di errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72e34-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span> <span data-ttu-id="72e34-118">Identico alla stringa restituita in **IErrorInfo::GetDescription**.</span><span class="sxs-lookup"><span data-stu-id="72e34-118">Identical to the string returned in **IErrorInfo::GetDescription**.</span></span>|  
|<span data-ttu-id="72e34-119">*pwszServer*</span><span class="sxs-lookup"><span data-stu-id="72e34-119">*pwszServer*</span></span>|<span data-ttu-id="72e34-120">Nome dell'istanza di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] per la sessione.</span><span class="sxs-lookup"><span data-stu-id="72e34-120">Name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the session.</span></span>|  
|<span data-ttu-id="72e34-121">*pwszProcedure*</span><span class="sxs-lookup"><span data-stu-id="72e34-121">*pwszProcedure*</span></span>|<span data-ttu-id="72e34-122">Se appropriato, restituisce il nome della stored procedure in cui ha avuto origine l'errore.</span><span class="sxs-lookup"><span data-stu-id="72e34-122">If appropriate, the name of the procedure in which the error originated.</span></span> <span data-ttu-id="72e34-123">In caso contrario, una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="72e34-123">An empty string otherwise.</span></span>|  
|<span data-ttu-id="72e34-124">*lNative*</span><span class="sxs-lookup"><span data-stu-id="72e34-124">*lNative*</span></span>|<span data-ttu-id="72e34-125">Numero di errore nativo di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72e34-125">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native error number.</span></span> <span data-ttu-id="72e34-126">Identico al valore restituito nel parametro *plNativeError* di **ISQLErrorInfo::GetSQLInfo**.</span><span class="sxs-lookup"><span data-stu-id="72e34-126">Identical to the value returned in the *plNativeError* parameter of **ISQLErrorInfo::GetSQLInfo**.</span></span>|  
|<span data-ttu-id="72e34-127">*bState*</span><span class="sxs-lookup"><span data-stu-id="72e34-127">*bState*</span></span>|<span data-ttu-id="72e34-128">Stato di un messaggio di errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72e34-128">State of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="72e34-129">*bClass*</span><span class="sxs-lookup"><span data-stu-id="72e34-129">*bClass*</span></span>|<span data-ttu-id="72e34-130">Gravità di un messaggio di errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="72e34-130">Severity of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message.</span></span>|  
|<span data-ttu-id="72e34-131">*wLineNumber*</span><span class="sxs-lookup"><span data-stu-id="72e34-131">*wLineNumber*</span></span>|<span data-ttu-id="72e34-132">Quando è applicabile, restituisce il numero di riga di una stored procedure in cui si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="72e34-132">When applicable, the line number of a stored procedure on which the error occurred.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72e34-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72e34-133">See Also</span></span>  
 <span data-ttu-id="72e34-134">[Errori](errors.md) </span><span class="sxs-lookup"><span data-stu-id="72e34-134">[Errors](errors.md) </span></span>  
 [<span data-ttu-id="72e34-135">RAISERROR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="72e34-135">RAISERROR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/raiserror-transact-sql)  
  
  
