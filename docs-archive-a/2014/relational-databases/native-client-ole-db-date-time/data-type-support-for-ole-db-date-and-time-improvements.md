---
title: Supporto dei tipi di dati per i miglioramenti relativi a data e ora OLE DB | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB], data type support
- OLE DB, date/time improvements
ms.assetid: d40e3fd6-9057-4371-8236-95cef300603e
author: rothja
ms.author: jroth
ms.openlocfilehash: 834583fdec63a8f613e623c239f9c3a1c9398950
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722735"
---
# <a name="data-type-support-for-ole-db-date-and-time-improvements"></a><span data-ttu-id="69ca0-102">Supporto dei tipi di dati per i miglioramenti relativi a data e ora OLE DB</span><span class="sxs-lookup"><span data-stu-id="69ca0-102">Data Type Support for OLE DB Date and Time Improvements</span></span>
  <span data-ttu-id="69ca0-103">In questo argomento vengono fornite informazioni sui tipi OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) che supportano i tipi di dati di data/ora di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69ca0-103">This topic provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date/time data types.</span></span>  
  
## <a name="data-type-mapping-in-rowsets-and-parameters"></a><span data-ttu-id="69ca0-104">Mapping dei tipi di dati in set di righe e parametri</span><span class="sxs-lookup"><span data-stu-id="69ca0-104">Data Type Mapping in Rowsets and Parameters</span></span>  
 <span data-ttu-id="69ca0-105">OLE DB fornisce due nuovi tipi di dati per supportare i nuovi tipi di server: DBTYPE_DBTIME2 e DBTYPE_DBTIMESTAMPOFFSET.</span><span class="sxs-lookup"><span data-stu-id="69ca0-105">OLE DB provides two new data types to support the new server types: DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET.</span></span> <span data-ttu-id="69ca0-106">Nella tabella seguente viene illustrato il mapping completo per il tipo di server:</span><span class="sxs-lookup"><span data-stu-id="69ca0-106">The following table shows the complete server type mapping:</span></span>  
  
|<span data-ttu-id="69ca0-107">Tipo di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69ca0-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="69ca0-108">Tipo di dati OLE DB</span><span class="sxs-lookup"><span data-stu-id="69ca0-108">OLE DB data type</span></span>|<span data-ttu-id="69ca0-109">Valore</span><span class="sxs-lookup"><span data-stu-id="69ca0-109">Value</span></span>|  
|-----------------------------------------|----------------------|-----------|  
|<span data-ttu-id="69ca0-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="69ca0-110">datetime</span></span>|<span data-ttu-id="69ca0-111">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="69ca0-111">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="69ca0-112">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="69ca0-112">135 (oledb.h)</span></span>|  
|<span data-ttu-id="69ca0-113">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="69ca0-113">smalldatetime</span></span>|<span data-ttu-id="69ca0-114">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="69ca0-114">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="69ca0-115">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="69ca0-115">135 (oledb.h)</span></span>|  
|<span data-ttu-id="69ca0-116">date</span><span class="sxs-lookup"><span data-stu-id="69ca0-116">date</span></span>|<span data-ttu-id="69ca0-117">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="69ca0-117">DBTYPE_DBDATE</span></span>|<span data-ttu-id="69ca0-118">133 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="69ca0-118">133 (oledb.h)</span></span>|  
|<span data-ttu-id="69ca0-119">time</span><span class="sxs-lookup"><span data-stu-id="69ca0-119">time</span></span>|<span data-ttu-id="69ca0-120">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="69ca0-120">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="69ca0-121">145 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="69ca0-121">145 (sqlncli.h)</span></span>|  
|<span data-ttu-id="69ca0-122">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="69ca0-122">datetimeoffset</span></span>|<span data-ttu-id="69ca0-123">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="69ca0-123">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="69ca0-124">146 (sqlncli. h)</span><span class="sxs-lookup"><span data-stu-id="69ca0-124">146 (sqlncli.h)</span></span>|  
|<span data-ttu-id="69ca0-125">datetime2</span><span class="sxs-lookup"><span data-stu-id="69ca0-125">datetime2</span></span>|<span data-ttu-id="69ca0-126">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="69ca0-126">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="69ca0-127">135 (oledb.h)</span><span class="sxs-lookup"><span data-stu-id="69ca0-127">135 (oledb.h)</span></span>|  
  
