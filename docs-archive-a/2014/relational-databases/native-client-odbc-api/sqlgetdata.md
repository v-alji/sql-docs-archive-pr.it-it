---
title: SQLGetData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetData function
ms.assetid: 204848be-8787-45b4-816f-a60ac9d56fcf
author: rothja
ms.author: jroth
ms.openlocfilehash: c351cf7340bc7b0afeb76b139bd75aa429f56e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87623249"
---
# <a name="sqlgetdata"></a><span data-ttu-id="a271b-102">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="a271b-102">SQLGetData</span></span>
  <span data-ttu-id="a271b-103">**SQLGetData** viene utilizzato per recuperare i dati del set di risultati senza associare i valori della colonna.</span><span class="sxs-lookup"><span data-stu-id="a271b-103">**SQLGetData** is used to retrieve result set data without binding column values.</span></span> <span data-ttu-id="a271b-104">**SQLGetData** può essere chiamato successivamente nella stessa colonna per recuperare grandi quantità di dati da una colonna con un tipo di dati **Text**, **ntext**o **Image** .</span><span class="sxs-lookup"><span data-stu-id="a271b-104">**SQLGetData** can be called successively on the same column to retrieve large amounts of data from a column with a **text**, **ntext**, or **image** data type.</span></span>  
  
 <span data-ttu-id="a271b-105">Non è necessario che un'applicazione associ le variabili per recuperare i dati del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a271b-105">There is no requirement that an application bind variables to fetch result set data.</span></span> <span data-ttu-id="a271b-106">È possibile recuperare i dati di qualsiasi colonna dal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client utilizzando **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="a271b-106">The data of any column can be retrieved from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by using **SQLGetData**.</span></span>  
  
 <span data-ttu-id="a271b-107">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native client non supporta l'utilizzo di **SQLGetData** per recuperare dati in ordine di colonna casuale.</span><span class="sxs-lookup"><span data-stu-id="a271b-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using **SQLGetData** to retrieve data in random column order.</span></span> <span data-ttu-id="a271b-108">Tutte le colonne non associate elaborate con **SQLGetData** devono avere un numero ordinale di colonna maggiore rispetto alle colonne associate nel set di risultati.</span><span class="sxs-lookup"><span data-stu-id="a271b-108">All unbound columns processed with **SQLGetData** must have higher column ordinals than the bound columns in the result set.</span></span> <span data-ttu-id="a271b-109">L'applicazione deve elaborare i dati dal valore della colonna dell'ordinale non associato più basso al più elevato.</span><span class="sxs-lookup"><span data-stu-id="a271b-109">The application must process data from the lowest unbound ordinal column value to the highest.</span></span> <span data-ttu-id="a271b-110">Il tentativo di recuperare dati dalla colonna con una numerazione di ordinali più bassa genera un errore.</span><span class="sxs-lookup"><span data-stu-id="a271b-110">Attempting to retrieve data from a lower ordinally numbered column results in an error.</span></span> <span data-ttu-id="a271b-111">Se l'applicazione sta utilizzando i cursori del server per indicare le righe del set di risultati, può recuperare nuovamente la riga corrente e quindi recuperare il valore di una colonna.</span><span class="sxs-lookup"><span data-stu-id="a271b-111">If the application is using server cursors to report result set rows, the application can refetch the current row and then fetch the value of a column.</span></span> <span data-ttu-id="a271b-112">Se un'istruzione viene eseguita sul cursore di sola lettura predefinito, è necessario eseguire di nuovo l'istruzione per eseguire il backup di **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="a271b-112">If a statement is executed on the default read-only, forward-only cursor, you must re-execute the statement to back up **SQLGetData**.</span></span>  
  
 <span data-ttu-id="a271b-113">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client restituisce accuratamente la lunghezza dei dati di tipo **Text**, **ntext**e **Image** recuperati utilizzando **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="a271b-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver accurately reports the length of **text**, **ntext**, and **image** data retrieved using **SQLGetData**.</span></span> <span data-ttu-id="a271b-114">L'applicazione può avvalersi del *StrLen_or_IndPtr* parametro return per recuperare rapidamente i dati lunghi.</span><span class="sxs-lookup"><span data-stu-id="a271b-114">The application can make good use of the *StrLen_or_IndPtr* parameter return to retrieve long data rapidly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a271b-115">Per i tipi di valore di grandi dimensioni, *StrLen_or_IndPtr* restituirà SQL_NO_TOTAL in caso di troncamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="a271b-115">For large value types, *StrLen_or_IndPtr* will return SQL_NO_TOTAL in cases of data truncation.</span></span>  
  
## <a name="sqlgetdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="a271b-116">Supporto di SQLGetData per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="a271b-116">SQLGetData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="a271b-117">I valori della colonna dei risultati dei tipi data/ora vengono convertiti come descritto in [conversioni da SQL a C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="a271b-117">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="a271b-118">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a271b-118">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgetdata-support-for-large-clr-udts"></a><span data-ttu-id="a271b-119">Supporto di SQLGetData per tipi definiti dall'utente CLR di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="a271b-119">SQLGetData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="a271b-120">**SQLGetData** supporta i tipi CLR definiti dall'utente di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="a271b-120">**SQLGetData** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="a271b-121">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente di grandi dimensioni &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a271b-121">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a271b-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="a271b-122">Example</span></span>  
  
```  
SQLHDBC     hDbc = NULL;  
SQLHSTMT    hStmt = NULL;  
long        lEmpID;  
PBYTE       pPicture;  
SQLINTEGER  pIndicators[2];  
  
// Get an environment, connection, and so on.  
...  
  
// Get a statement handle and execute a command.  
SQLAllocHandle(SQL_HANDLE_STMT, hDbc, &hStmt);  
  
if (SQLExecDirect(hStmt,  
    (SQLCHAR*) "SELECT EmployeeID, Photo FROM Employees",  
    SQL_NTS) == SQL_ERROR)  
    {  
    // Handle error and return.  
    }  
  
// Retrieve data from row set.  
SQLBindCol(hStmt, 1, SQL_C_LONG, (SQLPOINTER) &lEmpID, sizeof(long),  
    &pIndicators[0]);  
  
while (SQLFetch(hStmt) == SQL_SUCCESS)  
    {  
    cout << "EmployeeID: " << lEmpID << "\n";  
  
    // Call SQLGetData to determine the amount of data that's waiting.  
    if (SQLGetData(hStmt, 2, SQL_C_BINARY, pPicture, 0, &pIndicators[1])  
        == SQL_SUCCESS_WITH_INFO)  
        {  
        cout << "Photo size: " pIndicators[1] << "\n\n";  
  
        // Get all the data at once.  
        pPicture = new BYTE[pIndicators[1]];  
        if (SQLGetData(hStmt, 2, SQL_C_DEFAULT, pPicture,  
            pIndicators[1], &pIndicators[1]) != SQL_SUCCESS)  
            {  
            // Handle error and continue.  
            }  
  
        delete [] pPicture;  
        }  
    else  
        {  
        // Handle error on attempt to get data length.  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="a271b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a271b-123">See Also</span></span>  
 <span data-ttu-id="a271b-124">[Funzione SQLGetData](https://go.microsoft.com/fwlink/?LinkId=59350) </span><span class="sxs-lookup"><span data-stu-id="a271b-124">[SQLGetData Function](https://go.microsoft.com/fwlink/?LinkId=59350) </span></span>  
 [<span data-ttu-id="a271b-125">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="a271b-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
