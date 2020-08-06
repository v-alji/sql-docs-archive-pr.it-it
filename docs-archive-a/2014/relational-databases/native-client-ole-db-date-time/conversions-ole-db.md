---
title: Associazioni e conversioni (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- conversions [OLE DB]
- bindings [OLE DB]
- OLE DB, bindings and conversions
ms.assetid: c187df58-a8c8-4c74-a76f-663abbc5f0c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 95c73bdad80b5f948a45235ad208ab307fcceff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87636716"
---
# <a name="bindings-and-conversions-ole-db"></a><span data-ttu-id="d99b3-102">Associazioni e conversioni (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="d99b3-102">Bindings and Conversions (OLE DB)</span></span>
  <span data-ttu-id="d99b3-103">In questa sezione viene descritto come eseguire conversioni tra valori `datetime` e `datetimeoffset`.</span><span class="sxs-lookup"><span data-stu-id="d99b3-103">This section discusses how to convert between `datetime` and `datetimeoffset` values.</span></span> <span data-ttu-id="d99b3-104">Le conversioni descritte in questa sezione sono già disponibili in OLE DB o costituiscono un'estensione coerente di OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d99b3-104">The conversions described in this section are either already provided by OLE DB or are a consistent extension of OLE DB.</span></span>  
  
 <span data-ttu-id="d99b3-105">Il formato di valori letterali e stringhe per date e ore in OLE DB segue in genere lo standard ISO e non dipende dalle impostazioni locali del client.</span><span class="sxs-lookup"><span data-stu-id="d99b3-105">The format of literals and strings for dates and times in OLE DB generally follows ISO, and is not dependent on the client locale.</span></span> <span data-ttu-id="d99b3-106">Un'eccezione è rappresentata da DBTYPE_DATE, che utilizza come standard l'automazione OLE.</span><span class="sxs-lookup"><span data-stu-id="d99b3-106">One exception is DBTYPE_DATE, where the standard is OLE Automation.</span></span> <span data-ttu-id="d99b3-107">Poiché, tuttavia, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client esegue conversioni tra tipi solo quando i dati vengono trasmessi al o dal client, un'applicazione non può forzare in alcun modo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client per eseguire conversioni tra DBTYPE_DATE e formati stringa.</span><span class="sxs-lookup"><span data-stu-id="d99b3-107">However, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client only converts between types when data is transmitted to or from the client, there is no way for an application to force [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client to convert between DBTYPE_DATE and string formats.</span></span> <span data-ttu-id="d99b3-108">In caso contrario, le stringhe utilizzano i formati indicati di seguito. Il testo tra parentesi indica un elemento facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d99b3-108">Otherwise, strings use the following formats (text in brackets indicates an optional element):</span></span>  
  
-   <span data-ttu-id="d99b3-109">Formato delle stringhe `datetime` e `datetimeoffset`:</span><span class="sxs-lookup"><span data-stu-id="d99b3-109">The format of `datetime` and `datetimeoffset` strings is:</span></span>  
  
     <span data-ttu-id="d99b3-110">*aaaa* - *mm* - *DD*[ *HH*:*mm*:*SS*[.\* 9999999\*] [??</span><span class="sxs-lookup"><span data-stu-id="d99b3-110">*yyyy*-*mm*-*dd*[ *hh*:*mm*:*ss*[.*9999999*][ ??</span></span> <span data-ttu-id="d99b3-111">*HH*:*mm*]]</span><span class="sxs-lookup"><span data-stu-id="d99b3-111">*hh*:*mm*]]</span></span>  
  
-   <span data-ttu-id="d99b3-112">Formato delle stringhe `time`:</span><span class="sxs-lookup"><span data-stu-id="d99b3-112">The format of `time` strings is:</span></span>  
  
     <span data-ttu-id="d99b3-113">*hh*:*mm*:*ss*[.*9999999*]</span><span class="sxs-lookup"><span data-stu-id="d99b3-113">*hh*:*mm*:*ss*[.*9999999*]</span></span>  
  
-   <span data-ttu-id="d99b3-114">Formato delle stringhe `date`:</span><span class="sxs-lookup"><span data-stu-id="d99b3-114">The format of `date` strings is:</span></span>  
  
     <span data-ttu-id="d99b3-115">*aaaa*-*mm*-*gg*</span><span class="sxs-lookup"><span data-stu-id="d99b3-115">*yyyy*-*mm*-*dd*</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d99b3-116">Le versioni precedenti di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client e SQLOLEDB implementano conversioni OLE se le conversioni standard non vengono eseguite correttamente.</span><span class="sxs-lookup"><span data-stu-id="d99b3-116">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client and SQLOLEDB implemented OLE conversions, in case standard conversions failed.</span></span> <span data-ttu-id="d99b3-117">Di conseguenza, alcune conversioni eseguite in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 e versioni successive differiscono dalla specifica OLE DB.</span><span class="sxs-lookup"><span data-stu-id="d99b3-117">As a result, some conversions performed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 10.0 and later differ from the OLE DB specification.</span></span>  
  
 <span data-ttu-id="d99b3-118">Le conversioni dalle stringhe consentono flessibilità nella larghezza degli spazi vuoti e dei campi.</span><span class="sxs-lookup"><span data-stu-id="d99b3-118">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="d99b3-119">Per ulteriori informazioni, vedere la sezione "formati di dati: stringhe e valori letterali" in [supporto dei tipi di dati per OLE DB miglioramenti di data e ora](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="d99b3-119">For more information, see the "Data Formats: Strings and Literals" section in [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="d99b3-120">Di seguito vengono fornite le regole di conversione generali:</span><span class="sxs-lookup"><span data-stu-id="d99b3-120">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="d99b3-121">Quando una stringa viene convertita in un tipo di data/ora, la stringa viene prima analizzata come valore letterale ISO.</span><span class="sxs-lookup"><span data-stu-id="d99b3-121">When a string is converted to a date/time type, the string is first parsed as an ISO literal.</span></span> <span data-ttu-id="d99b3-122">Se l'operazione ha esito negativo, la stringa viene analizzata come valore letterale di data OLE, che include componenti per l'ora.</span><span class="sxs-lookup"><span data-stu-id="d99b3-122">If this fails, the string is parsed as an OLE date literal, which has time components.</span></span>  
  
-   <span data-ttu-id="d99b3-123">Se l'ora non è presente ma il ricevitore può archiviare l'ora, questa viene impostata su zero.</span><span class="sxs-lookup"><span data-stu-id="d99b3-123">If no time is present but the receiver can store time, the time is set to zero.</span></span> <span data-ttu-id="d99b3-124">Se la data non è presente ma il ricevitore può archiviare la data, questa viene impostata sulla data corrente quando si utilizzano conversioni ISO e su 1899-12-30 quando si utilizzano conversioni OLE.</span><span class="sxs-lookup"><span data-stu-id="d99b3-124">If no date is present but the receiver can store a date, the date is set to the current date when ISO conversions are used and to 1899-12-30 when OLE conversions are used.</span></span>  
  
-   <span data-ttu-id="d99b3-125">Se nel tipo di dati utilizzato dal client non è presente il fuso orario, ma il server può archiviare il fuso orario, la data nel client viene considerata nel fuso orario utilizzato dal client stesso.</span><span class="sxs-lookup"><span data-stu-id="d99b3-125">If no timezone is present in the data type that the client is using, but the server can store timezone, the data on the client is assumed to be in the client timezone.</span></span>  
  
-   <span data-ttu-id="d99b3-126">Se nel server non è presente il fuso orario ma il client dispone di informazioni sul fuso orario, viene presupposto il fuso orario UTC.</span><span class="sxs-lookup"><span data-stu-id="d99b3-126">If no timezone is present at the server but the client has timezone information, the UTC timezone is assumed.</span></span> <span data-ttu-id="d99b3-127">Questo comportamento differisce da quello del server.</span><span class="sxs-lookup"><span data-stu-id="d99b3-127">This differs from server behavior.</span></span>  
  
-   <span data-ttu-id="d99b3-128">Se l'ora è presente ma il ricevitore non può archiviare l'ora, il componente per l'ora viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="d99b3-128">If the time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="d99b3-129">Se la data è presente ma il ricevitore non può archiviare la data, il componente per la data viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="d99b3-129">If the date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="d99b3-130">Se si verifica un troncamento di secondi o di secondi frazionari durante la conversione dal client al server, viene restituito DB_E_ERRORSOCCURRED e viene impostato lo stato DBSTATUS_E_DATAOVERFLOW.</span><span class="sxs-lookup"><span data-stu-id="d99b3-130">If truncation of seconds or fractional seconds occurs when converting from client to server, DB_E_ERRORSOCCURRED is returned and the status DBSTATUS_E_DATAOVERFLOW is set.</span></span>  
  
-   <span data-ttu-id="d99b3-131">Se si verifica un troncamento di secondi o di secondi frazionari durante la conversione dal server al client, viene impostato lo stato DBSTATUS_S_TRUNCATED.</span><span class="sxs-lookup"><span data-stu-id="d99b3-131">If truncation of seconds or fractional seconds occurs when converting from server to client, DBSTATUS_S_TRUNCATED is set</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d99b3-132">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d99b3-132">In This Section</span></span>  
 [<span data-ttu-id="d99b3-133">Conversioni eseguite da client a server</span><span class="sxs-lookup"><span data-stu-id="d99b3-133">Conversions Performed from Client to Server</span></span>](conversions-performed-from-client-to-server.md)  
 <span data-ttu-id="d99b3-134">Vengono descritte le conversioni di data/ora eseguite tra un'applicazione client scritta con la specifica OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client e [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="d99b3-134">Describes date/time conversions performed between a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later).</span></span>  
  
 [<span data-ttu-id="d99b3-135">Conversioni eseguite da server a client</span><span class="sxs-lookup"><span data-stu-id="d99b3-135">Conversions Performed from Server to Client</span></span>](conversions-performed-from-server-to-client.md)  
 <span data-ttu-id="d99b3-136">Vengono descritte le conversioni di data/ora eseguite tra [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (o versione successiva) e un'applicazione client scritta con la specifica OLE DB di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="d99b3-136">Describes date/time conversions performed between [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later) and a client application written with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99b3-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d99b3-137">See Also</span></span>  
 [<span data-ttu-id="d99b3-138">Miglioramenti relativi a data e ora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="d99b3-138">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