## <a name="data-formats-strings-and-literals"></a><span data-ttu-id="69ca0-128">Formati di dati: stringhe e valori letterali</span><span class="sxs-lookup"><span data-stu-id="69ca0-128">Data Formats: Strings and Literals</span></span>  
  
|<span data-ttu-id="69ca0-129">Tipo di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69ca0-129">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="69ca0-130">Tipo di dati OLE DB</span><span class="sxs-lookup"><span data-stu-id="69ca0-130">OLE DB data type</span></span>|<span data-ttu-id="69ca0-131">Formato stringa per le conversioni client</span><span class="sxs-lookup"><span data-stu-id="69ca0-131">String format for client conversions</span></span>|  
|-----------------------------------------|----------------------|------------------------------------------|  
|<span data-ttu-id="69ca0-132">Datetime</span><span class="sxs-lookup"><span data-stu-id="69ca0-132">datetime</span></span>|<span data-ttu-id="69ca0-133">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="69ca0-133">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="69ca0-134">'yyyy-mm-dd hh:mm:ss[.999]'</span><span class="sxs-lookup"><span data-stu-id="69ca0-134">'yyyy-mm-dd hh:mm:ss[.999]'</span></span><br /><br /> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="69ca0-135">supporta fino a tre cifre per i secondi frazionari per datetime.</span><span class="sxs-lookup"><span data-stu-id="69ca0-135">supports up to three fractional second digits for Datetime.</span></span>|  
|<span data-ttu-id="69ca0-136">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="69ca0-136">smalldatetime</span></span>|<span data-ttu-id="69ca0-137">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="69ca0-137">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="69ca0-138">'yyyy-mm-dd hh:mm:ss'</span><span class="sxs-lookup"><span data-stu-id="69ca0-138">'yyyy-mm-dd hh:mm:ss'</span></span><br /><br /> <span data-ttu-id="69ca0-139">Questo tipo di dati ha un'accuratezza di un minuto.</span><span class="sxs-lookup"><span data-stu-id="69ca0-139">This data type has an accuracy of one minute.</span></span> <span data-ttu-id="69ca0-140">Il componente dei secondi sarà zero nell'output mentre verrà arrotondato dal server nell'input.</span><span class="sxs-lookup"><span data-stu-id="69ca0-140">The seconds component will be zero on output and will be rounded by the server on input.</span></span>|  
|<span data-ttu-id="69ca0-141">date</span><span class="sxs-lookup"><span data-stu-id="69ca0-141">date</span></span>|<span data-ttu-id="69ca0-142">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="69ca0-142">DBTYPE_DBDATE</span></span>|<span data-ttu-id="69ca0-143">'yyyy-mm-dd'</span><span class="sxs-lookup"><span data-stu-id="69ca0-143">'yyyy-mm-dd'</span></span>|  
|<span data-ttu-id="69ca0-144">time</span><span class="sxs-lookup"><span data-stu-id="69ca0-144">time</span></span>|<span data-ttu-id="69ca0-145">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="69ca0-145">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="69ca0-146">'hh:mm:ss[.9999999]'</span><span class="sxs-lookup"><span data-stu-id="69ca0-146">'hh:mm:ss[.9999999]'</span></span><br /><br /> <span data-ttu-id="69ca0-147">I secondi frazionari possono essere specificati facoltativamente utilizzando fino a sette cifre.</span><span class="sxs-lookup"><span data-stu-id="69ca0-147">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="69ca0-148">datetime2</span><span class="sxs-lookup"><span data-stu-id="69ca0-148">datetime2</span></span>|<span data-ttu-id="69ca0-149">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="69ca0-149">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="69ca0-150">'yyyy-mm-dd hh:mm:ss[.fffffff]'</span><span class="sxs-lookup"><span data-stu-id="69ca0-150">'yyyy-mm-dd hh:mm:ss[.fffffff]'</span></span><br /><br /> <span data-ttu-id="69ca0-151">I secondi frazionari possono essere specificati facoltativamente utilizzando fino a sette cifre.</span><span class="sxs-lookup"><span data-stu-id="69ca0-151">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
|<span data-ttu-id="69ca0-152">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="69ca0-152">datetimeoffset</span></span>|<span data-ttu-id="69ca0-153">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="69ca0-153">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="69ca0-154">'yyyy-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span><span class="sxs-lookup"><span data-stu-id="69ca0-154">'yyyy-mm-dd hh:mm:ss[.fffffff] +/-hh:mm'</span></span><br /><br /> <span data-ttu-id="69ca0-155">I secondi frazionari possono essere specificati facoltativamente utilizzando fino a sette cifre.</span><span class="sxs-lookup"><span data-stu-id="69ca0-155">Fractional seconds can optionally be specified using up to seven digits.</span></span>|  
  
 <span data-ttu-id="69ca0-156">Non vi sono modifiche nelle sequenze di escape per i valori letterali di data/ora.</span><span class="sxs-lookup"><span data-stu-id="69ca0-156">There are no changes to the escape sequences for date/time literals.</span></span>  
  
 <span data-ttu-id="69ca0-157">Per i secondi frazionari nei risultati viene utilizzato un punto (.) anziché i due punti (:).</span><span class="sxs-lookup"><span data-stu-id="69ca0-157">Fractional seconds in results use a dot (.) rather than a colon (:).</span></span>  
  
 <span data-ttu-id="69ca0-158">I valori stringa restituiti alle applicazioni sono sempre della stessa lunghezza per una colonna specifica.</span><span class="sxs-lookup"><span data-stu-id="69ca0-158">String values returned to applications will always be the same length for a given column.</span></span> <span data-ttu-id="69ca0-159">Nei componenti per anno, mese, giorno, ora, minuti e secondi vengono aggiunti con zero iniziali per raggiungere la larghezza massima.</span><span class="sxs-lookup"><span data-stu-id="69ca0-159">Year, month, day, hour, minute, and second components will be padded with leading zeros to their maximum width.</span></span> <span data-ttu-id="69ca0-160">Sarà presente esattamente uno spazio tra la data e l'ora ed esattamente uno spazio tra l'ora e la differenza di fuso orario.</span><span class="sxs-lookup"><span data-stu-id="69ca0-160">There will be exactly one space between date and time and exactly one space between the time and timezone offset.</span></span> <span data-ttu-id="69ca0-161">Una differenza di fuso orario sarà sempre preceduta da un segno.</span><span class="sxs-lookup"><span data-stu-id="69ca0-161">A timezone offset will always be preceded by a sign.</span></span> <span data-ttu-id="69ca0-162">Il segno sarà un più (+) quando la differenza è zero.</span><span class="sxs-lookup"><span data-stu-id="69ca0-162">This sign will be a plus (+) when the offset is zero.</span></span> <span data-ttu-id="69ca0-163">Non verrà aggiunto alcuno spazio vuoto tra il segno e il valore di differenza.</span><span class="sxs-lookup"><span data-stu-id="69ca0-163">There will be no white space between the sign and the offset value.</span></span> <span data-ttu-id="69ca0-164">Se necessario, nei secondi frazionari verranno aggiunti zero finali fino a raggiungere la precisione definita per la colonna, ma non oltre.</span><span class="sxs-lookup"><span data-stu-id="69ca0-164">Fractional seconds will be padded with trailing zeros, if necessary, up to the defined precision for the column, but no further.</span></span> <span data-ttu-id="69ca0-165">Per le colonne di tipo datetime, verranno utilizzate tre cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="69ca0-165">For datetime columns, there will be three fractional seconds digits.</span></span> <span data-ttu-id="69ca0-166">Per le colonne di tipo smalldatetime, non vi saranno cifre per i secondi frazionari e i secondi saranno sempre zero.</span><span class="sxs-lookup"><span data-stu-id="69ca0-166">For smalldatetime columns, there will be no fractional seconds digits and the seconds will always be zero.</span></span>  
  
 <span data-ttu-id="69ca0-167">Le conversioni dai valori stringa forniti dall'applicazione saranno più flessibili e consentiranno la presenza di valori di componente minori della larghezza massima.</span><span class="sxs-lookup"><span data-stu-id="69ca0-167">Conversions from string values provided by the application will be more flexible and will allow component values less than maximum width.</span></span> <span data-ttu-id="69ca0-168">Gli anni possono essere costituiti da una a quattro cifre.</span><span class="sxs-lookup"><span data-stu-id="69ca0-168">Years can be 1-4 digits.</span></span> <span data-ttu-id="69ca0-169">I mesi, i giorni, le ore, i minuti e i secondi possono essere costituiti da una o due cifre.</span><span class="sxs-lookup"><span data-stu-id="69ca0-169">Months, days, hours, minutes, and seconds can be 1 or 2 digits.</span></span> <span data-ttu-id="69ca0-170">Può essere presente uno spazio vuoto arbitrario tra le differenze data/ora e ora/fuso orario.</span><span class="sxs-lookup"><span data-stu-id="69ca0-170">There can be arbitrary white space between date/time and time/timezone offsets.</span></span> <span data-ttu-id="69ca0-171">Il segno utilizzato per una differenza con zero ore e zero minuti può essere un più o un meno.</span><span class="sxs-lookup"><span data-stu-id="69ca0-171">The sign of an offset with zero hours and zero minutes can be plus or minus.</span></span> <span data-ttu-id="69ca0-172">Gli zeri finali sono consentiti per i secondi frazionari fino a un massimo di 9 cifre.</span><span class="sxs-lookup"><span data-stu-id="69ca0-172">Trailing zeros are allowed for fractional seconds up to a maximum of 9 digits.</span></span> <span data-ttu-id="69ca0-173">Un componente per le ore può terminare con un separatore decimale e senza cifre per i secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="69ca0-173">A time component can terminate with a decimal point and no fractional seconds digits.</span></span>  
  
 <span data-ttu-id="69ca0-174">Una stringa vuota non è un valore letterale di data/ora valido e non rappresenta un valore NULL.</span><span class="sxs-lookup"><span data-stu-id="69ca0-174">An empty string is not a valid date/time literal and it does not represent a NULL value.</span></span> <span data-ttu-id="69ca0-175">Un tentativo di convertire una stringa vuota in un valore di data/ora genererà errori con SQLState 22018 e il messaggio "Carattere non valido per la specifica del cast".</span><span class="sxs-lookup"><span data-stu-id="69ca0-175">An attempt to convert an empty string to a date/time value will result in errors with SQLState 22018 and the message "Invalid character value for cast specification".</span></span>  
  
