---
title: Informazioni nelle interfacce di errore | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: rothja
ms.author: jroth
ms.openlocfilehash: e9859ccbd804ba15685d84b98cbe74d4b096d98c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636054"
---
# <a name="information-in-error-interfaces"></a><span data-ttu-id="44a30-102">Informazioni nelle interfacce di errore</span><span class="sxs-lookup"><span data-stu-id="44a30-102">Information in Error Interfaces</span></span>
  <span data-ttu-id="44a30-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client segnala alcune informazioni sugli errori e sullo stato nelle interfacce di errore definite dall'OLE DB **IErrorInfo**, **IErrorRecords**e **ISQLErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="44a30-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reports some error and status information in the OLE DB-defined error interfaces **IErrorInfo**, **IErrorRecords**, and **ISQLErrorInfo**.</span></span>  
  
 <span data-ttu-id="44a30-104">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta le funzioni membro **IErrorInfo** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="44a30-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IErrorInfo** member functions as follows.</span></span>  
  
|<span data-ttu-id="44a30-105">Funzione membro</span><span class="sxs-lookup"><span data-stu-id="44a30-105">Member function</span></span>|<span data-ttu-id="44a30-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a30-106">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="44a30-107">**GetDescription**</span><span class="sxs-lookup"><span data-stu-id="44a30-107">**GetDescription**</span></span>|<span data-ttu-id="44a30-108">Stringa descrittiva del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="44a30-108">Descriptive error message string.</span></span>|  
|<span data-ttu-id="44a30-109">**GetGUID**</span><span class="sxs-lookup"><span data-stu-id="44a30-109">**GetGUID**</span></span>|<span data-ttu-id="44a30-110">GUID dell'interfaccia che ha definito l'errore.</span><span class="sxs-lookup"><span data-stu-id="44a30-110">GUID of the interface that defined the error.</span></span>|  
|<span data-ttu-id="44a30-111">**GetHelpContext**</span><span class="sxs-lookup"><span data-stu-id="44a30-111">**GetHelpContext**</span></span>|<span data-ttu-id="44a30-112">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="44a30-112">Not supported.</span></span> <span data-ttu-id="44a30-113">Restituisce sempre zero.</span><span class="sxs-lookup"><span data-stu-id="44a30-113">Always returns zero.</span></span>|  
|<span data-ttu-id="44a30-114">**GetHelpFile**</span><span class="sxs-lookup"><span data-stu-id="44a30-114">**GetHelpFile**</span></span>|<span data-ttu-id="44a30-115">Non supportato.</span><span class="sxs-lookup"><span data-stu-id="44a30-115">Not supported.</span></span> <span data-ttu-id="44a30-116">Viene restituito sempre NULL.</span><span class="sxs-lookup"><span data-stu-id="44a30-116">Always returns NULL.</span></span>|  
|<span data-ttu-id="44a30-117">**GetSource**</span><span class="sxs-lookup"><span data-stu-id="44a30-117">**GetSource**</span></span>|<span data-ttu-id="44a30-118">Stringa "Microsoft SQL Server Native Client".</span><span class="sxs-lookup"><span data-stu-id="44a30-118">String "Microsoft SQL Server Native Client".</span></span>|  
  
 <span data-ttu-id="44a30-119">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta le funzioni membro **IErrorRecords** disponibili per il consumer come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="44a30-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports consumer-available **IErrorRecords** member functions as follows.</span></span>  
  
