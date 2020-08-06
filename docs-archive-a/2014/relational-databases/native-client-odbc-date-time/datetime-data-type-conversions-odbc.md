---
title: conversioni di tipi di dati DateTime (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- conversions [ODBC]
- bindings [ODBC]
- ODBC, bindings and conversions
ms.assetid: 66b9d282-c88d-40e5-93c2-fd5499a74458
author: rothja
ms.author: jroth
ms.openlocfilehash: 142e4388cb87055ddbc6faa7d5b1a92a627738c2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87635543"
---
# <a name="datetime-data-type-conversions-odbc"></a><span data-ttu-id="16322-102">Conversioni dei tipi di dati datetime (ODBC)</span><span class="sxs-lookup"><span data-stu-id="16322-102">datetime Data Type Conversions (ODBC)</span></span>
  <span data-ttu-id="16322-103">Le conversioni seguenti sono già definite da ODBC o sono un'estensione coerente di ODBC.</span><span class="sxs-lookup"><span data-stu-id="16322-103">The following conversions are either already defined by ODBC or are a consistent extension of ODBC.</span></span> <span data-ttu-id="16322-104">Le conversioni fornite da ogni provider dipendono dalla community servita dal provider, pertanto si può riscontrare la presenza frequente di incoerenze.</span><span class="sxs-lookup"><span data-stu-id="16322-104">The conversions supplied by each provider are determined by the community served by the provider, and there are often inconsistencies between providers as a result.</span></span> <span data-ttu-id="16322-105">I valori tra parentesi quadre sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="16322-105">Values in square brackets are optional.</span></span>  
  
-   <span data-ttu-id="16322-106">Il formato delle stringhe di data e ora è "yyyy-mm-dd[ hh:mm:ss [.9999999][ più/meno hh:mm]]"</span><span class="sxs-lookup"><span data-stu-id="16322-106">The format of datetime strings is 'yyyy-mm-dd[ hh:mm:ss[.9999999][ plus/minus hh:mm]]'</span></span>  
  
-   <span data-ttu-id="16322-107">Il formato delle stringhe dell'ora è "hh:mm:ss [.9999999]"</span><span class="sxs-lookup"><span data-stu-id="16322-107">The format of time strings is 'hh:mm:ss[.9999999]'</span></span>  
  
-   <span data-ttu-id="16322-108">Il formato delle stringhe della data è "yyyy-mm-dd"</span><span class="sxs-lookup"><span data-stu-id="16322-108">The format of date strings is 'yyyy-mm-dd'</span></span>  
  
 <span data-ttu-id="16322-109">Le conversioni dalle stringhe consentono flessibilità nella larghezza degli spazi vuoti e dei campi.</span><span class="sxs-lookup"><span data-stu-id="16322-109">Conversions from strings allow flexibility in white space and field width.</span></span> <span data-ttu-id="16322-110">Per ulteriori informazioni, vedere la sezione "formati di dati: stringhe e valori letterali" del [supporto dei tipi di dati per i miglioramenti di data e ora ODBC](data-type-support-for-odbc-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="16322-110">For more information, see the "Data Formats: Strings and Literals" section of [Data Type Support for ODBC Date and Time Improvements](data-type-support-for-odbc-date-and-time-improvements.md).</span></span>  
  
 <span data-ttu-id="16322-111">Di seguito vengono fornite le regole di conversione generali:</span><span class="sxs-lookup"><span data-stu-id="16322-111">The following are general conversion rules:</span></span>  
  
-   <span data-ttu-id="16322-112">Se l'ora non è presente ma il ricevitore può archiviare l'ora, questa viene impostata su zero.</span><span class="sxs-lookup"><span data-stu-id="16322-112">If no time is present but the receiver can store time, the time is set to zero.</span></span>  
  
-   <span data-ttu-id="16322-113">Se la data non è presente ma il ricevitore può archiviarla, viene utilizzata la data corrente.</span><span class="sxs-lookup"><span data-stu-id="16322-113">If no date is present but the receiver can store date, the current date is used.</span></span>  
  
-   <span data-ttu-id="16322-114">Se nel tipo di dati utilizzato dal client non è presente il fuso orario, ma il server può archiviarlo, la data viene archiviata nel fuso orario del client.</span><span class="sxs-lookup"><span data-stu-id="16322-114">If no timezone is present in the data type that the client is using but the server can store timezone, the date is stored in the client timezone.</span></span> <span data-ttu-id="16322-115">Questo comportamento differisce da quello del server.</span><span class="sxs-lookup"><span data-stu-id="16322-115">Note that this differs from the server behavior.</span></span>  
  
-   <span data-ttu-id="16322-116">Se il fuso orario non è presente nel tipo di server ma è presente nel tipo di client, l'ora viene convertita in formato UTC prima di essere archiviata nel server.</span><span class="sxs-lookup"><span data-stu-id="16322-116">If no timezone is present in the server type but the client type has a timezone, time is converted to UTC before being stored on the server.</span></span>  
  
-   <span data-ttu-id="16322-117">Se l'ora è presente ma il ricevitore non può archiviarla, il componente di ora viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="16322-117">If time is present but the receiver cannot store time, the time component is ignored.</span></span>  
  
-   <span data-ttu-id="16322-118">Se è presente una data ma il ricevitore non può archiviarla, il componente di data viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="16322-118">If a date is present but the receiver cannot store the date, the date component is ignored.</span></span>  
  
-   <span data-ttu-id="16322-119">Se quando si esegue la conversione da C a SQL si verifica il troncamento dei secondi o dei secondi frazionari, viene generato un record di diagnostica con SQLSTATE 22008 e il messaggio "Overflow del campo Datetime".</span><span class="sxs-lookup"><span data-stu-id="16322-119">If truncation of seconds or fractional seconds occurs when converting from C to SQL, a diagnostic record is generated with SQLSTATE 22008 and the message "Datetime field overflow".</span></span>  
  
-   <span data-ttu-id="16322-120">Se quando si esegue la conversione da SQL a C si verifica il troncamento dei secondi o dei secondi frazionari, viene generato un record di diagnostica con SQLSTATE 01S07 e il messaggio "Troncamento frazionario".</span><span class="sxs-lookup"><span data-stu-id="16322-120">If truncation of seconds or fractional seconds occurs when converting from SQL to C, a diagnostic record is generated with SQLSTATE 01S07 and the message "Fractional truncation".</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16322-121">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="16322-121">In This Section</span></span>  
 [<span data-ttu-id="16322-122">Conversioni da tipi di dati C a tipi di dati SQL</span><span class="sxs-lookup"><span data-stu-id="16322-122">Conversions from C to SQL</span></span>](datetime-data-type-conversions-from-c-to-sql.md)  
 <span data-ttu-id="16322-123">Sono elencati i problemi di cui tener conto durante le conversioni dai tipi C ai tipi di dati date/time di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="16322-123">Lists issues to consider when you convert from C types to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types.</span></span>  
  
 [<span data-ttu-id="16322-124">Conversioni dai tipi di dati SQL ai tipi di dati C</span><span class="sxs-lookup"><span data-stu-id="16322-124">Conversions from SQL to C</span></span>](datetime-data-type-conversions-from-sql-to-c.md)  
 <span data-ttu-id="16322-125">Sono elencati i problemi di cui tener conto durante le conversioni dai tipi date/time di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ai tipi C.</span><span class="sxs-lookup"><span data-stu-id="16322-125">Lists issues to consider when you convert from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data/time types to C types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16322-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16322-126">See Also</span></span>  
 [<span data-ttu-id="16322-127">Miglioramenti di data e ora &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="16322-127">Date and Time Improvements &#40;ODBC&#41;</span></span>](date-and-time-improvements-odbc.md)  
  
  