## <a name="data-formats-data-structures"></a><span data-ttu-id="69ca0-176">Formati di dati: strutture di dati</span><span class="sxs-lookup"><span data-stu-id="69ca0-176">Data Formats: Data Structures</span></span>  
 <span data-ttu-id="69ca0-177">Nelle strutture specifiche di OLE DB descritte di seguito a OLE DB si applicano gli stessi vincoli di ODBC.</span><span class="sxs-lookup"><span data-stu-id="69ca0-177">In the OLE DB-specific structures described below, OLE DB conforms to the same constraints as ODBC.</span></span> <span data-ttu-id="69ca0-178">Tali vincoli dipendono dal calendario gregoriano:</span><span class="sxs-lookup"><span data-stu-id="69ca0-178">These are taken from the Gregorian calendar:</span></span>  
  
-   <span data-ttu-id="69ca0-179">L'intervallo per i mesi è compreso tra 1 e 12.</span><span class="sxs-lookup"><span data-stu-id="69ca0-179">Month range is 1 through 12.</span></span>  
  
-   <span data-ttu-id="69ca0-180">L'intervallo per il campo del giorno è compreso tra 1 e il numero di giorni nel mese e deve essere coerente con i campi dell'anno e del mese, considerando gli anni bisestili.</span><span class="sxs-lookup"><span data-stu-id="69ca0-180">Day field range is 1 through the number of days in the month, and must be consistent with year and month fields, taking account of leap years.</span></span>  
  
