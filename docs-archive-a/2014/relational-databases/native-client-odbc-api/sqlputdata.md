---
title: SQLPutData | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPutData function
ms.assetid: d39aaa5b-7fbc-4315-a7f2-5a7787e04f25
author: rothja
ms.author: jroth
ms.openlocfilehash: 31da9c21f9e4323a492a25629a979c66a4f7d365
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87637269"
---
# <a name="sqlputdata"></a><span data-ttu-id="69a3e-102">SQLPutData</span><span class="sxs-lookup"><span data-stu-id="69a3e-102">SQLPutData</span></span>
  <span data-ttu-id="69a3e-103">Quando si usa SQLPutData per inviare più di 65.535 byte di dati (per la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versione 4.21 a) o 400 KB di dati (per SQL Server versione 6,0 e successive) per una colonna SQL_LONGVARCHAR ( `text` ), SQL_WLONGVARCHAR ( `ntext` ) o SQL_LONGVARBINARY (), `image` si applicano le restrizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="69a3e-103">The following restrictions apply when using SQLPutData to send more than 65,535 bytes of data (for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 4.21a) or 400 KB of data (for SQL Server version 6.0 and later) for a SQL_LONGVARCHAR (`text`), SQL_WLONGVARCHAR (`ntext`) or SQL_LONGVARBINARY (`image`) column:</span></span>  
  
-   <span data-ttu-id="69a3e-104">Il parametro a cui si fa riferimento può essere il *insert_Value* in un'istruzione INSERT.</span><span class="sxs-lookup"><span data-stu-id="69a3e-104">The referenced parameter can be the *insert_value* in an INSERT statement.</span></span>  
  
-   <span data-ttu-id="69a3e-105">Il parametro a cui si fa riferimento può essere un' *espressione* nella clausola set di un'istruzione Update.</span><span class="sxs-lookup"><span data-stu-id="69a3e-105">The referenced parameter can be an *expression* in the SET clause of an UPDATE statement.</span></span>  
  
 <span data-ttu-id="69a3e-106">L'annullamento di una sequenza di chiamate SQLPutData che forniscono dati in blocchi a un server che esegue [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comporta un aggiornamento parziale del valore della colonna quando si usa la versione 6,5 o precedente.</span><span class="sxs-lookup"><span data-stu-id="69a3e-106">Canceling a sequence of SQLPutData calls that provide data in blocks to a server running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] causes a partial update of the column's value when using version 6.5 or earlier.</span></span> <span data-ttu-id="69a3e-107">La `text` `ntext` colonna, o `image` a cui è stato fatto riferimento quando è stato chiamato SQLCancel è impostata su un valore di segnaposto intermedio.</span><span class="sxs-lookup"><span data-stu-id="69a3e-107">The `text`, `ntext`, or `image` column that was referenced when SQLCancel was called is set to an intermediate placeholder value.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="69a3e-108">Il driver ODBC di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client non supporta la connessione a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 6.5 e versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="69a3e-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 6.5 and earlier.</span></span>  
  
