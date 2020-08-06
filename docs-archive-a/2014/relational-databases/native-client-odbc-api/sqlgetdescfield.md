---
title: SQLGetDescField | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetDescField function
ms.assetid: 3e59a37a-28ee-4c91-8968-7fe3b966739d
author: rothja
ms.author: jroth
ms.openlocfilehash: 4538396dbfb5406d0464c4730c1f6f3bd5882799
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "87629810"
---
# <a name="sqlgetdescfield"></a><span data-ttu-id="0192c-102">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="0192c-102">SQLGetDescField</span></span>
  <span data-ttu-id="0192c-103">Il [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC di Native Client espone solo i campi di descrizione specifici del driver per il descrittore della riga di implementazione (IRD).</span><span class="sxs-lookup"><span data-stu-id="0192c-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver exposes driver-specific descriptor fields for the implementation row descriptor (IRD) only.</span></span> <span data-ttu-id="0192c-104">All'interno di IRD, ai [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] campi del descrittore viene fatto riferimento tramite attributi di colonna specifici del driver.</span><span class="sxs-lookup"><span data-stu-id="0192c-104">Within the IRD, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] descriptor fields are referenced through driver-specific column attributes.</span></span> <span data-ttu-id="0192c-105">Per informazioni su un elenco completo dei campi di descrizione specifici del driver disponibili, vedere [SQLColAttribute](sqlcolattribute.md).</span><span class="sxs-lookup"><span data-stu-id="0192c-105">For information about a complete list of available driver-specific descriptor fields, see [SQLColAttribute](sqlcolattribute.md).</span></span>  
  
 <span data-ttu-id="0192c-106">I campi di descrizione che contengono stringhe dell'identificatore di colonna sono spesso stringhe di lunghezza zero.</span><span class="sxs-lookup"><span data-stu-id="0192c-106">Descriptor fields that contain column identifier strings are often zero-length strings.</span></span> <span data-ttu-id="0192c-107">Tutti i valori dei campi di descrizione specifici di [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sono di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="0192c-107">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-specific descriptor field values are read-only.</span></span>  
  
 <span data-ttu-id="0192c-108">Come gli attributi recuperati con SQLColAttribute, i campi di descrizione che segnalano gli attributi a livello di riga (ad esempio SQL_CA_SS_COMPUTE_ID) vengono segnalati per tutte le colonne del set di risultati.</span><span class="sxs-lookup"><span data-stu-id="0192c-108">Like attributes retrieved with SQLColAttribute, descriptor fields that report row-level attributes (such as SQL_CA_SS_COMPUTE_ID) are reported for all columns in the result set.</span></span>  
  
## <a name="sqlgetdescfield-and-table-valued-parameters"></a><span data-ttu-id="0192c-109">SQLGetDescField e parametri con valori di tabella</span><span class="sxs-lookup"><span data-stu-id="0192c-109">SQLGetDescField and Table-Valued Parameters</span></span>  
 <span data-ttu-id="0192c-110">SQLGetDescField può essere utilizzato per ottenere i valori per gli attributi estesi dei parametri con valori di tabella e delle colonne di parametri con valori di tabella.</span><span class="sxs-lookup"><span data-stu-id="0192c-110">SQLGetDescField can be used to get values for extended attributes of table-valued parameters and table-valued parameter columns.</span></span> <span data-ttu-id="0192c-111">Per ulteriori informazioni sui parametri con valori di tabella, vedere [parametri con valori di tabella &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0192c-111">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="0192c-112">Supporto di SQLGetDescField per le caratteristiche avanzate di data e ora</span><span class="sxs-lookup"><span data-stu-id="0192c-112">SQLGetDescField Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="0192c-113">Per informazioni sui campi di descrizione disponibili con i nuovi tipi di data/ora, vedere [parametri e metadati dei risultati](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span><span class="sxs-lookup"><span data-stu-id="0192c-113">For information about the descriptor fields available with the new date/time types, see [Parameter and Result Metadata](../native-client-odbc-date-time/metadata-parameter-and-result.md).</span></span>  
  
 <span data-ttu-id="0192c-114">Per ulteriori informazioni, vedere [miglioramenti di data e ora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0192c-114">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
 <span data-ttu-id="0192c-115">A partire da [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , SQLGetDescField può restituire `SQL_C_SS_TIME2` (per i `time` tipi) o `SQL_C_SS_TIMESTAMPOFFSET` (per `datetimeoffset` ) invece di `SQL_C_BINARY` , se l'applicazione usa ODBC 3,8.</span><span class="sxs-lookup"><span data-stu-id="0192c-115">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], SQLGetDescField can return `SQL_C_SS_TIME2` (for `time` types) or `SQL_C_SS_TIMESTAMPOFFSET` (for `datetimeoffset`) instead of `SQL_C_BINARY`, if your application uses ODBC 3.8.</span></span>  
  
## <a name="sqlgetdescfield-support-for-large-clr-udts"></a><span data-ttu-id="0192c-116">Supporto di SQLGetDescField per tipi definiti dall'utente CLR di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="0192c-116">SQLGetDescField Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="0192c-117">`SQLGetDescField` supporta i tipi CLR definiti dall'utente di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="0192c-117">`SQLGetDescField` supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="0192c-118">Per ulteriori informazioni, vedere [tipi CLR definiti dall'utente di grandi dimensioni &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0192c-118">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="sqlgetdescfield-support-for-sparse-columns"></a><span data-ttu-id="0192c-119">Supporto di SQLGetDescField per colonne di tipo sparse</span><span class="sxs-lookup"><span data-stu-id="0192c-119">SQLGetDescField Support for Sparse Columns</span></span>  
 <span data-ttu-id="0192c-120">È possibile utilizzare SQLGetDescField per eseguire una query sul nuovo campo IRD SQL_CA_SS_IS_COLUMN_SET per determinare se una colonna è una `column_set` colonna.</span><span class="sxs-lookup"><span data-stu-id="0192c-120">SQLGetDescField can be used to query the new IRD field SQL_CA_SS_IS_COLUMN_SET to determine if a column is a `column_set` column.</span></span>  
  
 <span data-ttu-id="0192c-121">Per ulteriori informazioni, vedere [supporto di colonne di tipo sparse &#40;&#41;ODBC ](../native-client/odbc/sparse-columns-support-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="0192c-121">For more information, see [Sparse Columns Support &#40;ODBC&#41;](../native-client/odbc/sparse-columns-support-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0192c-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="0192c-122">Example</span></span>  
  
```  
typedef struct tagCOMPUTEBYLIST  
    {  
    SQLSMALLINT nBys;  
    SQLSMALLINT aByList[1];  
    } COMPUTEBYLIST;  
typedef COMPUTEBYLIST* PCOMPUTEBYLIST;   
  
SQLHDESC    hIRD;   
SQLINTEGER  cbIRD;   
SQLINTEGER  nSet = 0;   
  
// . . .  
// Execute a statement that contains a COMPUTE clause,  
//  then get the descriptor handle of the IRD and  
//  get some IRD values.  
  
SQLGetStmtAttr(g_hStmt, SQL_ATTR_IMP_ROW_DESC,  
    (SQLPOINTER) &hIRD, sizeof(SQLHDESC), &cbIRD);  
  
// For statement-wide column attributes, any  
//  descriptor record will do. You know that 1 exists,  
//  so use it.  
SQLGetDescField(hIRD, 1, SQL_CA_SS_NUM_COMPUTES,  
    (SQLPOINTER) &nComputes, SQL_IS_INTEGER, &cbIRD);  
  
if (nSet == 0)  
    {  
    SQLINTEGER      nOrderID;  
  
    printf_s("Normal result set.\n");  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ORDER,  
            (SQLPOINTER) &nOrderID, SQL_IS_INTEGER,  
            &cbIRD);  
  
        if (nOrderID != 0)  
            {  
            printf_s("Col in ORDER BY, pos: %ld",  
                nOrderID);  
            }  
            printf_s("\n");  
        }  
  
    printf_s("\n");  
    }  
else  
    {  
    PCOMPUTEBYLIST  pByList;  
    SQLSMALLINT     nBy;  
    SQLINTEGER      nColID;  
  
    printf_s("Computed result set number: %lu\n",  
        nSet);  
  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_BYLIST,  
        (SQLPOINTER) &pByList, SQL_IS_INTEGER,  
        &cbIRD);  
  
    if (pByList != NULL)  
        {  
        printf_s("Clause ordered by columns: ");  
        for (nBy = 0; nBy < pByList->nBys; )  
            {  
            printf_s("%u", pByList->aByList[nBy]);  
            nBy++;  
  
            if (nBy == pByList->nBys)  
                {  
                printf_s("\n");  
                }  
            else  
                {  
                printf_s(", ");  
                }  
            }  
        }  
    else  
        {  
        printf_s("Compute clause set not ordered.\n");  
        }  
  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        SQLGetDescField(hIRD, nCol+1,  
            SQL_CA_SS_COLUMN_ID, (SQLPOINTER) &nColID,  
            SQL_IS_INTEGER, &cbIRD);  
        printf_s("ColumnID: %lu, nColID);  
        }  
    printf_s("\n");  
    }  
  
if (SQLMoreResults(g_hStmt) == SQL_SUCCESS)  
    {  
    // Determine the result set indicator.  
    SQLGetDescField(hIRD, 1, SQL_CA_SS_COMPUTE_ID,  
        (SQLPOINTER) &nSet, SQL_IS_INTEGER, &cbIRD);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="0192c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0192c-123">See Also</span></span>  
 <span data-ttu-id="0192c-124">[SQLGetDescField (funzione)](https://go.microsoft.com/fwlink/?LinkId=59351) </span><span class="sxs-lookup"><span data-stu-id="0192c-124">[SQLGetDescField Function](https://go.microsoft.com/fwlink/?LinkId=59351) </span></span>  
 [<span data-ttu-id="0192c-125">Dettagli di implementazione dell'API ODBC</span><span class="sxs-lookup"><span data-stu-id="0192c-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