-   <span data-ttu-id="69ca0-181">L'intervallo delle ore è compreso tra 0 e 23.</span><span class="sxs-lookup"><span data-stu-id="69ca0-181">Hour range is 0 through 23.</span></span>  
  
-   <span data-ttu-id="69ca0-182">L'intervallo dei minuti è compreso tra 0 e 59.</span><span class="sxs-lookup"><span data-stu-id="69ca0-182">Minute range is 0 through 59.</span></span>  
  
-   <span data-ttu-id="69ca0-183">L'intervallo dei secondi è compreso tra 0 e 59,</span><span class="sxs-lookup"><span data-stu-id="69ca0-183">Seconds range from 0 through 59.</span></span> <span data-ttu-id="69ca0-184">consentendo fino a due secondi di compensazione per mantenere la sincronizzazione con l'ora siderale.</span><span class="sxs-lookup"><span data-stu-id="69ca0-184">This allows up to two leap seconds to maintain synchronization with sidereal time.</span></span>  
  
 <span data-ttu-id="69ca0-185">Sono state modificate le implementazioni per le strutture OLE esistenti seguenti in modo da supportare i nuovi tipi di data e ora di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69ca0-185">Implementations for the following existing OLE DB structs have been modified to support the new [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span> <span data-ttu-id="69ca0-186">Le definizioni, tuttavia, non sono state modificate.</span><span class="sxs-lookup"><span data-stu-id="69ca0-186">The definitions, however, have not changed.</span></span>  
  