|<span data-ttu-id="44a30-120">Funzione membro</span><span class="sxs-lookup"><span data-stu-id="44a30-120">Member function</span></span>|<span data-ttu-id="44a30-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a30-121">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="44a30-122">**GetBasicErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="44a30-122">**GetBasicErrorInfo**</span></span>|<span data-ttu-id="44a30-123">Inserisce in una struttura ERRORINFO le informazioni di base su un errore.</span><span class="sxs-lookup"><span data-stu-id="44a30-123">Fills an ERRORINFO structure with basic information about an error.</span></span> <span data-ttu-id="44a30-124">Una struttura ERRORINFO contiene membri che identificano il valore restituito HRESULT per l'errore nonché il provider e l'interfaccia alle quali si applica l'errore.</span><span class="sxs-lookup"><span data-stu-id="44a30-124">An ERRORINFO structure contains members that identify the HRESULT return value for the error, and the provider and interface to which the error applies.</span></span>|  
|<span data-ttu-id="44a30-125">**GetCustomErrorObject**</span><span class="sxs-lookup"><span data-stu-id="44a30-125">**GetCustomErrorObject**</span></span>|<span data-ttu-id="44a30-126">Restituisce un riferimento nelle interfacce **ISQLErrorInfo** e [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="44a30-126">Returns a reference on interfaces **ISQLErrorInfo,** and [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span>|  
|<span data-ttu-id="44a30-127">**GetErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="44a30-127">**GetErrorInfo**</span></span>|<span data-ttu-id="44a30-128">Restituisce un riferimento in un'interfaccia **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="44a30-128">Returns a reference on an **IErrorInfo** interface.</span></span>|  
|<span data-ttu-id="44a30-129">**GetErrorParameters**</span><span class="sxs-lookup"><span data-stu-id="44a30-129">**GetErrorParameters**</span></span>|<span data-ttu-id="44a30-130">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native client non restituisce parametri al consumer tramite **GetErrorParameters**.</span><span class="sxs-lookup"><span data-stu-id="44a30-130">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not return parameters to the consumer through **GetErrorParameters**.</span></span>|  
|<span data-ttu-id="44a30-131">**GetRecordCount**</span><span class="sxs-lookup"><span data-stu-id="44a30-131">**GetRecordCount**</span></span>|<span data-ttu-id="44a30-132">Conteggio dei record di errore disponibili.</span><span class="sxs-lookup"><span data-stu-id="44a30-132">Count of error records available.</span></span>|  
  
 <span data-ttu-id="44a30-133">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client supporta i parametri **ISQLErrorInfo:: GetSQLInfo** come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="44a30-133">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ISQLErrorInfo::GetSQLInfo** parameters as follows.</span></span>  
  
|<span data-ttu-id="44a30-134">Parametro</span><span class="sxs-lookup"><span data-stu-id="44a30-134">Parameter</span></span>|<span data-ttu-id="44a30-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44a30-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44a30-136">*pbstrSQLState*</span><span class="sxs-lookup"><span data-stu-id="44a30-136">*pbstrSQLState*</span></span>|<span data-ttu-id="44a30-137">Restituisce un valore SQLSTATE per l'errore.</span><span class="sxs-lookup"><span data-stu-id="44a30-137">Returns a SQLSTATE value for the error.</span></span> <span data-ttu-id="44a30-138">I valori SQLSTATE vengono definiti nelle specifiche API, SQL-92, ODBC e ISO SQL.</span><span class="sxs-lookup"><span data-stu-id="44a30-138">SQLSTATE values are defined in the SQL-92, ODBC and ISO SQL, and API specifications.</span></span> <span data-ttu-id="44a30-139">Né [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] né [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native client OLE DB provider definiscono valori SQLSTATE specifici dell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="44a30-139">Neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defined implementation-specific SQLSTATE values.</span></span>|  
|<span data-ttu-id="44a30-140">*plNativeError*</span><span class="sxs-lookup"><span data-stu-id="44a30-140">*plNativeError*</span></span>|<span data-ttu-id="44a30-141">Restituisce il numero di errore di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da **master.dbo.sysmessages**, quando disponibile.</span><span class="sxs-lookup"><span data-stu-id="44a30-141">Returns the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number from **master.dbo.sysmessages** when available.</span></span> <span data-ttu-id="44a30-142">Gli errori nativi sono disponibili dopo un tentativo riuscito di inizializzare un' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] origine dati del provider OLE DB di Native Client.</span><span class="sxs-lookup"><span data-stu-id="44a30-142">Native errors are available after a successful attempt to initialize a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source.</span></span> <span data-ttu-id="44a30-143">Prima del tentativo, il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client restituisce sempre zero.</span><span class="sxs-lookup"><span data-stu-id="44a30-143">Prior to the attempt, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider always returns zero.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44a30-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44a30-144">See Also</span></span>  
 [<span data-ttu-id="44a30-145">Errori</span><span class="sxs-lookup"><span data-stu-id="44a30-145">Errors</span></span>](errors.md)  
  
  