## <a name="diagnostics"></a><span data-ttu-id="69a3e-109">Diagnostica</span><span class="sxs-lookup"><span data-stu-id="69a3e-109">Diagnostics</span></span>  
 <span data-ttu-id="69a3e-110">Per SQLPutData è disponibile un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQLSTATE specifico di Native Client:</span><span class="sxs-lookup"><span data-stu-id="69a3e-110">There is one [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client specific SQLSTATE for SQLPutData:</span></span>  
  
|<span data-ttu-id="69a3e-111">SQLSTATE</span><span class="sxs-lookup"><span data-stu-id="69a3e-111">SQLSTATE</span></span>|<span data-ttu-id="69a3e-112">Errore</span><span class="sxs-lookup"><span data-stu-id="69a3e-112">Error</span></span>|<span data-ttu-id="69a3e-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69a3e-113">Description</span></span>|  
|--------------|-----------|-----------------|  
|<span data-ttu-id="69a3e-114">22026</span><span class="sxs-lookup"><span data-stu-id="69a3e-114">22026</span></span>|<span data-ttu-id="69a3e-115">Lunghezza dei dati non corrispondente.</span><span class="sxs-lookup"><span data-stu-id="69a3e-115">String data, length mismatch</span></span>|<span data-ttu-id="69a3e-116">Se la lunghezza dei dati in byte da inviare è stata specificata da un'applicazione, ad esempio con SQL_LEN_DATA_AT_EXEC (*n*), dove *n* è maggiore di 0, il numero totale di byte fornito dall'applicazione tramite SQLPutData deve corrispondere alla lunghezza specificata.</span><span class="sxs-lookup"><span data-stu-id="69a3e-116">If the length of data in bytes to be sent has been specified by an application, for example, with SQL_LEN_DATA_AT_EXEC(*n*) where *n* is greater than 0, the total number of bytes given by the application via SQLPutData must match the specified length.</span></span>|  
  
## <a name="sqlputdata-and-table-valued-parameters"></a><span data-ttu-id="69a3e-117">SQLPutData e parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="69a3e-117">SQLPutData and Table-Valued Parameters</span></span>  
 <span data-ttu-id="69a3e-118">SQLPutData viene utilizzato da un'applicazione quando si utilizza l'associazione di righe variabili con parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="69a3e-118">SQLPutData is used by an application when using variable row binding with table-valued parameters.</span></span> <span data-ttu-id="69a3e-119">Il parametro *StrLen_Or_Ind* indica che è possibile che il driver raccolga i dati per la riga o le righe successive dei dati dei parametri con valori di tabella oppure che non siano disponibili altre righe:</span><span class="sxs-lookup"><span data-stu-id="69a3e-119">The *StrLen_Or_Ind* parameter indicates that it is ready for the driver to collect data for the next row or rows of table-valued parameter data, or that no more rows are available:</span></span>  
  
-   <span data-ttu-id="69a3e-120">Un valore maggiore di 0 indica che è disponibile il set di valori di riga successivo.</span><span class="sxs-lookup"><span data-stu-id="69a3e-120">A value greater than 0 indicates that the next set of row values is available.</span></span>  
  
-   <span data-ttu-id="69a3e-121">Il valore 0 indica che non sono disponibili altre righe da inviare.</span><span class="sxs-lookup"><span data-stu-id="69a3e-121">A value of 0 indicates that there are no more rows to be sent.</span></span>  
  
-   <span data-ttu-id="69a3e-122">Qualsiasi valore minore di 0 rappresenta un errore e restituisce un record di diagnostica registrato con SQLState HY090 e il messaggio "Lunghezza di stringa o di buffer non valida".</span><span class="sxs-lookup"><span data-stu-id="69a3e-122">Any value less than 0 is an error and results in a diagnostic record being logged with SQLState HY090 and the messaage "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="69a3e-123">Il parametro *DataPtr* viene ignorato, ma deve essere impostato su un valore non null.</span><span class="sxs-lookup"><span data-stu-id="69a3e-123">The *DataPtr* parameter is ignored, but must be set to a non-NULL value.</span></span> <span data-ttu-id="69a3e-124">Per ulteriori informazioni, vedere la sezione relativa all'associazione di righe di variabile TVP nell' [associazione e trasferimento dati di parametri con valori di tabella e valori di colonna](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span><span class="sxs-lookup"><span data-stu-id="69a3e-124">For more information, see the section on Variable TVP row binding in [Binding and Data Transfer of Table-Valued Parameters and Column Values](../native-client-odbc-table-valued-parameters/binding-and-data-transfer-of-table-valued-parameters-and-column-values.md).</span></span>  
  
 <span data-ttu-id="69a3e-125">Se *StrLen_Or_Ind* ha un valore diverso da SQL_DEFAULT_PARAM o un numero compreso tra 0 e il SQL_PARAMSET_SIZE (ovvero il parametro *ColumnSize* di SQLBindParameter), si tratta di un errore.</span><span class="sxs-lookup"><span data-stu-id="69a3e-125">If *StrLen_Or_Ind* has any value other than SQL_DEFAULT_PARAM or a number between 0 and the SQL_PARAMSET_SIZE (that is, the *ColumnSize* parameter of SQLBindParameter), it is an error.</span></span> <span data-ttu-id="69a3e-126">A causa di questo errore, SQLPutData restituisce SQL_ERROR: SQLSTATE=HY090, "Lunghezza di stringa o di buffer non valida".</span><span class="sxs-lookup"><span data-stu-id="69a3e-126">This error causes SQLPutData to return SQL_ERROR: SQLSTATE=HY090, "Invalid string or buffer length".</span></span>  
  
 <span data-ttu-id="69a3e-127">Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="69a3e-127">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="69a3e-128">Supporto di SQLPutData per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="69a3e-128">SQLPutData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="69a3e-129">I valori dei parametri di tipo data/ora vengono convertiti come descritto in [conversioni da C a SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="69a3e-129">Parameter values of date/time types are converted as described in [Conversions from C to SQL](../native-client-odbc-date-time/datetime-data-type-conversions-from-c-to-sql.md).</span></span>  
  
 <span data-ttu-id="69a3e-130">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="69a3e-130">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlputdata-support-for-large-clr-udts"></a><span data-ttu-id="69a3e-131">Supporto di SQLPutData per i tipi CLR definiti dall'utente di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="69a3e-131">SQLPutData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="69a3e-132">`SQLPutData` supporta i tipi CLR definiti dall'utente di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="69a3e-132">`SQLPutData` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="69a3e-133">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente di grandi dimensioni &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="69a3e-133">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a3e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69a3e-134">See Also</span></span>  
 <span data-ttu-id="69a3e-135">[SQLPutData (funzione)](https://go.microsoft.com/fwlink/?LinkId=59365) </span><span class="sxs-lookup"><span data-stu-id="69a3e-135">[SQLPutData Function](https://go.microsoft.com/fwlink/?LinkId=59365) </span></span>  
 [<span data-ttu-id="69a3e-136">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="69a3e-136">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