-   <span data-ttu-id="69ca0-187">DBTYPE_DATE. Si tratta di un tipo DATE di automazione.</span><span class="sxs-lookup"><span data-stu-id="69ca0-187">DBTYPE_DATE (This is an automation DATE type.</span></span> <span data-ttu-id="69ca0-188">Viene rappresentato internamente come `double`.</span><span class="sxs-lookup"><span data-stu-id="69ca0-188">It is internally represented as a `double`..</span></span> <span data-ttu-id="69ca0-189">La parte intera corrisponde al numero di giorni a partire dal 30 dicembre 1899, mentre la parte frazionaria rappresenta una frazione del giorno.</span><span class="sxs-lookup"><span data-stu-id="69ca0-189">The whole part is the number of days since December 30, 1899 and the fractional part is the fraction of a day.</span></span> <span data-ttu-id="69ca0-190">Poiché questo tipo ha un'accuratezza di 1 secondo, dispone di una scala effettiva pari a 0.</span><span class="sxs-lookup"><span data-stu-id="69ca0-190">This type has an accuracy of 1 second, so has an effective scale of 0.)</span></span>  
  
-   <span data-ttu-id="69ca0-191">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="69ca0-191">DBTYPE_DBDATE</span></span>  
  
-   <span data-ttu-id="69ca0-192">DBTYPE_DBTIME</span><span class="sxs-lookup"><span data-stu-id="69ca0-192">DBTYPE_DBTIME</span></span>  
  
-   <span data-ttu-id="69ca0-193">DBTYPE_DBTIMESTAMP. Il campo della frazione è definito da OLE DB come numero di miliardesimi di secondo (nanosecondi) ed è incluso nell'intervallo compreso tra 0 e 999.999.999.</span><span class="sxs-lookup"><span data-stu-id="69ca0-193">DBTYPE_DBTIMESTAMP (the fraction field is defined by OLE DB as the number of billionths of a second (nanoseconds) and ranges from 0-999,999,999)</span></span>  
  
-   <span data-ttu-id="69ca0-194">DBTYPE_FILETIME</span><span class="sxs-lookup"><span data-stu-id="69ca0-194">DBTYPE_FILETIME</span></span>  
  
### <a name="dbtype_dbtime2"></a><span data-ttu-id="69ca0-195">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="69ca0-195">DBTYPE_DBTIME2</span></span>  
 <span data-ttu-id="69ca0-196">In questa struttura è possibile aggiungere fino a 12 byte nei sistemi operativi a 32 bit e a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="69ca0-196">This struct is padded to 12 bytes on both 32-bit and 64-bit operating systems.</span></span>  
  
```  
typedef struct tagDBTIME2 {  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    } DBTIME2;  
```  
  
### <a name="dbtype_-dbtimestampoffset"></a><span data-ttu-id="69ca0-197">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="69ca0-197">DBTYPE_ DBTIMESTAMPOFFSET</span></span>  
  
```  
typedef struct tagDBTIMESTAMPOFFSET {  
    SHORT year;  
    USHORT month;  
    USHORT day;  
    USHORT hour;  
    USHORT minute;  
    USHORT second;  
    ULONG fraction;  
    SHORT timezone_hour;  
    SHORT timezone_minute;  
    } DBTIMESTAMPOFFSET;  
```  
  
 <span data-ttu-id="69ca0-198">Se `timezone_hour` è negativo, `timezone_minute` deve essere negativo o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="69ca0-198">If `timezone_hour` is negative, `timezone_minute` must be negative or zero.</span></span> <span data-ttu-id="69ca0-199">Se `timezone_hour` è positivo, `timezone minute` deve essere positivo o uguale a zero.</span><span class="sxs-lookup"><span data-stu-id="69ca0-199">If `timezone_hour` is positive, `timezone minute` must be positive or zero.</span></span> <span data-ttu-id="69ca0-200">Se `timezone_hour` è zero, `timezone minute` può contenere un valore compreso tra -59 e +59.</span><span class="sxs-lookup"><span data-stu-id="69ca0-200">If `timezone_hour` is zero, `timezone minute` can hold a value between -59 and +59.</span></span>  
  
### <a name="ssvariant"></a><span data-ttu-id="69ca0-201">SSVARIANT</span><span class="sxs-lookup"><span data-stu-id="69ca0-201">SSVARIANT</span></span>  
 <span data-ttu-id="69ca0-202">Questa struttura include ora le nuove strutture DBTYPE_DBTIME2 e DBTYPE_DBTIMESTAMPOFFSET e viene aggiunta una scala di frazioni di secondo per i tipi appropriati.</span><span class="sxs-lookup"><span data-stu-id="69ca0-202">This struct now includes the new structures, DBTYPE_DBTIME2 and DBTYPE_DBTIMESTAMPOFFSET, and adds fractional seconds scale for appropriate types.</span></span>  
  
```  
struct SSVARIANT {  
   SSVARTYPE vt;  
   DWORD dwReserved1;  
   DWORD dwReserved2;  
   union {  
// ...  
      DBTIMESTAMP tsDateTimeVal;  
      DBDATE dDateVal;  
      struct _Time2Val {  
         DBTIME2 tTime2Val;  
         BYTE bScale;  
      } Time2Val;  
      struct _DateTimeVal {  
         DBTIMESTAMP tsDateTimeVal;  
         BYTE bScale;  
      } DateTimeVal;  
      struct _DateTimeOffsetVal {   
         DBTIMESTAMPOFFSET tsoDateTimeOffsetVal;  
         BYTE bScale;  
      } DateTimeOffsetVal;  
// ...  
   };  
};  
```  
  
 <span data-ttu-id="69ca0-203">L'enumerazione associata alla codifica dei tipi SSVARIANT che determina il tipo dell'enumerazione, inoltre, verrà estesa nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="69ca0-203">In addition, the enum associated with SSVARIANT type encoding, which determines the type of the enum, will be extended as follows:</span></span>  
  
```  
enum SQLVARENUM {  
// ...  
   // Datetime  
   VT_SS_DATETIME      = DBTYPE_DBTIMESTAMP,  
   VT_SS_SMALLDATETIME = 206,  
  
   VT_SS_DATE = DBTYPE_DBDATE,  
   VT_SS_TIME2 = DBTYPE_DBTIME2,  
   VT_SS_DATETIME2 = 212  
   VT_SS_DATETIMEOFFSET = DBTYPE_DBTIMESTAMPOFFSET  
};  
```  
  
 <span data-ttu-id="69ca0-204">Le applicazioni che eseguono la migrazione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, che utilizzano `sql_variant` e che si basano sulla precisione limitata di `datetime` dovranno essere aggiornate se lo schema sottostante è aggiornato per l'utilizzo di `datetime2` anziché di `datetime`.</span><span class="sxs-lookup"><span data-stu-id="69ca0-204">Applications migrating to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client that use `sql_variant` and rely on the limited precision of `datetime` will have to be updated if the underlying schema is updated to use `datetime2` rather than `datetime`.</span></span>  
  
 <span data-ttu-id="69ca0-205">Le macro di accesso per SSVARIANT sono state estese anche con l'aggiunta degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="69ca0-205">The access macros for SSVARIANT have also been extended with the addition of the following:</span></span>  
  
```  
#define V_SS_DATETIME2(X)       V_SS_UNION(X, DateTimeVal)  
#define V_SS_TIME2(X)           V_SS_UNION(X, Time2Val)  
#define V_SS_DATE(X)            V_SS_UNION(X, dDateVal)  
#define V_SS_DATETIMEOFFSET(X)  V_SS_UNION(X, DateTimeOffsetVal)  
```  
  
## <a name="data-type-mapping-in-itabledefinitioncreatetable"></a><span data-ttu-id="69ca0-206">Mapping dei tipi di dati in ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="69ca0-206">Data Type Mapping in ITableDefinition::CreateTable</span></span>  
 <span data-ttu-id="69ca0-207">Il mapping dei tipi seguente viene usato con strutture DBCOLUMNDESC usate da ITableDefinition::CreateTable:</span><span class="sxs-lookup"><span data-stu-id="69ca0-207">The following type mapping is used with DBCOLUMNDESC structures used by ITableDefinition::CreateTable:</span></span>  
  
|<span data-ttu-id="69ca0-208">Tipo di dati OLE DB (*wType*)</span><span class="sxs-lookup"><span data-stu-id="69ca0-208">OLE DB data type (*wType*)</span></span>|<span data-ttu-id="69ca0-209">Tipo di dati [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69ca0-209">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type</span></span>|<span data-ttu-id="69ca0-210">Note</span><span class="sxs-lookup"><span data-stu-id="69ca0-210">Notes</span></span>|  
|----------------------------------|-----------------------------------------|-----------|  
|<span data-ttu-id="69ca0-211">DBTYPE_DBDATE</span><span class="sxs-lookup"><span data-stu-id="69ca0-211">DBTYPE_DBDATE</span></span>|<span data-ttu-id="69ca0-212">date</span><span class="sxs-lookup"><span data-stu-id="69ca0-212">date</span></span>||  
|<span data-ttu-id="69ca0-213">DBTYPE_DBTIMESTAMP</span><span class="sxs-lookup"><span data-stu-id="69ca0-213">DBTYPE_DBTIMESTAMP</span></span>|<span data-ttu-id="69ca0-214">`datetime2`(p)</span><span class="sxs-lookup"><span data-stu-id="69ca0-214">`datetime2`(p)</span></span>|<span data-ttu-id="69ca0-215">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client controlla il membro *BSCALE* di DBCOLUMDESC per determinare la precisione dei secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="69ca0-215">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="69ca0-216">DBTYPE_DBTIME2</span><span class="sxs-lookup"><span data-stu-id="69ca0-216">DBTYPE_DBTIME2</span></span>|<span data-ttu-id="69ca0-217">`time`(p)</span><span class="sxs-lookup"><span data-stu-id="69ca0-217">`time`(p)</span></span>|<span data-ttu-id="69ca0-218">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client controlla il membro *BSCALE* di DBCOLUMDESC per determinare la precisione dei secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="69ca0-218">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
|<span data-ttu-id="69ca0-219">DBTYPE_DBTIMESTAMPOFFSET</span><span class="sxs-lookup"><span data-stu-id="69ca0-219">DBTYPE_DBTIMESTAMPOFFSET</span></span>|<span data-ttu-id="69ca0-220">`datetimeoffset`(p)</span><span class="sxs-lookup"><span data-stu-id="69ca0-220">`datetimeoffset`(p)</span></span>|<span data-ttu-id="69ca0-221">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provider di OLE DB di Native Client controlla il membro *BSCALE* di DBCOLUMDESC per determinare la precisione dei secondi frazionari.</span><span class="sxs-lookup"><span data-stu-id="69ca0-221">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider inspects the DBCOLUMDESC *bScale* member to determine the fractional seconds precision.</span></span>|  
  
 <span data-ttu-id="69ca0-222">Quando un'applicazione specifica DBTYPE_DBTIMESTAMP in *wType*, è possibile eseguire l'override del mapping a `datetime2` fornendo un nome di tipo in *pwszTypeName*.</span><span class="sxs-lookup"><span data-stu-id="69ca0-222">When an application specifies DBTYPE_DBTIMESTAMP in *wType*, it can override the mapping to `datetime2` by supplying a type name in *pwszTypeName*.</span></span> <span data-ttu-id="69ca0-223">Se `datetime` si specifica, *bScale* deve essere 3.</span><span class="sxs-lookup"><span data-stu-id="69ca0-223">If `datetime` is specified, *bScale* must be 3.</span></span> <span data-ttu-id="69ca0-224">Se `smalldatetime` si specifica, *bScale* deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="69ca0-224">If `smalldatetime` is specified, *bScale* must be 0.</span></span> <span data-ttu-id="69ca0-225">Se *bScale* non è coerente con *wType* e *pwszTypeName*, viene restituito DB_E_BADSCALE.</span><span class="sxs-lookup"><span data-stu-id="69ca0-225">If *bScale* is not consistent with *wType* and *pwszTypeName*,DB_E_BADSCALE is returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69ca0-226">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69ca0-226">See Also</span></span>  
 [<span data-ttu-id="69ca0-227">Miglioramenti relativi a data e ora &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="69ca0-227">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
